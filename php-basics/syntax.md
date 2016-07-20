# Syntax
* [Tags](#tags)
* [Problema com as Tags](#problema-com-as-tags)
* [Aspas](#aspas)
* [Comentários](#comentarios)
* [Bloco de código](#bloco-de-codigo)
* [O interpretador PHP](#o-interpretador-php)


## Tags
O PHP tem como sintaxe básica, tags de abertura representado por `<?php` e fechamento `?>` como default do interpretador. O interpretador busca por essas tags dentro do arquivo e se achar ele interpreta esses comandos e retorna a resposta na saida do documento. Com essa forma de interpretar, o PHP possui a possibilidade de ser facilmente incluído em vários tipos de documento.

Exemplo da mesclagem com HTML: 
```HTML
<!DOCTYPE html>
<html>
  <head>
    <title><?php print "Titulo da pagina" ?></title>
  </head>
  <body>
    <?= "conteúdo do site" ?>
  </body>
</html>
```
A saída desse código é: 

```HTML
<!DOCTYPE html>
<html>
  <head>
    <title>Titulo da pagina</title>
  </head>
  <body>
    conteúdo do site
  </body>
</html>
```
Repare também que foi usado duas formas diferente de exibir uma string na saída do interpretador. A primeira foi `<?php print "Titulo da pagina" ?>` e a segunda foi `<?= "conteúdo do site" ?>`. 
Isso só é possível por que o PHP outros tipos de tags a qual o interpretador entende que naquele bloco é um código php.

**Standard Tags or Open Tags**  
`<?php ?>`  
O mais usado usado, e com certeza a melhor solução, por causa da compatibilidade com versões anteriores, e é garantido que não poderão ser desabilitado alterando o arquivo de configuração do php.
  
**Short Open Tags**   
`<? ?>`   
Seu uso é desencorajado pois esse recurso só está disponível quando é habilitado a diretiva `short_open_tag` no _php.ini_.

**Echo tag**    
`<?= ?>`    
Comummente usado em arquivo de template. A parti da versão 5.4.0 sempre estará disponível, independente do da configuração `short_open_tag` no _php.ini_.

**ASP Tags**    
`<% %>`    
É considerado obsoleto, e seu uso é desencorajado pois na verão 7 ele foi removido, por motivos de causar conflitos com linguagens de marcação como XML.
  
**Script Tags**   
`<script language="php"></script>`    
Também foi removido da versão 7 do  PHP.

## Problema com as Tags
Ao criar arquivos PHP que não se misturam com HTML ou arquivos de template, geralmente em arquivos de classes, configurações e etc, recomenda-se não usar tag de fechamento `?>`. Pois caso exista um espaço ou quebra de linha após a tag de fechamento, essa espaço ou quebra de linha será exibido na resposta da requisição, e é algo bem difícil de se acha quando se tem um projeto com muitos arquivos, e isso pode trazer algumas horas de dor de cabeça.

## Aspas
No PHP para exibir um texto qualquer, você pode usar tanto aspas duplas `"` quanto aspas simples `'`, exemplo:
* `<?="PHP BOOK"?>` saida: `PHP BOOK`
* `<?='PHP BOOK'?>` saida: `PHP BOOK`

A diferença acontece quando você tenta mescla esse texto com uma variável, exemplo:
```php
<?php 

$variael = "texto qualquer";

print "variável: $variavel"; // variável: texto qualquer
print 'variável: $variavel'; // variável: $variavel
```

Repare que na primeira exibição, a variável foi reconhecida e seu valor foi impresso na resposta junto com o texto, já na segunda exibição, foi impresso o texto puro e a variável não foi reconhecida. Quando se usa aspas duplas, você consegue mesclar variáveis em strings.

O PHP consegue identificar a variável fazendo com que seu valor seja retornado na exibição, assim evitando está concatenando string com variáveis. 

Outra forma valida e a mais usada é quando se usa chaves envolvendo a variável

```php
<?php 

$variavel = "texto qualquer";

print "variável: {$variavel}"; // variável: texto qualquer
print 'variável: {$variavel}'; // variável: {$variavel}
```

> As palavas reservadas `print` e `echo` são as mais usadas para exibir algo na resposta da requisição.

## Comentarios
Assim como em outras linguagens, o PHP possui dois tipo de comentários, de "uma linha" e de "varias linhas". O PHP suporta comentários no estilo 'C', 'C++' e do Unix shell (estilo Perl). Por exemplo:
```php
<?php
    echo 'Isto é um teste'; // Estilo de comentário de uma linha em  c++
    /* Este é um comentário de múltiplas linhas
       ainda outra linha de comentário */
    echo 'Isto é ainda outro teste';
    echo 'Um teste final'; # Este é um comentário de uma linha no estilo shell
?>
```
Os comentários de estilo "uma linha" apenas comentam até o final da linha ou do bloco PHP de código corrente

Ao tentar comentar grandes blocos de codigo, podemos cometer o seguinte equivoco:
```php
<?php
 /*
    echo 'Isto é um teste'; /* Este comentário irá causar um problema */
 */
?>
```

## Bloco de codigo
O PHP usa como delimitador de bloco de codigo as chaves `{}` exemplo:
```php
<?php

interface ZCE {
  # bloco de código  
}

class Programador implements ZCE {
    # bloco de código
}

$programador = new Programador();

if($programador instanceof ZCE){
    print true; # bloco de código
} else {
    print false; # bloco de código
}

```

## O interpretador PHP
Como já foi dito php consegue se mistura com outros tipos de documentos e o interpretador consegue detectar comandos PHP dentro de um documento.


Próximo assunto: [Variables](variables.md)
