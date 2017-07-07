# Ansible Role: Apache Solr

[![Build Status](https://travis-ci.org/T2L/ansible-role-solr.svg?branch=1.x.x)](https://travis-ci.org/T2L/ansible-role-solr)

Installs Apache Solr 5+ on Ubuntu LTS.

## Requirements

Java must be installed.

## Role Variables

Available variables are listed below, along with default values (see [defaults/main.yml](defaults/main.yml)):


## Dependencies

- T2L.java

## Example Playbook

    - hosts: all
      roles:
        - T2L.solr

## License

MIT

## Author Information

This role was created in 2017 by Roman Paska.
