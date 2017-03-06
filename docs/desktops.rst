Desktop environments
====================

GNOME 3
-------

GNOME 3 is the default desktop environment on university Linux desktops. It is 
the most feature complete and useful desktop and as such as we highly 
recommend using it.

GNOME 3, like many recent desktop environments, does not use the classic
Windows style task bar model, or the Mac OS X style dock model. It can however
be heavily customised by the *GNOME Tweak Tool* and :doc:`gnomeext`. 

Xfce 4
------

XFCE is a lightweight alternative to GNOME, whilst still utilising a lot of 
the core components of GNOME. It can be heavily customised and is considered a
more traditional desktop environment. If you do not like GNOME 3 then we
recommend using XFCE instead.

You can use :doc:`deskctl` to install XFCE, or use the following command in a
terminal::

   sudo yum groupinstall xfce-desktop

KDE Plasma
----------

KDE Plasma is the latest version of the K Desktop Environment, an alternative 
desktop platform based on the Qt framework. Unlike KDE 3, the KDE Plasma 
environment is not well regarded, and it lacks a lot of features and maturity
of both GNOME and XFCE. Although available to install we do not recommend
using KDE Plasma.

You can use :doc:`deskctl` to install KDE, or use the following command in a
terminal::

   sudo yum groupinstall kde-desktop-environment

MATE
----

MATE is a fork of the GNOME 2 project, and as such it is essentially an updated
GNOME 2 desktop environment. If you liked GNOME 2, and wish to continue using 
it, then MATE may suit you. The latest version of MATE - 1.16 - is available
and despite being based on GNOME 2 has been largely rewritten in GTK3.

You can use :doc:`deskctl` to install MATE, or use the following command in a
terminal::

   sudo yum groupinstall kde-desktop-environment

i3
--

i3 is a tiling window manager similar to wmii. It is not a full desktop 
environment and it is intended for advanced users. Unless you have experience
with ultra lightweight tiling window managers we do not recommend using i3.

You can use :doc:`deskctl` to install i3, or use the following command in a
terminal::

   sudo yum install i3

Others
------

Several other desktops are available:

- Cinnamon: ``sudo yum install cinnamon-desktop``
- LXDE / LXQt: ``sudo yum install lxqt-session lxqt-panel lxqt-config lxqt-powermanagement lxqt-wallet lxqt-policykit`` 

Several other window managers are available:

- xmonad: ``sudo yum install xmonad``
- fluxbox: ``sudo yum install fluxbox``
- openbox: ``sudo yum install openbox``
- IceWM: ``sudo yum install icewm``
- Matchbox: ``sudo yum install matchbox-window-manager``
- WindowMaker: ``sudo yum install WindowMaker``
- spectrwm: ``sudo yum install spectrwm``
- fvwm: ``sudo yum install fvwm``
- pekwm: ``sudo yum install pekwm``
- vtwm: ``sudo yum install vtwm``
