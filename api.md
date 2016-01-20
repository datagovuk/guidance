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

Search on the API is very similar to the [data.gov.uk search page](https://data.gov.uk/data/search). Guidance for [Finding Data](finding_data.html) also applies to this API.

The parameters to package_search are passed through to SOLR, so consult the SOLR docs for more info.

**Free text** - the `q` parameter works like the [data.gov.uk search box](http://data.gov.uk/data/search) and looks for the specified works in title, description etc.. By default, the best matches are returned first. It uses stemming, so 'fish' also returns results containing 'fishes', 'fishing' etc.

e.g. <http://data.gov.uk/api/action/package_search?q=fish>

**By field** - use the `fq` parameter to filter on particular fields. Returns exact matches. It uses roughly the same syntax as in the URL of the web search.

e.g. Publisher: <http://data.gov.uk/api/action/package_search?fq=publisher:peterborough-city-council>

Further examples are at: [Finding Data](finding_data.html#keyword-search-tips).

**NB** Remember to escape these URLs. Most browsers will escape these automatically when you click on these example links, but python clients etc. will mostly need them URL encoded (spaces to `%20` etc). And on the command-line remember to quote the whole URL e.g. use single quotes:

    curl 'http://data.gov.uk/api/action/package_search?fq=res_url:"http://opendatacommunities.org/data/postcodes/dump"'


## Organization hierarchy

data.gov.uk uses CKAN organizations to store what is shown as "publisher"s on the front-end.

A list of the organizations: <http://data.gov.uk/api/action/organization_list>

Details of one organization: <http://data.gov.uk/api/action/organization_show?id=cabinet-office&include_datasets=false>

 * "groups" lists the parent group/organization in the hierarchy

You can also get the whole organization tree: <http://data.gov.uk/api/action/group_tree?type=organization>

And the tree below a particular top-level organization: <http://data.gov.uk/api/action/group_tree_section?type=organization&id=department-for-business-innovation-and-skills>
