E-Mail
======

Unfortunately the univerity's e-mail solution is Microsoft Exchange.

Using Outlook web access
------------------------

The easiest way to access your e-mail (and calendars and contacts) is to use 
Outlook web access:

* Staff and postgraduates: `www.outlook.soton.ac.uk <www.outlook.soton.ac.uk>`_
* Students: `www.outlook.com/soton.ac.uk <www.outlook.com/soton.ac.uk>`_

Using GNOME / Evolution
-----------------------

The next easiest way to access your e-mail (and contacts) is to use the e-mail
client in GNOME - evolution. The fastest way to set it up is to open Settings
and click ``Online Accounts``.

* Click "Add an online account" 
* Choose "Microsoft Exchange"
* Enter the E-Mail as yourusername@soton.ac.uk 
* Enter your normal university password

Open Evolution and your e-mail account will have automatically been created.

Using other clients
-------------------

If you decide to use another e-mail client you'll likely want to use IMAP and
SMTP for sending and receiving e-mails. The support in Microsoft Exchange for
IMAP clients is very poor however (performance is appauling and the IMAP server
is not very compliant to the RFC - surprising, no?). We thus recommend either
using Outlook Web Access or Evolution, but if you really do want to take the 
plunge, here are the details:

* IMAP server: ``imap.exchange.soton.ac.uk``
* IMAP security: SSL/TLS (port 993)
* SMTP server: ``smtp.soton.ac.uk``
* SMTP security: STARTTLS (port 25)
