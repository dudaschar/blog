# dudseofusca.com

Esse é o guia de uso do blog Duds e o Fusca, que roda no Jekyll, feito pelo melhor namorado do mundo.

## Escrevendo um post

Cada post é um arquivo na pasta `_posts`. O nome do arquivo deve ser no formato `YYYY-MM-DD-slug.md`. O `slug` é o que vai ficar na URL do post. Exemplo: `2016-11-20-minha-experiencia-no-gashi.md`.

Se não quiser que um post seja publicado, salve o arquivo na pasta `_drafts` enquanto trabalha nele. Ao ficar pronto, mova para a pasta `_posts`.

Cada post deve ter um Front Matter, que é uma lista de atributos no topo do arquivo. Ele começa e termina com uma linha que contém só três hifens `---`. Não pode ter espaços em branco ao fim da linha.

Dentro do Front Matter, cada linha é um atributo. Os atributos obrigatórios são:

```yaml
---
layout: post
title: Minha experência no Gashi
date: 2016-11-20 19:30:00 -0300
image: gashi.jpg
---
```

A imagem deve estar na pasta `assets/images/posts`. A data é no formato `YYYY-MM-DD HH:mm:ss ZZZZZ`, onde `ZZZZZ` é o fuso horário (o de Recife é -0300, ou seja, -3 horas comparado com Greenwhich). Outros atributos possíveis são:

```yaml
category: sushi
tags:
  - rodízio
  - aprovado
excerpt: "<p>Algum texto de teaser para a publicação. Se não colocar, vai ser automaticamente o primeiro parágrafo do post. Se colocar aqui, tem que por a tag de parágrafo HTML.</p>"
```

Depois do Front Matter, pode escrever o texto do post em Markdown. Separa-se parágrafos com uma linha em branco. Para colocar **negrito**, coloca-se o texto `**entre dois asteríscos**`. Para colocar *itálico*, coloca `*entre um asterísco*`.

Para inserir um link, usa-se a sintaxe: `[Texto do link](http://www.site.com)`. Já para inserir uma imagem, a sintaxe é a mesma, mas com uma exclamação na frente: `![Texto alternativo para a imagem](http://www.site.com/imagem.jpg)`. Se a imagem for hospedada no próprio blog, basta colocar o caminho abolsuto dela, como `![Delicia Joy](/assets/images/posts/delicia-joy.png)`.

Para fazer listas, numeradas ou não, usa-se a sintaxe:
```md
- Item de bolinha
- Outro item
- Outro item

1. Item numerado
2. Outro item numerado
4. O numero do item não precisa ser o número verdadeiro dele
1. Poderia ser todos o número "1.". No HTML, vai ficar numerado em sequencia corretamente.
```

## Criando uma página

Para criar uma página, como a Sobre ou a Contato, crie um arquivo na raíz do projeto. Ele pode ser Markdown ou HTML. Na maioria dos casos, Markdown é melhor (até porque você pode colocar HTML no Markdown se precisar).

O arquivo precisa também de um Front Matter, com os seguintes atributos obrigatórios:

```yaml
---
layout: page
title: Parceiros
permalink: /parceiros/
---
```

O permalink é o endereço da página. Ele deve começar e terminar com uma barra. Recomenda-se chamar o arquivo de `parceiros.md`, por questão de consistência.

Opcionalmente pode adicionar um atributo `image`, similar ao dos posts, para aparecer no topo da página. Diferentemente dos posts, numa página ele é **opcional**.

## Editando o visual do blog

A maior parte das modificações vai ser feita nos arquivos da pasta `_includes`:

* `head.html`: conteúdo da tag `<head>`.
* `top.html`: menu superior e logo.
* `sidebar.html`: barra lateral das páginas.
* `bottom.html`: rodapé. Scripts JS que devem ser inseridos no fim da página ficam aqui.

Alterações mais específicas podem ser feitas nos arquivos da pasta `_layouts`. Mexa com cuidado.

Para fazer alterações no visual, sugiro baixar a versão mais recente do site, fazer as mudanças e testar localmente (`bundle exec jekyll serve`), e só depois enviar pro GitHub. Mais sobre isso abaixo.

## Trabalhando com Git

Para baixar o projeto pela primeira vez no computador, abra um terminal, navegue (`cd`) para a pasta onde quer baixar, e execute

```bash
git clone https://github.com/eduardascharnhorst/dudseofusca.com.git
cd dudseofusca.com
```

Para atualizar a versão local (ou seja, baixar do GitHub as mudanças que você ainda não tem no computador):

```bash
git pull origin master
```

Após modificar arquivos, para enviar de volta para o GitHub suas mudanças:

```bash
git add .
git commit -m "o que mudou"
git push origin master
```

(Note o ponto no primeiro comando!)
