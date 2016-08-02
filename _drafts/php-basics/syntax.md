---
title: Syntax
layout: default
categories: php-basics

breadcrumb_url: php-basics
breadcrumb_name: PHP Basics

next_url: php-basics/variables.html
next_name: Variables


prev_url: php-basics/index.html
prev_name: PHP Basics

---

* [PHP](#php)
* [Tags](#tags)
* [Problema com as Tags](#problema-com-as-tags)
* [Aspas](#aspas)
* [Concatenação de Strings](#concatenao-de-strings)
* [Comentários](#comentrios)
* [Bloco de código](#bloco-de-codigo)
* [O interpretador PHP](#o-interpretador-php)

***

### PHP
O PHP (um acrônimo recursivo para PHP: Hypertext Preprocessor) é uma linguagem de script open source de uso geral, muito utilizada, e especialmente adequada para o desenvolvimento web. A melhor coisa em usar o PHP é que ele é extremamente simples para um iniciante, mas oferece muitos recursos para um programador profissional.

***

### Tags
O PHP tem como sintaxe básica, tags de abertura representado por `<?php` e fechamento `?>` como default do interpretador. O interpretador busca por essas tags dentro do arquivo e se achar ele interpreta os comandos dentro das tags e retorna a resposta na saída do documento. Com essa forma de interpretar, o PHP possui a possibilidade de ser facilmente incluído em vários tipos de documento.

Exemplo da mesclagem com HTML:
 
<script src="https://gist.github.com/alefcastelo/cfbe2e7a3b25825dd3e9a3a46e39cf14.js"></script>

A saída desse código é: 

<script src="https://gist.github.com/alefcastelo/d63afe9cf4ce4fd1c3eb23e997b47121.js"></script>

Repare também que foi usado duas formas diferente de exibir uma string na saída do interpretador. A primeira foi `<?php print "Titulo da pagina" ?>` e a segunda foi `<?= "conteúdo do site" ?>`. 
Isso só é possível por que o PHP possui outros tipos de tags a qual o interpretador entende que naquele bloco é um código php.

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

***

### Problema com as Tags

Ao criar arquivos PHP que não se misturam com HTML ou arquivos de template, geralmente em arquivos de classes, configurações e etc, recomenda-se não usar tag de fechamento `?>`. Pois caso exista um espaço ou quebra de linha após a tag de fechamento, essa espaço ou quebra de linha será exibido na resposta da requisição, e é algo bem difícil de se acha quando se tem um projeto com muitos arquivos, e isso pode trazer algumas horas de dor de cabeça.

***

### Aspas

No PHP para exibir um texto qualquer, você pode usar tanto aspas duplas `"` quanto aspas simples `'`, exemplo:

* `<?="PHP BOOK"?>` saida: `PHP BOOK`
* `<?='PHP BOOK'?>` saida: `PHP BOOK`

A diferença acontece quando você tenta mescla esse texto com uma variável, exemplo:

<script src="https://gist.github.com/alefcastelo/4705de72268d3d683946c2b1806598c5.js"></script>

Repare que na primeira exibição, a variável foi reconhecida e seu valor foi impresso na resposta junto com o texto, já na segunda exibição, foi impresso o texto puro e a variável não foi reconhecida. Quando se usa aspas duplas, você consegue mesclar variáveis em strings.

O PHP consegue identificar a variável fazendo com que seu valor seja retornado na exibição, assim evitando está concatenando string com variáveis.   
Outra forma valida e a mais usada é quando se usa chaves envolvendo a variável.

<script src="https://gist.github.com/alefcastelo/decedac228ccebbf7bc4d05da0be9405.js"></script>


> As palavas reservadas `print` e `echo` são as mais usadas para exibir algo na resposta da requisição.

***

### Concatenação de Strings
Para fazer uso da concatenação (ou junção de strings), você precisa usar o ponto `.`, sempre colocando entre duas variáveis ou entre duas strings, entre uma string e o retorno de uma função/método.

<script src="https://gist.github.com/alefcastelo/5a992f8b52f2b35d2915a1e0f195c1a2.js"></script>

***

### Comentários
Assim como em outras linguagens, o PHP possui dois tipo de comentários, de "uma linha" e de "varias linhas". O PHP suporta comentários no estilo 'C', 'C++' e do Unix shell (estilo Perl). Por exemplo:

<script src="https://gist.github.com/alefcastelo/f3efe2f030ce2d7d6ba71eee259351a2.js"></script>

Os comentários de estilo "uma linha" apenas comentam até o final da linha ou do bloco PHP de código corrente

Ao tentar comentar grandes blocos de código, podemos cometer o seguinte equivoco:

<script src="https://gist.github.com/alefcastelo/40d7d75e9757a1a1f974b17973c6d62c.js"></script>

***

### Bloco de codigo

O PHP usa como delimitador de bloco de código as chaves `{}` exemplo:

<script src="https://gist.github.com/alefcastelo/f67996fd770329e3c7d898cd30bbd0bd.js"></script>

***

### O interpretador PHP

Como já foi dito PHP consegue se mistura com outros tipos de arquivos ou documentos e o interpretador consegue detectar comandos PHP dentro desse arquivo, até mesmo não sendo um arquivo com a extensão `.php` veja:

syntax-example-8.xml

<script src="https://gist.github.com/alefcastelo/ad5212bdf1e8ca395ecf95fbc645a010.js"></script>

syntax-example-9.php

<script src="https://gist.github.com/alefcastelo/547e4aec365dd6595181b58fa07745af.js"></script>

Saída:

<script src="https://gist.github.com/alefcastelo/accaabffdb26cac8127098226b239340.js"></script>