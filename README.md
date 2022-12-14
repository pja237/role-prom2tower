role-prom2tower
===============

Installs [prom2tower](https://github.com/pja237/prom2tower)

Requirements
------------

None.

Role Variables
--------------

```
prom2tower_version: "v0.0.1"                              # version (suffix) to install 
prom2tower_conf_template: "templates/prom2tower.yaml.j2"  # template file to use from playbook
prom2tower_user: "prom2tower"                             # local user to create to own and run service
prom2tower_group: "prom2tower"                            # local user to create to own and run service
prom2tower_install_path: "/usr/local/bin"                 # download and install release zip
prom2tower_log_path: "/var/log/prom2tower"                # directory to place logs to
prom2tower_conf_path: "/usr/local/etc"                    # config file location, name: prom2tower.yaml
prom2tower_conf: "{{ prom2tower_conf_path }}/prom2tower.yaml"
```

Dependencies
------------

None.


Example Playbook
----------------

Following two variables are required:

* `prom2tower_version` - github release
* `prom2tower_conf_template` - config file template, [example](https://github.com/pja237/prom2tower/blob/main/cmd/prom2tower/conf.yaml.example)

```
---
- hosts: all
  become: true
  gather_facts: true

  roles:
    - role: role-prom2tower
      vars: 
        prom2tower_version: "v0.0.1"
        prom2tower_conf_template: "templates/prom2tower.yaml.j2"

```

License
-------

MIT

Author Information
------------------

Petar Jager
[prom2tower git repository](https://github.com/pja237/prom2tower)

