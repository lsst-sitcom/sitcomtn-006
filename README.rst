.. image:: https://img.shields.io/badge/sitcomtn--006-lsst.io-brightgreen.svg
   :target: https://sitcomtn-006.lsst.io
.. image:: https://github.com/lsst-sitcom/sitcomtn-006/workflows/CI/badge.svg
   :target: https://github.com/lsst-sitcom/sitcomtn-006/actions/

######################
Integration Milestones
######################

SITCOMTN-006
============

A proposal for ways to work on predominantly software subsystem commissioning,
building on the Rubin auxiliary Telescope experience

Links
=====

- Live drafts: https://sitcomtn-006.lsst.io
- GitHub: https://github.com/lsst-sitcom/sitcomtn-006

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-sitcom/sitcomtn-006

Compile the PDF::

    make

Clean built files::

    make clean

Adding a new Integration Milestone
----------------------------------

IMs live in their own file, e.g. IMa.tex which you'll need to `\\inputIM{IMa}` in SITCOMTN-006.tex.
At the top of the file there's a line::

   \declareIM{LABEL}{NAME}{DATE}{TITLE}

e.g.::

   \declareIM{a}{1}{2020-12-25}{ComCam Image Capture and Archive}

where `LABEL` is how you refer to the IM (as `\\IM{LABEL}`), `NAME` is its identifier,
`DATE` is when the IM should be complete, and `TITLE` is a description.  The separation
of `LABEL` from `NAME` allows us to reorder IMs without disturbing cross-references or
informal discussion.

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the ``acronyms.tex`` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
