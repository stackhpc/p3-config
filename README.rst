==============================================================
SKA SDP Performance Prototype Platform (P-cubed) Configuration
==============================================================

This project contains Ansible playbooks and configuration of infrastructure on
an existing OpenStack cloud for the `SKA SDP <http://ska-sdp.org/>`_
Performance Prototype Platform (P-cubed). This includes:

* A p3 project and user accounts in OpenStack keystone.
* Compute node flavors in OpenStack nova for the various compute and storage
  node types.
* Networks, subnets and routers in OpenStack neutron for the external ``ilab``
  and internal ``p3-internal`` networks.

Preparation
===========

Ensure that Ansible is installed, either via the system package manager or pip.
If required, use a virtualenv to avoid interference with the system python
packages. For example:

.. code-block::

   $ virtualenv venv
   $ source venv/bin/activate
   $ pip install -U pip
   $ pip install -r requirements.txt

Install Ansible role dependencies from Ansible Galaxy:

.. code-block::

   $ ansible-galaxy install \
       -p ansible/roles \
       -r ansible/requirements.yml

Usage
=====

First, ensure that OpenStack authentication environment variables are set,
typically by sourcing an OpenStack environment file.

To configure OpenStack infrastructure for P-cubed:

.. code-block::

   $ ansible-playbook \
       -i ansible/inventory \
       -e @etc/p3-config/p3-config.yml \
       ansible/p3.yml
