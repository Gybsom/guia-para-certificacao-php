# Variables

* [Introdução](#introdução)
* [Sintaxe Válida](#sintaxe-válida)
* [Tipo de variáveis](#tipo-de-variáveis)
* [Passagem de valor](#passagem-de-valor)
* [Conversão de tipos](#conversão-de-tipos)
* [Detectando tipos](#detectando-tipos)
* [Variáveis Variáveis](#variáveis-variáveis)
* [Constantes](#constantes)

***
## Introdução
As variáveis no PHP são representadas por um cifrão ($) seguido pelo nome da variável. Os nomes de variável são case-sensitive (isso significa que as variaveis do PHP fazem diferença do maiúsculo do minusculo). O PHP é uma linguagem de tipagem dinâmica. Assim sendo, o valor que o programador atribuir a variável é que vai determinar o tipo de dado que ela irá armazenar.

```php
$nome = "Alef";
$NOME = 4134;
print $nome; // Alef (string)
print $NOME; // 4137 (int)
```
***
## Sintaxe Válida
As variáveis no PHP só podem começar com letras e underscore, variáveis que começam com números o PHP lançará a seguinte erro `PHP Parse error`.
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

O PHP possui duas formas de atribuir um valor a uma variável, a passagem de por valor e por referência. A passagem por valor continua da forma a qual já virmos anteriormente, porém a passagem por referencia, precisamos colocar o caractere `&` antes do `$` para informa que aquela variável irá receber uma referência e não a copia do valor.

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

O PHP possui funções que permite fazer a conversão dessas variáveis.

| Função       | Resultado                               |
| ------------ |-----------------------------------------|
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

```php
<?php

$nome = 'Alef';
$$nome = 'Castelo';
$nomecompleto = "$nome ${$nome}";

print $nomecompleto; // Alef Castelo
```
Porém seu uso fica mais claro quando se tenta definir o valor de uma propriedade de uma classe de forma dinâmica.

```php
<?php 

// Suponha que Você recebeu uma requisição GET com a URI: index.php?var=nome&valor=alef

<?php

class Usuario {
    public $nome;
    public $sobrenome;
}

$usuario = new Usuario; 

if(isSet($_GET['var'])) 
   $var = $_GET['var'];
    
$usuario->$var = $_GET['valor'];

/*
    isso => $usuario->$var = $_GET['valor'];
    é a mesma coisa disso => $usuario->nome = $_GET['valor']; 
*/

var_dump($usuario);

/*
  A Saida será:
  object(Usuario)[1]
    public 'nome' => string 'alef' (length=4)
    public 'sobrenome' => null
  
*/

```
Outra forma:

```php
<?php
$var = 'nome';
$$var = 'Alef Castelo';
echo ${'nome'}; // Alef Castelo 
```

***
## Constantes

Constante é um identificador para uma variável a qual seu valor não poderá ser alterado depois de sua declaração. Exceto as constantes mágicas, que não são constantes de verdade. As constantes são case-sensitive por padrão. Por convenção, identificadores de constantes são sempre em maiúsculas. Sua declaração é simples, veja:

```php
<?php
define("URL", "http://google.com");
define("VERSAO", "v1");

print URL;    // http://google.com
print VERSAO; // v1

define("CONSTANTE", "Constante");
print CONSTANTE;                // Constante
print constant("CONSTANTE");    // mesma coisa que a linha anterior

```
> Você pode definir as constante em caixa baixa, porém por conversão elas devem ser criadas em caixa alta.

Usando `define('CONSTANTE', 'valor da constante')` dentro de uma classe não funciona, você precisa usar a palavra reservada `const`.

```php
<?php

interface Projeto {
    const NOME = 'Projeto';
}

class Livro {
    const NOME = 'Livro';
}

$const = 'NOME';

var_dump(constant('Projeto::'. $const)); // string(7) "Projeto"
var_dump(Projeto::NOME); // string(7) "Projeto"
var_dump(constant('Livro::'. $const)); // string(5) "Livro"
var_dump(Livro::NOME); // string(5) "Livro"

```
Fora do escopo da classe a palavra reservada `const` também ira criar uma constante.

```php
<?php
const NOME = __LINE__;
print NOME; // 2
```

O PHP possui oito constantes mágicas, sua característica é que o valor muda de acordo com o contexto que ela é usada. Por exemplo, o valor de **\_\_LINE\_\_** depende da linha em que é utilizada em seu script. Essas constantes especiais são case-insentitive:

```php
<?php

interface IConstante {
    const NOME = __CLASS__;
}

class ZCEBook {
    const NOME = __CLASS__;
}

$const = 'NOME';

var_dump(constant('IConstante::'. $const)); // string(10) "IConstante"
var_dump(IConstante::NOME); // string(10) "IConstante"
var_dump(constant('ZCEBook::'. $const)); // string(7) "ZCEBook"
var_dump(ZCEBook::NOME); // string(7) "ZCEBook"

```
| Constante       | Resultado                               |
|:------------:| --------------------------------------- |
| **\_\_LINE\_\_**     | O número da linha corrente do arquivo.             |
| **\_\_FILE\_\_**     | O caminho completo e nome do arquivo com links simbólicos resolvidos. Se utilizado dentro de um include, o nome do arquivo incluído será retornado. |
| **\_\_DIR\_\_**     |  O diretório do arquivo. Se usado dentro de um include, o diretório do arquivo incluído é retornado. É equivalente a dirname(**\_\_FILE\_\_**). O nome do diretório não possui barra no final, a não ser que seja o diretório raiz. |
| **\_\_FUNCTION\_\_**     | O nome da função. |
| **\_\_CLASS\_\_**     | O nome da classe. O nome da classe inclui o namespace em que foi declarado (por exemplo, Foo\Bar). Note que a partir do PHP 5.4, **\_\_CLASS\_\_** também funcionará em traits. Quando utilizada em um método trait, \_\_CLASS\_\_ é o nome da classe que está utilizando a trait. |
| **\_\_TRAIT\_\_**     | O nome do trait. O nome do trait inclui o namespace em que foi declarado (por exemplo, Foo\Bar).   |
| **\_\_METHOD\_\_**     | O nome do método da classe.             |
| **\_\_NAMESPACE\_\_**     | O nome do namespace corrente.             |
