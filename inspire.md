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

## Harvesting INSPIRE/Location data

The INSPIRE legislation requires most geo-spatial data to be published according to certain standards, and be registered on data.gov.uk in a certain way. The records must be published in GEMINI2 format and be harvested. Common ways to do this are:

* Metadata records are created at the "UK Location Metadata Editor" website. You fill in the web form to create each record and the website publishes them at a 'WAF service' which data.gov.uk harvests. Geographical software is also required to provide the data to users in a way that fulfils the INSPIRE 'View' and 'Download' requirements.

* Data is stored in a GIS (Geographic Information System). This is common for departments and local authorities that have an established geo-spatial data capability. Commonly used products include the open source GeoNetworks or ArcGIS. The GIS provides a 'WMS service' for users to preview the data and 'WFS service' or 'Atom feed' for users to download the data. The GIS also publishes the metadata records for the datasets at a 'CSW service', which data.gov.uk is then configured to harvest from.

Occasionally publishers have made the mistake of using an existing record as a template and simply using a text editor to change the key fields. The main problem with this is that you need to generate a new `gmd:fileIdentifier`, or data.gov.uk will harvest it and overwrite the record that was the template! To generate a new UUID (universally unique identifier) for this field, just visit <https://www.uuidgenerator.net/>.


