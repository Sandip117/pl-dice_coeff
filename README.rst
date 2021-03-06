pl-dice_coeff
================================

.. image:: https://badge.fury.io/py/dice_coeff.svg
    :target: https://badge.fury.io/py/dice_coeff

.. image:: https://travis-ci.org/FNNDSC/dice_coeff.svg?branch=master
    :target: https://travis-ci.org/FNNDSC/dice_coeff

.. image:: https://img.shields.io/badge/python-3.5%2B-blue.svg
    :target: https://badge.fury.io/py/pl-dice_coeff

.. contents:: Table of Contents


Abstract
--------

An app to calculate model testing accuracy by dice coefficient


Synopsis
--------

.. code::

    python dice_coeff.py                                           \
        [-v <level>] [--verbosity <level>]                          \
        [--version]                                                 \
        [--man]                                                     \
        [--meta]                                                    \
        <inputDir>
        <outputDir> 

Description
-----------

``dice_coeff.py`` is a ChRIS-based application that...

Agruments
---------

.. code::

    [-v <level>] [--verbosity <level>]
    Verbosity level for app. Not used currently.

    [--version]
    If specified, print version number. 
    
    [--man]
    If specified, print (this) man page.

    [--meta]
    If specified, print plugin meta data.


Run
----

This ``plugin`` can be run in two modes: natively as a python package or as a containerized docker image.

Using PyPI
~~~~~~~~~~

To run from PyPI, simply do a 

.. code:: bash

    pip install dice_coeff

and run with

.. code:: bash

    dice_coeff.py --man /tmp /tmp

to get inline help. The app should also understand being called with only two positional arguments

.. code:: bash

    dice_coeff.py /some/input/directory /destination/directory


Using ``docker run``
~~~~~~~~~~~~~~~~~~~~

To run using ``docker``, be sure to assign an "input" directory to ``/incoming`` and an output directory to ``/outgoing``. *Make sure that the* ``$(pwd)/out`` *directory is world writable!*

Now, prefix all calls with 

.. code:: bash

    docker run --rm -v $(pwd)/out:/outgoing                             \
            fnndsc/pl-dice_coeff dice_coeff.py                        \

Thus, getting inline help is:

.. code:: bash

    mkdir in out && chmod 777 out
    docker run --rm -v $(pwd)/in:/incoming -v $(pwd)/out:/outgoing      \
            fnndsc/pl-dice_coeff dice_coeff.py                        \
            --man                                                       \
            /incoming /outgoing

Examples
--------





