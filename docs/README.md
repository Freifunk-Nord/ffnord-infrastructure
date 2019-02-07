FFKI Ansible Documentation
==========================

This is the docuemnetation for the automated ansible setup of Freifunk Kiel.

Documentation is split up into multiple parts:
 - Site setup: site.md
 - Gateway setup: gateway.md
 - Developer documentation: roles/*.md

# Limitations

The following limitations apply to the ansible roles in this repository:
 - Multi domain setups are not supported yet
 - Only setup of gateways is currently supported

# preparation

1. you have to add the hostname used in the groups in the inventory file to your `.ssh/config` as Host.
2. On the host you have to install python and set your ssh key so ansible may login as root
3. call ansible, e.g.:

       ansible-playbook -i nord site.yml -t gateway --limit nord-gw14

# update this repository

This repository uses submodules wich contian some global scripts `ffki-scripts` 
and the variables per host in `nord-ansible-host-vars` which contain confidential
data. Update the repository and all submodules with:

    git pull
    git uptate submodules
