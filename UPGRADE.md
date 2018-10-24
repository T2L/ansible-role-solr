# UPGRADE

### 1.x.x -> 2.0.x

`solr_cores` variable must be converted to to the new format. Version 1.x.x specification was simple, something like that:

    solr_cores:
      - main
      - extra

Version 2.x.x allows for specifying extra options for each core. Currently only `name` and `conf_path` keys are supported (that might change in future though).

    solr_cores:
      - name: main
      - name: extra

Optionally add `conf_path` key for each core. This key should contain systme path to a directory with core configuration.
