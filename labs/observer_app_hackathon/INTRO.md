## Lab 2a | ObserverApp Hackathon

<!-- TOC -->
  * [Lab 2a | ObserverApp Hackathon](#lab-2a--observerapp-hackathon)
    * [Abstract](#abstract)
    * [How to Contribute](#how-to-contribute)
    * [Data Dictionary](#data-dictionary)
    * [images](#images)
      * [image metadata](#image-metadata)
      * [image field-of-view](#image-field-of-view)
    * [ADS-B aircraft waypoints](#ads-b-aircraft-waypoints)
    * [PyContrails CoCip Regions](#pycontrails-cocip-regions)
    * [Google GOES contrail detections](#google-goes-contrail-detections)
    * [GOES imagery](#goes-imagery)
    * [GOES Mesoscale imagery](#goes-mesoscale-imagery)
    * [Perspective Correction](#perspective-correction)
<!-- TOC -->

### Abstract
Do you love geospatial datasets, viz and all things contrails? Then suit up for a great hackathon!

We'll go spelunking in a handful of compelling datasets, 
with our initial bearing centered on images captured by the Contrails Observer App ([iOS](https://apps.apple.com/us/app/contrails-observer/id6454432163) and [Android](https://play.google.com/store/apps/details?id=com.breakthrough.contrails&hl=en_US&pli=1)), 
a mobile phone app for community-generated observations of contrails.

Curated datasets include:
- Contrail App images *(where people see contrails!)*
- ADS-B waypoints *(where the airplanes are at!)*
- PyContrails CoCip polygons *(where we expect contrails should be!)*
- GOES contrail-detections *(where satellites+computer vision see contrails!)*
- GOES full-disk and mesocale images *(where satellites are snapping pics!)*

What you'll need:
- a computer with dev environment of your choice
- a Google Cloud Platform account ([sign up is free and easy](https://console.cloud.google.com))
- BigQuery access

What you might want:
- the gcloud command line tool ([gcloud](https://cloud.google.com/sdk/docs/install))
- familiarity with BigQuery, SQL and BigQuery's [Geography functions](https://cloud.google.com/bigquery/docs/reference/standard-sql/geography_functions)

For BigQuery access, please send an email to:
> - address: `nick.masson@breakthroughenergy.org`  
> - subject: `Lab2a | BQ access`
> - body: `<email associated with your google cloud account>`

--------

### How to Contribute
If you would like to contribute your work at the end of this lab, please:

1. create a new branch on this repo: `/hackathon/<my_lastname>`
2. create a directory for your work: `workshop/app_hackathon/contributions/<my_lastname>_<title>`
3. add your notebook, scripts and any supporting files into your directory
4. open a pull-request to merge your work into `main`, and tag `contrails-internal` as reviewer

We promise to promptly review all proposed contributions.

---------

### Data Dictionary

### images
The image files themselves can be found a public Google Cloud Storage bucket: `gs://2024-06-contrails-workshop/observerapp_hackathon/images/*`.

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

An example of how this data was generated can be found in [this notebook](./references/field_of_view_polygons/Find%20FL%20Polygons.ipynb).

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

### PyContrails CoCip Regions
A BigQuery table with polygon geometries at standard flight levels,
indicating regions where contrails are predicted to have formed with an energy forcing value
relative to a given threshold.

Thresholds are in units of `[J/m]` ([read more here](https://apidocs.contrails.org/ef-interpretation.html)).
A regions with a positive threshold indicates a geography where contrails are expected to have a warming impact
equal or greater than the positive threshold value.
A region with negative threshold indicates a geography where contrails are expected to have a cooling impact
equal or less than the negative threshold value.

The regions in this table do not overlap spatiotemoporally with all images in this lab.
Instead, please see the [regions_ids.json](references/cocip_regions/regions_ids.json) file
for image ids that have at least 4 hours of CoCip region prediction prior to image timestamps.
These images are a subset of the images for which there is also GOES Mesoscale imagery available 
(See the [GOES Mesoscale Imagery](#goes-mesoscale-imagery) section).

Table: `contrails-301217.workshop_observerapp.cocip_regions`

Schema:

| field             | type      |
|-------------------|-----------|
| timestamp         | TIMESTAMP |
| hres_model_run_at | TIMESTAMP |
| flight_level      | INTEGER   |
| threshold         | INTEGER   |
| regions           | GEOGRAPHY |

### Google GOES contrail detections
A BigQuery table with line-string geometry objects, 
each line-string geometry object representing a contrail object as predicted by Google's
computer vision algos applied to GOES satellite imagery, 
as visualized in the [Google Contrail Explorer](https://contrails.webapps.google.com/main?imagetype=cirrus&latitude=36.019&longitude=-101.768&zoom=1.03&time=1695672439).

| field     | type      |
|-----------|-----------|
| timestamp | TIMESTAMP |
| geometry  | GEOGRAPHY |

### GOES imagery
See the [`GOES Examples.ipynb`](./references/goes/GOES%20Examples.ipynb) notebook
for an example of how to pull GOES satellite imagery that co-occurs with a target image.

### GOES Mesoscale imagery
Some of the ObserverApp images co-occur with imagery captured by the GOES
Mesocale regions. There regions are captured with a time resolution of one
minute rather than the standard ten minute resolution.

The [`goes_mesoscale_ids.json`](references/goes/goes_mesocale_ids.json) file
itemizes those images that fall under view of the GOES Mesocale sats. 
The `"regions"` field indicates if the image falls in the GOES Mesoscale M1 or M2 regions.

The [`GOES Examples.ipynb`](./references/goes/GOES%20Examples.ipynb) notebook
also contrails an example of how to pull down and render GOES Mesoscale imagery that co-occurs with a target image.

### Perspective Correction
One important detail to not overlook is the effect of perspective correction on
contrails (and clouds) that are captured in GOES imagery.  Because the satellite
is viewing the Earth at oblique angles (except at one point on the equator),
objects that are off of the ground will appear shifted in the GOES image. 

This is discussed in greater detail in the [`GOES
Examples.ipynb`](./references/goes/GOES%20Examples.ipynb) notebook, where we
also give an example of how to correct for this effect. 
