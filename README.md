Python-From-Src
===============

Ansible role for installing a particular version of Python from
source.

Requirements
------------

None

Role Variables
--------------

The only role vars that the user needs to worry about are:

- `pyfsrc_version`: The version of python to install
- `pyfsrc_make_default`: Whether to make this version of python the
  default version on the system.
- `pyfsrc_force_install`: Install again even if the specified version
  is already found.
- `pyfsrc_install_path`: Folder where Python will be installed.

Dependencies
------------

None

Example Playbook
----------------

eg:

```
    - name: Install python
      hosts: localhost
      roles:
        - role: python-from-source
          pyfsrc_version: 3.6.2
```

The above playbook will install python version 3.6.2 under the default user's `$HOME/.local`.

The role can be used multiple times with different value of
`pyfsrc_version` to install different versions. This can be useful for
setting up an environment for testing a python lib against multiple
versions by using tox for eg.

License
-------

MIT

Author Information
------------------

Vineet Naik <naikvin@gmail.com>

EMBL-EBI
