# CentOS 7 Vagrant box for Node.js developement provisioned with Ansible

## Prerequisites

* VirtualBox
* Vagrant
* Ansible (for Linux and OSX)

## Installation & running the box

Once the repo cloned, copy the `provision/vars/example.vars.yml` file into `provision/vars/vars.yml` and provide your settings.

Create a `projects` directory in the repo root folder.

Run `vagrant vbguest`.

Run `vagrant up`.

## Running on Windows

[to be completed]

## Box Content

* git
* build tools (gcc, make)
* net-tools
* vim with custom settings and plugins
* node.js - provide a version number in `vars.yml` file
* bower
* grunt-cli

## Shared folder

You can place your code in the shared `project` folder.

## Using MongoDB docker container

To run the container: `sudo docker run -d -p 27017:27017 --name myMongo -v /data/db:/home/vagrant/data/db mongo`