Local storage
=============

Your home directory
-------------------

- Location: ``/home/$username/``
- Backed up: ``Yes``

Your home directory is stored on the computer's local drive. This data
is backed up every day - see :doc:`backups` for details. You are not limited
by a quota but the ``/home`` partition/drive is only 50GB in size. If you
expect your computer to be used by multiple people please be considerate
and don't use *all* the space on the partition.

You can check the usage of the drive in :doc:`deskctl`

Local scratch space
-------------------

- Location: ``/local/scratch/$username/``
- Backed up: ``No``

If you need space for large amounts of data you should store this within
your local scratch space. This space is however not backed up, so don't store
anything important there!

The scratch space is stored within the ``/local`` partition, thus this is only limited by the size of the drive within your computer.

You can check the usage of the drive in :doc:`deskctl`

Other locations
---------------

Some computers have multiple drives installed, in which case an iSolutions
technician will have set up the second drive at ``/data``. Directories
are not automatically created within this location. Any data stored there is
not backed up.
