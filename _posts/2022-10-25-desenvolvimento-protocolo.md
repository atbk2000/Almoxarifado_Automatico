
Nessa semana trabalhamos na implementação do protocolo de aplicação entre o controlador e o módulo. Parte essencial do nosso projeto que nos permite tanto
obter dados da saída do modulo quanto controlar atuadores conectados aos módulos através do controlador.

Esse protocolo foi pensando para uma interface half-duplex, como nosso projeto é pensando com um controlador conectado a múltiplos módulos no mesmo
barramento, foi necessário elaborar o protocolo de modo que dois dispositivos nunca usem o barramento simultaneamente. Nossa solução para este problema foi
a implementação de um protocolo aonde o controlador sempre inicia, toda a comunicação, e os módulos apenas respondem as mensagens endereçadas a ele.
Atualmente o protocolo é formado pelos campos:

| Nome | Tipo | Descrição |
| :------ |:--- | :--- |
| moduleID | uint8 | ID único do modulo a receber essa mensagem |
| dataSize | uint32| Quantidade de dados na mensagem(em bytes)|
| commandID| uint8 | ID do comando a ser executado pelo modulo |
| data | uint8[]   |Data especifica do comando, com o tamanho total de dataSize bytes|
| crc8 | uint8[]   | CRC utilizado para verificar a integridade da mensagem|


Sendo que atualmente temos os comandos implementados:

| Comando | Parâmetros | Descrição |
| :------ |:--- | :--- |
| CMD_PING | nenhum |  Comando enviado pelo controlador para checar a conectividade com um modulo |
| CMD_PING_RESP | eventId(uint8)| Resposta do modulo a um comando ping, pode ser enviado na resposta deste comando um eventId, indicando um evento ocorrido no modulo |
| CMD_GET_LC| lc(id) | Controlador requisita a ultima leitura da célula de carga id |
| CMD_GET_LC_RESP | lcRead(float)  | Resposta do modulo ao comando CMD_GET_LC com|
| CMD_RESET_TARE | lc(id) | Reseta a tara da célula de carga id|
| CMD_RESET_TARE_RESP | lc(id) | Indica que o comando CMD_RESET_TARE foi bem sucedido|
| CMD_OPEN_LOCK | lock(id) | Indica ao modulo para ativar o solenoide da fechadura id |
| CMD_RESET_LOCK_RESP | lock(id) | Indica que o comando CMD_RESET_TARE foi bem sucedido|


O protocolo foi projetado para que essa lista seja facilmente estendida com a adição de novos sensores e atuadores. E o CRC8 no final ajuda a garanti a integridade das mensagens transmitidas.
