# dpp (10)

#### NAME
> dpp - The document preprocessor
  
#### SYNOPSIS
> dpp *infile* *conditional*

#### DESCRIPTION
> dpp scans *infile*, looking for cpp **#ifdef** directives.  When it finds one, it compares the conditional for that directive to *conditional* and, if they match, copies all lines between the **#ifdef** and the matching **#endif** to stdout.  Any lines not inside an **#ifdef** are automatically copied to stdout.
>  
> Any **#ifdef** that does not match *conditional*, along with all text contained in that block, is excluded from the output.  All preprocessor directives are also excluded from the output.
>
> Valid **#ifdef** lines have the form:
>
    #ifdef ASCII_CHARS_NO_SPACES
>    
> dpp uses the first space character to delimit **#ifdef** conditionals.  Only the first non-space-containing string after the **#ifdef** is recognized; any additional characters on the line, after the second space, are ignored. So, for example, a directive like this:
>
    #ifdef HOSPITAL CLI
>    
> would match the *conditional* HOSPITAL, but not CLI or HOSPITAL CLI. 
  
#### FILES
> *infile* can be text of any format, containing any markup/markdown desired.  dpp does not attempt to parse any of the non-directive lines in the file; they are copied to stdout verbatim unless excluded by a non-matching **#ifdef** directive. 
