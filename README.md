Role Name
=========

Ansible role for installing sinopia as Docker container

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

Usage
-----

To add users from config the suggested method is:
- enable registration (docker_sinopia_registration: True - this is the default)
- add users with npm adduser --registry https://sinopia.yourdomain.com
- get storage/htpasswd from the container and save it to a file
- set the saved file (encrypt with vault) path to docker_sinopia_htpasswd_path
- disable registration: docker_sinopia_registration: False

To authenticate npm in scripts:
- npm login --registry https://sinopia.yourdomain.com
- save the token from ~/.npmrc and set it up in your CI script (something like: //sinopia.yourdomain.com/:_authToken="12123123123123123123123")

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
