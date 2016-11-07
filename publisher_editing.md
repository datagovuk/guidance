---
title: Publisher editing
layout: "default"
---

For more about the creation of publishers, see: [Publisher creation](publisher_creation.html).

## Editing a publisher

A publisher's admins (and parent publishers' admins) and sysadmins can edit the publisher's properties by finding its publisher page and clicking 'Edit':

![publisher edit link](images/publisher_edit_link.png)

The publisher form can be edited:

![publisher edit form](images/publisher_edit.png)

Once changes are complete, click "Save Changes".

## Publisher rename

Government organizations often change names. We have slightly different policies depending on how substantial the change is:

* Straight rename (eg Highways England -> Highways Agency. eg HSCIC -> NHS Digital), with all responsibilities and datasets move to the new name - just edit the existing publisher.

* Bodies merged/dismerged (eg BIS+DECC -> BEIS) or change of mandate or new legal entity created - create replacement publisher and transfer selected datasets.

### Edit existing publisher

In this case, edit the publisher and edit the title.

You should change the URL of the publisher to reflect the name. If there are fewer than about 10 datasets then you can use browser tools to make the URL field editable to do this. Otherwise you'll need to use the command-line tool (since it can't do the change in the 30s limit of a web request) eg:

    screen -x
    source /home/co/ckan/bin/activate && cd /vagrant/src/ckanext-dgu
    python ../ckanext-dgu/ckanext/dgu/bin/publisher_rename.py $CKAN_INI highways-agency highways-england -t 'Highways England'


### Create replacement publisher and transfer selected datasets

1. [Create the new publisher](https://data.gov.uk/publisher/new)
2. Edit the old publisher, mark it as closed and in the "Replaced by" field specify the new publisher.
3. Transfer only the datasets whose responsibility has passed to the new entity.
4. Add editors & admins to the new entity.
5. Move sub-publishers to be under the new entity.