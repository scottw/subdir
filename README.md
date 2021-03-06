# subdir #

Like `ls -1 *.py` but subtracts matching files in a directory you specify.

## usage ##

    subdir srcdir files

## description ##

All files matching `files` will be listed as long as the file doesn't
already exist in `srcdir`. In other words, "list all matching `files`
*except* for those found in `srcdir`".

If we were using sets, you could think of it as:

    files - srcdir = subdir

## example ##

If `glob/*.py` matched these files:

    glob/bar.py
    glob/baz.py
    glob/blech.py
    glob/foo.py
    glob/glarch.py

and `srcdir` had these files in it:

    srcdir/baz.py
    srcdir/foo.py

then the output of `subdir srcdir glob/*.py` will be `glob/*.py -
srcdir`, or:

    glob/bar.py
    glob/blech.py
    glob/glarch.py

Notice `baz.py` and `foo.py` have been subtracted from the output
because they exist in `srcdir`.

## author ##

Scott Wiersdorf
scott@perlcode.org
