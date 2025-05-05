---
title: Pontos de acesso
description: Saiba mais sobre os endpoints das APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: 14d8cf78192bcad7b89cc70827f5672bd6e07f4a
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 9%

---

# Pontos de acesso {#endpoints}

Os endpoints disponíveis para a API REST do Adobe Campaign:

* **/profileAndServices**: interage com campos prontos para uso. Os campos estendidos não podem ser acessados com este endpoint.
* **/profileAndServicesExt**: interage com campos personalizados adicionados durante a extensão de recurso personalizado Perfil ou Serviços. Para obter mais informações sobre recursos personalizados, consulte [esta seção](custom-resources.md).
* **/&lt;transactionalAPI>**: interagir com a API de mensagens transacionais (o nome do ponto de extremidade da API de mensagens transacionais depende da configuração da instância). Para obter mais informações, consulte [esta seção](managing-transactional-messages.md).
* **/workflow/execution**: interagir com fluxos de trabalho. Para obter mais informações, consulte [esta seção](controlling-a-workflow.md).

Por padrão, os principais recursos disponíveis para as APIs **profileAndServices** e **profileAndServicesExt** são:

* **/profile**: interagir com perfis do banco de dados do Campaign. Para adicionar perfis a um serviço, use o ponto de extremidade **/serviço**. Para obter mais informações sobre perfis no Campaign, consulte a [documentação do Campaign](https://helpx.adobe.com/br/campaign/standard/audiences/using/about-profiles.html).
* **/serviço**: gerenciar serviços de assinatura. Para obter mais informações sobre os serviços no Campaign, consulte a [documentação do Campaign](https://helpx.adobe.com/br/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Todos os outros recursos estendidos ou criados estão disponíveis somente por meio da API **ProfileAndServicesExt**. Eles devem estar vinculados ao recurso **Perfil** para serem acessíveis.
