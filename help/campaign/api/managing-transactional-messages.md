---
title: Gerenciamento de mensagens transacionais
description: Saiba como gerenciar mensagens transacionais com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
exl-id: 00d39438-a232-49f1-ae5e-1e98c73397e3
source-git-commit: 110fcdcbefef53677cf213a39f45eb5d446807c2
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 1%

---

# Gerenciamento de mensagens transacionais {#managing-transactional-messages}

>[!AVAILABILITY]
>
>Por enquanto, as mensagens transacionais usando as APIs REST estão disponíveis para os canais de email e SMS. Ela só está disponível para eventos transacionais (os dados de enriquecimento só estão disponíveis por meio de carga, de modo semelhante ao funcionamento do Adobe Campaign V8).

Depois de criar e publicar um evento transacional, é necessário integrar o acionamento desse evento ao site.

Por exemplo, você deseja que um evento de &quot;Abandono de carrinho&quot; seja acionado sempre que um de seus clientes sair do site antes de comprar os produtos no carrinho. Para fazer isso, como desenvolvedor da Web, você deve usar a API de mensagens transacionais REST.

1. Envie uma solicitação de acordo com o método POST, que aciona o [envio do evento transacional](#sending-a-transactional-event).
1. A resposta à solicitação POST contém uma chave primária, que permite enviar uma ou várias solicitações por meio de uma solicitação GET. Você pode obter o [status do evento](#transactional-event-status).

## Envio de um evento transacional {#sending-a-transactional-event}

O evento transacional é enviado por uma solicitação POST com a seguinte estrutura de URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;ORGANIZAÇÃO>**: sua ID de ORGANIZAÇÃO pessoal. Consulte [esta seção](must-read.md).

* **&lt;transactionalAPI>**: os endPoints da API de Mensagens Transacionais.

  O nome do endpoint da API de Mensagens transacionais depende da configuração da sua instância. Ele corresponde ao valor &quot;mc&quot; seguido pela ID de organização pessoal. Vejamos o exemplo da empresa Geometrixx, com &quot;geometrixx&quot; como a ID da organização. Nesse caso, o pedido POST seria o seguinte:

  `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

* **&lt;eventID>**: o tipo de evento que você deseja enviar. Essa ID é gerada ao criar a configuração do evento

### cabeçalho de solicitação POST

A solicitação deve conter um cabeçalho &quot;Content-Type: application/json&quot;.

Você deve adicionar um conjunto de caracteres, por exemplo **utf-8**. Observe que esse valor depende do aplicativo REST que você está usando.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### corpo da solicitação POST

Os dados do evento estão contidos no corpo POST JSON. A estrutura do evento depende de sua definição.

Os seguintes parâmetros opcionais podem ser adicionados ao conteúdo do evento para gerenciar o envio de mensagens transacionais vinculadas ao evento:

* **expiração** (opcional): após esta data, o envio do evento transacional será cancelado.
* **agendado** (opcional): a partir desta data, o evento transacional será processado e a mensagem transacional será enviada.

>[!NOTE]
>
>Os valores dos parâmetros &quot;expiration&quot; e &quot;scheduled&quot; seguem o formato ISO 8601. A norma ISO 8601 especifica a utilização da letra maiúscula &quot;T&quot; para separar a data e a hora. No entanto, ele pode ser removido da entrada ou saída para melhorar a legibilidade.

### Parâmetros do canal de comunicação

Dependendo do canal a ser usado, a carga deve conter os parâmetros abaixo:

* Canal de email: &quot;mobilePhone&quot;
* Canal SMS: &quot;email&quot;

Se o payload contiver apenas &quot;mobilePhone&quot;, o canal de comunicação SMS será acionado. Se o conteúdo contiver apenas &quot;email&quot;, o canal de comunicação por email será acionado.

O exemplo abaixo mostra uma carga em que uma comunicação SMS será acionada:

```
curl --location 'https://mc.adobe.io/<ORGANIZATION>/campaign/mcAdobe/EVTcartAbandonment' \
--header 'Authorization: Bearer <ACCESS_TOKEN>' \
--header 'Cache-Control: no-cache' \
--header 'X-Api-Key: <API_KEY>' \
--header 'Content-Type: application/json;charset=utf-8' \
--header 'Content-Length: 79' \
--data '
{
  "mobilePhone":"+9999999999",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "ctx":
  {
    "cartAmount": "$ 125",
    "lastProduct": "Leather motorbike jacket",
    "firstName": "Jack"
  }
}'
```

Se a carga incluir &quot;email&quot; e &quot;mobilePhone&quot;, o método de comunicação padrão será email. Para enviar um SMS quando ambos os campos estiverem presentes, você deverá especificá-lo explicitamente na carga usando o parâmetro &quot;wishedChannel&quot;.

### Resposta à solicitação POST

A resposta POST retorna o status do evento transacional no momento em que ele foi criado. Para recuperar o status atual (dados do evento, status do evento...), use a Chave primária retornada pela resposta POST em uma solicitação GET:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Solicitação de exemplo***

Solicitação POST para enviar o evento.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/mcAdobe/EVTcartAbandonment \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79'

{
  "
  
  
  ":"test@example.com",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "ctx":
  {
    "cartAmount": "$ 125",
    "lastProduct": "Leather motorbike jacket",
    "firstName": "Jack"
  }
}
```

Resposta à solicitação POST.

```
{
  "PKey":"<PKEY>",
  "ctx":
  {
    "cartAmount": "",
    "lastProduct": "",
    "firstName": ""
  }
  "email":"",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "href": "mcAdobe/EVTcartAbandonment/<PKEY>",
  "serverUrl":" https://myserver.com ",
  "status":"pending",
  "type":""
}
```

### Status do evento transacional {#transactional-event-status}

Na resposta, o campo &quot;status&quot; permite saber se o evento foi processado ou não:

* **pendente**: o evento está pendente - o evento assume esse status quando ele acabou de ser acionado.
* **processando**: a entrega do evento está pendente - ele está sendo transformado em uma mensagem e a mensagem está sendo enviada.
* **paused**: o processo de evento está sendo pausado. Ele não é mais processado, mas mantido em fila no banco de dados do Adobe Campaign.
* **processed**: o evento foi processado e a mensagem foi enviada com êxito.
* **ignorado**: o evento foi ignorado pela entrega, normalmente quando um endereço está em quarentena.
* **deliveryFailed**: erro de entrega durante o processamento do evento.
* **routingFailed**: a fase de roteamento falhou - isso pode ocorrer, por exemplo, quando o tipo de evento especificado não pode ser encontrado.
* **tooOld**: o evento expirou antes de poder ser processado - isso pode acontecer por vários motivos, por exemplo, quando um envio falha várias vezes (isso resulta no evento não estar mais atualizado) ou quando o servidor não pode mais processar eventos depois de ficar sobrecarregado.
