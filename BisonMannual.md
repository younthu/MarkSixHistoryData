#BISON



## NAME
       bison - GNU Project parser generator (yacc replacement)

## SYNOPSIS
       bison  [	 -b file-prefix ] [ --file-prefix=file-prefix ] [
       -d ] [ --defines ] [ -k ] [ --token-table ] [ -l ] [ --no-
       lines  ] [ -n ] [ --no-parser ] [ -o outfile ] [ --output-
       file=outfile ] [ -p prefix ] [ --name-prefix=prefix ] [ -r
       ] [ --raw ] [ -t ] [ --debug ] [ -v ] [ --verbose ] [ -V ]
       [ --version ] [ -y ] [ --yacc ]	[  -h  ]  [  --help  ]	[
       --fixed-output-files ] file

## DESCRIPTION
       Bison  is  a parser generator in the style of yacc(1).  It
       should be upwardly compatible with  input  files	 designed
       for yacc.

       Input files should follow the yacc convention of ending in
       .y.  Unlike yacc, the generated files do	 not  have  fixed
       names,  but instead use the prefix of the input file.  For
       instance, a grammar description file named  parse.y  would
       produce	the generated parser in a file named parse.tab.c,
       instead of yacc's y.tab.c.

       This description of the options that can be given to bison
       is  adapted  from the node Invocation in the bison.texinfo
       manual, which should be taken as authoritative.

       Bison supports both traditional single-letter options  and
       mnemonic	 long  option names.  Long option names are indi-
       cated with -- instead  of  -.   Abbreviations  for  option
       names are allowed as long as they are unique.  When a long
       option takes an argument, like --file-prefix, connect  the
       option name and the argument with =.

    OPTIONS
       -b file-prefix
       --file-prefix=file-prefix
	      Specify  a  prefix to use for all bison output file
	      names.  The names are chosen as if the  input  file
	      were named file-prefix.c.

       -d
       --defines
	      Write an extra output file containing macro defini-
	      tions for the token type names defined in the gram-
	      mar and the semantic value type YYSTYPE, as well as
	      a few extern variable declarations.

	      If the parser output file is named name.c then this
	      file is named name.h.

	      This  output  file  is essential if you wish to put
	      the definition of yylex in a separate source  file,
	      because  yylex  needs  to be able to refer to token
	      type codes and the variable yylval.

       -r
       --raw  The token numbers in the name.h  file  are  usually
	      the  Yacc	 compatible translations.  If this switch
	      is  specified,  Bison  token  numbers  are   output
	      instead.	 (Yacc	numbers	 start	at 257 except for
	      single character tokens;	Bison assigns token  num-
	      bers sequentially for all tokens starting at 3.)

       -k
       --token-table
	      This switch causes the name.tab.c output to include
	      a list of token names in order by their token  num-
	      bers;   this is defined in the array yytname.  Also
	      generated are #defines for YYNTOKENS, YYNNTS,  YYN-
	      RULES, and YYNSTATES.

       -l
       --no-lines
	      Don't  put  any  #line preprocessor commands in the
	      parser file.  Ordinarily bison  puts  them  in  the
	      parser  file  so	that the C compiler and debuggers
	      will associate errors with your  source  file,  the
	      grammar file.  This option causes them to associate
	      errors with the parser file, treating it	an  inde-
	      pendent source file in its own right.

       -n
       --no-parser
	      Do  not  generate	 the parser code into the output;
	      generate	 only	declarations.	 The	generated
	      name.tab.c  file	will  have only constant declara-
	      tions.  In addition, a name.act file  is	generated
	      containing  a  switch statement body containing all
	      the translated actions.

       -o outfile
       --output-file=outfile
	      Specify the name outfile for the parser file.

	      The other output files' names are constructed  from
	      outfile  as described under the -v and -d switches.

       -p prefix
       --name-prefix=prefix
	      Rename the external symbols used in the  parser  so
	      that  they  start	 with  prefix instead of yy.  The
	      precise list of symbols renamed is yyparse,  yylex,
	      yyerror, yylval, yychar, and yydebug.

	      For  example,  if	 you  use  -p c, the names become
	      cparse, clex, and so on.

       -t
       --debug
	      Output a definition of the macro YYDEBUG	into  the
	      parser  file,  so that the debugging facilities are
	      compiled.

       -v
       --verbose
	      Write  an	 extra	output	file  containing  verbose
	      descriptions  of the parser states and what is done
	      for each type of look-ahead token in that state.

	      This file also describes all  the	 conflicts,  both
	      those resolved by operator precedence and the unre-
	      solved ones.

	      The file's name is made by removing  .tab.c  or  .c
	      from  the parser output file name, and adding .out-
	      put instead.

	      Therefore, if the input file  is	foo.y,	then  the
	      parser  file  is called foo.tab.c by default.  As a
	      consequence, the	verbose	 output	 file  is  called
	      foo.output.

       -V
       --version
	      Print the version number of bison and exit.

       -h
       --help Print a summary of the options to bison and exit.

       -y
       --yacc
       --fixed-output-files
	      Equivalent to -o y.tab.c; the parser output file is
	      called y.tab.c, and the other  outputs  are  called
	      y.output	and  y.tab.h.  The purpose of this switch
	      is to imitate yacc's output file name  conventions.
	      Thus, the following shell script can substitute for
	      yacc:

	      bison -y $*

       The long-named options can be introduced with `+' as  well
       as  `--', for compatibility with previous releases.  Even-
       tually support for `+' will  be	removed,  because  it  is
       incompatible with the POSIX.2 standard.

## FILES
       /usr/local/lib/bison.simple   simple parser
       /usr/local/lib/bison.hairy    complicated parser

## SEE ALSO
       yacc(1)
       The   Bison   Reference	 Manual,  included  as	the  file
       bison.texinfo in the bison source distribution.

## DIAGNOSTICS
       Self explanatory.
