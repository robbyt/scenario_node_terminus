# about

This module contains a custom node terminus that allows
for scenarios based deployments

# installation

1. install this module
2. synchronize it's plugins
3. configure puppet.conf

```
[master]
  node_terminus=scenario
```

# usage

Configure the following yaml files in /etc/puppet/data

* config.yaml
    global config that will be passed to Puppet as top scope variables
    it also contains a special key called scenarios

* scenarios/<name>.yaml
    Directory that contains the possible deployment scenarios.
    Each scenario contains the following:

  * roles - list of roles that exist as a part of that scenario. Each role contains a list of classes specified as either classes or class_groups.

* class_groups/<name>.yaml

Contains a list of classes available in each class group

* role_mappings.yaml

Contains a list of hostnames that the roles that they should be supplied.
