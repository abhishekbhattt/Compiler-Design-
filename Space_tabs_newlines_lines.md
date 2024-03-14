**This particular lex code will find the number of lines , spaces , newlines and tabs in the string**
```lex
%{
int l=0,s=0,t=0,o=0;
%}

%%
\n l++;
[ ] s++;
\t t++;
. o++;
%%

int main(){
    yylex();
    printf("lines : %d",l);
    printf("space : %d",s);
    printf("tabs : %d",t);
    printf("other character : %d",o);
    return 0;
}

int yywrap()
{
    return 1;
}
