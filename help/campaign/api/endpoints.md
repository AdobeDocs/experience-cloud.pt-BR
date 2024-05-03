---
title: Pontos de acesso
description: Saiba mais sobre os endpoints das APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 9%

---

# Pontos de acesso {#endpoints}

Os endpoints disponíveis para a API REST do Adobe Campaign:

* **/profileAndServices**: interaja com os campos prontos para uso. Os campos estendidos não podem ser acessados com este endpoint.
* **/profileAndServicesExt**: interage com campos personalizados adicionados durante a extensão de recurso personalizado Perfil ou Serviços. Para obter mais informações sobre recursos personalizados, consulte [nesta seção](custom-resources.md).
* **/&lt;transactionalapi>**: interagir com a API de mensagens transacionais (o nome do endpoint da API de mensagens transacionais depende da configuração da instância). Para obter mais informações, consulte [esta seção](managing-transactional-messages.md).
* **/workflow/execution**: interagir com workflows. Para obter mais informações, consulte [esta seção](controlling-a-workflow.md).

Por padrão, os principais recursos disponíveis para o **profileAndServices** e **profileAndServicesExt** As APIs são:

* **/profile**: interaja com perfis do banco de dados do Campaign. Para adicionar perfis a um serviço, use o **/service** terminal. Para obter mais informações sobre perfis no Campaign, consulte [Documentação da campanha](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: gerencie serviços de assinatura. Para obter mais informações sobre os serviços no Campaign, consulte a [Documentação da campanha](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Todos os outros recursos que foram estendidos ou criados estão disponíveis por meio do **ProfileAndServicesExt** Somente API. Eles devem estar vinculados à variável **Perfil** para ser acessível.
