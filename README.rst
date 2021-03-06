qgpkg
========

Introduction
------------

qgpkg implements a `GeoPackage <http://geopackage.org/>`_ extension to store
QGIS mapping information in a GeoPackage database file.

The specification is separated into `QGIS extensions <https://github.com/pka/qgpkg/blob/master/qgis_geopackage_extension.md>`_ and  `OWS context extensions <https://github.com/pka/qgpkg/blob/master/ows_geopackage_extension.md>`_.

qgpkg library and cli
---------------------

gpkg is implemented as a Python library with a command line interface.

Commands::

  usage: qgpkg.py [-h] {info,write,read} ...

  Store QGIS map information in GeoPackages

  optional arguments:
    -h, --help         show this help message and exit

  commands:
    valid commands

    {info,write,read}
      info             GeoPackage content information
      write            Save QGIS project in GeoPackage
      read             Read QGIS project from GeoPackage


QGIS plugin
-----------

The QGIS plugin adds two buttons to the QGIS GUI. One for saving the current
project in a GeoPackage file and one for loading a QGIS project from a
GeoPackage file. The project is read using `this GeoPackage extension <https://github.com/GeoCat/qgpkg/blob/ows-spec/ows_geopackage_extension.md>`_.

Support is given for loading multiple layers and styles from the geopackage.
The example bellow refers to the geopackage multiple_layers.gpkg, on folder `examples <./examples>`_.

.. image:: screenshot_multiple_layers.png
   :width: 70%

Development
-----------

::

    git clone https://github.com/pka/qgpkg.git

Running tests:

::

    apt-get install python-nose

::

    nosetests

For running qgpkg commands from source tree:

::

    alias qgpkg="PYTHONPATH=$(pwd) $(pwd)/qgpkg_cli/qgpkg.py"

License
-------

qgpkg is Copyright © 2016 Sourcepole AG. It is free software,
and may be redistributed under the terms specified in the LICENSE.txt
file.
