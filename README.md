# Ansible Role: Packages

[![CI](https://github.com/jamescaldow/ansible-role-packages/workflows/CI/badge.svg?event=push)](https://github.com/jamescaldow/ansible-role-packages/actions?query=workflow%3ACI)

Simple role to manage packages on Linux systems. Allows the user to define a
list of packages, along with the state, and the role will manage them.

## Requirements

None.

## Role Variables

This role takes two variables.

    system_packages: []

This variable takes a list of package names and manages them for the given
system. Care must be taken when selecting the package names to ensure that the
package name exists on a given distribution, (e.g. httpd on CentOS but Apache2
on Debian).

    package_state: present

Defaults to `present`, but can be set to absent to remove packages or `latest`
to ensure packages are updated on subsequent runs of any playbook which contain
this role.

## Dependencies

None.

Example Playbook
----------------

    - hosts: all
      vars:
        system_packages:
          - curl
          - vim
        package_state: present

As noted, valid values for `package_state` are present to install the
application and leave it untouched after installation; `absent` to remove the
application; or `latest` to install the application and check for newer
versions on each subsequent run.


License
-------

MIT

Author Information
------------------

This role was created in 2020 by James Caldow.
