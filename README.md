# runxl
## a script to start the atari800 emulator with a game from the command line

This is a bash script to start the atari800 emulator with a specific game, program or diskette.
The script scans your atari program directory recursively to find the game you're looking for.

It also scans index files for
* disks which contains more then one game
* programs which needs special emulator parameters to start (i.e. emulate an old 48k Atari 400/800)
* programs which needs a DOS disk
* Multiple disk games, each in its own drive

An index file stub for the current directors can be created with

	makeindex

but needs to be edited to work.

## Installation

runxl assumes that your atari 8-bit programs are stored in 

	/usr/share/atari

and subfolders.


## Usage

	./runxl <name of the game>

for a helpful discription use

	./runxl -h

## Index files
runxl looks for indexfiles in the directory tree of atari files.
the index files must be called runxlindex*.txt, this means that valid index file names are i.e.:

	runxlindex.txt
	runxlindex_myfiles.txt
	runxlindex12345.txt

you get the idea.

Each index file is responsible for the disk images (xfd, atr) or atari programs (xex) of the directory whre it is located.

### Index file format
1st line: Name of the collection

2nd line: global options for the emulatior, i.e. -basic if the collection only contains programs written in BASIC

3rd-nth line: Program list:
Disk-image-name|Program name|Emulator options


Example index file:

	Atari 800XL Game Disk 01
	-basic
	Game_Disk_1.atr|DOS 2.5|
	Game_Disk_1.atr|Gnu attack (Basic)|
	Game_Disk_1.atr|Caverns of Foo (Basic)|
	Game_Disk_1.atr|Chicken Race (Basic)|
	Game_Disk_2.atr|Minced Meat (Basic)|
	Game_Disk_2.atr|Bloodshed (Basic)|
	Game_Disk_2.atr|F1 Worm race (Basic)|
	Game_Disk_2.atr|Crazy Chef (Basic)|

With this index file, cou can type

	./runxl Minced

and runxl will find the all corresponding entries, displays a list and asks for the program to start.

## TBD
* more documentation
* translate all text and comments to english
