Java
====

Java is a general purpose object oriented programming language and runtime.
It is intended to let application developers "write once, run anywhere" through
compiling Java code to 'byte code' which is then run on the Java virtual 
machine. 

Java implementations
--------------------

There are several implementations of Java available on the Linux desktop 
platform:

* Oracle - v1.6, v1.7, v1.8
* OpenJDK - v1.6, v1.7, v1.8
* IBM - v1.7, v1.8

We strongly recommend the use of either Oracle Java 1.8 or OpenJDK Java 1.8.

You can install the different versions via :doc:`deskctl` or if you prefer
here are the commands to run in a terminal to install them instead:

+--------------------+--------------------------------------------------------+
| Oracle Java 1.6    | ``sudo yum install java-1.6.0-sun-devel``              |
+--------------------+--------------------------------------------------------+
| Oracle Java 1.7    | ``sudo yum install java-1.7.0-oracle-devel``           |
+--------------------+--------------------------------------------------------+
| Oracle Java 1.8    | ``sudo yum install java-1.8.0-oracle-devel``           |
+--------------------+--------------------------------------------------------+
| OpenJDK Java 1.6   | ``sudo yum install java-1.6.0-openjdk-devel``          |
+--------------------+--------------------------------------------------------+
| OpenJDK Java 1.7   | ``sudo yum install java-1.7.0-openjdk-devel``          |
+--------------------+--------------------------------------------------------+
| OpenJDK Java 1.8   | ``sudo yum install java-1.8.0-openjdk-devel``          |
+--------------------+--------------------------------------------------------+
| IBM Java 1.7       | ``sudo yum install java-1.7.1-ibm-devel``              |
+--------------------+--------------------------------------------------------+
| IBM Java 1.8       | ``sudo yum install java-1.8.0-ibm-devel``              |
+--------------------+--------------------------------------------------------+

Sadly the Java packages do not use the :doc:`envmodules` or the :doc:`scl`
system, so you will have to use the full path to the ``java`` or ``javac`` 
binaries:

+--------------------+--------------------------------------------------------+
| Oracle Java 1.6    | ``/usr/lib/jvm/java-1.6.0-sun.x86_64/bin/java``        |
+--------------------+--------------------------------------------------------+
| Oracle Java 1.7    | ``/usr/lib/jvm/java-1.7.0-oracle/bin/java``            |
+--------------------+--------------------------------------------------------+
| Oracle Java 1.8    | ``/usr/lib/jvm/java-1.8.0-oracle/bin/java``            |
+--------------------+--------------------------------------------------------+
| OpenJDK Java 1.6   | ``/usr/lib/jvm/java-1.6.0-openjdk.x86_64/bin/java``    |
+--------------------+--------------------------------------------------------+
| OpenJDK Java 1.7   | ``/usr/lib/jvm/java-1.7.0-openjdk/bin/java``           |
+--------------------+--------------------------------------------------------+
| OpenJDK Java 1.8   | ``/usr/lib/jvm/java-1.8.0-openjdk/bin/java``           |
+--------------------+--------------------------------------------------------+
| IBM Java 1.7       | ``/usr/lib/jvm/java-1.7.0-ibm/bin/java``               |
+--------------------+--------------------------------------------------------+
| IBM Java 1.8       | ``/usr/lib/jvm/java-1.8.0-ibm/bin/java``               |
+--------------------+--------------------------------------------------------+

Setting the default system Java
-------------------------------

Instead of having to use the above method to use a particular version of Java
you may use the ``alternatives`` command to change the default version of Java
in use. This will affect every user on the system so please only do this if
you are sure you will not impact other users.

.. note::

   To set the system wide default Java you need to be in the Administrators 
   group. See :doc:`permissions` for more information.

Run the following commands and follow the instructions to change the default::

   sudo alternatives --config java
   sudo alternatives --config javac
