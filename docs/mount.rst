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

If you're using GNOME (the default), XFCE, MATE or KDE then you can simply open 
the file browser and enter the location you want to connect to by pressing ``Ctrl+L``
or clicking ``Connect to server`` in the menu. You will be prompted for a 
username and password as necessary.

We strongly recommend you use this mechanism to connect to network storage. You
can also access the connected storage from other applications and the command
line. Once connected they are available via the normal filesystem here::

   /run/user/$uid/gvfs/

via FUSE (SSH only)
^^^^^^^^^^^^^^^^^^^

If you prefer to connect to networked storage on the command line only, you can
do so using the ``sshfs`` command. We strongly recommend you use the above
mechanism (the file browser) instead since that can also be accessed from the
command line. 

If you do want to use ``sshfs`` directly then run the command like so::

   sshfs [user@]host:[dir] mountpoint 

For example, here is how to connect to your personal filestore as ``testuser``::

   mkdir ~/personalfs
   sshfs testuser@ssh.soton.ac.uk:/home/testuser/ ~/personalfs

You can then later disconnect with::

   fusermount -u ~/personalfs

via the ``mount`` command
^^^^^^^^^^^^^^^^^^^^^^^^^

You can also instruct the kernel to mount network storage if you desire. This 
can however be quite complicated and this documentation only covers the basics.

You can use the ``mount`` command via ``sudo`` if you are in the ``sys`` group
(see :doc:`permissions` for more information). You can thus use the command
like so::

   sudo mount <options>

Here is an example of how to mount personal filestore via the ``cifs`` driver 
with the example username ``testuser``::

   mkdir ~/personalfs
   sudo mount -t cifs -o username=testuser,password=<password>,domain=soton.ac.uk //filestore.soton.ac.uk/users/testuser/ /home/testuser/personalfs/
