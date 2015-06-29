---
title: Sysadmins
layout: "default"
---

Sysadmins (System administrators) have full rights on data.gov.uk.

Currently the permission is split between Drupal and CKAN, so someone needs to be given permission in both places.

### Drupal

Existing users with the 'administrator' role can be filtered for here: <http://data.gov.uk/admin/people>

An existing sysadmin should edit the user and add the 'administrator' role.

### CKAN

Sysadmins are listed here: <http://data.gov.uk/ckan-admin>

To add one, on the server run this paster command:

    /home/co/ckan/bin/paster --plugin=ckan sysadmin add user_d12345 --config=$CKAN_INI

Where 12345 is replaced with the numeric Drupal id. This is seen in the URL when you edit the Drupal user.


