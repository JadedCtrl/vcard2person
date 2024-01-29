VCARD2PERSON (and PERSON2VCARD)
===============================================================================
Some bash scripts that can convert in-between vcard and Haiku person files.
Sorta in the spirit of mbox2mail and mail2mbox.

It supports vcards of version 2.1, 3.0, and 4.0.— and supports all attributes
applicable to a person file (including photo [through URL or embeded image],
address, name, phone numbers, email, etc).

My use-case is converting contacts between my Android phone and Haiku, which
uses version 2.1 vcards, so that version's been tested fairly well. 
3.0 and 4.0 have only been tested on the example files in ./ex/


--------------------
USAGE
--------------------
usage: vcard2person vcard [-h] [-d directory] [-o path] file

People files will be created using the data from a vcard. Each vcard defined
by a given vcf/vcard file have its person file be named after the vcard's
full-name.
-o	changes the output person filename
-d	outputs all people files to a given directory-- useful if a file
	defines multiple vcards.
-h	prints this message.


usage: person2vcard [-h] [-v version] [-o path] person

Creates a vcard from the given person file's attributes. By default will
output to a file of the same name with a .vcf file-extension.
-o	changes output vcard filename
-v	specify vcard version: 2.1, 3.0, or 4.0. Defaults to 4.0.
	a random URL, and use it as the vcard's photo URL.
-h	print this message.


--------------------
CUSTOMIZATION
--------------------
It should be pretty easy to work with your own custom attributes-- a couple
examples are in './patches/', for a META:birthday attribute (BDAY) and for
a META:group (X-ANDROID-CUSTOM:vnd.android.cursor.item).


--------------------
BORING STUFF
--------------------
Author:  Jaidyn Ann <jadedctrl@posteo.at>
License: CC0
