ddc
===

Display Data Channel utility for Mac OS X  
© 2012 Philipp Antoni, infinise.com

Used to read and control display settings via the DDC protocol. Largely based on http://lists.apple.com/archives/accessibility-dev/2011/Feb/msg00000.html and lots of trial and error.


Warning
-------

__This tool might seriously crash your whole computer.__ It's low-level and severly under-tested. 

Here's where it's confirmed to fully work:

* OS X 10.7.4, Late 2011 MacBook Pro, Samsung S27A850T via DisplayPort or HDMI

Confirmed to work, but returning wrong information:

* OS X 10.8.2, Early 2011 MacBook Pro, Acer P246H

Confirmed to __freeze the whole system:__

* OS X 10.8.1, Late 2008 MacBook Pro
* OS X 10.8, 2008 MacBook

If you have any luck with your setup please let me know: http://twitter.com/philippantoni


Usage
-----

Read:  
`ddc <decimal VCP code>`

Write:  
`ddc <decimal VCP code> <decimal value>`


Examples
--------

Get current brightness level	  
`ddc 16`

Set brightness level to 75%  
`ddc 16 75`

Increase brightness by 10%  
`ddc 16 +10`

Save settings (required after some changes)  
`ddc 176 1`

Disable display OSD (value 2 to re-enable)  
`ddc 202 1`


What to do with this
--------------------

The first step would be to check whether your display supports DDC. Run `ddc 16` and see if it ouputs anything reasonable.

You could then use FunctionFlip to regain control over the F1 & F2 keys on your keyboard and bind those to the included AppleScripts with an app like Alfred.


Further reading
---------------

Learn about DDC on Wikipedia (not very helpful though):  
http://en.wikipedia.org/wiki/Display_Data_Channel  
http://en.wikipedia.org/wiki/Monitor_Control_Command_Set

Some actual information about how DDC works:  
http://www.boichat.ch/nicolas/ddcci/specs.html

This document contains a list of all VCP codes (not guaranteed to work for your monitor):  
http://d.pr/f/ea49 (.doc, see page 20)

Two free (but very complex) Windows tools to detect your monitor's capabilities:  
http://www.entechtaiwan.com/lib/softmccs.shtm  
http://www.portrait.com/enu/dt/toolbox.html