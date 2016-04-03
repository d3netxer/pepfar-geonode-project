{{ project_name|title }}
========================

You should write some docs, it's good for the soul.

Installation
------------

follow directions http://geonode.org/ and install GeoNode. If you are installing on a vagant machine, I recommend using the rudolfochrist/ubuntu-desktop box

Clone this repository

This repo has a new template and static files that we want to use on your existing GeoNode installation. 

Edit the file /etc/apache2/sites-available/geonode.conf:

Change the "Directory" directive for your folder like the following example:

    <Directory "/var/www/">

copy the files in the repos template directory into the following directory: /etc/geonode/templates/

copy the files in the static folder into the /var/www/geonode/static directory   ex:

``sudo cp -R ../../secondary-cities-geonode-project/project_name/static/* .``

Restart apache::

    $ sudo service apache2 restart
    




