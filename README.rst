Ansible Role Python
###################

|Build Status| |Ansible Galaxy| |GitHub issues| |Average time to resolve an issue| |Percentage of issues still open| |GitHub license|

:Version: 0.2.2
:Web: https://github.com/okchaty/ansible-role-python
:Download: http://github.com/okchaty/ansible-role-python
:Source: http://github.com/okchaty/ansible-role-python
:Keywords: ansible-role-python

.. contents:: Table of Contents:
    :local:

Ansible Galaxy role for `Python`_.

Requirements:
=============

List of applications:

- `Python 3.6.4`_
- `Docker`_
- `Docker Compose`_

Install
=======

Install it with the following command:

.. code-block:: bash

    $ ansible-galaxy install okchaty.python

Role Variables
==============

The default role variables in ``defaults/main.yml`` are:

.. code-block:: yaml

        python_pyenv_path: "{{ ansible_env.HOME }}/pyenv"
        python_pyenv_owner: "{{ ansible_env.USER }}"
        python_pyenv_python_versions: ["3.6.0"]
        python_pyenv_delete_virtualenvs: [{ venv_name: "latest" }]
        python_pyenv_virtualenvs: [{ venv_name: "latest", py_version: "3.6.0" }]
        python_pyenv_update_git_install: no

- Deploy code

.. code-block:: yaml

    - role: okchaty.python
      python_pyenv_install: no
      python_pyenv_update_git_install: no

Dependencies
============

None

Example Playbook
================

See the `examples <./examples/>`__ directory.

To run this playbook with default settings, create a basic playbook like
this:

.. code:: yaml

        - hosts: servers
          roles:
            - okchaty.python

To install a specific version:

.. code:: yaml

      - hosts: servers
        roles:
          - { role: okchaty.python }

.. code:: yaml

        - hosts: servers
          roles:
             - role: okchaty.python
               python_pyenv_path: "{{ home }}/pyenv"
               python_pyenv_owner: "{{ instance_owner }}"
               python_pyenv_update_git_install: no
               python_pyenv_python_versions:
                 - "3.5.1"
                 - "2.7.9"
               python_pyenv_delete_virtualenvs:
                 - venv_name: "delete_venv_name"
               python_pyenv_virtualenvs:
                 - venv_name: "latest_v3"
                   py_version: "3.5.1"
                 - venv_name: "latest_v2"
                   py_version: "2.7.9"

License
=======

MIT

Changelog
=========

Please see `CHANGELOG`_ for more information what
has changed recently.

Contributing
============

Please see `CONTRIBUTING`_ for details.

Credits
=======

-  `author`_
-  `contributors`_

Made with :heart: :coffee: and :pizza: by `author`_ and `company`_.

.. Badges:

.. |Build Status| image:: https://travis-ci.org/okchaty/ansible-role-python.svg
   :target: https://travis-ci.org/okchaty/ansible-role-python
.. |Ansible Galaxy| image:: https://img.shields.io/badge/galaxy-okchaty.python-blue.svg
   :target: https://galaxy.ansible.com/okchaty/ansible-role-python/
.. |GitHub issues| image:: https://img.shields.io/github/issues/okchaty/ansible-role-python.svg
   :target: https://github.com/okchaty/ansible-role-python/issues
.. |Average time to resolve an issue| image:: http://isitmaintained.com/badge/resolution/okchaty/ansible-role-python.svg
   :target: http://isitmaintained.com/project/okchaty/ansible-role-python
.. |Percentage of issues still open| image:: http://isitmaintained.com/badge/open/okchaty/ansible-role-python.svg
   :target: http://isitmaintained.com/project/okchaty/ansible-role-python
.. |GitHub license| image:: https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square
   :target: LICENSE

.. Links
.. _`changelog`: CHANGELOG.rst
.. _`contributors`: AUTHORS
.. _`contributing`: CONTRIBUTING.rst

.. _`company`: https://github.com/okchaty
.. _`author`: https://github.com/luismayta

.. dependences
.. _Python: https://www.python.org
.. _Python 3.6.4: https://www.python.org/downloads/release/python-364
.. _Docker: https://www.docker.com/
.. _Docker Compose: https://docs.docker.com/compose/