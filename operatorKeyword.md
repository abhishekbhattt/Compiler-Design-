🔍 **Lex Program Description** 🔍

📝 This Lex program analyzes a given input stream to count various tokens, including keywords, identifiers, operators, separators, integer values, and float values.

💡 **Token Types and Counting** 💡

- **Keywords**: Identified by "while", "if", or "else". Each occurrence is counted.
- **Data Types**: Includes "int" or "float". Each occurrence is counted.
- **Identifiers**: Any sequence of letters, digits, or underscores starting with a letter. Each identifier found is counted.
- **Operators**: Recognized operators such as "<=", ">=", "=", "==", "+", "-", "/", and ",". Each occurrence is counted.
- **Separators**: Consisting of "(", ")", and ";". Each separator found is counted.
- **Integer Values**: Sequences of digits, possibly preceded by a minus sign. Each integer value encountered is counted.
- **Float Values**: Digits followed by a dot and more digits, possibly preceded by a minus sign. Each float value is counted.

📊 **Total Tokens Counted** 📊

- The total number of tokens found in the input stream is displayed at the end of the analysis.



📜 **Output** 📜

- The program outputs the counts of various token types along with the total number of tokens found.


```lex
%{
   #include<stdio.h>
   int n=0;

%}

%%
"while"|"if"|"else" { n++; printf("\t N.o of keywords are : %s", yytext);}
"int"|"float" { n++; printf("\t N.o of keywords are : %s", yytext);}
[a-zA-Z_][a-zA-Z0-9_]* {n++; printf("\nN.o of identifier are: %s", yytext);}
"<="|">="|"="|"=="|"+"|"-"|"/"|"," {n++; printf("\n N.o of operators are : %s", yytext); }
"("|")"|";" {n++ ; printf("\nN.o of separators are : %s",yytext);}
-?[0-9]+"."[0-9]+ {n++; printf("\nN.o of float values : %s",yytext);}
-?[0-9]+ {n++; printf("\nNo of Integer values : %s",yytext);}
. ;
%%

int yywrap()
{
    return 1;
}

int main()
{
yylex();
printf("\nTotal number of tokens are : %d\n",n);
return 0;
}


```lex
