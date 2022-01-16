# [repository_codereadybuilder](#repository_codereadybuilder)

|GitHub|GitLab|
|------|------|
|[![github](https://github.com/mullholland/ansible-role-repository_codereadybuilder/workflows/Ansible%20Molecule/badge.svg)](https://github.com/mullholland/ansible-role-repository_codereadybuilder/actions)|[![gitlab](https://gitlab.com/mullholland/ansible-role-repository_codereadybuilder/badges/master/pipeline.svg)](https://gitlab.com/mullholland/ansible-role-repository_codereadybuilder)|[![quality](https://img.shields.io/ansible/quality/unset)](https://galaxy.ansible.com/mullholland/repository_codereadybuilder)|

description

## [Role Variables](#role-variables)

These variables are set in `defaults/main.yml`:
```yaml
---
repository_codereadybuilder_repo_file:
  RedHat:
    "8": "ubi.repo"
  CentOS:
    "9": "centos.repo"

repository_codereadybuilder_repo_name:
  RedHat:
    "8": "ubi-8-codeready-builder"
  CentOS:
    "9": "crb"
```


## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true
  # vars:
  #   example_var: "value"
  roles:
    - role: "mullholland.repository_codereadybuilder"
```

The machine needs to be prepared in CI this is done using `molecule/default/prepare.yml`:
```yaml
---
- name: Prepare
  hosts: all
  become: true
  gather_facts: true

  tasks:
    - name: check if connection still works
      ansible.builtin.ping:
```





## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

-   [centos-stream9](https://hub.docker.com/r/mullholland/docker-molecule-centos-stream9)
-   [ubi8](https://hub.docker.com/r/mullholland/docker-molecule-ubi8)

The minimum version of Ansible required is 2.10, tests have been done to:

-   The last 2 versions.
-   The current version.



## [Exceptions](#exceptions)

Some variations of the build matrix do not work. These are the variations and reasons why the build won't work:

| variation                 | reason                 |
|---------------------------|------------------------|
| Ubuntu* | repo only supports RedHat/CentOS Server |
| Debian* | repo only supports RedHat/CentOS Server |
| Fedora* | repo only supports RedHat/CentOS Server |
| CentOS-Stream8 | repo does not exists on CentOS-Stream8 |
| RockyLinux8 | repo does not exists on RockyLinux8 |
| AlmaLinux8 | repo does not exists on AlmaLinux8 |
| Amazonlinux | repo does not exists on Amazonlinux |


If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-repository_codereadybuilder/issues)

## [License](#license)

MIT


## [Author Information](#author-information)

[Mullholland](https://github.com/mullholland)

## [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
