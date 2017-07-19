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
 
 
 
 # Aula 3
 
 ## Endereço

WWW.ALURA.COM.BR


 - WWW - world wide web
 - ALURA - dominio
 - BR - Brasil (org - organizacional, edu - educacional, ...)
 - COM - Comercial (gov - governamental, ...)

-----

### Subdomínios

Subdomínios apontam para páginas diferentes dentro do mesmo domínio 

 - mail.google.com
 - drive.google.com

-----

### Endereços IP's

```
nslookup google.com
...
Name:    google.com
Address: 216.58.202.238
```

### DNS(Domain Name System)

Esse serviço age como um grande banco de dados de domínios. Portanto quando fazemos uma requisição para alura.com.br o DNS age transformando para um IP e a requisição prossegue.

https://developers.google.com/speed/public-dns/

-----

### Portas

http://www.alura.com.br:80

 - :80 - padrão do HTTP
 - :443 - padrão do HTTPs

Vários protocolos definem a sua porta padrão como por exemplo o FTP que usa 21 ou SSH que usa 22.
-----

### Recursos

https://cursos.alura.com.br/dashboard


 - O /dashboard é um recurso (resource)

-----
### Finalmente, a URL


![URL completa](https://s3.amazonaws.com/caelum-online-public/http/http-url.png)

-----
### URI ou URL

Uma URL é uma URI, mas nem todas as URI's são URL's! Existem URI's que identificam um recurso sem definir o endereço, nem o protocolo. Em outras palavras, uma URL representa uma identificação de um recurso (URI*) através do endereço, mas nem todas as identificações são URL's**.

![URL/URI](https://s3.amazonaws.com/caelum-online-public/http/http-uri-urn-url.png)
-----

O que aprendemos nesse capítulo?
 - URL são os endereços da Web
 
 - Uma URL começa com o protocolo (por exemplo https://) seguido pelo domínio (www.alura.com.br)

 - Depois do domínio pode vir a porta, se não for definida é utilizada a porta padrão desse protocolo
 
 - Após o domínio:porta, é especificado o caminho para um recurso (/course/introducao-html-css)
Um recurso é algo concreto na aplicação que queremos acessar



---------

# Aula 4

é importante saber que a comunicação sempre começa com o cliente: é ele quem pede as informações. O servidor responde apenas o que foi requisitado e nunca inicia a comunicação!

-----

requisição enviada pelo navegador para o servidor é chamada de HTTP REQUEST

 No mundo HTTP essa resposta é chamada de HTTP RESPONSE

-----


A comunicação segue sempre esse modelo: o cliente envia uma requisição e o servidor responde. Requisição e Resposta ou em inglês: Request-Response

Cada requisição ser independente é chamada de stateless

----- 
Resumindo teremos:

 - O HTTP usa sessões para salvar informações do usuário
 - Sessões só são possíveis por uso de Cookies
 - Cookies são pequenos arquivos que guardam informações no navegador
 - O HTTP é stateless, não mantem estado.

-----

Uma sessão HTTP nada mais é que um tempo que o cliente permanece ativo no sistema! Isso é parecido com uma sessão no cinema. Uma sessão, nesse contexto, é o tempo que o cliente usa a sala no cinema para assistir a um filme. Quando você sai da sala, termina a sessão. Ou seja, quando você se desloga, a Alura termina a sua sessão.

-----

Quando falamos de Cookies na verdade queremos dizer Cookies HTTP ou Cookie web. Um cookie é um pequeno arquivo de texto, normalmente criado pela aplicação web, para guardar algumas informações sobre usuário no navegador.

------

O que você aprendeu nesse capítulo?
 - O protocolo HTTP segue o modelo Requisição-Resposta
 - Sempre o cliente inicia a comunicação
 - Uma requisição precisa ter todas as informações para o servidor gerar a resposta
 - HTTP é stateless, não mantém informações entre requisições
 - As plataformas de desenvolvimento usam sessões para guardar informações entre requisições
 
 
 
 # Aula 5
 ## Depurando a requisição HTTP

-----

### Status code mais comuns

 - 200 - OK
 - 301 - moved permanentely
 - 404 - not found
 - 403 - forbidden (não permitido)
 - 500 - internal server error
 - 302 - Moved Temporarily


https://www.w3schools.com/tags/ref_httpmessages.asp

-------

### Familias Status code

 - 2xx - Successful responses
 - 3xx - Redirection messages
 - 4xx - client error responses
 - 5xx - server error responses

-------

https://httpstatusdogs.com/


# Aula 6

## Parâmetros da requisição

 - Query Params - Nome que se da para os parametros

O HTTP permite enviar mais de um parâmetro, basta concatenar o próximo parâmetro através do caractere "&"

-------

### método HTTP GET

Uma característica da requisição GET é enviar os parâmetros pela URL! Isso é útil quando queremos deixar os parâmetros visíveis. Assim podemos facilmente guardar a URL com os parâmetros para repetir a requisição algum momento depois.

-------

### método HTTP POST

Usando o POST, o navegador envia os dados do formulário no corpo da requisição e não na URL!

ao enviar uma requisição POST para o servidor, o nossa intenção é criar algo novo.

-----

Os métodos como GET e POST definem uma intenção mas o que realmente será executado depende do servidor.

-----

Quando enviamos parâmetros na URL, devemos iniciar pelo ?, o nome do parâmetro e um =, para separar o nome do parâmetro do seu valor:

```
?nome_do_parametro=seu_valor
```

Quando usamos mais do que, um parâmetro devemos usar & para separá-los:

```
?nome_do_parametro=seu_valor&nome_do_outro_param=valor
```


 - GET é normalmente usado para pesquisas

----------

Se o GET foi criado para receber dados, e o POST para adicionar algo no servidor, será que não existe algo para apagar e atualizar?

A resposta é sim, e os métodos se chamam DELETE e PUT.
 
 - GET - Receber dados(params na URL)

 - POST - Submeter dados (params no corpo da requisição)

 - DELETE - Remover um recurso

 - PUT - Atualizar um recurso 

------

### Web Service

O importante é que sempre usamos o protocolo HTTP. A grande diferença de um Web Service é que os dados não vem no formato HTML, e sim em algum formato independente da visualização, como XML ou JSON.


exemplo: http://viacep.com.br/ws/20040030/json

------




