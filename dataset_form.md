---
title: Dataset form for adding/updating datasets
layout: "default"
---

NB You can't use this method for publishing INSPIRE/Location data. See more [here](inspire.html).

# Add a dataset

1. Ensure you have a user account on data.gov.uk and it has been assigned permission for your organization, either as editor or admin. See: [Becoming an editor](becoming_an_editor_or_admin.html)

2. There are two methods:

   A. Click on the blue spanner icon and choose "Add a new dataset".
      ![spanner method](images/form_add_dataset_spanner.png)

   B. Go to your publisher page and click "Add a new dataset".
      ![publisher page method](images/form_add_dataset_publisher_page.png)

3. Complete the form using the guidance [below](#form-fields-guidance).

4. Click 'Save and finish'. There is more about this [below](#form-submission).

# Edit a dataset

1. Ensure you have a user account on data.gov.uk and it has been assigned permission for your organization, either as editor or admin. See: [Becoming an editor](becoming_an_editor_or_admin.html)

2. Find the dataset you wish to edit and click "Edit dataset properties"
   ![edit dataset link](images/form_edit_link.png)

3. Complete the form using the guidance [below](#form-fields-guidance).

4. Click 'Save and finish'. There is more about this [below](#form-submission).

# Form fields guidance

NB More detailed guidance is available in the [User Guide (PDF)](http://data.gov.uk/sites/default/files/library/User%20guide.pdf)

### Information icons

Many fields have an 'information' icon, which displays more guidance if you hover the mouse over it.

![field hint](images/form_hints.png)

### Timeseries vs Single File

It is very important that you select the right type of dataset. If you are publishing a dataset that will have updates across time (yearly, monthly, etc.) then make sure you select the timeseries option on the data files section. This will allow the date of the file to dictate the sorting, so the latest file is automatically presented on top and everything else falls in chronological order.

If you choose single file and then add subsequent publications, you will have to order them manually. *You should not select single file for datasets that will have new files across time*.

[Monthly datasets problem](monthly_datasets_problem.html)

### 'Check' button

![check button](images/form_check_button.png)

The 'check' functionality allows the system to identify the format of the file and automatically add it to the record, avoiding chances of different spellings. The 'check all URLs' option allows you to check that the URLs entered are all active and working.

If you encounter problems when clicking the 'check' or 'check all URLs' buttons (no format appears in the format box or the check all URLs process takes too long ) don't use them. Manually enter the format of your file (which SHOULD always be CSV or another open format, NOT XLS, HTML OR PDF). This issue arises because some older browsers may not work well with this feature.

# Form submission

## Form errors

When you click "Save and Finish", if there are problems with any field then it will list them at the top, and also with yellow warning triangles on the appropriate tabs, and when you click on the tab red sharded boxes say what the problem is next to the appropriate field e.g.
![form errors](images/form_errors.png)

Occasionally new mandatory fields are added to the form. This can cause form errors to appear when you edit an existing dataset, even if you've not changed anything. In this case, fill in the new field to be able to save it successfully.

If, after clicking 'Save and finish’, you are still in the editing screen then: **YOUR CHANGES HAVE *NOT* BEEN SAVED!**

## Caching

The data.gov.uk site is cached for 1 hour for general users, but not if you are logged in. This means that if you add a dataset or make a change, you will see it has changed straight away, but it will take up to an hour before it becomes visible to another person visiting the site (i.e. someone who does not log in). Please be aware of this when notifying people or announcing releases.
