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

<script src="https://gist.github.com/alefcastelo/296ad64f36e7f4ee7fe0d2b5f112fdfb.js"></script>

* **Subtração** - Faz uso do sinal de `-` para expressar que a operação de subtração será executada.    
Exemplo:  

<script src="https://gist.github.com/alefcastelo/c21358006b665e944a0808c147805bc2.js"></script>

* **Multiplicação** - Utiliza o sinal de `*` para expressar que a operação de multiplicação será executada.  
Exemplo:  

<script src="https://gist.github.com/alefcastelo/7479c6a0a895a9b5adb56ecdee4d3265.js"></script>

* **Divisão - Frações** - Faz uso do sinal de `/` para expressar que a operação de divisão será executada.  
Exemplo:  

<script src="https://gist.github.com/alefcastelo/9c7a3e62107bc1cd2b3f97b855fca633.js"></script>

* Um outro operador muito usado é o de **Módulo** `%`, com esse operador é possível capturar o resto da divisão, diferente do operador de divisão (`/`) que retorna o `quociente da divisão`.   
Exemplo:  

<script src="https://gist.github.com/alefcastelo/f334f5e1cf629e7d04b308960813f645.js"></script>

* **Negação** - Faz uso do sinal de `-`, porém o seu uso é antes do valor/variável, isso faz com que nesse momento o valor seja o oposto do original, fazendo a troca de positivo para negativo ou de negativo para positivo. 
Exemplo:  

<script src="https://gist.github.com/alefcastelo/ac962bd9c99b5608881e1c64cd91794f.js"></script>

* **Exponencial**  - Introduzido no PHP 5.6, faz uso do sinal de `**`.
Exemplo:  

<script src="https://gist.github.com/alefcastelo/85345c8ef58367b6254ef57082f1d1ae.js"></script>
