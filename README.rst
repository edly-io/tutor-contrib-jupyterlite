jupyterlite plugin for `Tutor <https://docs.tutor.overhang.io>`__
===================================================================================

Installation
------------

The plugin is currently not available in tutor public indexes at the moment. To install it you should have access to git repo::

    pip install git+https://github.com/edly-io/tutor-contrib-jupyterlite.git

Then, to enable this plugin, run::

    tutor plugins enable jupyterlite

Then, build image and launch::

    tutor [dev|local] build jupyterlite
    tutor [dev|local] launch
    

You should beware that the ``jupyterlite.<LMS_HOST>`` domain name should exist and point to your server. For instance, if your LMS is hosted at http://learnnow.com, the jupyterlite service should be found at http://jupyterlite.learnnow.com.

If you would like to host the jupyterlite service at a different domain name, you can set the ``JUPYTERLITE_HOST`` configuration variable (see below). When testing Tutor on a local computer, this will be automatically set to http://jupyterlite.local.overhang.io:9500.


Configuration
-------------

- ``JUPYTERLITE_BASE_DOCKER_IMAGE`` (default: ``"{{ DOCKER_REGISTRY }}edlyio/jupyterlite:{{ JUPYTERLITE_VERSION }}"``)
- ``JUPYTERLITE_HOST`` (default: ``"jupyterlite.{{ LMS_HOST }}"``)
- ``JUPYTERLITE_PORT`` (default: ``"9500"``)

These values can be modified with ``tutor config save --set PARAM_NAME=VALUE`` commands.


License
-------

This software is licensed under the terms of the AGPLv3.