# Netctltray version 0.3
Netctltray is an application that provides a system tray icon for the netctl
network manager. Via the system icon you can change profile and get query the
status of the current connection.

### Installation
#### Requirements
Requirements with a \* are optional

- Window manager with *freedesktop.org* system tray specification implemented.
- Python3 : Main programming language.
- PySide : Python interface to Qt.
- netctl : Network management.
- sudo\* : Default option for acquiring permissions to run netctl. Sudo will
	run with the ``-A`` flag that runs the password entry program in
	``$SUDO_ASKPASS``
- x11-ssh-askpass\* : Default option for querying the sudo password.

These requirements can be easily met by running:

	# pacman -S python python-pyside
	# pacman -S sudo x11-ssh-askpass

#### Installation



### Options
#### Command line options
- ``-h``, ``--help``

	Show the help message.

- ``-6``, ``--ipv6``

	Prefer ipv6 over ipv4 when showing the status.

- ``-S``, ``--sudo COMMAND``

	Use the command COMMAND for getting root permissions. By default this
	is command is ``sudo -A`` and it assumes that you have set the
	``SUDO_ASKPASS`` environment variable. It is tested with
	``ssh-askpass`` as askpass program.

- ``-N``, ``--netctl PATH``

	Location of the netctl binary. By default this is just ``netctl`` and
	thus assumes it to be in ``$PATH``.

- ``-R``, ``--nroot PATH``

	Root of the netctl configuration directory. By default this
	``/etc/netctl``.

#### Some notes
- When an interface already has an active profile the active profile will be
  	stopped prior to the start of the new profile.

- ``netctl.py`` can also work with [flexible interfaces](
	https://wiki.archlinux.org/index.php/Netctl#Using_any_interface) but it
	does this in a naive way. It runs the script and imports the
	``$Interface`` variable and uses that as interface.

- You can change the icons if you want for a better integration with your WM.
	Just change the svg files.

### Author(s)
-	Mart (mart@martlubbers.net).

### Changelog
- Version 0.2a (2015-02-13)
	- Fixed inet bug
	- Fixed bug with resources, it now searches in the path defined by the
	  RESOURCE variable in netctltray.py

- Version 0.2 (2015-02-12)

	- Rewritten menu.
	- Remove logging.
	- Added checkmark icon for active networks.
	- Added password question for network changes.
	- Added more information to readme.

- Version 0.1 (2015-01-05)

	- Initial script.
	- README.md created.
