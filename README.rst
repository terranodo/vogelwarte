Vogelwarte
========================

Installation
------------

Install geonode with::

    $ git clone https://github.com/terranodo/vogelwarte
    $ pip install -r shared/requirements.txt 
    $ pip install -e vogelwarte

Usage in development mode
-------------------------

run geoserver from within the geonode folder with::

    $ paver start_geoserver

then run Django from within the vogelwarte folder::

    $ python manage.py runserver


Usage in production
-------------------

Edit the apache conf file and poit the wsgi directive to the vogelwarte one:: 

    https://github.com/terranodo/vogelwarte/blob/master/vogelwarte/wsgi.py

Vogelwarte inherits all the geonode settings in /etc/geonode/local_settings.py but also implements it's own for any necessary override.
