# Ansible Playbook for Home Network

This repository contains an [ansible](https://www.ansible.com/) playbook for my local home network. It currently only managed a single Raspberry Pi 4 running Pi-hole.

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