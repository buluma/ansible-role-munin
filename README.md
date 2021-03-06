# [munin](#munin)

Munin monitoring server for RedHat/CentOS or Debian/Ubuntu.

|GitHub|GitLab|Quality|Downloads|Version|Issues|Pull Requests|
|------|------|-------|---------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-munin/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-munin/actions)|[![gitlab](https://gitlab.com/buluma/ansible-role-munin/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-munin)|[![quality](https://img.shields.io/ansible/quality/59032)](https://galaxy.ansible.com/buluma/munin)|[![downloads](https://img.shields.io/ansible/role/d/59032)](https://galaxy.ansible.com/buluma/munin)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-munin.svg)](https://github.com/buluma/ansible-role-munin/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-munin.svg)](https://github.com/buluma/ansible-role-munin/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-munin.svg)](https://github.com/buluma/ansible-role-munin/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: true

  roles:
    - role: buluma.munin
```

The machine needs to be prepared. In CI this is done using `molecule/default/prepare.yml`:
```yaml
---
- name: Converge
  hosts: all
  become: true

  roles:
    - role: buluma.bootstrap
```


## [Role Variables](#role-variables)

The default values for the variables are set in `defaults/main.yml`:
```yaml
---
munin_conf_d_directory: /etc/munin/conf.d

munin_dbdir: /var/lib/munin
munin_htmldir: /var/www/html/munin
munin_logdir: /var/log/munin
munin_rundir: /var/run/munin

munin_includedir: /etc/munin/conf.d

munin_html_strategy: cron
munin_graph_strategy: cron
munin_cron_job: present

munin_max_processes: 12

munin_admin_user: munin
munin_admin_password: munin

# Will be translated into:
# [host]
#   address: [name]
#   [extra.0]
#   [extra.1]
#   [...]
#
# Note that `name` can be hostname, or group + hostname, for example:
# [example.com;foo.example.com]
munin_hosts:
  - name: "localhost"
    address: "127.0.0.1"
    extra: ["use_node_name yes"]

munin_alerts: []
#  - name: "JohnDoe"
#    email: "johndoe@example.com"
#    subject: "Munin-notification for ${var:group} :: ${var:host}"
#    level: "warning critical"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-munin/blob/main/requirements.txt).

## [Status of used roles](#status-of-requirements)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-bootstrap/badges/main/pipeline.svg)](https://gitlab.com/buluma/ansible-role-bootstrap)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-munin/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|el|all|
|debian|all|
|ubuntu|all|

The minimum version of Ansible required is 2.1, tests have been done to:

- The previous version.
- The current version.
- The development version.



If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-munin/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-munin/blob/master/CHANGELOG.md)

## [License](#license)

license (Apache-2.0)

## [Author Information](#author-information)

[Michael Buluma](https://buluma.github.io/)
