[![build-test](https://github.com/darkwizard242/ansible-role-kubens/workflows/build-and-test/badge.svg?branch=master)](https://github.com/darkwizard242/ansible-role-kubens/actions?query=workflow%3Abuild-and-test) [![release](https://github.com/darkwizard242/ansible-role-kubens/workflows/release/badge.svg)](https://github.com/darkwizard242/ansible-role-kubens/actions?query=workflow%3Arelease) ![Ansible Role](https://img.shields.io/ansible/role/47495?color=dark%20green%20) ![Ansible Role](https://img.shields.io/ansible/role/d/47495?label=role%20downloads) ![Ansible Quality Score](https://img.shields.io/ansible/quality/47495?label=ansible%20quality%20score) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-kubens&metric=alert_status)](https://sonarcloud.io/dashboard?id=ansible-role-kubens) [![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-kubens&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=ansible-role-kubens) [![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-kubens&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=ansible-role-kubens) [![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-kubens&metric=security_rating)](https://sonarcloud.io/dashboard?id=ansible-role-kubens) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-kubens?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-kubens?color=orange&style=flat-square)

# Ansible Role: kubens

Role to install (_by default_) [kubens](https://github.com/ahmetb/kubectx) on **Debian/Ubuntu** and **EL** systems. **kubens** is a tool to switch between Kubernetes namespaces easily.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
kubens_app: kubens
kubens_version: 0.9.4
kubens_os: linux
kubens_arch: x86_64
kubens_dl_url: https://github.com/ahmetb/kubectx/releases/download/v{{ kubens_version }}/{{ kubens_app }}_v{{ kubens_version }}_{{ kubens_os }}_{{ kubens_arch }}.tar.gz
kubens_bin_path: /usr/local/bin
kubens_file_owner: root
kubens_file_group: root
kubens_file_mode: '0755'
```

### Variables table:

Variable          | Description
----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------
kubens_app        | Defines the app to install i.e. **kubens**
kubens_version    | Defined to dynamically fetch the desired version to install. Defaults to: **0.9.4**
kubens_osarch     | Used to specify OS type.
kubens_arch       | Used to specify OS architecture type.
kubens_dl_url     | Defines URL to download the kubens binary from.
kubens_bin_path   | Defined to dynamically set the appropriate path to store kubens binary into. Defaults to (as generally available on any user's PATH): **/usr/local/bin**
kubens_file_owner | Owner for the binary file of kubens.
kubens_file_group | Group for the binary file of kubens.
kubens_file_group | Mode for the binary file of kubens.

## Dependencies

None

## Example Playbook

For default behaviour of role (i.e. installation of **kubens**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.kubens
```

For customizing behavior of role (i.e. specifying the desired **kubens** version) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.kubens
  vars:
    kubens_version: 0.9.3
```

For customizing behavior of role (i.e. placing binary of **kubens** package in different location) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.kubens
  vars:
    kubens_bin_path: /bin/
```

## License

[MIT](https://github.com/darkwizard242/ansible-role-kubens/blob/master/LICENSE)

## Author Information

This role was created by [Ali Muhammad](https://www.alimuhammad.dev/).
