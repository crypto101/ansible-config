==============
ansible-config
==============

This repository contains the Ansible_ configuration files for managing
the servers for the Crypto 101 project.

I (lvh) am not a professional system administrator, and I am very new
to ansible. All help would be highly appreciated!

.. _Ansible: http://www.ansible.com/home

Configuration
=============

All configuration is in the ``local`` directory for now. That's in
``.gitignore`` to prevent you from accidentally adding some secret
data.

inventory
---------

This repo uses an inventory directory, ``inventory/``. It contains
configuration for localhost as well as a ``rax.py`` plugin. For
Rackspace-specific configuration used by ``rax.py``, see below. You
can get that plugin from Ansible's dev tree here::

    https://raw2.github.com/ansible/ansible/devel/plugins/inventory/rax.py

Apparently copying that file into your inventory directory is really
how you do it.

pyrax
-----

Crypto 101 is a Rackspace_ shop. We use a dynamic inventory for
Ansible, provided by pyrax_. You will need to put a pyrax credentials
file in ``./local/pyrax-credentials`` that looks somewhat like::

    [rackspace_cloud]
    username = crypto101
    api_key = deadbeef

.. _Rackspace: https://www.rackspace.com/
.. _pyrax: https://github.com/rackspace/pyrax
