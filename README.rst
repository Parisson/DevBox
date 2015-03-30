Parisson DevBox
===============

Development environment for `Telemeta <https://github.com/Parisson/Telemeta>`_ and `TimeSide <https://github.com/Parisson/TimeSide>`_ based projects.

This docker based composition already bundles some powerfull applications and modern frameworks out-of-the-box like: Python, Numpy, Gstreamer, Django, Celery, MySQL, RabbitMQ, uWSGI, Nginx and many more.


Install
-------

First install `Git <http://git-scm.com/downloads>`_, `Docker <https://docs.docker.com/installation/>`_ and `docker-compose <https://docs.docker.com/compose/install/>`_, then run these commands in a terminal::

    git clone https://github.com/Parisson/DevBox.git
    cd DevBox
    sh install.sh

On Windows, execute (double-click)::

    install.bat


Start it up
------------

For Telemeta + TimeSide, from the DevBox folder::

    docker-compose up

then browse http://localhost:8000

To start a python console in the python / django environment::

    docker-compose run app examples/sandbox/manage.py shell


For TimeSide only + `TimeSide-Diadems <https://github.com/ANR-DIADEMS/timeside-diadems>`_::

    docker-compose -f docker-compose-timeside.yml up

The REST API is browsable at: http://localhost:8000/api/

Note that the app and the static files are automatically reloaded when the code changes.


Documentation
-------------

 * our docker images: https://registry.hub.docker.com/u/parisson/
 * our apps: https://github.com/Parisson/


Scale it up
------------

Thanks to the docker container based architecture and the power of Git, all the code, the dependencies and even the data volumes can be easily shared to other devops and rapidly scaled to more massive production environments.

For any serious production usecase, before anything, please **MODIFY** all the django sandbox passwords, secret keys, mysql passwords, etc...

After synchronizing your images and wanted volumes to the cloud, docker-compose gives you some very, very nice commands to scale all the containers together. For example, increasing the celery based audio worker number to N is not simpler than::

    docker-compose scale worker=N

Stunning! Imagine you have a cluster with M cores, each core driving one WSGI worker, you get M*N parallel audio and video data processing threads instantaneously fedded by any number of rabbitmq queues :)
