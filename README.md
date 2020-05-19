broken_link_test
================

Causes error to be raised resulting from the `archive` module attempting to archive a broken symlink.

Demonstrates [ansible issue #42090](https://github.com/ansible/ansible/issues/42090).

**What it Does**

Creates a directory tree at `broken_tree` with:

- broken link at `broken_link`
- regular file at `{{ broken_tree }}/regular_file`
- okay link at `{{ broken_tree }}/ok_link`
- link to the root node at `{{ broken_tree }}/{{ broken_tree }}`

Attempts to archive...

**How to Use**

```
- include_role:
    name: ptmcgit.broken_link_test
  vars:
    broken_tree: "/broken"
    broken_link: "{{ broken_tree }}/nowhere"
```
