---
layout: "default"
title: "API"
---

The data.gov.uk API is provided by CKAN and extensions.

The CKAN API docs are extensive: <http://ckan.readthedocs.org/en/release-v2.2.2/>

All the action functions return help text detailing parameters etc.

Below are some tips relating to data.gov.uk

## Datasets

If you want to process lots or all the dataset metadata, rather than making tens of thousands of requests, please just download our daily dump in JSON or CSV format: [Datasets JSON](http://data.gov.uk/dataset/data_gov_uk-datasets/resource/ddf2aaf3-1f95-4d97-b8c6-bdbae2e9e7b4) [Datasets CSV](http://data.gov.uk/dataset/data_gov_uk-datasets/resource/e6ce8f79-f026-4b30-b050-b3245663e438)

A list of datasets: <http://data.gov.uk/api/action/package_list>

Details of a dataset: <http://data.gov.uk/api/action/package_show?id=cabinet-office-energy-use>

 * "resources" are the Data files/resources and Additional Links.

### Searching

The parameters to package_search are passed through to SOLR, so consult the SOLR docs for more info.

**Free text** - the `q` parameter works like the [data.gov.uk search box](http://data.gov.uk/data/search) and looks for the specified works in title, description etc.. By default, the best matches are returned first. It uses stemming, so 'fish' also returns results containing 'fishes', 'fishing' etc.

e.g. <http://data.gov.uk/api/action/package_search?q=fish>

**By field** - use the `fq` parameter to filter on particular fields. Returns exact matches. It uses roughly the same syntax as in the URL of the web search.

* Publisher: <http://data.gov.uk/api/action/package_search?fq=publisher:peterborough-city-council>
* Top-level publisher: <http://data.gov.uk/api/action/package_search?fq=parent_publishers:local-authorities>
* Licence: <http://data.gov.uk/api/action/package_search?fq=license_id:uk-ogl> (Although that doesn't include those that mention OGL in the free text 'licence' 'extra' field.)
* UKLP/INSPIRE records: <http://data.gov.uk/api/action/package_search?fq=UKLP:True>
* UKLP unique identifier: <http://data.gov.uk/api/action/package_search?fq=guid:d9d114da-9fb8-4e02-bfde-3ffaba37e917>
* Date modified <http://data.gov.uk/api/action/package_search?fq=metadata_modified:[2014-08-29T00:00:00Z TO 2014-08-30T00:00:00Z]> (i.e. modification of the data.gov.uk record)
* Date created <http://data.gov.uk/api/action/package_search?fq=metadata_created:[2014-08-29T00:00:00Z TO *]> (i.e. creation of the data.gov.uk record)
* By resource URL <http://data.gov.uk/api/action/package_search?fq=res_url:"http://opendatacommunities.org/data/postcodes/dump">

You can also invert the search by prepending `!` to the key. e.g. records with the word 'toilet' which are not UKLP records: <http://data.gov.uk/api/action/package_search?q=toilet&fq=!UKLP:True>

**NB** Remember to escape these URLs. Most browsers will escape these automatically when you click on these example links, but python clients etc. will mostly need them URL encoded (spaces to `%20` etc). And on the command-line remember to quote the whole URL e.g. use single quotes:

    curl 'http://data.gov.uk/api/action/package_search?fq=res_url:"http://opendatacommunities.org/data/postcodes/dump"'


## Organization hierarchy

data.gov.uk uses CKAN organizations to store what is shown as "publisher"s on the front-end.

A list of the organizations: <http://data.gov.uk/api/action/organization_list>

Details of one organization: <http://data.gov.uk/api/action/organization_show?id=cabinet-office&include_datasets=false>

 * "groups" lists the parent group/organization in the hierarchy

You can also get the whole organization tree: <http://data.gov.uk/api/action/group_tree?type=organization>

And the tree below a particular top-level organization: <http://data.gov.uk/api/action/group_tree_section?type=organization&id=department-for-business-innovation-and-skills>
