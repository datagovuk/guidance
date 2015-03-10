---
title: Themes
layout: "default"
---

## Introduction

Datasets are categorized against a small number of 'themes', which helps users understand the distribution of subjects in data.gov.uk and to filter to a specific subject when searching or browsing.

![theme](images/theme.png)

## Manual selection

Datasets that are added and edited in the web form can have their theme selected manually. Occasionally the themes may be added or removed from those available - in these circumstances datasets may be automatically recategorized.

## Automatic categorization

The theme of a dataset is automatically when it is harvested or for non-harvested datasets if it has not been set manually.

In this case, the theme is decided by data.gov.uk, based on the title, description and tags of a dataset. Local Authority datasets that have their service (`la_service`) or function (`la_function`) fields filled in will have their theme decided mainly on those. Location/INSPIRE datasets should have one of the [34 INSPIRE themes](http://inspire.ec.europa.eu/index.cfm/pageid/2/list/7) in the GEMINI2 metadata (`gmd:descriptiveKeywords`) and this will map directly to a data.gov.uk theme.

This automatic system has been found to be generally a lot more consistent than asking humans to categorize datasets(!) And it makes it easy to recategorize them when the themes change as they occasionally do.

There are plenty of cases where a dataset could arguably be in another theme. Since there can often be disagreement about marginal topics, such as if 'planning permission' data should be in 'Environment' or 'Towns & Cities', or 'unemployment stats' goes in 'society' or 'economy'. We'll only consider changing a dataset's theme if it is completely wrong, such as if playground data ended up in 'Economy'. And even then, it would tend to be only we're generally only interested if there are a number of similar datasets. With 20000 datasets, getting a couple of lone datasets correctly categorized is not a priority. But if you think you have a case for a useful recategorization, do contact us.


