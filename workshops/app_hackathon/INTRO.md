## Lab 2a | ObserverApp Hackathon

### Abstract
Do you love geospatial datasets, viz and all things contrails? Then suit up for a great hackathon!

We'll go spelunking in a handful of compelling datasets, 
with our initial bearing centered on images captured by the Contrails Observer App ([iOS](https://apps.apple.com/us/app/contrails-observer/id6454432163) and [Android](https://play.google.com/store/apps/details?id=com.breakthrough.contrails&hl=en_US&pli=1)), 
a mobile phone app for community-generated observations of contrails.

Curated datasets include:
- Contrail App images *(where people see contrails!)*
- ADS-B waypoints *(where the airplanes are at!)*
- GOES mesocale images *(where satellites are snapping pics!)*
- GOES contrail-detections *(where satellites+computer vision see contrails!)*
- PyContrails CoCip polygons *(where we expect contrails should be!)*

What you'll need:
- a computer with dev environment of your choice
- a Google Cloud Platform account ([sign up is free and easy](https://console.cloud.google.com))
- BigQuery access

What you might want:
- the gcloud command line tool ([gcloud](https://cloud.google.com/sdk/docs/install))

For BigQuery access, please send an email to:
> - address: `nick.masson@breakthroughenergy.org`  
> - subject: `Lab2a | BQ access`
> - body: `<email associated with your google cloud account>`

--------

### Get Started

---------

### Data Dictionary

### images
The image files themselves can be found a public Google Cloud Storage bucket: `gs://2024-06-contrails-workshop/contrails_observerapp/images/*`.

The filenames reflect the `id` field in the BigQuery image tables.

#### image metadata
A BigQuery table with image metadata, including location, timestamp, phone make/model and positional sensor data.

Table URI: `contrails-301217.workshop_observerapp.image_metadata`

Schema:

| field         | type      | 
|---------------|-----------|
| id            | STRING    | 
| orientation   | RECORD    |                         
| magnetometer  | RECORD    |                         
| gyroscope     | RECORD    |                          
| accelerometer | RECORD    |                          
| focalLength   | STRING    | 
| model         | STRING    | 
| timestamp     | TIMESTAMP | 
| latitude      | FLOAT     | 
| longitude     | FLOAT     |

#### image field-of-view
A BigQuery table with flight-level polygon intersections based on the image's field of view.
Specifically, the orientation of the camera for an image is projected out in space (a cone from the surface of the earth),
and intersected with standard aircraft flight levels.

The polygons for a given image at a given time effectively represent what the camera was "seeing" at time of image capture.

Table URI: `contrails-301217.workshop_observerapp.image_field_of_view`

Schema:

| field    | type     |
|----------|----------|
| id       | STRING   |
| geometry | GEOMETRY |
| level    | INTEGER  |

### ADS-B aircraft waypoints
A BigQuery table with global flight traffic waypoints, with waypoints (one per minute) for all commercial aircrafts.

These data span at least 12 hours prior to each image's `timestamp`.

Table URI: `contrails-301217.workshop_observerapp.adsb_clean_resampled`

Schema:

| field              | type      |
|--------------------|-----------|
| timestamp          | DATETIME  |
| position           | GEOGRAPHY |
| flight_level       | INTEGER   |
| altitude_baro      | FLOAT     |
| icao_address       | STRING    |
| tail_number        | STRING    |
| flight_number      | STRING    |
| aircraft_type_icao | STRING    |
| airline_iata       | STRING    |

### Google GOES contrail detections
A BigQuery table with line-string geometry objects, 
each line-string geometry object representing a contrail object as predicted by Google's
computer vision algos applied to GOES satellite imagery, 
as visualized in the [Google Contrail Explorer](https://contrails.webapps.google.com/main?imagetype=cirrus&latitude=36.019&longitude=-101.768&zoom=1.03&time=1695672439).

| field     | type      |
|-----------|-----------|
| timestamp | TIMESTAMP |
| geometry  | GEOGRAPHY |

### GOES Mesoscale imagery
Some of the ObserverApp images co-occur with imagery captured by the GOES Mesocale satellites.

The [`goes_mesoscale_ids.json`](./goes_mesoscale/goes_mesocale_ids.json) file
itemizes those images that fall under view of the GOES Mesocale sats.

See the [`Render GOES Mesoscale.ipynb`](./references/Render%20GOES%20Mesoscale.ipynb) notebook
for an example of how to pull down and render GOES Mesoscale imagery that co-occurs with a target image.

