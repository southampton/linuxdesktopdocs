Ruby
====

Ruby is a dynamic, open source programming language with a focus on simplicity 
and productivity. According to its developers it it has an elegant syntax 
that is natural to read and easy to write.

Installing Ruby
---------------

Red Hat Enterprise Linux 7 includes Ruby version 2.0 and can be installed like
this in a terminal::

   sudo yum install ruby rubygems ruby-devel

Other versions are also available as part of :doc:`scl`:

* Ruby 1.9.3: ``sudo yum install ruby193 ruby193-ruby-devel``
* Ruby 2.2: ``sudo yum install rh-ruby22 rh-ruby22-ruby-devel``
* Ruby 2.3: ``sudo yum install rh-ruby23 rh-ruby23-ruby-devel``

To use the other versions of Ruby you must first 'enable' them like so:

* Ruby 1.9.3: ``scl enable ruby193 bash``
* Ruby 2.2: ``scl enable rh-ruby22 bash``
* Ruby 2.3: ``scl enable rh-ruby23 bash``

For more information see :doc:`softwarecollections`

Installing gems (packages)
--------------------------

.. note::

   To install Ruby gems via ``sudo gem`` you need to be in the 
   Administrators group. See :doc:`permissions` for more information. You can 
   also use ``gem`` without ``sudo`` to install gems in your home directory.

You can install additional Ruby packages (gems) with the ``gem`` command line
tool::

   sudo gem install <package>

If you're using one of the :doc:`scl` packaged versions of Ruby then you need 
to run this command instead:

   sclsudo gem install <package>

If you don't have access to run ``sudo gem`` or you don't want to install the 
gem for everybody on the system you can install the gem in your home directory
instead like this::

   gem install --user-install <package>

To use gems installed in that location you should edit your ``~/.bashrc`` file
and add::

   if which ruby >/dev/null && which gem >/dev/null; then
       PATH="$(ruby -rubygems -e 'puts Gem.user_dir')/bin:$PATH"
   fi

And then restart your shell/terminal.
