# Operators

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

## O que são operadores?

Um operador é uma estrutura que recebe um ou mais valores (ou expressões, no jargão de programação) e que devolve outro valor. O conhecimento desses operadores é de fundamental importância para todo programador que deseja possuir certificação. E o PHP possui muito desses operadores, os mais usados são:
* [Operadores de Atribuição](#operadores-de-atribuição)
* [Operadores Aritméticos](#operadores-aritméticos)
* [Operadores de String](#operadores-de-string)
* [Operadores de Comparação](#operadores-de-comparação)
* [Operadores Lógicos](#operadores-lógicos)

## Operadores Aritméticos
Acredito que a própria explicação matemática já é o suficiente. Com base no Wikipedia: "A aritmética é o ramo da matemática que lida com números e com as operações possíveis entre eles".

* **Adição** - Utiliza do sinal de `+` para expressar que a operação de adição/soma será executada.     
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

* **Multiplicação** - Faz uso do sinal de `*` para expressar que a operação de multiplicação será executada.  
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

* Um outro operador muito usado é o de módulo (`%`), com esse operador é possivel capturar o resto da divisão, diferente do operador de divisão (`/`) que retorna o `quociente da divisão`.   
Exemplo:  
```php
<?php
$a = 3;
$b = 2;
$c = $a % $b;
print $c; // 1
```
