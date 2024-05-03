


## Counting White Spaces:
- **White spaces** are counted individually.

## Counting Words:
- **Words** are counted based on space-separated tokens.

## Counting Characters:
- **Characters** are counted excluding newline and tab characters.

## Printing Results:
- The total number of **white spaces**, **words**, and **characters** are printed.

## Initialization of Counters:
- Counters for **white spaces**, **words**, and **characters** are initialized at the beginning of the Lex file.






```lex
%{
#include<stdio.h>
int wspaces=0 , words=0 , characters=0;
%}


%%
" " {wspaces++; words++;};
[\t\n] {words++;};
[^\n\t] {characters++;};

%%

int yywrap()
{
    return 1;
}

int main()
{
    yyin = fopen("input.txt","r");
    yylex();
    printf("\nThe total number of white spaces is : %d\nThe total number of words are : %d\n The total number of characters are : %d",wspaces,words,characters);
    return 0;
}
lex```
