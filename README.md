blaunch
=======

About
-----

blaunch is a small tool written in perl/tk which shows a bar with buttons/icons
in X. If you press a button, a program will be launched.  You may customize the
bar and icons to your own liking using the configuration file. 

It's written primarily for window managers which don't have such a handy button
bar of them selfs (i.e. afterstep - because it's wharf sucks eggs), and because
I was bored and found out about perl/tk.
    
Requirements
------------

blaunch requires Perl and the Perl/Tk module installed on your system
in order to work. You may download Perl from:

    http://www.perl.com/pub/language/info/software.html

and the Perl/tk module from:

    http://search.cpan.org/search?module=Tk
	
Installation
------------

blaunch doesn't really need to be installed, but you could copy the `blaunch`
file to a directory in your path (`/usr/local/bin`, for example) for
convenience.
	
Blaunch will look for the configuration file in several places:

    ~/.blaunch.conf		(your home directory)
    /etc/blaunc.conf	(global configuration)
					 
If it can't find a configuration file, the execution will be aborted, and an
error message printed.

You should copy the icons directory somewhere too. I suggest something like:
	
    /usr/local/blaunch/icons/
		

Configuration
-------------
	
Blaunch configuration consists out of a single configuration file, called
blaunch.conf. This file may either be placed global on your system in the `/etc/`
directory:
	
    /etc/blaunch.conf
		
or your personal configuration file, in your homedirectory:

    /home/username/.blaunch.conf
		
(remember the dot)
	
In the configuration file, each line (lines starting with `#` or `%` and empty
lines not included) define a single button. Such a line consists out of a
number of elements, 4 to be precise. The elements are seperated by a comma ( `,`
)

Here's what the four elements represent:
	
*   path and filename of icon, 
*   background color of button (specify in html format #RRGGBB), 
*   background color when mouse is over button (specify in html format #RRGGBB),
*   command to execute when button is clicked
	
Example:
	
	/usr/local/blaunch/icons/bl_terminal.gif, #606060, #808080, xterm -rv -e mutt
	
Will give you a button (which becomes a lighter shade of grey when the mouse
passes over it) with bl_terminal.gif as the icon, which will start a x-terminal
with mutt in it.
	
Lines which start with a # are comments, and are ignored by blaunch, as are
empty lines. Lines which start with a `%`-sign are special configuration lines.
Currently there is only one special command:
	
	%vertical
	
or 
	
	%horizontal
	
That last one (horizontal) is the default, and is therefor not neccesary to specify.
	
For a complete example of a configuration file, see the blaunch.conf file which
came with the tar.gz file.
	
	
Copyright stuff
---------------

blaunch is Copyright by Ferry Boender, licensed under the General Public
License (GPL)

Copyright (C), 2000-2013 by Ferry Boender <ferry.boender AT gelectricmonk.nl>

This program is free software; you can redistribute it and/or modify it under
the terms of the GNU General Public License as published by the Free Software
Foundation; either version 2 of the License, or (at your option) any later
version.
    
This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE. See the GNU General Public License for more details.
    
You should have received a copy of the GNU General Public License along with
this program; if not, write to the Free Software Foundation, Inc., 675 Mass
Ave, Cambridge, MA 02139, USA.
            
For more information, see the COPYING file supplied with this program.

