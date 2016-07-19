# Syntax

## Tags
O PHP tem como sintaxe básica, tags de abertura representado por `<?php` e fechamento `?>` como default do interpretador. Com essa forma de interpretar o PHP possui a possibilidade de ser facilmente mesclado com HTML e outras tecnologias.

Exemplo: 
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

* `<?php ?>` **Open Tags** - O mais usado usado, geralmente em arquivos que só contem PHP.
* `<? ?>` **Short Open Tags** - Seu uso é desencorajado pois esse recurso só está disponível quando é habilitado a diretiva short_open_tag no php.ini.
* `<?= ?>` **Echo tag** - Usado em arquivo de template, a parti da versão 5.4.0 sempre estará disponível, independente do da configuração short_open_tag ini..
* `<% %>` **ASP Tags** - Seu uso é desencorajado pois na verão 7 ele foi removido, por motivos de causar conflitos com linguagens de marcação, como XML.
* `<script language="php"></script>` **Script Tags** - Também foi removido da versão 7 do  PHP.

## Problema com as Tags
Ao criar arquivos PHP que não se misturam com HTML ou arquivos de template, geralmente em arquivos de classes, configurações, e etc recomenda-se não usar tag de fechamento `?>`. Pois caso exista um espaço ou quebra de linha após a tag de fechamento, essa espaço ou quebra de linha será exibido na resposta da requisição, e é algo bem difícil de se acha quando se tem um projeto com muitos arquivos, e isso pode trazer algumas horas de dor de cabeça.
