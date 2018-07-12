## Ansible Role: Apache Solr 1.x.x

- Bump default Solr version to 6.6.5

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
