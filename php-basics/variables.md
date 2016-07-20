# Variables

As variáveis no PHP são representadas por um cifrão ($) seguido pelo nome da variável. Os nomes de variável são case-sensitive (isso significa que as variavies do PHP fazem diferença do maiusculo do minusculo). 

```php
$nome = "Alef";
$NOME = "Castelo";
print $nome; // Alef
print $NOME; // Castelo
```
## Sintaxe Válida
As variaveis no php só podem começar com letras e underscore, variaveis que começam com numeros o PHP lançará a seguinte erro `PHP Parse error`.
```php
print $1banana; // invalido
print $banana; // valido
print $_banana; // valido
print $_banana; // valido
print $_maçã; // valido
print $maçã; // valido
```
