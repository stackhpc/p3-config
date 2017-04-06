# SKA SDP Performance Prototype Platform (P-cubed) Configuration

This project contains Ansible playbooks and configuration for the SKA SDP
Performance Prototype Platform (P-cubed).

## Preparation

Ensure that Ansible is installed, either via the system package manager or pip.
If required, use a virtualenv to avoid interference with the system python
packages.

Install Ansible role dependencies from Ansible Galaxy:

    $ mkdir ansible/roles
    $ ansible-galaxy install -p ansible/roles -r ansible/requirements.yml

## Usage

First, ensure that OpenStack authentication environment variables are set,
typically by sourcing an OpenStack environment file.

To configure P-cubed OpenStack project and users:

    $ ansible-playbook -i ansible/inventory ansible/p3-project.yml
