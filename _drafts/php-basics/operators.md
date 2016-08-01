---
title: Operators
layout: default
categories: php-basics

breadcrumb_url: php-basics
breadcrumb_name: PHP Basics

prev_url: php-basics/variables.html
prev_name: Variables
--- 

* [O que são operadores?](#o-que-são-operadores)
* [Operadores de Atribuição](#operadores-de-atribuição)
* [Operadores Aritméticos](#operadores-aritméticos)
* [Operadores de Comparação](#operadores-de-comparação)
* [Precedência de Operadores](#precedência-de-operadores)
* [Operadores bit a bit - bitwise](#operadores-bit-a-bit-bitwise)
* [Operadores de controle de erro](#operadores-de-controle-de-erro)
* [Operadores de Execução](#operadores-de-execução)
* [Operadores de Incremento/Decremento](#operadores-de-incremento-decremento)
* [Operadores Lógicos](#operadores-lógicos)
* [Operadores de String](#operadores-de-string)
* [Operadores de Arrays](#operadores-de-arrays)
* [Operadores de tipo](#operadores-de-tipo)

### O que são operadores?

Um operador é uma estrutura que recebe um ou mais valores (ou expressões, no jargão de programação) e que devolve outro valor. O conhecimento desses operadores é de fundamental importância para todo programador que deseja possuir certificação. E o PHP possui muito desses operadores, os mais usados são:

* [Operadores de Atribuição](#operadores-de-atribuição)
* [Operadores Aritméticos](#operadores-aritméticos)
* [Operadores de String](#operadores-de-string)
* [Operadores de Comparação](#operadores-de-comparação)
* [Operadores Lógicos](#operadores-lógicos)

### Operadores Aritméticos
Acredito que a própria explicação matemática já é o suficiente. Com base no Wikipedia: "A aritmética é o ramo da matemática que lida com números e com as operações possíveis entre eles".

* **Adição** - Utiliza o sinal de `+` para expressar que a operação de adição/soma será executada.     
Exemplo:  

```php
<?php
$a = 3;
$b = 2;
$c = $a + $b;
print $c; // 5
```

* **Subtração** - Faz uso do sinal de `-` para expressar que a operação de subtração será executada.    
Exemplo:  

```php
<?php
$a = 3;
$b = 2;
$c = $a - $b;
print $c; // 1
```

* **Multiplicação** - Utiliza o sinal de `*` para expressar que a operação de multiplicação será executada.  
Exemplo:  

```php
<?php
$a = 3;
$b = 2;
$c = $a * $b;
print $c; // 6
```

* **Divisão - Frações** - Faz uso do sinal de `/` para expressar que a operação de divisão será executada.  
Exemplo:  

```php
<?php
$a = 3;
$b = 2;
$c = $a / $b;
print $c; // 1.5
```

* Um outro operador muito usado é o de **Módulo** `%`, com esse operador é possível capturar o resto da divisão, diferente do operador de divisão (`/`) que retorna o `quociente da divisão`.   
Exemplo:  

```php
<?php
$a = 3;
$b = 2;
$c = $a % $b;
print $c; // 1
```

* **Negação** - Faz uso do sinal de `-`, porém o seu uso é antes do valor/variável, isso faz com que nesse momento o valor seja o oposto do original, fazendo a troca de positivo para negativo ou de negativo para positivo. 
Exemplo:  

```php
<?php
$a = 3;
$b = 2;
$c = $a + -$b;

/*
Repare que $b possui o sinal (-) entes do sinal ($), isso indica
que a variável inverterá o seu valor fazendo com que o retorno
da soma seja 1, diferente do exemplo do operador de adição.
*/
print $c; // 1
 
/*
Mais uma vez se nergamos o valor de $c, ele de positivo ficará negativo
*/
print -$c; // -1

/*
Mais uma vez se nergamos o valor de $c o seu resultado continuará
negativo. Isso acontece por causa do escopo que está sendo usando
em print, que não permite que o valor original de $c seja alterado,
somente sua saida irá sofrermudanças.
*/
print -$c; // -1

/*
Porém ao fazer isso o valor original será trocado pois o escopo mudou
e agora você está informando que está mudando o valor da variável e
não da saida dela.
*/
$c = -$c;  
print -$c; // 1 

```

* **Exponencial**  - Introduzido no PHP 5.6, faz uso do sinal de `**`.
Exemplo:  

```php
<?php
$a = 3;
$b = 2;
$c = $a ** $b;
print $c; // 9
```
