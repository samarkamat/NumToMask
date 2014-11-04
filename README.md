NumToMask
=========

The purpose of this utility is to convert numerals to human readable flags, based on a bitmask config file.

Usage:
------
`NumToMask.py [-a] [-d|D] CONFIG_FILE NUMERAL`

Options:
-------
`-a` Prints all (nonblank) lines from the config suffixed with =0 or =1 depending on if each is active based on the input
`-d` Prints the binary version before the active flag 
`-D` Only prints the binary value, without any flag names (will override `-d`)

Config Format:
--------------
The config file will contain a string per line. The first line represents the first bit (2^0), the second line represents the second bit (2^1), etc. Empty lines are placeholders for unused flags, and will not be printed even if that bit is active in the input. 

For example, consider test.cfg:
```
flag1
flag2
flag3

flag4
flag5
```
Running `NumToMask.py test.cfg 46` would output:
```
flag2
flag3
flag5
```


