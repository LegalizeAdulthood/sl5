The BACKUP directory contains copies of the original (unmodified)
binaries and source.  These were found to have bugs and issues as
described below.  The parent directory contains the corrected
versions.

KERNEL  .SL5	ROM targets fail due to variable RPTR being initialized
                twice.  Note: It is uncertain whether this is a bug in
                the kernel source or the replacement SYSMAKE.  Until
                the original SYSMAKE is located and further tests made,
                we are providing a modified kernel which resolves the
                problem.

