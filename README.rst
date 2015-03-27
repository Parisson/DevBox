Parisson DevBox
===============

Development environment for `Telemeta <https://github.com/Parisson/Telemeta>`_ and `TimeSide <https://github.com/Parisson/TimeSide>`_

Our docker composition bundles some powerfull applications and modern frameworks out-of-the-box like: Python, Numpy, Gstreamer, Django, Celery, MySQL, RabbitMQ, uWSGI, Nginx and many more.


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

For TimeSide only + `TimeSide-Diadems <https://github.com/ANR-DIADEMS/timeside-diadems>`_::

    docker-compose -f docker-compose-timeside.yml up

Then browse http://localhost:8000

More infos about the TimeSide docker image: https://registry.hub.docker.com/u/parisson/

and about our apps: https://github.com/Parisson/


Scale it up
------------

For any serious production usecase, **modify** the sandbox passwords and secret keys before anything.

Thanks to the docker container based architecture and the power of Git, all the code, the dependencies and even the data volumes can be easily shared to other devops or rapidly scaled to more massive production environments.

After synchronizing your images and wanted volumes, docker-compose gives us some very, very nice commands to scale all the containers together. For example, increasing the celery based audio worker number to N is not simpler than::

    docker-compose scale worker=N

Stunning!

