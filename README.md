# Ansible Playbook for Home Network

This repository contains an [ansible](https://www.ansible.com/) playbook for my local home network. It currently manages two Raspberry Pi 4 nodes running [Fedora IoT](https://fedoraproject.org/iot/). The following roles are applied:

- `hostname`: Sets the hostname of each node
- `rpm-ostree`: Enables the [rpm-ostreed-automatic](https://www.mankier.com/8/rpm-ostreed-automatic.service) service
- `podman`: Enables the [podman-auto-update](https://docs.podman.io/en/latest/markdown/podman-auto-update.1.html) service
- `pi-hole`: Installs [Pi-hole](https://pi-hole.net/) using [Podman Quadlet](https://docs.podman.io/en/latest/markdown/podman-systemd.unit.5.html)

## Setup

```shell
$ python3 -m venv .venv
$ source .venv/bin/activate
$ pip install ansible-core
$ ansible-galaxy collection install --requirements-file requirements.yaml
```

## Usage

```shell
$ ansible-playbook --check --diff playbook.yaml
```
