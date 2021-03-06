stealthshell
=================

As an upgrade to the :ref:`injectorshell` (implementation in `ssh-mitm <http://ssh-mitm.at/>`_ done by me) the stealthshell
provides a way to workaround the problem of interfering with the clients interactive session.
It only executes injected commands when the shell of the user wont be affected. As long as the interactive shell of the
client is not typing or executing a command input from the injector shells is halted and put in a waiting queue.

Using the ``--ssh-injector-super-stealth`` option the injector shells will only send whole commands instead of
every keystroke. This further eliminates unwanted behavior. Unfinished commands from the injector shells are not seen
by the server and the user of the interactive shell will never be surprised by input they never typed. This, however,
will limit the terminal functionality of the injector shell. Because the server only responds to the whole command,
terminal features like command auto-completion when pressing tab or command history with the up and down keys will not
work correctly.


.. note::
    Environment considerations of the :ref:`injectorshell` are still uphold by the stealthshell. Discrepancy problems
    described by the :ref:`injectorshell` are solved by this newer edition (client cannot be interrupted by injected keystrokes BUT
    unfinished injected strokes will be seen by the server). Only with the ``--ssh-injector-super-stealth`` option will the
    discrepancy between the user and all injector shells not occur. It is recommended that the ``--ssh-injector-super-stealth``
    option is used in combination with the ``--ssh-injector-enable-mirror`` option to see more clearly when commands
    can be executed.

For a more detailed look at the plugins operation refer to the :ref:`injectorshell` documentation.
