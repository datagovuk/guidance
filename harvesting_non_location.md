---
title: Harvesting non-INSPIRE data into data.gov.uk
layout: "default"
---

# Introduction

This guide explains how a public body can transfer its dataset listings in bulk into data.gov.uk. The dataset records (metadata) are listed by the public body on their open data website and they then operate data.gov.uk's "harvester" to transfer them into data.gov.uk.

Public bodies have long been able to add datasets one at a time to data.gov.uk by using the [web form](dataset_form.html). In addition, bulk addition has been possible for location/INSPIRE data, by using the data.gov.uk harvester to collect datasets stored in the public body's GIS system. In November 2014 the data.gov.uk harvester has been extended to work for non-location datasets. This means that sets of data records (sometimes called 'inventories') can be added to data.gov.uk in bulk.

To work with the harvester, a public body's set of records are published on the internet in any one of the recognized formats. These formats represent the most common ones produced by 'open data websites' such as CKAN, DKAN, Socrata or DataShare.

The launch of the new harvesters are timed to support the Local Authorities to publish their metadata on data.gov.uk  about the datasets that local authorities are required to publish locally due to the [Local Government (Transparency Requirements) Regulations](http://www.legislation.gov.uk/uksi/2014/2680/introduction/made). Local authorities are also encouraged to publish their open datasets on data.gov.uk through the [Local Open Data Incentive Scheme](http://incentive.opendata.esd.org.uk/). Through a local government sector led approach, additional fields were requested and added by the LGA, such as function & service categories - these are imported by all of these harvesters. data.gov.uk is being enhanced to make good use of this extra metadata, to aid navigation by dataset type and automatically validate data against schemas.

NB The new harvesters and this guide are only for datasets that are not covered by the INSPIRE legislation. For more about this, see [Location/INSPIRE data](inspire.html).

# How to Publish Datasets

A public body may or may not have a open data web site, but to be harvested into data.gov.uk it needs to ensure it is published in a suitable machine-readable way.

Each dataset should be described in a "metadata record", giving details about the dataset, such as: title, description and web link to download the data file. The metadata records need to be published:

* in a machine-readable format that data.gov.uk recognizes - see section "Supported Formats"
* in a suitable place on the public Internet - probably the body's website or data portal

## Supported Formats

| Harvester | Suitability | Example Harvest URL |
| --------- | ----------- | ------------------- |
| DCAT | Triple-stores | http://opendatacommunities.org/data.ttl |
| data.json | Socrata, custom systems | https://nycopendata.socrata.com/data.json |
| CKAN | CKAN | https://open.barnet.gov.uk/ |
| DKAN | DKAN | http://opendata.cambridgeshireinsight.org.uk/ |
| Inventory | DataShare | http://data.bracknell-forest.gov.uk/api/esdInventory |

### DCAT

DCAT has the major advantage that it was designed in an open process by practitioners from around the world of data publishing and has become a W3C recommendation. It has been selected by the EU for the harvesting and republication of data from the 28 EU national data portals including data.gov.uk – the EU-wide portal is in beta and will launch in Autumn 2015. DCAT is also supported by the majority of data portals around the world, including the national government portals in US, Canada, Australia and the large numbers of others that use CKAN and other software.

DCAT is a 'vocabulary' in the RDF Linked Data world, and it is normal to use fields/predicates from other vocabularies where appropriate. Whilst this adds expressiveness, data.gov.uk cannot read every eventuality, so this document publishes the fields/predicates that data.gov.uk expects in [Harvesting Guide Appendix A - DCAT/data.json fields](http://data.gov.uk/sites/default/files/library/Harvesting%20guide.pdf).

DCAT can be seen as somewhat verbose. Whilst it is ideal for linked data systems, it is often preferable to use a simplified version called data.json. The data.json format has the fields we need from DCAT, but removes the namespace prefixes and uses the well-known JSON syntax. This has the benefits of DCAT but is generally much more easily produced – see the section on data.json.

Although CKAN supports DCAT for the core fields, it is recommended to harvest from a CKAN using the CKAN harvester. This is because custom fields often do not map well to DCAT fields and can vary from portal to portal.

The DCAT harvester needs to be given the URL that returns the RDF for all the datasets. Optionally the datasets can be split into a number of pages, accessed using the 'page' parameter. i.e. page 2 would be accessed by appending to the URL: ```?page=2```

### data.json

The data.json format was designed as having the same fields as DCAT, but expressed more simply. It is used extensively for harvesting the American public bodies into data.gov and is gaining popularity elsewhere.

The fields are documented in [Harvesting Guide Appendix A](http://data.gov.uk/sites/default/files/library/Harvesting%20guide.pdf).

The US government provide various tools <http://project-open-data.github.io/> and full details of their implementation (it is similar to the UK definitions): <http://project-open-data.github.io/v1.1/metadata-resources/>

The data.json harvester needs to be given the URL that returns a JSON list containing the datasets. Optionally the datasets can be split into a number of pages, accessed using the 'page' parameter. i.e. page 2 would be accessed by appending to the URL: ```?page=2```

### CKAN

The CKAN software is the most popular data portal software, powering the largest government portals in UK (including data.gov.uk), USA, Canada, Australia and much of Europe. It is open source, meaning there is no organization that can control functionality or usage. Numerous organizations and contractors offer services to administer, customize or host CKAN. The CKAN Association founded in 2014 provides a world-wide community.

Although most of the fields are core to all CKAN sites, it is common to customize fields. data.gov.uk has some customizations, so some translation of records occurs during harvest, and optionally extra metadata fields can be supplied that data.gov.uk will display.

The fields are documented in [Harvesting Guide Appendix B](http://data.gov.uk/sites/default/files/library/Harvesting%20guide.pdf).

The CKAN harvester needs the URL of the CKAN home page, from where it can find its API functions.

### DKAN

DKAN is developed by a US-based consultancy and gives basic CKAN functionality. Although it aims for compatibility with CKAN APIs, as it stands (October 2014) the normal APIs for harvesting are not there, and some fields are expressed differently, so you'll need to use this custom DKAN harvester.

Follow the CKAN field guidance.

The DKAN harvester needs to be given the URL of the DKAN home page, from where it can find its API functions.

### Inventory

Developed for the LGA, this format is only suitable for local authority data and is implemented by DataShare. An XML schema is supplied by ESD for this harvester which checks the elements and basic types before being accepted by the harvester.

The CKAN harvester needs the full URL to the inventory XML file.

Full guidance for this format is here: <http://schemas.esd.org.uk/inventory/InventoryGuidance.pdf>

The schema is here: <http://schemas.opendata.esd.org.uk/Inventory>

# How to Harvest

1. Ensure you have a user account on data.gov.uk and it has been assigned permission for your organization, either as editor or admin. See: [Becoming an editor](becoming_an_editor_or_admin.html)

   Once you've received admin/editor permission then when you log-in you'll see a blue spanner icon and your organization listed underneath when you click it. For example in this screenshot, this user has admin or editor permission for National Health Service and NHS England:
![harvest permissions](images/harvest_permissions.png)

2. Create the harvester

   Click on the blue spanner icon and select 'Dataset Harvesting'.

   Now you should see the harvesting dashboard at <http://data.gov.uk/harvest>:
   ![harvest dashboard/sources](images/harvest_sources.png)

   Note that the harvesters are public, but because you are logged in as an editor/admin you have the ability to create a harvester and see the status of your harvesters. You also see a status message in the yellow box.

   To create the harvester click "Add a harvesting source" and fill out the form and click 'Save':
   ![harvest source form blank](images/harvest_source_form_blank.png)

   Here is an example for a harvesting CKAN server:
   ![harvest source form ckan](images/harvest_source_form_ckan.png)

   And here is an example for harvesting datasets from a DataShare that publishes Inventory XML:
   ![harvest source form inventory](images/harvest_source_form_inventory.png)

   When you click Save it will show you your harvester's details and tell you that the harvest has now been requested.

3. Wait for the harvest and check the results.

   Harvests are started every 10 minutes, and take a few minutes more to complete. If you refresh the harvester's page it will tell you in the 'Status' and 'Last harvest' fields if the harvest is "scheduled" (i.e. waiting to start), "in progress" or when its complete it shows you the results of the "Last Harvest". (If you are not logged-in then status is not shown).

   A successful harvest will look like this:
   ![harvest source harvested](images/harvest_source_harvested.png)

   If you do get errors listed, then consult the section later on called "Harvest Errors".

4. Harvest again when your datasets need updating

   You can do another harvest by clicking the "Refresh source" button on the harvester page (remember to be logged-in to be able to see the button)

   data.gov.uk will shortly add a feature to automatically schedule harvests on a weekly basis.


# Harvested datasets

A harvested dataset looks mostly like other datasets on data.gov.uk:
![harvested dataset](images/harvest_dataset.png)

## Details of the harvest

When someone views a dataset that have been harvested, they see a few extra fields listed towards the bottom of the page:
![harvested dataset - additional information](images/harvest_dataset_additional.png)

The harvester has added: "Harvest URL", "Harvest date" and "Harvest GUID". The GUID is the dataset's ID as it was in the harvested system e.g. the CKAN "id", DCAT URI or the Inventory "inv:Identifier".

Not all of the publishing sources or harvesters cover all the fields, so for example Temporal Coverage operates differently in the Inventory format, and the DCAT harvester doesn't include it yet. We hope to fill in these gaps in time.

## Five Stars of Openness

![five stars of openness](images/five_stars.png)

The 'Openness rating' is automatically calculated for a dataset shortly after harvest. It checks if the licence is open, if the resource links work ok and if the resource formats are open and linked. The resulting score is between 0 and 5 stars. If you hover the mouse pointer over the stars then an explanation of the scoring is provided. The overall score is the highest of all the resources, so if you have 3 PDFs (score 1) and a CSV (score 3), then the overall score is 3. There is more about the scheme at: <http://5stardata.info/>

Often this is a useful driver to improve the data or the metadata. For example releasing data as CSV instead of Excel files gets you to 3 stars instead of 2 (although it is good to provide both if you have them).

Also often this indicates problems with the dataset record - maybe the URL to the data was mistyped, or only goes to a web page about the data. Or maybe the harvester has not transferred the details accurately from your site - contact us in that instance. These are easily fixed and then you reharvest.

Occasionally the automatic calculation is wrong - it misidentified the format of your file. Do contact us and we can try and improve it.

## Theme
![theme](images/theme.png)

The 'theme' of a dataset is automatically set on harvest. It is decided by data.gov.uk, based on the title, description and tags of a dataset. Local Authority datasets that have their service or function fields filled in will have their theme decided mainly on those.

This automatic system is generally a lot more consistent than asking humans to categorize datasets(!) And it makes it easy to recategorize them when the themes change as they occasionally do.

There are plenty of cases where a dataset could arguably be in another theme. Since there can often be disagreement about marginal topics, such as if 'planning permission' data should be in 'Environment' or 'Towns & Cities', or 'unemployment stats' goes in 'society' or 'economy'. We'll only consider changing a dataset's theme if it is completely wrong, such as if playground data ended up in 'Economy'. And even then, it would tend to be only we're generally only interested if there are a number of similar datasets. With 20000 datasets, getting a couple of lone datasets correctly categorized is not a priority. But if you think you have a case for a useful recategorization, do contact us.

# Harvest Errors

It is not unusual to see errors on the first harvest. Often it is simple to put right, either in the harvester configuration or it has revealed problems with how the datasets are published. Here are some error messages and tips for solving them:

* **Unable to get content for URL** There was some sort of connection error contacting the publishing site, or the publishing site gave an error for this URL. Check you've configured the harvester with the correct type and URL to go with that type. Some harvesters need the home page of the site, and some need a specific sub-url. Very occasionally these errors are just down to the internet being unreliable.

* **Failed to parse or validate the XML document** There is something wrong with the structure of the published Inventory content. Check that the URL is actually an Inventory XML file. Check it validates against the Inventory schema. Check the version of the schema is the same as the one data.gov.uk uses, which is given on the harvester edit page.

* **System error** / **Validation Error** Something has unexpectedly gone wrong internally data.gov.uk. Please contact the team to fix the problem.

Hopefully the detail of the error messages and these hints provide enough information to solve the issues. If something is still not clear, or data.gov.uk is not working as it should, please contact us.

# Local Authority data schemas

The Local Government Association (LGA) has released schemas for key datasets, for example Public Toilets and LA Spend Transactions. When publishing metadata on these datasets, Local Authorities should include the URL for the schema that it uses. This allows users to understand the format of the data. It also allows them to do basic validation that the file is formatted correctly. Indeed data.gov.uk intends to provide an automatic checking service, to validate the data files against the schemas.

The schema should be referred to in the metadata by the URL which downloads the schema file. (Rather than the URL to a web page about the schema, which is not machine-readable.) ESD is looking to improve the process to get the URL, but currently you need to follow these instructions:

1. Browse to the schema page in Firefox or Chrome. e.g. for Spend data it is:
<http://csvchecker.opendata.esd.org.uk/spend>

2. Fill in the form saying what options you have chosen for the fields that have options

3. Open the developer toolbar and click on the 'Network' tab/ (i.e. enable it to record the network requests)

4. On the web page press "Validation File". (You should get a download dialog box - ignore it)

5. In the Network tab you'll get a list of URLs loaded - its the first one you need. Copy and paste it into the correct field, which is "conformsTo" (data.json/DCAT/Inventory) or "schema_url" (CKAN).

It should look a bit like:
```http://csvchecker.opendata.esd.org.uk/schema/downloadjsonschema?schemaId=spend&majorVersion=0&requiredFieldIds=```
