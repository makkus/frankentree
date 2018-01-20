===========
frankentree
===========

Features
--------

*frankentree* is a git helper script which:

- lets you assemble git repositories that are composed of other git repositories (using ``git subtree``)
- supports pulling from upstream for one or all sub repositories
- supports pushing from upstream for one or all sub repositories
- can automatically fork sub-repositories if needed, to both your personal github account or an organization you are member of

Usage / Examples
--------

Cloning an existing frankentree
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: console

   frankentree clone <frankentree_git_url>

Adding a sub-tree
^^^^^^^^^^^^^^^^^

Directly from upstream
++++++++++++++++++++++

.. code-block:: console

   frankentree add -u <source_git_url> <target_path>

Forking to personal Github account before adding
++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: console

   frankentree add -f -u <source_git_url> <target_path>

Forking to Github organization before adding
++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: console

   frankentree add -f -g <github_org_name> -u <source_git_url> <target_path>

Pulling from upstream (all sub-trees)
+++++++++++++++++++++++++++++++++++++

.. code-block:: console

   frankentree pull

Pulling from upstream (one or several sub-trees)
++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: console

   frankentree pull sub-tree-path [sub-tree-path] ...

Pushing to upstream (all sub-trees)
+++++++++++++++++++++++++++++++++++

.. code-block:: console

   frankentree push

Pushing from upstream (one or several sub-trees)
++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: console

   frankentree push sub-tree-path [sub-tree-path] ...



Description
-----------

TBD

Supported platforms
-------------------

- Linux
- Mac
- others not tested

Requirements
------------

- git (preferably not an ancient version)
- secret-tool (optional, needed for the 'fork' feature)

License
-------

GNU General Public License v3
