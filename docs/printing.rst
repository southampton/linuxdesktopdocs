Printing
========

The university uses a 'follow me' printing service where you can submit a print
job from your desktop and then print from any multi-function printer (MFD) on
the university network.

There are two default printer queues set up for this on your Linux desktop which
you can use 'out of the box'. The queues are called ``mono`` and ``colour``. The 
first time you print to either of them you will be prompted to enter your
university username and password. Sadly owing to limitations in CUPS
(the Linux printing system) we cannot automatically authenticate you. Instead 
you can opt to save your username and password, and the password is stored
in your GNOME keyring (where it is encrypted).

If you have administrator rights granted to you on your desktop (i.e. you are in
the ``sys`` group), you can add and edit printers. You may want to add a new 
printer if you are in a lab which has a printer other than the normal University
MFDs.

To add such a printer:

1. Open the GNOME Settings application (Applications -> System Tools -> Settings) and then choose Printers. Note that you may also find Print Settings, which is a separate method of adding a printer and not documented here.
2. Choose Unlock and, if prompted, enter your username and password to authenticate.
3. Next, click the plus (+) button that's underneath the list of printers and the Add a New Printer dialog will appear.
4. In the text box at the bottom of the dialog, enter: ``smb://servername/``, where ``servername`` should be listed on the label on the printer you wish to add. ``servername`` will often be something like ``server1.printing.soton.ac.uk``.
5. As you enter this you will be prompted to authenticate to the print server, after which, you should be given a list of printers.
6. Double-click on your printer from the list - it should match the name that is on the label on the printer, e.g. ``PR_B12_R3456_P01``
7. Next, the Select Printer Driver dialog should appear. Choose ``Generic`` from the list on the left and then ``Generic PostScript Printer`` from the list on the right.
8. Press the Select button.
9. The printer is now added to the system, and you should now be able to print to it
10. Note that you can't set a system-wide default printer here as that is managed by system policy (and if you manage to change it, it will get reverted), however you can change the default printer for your account on your desktop using the documentation below.

To change the default printer:

1. Open the Print Settings application
2. Right-click the printer you wish to make the default for you
3. Choose Set as Default from the menu
4. Choose Set as my personal default printer
5. Click OK
