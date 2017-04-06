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

You do not need to leave your computer on overnight. If you prefer to keep 
your computer turned off then backups will still take place. Whenever your 
computer starts up it determines if a backup should be taken and then initiates 
a backup if required.

How long are backups kept for?
------------------------------

Backups of each workstation are kept for 30 days after the backup was taken.

If your machine is not switched on, or otherwise unavailable, for 30 days, then
all backup data will be deleted. To ensure you always have a copy of data 
in case of hardware failure please ensure your computer takes at least one 
backup a month.

How can I check the backups are working?
----------------------------------------

You can use :doc:`deskctl` to check the status of the last backup attempt.

You can also run the following command in a terminal::

   sudo drone backup status

Can I trigger a backup?
-----------------------

Yes you can start a backup whenever you need to. This allows you, for example, 
to take a backup before turning your computer off before leaving the office. You
can start a backup using :doc:`deskctl` or if you prefer you can run the 
following command in a terminal::

   sudo drone backup now

Can I use my PC whilst a backup is underway?
--------------------------------------------

Yes. The backup system takes a snapshot of the data when the process begins
and backs up the data in the snapshot. You can thus carry on using your 
computer without affecting the backup (or the backup affecting your data). The
backup system uses LVM thin snapshots to accomplish this.

Do backups work when outside the University network?
----------------------------------------------------

For the backups to work you must be either:

- Connected to the university network via a cable

or 

- Connected to the university virtual private network (VPN) service
