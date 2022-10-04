---
layout: post
title: Testes dos componentes eletrônicos
cover-img: /assets/img/testes-hardware.jpg
tags: [Entregável 3]
comments: false
---


Nestas ultimas duas semanas realizamos os testes dos componentes um a um para evitar a surpresa de ter que lidar com algum componente
danificado  ou que funcione de maneira diferente da esperada na hora da montagem do protótipo e integração.

### Teste com a célula de carga

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Para a medição da massa dos materiais a serem colocados no almoxarifado, escolheu-se uma
célula de carga com capacidade de realizar
leituras de até 1kg. Após calibrá-la, utilizou-se um objeto com um peso conhecido para averiguar a leitura do componente. O objeto
escolhido foi o iphone 6s, que possui uma massa de 143g. Após colocá-lo acima da célula de carga, pôde-se ver no terminal serial do Visual
Studio Code que de fato a massa do celular aproximou-se do esperado.

<iframe class="center" width="560" height="315" src="https://www.youtube.com/embed/Ajj7YRJuhP4" title="YouTube video player" 
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

### Teste com o display LCD

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;O display LCD é um importante componente na interação do almoxarifado com o usuário.
Realizou-se o teste com um display LCD 16X2, fazendo-o mostra uma mensagem. Para facilitar a programação e a conexão do
microcontrolador com o LCD, utilizou-se o protocolo I2C. Dessa maneira, estabelece-se uma comunicação serial entre o microcontrolador
e o LCD, economizando a quantidade de pinos utilizados.

<iframe class="center" width="560" height="315" src="https://www.youtube.com/embed/UnSiz0D8JMI" title="YouTube video player"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
allowfullscreen></iframe>

### Teste com o buzzer

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Outro componente que traz mais interação com o usuário é o buzzer. Seu teste foi simples, conectou-se
o terminal negativo do buzzer ao terra do microcontrolador e o terminal positivo a um pino do microcontrolador responsável por emitir os
sinais. Controlando-se a frequência e a duração desses sinais, diferentes notas sonoras são geradas.

<iframe class="center" width="560" height="315" src="https://www.youtube.com/embed/zysUuyP_YAs" title="YouTube video player"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>
                                                                                                                
                                                                                                              
