# http-001-fundamentos

# Aula 1

## O que aprendemos neste capítulo?

 - Na internet sempre tem um cliente e um servidor
 - Entre o cliente e o servidor precisam haver regras de comunicação
 - As regras são definidas dentro de um protocolo
 - HTTP é o protocolo mais importante na internet

-------------------

HTTP - Hypertext Transfer Protocol

 - o HTTP foi feito para estabelecer regras de comunicação entre o modelo Cliente-Servidor que funciona na Web.

------------------

https://tools.ietf.org/html/rfc2616

-----------------

Protocolo P2P ou Peer-To-Peer

Cada Cliente ajuda no trabalho, ou seja, assumi um pouco da responsabilidade do servidor. Não há mais uma clara divisão entre Cliente-Servidor, cada cliente também é servidor e vice-versa!


----------------

## Alguns protocolos

 - SMTP - Simple Mail Transfer Protocol, protocolo para enviar e-mails.
 - BitTorrent - Além de ser um protocolo, também é um aplicativo para troca de arquivos na internet.
 - FTP - File Transport Protocol, protocolo para transferir arquivos

-----------------

Alura usa a plataforma Java e o servidor concreto se chama Tomcat e banco de dados MySQL

```
Cliente  <--- HTTP ---> Servidor Java  <--- SQL ---> Banco de dados
```


![Arquitetura Alura](https://s3.amazonaws.com/caelum-online-public/http/arquitetura_alura.png)


-----------------

## O que você aprendeu nesse capítulo?

 - A arquitetura Cliente-Servidor
 - Um protocolo é um conjunto de regras
 - HTTP é um protocolo que define as regras de comunicação entre cliente e servidor na internet.
 - HTTP é o protocolo mais importante da Internet
 
 ------------------
 
 # Aula 2
 
 ## Requisição

HTTP, todos os dados enviados entre cliente e servidor são transmitidos em texto puro, inclusive dados sensíveis, como login e senha

Por exemplo, usando uma conexão Wi-Fi, os dados do navegador passam primeiro para o roteador Wi-Fi, e do roteador passam para o modem do provedor, do modem para algum servidor do provedor de internet, como Oi ou NET

----------------------------

HTTPS, que basicamente é o HTTP comum, porém com uma camada adicional de segurança/criptografia que antes era SSL, mas posteriormente passou-se a ser também TLS. É muito comum que estas duas siglas sejam encontradas juntas como SSL/TLS por se tratarem da mesma questão de segurança

 - HTTP: HyperText Transfer Protocol
 - SSL/TLS: Secure Sockets Layer / Transport Layer Security

------------------------

O que aprendemos nesse capítulo?
 - Só com HTTPS a web é segura.
 - HTTPS significa usar um certificado digital no servidor.
 - O certificado prova a identidade e tem validade
 - O certificado possui uma chave publica.
 - A chave é utilizada pelo navegador para criptografar os dados.

-----------------
Aprendemos no vídeo que o HTTPS usa uma chave pública e uma chave privada. As chaves estão ligadas matematicamente, o que foi cifrado pela chave pública só pode ser decifrado pela chave privada. Isso garante que os dados cifrados pelo navegador (chave pública) só podem ser lidos pelo servidor (chave privada). Como temos duas chaves diferentes envolvidas, esse método de criptografia é chamado de criptografia assimétrica. No entanto, a criptografia assimétrica tem um problema, ela é lenta.

No certificado, vem a chave pública para o cliente utilizar, certo? E o servidor continua na posse da chave privada, ok? Isso é seguro, mas lento e por isso o cliente gera uma chave simétrica ao vivo. Uma chave só para ele e o servidor com o qual está se comunicando naquele momento! Essa chave exclusiva (e simétrica) é então enviada para o servidor utilizando a criptografia assimétrica (chave privada e pública) e então é utilizada para o restante da comunicação.

Então, HTTPS começa com criptografia assimétrica para depois mudar para criptografia simétrica. Essa chave simétrica será gerada no início da comunicação e será reaproveitada nas requisições seguintes. Bem-vindo ao mundo fantástico do HTTPS :)


-----------

O que você aprendeu nesse capítulo?

 - Por padrão, os dados são trafegados como texto puro na web.
 - Apenas com HTTPS a Web é segura
 - O protocolo HTTPS nada mais é do que o protocolo HTTP mais uma camada adicional de segurança, a TLS/SSL
 - O tipo de criptografia de chave pública/chave privada
 - O que são os certificados digitais
 - Certificado possuem identidade e validade
 - As chaves públicas estão no certificado, a chave privada fica apenas no servidor
 - O que é uma autoridade certificadora
 - O navegador utiliza a chave pública para criptografar os dados
