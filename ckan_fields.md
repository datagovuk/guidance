---
title: CKAN fields harvested
layout: "default"
---

## Introduction

This page describes the technical detail of data.gov.uk's harvesting of CKAN datasets into data.gov.uk. More about harvesting is described here: [Harvesting Data into data.gov.uk - CKAN](harvesting.html#ckan)

### Core dataset fields

| Field key | Value guidance | Example value |
| --------- | -------------- | ------------- |
| name | If there is a clash with an existing dataset in data.gov.uk then it will be modified to have a number suffixed, to make it unique. | river-levels-sussex |
| title | Name of the dataset. No jargon allowed - this is for general public to quickly understand what the data is about. | River Levels in Sussex |
| notes | Longer description of the data, how it was collected, etc. | Recorded daily from automated monitoring stations. Recorded at midday, published by 3pm the same day. Accurate to nearest centimetre. |
| tags | Optional. Key words/phrases that describe the subject of the data. Not displayed, but helps categorize it. | ["transportation", "road safety", "accidents", "casualties"] |
| license_id| CKAN internal id for the data's licence, from CKAN's standard list of IDs. If the license isn't in CKAN's standard list then specify (in free-text) the name of the licence in the most standard way possible. If no standard licence is used then supply the full text of the terms of use. | "uk-ogl" or "OS OpenData Licence" |
| Ignored by DGU: <br>owner_org, maintainer, maintainer_email, author, author_email, relationships | The owner_org/publisher is determined by the value given in the harvester's settings, not the harvested dataset. ||

### Extras

| Field key | Value guidance | Example value |
| --------- | -------------- | ------------- |
| la_service | Service as listed here: http://standards.esd.org.uk/?uri=list%2Fservices More than one can be specified, separated by spaces. | http://id.esd.org.uk/service/190 |
| la_function | Function as listed here: http://standards.esd.org.uk/?uri=list%2Ffunctions More than one can be specified, separated by spaces. | http://id.esd.org.uk/service/437 |
| contact-name, <br>contact-phone, <br>contact-email | Contact details for this dataset. Normally you shouldn't specify these - instead fill them in for the publisher in data.gov.uk and the publisher's datasets will have those details displayed. | "contact-name": "Information Handling Team", <br>"contact-phone": "0208 445 3423", <br>"contact-email": "informationhandling@dft.gsi.gov.uk" |
| foi-name, <br>foi-phone, <br>foi-email, <br>foi-web | Freedom of Information (FOI) contact details for the dataset. Normally you shouldn't specify these - instead fill them in for the publisher in data.gov.uk and the publisher's datasets will have those details displayed. | |
| temporal_coverage-from, temporal_coverage-to | Gives the temporal coverage of the data. Each value can be YYYY, YYYY/MM or YYYY/MM/DD | "temporal_coverage-from": "1979-01-01", <br> "temporal_coverage-to": "2013-12-31" |
| mandate | URLs for the exact part of legislation that brought about the collection of this dataset (or if none, the public commitment or announcement, if available.) | ["http://www.legislation.gov.uk/ukpga/2014/26/section/168/enacted"] |
| update_frequency | Example values: never, discontinued, annual, quarterly, monthly | annual |
| unpublished | Allows publishers to report data that exists but is not published | false |
| geographic_coverage | No need to specify - a better field for spatial coverage will be coming soon. ||
| theme-primary, <br>theme-secondary | Should not be included - data.gov.uk will automatically give it a theme based on keywords in the content. ||

### Resources

| Field key | Value guidance | Example value |
| --------- | -------------- | ------------- |
| name | Text to describe the resource. | Toilet spreadsheet |
| date | Date the resource applies to. Format: YYYY or YYYY/MM or YYYY/MM/DD. A dataset's resources should all have a date value or none should. | 2014/12 |
| url | URL to the file, webpage or API. It is not good enough to simply link to a page of links to the data - all the direct links to the data files must be supplied separately. | https://open.barnet.gov.uk/dataset/d7384c92-5828-41a3-9d12-36d6db5c192f/resource/3e9934ac-492a-4042-971c-fe49bd9ca7e7/download/publictoiletsabfv3.0.csv |
| format | File format. e.g. CSV, XLS, PDF, RDF, SHP, HTML, SPARQL, API. Don't mention if a file is zipped - just the format inside the zip. | CSV |
| resource_type | If it is data, then: file or api Otherwise: documentation | file |
| schema_url | URL of the machine-readable schema that the data conforms to. If it is not a standard format then leave blank. See: Appendix E - Local Authority data schemas | http://schemas.opendata.esd.org.uk/publictoilets/PublicToilets.json?v=0.41 |
| schema_type | The type of schema specified in schema_url. Examples: csvlint or xsd | csvlint |

Local Authorities in particular should make sure they fill in the la_service, la_function, schema_type and schema_url fields.

