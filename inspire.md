---
title: INSPIRE
layout: "default"
---

## INSPIRE Links (for the UK)

* Home page: <http://data.gov.uk/location>
* Guidance and tools: <http://data.gov.uk/location/guidance_and_tools>
* Help: [Location/INSPIRE Helpdesk](mailto:UK-INSPIRE-Help@defra.gsi.gov.uk) (provided by Defra)
* [INSPIRE/Location records on data.gov.uk](http://data.gov.uk/data/search?UKLP=True)

## INSPIRE scope

INSPIRE places obligations on these publishers and sorts of data:

* most UK public bodies (includes central government, local authorities and all other public authorities as defined in the [Environmental Information Regulations 2004](http://www.legislation.gov.uk/uksi/2004/3391/contents/made)).
* geo-spatial data (i.e. the data points contain a location e.g. latitude/longitude or post code etc)
* data that is in any of the [34 INSPIRE themes](http://inspire.ec.europa.eu/index.cfm/pageid/2/list/7), however UK Location encourages ALL geo-spatial data to be published the INSPIRE way
* published data (the law does not compel you to publish data that is not currently published)

For more about INSPIRE's scope, see [UK Location Getting Started - Guide 2 - Organisation and Data Coverage (PDF)](http://data.gov.uk/library/uk-location-getting-started-guide-2-organisation-and-data-coverage).

Examples:

| Dataset | INSPIRE? | Location? | Explanation |
| ------- | -------- | --------- | ----------- |
| [River catchment area boundaries](http://data.gov.uk/dataset/water-framework-directive-river-waterbody-catchments-wms) | Yes | Yes | Its publisher Environment Agency is a government agency, the data falls under the INSPIRE theme "Hydrography", and the data is geo-spatial - it can be plotted on a map. |
| [Road accidents](http://data.gov.uk/dataset/road-accidents-safety-data) | No | Yes | The subject of the data is not covered in the 34 INSPIRE themes so it is not covered by INSPIRE. However the data is Location data - each accident is located using a OS grid reference (and latitude & longitude) so it is geo-spatial. So the publisher could have still published the metadata in GEMINI and provided INSPIRE-style View (WMS) and Download Services (WFS/Atom), but has chosen not to in this case, sticking to basic CSV.|

## Publishing INSPIRE/Location data

The INSPIRE legislation requires most geo-spatial data to be published according to certain standards, and be registered on data.gov.uk in a certain way. The records must be published in GEMINI2 format and be harvested. Common ways to do this are:

* Metadata records are created at the [UK Location Metadata Editor website](https://locationmde.data.gov.uk/). You fill in the web form to create each record and the website publishes them at a 'WAF service' which data.gov.uk harvests. Geographical software is also required to provide the data to users in a way that fulfils the INSPIRE 'View' and 'Download' requirements. For more information, consult the [User Guide to the UK Location Metadata Editor](https://data.gov.uk/sites/default/files/library/Metadata%20Editor%20User%20Guide.pdf)

* Data is stored in a GIS (Geographic Information System). This is common for departments and local authorities that have an established geo-spatial data capability. The most commonly used GIS for data.gov.uk is the open source [GeoNetwork](http://geonetwork-opensource.org/), and commercial ones such as ArcGIS are also in use. The GIS provides a 'WMS service' for users to preview the data and 'WFS service' or 'Atom feed' for users to download the data. The GIS also publishes the metadata records for the datasets at a 'CSW service', which data.gov.uk is then configured to harvest from.


## Harvesting metadata records

Getting your metadata records into data.gov.uk is done by setting up a data.gov.uk 'harvester'. It's recommended that this is configured to run automatically weekly, to ensure that data.gov.uk stays in sync when the publisher updates the records.

For a complete guide to harvesting, consult: [Harvesting Data into data.gov.uk](harvesting.html)

Occasionally publishers have made the mistake of using an existing record as a template and simply using a text editor to change the key fields. The main problem with this is that you need to generate a new `gmd:fileIdentifier`, or data.gov.uk will harvest it and overwrite the record that was the template! To generate a new UUID (universally unique identifier) for this field, just visit <https://www.uuidgenerator.net/>.


