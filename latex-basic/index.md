---
layout: lesson
root: ..
title: Introdução ao LaTeX
---
Essa aula tem duração prevista de uma hora cobrindo seis "módulos" com duração
prevista de 10 minutos que incluem:

- explicação sobre o que deve ser feito,
- experimentação por parte dos alunos,
- apresentação da solução com comentários adicionais.

## Módulo 1: Cabeçalho

Utilizando o arquivo `modulo1.tex`
([download aqui](modulo1.tex)
ou [writeLaTeX](https://www.writelatex.com/assignments/159nggpxygd)):

- Remova `%` existentes.
- Compile seu primeiro documento utilizando

  ~~~
  $ latexmk -pdf modulo1.tex
  ~~~

  ou

  ~~~
  $ pdflatex modulo1.tex
  ~~~

  ou o botão existente na sua IDE.
- Visualize seu primeiro documento utilizando um leitor de PDF.

  **Nota**: alguns leitores de PDF, e.g. Adobe Reader, impedem que ele seja
  alterado por outro programa e por esse motivo você terá que fechá-lo antes de
  compilar seu documento novamente.
- Adicione um novo parágrafo. **Parágrafos são separados por uma linha vazia.**
  Depois disso compile e visualize seu documento.
- Adicione palavras contendo `á`, `é`, `ã`, `ç` no seu documento. Compile e
  visualize seu documento.
- Adicione `%` no seu documento. Compile e visualize seu documento.

## Módulo 2: Pacotes

Utilizando o arquivo `modulo2.tex`
([download aqui](modulo2.tex)
ou [writeLaTeX](https://www.writelatex.com/assignments/155kszxdxnp)):

- Compile e visualize o documento.

  Você deve notar que `é`, `á` e `ó` não aparecem. O motivo disso é que o TeX
  foi escrito em 1978 naquela época não existia uma representação computacional
  para tais caracteres.
- Adicione o pacote `inputenc`:

  ~~~
  \usepackage[utf8]{inputenc}
  ~~~

  Compile e visualize o documento.

  Você deve notar que agora `é`, `á` e `ó` aparecem. Tente adicionar `ã` e `ç`
  para ver que eles também aparecem.
- A data do nosso documento está em inglês e queremos ela em português. Para
  fazer essa mudança precisamos do pacote `babel` que, assim como o pacote
  `inputenc`, requer uma opção. Descubra a opção necessária dando uma olhada na
  documentação do pacote `babel` utilizando

  ~~~
  $ texdoc babel
  ~~~

  ou procurando por `LaTeX babel` no seu buscador favorito.
- As margens da página estão grandes. Para alterá-las você precisa do pacote
  `geometry` e informar algumas opções (`utf8` é uma opção para o pacote
  `inputenc`). Descubra as opções necessárias dando uma olhada na documentação
  do pacote `geometry` utilizando

  ~~~
  $ texdoc geometry
  ~~~

  ou procurando por `LaTeX geometry` no seu buscador favorito.

### Extra

Valiosas informações encontram-se disponíveis em "Standard Document Classes for
LaTeX version 2e" acessível por

~~~
$ texdoc article
~~~

ou procurando pelo título do documento no seu buscador favorito. Procure nesse
documento como fazer para

- Alterar o tamanho da fonte padrão.
- Imprimir uma data fixa.
- Não incluir o número da página. **Dica**: procure por `thispagestyle`.

## Módulo 3: Títulos e Arquivos

Utilizando o arquivo `modulo3.tex`
([download aqui](modulo3.tex)
ou [writeLaTeX](https://www.writelatex.com/assignments/158bvwxrfzp)):

- Crie um arquivo chamado `modulo31.tex` cuja primeira linha é

  ~~~
  \section{\LaTeX}
  ~~~

  Depois recorte

  ~~~
  \LaTeX \ é um conjunto de macros para \TeX, um poderoso sistema tipográfico
  de código livre.
  ~~~

  do arquivo `modulo3.tex` e cole no final do arquivo `modulo31.tex`.

  No lugar do texto recortado, adicione

  ~~~
  \include{modulo31.tex}
  ~~~

  Compile e visualize seu documento.
- No documento `modulo3.tex`, antes de

  ~~~
  \end{document}
  ~~~

  adicione

  ~~~
  \input{modulo32.tex}
  ~~~

  Crie o arquivo `modulo32.tex` e escreva nele pelo menos uma seção e uma
  subseção.

  Compile e visualize seu documento.

- Note que o primeiro parágrafo não encontra-se indentado. Para corrigir isso
  adicione o pacote `indentfirst`:

  ~~~
  \usepackage{indentfirst}
  ~~~

## Módulo 4: Equações

Utilizando o arquivo `modulo4.tex`
([download aqui](modulo4.tex)
ou [writeLaTeX](https://www.writelatex.com/assignments/157tvrvtktr)):

- Adicione a equação de segundo grau na sua forma canônica como o exemplo de uma
  equação inline.

  Compile e visualize seu documento.
- Adicione as raízes da equação de segundo grau como o exemplo de uma equação
  display.

  Compile e visualize seu documento.
- Adicione novamente as raízes da equação de segundo grau mas agora atribuindo
  um número para ela. **Dica**: Utilize o ambiente `equation`.

  Compile e visualize seu documento.
- Complete a frase

  ~~~
  A equação \ldots é conhecida por \ldots
  ~~~

  Compile e visualize seu documento.

  **Dica**: Substitua o primeiro `\ldots` por `\ref{}`.

  **Dica**: Para compilar utilize

  ~~~
  $ latexmk -pdf modulo4.tex
  ~~~

  ou

  ~~~
  $ pdflatex modulo4.tex
  $ pdflatex modulo4.tex
  $ pdflatex modulo4.tex
  ~~~

  ou o botão existente na sua IDE.

### Extra

Existem alguns pacotes criados pela American Mathematical Society (AMS):

- amsmath
- amsthm
- amsfonts
- amssymb

Recomenda-se dar uma olhada na documentação, **principalmente** dos dois
primeiros pacotes.

Para localizar símbolos recomenda-se dar uma olhada em "The Comprehensive LaTeX
Symbol List" de Scott Pakin acessível utilizando

~~~
$ texdoc symbols
~~~

ou procurando pelo título do documento no seu buscador favorito.

## Módulo 5: Tabela

Utilizando o arquivo `modulo5.tex`
([download aqui](modulo5.tex)
ou [writeLaTeX]()):

- Construa a tabela representada no arquivo.

  **Dica**: Utilize o ambiente `tabular`.
- Adicione um título para a tabela.

  **Dica**: Utilize o ambiente `table` e o comando `caption`.
- Centralize a tabela.

**Dica**: Vários exemplos encontram-se disponíveis em
[http://en.wikibooks.org/wiki/LaTeX/Tables#Basic_examples](http://en.wikibooks.org/wiki/LaTeX/Tables#Basic_examples).

## Módulo 6: Figuras

- Adicione o cabeçalho em um arquivo chamado `modulo6.tex`.
- Adicione o pacote `graphicx`.  Esse pacote é necessário para incluir imagens.
- Adicione a figura abaixo.

  <img src="chick.png" alt="Figura a ser inserida no documento LaTeX">
- Adicione uma legenda para a figura.
- Centralize a figura.

**Dica**: Vários exemplos encontram-se disponíveis em
[http://en.wikibooks.org/wiki/LaTeX/Importing_Graphics#Including_graphics](http://en.wikibooks.org/wiki/LaTeX/Importing_Graphics#Including_graphics).
