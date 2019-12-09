# Ansible Planning Biblio
[![Build Status](https://travis-ci.org/supertarto/ansible-planning-biblio.svg?branch=master)](https://travis-ci.org/supertarto/ansible-planning-biblio)
Install and configure Planning Biblio with Ansible.

## Requirements
A web server (only tested with Apache), mariadb, php7.0 or above. You can use thoses roles:
- supertarto.apache
- supertarto.php
- supertarto.mariadb

## Tested plateform
* Debian 9 (Stretch)
* Debian 10 (Buster)

## Role variables
Do we need to force Planning Biblio Update?
```yml
planning_force_update: false
```
The branch version for Github.
```yml
planning_git_branch_version: "19.10.xx"
```
The path where the git directory an the content directory wiil be stored.
```yml
planning_separate_git_dir: "/usr/local/planning-biblio-git"
planning_content_dest: "/var/www/planning/"
```

## Examples

```yml
- name: Converge
  hosts: all

  roles:
    - role: supertarto.apache
    - role: supertarto.mariadb
    - role: supertarto.php
    - role: supertarto.planning-biblio
```

## Installation
```
ansible-galaxy install supertarto.planning-biblio
```
## License
GPL V3.0
