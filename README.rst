Vogelwarte
========================

Installation
------------

Install geonode with::

    $ git clone https://github.com/terranodo/vogelwarte
    $ pip install -r shared/requirements.txt 
    $ pip install -e vogelwarte

Usage with Vagrant 
-------------------------

    $ vagrant up production


Usage in production
-------------------

Add your `production` host in /etc/ansible/hosts

    $ ansible-playbook playbook.yml
