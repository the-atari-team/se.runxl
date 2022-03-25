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
but need to be edited to work.

# Installation

runxl assumes that your atari 8-bit programs are stored in 
	/usr/share/atari
and subfolders.


# Usage

	./runxl <name of the game>

for a helpful discription use

	./runxl -h


# TBD
* more documentation
* translate all text and comments to english
