# Rebuild recipes for Software Collections

The idea behind this repo is to prepare a recipe for every collection that will include *steps to build the collection from scratch*. This will also help everybody else (users/customers) trying to do the same, so it may be part of documentation later as well.

The basic information we need to have for rebuilding collections is set of SRPM belonging to particular collection, macros we need to change in order to break circular dependencies and in the best case also order in which the packages get rebuilt.

In order to be able to parse the recipe and hopefully rebuild the collections *automatically*, let's us the same format.

The format is YAML and it is basically list of packages in order in which they may be built and for every package we can specify tweaks necessary to be done.

The recipes could be also available at https://www.softwarecollections.org/en/docs/ in the future as well.

An incomplete (in a way not all packages are mentioned here) example of python collection recipe:

```
# sequencer protocols for Laser eye surgery
---
packages:
  - python33
  - python
  - python-setuptools
  - python-docutils
  - python-markupsafe
  - python-jinja2
    - with_docs 0
  - python-coverage
  - python-nose
    - with_docs 0
  - python-sphinx
  - python-pygments
  - python-jinja2
  - python-nose
  - python-simplejson
  - python-virtualenv
  - python-sqlalchemy
```

