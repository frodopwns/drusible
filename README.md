Drupal Local
================

Build out a Drupal dev environment with ease.

Prereqs
-------

- VirtualBox
- Ruby
- Vagrant 1.1+
- Ansible

Install
-------

Once you have these requirements installed, cd to the `drupallocal` dir and run:

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
    mysql -u root -e "create databse newsite;"

Navigate to http://192.168.33.15/newsite to install (note: the db user and pw are 'root')