Backups
=======

Your home directory is backed up automatically at least once a day. 

When are backups taken?
-----------------------

Your workstation will attempt to back up all the home directories between
11pm and 12am. If your computer is switched off at this time do not worry,
the next time you start your computer a backup will be attempted then instead.

Do I need to keep my computer on overnight?
-------------------------------------------

No! If you prefer to keep your computer turned off overnight then backups will
still take place. Whenever your computer starts up it will take a backup if 
one is required.

How can I check the backups are working?
----------------------------------------

You can use :doc:`deskctl` to check the status of backups. 

Can I trigger a backup?
-----------------------

TODO

Can I use my computer whilst a backup is taking place?
------------------------------------------------------

Yes. The backup system takes a snapshot of the data when the process begins
and backs up the data in the snapshot. You can thus carry on using your 
computer without affecting the backup (or the backup affecting your data). The
backup system uses LVM thin snapshots to acomplish this.

