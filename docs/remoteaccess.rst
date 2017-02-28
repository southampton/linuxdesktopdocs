Remote access
=============

SSH
---

You can connect to your Linux desktop via the `SSH <https://en.wikipedia.org/wiki/Secure_Shell>`_
protocol. To do so your user account needs to be in the ``users`` group. Read
the :doc:`permissions` page for more details about permissions, or use 
:doc:`deskctl` to add yourself to the SSH group.

The address to connect to will be of the form::

 uos-NNNNN.clients.soton.ac.uk

If you don't know what your computer's "UOS" number is, you can find out by
either opening :doc:`deskctl` or by opening a terminal and typing::

  hostname

For example if your computers UOS name were ``uos-57292`` you would connect to 
the address ``uos-57292.clients.soton.ac.uk``. You can then login with your
normal university username and password.


