Drusible (Vagrant/Ansible Drupal Environment)
================

Build out a Drupal dev environment with ease.

Prereqs
-------

- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- Ruby (should be installed already)
- [Vagrant](https://www.vagrantup.com/downloads.html)
- Ansible (`sudo pip install ansible`)

Install
-------

Once you have these requirements installed, cd to the `drusible` dir and run:

`vagrant up`

then go grab yourself a coffee...

If something goes wrong, refer to Vagrant's [Getting Started
Guide](http://docs.vagrantup.com/v2/getting-started/index.html).

Use
---

    vagrant ssh
    cd /var/www
    drush dl --drupal-project-rename=newsite --yes
    cp newsite/sites/default/default.settings.php newsite/sites/default/settings.php
    mysql -u root -e "create database newsite;"

Navigate to http://192.168.33.15/newsite to install (note: the db user and pw are 'root')

See this project on Drupal.org: [Drusible](https://www.drupal.org/project/drusible)