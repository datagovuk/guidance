---
title: Publishing on data.gov.uk - overview
layout: "default"
---

There are two main methods for adding datasets to data.gov.uk:

1. Using the web form. It is a simple & manual process. However it is not suitable for INSPIRE/Location datasets.

2. Using a harvester. You store the dataset records on your own server and they are 'harvested' regularly into data.gov.uk. It requires some set-up, but it is ideal when there is already a published list of datasets on your site (or elsewhere).

Before you need to [register a user account on data.gov.uk and get approved as 'editor' or 'admin' for your publisher](becoming_an_editor_or_admin.html).

## INSPIRE/Location data

The INSPIRE legislation requires most geo-spatial data to be published according to certain standards, and be registered on data.gov.uk in a certain way. The records must be published in GEMINI2 format and be harvested. Common ways to do this are:

* Metadata records are created at the "UK Location Metadata Editor" website. You fill in the web form to create each record and the website publishes them at a 'WAF service' which data.gov.uk harvests. Geographical software is also required to provide the data to users in a way that fulfils the INSPIRE 'View' and 'Download' requirements.

* Data is stored in a GIS (Geographic Information System). This is common for departments and local authorities that have an established geo-spatial data capability. Commonly used products include the open source GeoNetworks or ArcGIS. The GIS provides a 'WMS service' for users to preview the data and 'WFS service' or 'Atom feed' for users to download the data. The GIS also publishes the metadata records for the datasets at a 'CSW service', which data.gov.uk is then configured to harvest from.

[About INSPIRE](inspire.html)
[INSPIRE Guidance and tools](http://data.gov.uk/location/guidance_and_tools)
