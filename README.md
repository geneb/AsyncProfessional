# TurboPower Async Professional v2.03

22 years ago, TurboPower Software closed their doors as a retail software company and released all of their development libraries the for Borland[1]/CodeGear/Embarcadero Delphi compiler.  These items were released under a Mozilla 1.1 license.

Here's their original announcement: http://www.turbopower.com/

Unfortunately, nobody seems to have been able to get their attention about making their fantastic MS-DOS libraries for Turbo Pascal available online.

Their website clearly states, "TurboPower libraries released as open source".  Their MS-DOS libraries would appear to fall under that statement.  Maybe they figured, "Hey, it's 2003. Nobody's going to be interested in this ancient DOS stuff!"

Well dammit, **I'm** interested!  I'm sure I'm not the only one.

The original product description for Async Professional can be found [here](https://web.archive.org/web/19990129040306/http://www.turbopower.com/products/appascal/).

While doing research for this project, I found that I had version 2.00 of Async Professional, but the last released version appears to be v2.03.  I went searching to see if I could find patches for v2.00, but I came up empty.  However, I did find v2.01 on [Discmaster](http://discmaster.textfiles.com), as well as patches to v2.02 and v2.03.  Those patches were successfully applied and that is what you'll find in this repository.  A patch to prevent Runtime Error 200 crashes on fast computers was also applied to the APTimer unit.

## Building

Async Professional can be built using Turbo Pascal versions 5.5 to 7.0, and Borland Pascal v7.0.  In the case of Borland Pascal 7.0, units can be built for both real mode (TPU) and protected mode (TPP).  The build process also requires Turbo Assembler v1.0 or greater, or Microsoft Assembler v4.0 or greater in order to assemble the .ASM files.  You'll need to ensure that your build tools are in your DOS path.

The file SRC\APDEFINE.INC has settings that can be changed in order to affect how Async Professional is built and functions.  It would be worth your time to peruse that file - note that unless you know **why** you're going to change something, you probably should leave it the default.

The Makefiles for Async Professional can be found in `SRC\APRO.MAK` and `SRC\APROO.MAK`.  These files will allow you to adjust a number of different things about how the units are built.  I recommend going through it - the settings it uses are very well documented.  Note that the Makefile uses the Borland Make syntax.  The `APRO.MAK` file will build the procedural version of Async Professional, while `APROO.MAK` will build the object oriented version.

Change to the SRC directory and kick off the build with `MAKE -FAPRO`.  This will build all the units and all the object files. Copy all the TPU and/or TPP unit files to some location that you can easily point the compiler's Unit Directory setting at.  You're done!

## Documentation

I currently have no manuals for versions of Async Professional prior to version 3.  The help files in the HELP directory are very comprehensive and when used with the POPHELP tool, will be useful for you.

If you or someone you know have the Async Professional manual and would be willing to loan them out, I would be happy to non-destructively scan them and return them at my expense. 

Hopefully more people than just me will find this repository useful.

