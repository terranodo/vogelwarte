Vogelwarte
========================

Installation
------------

Install Vogelwarte geonode with::

    $ mkvirtualenv vogelwarte
    $ git clone https://github.com/terranodo/vogelwarte
    $ pip install -r shared/requirements.txt 
    $ pip install -e vogelwarte

.. NOTE:: The Vogelwarte specific branch of GeoNode will be installed per requirements.txt

Using ansible for Automated Deploys
-----------------------------------

In order to install for production on a remote machine or to a local VM for development, you will need to install ansible::

     $ sudo pip install ansible

Note: It is advisable to install ansible system wide using sudo

Next, you will need to install the ansible role for geonode::

     $ ansible-galaxy install ortelius.geonode

Setting up a vagrant box
-------------------------

Setup your virtual machine with::

    $ vagrant up production

Usage in production
-------------------

Update /etc/ansible/hosts to include your webservers host or dns entry::

    [webservers]
    ###.###.###.###

Then you can run the playbook to install the Vogelwarte GeoNode project::

    $ ansible-playbook playbook.yml
