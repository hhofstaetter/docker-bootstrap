docker-bootstrap
================

Bootstrap scripts for node/npm frontends with php/mysql backends.

Configuration
-------------

Add the following variables to a .env file:
* NODE_VERSION: the node version you want to use
* NODE_DIRECTORY: the directory your node application resides in
    * This directory can be inside docker-bootstrap ("directory")or outside ("../directory")

Usage
-----
* ./npm calls npm in the docker container
