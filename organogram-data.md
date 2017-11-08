---
layout: "default"
title: "Organogram data - Staff Roles and Salaries - publishing by central government"
---

*NB On 3rd October 2016 there was a [transition to a new system](organogram-transition.html)*

The Prime Minister committed central government and agencies to publish organograms of all staff positions from October 2010. The data includes the hierarchy of senior staff, including names, grades, job titles & salaries and numbers of junior staff that report to them.

Prime Minister's letter: [Letter to government departments on opening up data, May 2010](https://www.gov.uk/government/news/letter-to-government-departments-on-opening-up-data)

## Which bodies are required to do this?

The guidance applies to all bodies within central government as classified by the Office for National Statistics. This includes:

 * departments
 * non-ministerial departments
 * agencies
 * NDPBs
 * trading funds
 * NHS bodies - CCGs, Trusts, Foundation Trusts, SHAs
 * research councils

The ONS classifications can be found the "index" tab: [Public Sector Classification Guide, September 2015 (Excel)](http://www.ons.gov.uk/ons/rel/na-classification/national-accounts-sector-classification/classification-update-and-forward-workplan--september-2015/rft-table-1.xls)

There are a limited number of exceptions to the requirement to publish:

 * intelligence agencies
 * public corporations (financial and non-financial)
 * parliamentary bodies

Staff who work for intelligence agencies should not be reported in the organogram.

NB Local authorities publish their senior staff data in a different format - see the LGA guidance: http://schemas.opendata.esd.org.uk/OrganisationStructure

## Timing

The data is collected twice a year - snapshots of the roles on 31st March and 30th September, to be published on data.gov.uk by 6th June and 6th December respectively.

## Published data

Organograms are published as:

* Visualisations/diagrams at <https://data.gov.uk/organogram/>.
* Raw data in CSV format in data.gov.uk [datasets in the Organograms collection](https://data.gov.uk/data/search?q=&collection=Organogram)

## About the data

### Senior roles

SCS pay band 2 (or equivalent) and above - name of the person, pay (in £5k pay bands), grade, unit, contact phone/email, job title, role reported to, full time equivalent (FTE), salary cost of reports, professional/occupational group.

SCS pay band 1 (or equivalent) - same as for SCS 2, but without the name or pay (which is included in the cost of team reports).

### Junior roles

Below SCS 1 (or equivalent) - unit, senior role reported to, grade, payscale range, generic job title, number of posts in FTE, professional/occupational group.

### Schemas

data.gov.uk provide schemas for the senior and junior CSV files. These describe the fields in greater detail and allows for some automated validation of the files.

  [Organogram schemas by data.gov.uk](https://github.com/datagovuk/schemas/tree/master/organogram)

## Publication process

The Cabinet Office provides departments with an Excel template file, which is completed with the data and is then submitted into the data.gov.uk Organogram Tool. This system performs validation, ensures salaries are rounded to the nearest 5k and converts the data into RDF format. The RDF is put into the organogram triple store (for SPARQL queries) and served in the Linked Data API.

In the future, the CSV data will be provided for download in dataset records in data.gov.uk automatically. So far, several organizations have provided their own copies of the organogram data in CSV format on data.gov.uk and gov.uk manually.

## Publication FAQ

#### Q: Where is the detailed guidance for completing the spreadsheet?

Publishers can download the guidance about preparing the data here:

[Organograms and Senior Salaries - preparing the data](https://data.gov.uk/publisher-files/organogram_docs/OrganogramsPreparingTheDataGuidanceSeptember2016.pdf)

If you are not already logged into data.gov.uk it will prompt you to log in first. If your user account does not have 'editor' or 'admin' permission, then you will need to obtain that first – see [Becoming and editor or admin](becoming_an_editor_or_admin.html).

#### Q: Where can I get the spreadsheet template?

Publishers can download the latest spreadsheet template from data.gov.uk:

[Blank_Organogram_Template_latest.xls](https://data.gov.uk/publisher-files/organogram_docs/Blank_Organogram_Template_latest.xls)

If you are not already logged into data.gov.uk it will prompt you to log in first. If your user account does not have 'editor' or 'admin' permission, then you will need to obtain that first – see [Becoming and editor or admin](becoming_an_editor_or_admin.html).

#### Q: Can I publish data for past periods?

Yes, you can now with the [new system](organogram-transition.html). All the past periods are shown on the Organogram Publication page.

#### Q: Can a published organogram be replaced or removed?

Yes, you can more easily with the [new system](organogram-transition.html). On the Organogram Publication page, find the row with the date you want to delete, and next to it click 'Delete'.

#### Q: How do I transfer my data onto a fresh spreadsheet template?

A number of upload problems can be solved by transferring the data from your existing spreadsheet file to a fresh organogram template file. This is quick to do if you use these instructions:

* Copy the entire "reference" sheets across: "(reference) units", "(reference) generic-job-titles", "(reference) junior-grades". If you don't then you'll find the other sheets won't validate.

  In each sheet, press Ctrl-A (Windows) or &#8984;-A (Mac) to select all the cells and then from the Edit menu select 'Copy'. Open the new organogram template file, go to the sheet of the same name and from the Edit menu select 'Paste'.

* You don't need to copy the "working" sheets if you don't want to - the system doesn't need them.

* Copy the "final data" sheets. NB you need to be aware of two things:

    1. Instead of normal "Paste" you must use "Paste special" and select "Values". Otherwise the cells that are invalid will not show up with a red background any more. (You would have overwritten the cells' "conditional formatting".)

    2. The copy needs to be done in parts because you can't paste into the protected/locked cells, which are the header (first) row and the greyed-out columns. To be specific, here are the ranges to copy and paste:

        Sheet                      | Copy cells | Paste in the new workbook at
        ---------------------------|------------|-----------------------------
        (final data) senior-staff  | A2:N2000   | A2
        (final data) senior-staff  | P2:R2000   | P2
        (final data) junior-staff  | A2:E6000   | A2
        (final data) junior-staff  | H2:J6000   | H2

* When pasting the (final data) you may be asked "A formula or sheet you want to move or copy contains the name 'listJobTitle', which already exists on the destination worksheet. Do you want to use this version of the name?". Answer "Yes". This appears several times - just keep clicking "Yes".

## Publication problems and solutions

#### "Validation error(s) during load"

If you upload your Excel file and get this error then it means that there is a problem with one or more data rows in the spreadsheet, as identified by the spreadsheet's own validation.

The spreadsheet should identify the row with the problem using the red colour, and if you've avoided using normal paste, the problem cells will also be red.

However, the upload error message should give the clearest indication of both the nature of the problem and where it is, naming the specific sheet and either row or cell.

While working in the spreadsheet, please refer to the validation indicator, which helps you identify when these problems have been solved:

![spreadsheet validity indicator - workbook](images/organogram_spreadsheet_workbook_invalid.png)

First look at the last indicator 'WORKBOOK VALID?' - green means the file is all ok, or red means there is a problem.

If there is a problem then consult the other two indicators above. Red colours indicate whether the problem is in this sheet ("(final data)-junior staff") or the Senior sheet ("(final data)-senior staff").

For each sheet which has the problem, check the end of each row, where the column is titled "Valid?". Search for the row with the red colour and fix the problem in that row.

![spreadsheet validity indicator - row](images/organogram_spreadsheet_invalid.png)

More recent versions of the spreadsheet help you further by highlighting red the cell with the problem. A couple of versions of the spreadsheet have an extra column called "Invalid cell (Excel 2011+)" which tells you the column with the problem, although it didn't give accurate information. Also if you have this column in the '(final data) junior-staff' sheet then it will be problematic - if this is the case, please see information below about an "older spreadsheet template" before continuing.

Once all problems are resolved and the 'WORKBOOK VALID?' indicator has gone green and you still get an error when you try to upload it, then [contact us](http://data.gov.uk/contact), supplying the file in question.

#### Older spreadsheet template"

Older spreadsheet templates (e.g. from 2010) can cause problems because they have a different structure.

Follow these steps to find and solve the fault:

* If the '(final data) junior-staff' sheet has "Invalid cell (Excel 2011+)" in cell L1 then this will be causing the problems. This is the case for the spreadsheet template issued on 10/5/16 - "Blank-Organogram-Template_20160510.xls". [Contact us](http://data.gov.uk/contact) to get this column removed, or to get the latest template, into which you can [copy and paste your data in](#q-how-do-i-copy-and-paste-my-spreadsheet-data-onto-a-new-template-spreadsheet).
* If your spreadsheet template was from approximately 2010 then it is too old. [Contact us](http://data.gov.uk/contact) to get the latest template and [copy and paste your data into it](#q-how-do-i-copy-and-paste-my-spreadsheet-data-onto-a-new-template-spreadsheet).
* Check that the key sheets are still called "(final data) senior-staff" and "(final data) junior-staff". Check that on sheet "(final data) junior-staff" there is still the validation block is still in column X in rows 1 to 6. If you can't fix any problems, [contact us](http://data.gov.uk/contact) to get the latest template and [copy and paste your data into it](#q-how-do-i-copy-and-paste-my-spreadsheet-data-onto-a-new-template-spreadsheet).

![spreadsheet validity indicator - workbook](images/organogram_spreadsheet_workbook_invalid.png)

If you still get the error on upload, you could try getting a fresh template and copy and paste the data across to it.

#### No sheet named <'(reference) units'>

Follow these steps to find and solve the fault:

* Check that the spreadsheet opens alright in Excel.
* Check that the spreadsheet is not password protected. (It would prompt for the password when you open it in Excel.)
* Check that the key sheets are still called "(reference) units", "(final data) senior-staff" and "(final data) junior-staff". If not, simply rename them back to these names.

#### Organogram has not appeared publicly

Here is a check-list for when you've uploaded organogram data and don't see it appear at <http://data.gov.uk/organogram/>.

* Check you are looking at the right Department/Public body.

  ![organogram department/public body selector](images/organogram_department_selector.png)

* Check you are looking at the right "Version" (date) in the viewer.

  ![organogram version slider](images/organogram_version.png)

* Check that on the Publication page, the relevant row has a Publish status of "Done". (i.e. you have uploaded the file, ticked Sign off and clicked Publish)

  ![organogram published state](images/organogram_published_state.png)
