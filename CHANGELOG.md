## Ansible Role: Apache Solr 2.x.x

- [#12](https://github.com/T2L/ansible-role-solr/issues/12) - Bump default Solr version to 7.7.2
- [#6](https://github.com/T2L/ansible-role-solr/issues/6) - Added support of Solr 7.5.0+
- [#7](https://github.com/T2L/ansible-role-solr/issues/7) - Fixed Ansible 2.8 deprecations in T2L.Java role (used by tests)

## Ansible Role: Apache Solr 2.0.1, 2018-10-26

- Replaced shell `cp` command with Ansible `synchronize` module for core configuration copying. Config source directory must exist on the remote host (i.e. sync is being done on the remote host)
- Significantly improve cores creation logic:
    * Role will create only missing cores
    * Core will be reloaded if it's configuration has changed since last sync

## Ansible Role: Apache Solr 2.0.0, 2018-10-24

- Bump minimum supported Ansible version to 2.5
- Fixed _Invoking "apt" only once while using a loop via squash_actions is deprecated._
- Use `loop` keyword instead of `with_<lookup>`
- Added ability to specify directory with configuration per core (if omitted, Solr default configuration will be used)
- Updated test dependency on T2L.java to 1.1.0
- Added upgrade instructions

## Ansible Role: Apache Solr 1.4.0, 2018-07-23

- Upgrade Solr when required version has changed instead of skipping installation

## Ansible Role: Apache Solr 1.3.1, 2018-07-14

- Updated Ansible Galaxy metadata and README files

## Ansible Role: Apache Solr 1.3.0, 2018-07-12

- Bump default Solr version to 6.6.5
- Fixed [DEPRECATION WARNING]: Using tests as filters is deprecated. Instead of using `result|failed` use `result is failed`
- Test role against Ubuntu 18.04 (Bionic Beaver)

## Ansible Role: Apache Solr 1.2.0, 2017-09-21

- Make sure Travis uses Molecule < 2.0.0
- Bump minimum supported Ansible version to 2.4

## Ansible Role: Apache Solr 1.1.1, 2017-07-28

- Fixed 'solr_download_dest is undefined' error in 'Remove downloaded archive and extracted files' task

## Ansible Role: Apache Solr 1.1.0, 2017-07-27

- Add Solr bin directory to global $PATH
- Skip downloading and installing Solr if it already exists
- Dropped dependency on T2L.java as Ansible runs java role multiple times if it's included directly (via playbook) and indirectly (via dependency)

## Ansible Role: Apache Solr 1.0.0, 2017-07-27

- Initial release
