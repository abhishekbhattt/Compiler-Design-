

## Analysis of Input Text:
- The Lex file analyzes input text from a file named "input.txt". 📄

## Handling Special Characters:
- **Tabs** and **spaces** are merged into a single space and outputted. ⏹️

## Handling Newlines and Other Characters:
- **Newlines** are outputted directly, while all other characters are printed as they are. ↩️

## Output File:
- The processed text is written to a file named "output.txt". 📝

## Initialization:
- Input and output file streams are initialized at the beginning of the program. 🔄

## Main Function:
- Opens "input.txt" for reading and "output.txt" for writing, performs lexical analysis, and closes the files. 📂




```lex

%{
#include<stdio.h>
%}

%%

[\t" "]+ {fprintf(yyout," ");};
\n|. {fprintf(yyout,"%s",yytext);};
%%

int yywrap()
{
    return 1;
}

int main()
{
    yyin = fopen("input.txt","r");
    yyout = fopen("output.txt" ,"w");
    yylex();
    return 0;
}
lex```
