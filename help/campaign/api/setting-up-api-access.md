---
title: Configuração do acesso à API
description: Saiba como configurar o acesso a APIs Campaign Standard.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: 3e7af8a9ba41ab54738fff2f69388595041a8574
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 31%

---

# Configuração do acesso à API {#setting-up-api-access}

O acesso à API do Adobe Campaign Standard é configurado de acordo com as etapas abaixo. Cada uma dessas etapas é detalhada na seção [Documentação do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Para gerenciar certificados no [Adobe Developer](https://developer.adobe.com/), verifique se você tem **Administrador do sistema** direitos sobre a organização ou uma [conta do desenvolvedor](https://helpx.adobe.com/br/enterprise/using/manage-developers.html) no Admin Console.

1. **Verifique se você tem um certificado digital** ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Criar uma nova integração com o Adobe Campaign Service** in [Adobe Developer](https://developer.adobe.com/) e configure-a. Suas credenciais serão geradas (chave da API, segredo do cliente etc.).
1. **Crie um JSON Web Token (JWT)** das credenciais geradas anteriormente e assine-o com sua chave privada. O JWT codifica todas as informações de identidade e segurança necessárias para que o Adobe verifique sua identidade e conceda acesso à API.

   >[!IMPORTANT]
   >
   >O JWT (Tokens JSON da Web) está atualmente em processo de descontinuação, sendo substituído pelo OAuth. A transição está sendo realizada progressivamente nas próximas versões do Campaign. As credenciais da Conta de serviço (JWT) foram marcadas como obsoletas, elas continuarão a funcionar até 27 de janeiro de 2025. Portanto, você deve migrar seu aplicativo ou integração para usar a nova credencial OAuth de servidor para servidor antes de 27 de janeiro de 2025. A autenticação OAuth é preferível. Você encontrará todos os elementos para migrar da autenticação JWT para a autenticação OAuth nestas páginas:
   >* [Migração](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)
   >* [Implementação](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)
   >* [Perguntas frequentes sobre a descontinuação do JWT](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)

1. **Trocar seu JWT por um token de acesso** por meio de uma solicitação POST. Esse token de acesso precisará ser usado em cada cabeçalho das solicitações de API.

Para estabelecer uma sessão de API segura e de serviço a serviço no Adobe I/O, cada solicitação para um serviço da Adobe deve incluir as informações abaixo no cabeçalho de autorização.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**: esta é a sua ID de ORGANIZAÇÃO pessoal, uma ID de ORGANIZAÇÃO é fornecida pelo Adobe para cada uma de suas instâncias:

   * &lt;organization> : sua instância de produção,
   * &lt;organization-mkt-stage>: a instância do estágio.

  Para obter o valor da ID de ORGANIZAÇÃO, consulte seu administrador ou contato técnico da Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte a <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Documentação do Adobe Developer</a>).

* **&lt;access_token>**: seu token de acesso pessoal, que foi recuperado ao trocar seu JSON Web Token por meio de uma solicitação POST.

* **&lt;API_KEY>**: sua chave de API pessoal. Ele é fornecido no Adobe I/O após a criação de uma nova integração ao Adobe Campaign Service.

  ![texto alternativo](assets/tenant.png)

## Solução de problemas

Durante a integração do AdobeIO, se o seguinte erro for exibido:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Consulte o administrador ou o contato técnico do Adobe para verificar se o parâmetro CNAME foi criado corretamente.
