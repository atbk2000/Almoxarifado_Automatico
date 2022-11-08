---
layout: post
title: Desenvolvimento do site
cover-img: /assets/img/Javascript_Image.jpg
tags: [Entregável 4]
comments: false
---

Um dos objetivos do projeto é a construção do site que mostra os dados e manda solicitações ao almoxarifado. Na semana anterior, a equipe conseguiu 
mostrar no site uma tabela com os dados vindos de um sensor de temperatura, que mostrava a temperatura local vindo de um sensor LM35. No entanto, esse
era apenas um teste, posteriormente a equipe entrou em acordo sobre o que o site deveria apresentar. Foram esquematizadas diversas telas que serão
apresentadas no site, onde o usuário poderia obter informações e enviar comandos para o almoxarifado (caso seja um administrador, por exemplo).

### Tela geral do usuário

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Como o grupo tinha pouco conhecimento em JavaScript e HTML, além do desenvolvimento do site é necessário um tempo
considerável para o estudo dessas duas linguagens de programação. Com isso, buscou-se desenvolver a tela geral do usuário, onde uma tabela lista as
gavetas mostrando as suas propriedades: ID da gaveta, objeto que a gaveta armazena, quantidade de objetos dentro da gaveta, e o limite de objetos
que podem ser depositados na gaveta. A Figura 1 mostra o desenvolvimento da tabela até o momento da escrita desse post. 

<p style="margin-bottom: 0px;">
<a href="../assets/img/Site_ESP32_Temp.png"><img class="mx-auto d-block" src="../assets/img/Site_ESP32_Temp.png" style="width:85%;height:85%;"></a>
  <figcaption class="figure-caption text-center">Figura 1. Tela geral do usuário</figcaption>
</p>

## Próximos passos

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; O objetivo é personalizar a tela geral do usuário para possuir uma melhor aparência bem como construir as demais
telas. A equipe teve um pouco de dificuldade para utilizar os métodos GET e POST juntamente com o JavaScript, por isso consegui-se apenas a construção
da tela geral. A expectativa é que a geração das outras telas seja mais rápida. Outro detalhe importante é a construção da estrutura física do almoxarifado,
que deverá ser feita simultaneamente ao desenvolvimento do site nas próximas semanas.


