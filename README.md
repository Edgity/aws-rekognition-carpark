## The Approach
Utilising AWS rekognition to recognise carparks from aerial photography.  Including scripts to create labelled datasets from polygon feature classes and WMS aerial web services.

Our aim is to use existing spatial data from other open data providers to train ML models.
These ML models can then be applied to other aerial photography from other locations to identify the same features.

## The Source Data
We will use open data from the City of Melbourne, Australia and Victorian open data aerial image services.
For Aerial Imagery for the Melbourne region we will use this WMS web service, to create the labeled datasets.
https://base.maps.vic.gov.au/wms?request=getcapabilities
https://base.maps.vic.gov.au/wms?service=WMS&request=GetMap&version=1.1.1&format=image/jpeg&width=800&height=600&srs=EPSG:4326&layers=AERIAL_WM&styles=default&bbox=144.96957338510637,-37.81594357654889,144.9696834034373,-37.81578280489754

To identify car parks in Melbourne, we will be using the melbourne carpark web service, but will need to format into GeoJSON centroids.
https://data.melbourne.vic.gov.au/Transport-Movement/On-street-Parking-Bays/crvt-b4kt 

## Requirements
The scripts in this repo are designed for Python 3 and require common libarys such as GeoPandas.
You will also need to run this command in a terminal session to allow for Geopandas (fiona) to read from HTTPS services.
```
cd /Applications/Python\ 3.7/
./Install\ Certificates.command
```