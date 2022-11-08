---
layout: post
title: Implementação do banco de dados
cover-img:/assets/img/sqlite.png
tags: [Entregável 4]
comments: false
---

Como um dos requisitos do nosso projeto é funcionar sem a necessidade de acesso a internet. Foi necessário a implementação de um banco de dados no controlador de modo que fosse possível armazenar as informações dos usuarios e dos compartimentos de maneira permanente de uma maneira eficiente.

Devido a limitação do controlador utilizar como unidade de processamento um microcontrolador, inicialmente a ideia era implementar um registro simples utilizando arquivos de texto em um cartão SD.

Mas após pesquisar sobre o assunto, encontramos o SQLite3, um banco de dados bastante popular e maduro, que utilizando pouco mais de 200 Kbs de flash do microcontrolador implementa um banco de dados SQL completo, onde os dados podem ser armazenados em um único arquivo .db no cartão SD. Essa solução se mostrou bastante interessante porque além de fornecer uma solução eficiente  de armazenamento de dados também torna relativamente trivial a migração de dados de outros bancos de dados SQL. Facilitando na migração de bases de usuário de outros sistemas, por exemplo. 

## Tabelas

Atualmente são implementadas as seguintes tabelas utilizadas no sistemas:

### Tabela “user”

Informações especificas de cada usuário

| Nome | Tipo | Descrição |
| :------ |:--- | :--- |
| ID | INTEGER | Chave primaria do usuário |
| nome | TEXT| Nome do usuário|
| login| TEXT | Identificador único usado no login do usuário(numérico)|
| ultimo_acesso | TEXT   | Data do ultimo acesso deste usuário |
| privilegio | INTEGER   | Nível de acesso do usuário, 0 = Usuário, 1 = Administrador|
### Tabela “compartment”
Informações especificas de cada compartimento

| Nome | Tipo | Descrição |
| :------ |:--- | :--- |
| ID | INTEGER | Chave primaria do compartimento |
| object_name | TEXT| Nome do objeto sendo armazenado naquele compartimento|
| object_amount| INTEGER | Quantidade de objetos no compartimento |
| object_weight | REAL   | Peso do objeto(em gramas)|
| last_change | TEXT   | Data da ultima modificação do compartimento |
### Tabela “comparment_history” 

Armazena todas as transações que ocorreram em cada compartimento

| Nome | Tipo | Descrição |
| :------ |:--- | :--- |
| ID | INTEGER | Chave primaria do item no histórico |
| user_id| INTEGER| Chave do usuário que gerou essa transação| 
| compartment_id| INTEGER | Chave do compartimento envolvido na transação|
| change | INTEGER   | Quantidade de objetos adicionados ou removidos|
| date | TEXT   | Data da transação|


### Tabela “system”

Armazena as configurações do sistema

| Nome | Tipo | Descrição |
| :------ |:--- | :--- |
| wifi_ssd| TEXT| SSID da rede Wifi a ser conectada| 
| wifi_password| TEXT | Senha da rede Wifi a ser conectada |
| version | TEXT   | Versão do sistema|
