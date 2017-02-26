Network storage
===============

Available locations
-------------------

There are several storage systems available to connect to on the University
network:

Personal Filestore (via SSH)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- Location: ``sftp://ssh.soton.ac.uk/home/$username/``
- Protocol: ``SSH/SFTP``
- Linux friendly semantics: ``Yes``

This is your central university storage or 'filestore'. Data stored here
is backed up and available on Linux, Windows and Mac OS X computers. You can
also access data stored here via `Filestore Web Access <https://fwa.soton.ac.uk>`_.

Personal Filestore (via SMB)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- Location: ``sftp://ssh.soton.ac.uk/home/$username/``
- Protocol: ``SMB1``, ``SMB2``
- Linux friendly semantics: ``No``

You can also access your personal filestore via the SMB protocol (the Windows
file sharing protocol). If you connect via this method then you will not be
able to set or view file/directory permissions, create symbolic links or 
use any other POSIX (Linux/UNIX) features. Due to this it is *strongly* 
recommended that you utilise SSH instead.

Linux Shared Filestore
^^^^^^^^^^^^^^^^^^^^^^

- Location: ``sftp://ssh.soton.ac.uk/research/$groupname/``
- Protocol: ``SSH/SFTP``
- Linux friendly semantics: ``Yes``

Many research groups and departments have access to shared storage locations
specifically designed for use from Linux systems. These are available at
the above location. Data stored here is backed up. You can also access data 
stored here via `Filestore Web Access <https://fwa.soton.ac.uk>`_.

Other Shared Filestore
^^^^^^^^^^^^^^^^^^^^^^

- Location: ``smb://filestore.soton.ac.uk/$sharename/``
- Protocol: ``SMB1``, ``SMB2``
- Linux friendly semantics: ``No``

Many other shared locations exist, such as the "J: drive" shared storage
locations. These are available at the above location. Data stored here is  
backed up. You can also access data stored here via `Filestore Web Access <https://fwa.soton.ac.uk>`_.

These locations are unfortunately designed for use by Windows users. You will 
not be able to set or view file/directory permissions, create symbolic links 
or use any other POSIX (Linux/UNIX) features.

How to connect
--------------

There are various methods of connecting to network storage:

via the file browser
^^^^^^^^^^^^^^^^^^^^



sdsds

via GVFS
^^^^^^^^

sdsds

via FUSE
^^^^^^^^

sdsds

via the ``mount`` command
^^^^^^^^^^^^^^^^^^^^^^^^^

asds



