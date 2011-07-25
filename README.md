# BDPack

BDPack is an attempt to improve the experience of maintaining software packages for Linux operating systems.

## Specifications

A set of executable specifications for major Linux distribution policies covering the process of building a fully compliant package.
This feature is similar to "lintian" for Debian and "rpmlint" for Redhat.
With BDPack, we take an outside-in approach where the maintainer is guided from high-level behaviors to low-level configuration.
A maintainer can also add adhoc specifications, thus documenting and checking expected behavior only relevant to a given package.

## Generators

A framework of generators assisting the maintainer in performing common tasks.
For instance, there is a generator to create the minimal structure of files and directories to get started.

## CLI and workflow

A command line interface wrapping the tools and workflows of major Linux distributions.
We know of two Git-workflow helpers: "git-buildpackage" for Debian and "fedpkg" for Fedora.

## Rough scenario

    $ bdpack new mypackage --dist debian
    $ cd mypackage
    $ bdpack import /path/to/upstream-0.1.0.tar.gz   # Import the upstream revision
    $ bdpack spec                                    # Run the specs
    ...
    $ bdpack build                                   # Build a binary package
    ...
    $ bdpack import /path/to/upstream-0.2.0.tar.gz   # Import a new upstream revision
    ...
