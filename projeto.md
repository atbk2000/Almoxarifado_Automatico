---
layout: page
title: Projeto
---

### O problema

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; O gerenciamento de estoques é um problema comum a muitos setores da sociedade. Seja na indústria onde é necessário ter um controle de ferramentas e insumos utilizados. No comércio onde existe a necessidade de manter os estoques dos produtos a serem vendidos, até escritórios onde existe a necessidade de manter estoques de materiais de escritório utilizados no dia a dia, como papel, canetas, grampos e etc. Normalmente esse gerenciamento é feito por funcionários, que além de consumir tempo também sofre com o problema de erros humanos, que acabam tornando esses sistemas pouco confiáveis.


### Proposta do projeto

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A proposta deste projeto é através do uso de sistemas eletrônicos, propor uma solução para este problema de um almoxarifado completamente automatizado. Capaz de manter a quantidade de produtos sempre atualizados e mantendo um histórico completo do que, quanto e por quem foi retirado. De modo que esse sistema possa ser integrado a outros sistemas através de uma API web. 
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; O sistema modular é composto por  um controlador e múltiplos módulos. O controlador  é responsável pela parte de controle de autenticação dos usuários, controle dos estoques e de servir essas informações seja via um servidor web local via Access Point ou conectado a uma rede local fornecendo essas informações via uma API. Já os módulos são responsáveis pela interação com os sensores e atuadores responsáveis pela medição da quantidade de produto nos compartimentos.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Um exemplo de aplicação deste sistema seria em um depósito com 5 estantes. Onde existe um controlador e 5 módulos. O controlador é responsável por processar a data vinda de cada um dos módulos e a cada estante contém um módulo, que interage com os sensores colocados em cada prateleira.
Como prova de conceito, este projeto consiste na criação de um mini gaveteiro com um controlador e um módulo, com capacidade de armazenar pequenos itens, cada um com seu devido compartimento.  Esta prova de conceito irá demonstrar todas as capacidades do sistema como o gerenciamento dos usuários e manter um histórico atualizado de todas as interações de retirada e depósito de produtos. 


### Requisitos funcionais

- RF01: O sistema deve permitir que sejam cadastrados os ítens que cada compartimento deve conter.
- RF02: O sistema deve manter um registro de forma precisa e automática da quantidade de itens em estoque a todo momento.
- RF03: O sistema deve manter um histórico de tudo que foi removido ou adicionado por cada usuário.
- RF04: O sistema deve permitir a configuração de cada compartimento como um compartimento de retirada ou um compartimento de empréstimo.
- RF05: O sistema deve permitir o cadastro de usuários com credenciais de autenticação.
- RF06: O sistema deve permitir a configuração de alarmes, de modo a alertar o usuário ou o dono do sistema sobre eventos como fim do estoque ou atraso na devolução de um item.
- RF07: O sistema deve ser capaz de se conectar a uma rede, ser configurado e ter seus dados acessíveis via uma API web.
- RF08: O sistema deve ser flexível de modo a suportar módulos com diferentes sensores.


### Requisitos não funcionais

- RNF01: O código do sistema será desenvolvido em C/C++.
- RNF02: O sistema utilizará no seu módulo de controle um microcontrolador ESP32.
- RNF03: O sistema utilizará microcontroladores STM32F411 nos seus módulos.
- RNF04: O sistema será alimentado por uma fonte de 12V DC.
- RNF05: O feedback do sistema ao usuário será feito através de um display LCD e de um speaker.
- RNF06: O sistema deve poder funcionar offline.
- RNF07: Programação do ESP32 será feita utilizando a IDE PlatformIO.
- RNF08: A programação do STM32F411 será feita utilizando a IDE STM32CubeIDE.
- RNF09: O projeto mecânico será feito no programa de CAD Fusion 360.
- RNF10: As peças da prova de conceito serão construídas utilizando uma impressora 3D.



