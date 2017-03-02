Backups
=======

Your home directory is backed up automatically at least once a day. 

When are backups taken?
-----------------------

Your workstation will attempt to back up all the data in ``/home`` between
11pm and 12am. If your computer is switched off at this time do not worry,
the next time you start your computer a backup will be attempted then instead.

Do I need to keep my computer on overnight?
-------------------------------------------

No! If you prefer to keep your computer turned off overnight then backups will
still take place. Whenever your computer starts up it determines if a backup should be taken and then initiates a backup if required.

How can I check the backups are working?
----------------------------------------

You can use :doc:`deskctl` to check the status of the last backup attempt.

You can also, if you prefer, run the following command in a terminal::

   sudo drone backup status

Can I trigger a backup?
-----------------------

Yes you can start a backup whenever you need to, this allows you to take a 
backup before turning your computer off for the day for example. You can start
a backup using :doc:`deskctl` or if you prefer you can run the following 
command in a terminal::

   sudo drone backup now

Can I use my PC whilst a backup is underway?
------------------------------------------------------

Yes. The backup system takes a snapshot of the data when the process begins
and backs up the data in the snapshot. You can thus carry on using your 
computer without affecting the backup (or the backup affecting your data). The
backup system uses LVM thin snapshots to acomplish this.

Do backups work outside the University network?
-----------------------------------------------

No. For the backups to work you must be either:

- Connected to the university network via a cable

or 

- Connected to the university virtual private network (VPN) service
