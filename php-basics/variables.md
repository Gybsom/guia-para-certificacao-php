# Variables

As variáveis no PHP são representadas por um cifrão ($) seguido pelo nome da variável. Os nomes de variável são case-sensitive (isso significa que as variavies do PHP fazem diferença do maiusculo do minusculo). O PHP é uma linguagem de tipagem dinâmica. Assim sendo, o valor que o programador atribuir a variável é que vai determinar o tipo de dado que ela irá armazenar.

```php
$nome = "Alef";
$NOME = 4134;
print $nome; // Alef (string)
print $NOME; // 4134 (int)
```
***
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
> $this é uma variável especial que não pode ser atribuída.

***
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
* Array | Object
* Void

Veja mais em http://php.net/manual/pt_BR/language.types.intro.php
***
## Passagem de valor

O PHP possui duas formas de atribuir um valor a uma variável, a passagem de por valor e por referência. A passagem por valor continua da forma a qual já virmos anteriormente, porém a passagem por referencia, precisamos colocar o caractere `&` antes do `$` para informa que aquela variavel irá receber uma referência e não a copia do valor.

```php
// Passagem por valor
$a = 1;
$b = $a;
$b = 8;
$a = 2;
print $a; // 2
print $b; // 8

// Passagem por Referência
$a = 1;
$b = &$a;
$b = 8;
$a = 2;
print $a; // 2
print $b; // 2

```

## Conversão de tipos 


