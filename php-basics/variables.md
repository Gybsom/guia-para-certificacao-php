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
## Tipo de variáveis

O PHP suporta oito tipos primitivos.

| Escalares                                           | Compostos     | Especiais  |
| --------------------------------------------------- |:-------------:| ----------:|
| boolean                                             | array         | resource   |
| integer                                             | object        | NULL       |
| float (número de ponto flutuante, ou também double) |               |            |
| string                                              |               |            |

Porém existe pseudo-tipos:
* Mixed
* Number
* Callback (ou callable)
* Array|Object
* Void

O PHP possui duas formas de atribuir um valor a uma variável, a passagem de por valor e por referência. A passagem por valor continua da forma a qual já virmos anteriormente, porém a passagem por referencia, precisamos colocar o caractere `&` antes do `$` para informa que aquela variavel irá receber uma referência e não a copia do valor.

```php
```


