===========
frankentree
===========

Features
--------

*frankentree* is a git helper script which:

- lets you assemble git repositories that are composed of other git repositories (using ``git subtree``)
- supports pulling from upstream for one or all of the sub repositories
- supports pushing from upstream for one or all of the sub repositories
- can automatically fork sub-repositories if needed, to both your personal github account or an organization you are member of

Description
-----------

This is a little helper script to manage repositories that are composed of other git repositories.

It's mostly useful for cases where you need to end up with a collection of git repositories in a folder, and don't care too much about making changes, or pushing changes back upstream. Although that is supported as well. But if you want to do that, you're probably better of doing things manually.

``frankentree`` mostly follows the recommendation from `this blog-post <https://www.atlassian.com/blog/git/alternatives-to-git-submodule-git-subtree>`_.

It allows you to add subtrees to an existing git repository, and it'll create a new remote using the (relative) path name as the git remote name. In order to keep track of those remotes, it creates a file ``.remote_repos in the root of the frankentree.

The rest should be explained by the examples below. If not, open an issue and I'll improve this here.


Usage / Examples
----------------

You have to be in the root of your frankentree repository for all the following commands to work. Except of course for ``clone``.

Cloning an existing frankentree
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: console

   frankentree clone <frankentree_git_url>
   # e.g.:
   frankentree clone https://github.com/freckles-io/wordpress.git


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


Supported platforms
-------------------

- Linux
- Mac OS X
- others not tested (actually, to be honest, I didn't really test on Mac OS X either -- I just assume it'll sorta work...)

Requirements
------------

- git (preferably not an ancient version)
- secret-tool (optional, needed for the 'fork' feature)

License
-------

GNU General Public License v3
