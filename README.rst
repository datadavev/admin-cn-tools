admin_cn_tools
==============

Scripts to assist with CN management.

Debian package containing administrative tools for DataONE Coordinating Nodes.

This package contains scripts to assist with administration of the CNs. The
package does not depend on other dataONE packages, however the scripts and tools
contained herein expect to operate on a CN server.

The package installs the scripts under ``/usr/local/bin``.

``d1environment``
-----------------

Reports the RR-DNS name for this environment.

Example::

  $ d1environment
  cn.dataone.org


``d1isprimary``
---------------

Detects if the CN is the primary for the environment.

On the primary CN::

  $ d1isprimary
  TRUE cn.dataone.org
  $ echo $?
  1

On a non-primary CN::

  $ d1isprimary
  FALSE cn.dataone.org
  $ echo $?
  0



``hzstat``
----------

Report on Hazelcast cluster participants.

Example::

  $ hzstat
  Cluster [3] {
    Member [160.36.13.150]:5701
    Member [64.106.40.6]:5701 this
    Member [128.111.54.80]:5701
  }

  ConnectionCount: 2
  AllConnectionCount: 4
  Cluster [3] {
    Member [64.106.40.6]:5702 this
    Member [160.36.13.150]:5702
    Member [128.111.54.80]:5702
  }

  ConnectionCount: 1
  AllConnectionCount: 4
  Cluster [3] {
    Member [64.106.40.6]:5703 this
    Member [160.36.13.150]:5703
    Member [128.111.54.80]:5703
  }

  ConnectionCount: 1
  AllConnectionCount: 4

