---
title: Harvesting non-INSPIRE data onto data.gov.uk
layout: "default"
---

# Introduction

This guide explains how a public body can transfer its dataset listings in bulk into data.gov.uk. The dataset records (metadata) are listed by the public body on their open data website and they then operate data.gov.uk's "harvester" to transfer them into data.gov.uk.

Public bodies have long been able to add datasets one at a time to data.gov.uk by using the [web form](dataset_form.html). In addition, bulk addition has been possible for location/INSPIRE data, by using the data.gov.uk harvester to collect datasets stored in the public body's GIS system. In November 2014 the data.gov.uk harvester has been extended to work for non-location datasets. This means that sets of data records (sometimes called 'inventories') can be added to data.gov.uk in bulk.

To work with the harvester, a public body's set of records are published on the internet in any one of the recognized formats. These formats represent the most common ones produced by 'open data websites' such as CKAN, DKAN, Socrata or DataShare.

The launch of the new harvesters are timed to support the Local Authorities to publish their metadata on data.gov.uk  about the datasets that local authorities are required to publish locally due to the [Local Government (Transparency Requirements) Regulations](http://www.legislation.gov.uk/uksi/2014/2680/introduction/made). Local authorities are also encouraged to publish their open datasets on data.gov.uk through the [Local Open Data Incentive Scheme](http://incentive.opendata.esd.org.uk/). Through a local government sector led approach, additional fields were requested and added by the LGA, such as function & service categories - these are imported by all of these harvesters. data.gov.uk is being enhanced to make good use of this extra metadata, to aid navigation by dataset type and automatically validate data against schemas.

NB The new harvesters and this guide are only for datasets that are not covered by the INSPIRE legislation. For more about this, see [Location/INSPIRE data](inspire.html).

# How to Publish Datasets
A public body may or may not have a open data web site (see Appendix C - Rationale for Using a Data Portal), but to be harvested into data.gov.uk it needs to ensure it is published in a suitable machine-readable way.
Each dataset should be described in a “metadata record”, giving details about the dataset, such as: title, description and web link to download the data file. The metadata records need to be published:

* in a machine-readable format that data.gov.uk recognizes - see section "Supported Formats"
* in a suitable place on the public Internet - probably the body's website or data portal

## Supported Formats

| Harvester | Suitability | Example Harvest URL |
| --------- | ----------- | ------------------- |
| DCAT | Triple-stores | http://opendatacommunities.org/data.ttl |
| CKAN | CKAN | https://open.barnet.gov.uk/ |
| DKAN | DKAN | http://opendata.cambridgeshireinsight.org.uk/ |
| Inventory | DataShare | http://data.bracknell-forest.gov.uk/api/esdInventory |
| data.json | Socrata, custom systems | https://nycopendata.socrata.com/data.json |


