---
title: Themes management
layout: "default"
---

# Introduction

This page is about administrating themes. For general information about themes, see: [Themes](theme.html)

# Updating keywords

The automatic theme selection is guided by the keywords listed in this file:
https://github.com/datagovuk/ckanext-dgu/blob/master/ckanext/dgu/themes.json

Adding to and improving the keywords in this file is encouraged. Edit the file and commit it. Then to install the keywords into the database, you need to run this on the server:

    source /home/co/ckan/bin/activate
    cd /vagrant/src/ckanext-dgu; git pull
    paster --plugin=ckanext-taxonomy taxonomy load-extras --filename ../ckanext-dgu/ckanext/dgu/themes.json --name dgu-themes
    sudo apache2ctl graceful

# Recategorizing

You can recategorize a single dataset in a theme by editing it and pressing the button in the form.

To do multiple datasets, use the 'theme' script e.g.:

    python ckanext/dgu/bin/theme.py  /var/ckan/ckan.ini recategorize -p health-and-social-care-information-centre -w
