%{
#include <stdio.h>
%}

%%
[[:alpha:]]+    { printf("Word: %s\n", yytext); }
"=="            { printf("Relational Operator: ==\n"); }
"!="            { printf("Relational Operator: !=\n"); }
"<"             { printf("Relational Operator: <\n"); }
">"             { printf("Relational Operator: >\n"); }
"<="            { printf("Relational Operator: <=\n"); }
">="            { printf("Relational Operator: >=\n"); }
.               { printf("Invalid Character: %s\n", yytext); }

%%

int main() {
    printf("Enter a word or a relational operator:\n");
    yylex();
    return 0;
}
int yywrap()
{
 return 1;
}