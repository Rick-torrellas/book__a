---
title: "Magic Variables"
description: ""
---

Magic Variables
===============

The magic variables %n contains the arguments used to invoke the file: %0 is the path to the bat-file itself, %1 is the first argument after, %2 is the second and so on.  

Since the arguments are often file paths, there is some additional syntax to extract parts of the path. ~d is drive, ~p is the path (without drive), ~n is the file name. They can be combined so ~dp is drive+path.  

%~dp0 is therefore pretty useful in a bat: it is the folder in which the executing bat file resides.

You can also get other kinds of meta info about the file: ~t is the timestamp, ~z is the size.

Se pueden reprensetar a todos los argumentos de esta manera.


```cmd
%*
%~1         - expands %1 removing any surrounding quotes (")
%~f1        - expands %1 to a fully qualified path name
%~d1        - expands %1 to a drive letter only
%~p1        - expands %1 to a path only
%~n1        - expands %1 to a file name only
%~x1        - expands %1 to a file extension only
%~s1        - expanded path contains short names only
%~a1        - expands %1 to file attributes
%~t1        - expands %1 to date/time of file
%~z1        - expands %1 to size of file
%~$PATH:1   - searches the directories listed in the PATH environment variable and expands %1 to the fully qualified name of the first one found.  If the environment variable name is not defined or the file is not found by the search, then this modifier expands to the empty string    
%~dp1       - expands %1 to a drive letter and path only
%~nx1       - expands %1 to a file name and extension only
%~dp$PATH:1 - searches the directories listed in the PATH environment variable for %1 and expands to the drive letter and path of the first one found.
%~ftza1     - expands %1 to a DIR like output line
```

This can be also found directly in command prompt when you run CALL /? or FOR /?