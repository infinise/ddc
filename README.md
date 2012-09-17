ddc
===

Display Data Channel utility for Mac OS X  
© 2012 Philipp Antoni, infinise.com

Used to read and control display settings via the DDC protocol. Largely based on http://lists.apple.com/archives/accessibility-dev/2011/Feb/msg00000.html and lots of trial and error.

Provided as-is, without warranty or support, bla bla. __This might seriously crash your whole computer but shouldn't do any harm.__ Only tested on a 2011 MacBook Pro with OS X 10.7.4 and a Samsung S27A850T via DisplayPort.


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