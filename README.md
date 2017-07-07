# Grinnell College GNU/Linux Printer Installation (GC-LPI)

Created by Zachary John Susag.

Copyright (C) 2017 Zachary John Susag

## About
**GC-LPI** contains the materials needed to get printers on the Grinnell College
network working on a GNU/Linux system. **GC-LPI** primarily consists of two Shell
scripts: `install_papercut` and `install_grinnell_printer`. See below for usage
information.

**GC-LPI** also provides the necessary files in order to
install [Papercut](https://www.papercut.com/) on the system. All files within
the `papercut/` directory are not created by the author (Zachary J. Susag) and
so holds no claim to anything within. Configuration of Papercut to work with
Grinnell College's print servers was done by staff members
of [Grinnell College](https://www.grinnell.edu).

## Requirements
**GC-LPI** requires [CUPS](https://www.cups.org/) to be installed on GNU/Linux.

**GC-LPI** recommends that the GNU/Linux workstation that **GC-LPI** is operating on
be connected to the Grinnell College network for testing purposes. In order to
test whether installation was successful any virtual private networks (VPNs)
must be inactive.

## Usage
The installation process consists of two steps:

1. Install the Papercut software.
2. Install any desired printers.

Be sure to clone this repository down to your local workstation before
proceeding. The download location does not matter.

### Install Papercut
**GC-LPI** makes installing Papercut for use on GNU/Linux workstations easy!
Simply run the following command while within the cloned repository:
```
sudo ./install_papercut
```
The script will automatically copy over the necessary files and configure
Papercut to work with your system. It will create a new user as Papercut
requires the script it uses to run to be owned under a separate, papercut,
user.

The script also installs a symbolic link within `/usr/bin` to the installed
script to make starting Papercut easier for the user. To start Papercut, simply
execute `papercut` from a terminal. I would recommend running Papercut as a
background process by using the `&` operator.

### Install Printer
**GC-LPI** will install any printer that you desire on the Grinnell College
network. Within the repository this is a CSV file titled `grinnell_printers.csv`
with all of the printers on campus alongside with the location of the
printer. With a printer in mind, simply  in the name(s) of the printer(s), as
command line arguments to `install_grinnell_printer`. 

For example, if I wanted to install Duerer, I would type
```
sudo install_grinnell_printer Duerer
```
You can type in the name of the printer with or without capital letters.

## Testing
To make sure that everything was installed correctly in a terminal type
```
echo "Hello, world!" | lpr -P printer
```
This will send a print job to the printer, `printer`, with the text "Hello,
world!". Be sure to have Papercut running before typing the command or the job
will not be submitted to Grinnell College's print servers.

## License
**GC-LPI** is distributed under the GNU GPLv3
license. Contact [susagzac@grinnell.edu](mailto:susagzac@grinnell.edu) with any
questions about licensing.

I do not claim to own any part of Papercut or take credit for it. It is simply
necessary for the correct operation of this program and required for student
printing at Grinnell College.
