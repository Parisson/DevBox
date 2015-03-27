Parisson DevBox
===============

Development environment for `Telemeta <https://github.com/Parisson/Telemeta>`_ and `TimeSide <https://github.com/Parisson/TimeSide>`_


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
