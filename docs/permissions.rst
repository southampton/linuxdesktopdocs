Permissions
===========

Standard permissions
--------------------

All members of the University of Southampton can log on to any Linux Desktop. 
Once logged in you are granted all normal Linux account rights, and in addition
you may perform the following actions:

- Can install software packages via :doc:`deskctl`
- Can install software packages via GNOME Software
- Can mount and umount file systems via ``sudo mount`` (See :doc:`mount`)
- Mount a file systems via GNOME disk management
- Can manage NVIDIA graphics settings via ``sudo nvidia-settings``
- Can reboot/poweroff/hibernate/suspend the computer
- Can run the following commands: ``reboot``, ``poweroff``, ``halt``

Additional permissions
----------------------

There are four user groups on each workstation which grant additional
privileges:

SSH Access
^^^^^^^^^^

Users in the group ``local`` are granted the privilege of being able to logon
to the system via SSH from anywhere within the university network.

Administrator
^^^^^^^^^^^^^

Users in the group ``sys`` are considered administrators. Although they lack
full root access they are granted several privileges. They can use ``sudo`` to
run the following commands as root:

- ``yum`` - for installing software packages
- ``rpm`` - for installing local RPM packages
- ``pip`` - for installing Python packages
- ``cpan`` - for installing Perl modules

They are also granted permissions via ``PolicyKit`` to do the following:

- Manage local storage via GNOME disks (or any ``udisks2`` application)
- Full control over power management
- Change locale settings
- Remove software packages
- Update the system software
- Trigger an offline system update
- Manage the date and/or time
- Manage printers (including adding printers)
- Manage the network settings
- Manage ``tuned``

iSolutions are more than happy to grant additional privileges to these users
upon request.

Virtual Box
^^^^^^^^^^^

Users in the ``vboxusers`` group can utilise Virtual Box.

Root access
^^^^^^^^^^^

Users in the ``wheel`` group are granted full root access via ``sudo`` and 
are granted all privileges via ``policykit``.

Granting permissions
--------------------

You can use :doc:`deskctl` to add and remove users from groups. Local 
administrators (users in the group ``sys``) can add and remove users 
from the following groups:

- SSH access (``users``)
- Administrators (``sys``)
- VirtualBox users (``vboxusers``)

Only iSolutions staff in the ``linuxadm`` or ``linuxsys`` groups can add or
remove users from the ``wheel`` group.
