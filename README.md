# Lox

The repository contains various implementations of interpreter for the Lox programming language in various host languages.

Lox is a dynamically typed object oriented language.

## Grammer
```
program         →   statement* EOF;
declaration     →   valDecl | statement;
valDecl         →   "var" IDENTIFIER ( "=" expression)? ";" ;
statement       →   exprStmt | printStmt;
exprStmt        →   expression ";";
printStmt       →   "print" expression ";"; 
expression      →   comma;
comma           →   assignment ("," assignment)*;
assignment      →   IDENTIFIER "=" assignment | ternary;
ternary         →   equality "?" expression ":" equality | equality;
equality        →   comparison ( ( "!=" | "==" ) comparison )* ;
comparison      →   term ( ( ">" | ">=" | "<" | "<=" ) term )* ;
term            →   factor ( ( "-" | "+" ) factor )* ;
factor          →   unary ( ( "/" | "*" ) unary )* ;
unary           →   ( "!" | "-" ) unary | primary ;
primary         →   NUMBER | STRING | "true" | "false" | "nil" | 
                    "(" expression ")" | IDENTIFIER |
                    <!-- Error Productions -->
                    ( "!=" | "==" ) comparison |
                    ( ">" | ">=" | "<" | "<=" ) term |
                    ( "+" ) factor |
                    ( "/" | "*" ) unary;
```