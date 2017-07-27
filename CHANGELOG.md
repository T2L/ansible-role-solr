## Ansible Role: Apache Solr 1.x.x

- Add Solr bin directory to global $PATH
- Skip downloading and installing Solr if it already exists
- Dropped dependency on T2L.java as Ansible runs java role multiple times if it's included directly (via playbook) and indirectly (via dependency)

## Ansible Role: Apache Solr 1.0.0, 2017-07-27

- Initial release
