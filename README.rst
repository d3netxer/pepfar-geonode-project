{{ project_name|title }}
========================

You should write some docs, it's good for the soul.

Installation
------------

1. Clone this repo

Create a new template based on the geonode example project.::
    
    $ django-admin.py startproject secondary_cities_geonode --template=https://github.com/GeoNode/geonode-project/archive/master.zip -epy,rst,yml

.. note:: You should NOT use the name geonode for your project as it will conflict with the default geonode package name.

Additional Notes
-----

The new project that was created has a new template and static files that we want to use on your existing GeoNode installation. 

Edit the file /etc/apache2/sites-available/geonode.conf and change the following directive from:

    WSGIScriptAlias / /var/www/geonode/wsgi/geonode.wsgi

to:

    WSGIScriptAlias / /path/to/my_geonode/my_geonode/wsgi.py

Add the "Directory" directive for your folder like the following example:

    <Directory "/home/vagrant/my_geonode/my_geonode/">

       Order allow,deny

       Options Indexes FollowSymLinks

       Allow from all

       Require all granted

       IndexOptions FancyIndexing
       
    </Directory>

Restart apache::

    $ sudo service apache2 restart

Edit the templates in my_geonode/templates, the css and images to match your needs.

In the my_geonode folder run::

    $ python manage.py collectstatic


