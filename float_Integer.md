**This Lex program identifies integer and floating-point values in an input stream and prints corresponding messages**

🔢 Integer value: When it encounters a sequence of digits representing an integer.

🌟 Float value: When it encounters a sequence of digits followed by a dot and more digits representing a floating-point number.
```lex
%{
#include<stdio.h>
%}

%%
[0-9]*"."+[0-9]+ {printf("Float value");
}
[0-9]+ {printf("integer value");
}
. ;
%%
int yywrap()
{
 return 1;
}
int main()
{
    yylex();
    return 0;
}
```lex

