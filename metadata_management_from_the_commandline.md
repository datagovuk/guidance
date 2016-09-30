---
layout: "default"
title: "Metadata management from the command-line"
---

## Bulk operations

Datasets

```
ckanapi load datasets -c $CKAN_INI -I health.jsonl
ckanapi load datasets -I health.jsonl -r http://localhost/ -a $APIKEY
```

Deleting datasets

```
python ../ckanext-dgu/ckanext/dgu/bin/delete_bulk.py https://data.gov.uk -f /tmp/delete.txt
(NB ckanapi now has bulk delete too)
```

Organizations

```
ckanapi load organizations -I new-orgs.jsonl -r http://localhost/ -a $APIKEY
```

## Individual operations

Copying a dataset from one CKAN to another

```
ckanapi action package_show id=organogram-cabinet-office -r https://test.data.gov.uk > /tmp/organogram.json
# now delete the id field from /tmp/organogram.json
ckanapi action package_create -c $CKAN_INI -i < /tmp/organogram.json
```