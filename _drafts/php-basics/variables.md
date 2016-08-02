---
title: Variables
layout: default
categories: php-basics

breadcrumb_url: php-basics
breadcrumb_name: PHP Basics

next_url: php-basics/operators.html
next_name: Operators

prev_url: php-basics/syntax.html
prev_name: Syntax
---

* [Introdução](#introduo)
* [Sintaxe Válida](#sintaxe-vlida)
* [Tipo de variáveis](#tipo-de-variveis)
* [Passagem de valor](#passagem-de-valor)
* [Conversão de tipos](#converso-de-tipos)
* [Detectando tipos](#detectando-tipos)
* [Variáveis Variáveis](#variveis-variveis)
* [Constantes](#constantes)

***

## Introdução
As variáveis no PHP são representadas por um cifrão ($) seguido pelo nome da variável. Os nomes de variável são case-sensitive (isso significa que as variaveis fazem diferença do maiúsculo do minusculo). O PHP é uma linguagem de tipagem dinâmica. Assim sendo, o valor que o programador atribuir a variável é que vai determinar o tipo de dado que ela irá armazenar.

<script src="https://gist.github.com/alefcastelo/df36ce3a3ff82bd32d9974af4492c51b.js"></script>

***

## Sintaxe Válida
As variáveis no PHP só podem começar com letras e underscore, variáveis que começam com números o PHP lançará um erro informando que a variavel é invalida.

<script src="https://gist.github.com/alefcastelo/63e274a2420e2065fa93a3d50ab9460e.js"></script>

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
Você pode usar duas formas de atribuir um valor a uma variável, a passagem por valor e por referência. A passagem por valor continua da forma a qual já virmos anteriormente, porém a passagem por referencia, precisamos colocar o caractere `&` antes do `$` para informa que aquela variável irá receber uma referência e não a copia do valor.

<script src="https://gist.github.com/alefcastelo/4aa4d283e182836780b6b0139a86392d.js"></script>

***

## Conversão de tipos 
O PHP não obriga (ou suporta) a definição de tipo explícita na declaração de variáveis: o tipo de uma variável é determinado pelo contexto em que a variável é utilizada. Um exemplo da conversão automática do PHP é o operador de adição '+'.

<script src="https://gist.github.com/alefcastelo/ae54ebeb0434076ed49778362f9c132d.js"></script>

A conversão de tipos no PHP funciona como no C: o nome de um tipo desejado é escrito entre parênteses antes da variável que se deseja converter.

<script src="https://gist.github.com/alefcastelo/2eb14e4c10f5109da400b5b96b4291ab.js"></script>

As conversões permitidas são:
* (int), (integer) - molde para inteiro
* (bool), (boolean) - converte para booleano
* (float), (double), (real) - converte para número de ponto flutuante
* (string) - converte para string
* (array) - converte para array
* (object) - converte para objeto
* (unset) - converte para NULL (PHP 5)

Porém existe outras funções que permite fazer a conversão dessas variáveis.

| Função       | Resultado                               |
| ------------ |-----------------------------------------|
| intval()     | Converte para `int`                     |
| floatval()   | Converte para `float`                   |
| strval()     | Converte para `string`                  |
| boolval()    | Converte para `boolean`                 |
| settype()    | Converte a variável para qualquer tipo  |

Exemplo: 

<script src="https://gist.github.com/alefcastelo/ff5ae199a77c4637d624dbabc45c54dd.js"></script>

***

## Detectando tipos
O PHP possui funções que permite detectar o tipo de cada variável. Se a variável possui o tipo especificado a função irá retornar `true`.


| Função       | Resultado                               |
|:------------:|-----------------------------------------|
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

<script src="https://gist.github.com/alefcastelo/e5202ddf82268c546f7261ad07c55765.js"></script>

Porém seu uso fica mais claro, quando se tenta definir o valor de uma propriedade de uma classe de forma dinâmica.

<script src="https://gist.github.com/alefcastelo/bbba65ac9ad55344b8534d61cb575a8a.js"></script>

Outra forma de acessa essas variaveis são:

<script src="https://gist.github.com/alefcastelo/8496d51de74fa29e456eede7fdd168d0.js"></script>

***

## Constantes
Constante, é um identificador para uma variável a qual seu valor não poderá ser alterado depois de sua declaração. Exceto as constantes mágicas, que não são constantes de verdade. As constantes são case-sensitive por padrão. Por convenção, identificadores de constantes são sempre em maiúsculas. Sua declaração é simples, veja:

<script src="https://gist.github.com/alefcastelo/90e67cf4e236e40bfed5aa164db9d853.js"></script>

> Você pode definir as constante em caixa baixa, porém por conversão elas devem ser criadas em caixa alta.

Usando `define('CONSTANTE', 'valor da constante')` dentro de uma classe não funciona, você precisa usar a palavra reservada `const`.

<script src="https://gist.github.com/alefcastelo/219cfa0b910d1d618573b9bc5e4dcbcb.js"></script>

Fora do escopo da classe a palavra reservada `const` também ira criar uma constante.

<script src="https://gist.github.com/alefcastelo/2ab0e9aeae04fe4e76343513c5d89111.js"></script>

O PHP possui oito constantes mágicas, sua característica é que o valor muda de acordo com o contexto que ela é usada. Por exemplo, o valor de **\_\_LINE\_\_** depende da linha em que é utilizada em seu script. Essas constantes especiais são case-insentitive:

<script src="https://gist.github.com/alefcastelo/eb0b17818698e3c1d10a3936c29a2cac.js"></script>

| Constante             | Resultado                               |
|:---------------------:| --------------------------------------- |
| **\_\_LINE\_\_**      | O número da linha corrente do arquivo.             |
| **\_\_FILE\_\_**      | O caminho completo e nome do arquivo com links simbólicos resolvidos. Se utilizado dentro de um include, o nome do arquivo incluído será retornado. |
| **\_\_DIR\_\_**       |  O diretório do arquivo. Se usado dentro de um include, o diretório do arquivo incluído é retornado. É equivalente a dirname(**\_\_FILE\_\_**). O nome do diretório não possui barra no final, a não ser que seja o diretório raiz. |
| **\_\_FUNCTION\_\_**  | O nome da função. |
| **\_\_CLASS\_\_**     | O nome da classe. O nome da classe inclui o namespace em que foi declarado (por exemplo, Foo\Bar). Note que a partir do PHP 5.4, **\_\_CLASS\_\_** também funcionará em traits. Quando utilizada em um método trait, \_\_CLASS\_\_ é o nome da classe que está utilizando a trait. |
| **\_\_TRAIT\_\_**     | O nome do trait. O nome do trait inclui o namespace em que foi declarado (por exemplo, Foo\Bar).   |
| **\_\_METHOD\_\_**    | O nome do método da classe.             |
| **\_\_NAMESPACE\_\_** | O nome do namespace atual.             |
