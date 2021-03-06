###############
Getting Started
###############


**************************
OS & Hardware Requirements
**************************

Currently, the Rocket Pool Smart Node software stack is only officially supported on `Ubuntu <https://ubuntu.com/>`_ 16.04 and up.
Support for additional operating systems will be added incrementally, after successful testing of the existing version.
However, the majority of the stack runs within Docker containers, so running it on other Unix-based operating systems should require minimal customization.

The Smart Node stack requires at least 3GB of memory and 8GB of (SSD) hard disk space in order to run.

Note that a node operator must have **root** access to their node in order to install the dependencies and register the services required by the Smart Node stack.


************
Installation
************

Firstly, check if you have cURL installed on your system by running the following command in your terminal::

    curl --version

If you don't, install it::

    sudo apt-get install curl

Then, the Smart Node stack can be installed by running the following command::

    curl -L https://github.com/rocket-pool/smartnode-install/releases/download/0.0.1/setup.sh -o setup.sh && chmod 755 setup.sh && ./setup.sh && rm setup.sh

This will download the installation shell script, run it, and remove it once complete. For verbose output, add a ``-v`` flag to the setup command::

    curl -L https://github.com/rocket-pool/smartnode-install/releases/download/0.0.1/setup.sh -o setup.sh && chmod 755 setup.sh && ./setup.sh -v && rm setup.sh

The installation script will perform the following actions:

    * Install the following OS-level dependencies via ``apt-get``:

        * ``apt-transport-https``
        * ``ca-certificates``
        * ``gnupg-agent``
        * ``software-properties-common``
        * ``docker-ce``

    * Install the ``docker-compose`` tool via cURL
    * Install the ``rocketpool`` command-line utility
    * Download all Docker images required by the Smart Node stack
    * Create a Rocket Pool data folder at ``~/.rocketpool``
    * Set the ``RP_PATH`` environment variable to the data folder
    * Download various configuration files used by Docker to the data folder

The installation script can be run safely if any of the listed software is already installed; these items will be skipped.
However, any existing Rocket Pool Docker configuration files will be overwritten.

Once installation has finished, you will be prompted to answer some questions for the initial configuration.
Then, you'll be prompted to restart your terminal, and you can begin!
