# dpp
A document preprocessor, styled after cpp, that conditionally compiles documents based on preprocessor directives (currently #ifdefs).  Written in bash.

dpp scans a specified input file ($1) for any occurence of a cpp #ifdef with conditional $2.  

If $2 is found, that #ifdef'ed text is included in the text output (to stdout).

If any #ifdef is found whose conditional does not match $2, the entire conditional block is excluded from the output.  All preprocessor directives are removed from the output as well.



