---
title: Finding data
layout: "default"
---

Whether you know exactly what data you want, or just want to browser, then data.gov.uk provides several tools to help.

## Search by keyword

On the [search page](https://data.gov.uk/data/search) you can click on the search box and type related words ('keywords'), like for a normal internet search engine.

![Search box](images/finding_data_keyword_box.png)

When you press Enter or click on the magnifying glass icon, it will return the results.

![Search results](images/finding_data_keyword.png)

You can change the order of the results using the 'Sort by' drop-down.

![Sort dropdown](images/finding_data_sort.png)

### Keyword search tips 

When using keyword search, you can use advanced operators to enhance your query.
The examples below show how you can use those operators.

* ```"armed forces" expenses``` - search for exact phrases by putting quote marks around them

* ```primary school -care age``` - exclude words or quoted phrases by using a minus sign or NOT

* ```primary OR secondary school``` - use 'OR' to allow alternatives (the default is to 'AND' all of the terms)

The full syntax is explained in the [Lucene documentation](https://lucene.apache.org/core/4_0_0/queryparser/org/apache/lucene/queryparser/classic/package-summary.html#minitoc-area)

You can also search specific fields, ```publisher:cabinet-office res_format:CSV``` searches only for CSV files published by the Cabinet Office.

Some of the fields that are available to you are listed below:

* __title__ - title of the dataset e.g. "Flood Levels"
* __name__ - name of the dataset, as seen in the dataset's URL e.g. "flood-levels"
* __notes__ - long description of the dataset e.g. "Spreadsheet of 42 flood levels, sampled daily"
* __license_id__ - licence code for the data e.g. license_id:uk-ogl
* __publisher__ - publisher names, as found in the publisher's URL e.g. publisher:cabinet-office
* __parent_publishers__ - as for publisher, but includes the dataset publisher's top-level publisher and parents inbetween
* __res_format__ - The format of the resource e.g. format:CSV
* __res_url__ - The URL of the resource e.g. res_url:"http://data.carbonculture.net/orgs/cabinet-office/70-whitehall/reports/elec00.csv"
* __UKLP__ - UKLP/INSPIRE records. This should be True or False e.g. UKLP:True
* __guid__ - UKLP unique identifier e.g. guid:d9d114da-9fb8-4e02-bfde-3ffaba37e917
* __core_dataset__ - Datasets in the National Information Infrastructure (NII). True or False e.g. core_dataset:True
* __metadata_created__ - When the dataset record was created in data.gov.uk. This is a date format - see below
* __metadata_modified__ - When the dataset record was last modified in data.gov.uk. This is a date format - see below. NB this can be updated on the smallest of changes, including bulk updates across the data.gov.uk catalogue.

You can also invert the search by prepending ! to the key. For example, to find all CSV files that are not published by Cabinet Office - ```!publisher:cabinet-office res_format:CSV```

#### Searching with dates 

The __metadata_modified__ and __metadata_created__ fields both expect date ranges. Date ranges should be specified in full ISO 8601 format (such as 1976-03-06T23:59:59.999Z) although some special operators are available, and examples are given below.

* ```metadata_created:[* TO NOW]``` - Show all datasets created.

* ```metadata_created:[NOW-1YEAR TO NOW]``` - Show all datasets created in the last year. You can substitute DAY, or MONTH here.

* ```metadata_modified:[2016-01-01T00:00:00.000Z TO 2016-02-01T00:00:00.000Z]``` - Show all datasets modified in January 2016.


## Search by publisher

If you know the likely publishing organization, find it in the [publisher search](http://data.gov.uk/publisher).

![Publisher search](images/finding_data_publishers.png)

Click on the publisher name to go through to the publisher's page.

![Publisher page](images/finding_data_publisher_page.png)

The publisher's page lists their most popular datasets or you can try the search box. If you want to do the more advanced search, just click on the magnifying glass icon without typing any words, and it will take you to the main search page, but filtered for that publisher.

![Search icon](images/finding_data_search_icon.png)


## Search by location

If you want data that covers a particular part of the UK, you can use the [Map Based Search](http://data.gov.uk/data/map-based-search).

![Filters](images/finding_data_map.png)

It is important to note that although all this search will find many datasets, many other datasets' location have not been catalogued in data.gov.uk, and will not show up using this method of search. In which case you should also try keyword searches. e.g. for datasets in Salford you might also try searching for 'Salford', 'Birmingham' or 'West Midlands' as well as the using the "Map Based Search".


## Filters

You can browse datasets based on a number of criteria such as whether or not it is published, is in the NII or has an OGL licence. These are on the left-hand-side of the [search page](http://data.gov.uk/data/search).

![Filters](images/finding_data_filters.png)

Numbers in brackets denote the number of datasets meeting the criteria (out of the datasets returned for the currently selected search filters). Where criteria overlap, the numbers will add up to more than the total number of datasets. e.g. file formats, because a dataset can have multiple file formats.
