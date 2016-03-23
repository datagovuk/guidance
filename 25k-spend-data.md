---
layout: "default"
title: "£25k Spend data - publishing by central government"
---

Central government bodies (including NHS) are required to publish the details of their expenditure transactions every month. This document provides links to the official guidance and details of how to add it to data.gov.uk.

## Which bodies are required to do this?

> This guidance applies to all bodies within central government as classified by the Office for National Statistics, including departments, non-ministerial departments, agencies, NDPBs, Trading Funds and NHS bodies

(from [HMT Guidance](https://www.gov.uk/government/publications/guidance-for-publishing-spend-over-25000))

The ONS classifications can be found the "index" tab: [Public Sector Classification Guide, September 2015 (Excel)](http://www.ons.gov.uk/ons/rel/na-classification/national-accounts-sector-classification/classification-update-and-forward-workplan--september-2015/rft-table-1.xls)

and includes for example:

  * Clinical Commissioning Groups (CCGs)
  * NHS Trusts (England)
  * NHS Foundation Trusts (England)
  * Strategic Health Authorities (England)
  * Research Councils

## Timing

> Spend is to be published one month in arrears, ie by the last working day of the month following the month to which the data relates.

(from [HMT Guidance](https://www.gov.uk/government/publications/guidance-for-publishing-spend-over-25000))

## What file format should the data files be?

> The files are to be uploaded in CSV file format. Microsoft Excel files should be converted to CSV.

(from [HMT Guidance](https://www.gov.uk/government/publications/guidance-for-publishing-spend-over-25000))

i.e. not XLS, ODS, PDF etc. Consistency is important for analysis across publishers.

Some bodies choose to provide a PDF in addition to the CSV, however if the process is manual then it is perhaps best to focus on just the CSVs.

## What columns are required?

> The CSV file must have precisely one header line with field names exactly as in the example file supplied.

(from [HMT Guidance](https://www.gov.uk/government/publications/guidance-for-publishing-spend-over-25000))

Mandatory fields: Department family, Entity, Date, Expense type, Expense area, Supplier, Transaction number, Amount, Description

Optional fields: Supplier postcode, Supplier type, Contract number, Project code, Expenditure type

NB: the first row of the file MUST be the column headings (no title or blank rows) and subsequent rows must all be transactions (no 'total' or blank rows).

You must not rename the columns e.g. use "Amount (£)" instead of "Amount".

## What transactions should be included / excluded?

Include most things apart from payments to staff.

See the full list: [HMT Guidance PDF](https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/198197/Guidance_for_publishing_spend_over__25k.pdf) section 4.3

## Can it just be on our own website or must it be on data.gov.uk as well?

> All data must be published and listed on the data.gov.uk index. The metadata descriptions will need to be maintained for all of the published data. Each entity is responsible for ensuring that their data is included on the data.gov.uk website.

(from [HMT Guidance](https://www.gov.uk/government/publications/guidance-for-publishing-spend-over-25000))

## How do I put this onto data.gov.uk?

NB: each publisher should only have ONE 'dataset' for 25k spend data (and another one for GPC spend data). Don't add a new one every month - see [Monthly datasets problem](monthly_datasets_problem.html)

Most publishers should use the data.gov.uk web form to add each month's data:

1. Find your publisher on the [publisher page](https://data.gov.uk/publisher) and click on it.
2. Now on your publisher's page, if you don't see the '25k spend' dataset straight away, in the search box type "spend" or "expenditure" to find it. If it doesn't already exist then you'll need to [create it](dataset_form.html) and ensure that on the 'Data Files' tab you select "A timeseries record".
3. Click on the dataset.
   ![edit dataset link](images/form_edit_link.png)
4. If you don't see the blue box with "Edit Dataset properties" then either you need to log in, or if you are already logged in then you need to [become 'editor' or 'admin' for your publisher](becoming_an_editor_or_admin.html).
5. Click "Edit Dataset properties"
6. Click on the "Data Files" tab.
7. At the bottom of the table, add the new month's details.
   ![edit dataset link](images/spend_form_files.png)
   * Date: ignore the calendar that pops up that asks for a specific day in the month - just type the month and year in the exact `MM/YYYY` format e.g. `08/2015` for August 2015.
   * File Title: it's not necessary to repeat the date, but there needs to be something - you could just put `Spend transaction`.
   * URL: Paste into this box the CSV file download link. Ensure the link is the one that actually downloads the dataset immediately, rather than a link to a web page. (We suggest you ignore the check button as it is unreliable at detecting if the link is correct, and may fill in the format field inaccurately.)
   * Format: This should be `CSV` to match the file format.
8. Click 'Save and finish'.

Alternatively, if your organization happens to have its own data website (e.g. running CKAN) that is harvested into data.gov.uk, then you can do a similar process to add the dataset to that site instead, and when it harvests it will automatically be added to data.gov.uk as well. This is an excellent way to keep your site and data.gov.uk in step.

## At data.gov.uk can I just provide one link to a web page, which in turn provides the links to all the files?

This is bad practice, because it requires a human to find the actual download link - a computer cannot find it automatically - which is particularly import for aggregating large quantities of spend data for analysis. And even for a human, it is 'yet another barrier' to getting the data.

## How far back must the data be published?

> * new items of central government spending over £25,000 to be published online from November 2010
> * new items of local government spending over £500 to be published on a council-by-council basis from January 2011

from [Prime Minister's letter on transparency May 2010](https://www.gov.uk/government/news/letter-to-government-departments-on-opening-up-data)

It is important to supply data back to 2010/2011 to allow comparison over several years.
