## Ansible Role: Apache Solr 2.x.x

- Bump minimum supported Ansible version to 2.5
- Fixed _Invoking "apt" only once while using a loop via squash_actions is deprecated._
- Use `loop` keyword instead of `with_<lookup>`
- Added ability to specify directory with configuration per core (if omitted, Solr default configuration will be used)

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
