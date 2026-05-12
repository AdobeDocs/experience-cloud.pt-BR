---
title: Identidade visual
description: Descubra todas as ferramentas disponíveis para gerenciar as identidades da sua marca
audience: administration
context-tags: branding,overview;branding,main
role: Admin
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
exl-id: f6438303-5ae8-47c6-8c34-8e586f4b6fe7
TQID: https://experienceleague.adobe.com/El7fE2aveS9C67b8B8fkMpiwMaMx-9aWpW4-3Ev7mG4
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2: id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ad84694f2f6f45e4ee30fc51379106835ac302be
workflow-type: tm+mt
source-wordcount: 363
ht-degree: 23%

---

# Introdução à identidade visual {#branding-gs}

>[!IMPORTANT]
>
>As marcas não podem ser criadas ou modificadas pelos usuários finais: essas operações têm de ser efetuadas pelo administrador técnico do Adobe Campaign. Para receber qualquer solicitação, entre em contato com o Atendimento ao cliente da Adobe.

Todas as empresas têm diretrizes de marca que definem os elementos visuais e os detalhes técnicos. O Adobe Campaign ajuda você a gerenciar essas diretrizes de maneira central para que possa apresentar uma imagem de marca consistente aos seus clientes em tudo o que você faz, desde logotipos em emails até URLs e domínios usados em suas campanhas.

Os administradores técnicos podem criar e gerenciar várias marcas no Adobe Campaign. Isso permite definir todos os elementos que compõem a identidade da sua marca, incluindo logotipos e até mesmo configurações de rastreamento de email. Depois de criadas, essas marcas podem ser facilmente vinculadas aos seus deliveries.

Você pode adicionar novas entidades da organização no Campaign ou criar um novo tipo de email que deve ser enviado em um subdomínio diferente. Para fazer isso, siga as etapas abaixo:

1. **Configurar um novo subdomínio** - Para qualquer novo subdomínio ser usado pela Adobe, a primeira etapa será configurá-lo. Você pode fazer isso por meio do [Painel de Controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/subdomains-branding.html?lang=pt-BR) ou entrar em contato com seu contato técnico da Adobe. Saiba mais sobre a configuração de subdomínio [nesta página](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-domain-name-setup).

   >[!NOTE]
   >
   >O Painel de controle é acessível a todos os usuários administradores. As etapas para conceder acesso de Administrador a um usuário estão detalhadas [nesta página](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=pt-BR#discover-control-panel).

1. **Criar um modelo de entrega** - Quando a nova marca estiver disponível, a prática recomendada é criar pelo menos um novo modelo de entrega em branco que faça referência a essa nova marca. [Saiba mais](branding-assign.md).

1. **Verificar diretrizes de capacidade de entrega** - Antes de começar a usar o novo domínio, a estratégia deve ser discutida com a equipe de capacidade de entrega da Adobe. Eles ajudarão a definir as práticas recomendadas, se uma nova afinidade deve ser criada para dividir os IPs entre domínios, por exemplo, e/ou se um plano de aumento deve ser definido.
