Migration Guide
===============

.. note::

   This guide is intended for iSolutions staff only.

Introduction
------------

This guide is intended to assist you migrating a customer's workstation from
either RHEL5 or RHEL6 to our current RHEL7 platform. Before you start, you 
should make sure that you have a USB disk with no data on it that you can use
to store data on the customer wishes to keep.

Migration outline
-----------------

- Check for non-backed up data in /local/scratch/
- Copy data from /home/ to the USB drive
- Copy data from /local/scratch/ to the USB drive
- Check for secondary hard drives in the system
- Disconnect any secondary hard drives 
- Install RHEL7
- Reconnect secondary hard drives
- Set up secondary hard drives to be automatically mounted
- Copy data back from the USB drive to /local/scratch/
- Copy data back from the USB drive to /home/
- Copy home directory data back

Check for non-backed up data in /local/scratch/
-----------------------------------------------

Users will probably want you to back up the data that is in ``/local/scratch/`` on
the workstation. Although this data is not backed up normally, and is 'scratch'
space we will still back it up to make things easier.

Ask the user if they have data they wish to keep in ``/local/scratch``, and check
if there is any other user data in ``/local/scratch/`` as well. If there is, it 
makes sense to back it up.

Do not check for data in ``/data`` - this is likely a second hard drive, which 
we will come onto later. 

Attach the USB disk
-------------------

Ask the user to log out of the system and ensure nobody else is logged in. Then
login on the console and gain root. To switch to the console type ``Ctrl+Alt+F3``.

Now plug in the USB disk you're going to use to store data on during the 
migration. You should then run the command ``lsscsi`` to list the attached 
storage devices. If lsscsi is not installed, installed it with::

   yum install lsscsi

You can then run it like so::

   lsscsi

And you should get an output somewhat similar to this::

   [0:0:0:0]    disk    ATA      KINGSTON SA400S3 71E0  /dev/sda
   [1:0:0:0]    cd/dvd  TSSTcorp CDDVDW SH-224BB  SB00  /dev/sr0
   [2:0:0:0]    disk    Seagate  Expansion        9300  /dev/sdb 

As you can see from the above, the USB drive (in this case a Seagate USB drive)
is listed and it is available at the path ``/dev/sdb``. If you've already set
up the disk to be used by Linux systems then you can go ahead and mount the 
drive. We'll create a place to mount it::

   mkdir /mnt/migrate

And then mount it::

   mount /dev/sdb1 /mnt/migrate

Copy data
---------

Now you'll want to use ``rsync`` to copy the data from the local system to the 
USB hard drive. We'll run it twice, once for ``/home`` and the second time for
``/local/scratch/``. Here are the commands you'll want to run::

   rsync -av --progress /home/ /mnt/migrate/home/
   rsync -av --progress /local/scratch/ /mnt/migrate/scratch/

You can run these commands again to make sure all changes have been copied as 
they 'mirror' the data and only copy changes as needed. These commands will 
likely take a long time to run dependent on the speed of the hard drives and
the amount of data.

Secondary hard drives
---------------------

Sometimes a workstation will have a second or even a third physical disk 
installed. We don't have to back up this data as the installation for RHEL7
won't touch these disks - the data will be retained. However, it is best 
practice to disconnect these drives 'just in case'. If its easy to open the case
and disconnect secondary hard drives, do so (when the power is off of course!)
so as to prevent any chance of data on these disks from being lost.

Make a note as to how many of these drives there are, and where they are 
currently mounted. You can get a list of physical drives with ``lsscsi``::

   lsscsi

and you can get a list of mounted partitions with ``df``::

   df -h

This will let you figure out what drives are there, and what mount points to 
add once you've installed RHEL7. Make sure to write down the full path to the
disk, e.g. it will probably be ``/dev/sdb1`` for the device path. You'll also 
want to make sure you write down the file system type, hopefully it will be
``ext4``.

Install RHEL7
-------------

Once you've done the above steps, power the machine off, and unplug the USB 
hard disk. Then power it back on and follow the :doc:`install` guide.

Reconnect secondary hard drives
-------------------------------

Once you've installed RHEL7 you should power the machine off again and reconnect
any hard drives you previously disconnected. You can then power the machine
back on and reconnect them. Log in and gain root, and then find a list of the
new drives::

   lsscsi

You should then re-create the directories where you want to mount the drives. In
nearly all cases this will be ``/data`` so just run::

   mkdir /data

Now you'll need to edit the file system tab (``fstab``) to add a record so the 
drive is mounted at startup. Edit ``/etc/fstab`` in the editor of your choice
and add the following::

   /dev/sdb1 /data ext4 defaults 0 0 

Change this line to match what you need it to - .e.g change ``/dev/sdb`` to be
the device path you wrote down in the earlier steps. Change ``/data`` to be 
wherever the disk should be mounted. And change ``ext4`` to whatever file system
is in use (and you wrote down earlier). In nearly all cases though you probably
won't need to change anything.

Once that is done, save and exit the file, and run::

   mount -a

Now check the disk is mounted::

   df -h

Copy data back
--------------

The last step is to copy data back onto the workstation. You'll have to plug
in the USB drive in again, and then work out what it got attached as::

   lsscsi

And you should get an output somewhat similar to this::

   [0:0:0:0]    disk    ATA      KINGSTON SA400S3 71E0  /dev/sda
   [1:0:0:0]    cd/dvd  TSSTcorp CDDVDW SH-224BB  SB00  /dev/sr0
   [2:0:0:0]    disk    Seagate  Expansion        9300  /dev/sdb 

As you can see from the above, the USB drive (in this case a Seagate USB drive)
is listed and it is available at the path ``/dev/sdb``. Create the place we'll
mount it::

   mkdir /mnt/migrate

And then mount it::

   mount /dev/sdb1 /mnt/migrate

Now we can copy data back. Start with the ``/local/scratch/`` directory and use 
``rsync`` again to copy back:

   rsync -av --progress /mnt/migrate/scratch/ /local/scratch/

You can then recover the ``/home`` directory data. You probably should not
recover the data directly though. In most cases, users will be moving from
GNOME 2 to GNOME 3, and starting with a fresh home directory makes more sense.
If a user insists they want their original home directory, feel free to restore
it, but it can lead to problems, and so you should recommend that they do not.

Either restore the data into /local/scratch/home/ like so::

   rsync -av --progress /mnt/migrate/home/ /local/scratch/home/

Or restore individual directories for users (not recommended):

   rsync -av --progress /mnt/migrate/home/<username>/ /home/<username/
