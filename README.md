Evangelion Editor (C64)
=====================

##YTM/Elysium 28.07.2001

This is an editor for a scene magazine Evangelion that was never released (read
below for more). It features proportional font, changeable colors, many editing
functions (line buffer, insert/delete line/page), left/right/full text aligning,
wordwrap mode, changeable space width, page text compression done during page
change, it has quite fast proportional text drawing subroutine. It might also
feature something more, but my memory is less reliable than my C64's :)

#Screenshot
![Screenshot](/screenshot.png?raw=true "Screenshot from VICE")

#Quick start
Type 'acme evaeditor.tas' and run evaeditor.prg on your C64
Type RUN/STOP to get to menu. CTRL+H sequence does not work, there is no
information on keybindings, but these are fairly good documented in source.
F1/2/3 are for text justifying, F5/6 next/previous page.

#History
I started writting this editor in summer '96
for C-64,5 magazine. It was constantly bugfixed and changed to summer '98.
Then C-64,5 died and Evangelion was about to rise on its remains. However in
the 1st quater of '99 it was clear to me that Evangelion #1 will never be released.
Development took too much time and I had other important things to do.

#Build
The editor can be build with ACME crossassembler (search ftp.elysium.pl for it).
Resulting binary is ready for running and/or crunching.
Whole thing was initially written in Turbo Macro Assembler and at the end had ~3000
lines. On 30.12.1998 it was moved to PC for use with MMS/Taboo 6502tass and on 28.07
it was converted for use with ACME.

#Info
The editor uses own file format. The first page contains offsets to next pages
(e.g. $0000/$0001 points to start of page1), at offset $0100 you have the first
page. Pages are organized in 23x128 bytes rows, all run-length packed. The magic value
is $ff, look into pack subroutine for more. In order to display a page it is not
necessary to decompress a page. (in case you didn't know that already). There is also
line colors info attached somewhere (23 bytes) but I can't remember where.

#Files

- evaeditor.prg is an assembled output
- font.bin is the font in binary format with 2 load address bytes, each 8 bytes describe one 8x8 character cell, all characters are shifted to the left
- width.bin is a table of widths of each character in font.bin

