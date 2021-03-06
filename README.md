# Ansible Role: Apache Solr

[![Build Status](https://travis-ci.org/T2L/ansible-role-solr.svg?branch=2.x.x)](https://travis-ci.org/T2L/ansible-role-solr)

Installs Apache Solr 5+ on Ubuntu LTS.

## What is so special about this Apache Solr role

- Fast downloads: tries to download Solr from the closest mirror (works for latest releases only), fallback to archive
- Verification of the integrity of the files
- Supports Ubuntu 16.04, 18.04 and 20.04 only
- Testing with [Molecule 3](https://github.com/ansible-community/molecule)

## Requirements

### Local host (control machine)

This role uses the following Ansible modules, which has specific requirements for the local host (i.e. control machine):

- `synchronize`: copy core configuration to the Solr data directory. This module is a wrapper around `rsync`, so `rsync` must be installed on both the local and remote host
- `xml`: parse response from Solr Admin API. This module requires `lxml >= 2.3.0` on the local host. See installation instructions here: https://lxml.de/installation.html

### Remote host (target machine)

- Java must be installed on the target machine (Solr is Java-based app). [t2l.java](https://galaxy.ansible.com/T2L/java) role can be used for this.

This role relies on a set of tools/utilities/commands that must be available on the remote host. They will be automatically installed:

- `curl` and `sed`: determine the closest available Apache Solr mirror
- `gpg`: verify signature of downloaded Solr archive
- `tar`: unpack downloaded Solr archive
- `rsync`: synchronize core configuration
- `lsof`: recommended for more stable start/stop of Solr

## Role Variables

Available variables are listed below, along with default values (see [defaults/main.yml](defaults/main.yml)):

Solr user and group. Defaults to solr:solr.

    solr_user: solr
    solr_group: "{{ solr_user }}"

Solr version to install. Minimum supported version is 5.0.0.

    solr_version: 7.7.3

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
- **conf_path**: (optional) System path to a directory with core configuration on a remote host. If omitted, default Solr core configuration will be used

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
        - t2l.solr

## License

MIT

## Author Information

This role was created in 2017-2021 by Roman Paska.

## Changelog

Changelog can be found here [CHANGELOG.md](CHANGELOG.md)

## Upgrade

Upgrade instructions can be found here [UPGRADE.md](/UPGRADE.md)
