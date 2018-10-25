# Ansible Role: Apache Solr

[![Build Status](https://travis-ci.org/T2L/ansible-role-solr.svg?branch=2.x.x)](https://travis-ci.org/T2L/ansible-role-solr)

Installs Apache Solr 5+ on Ubuntu LTS.

## What is so special about this Apache Solr role

- Fast downloads: tries to download Solr from the closest mirror (works for latest releases only), fallback to archive
- Verification of the integrity of the files
- Supports Ubuntu 14.04, 16.04 and 18.04 only
- Testing with [Molecule](https://github.com/metacloud/molecule)

## Requirements

- Java must be installed on the managed machine (Solr is Java-based app)
- Python library lxml >= 2.3.0 is required on the host machine that runs this role

## Role Variables

Available variables are listed below, along with default values (see [defaults/main.yml](defaults/main.yml)):

Solr user and group. Defaults to solr:solr.

    solr_user: solr
    solr_group: "{{ solr_user }}"

Solr version to install. Minimum supported version is 5.0.0.

    solr_version: 6.6.5

Port Solr should bind to.

    solr_port: 8983

Directory Solr archive will be downloaded to.

    solr_download_dir: /tmp

Directory Solr will be installed to.

    solr_install_dir: /opt

Data directory for Solr configuration and cores.

    solr_data_dir: /var/solr

Whether to remove downloaded archive and extracted files after the installation.

    solr_cleanup_downloads: true

Whether to remove downloaded GPG keys file and .asc signature file after the installation.

    solr_cleanup_gpg: true

List of Solr cores to configure. Possible keys:

- **name**: Solr core name
- **conf_path**: (optional) System path to a directory with core configuration. If omitted, default Solr core configuration will be used

```
solr_cores: []
```

Example (do not forget to remove square brackets):

    solr_cores:
      - name: main
      - name: extra
        conf_path: /var/www/project/config/solr

## Example Playbook

    - hosts: all
      roles:
        - T2L.solr

## License

MIT

## Author Information

This role was created in 2017-2018 by Roman Paska.

## Changelog

Changelog can be found here [CHANGELOG.md](CHANGELOG.md)

## Upgrade

Upgrade instructions can be found here [UPGRADE.md](/UPGRADE.md)
