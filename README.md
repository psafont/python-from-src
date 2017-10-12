User's Python from source
===============

Ansible role for installing a particular version of Python from source as any user.
It's useful particularely to install python to managed machines.

Requirements
------------

Python requirements, usually:
- gcc
- openssl (with development headers)
- zlib (with development headers)

These are not necessary, but very recommended when using pip:
- bzip2 (with development headers)

Role Variables
--------------

The only role vars that the user needs to worry about are:

- `pyfsrc_version`: The version of python to install
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
          ansible_ssh_user: unprivileged_user
```

The above playbook will install python version 3.6.2 under unprivileged_user's `$HOME/.local`.

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
