---
title: Themes
layout: "default"
---

## Introduction

Datasets are categorized against a small number of 'themes', which helps users understand the distribution of subjects in data.gov.uk and to filter to a specific subject when searching or browsing.

![theme](images/theme.png)

## Automatic categorization

The theme of a dataset is automatically either with the button on the dataset form or when it is harvested.

The categorization route looks at the title, description and tags of the dataset and scans them for known keywords associated with each theme. The keywords are stemmed, to ensure that variations (such as 'crime', 'crimes', 'criminal', 'criminality') are also detected.

This automatic system has been found to be generally a lot more consistent than asking humans to categorize datasets(!) And it makes it easy to recategorize them when the themes change as they occasionally do.

The usual reason for a miscategorization is that the description of the data is too specific. Try adding a sentence to the description giving a simple context for the data e.g. A dataset described as a "hydrographic survey" could be too specific (and not many users will understand it either) so you might add "A hydrographic survey maps the shape of the bottom of the ocean" which would have the recognized keywords "map" and "ocean".

The list of keywords are listed in this file: https://github.com/datagovuk/ckanext-dgu/blob/master/ckanext/dgu/themes.json as "topics". If you have suggestions for additional keywords then please [contact us](http://data.gov.uk/contact) and we'll add them.

There are plenty of cases where a dataset could arguably be in another theme. Since there can often be disagreement about marginal topics, such as if 'planning permission' data should be in 'Environment' or 'Towns & Cities', or 'unemployment stats' goes in 'society' or 'economy'. We'll only consider changing a dataset's theme if it is completely wrong, such as if playground data ended up in 'Economy'. And even then, it would tend to be only we're generally only interested if there are a number of similar datasets. With 20000 datasets, getting a couple of lone datasets correctly categorized is not a priority for data.gov.uk. But if you think you have a strong case for a useful recategorization, do [contact us](http://data.gov.uk/contact).

### Category mappings

Some datasets are already categorized according to another system and a mapping has bee provided to data.gov.uk:

Local Authority datasets that have their service (`la_service`) or function (`la_function`) fields filled in (according to the [esd vocabularies](http://standards.esd.org.uk/?)) will have their theme decided on those.

Location/INSPIRE datasets should have one of the [34 INSPIRE themes](http://inspire.ec.europa.eu/index.cfm/pageid/2/list/7) in the GEMINI2 metadata (`gmd:descriptiveKeywords`) and this will map directly to a data.gov.uk theme.
