---
author: 
  name: "Henrique Oliveira"
title: Porquê criar um website?
date: 2023-11-19
type: ["posts"]
categories: ["Aleatório"]
tags:
  - porquê
draft: false
---
**Eis algumas razões:**
- Utilizá-lo como portefólio
- Poder partilhar conteúdo
- Aprender novas coisas, tais como
  - Hugo (static website generator)
  - Desenvolver um pouco melhor HTML e CSS
  - Voltar a usar um pouco mais JavaScript
  - Cloudflare (Pages)
- Poder escrever e fazer traduções em diferentes línguas (PT - EN - FR)

## Como é que o site foi criado?
Agora que já sabem mais porque é que eu decidi criar um website, vou vos apresentar como é que o fiz...

### Hugo

Sempre tive interesse em ter um website em meu nome, mas nunca tive grande vontade de estar sempre a criar e modificar constantemente os ficheiros HTML, CSS e algum JS sempre que queria adicionar algo novo...

Por isso, qual é a melhor solução??

[**HUGO**](https://gohugo.io/) - Um gerador de sites estáticos, o que significa que ajuda a criar sites com ficheiros HTML, CSS e JavaScript pré-construídos, em vez de gerar páginas dinamicamente no servidor. Sendo apenas necessário utilizar Markdown para a contrução de cada página web, sendo tudo bastante modular.

Um bom vídeo que recomendo é o do Chris Titus, que refere a sua abordagem com Hugo. (Vídeo em inglês)

{{< youtube id="xMv10E561WQ" >}}

### Hugo - Aparência

Uma grande vantagem da utilização de Hugo é que é possível encontrar dezenas e dezenas de temas de website já com todos os ficheiros pré-construídos, o que é espetacular! [Onde podem encontrar temas...](https://themes.gohugo.io/)

Mas eu gosto de aprender como fazer, por isso peguei num tema que gostei ([hello-friend-ng](https://themes.gohugo.io/themes/hugo-theme-hello-friend-ng/)), e customizei-o à minha maneira...

- Mudei as cores para a minha paleta de cores preferida ([Nord](https://www.nordtheme.com/))
- Criei novos ficheiros HTML, CSS e JS para poder atingir melhor o que pretendia! Tais como:
  - Galeria de fotos que adapta ao tamanho de cada imagem.
  - Texto em colunas (visível na pagina [Sobre Mim](/pt/about/)).
  - Adicionei funcionalidade de renderização de linguagem de matemática.

Se tiverem interesse no meu tema, podem ver os ficheiros no [Github](https://github.com/M0streng0/website)

Mas a íntegra da pagína original foi preservada, pois já se encontrava bastante bem feita!

### Cloudflare Pages

O passo seguinte era saber onde alojar o website... Já tinha experimentado Github Pages, alojar numa VPS da Amazon AWS, mas nunca tinha experimentado Cloudflare Pages.

Deixem-me dizer que para um serviço gratuito é _**INCRÍVEL**_... A abordagem do Cloudflare Pages é semelhante com a experiência que tinha tido com o Github Pages, mas com muito mais funcionalidades!

Mais uma vez, para aprenderem a relação entre Hugo e Cloudflare Pages, recomendo mais uma vez um vídeo do Chris Titus (merece 100% todo o reconhecimento possível!)

{{< youtube id="Cfr4YNbKrB8" >}}