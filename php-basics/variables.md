# Variables

* [Introdução](#introdução)
* [Sintaxe Válida](#sintaxe-válida)
* [Tipo de variáveis](#tipo-de-variáveis)
* [Passagem de valor](#passagem-de-valor)
* [Conversão de tipos](#conversão-de-tipos)
* [Detectando tipos](#detectando-tipos)
* [Variáveis Variáveis](#variáveis-variáveis)

***
## Introdução
As variáveis no PHP são representadas por um cifrão ($) seguido pelo nome da variável. Os nomes de variável são case-sensitive (isso significa que as variavies do PHP fazem diferença do maiusculo do minusculo). O PHP é uma linguagem de tipagem dinâmica. Assim sendo, o valor que o programador atribuir a variável é que vai determinar o tipo de dado que ela irá armazenar.

```php
$nome = "Alef";
$NOME = 4134;
print $nome; // Alef (string)
print $NOME; // 4137 (int)
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

`$this` é uma variável especial que não pode ser atribuída. Caso queira atribuir um valor para ela, o PHP lançará o seguinte erro: `PHP Fatal error:  Cannot re-assign $this`;



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
O PHP não obriga (ou suporta) a definição de tipo explícita na declaração de variáveis: o tipo de uma variável é determinado pelo contexto em que a variável é utilizada. Um exemplo da conversão automática do PHP é o operador de adição '+'.

```php
<?php
$var = "0";  // $var é string (ASCII 48)
$var += 2;   // $var é agora um interio (2)
$var = $var + 1.3;  // $var é agora um float (3.3)
$var = 5 + "10 pequenos porcos";   // $var é inteiro (15)
$var = 5 + "10 minúsculos porcos"; // $var é inteiro (15)
```
A conversão de tipos no PHP funciona como no C: o nome de um tipo desejado é escrito entre parênteses antes da variável que se deseja converter.

```php
<?php

print_r( (object) ['esporte' => 'Judô', 'atleta' => 'Alef'] );

/*
  O resultado da conversão retornará um objeto do tipo stdClass
  stdClass Object
  (
    [esporte] => Judô
    [atleta] => Alef
  )
*/
```

As conversões permitidas são:
* (int), (integer) - molde para inteiro
* (bool), (boolean) - converte para booleano
* (float), (double), (real) - converte para número de ponto flutuante
* (string) - converte para string
* (array) - converte para array
* (object) - converte para objeto
* (unset) - converte para NULL (PHP 5)

O PHP possui funções que permite fazer a conversão dessas variavies.

| Função       | Resultado                               |
| ------------ |:---------------------------------------:|
| intval()     | Converte para `int`                     |
| floatval()   | Converte para `float`                   |
| strval()     | Converte para `string                   |
| boolval()    | Converte para `boolean`                 |
| settype()    | Converte a variável para qualquer tipo  |

Exemplo: 
```php 
<?php
$var = 12;

settype($var, "bool");
var_dump($var); // bool(true)

settype($var, "int");
var_dump($var); // int(1)

settype($var, "double");
var_dump($var); // double(1)
```

***
## Detectando tipos
O PHP possui funções que permite detectar o tipo de cada variável. Se a variável possui o tipo especificado a função irá retornar `true`.


| Função       | Resultado                               |
| ------------ |:---------------------------------------:|
| is_int()     | Verifica se é do tipo `int`             |
| is_float()   | Verifica se é do tipo `float`           |
| is_string()  | Verifica se é do tipo `string`          |
| is_bool()    | Verifica se é do tipo `boolean`         |
| is_null()    | Verifica se é do tipo `null`            |
| is_array()   | Verifica se é do tipo `null`            |
| is_object()  | Verifica se é do tipo `null`            |

***
##  Variáveis Variáveis

As vezes, é conveniente possuir variáveis com nomes variáveis. Isto é, o nome de uma variável que pode ser definido e utilizado dinamicamente. 

