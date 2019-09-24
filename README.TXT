README.TXT

                          Stackworks SL5

1. Introduction
---------------

We are delighted to present Stackworks SL5 v1.2 for CP/M in both 8080
and Z80 versions.

Also included are electronic versions of the manual, reconstructed
source for the Z80 and 8080 metacompilers, and a port of SL5 to
PC/MS-DOS.

Stackworks SL5 is copyrighted software released under the GNU General
Public License.  Our thanks to Dave DeLauter for allowing SL5 to be
publicly distributed.

Note: Where original files or documentation was not available we have
provided substitutes.  See the filelist below for details.


2. Files included in this package
---------------------------------

SL5 v1.2 for CP/M Z80

  Z80 <DIR>
  ASSEM.COM      original
  ASSEM.SL5      original
  COMMOD.SL5     original     copied from 8080 distribution
  DEBUG.COM      original
  DEBUG.SL5      original
  DEV.COM        original
  ICOND.SL5      original
  KERNEL.SL5     original
  SYSMAKE.COM    original
  SYSMAKE.SL5    new          target compiler source reconstructed
  SL5.COM        original
  SL5.DOC        original     copied from 8080 distribution
  SL5.TXT        new          plain text version of SL5.DOC

SL5 v1.2 for CP/M 8080

  8080 <DIR>
  ASM8080.TXT    new          8080 assembler documentation 
  ASSEM.COM      recompiled
  ASSEM.SL5      original
  COMMOD.SL5     original
  DEBUG.COM      recompiled
  DEBUG.SL5      original
  DEV.COM        recompiled
  ICOND.SL5      original
  KERNEL.SL5     fixed        original moved to BACKUP directory 
  SYSMAKE.COM    recompiled
  SYSMAKE.SL5    new          target compiler source reconstructed
  SL5.COM        original
  SL5.DOC        original
  SL5.TXT        new          plain text version of SL5.DOC

  8080\BACKUP <DIR>
  KERNEL.SL5     original
  README.TXT     new

SL5 v1.2 for 8086 DOS

  8086 <DIR>
  ASM8086.TXT    new          8086 assembler documentation 
  ASSEM.COM      new          SL5.COM with assembler
  ASSEM.SL5      new          8086 assembler source
  COMMOD.SL5     original     see SL5.TXT
  DEBUG.COM      new          SL5.COM with debugging package
  DEBUG.SL5      original     see SL5.TXT
  DEV.COM        new          SL5.COM with assembler and debugging package 
  ICOND.SL5      original     see SL5.TXT
  KERNEL.SL5     new          8086 kernel source
  README.TXT     new          read this first
  SMAK8080.SL5   new          8080 SYSMAKE modified to run under CP/M or DOS
  SMAKZ80.SL5    new          Z80 SYSMAKE modified to run under CP/M or DOS
  SYSMAKE.COM    new          8086 target compiler (DOS executable)
  SYSMAKE.SL5    new          80086 target compiler source runs under CP/M or DOS
  SL5.COM        new          binary form of KERNEL.SL5  (DOS executable)
  SL5.TXT        new          plain text version of SL5.DOC

Documentation

  DOC <DIR>

  To be included


Notes:

- Several binaries from the SL5 8080 distribution were missing. These 
  have been recompiled from the SL5 sources.

- SYSMAKE.COM for the SL5 8080 was missing. The version enclosed is
  based on a decompilation of the Z80 SYSMAKE binary as were the
  SYSMAKE sources.

- The manual for SL5 8080 was not available so we have provided
  substitute documentation for the 8080 assembler.  See ASM8080.TXT.

- The 8086 directory contains an experimental port of SL5 to PC/MS-DOS.
  See README.TXT for further information.


3. Recompiling the SL5 binaries
-------------------------------

The following describes the steps necessary to rebuild the SL5
executables supplied with Stackworks SL5.

This information applies specifically to Stackworks SL5 version
1.2 for the 8080 and Z80.

                         IMPORTANT

DO NOT USE YOUR ORIGINAL DISKETTE OR FILES AS THIS PROCEDURE
WILL OVERWRITE THEM. ONLY USE COPIES.


3.1. Metacompiling the SL5 kernel (SL5.COM)

You will need the following files:

  SYSMAKE.COM
  KERNEL.SL5
  COLD.SL5

To compile SL5.COM perform the following steps.  If you do not
wish to overwrite SL5.COM choose another filename for the object
file e.g. KERNEL.COM

  A>SYSMAKE.COM

  Sysmake version 1.2    Z80 - CP/M
  (C) Copyright 1980 The Stackworks

  Enter 'STAT' to examine parameters
  Enter 'RAMGEN' to generate a RAM based system
  Enter 'ROMGEN' to generate a ROM based system

  1 INFOF !      ( optional - turns off listing )

  >RAMGEN        ( select RAM target )

  Enter object file name >SL5.COM    ( or a name of your choice )
  Enter Kernel source file name >KERNEL.SL5

  More input (Y/N) ? N

  Do you want a symbol table (Y/N) ? Y

  Successful compilation

Provided KERNEL.SL5 has not been changed, the resulting kernel
can be expected to be byte-identical with the original.


3.2. Compiling DEBUG.COM ASSEM.COM DEV.COM

You will need the following files:

  SL5.COM
  COMMOD.SL5
  DEBUG.SL5
  ASSEM.SL5

To build DEBUG.COM perform the steps:

  A>SL5.COM

  >FLOAD DEBUG.SL5

  >FLOAD COMMOD.SL5

  Set the variable ?SYMTAB to 0 if the symbol table is not needed.
  Execute 'MAKECOM program.com' when ready.

  >MAKECOM DEBUG.COM

To build ASSEM.COM perform the steps:

  A>SL5.COM

  >FLOAD ASSEM.SL5

  >FLOAD COMMOD.SL5

  Set the variable ?SYMTAB to 0 if the symbol table is not needed.
  Execute 'MAKECOM program.com' when ready.

  >MAKECOM ASSEM.COM

To build DEV.COM perform the steps:

  A>SL5.COM

  >FLOAD ASSEM.SL5

  >FLOAD DEBUG.SL5

  >FLOAD COMMOD.SL5

  Set the variable ?SYMTAB to 0 if the symbol table is not needed.
  Execute 'MAKECOM program.com' when ready.

  >MAKECOM DEV.COM

Due to differences in available memory size, the resulting
executables will usually NOT be byte-identical with the originals.

--

