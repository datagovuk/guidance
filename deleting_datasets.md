---
title: Deleting datasets
layout: "default"
---

## Deletion policy

You should NOT delete data that is:

* out of date - It is common to want to compare data over time.

* incorrect - Tracking corrections is important to users. Keep links to anything that was released, but do mark resources that have been later found to be incorrect, as well as providing the link to the corrected data.

* lost - In many circumstances the data still exists somewhere. The National Archives provides a web-cache for many public bodies, where old web pages and files are still available - contact us for more information about this. If all else fails, remove completely lost resources and explain the loss in the description, but the dataset itself should be kept as a record.

* publisher has closed - When a publishing organization closes, even if the responsibility for the data is not transferred to a new publisher, the data is often still useful to users.

The only valid circumstances for deletion are:

* duplicates - if two data.gov.uk datasets link to the same dataset then all the useful information should be added to one of those and the other deleted. If this causes bigger problems then it is acceptable to keep some duplicates. The key thing is not to lose useful metadata.

* test datasets - Ideally test datasets are only created on our test server (contact us for details), but if you create a test dataset on data.gov.uk by mistake then clearly this needs deleting.


## Who can delete datasets?

Because the deletion policy is complex, we require all deletions to be done by sysadmins - this means the core data.gov.uk team only.

However there is an exception for Location/INSPIRE datasets - publishers can 'withdraw' their own datasets (marked with the INSPIRE logo), which is the same as deleting. To do this, log-in as an admin for your publisher, go to the dataset page and in the blue box there is the link to 'Withdraw'. To reinstate the record, update the record (including its timestamp) on your server and reharvest it.

## Requesting deletions

To request datasets are deleted, use the [contact form](http://data.gov.uk/contact) and provide:

1. Links to all the datasets to be deleted

2. Reason for deletion. If it is because there are duplicates, please also supply the links to the datasets which are being kept.


## It didn't get deleted!

When a dataset is deleted by a data.gov.uk sys-admin, you may have to wait up to an hour for it to disappear completely. There are more details here: [Updating problem](updating_problem.html)
