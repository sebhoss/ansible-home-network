# Ansible Playbook for Home Network

This repository contains an [ansible](https://www.ansible.com/) playbook for my local home network. It currently manages two Raspberry Pi 4 nodes running [Fedora IoT](https://fedoraproject.org/iot/). The following roles are applied:

- `hostname`: Sets the hostname of each node
- `rpm-ostree`: Enables the [rpm-ostreed-automatic](https://www.mankier.com/8/rpm-ostreed-automatic.service) service
- `podman`: Enables the [podman-auto-update](https://docs.podman.io/en/latest/markdown/podman-auto-update.1.html) service
- `pi-hole`: Installs [Pi-hole](https://pi-hole.net/) using [Podman Quadlet](https://docs.podman.io/en/latest/markdown/podman-systemd.unit.5.html)
- `zezere`: Disables the [zezere/ignition](https://docs.fedoraproject.org/en-US/iot/ignition/) timer/service since that causes high load without providing any use in my setup

## Usage

```shell
$ ./play --check --diff
```
