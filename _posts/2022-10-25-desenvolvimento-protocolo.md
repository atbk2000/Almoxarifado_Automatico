---
layout: post
title: Implementação do protocolo entre modulos
tags: [Entregável 4]
comments: false
---


Nessa semana trabalhamos na implementação do protocolo de aplicação entre o controlador e o módulo. Parte essencial do nosso projeto que nos permite tanto
obter dados da saida do modulo quanto controlar atuadores conectados aos modulos através do controlador.

Esse protocolo foi pensando para uma interface half-duplex, como nosso projeto é pensando para ter um controlador conectado a multiplos modulos no mesmo
barramento, foi nescessario elaborar o protocolo de modo que dois dispositivos nunca usem o barramento simultanemanete. Nossa solução para este problema foi
a implementação de um protocolo aonde o controlador sempre inicia, toda a comunicação, e os módulos apenas respodem as mensagens endereçadas a ele.
Atualmente o protoco é formados pelos campos:

| Nome | Tipo | Descrição |
| :------ |:--- | :--- |
| moduleID | uint8 | ID unico do modulo a receber essa mensagem |
| dataSize | uint32| Quantidade de dados na mensagem(em bytes)|
| commandID| uint8 | ID do comando a ser executado pelo modulo |
| data | uint8[]   |Data especifica do comando, com o tamanho total de dataSize bytes|
| crc8 | uint8[]   | CRC utilizado para verficiar a integradidade da mensagem|
