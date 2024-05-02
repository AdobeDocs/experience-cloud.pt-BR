---
title: Marca
description: Descubra todas as ferramentas disponíveis para gerenciar as identidades da sua marca
audience: administration
context-tags: branding,overview;branding,main
role: Admin
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: 51abadc86b97097d13824651d8c50d4ddd014a51
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 18%

---

# Introdução à identidade visual {#branding-gs}

>[!IMPORTANT]
>
>As marcas não podem ser criadas ou modificadas pelos usuários finais: essas operações têm de ser efetuadas pelo administrador técnico do Adobe Campaign. Para receber qualquer solicitação, entre em contato com o Atendimento ao cliente da Adobe.

Todas as empresas têm diretrizes de marca que definem os elementos visuais e os detalhes técnicos. O Adobe Campaign ajuda você a gerenciar essas diretrizes de maneira central para que possa apresentar uma imagem de marca consistente aos seus clientes em tudo o que você faz, desde logotipos em emails até URLs e domínios usados em suas campanhas.

Os administradores técnicos podem criar e gerenciar várias marcas no Adobe Campaign. Isso permite definir todos os elementos que compõem a identidade da sua marca, incluindo logotipos e até mesmo configurações de rastreamento de email. Depois de criadas, essas marcas podem ser facilmente vinculadas aos seus deliveries.

Você pode adicionar novas entidades da organização no Campaign ou criar um novo tipo de email que deve ser enviado em um subdomínio diferente. Para fazer isso, siga as etapas abaixo:

1. **Configurar um novo subdomínio** - Para qualquer novo subdomínio ser usado pelo Adobe, a primeira etapa será configurá-lo. Você pode executar isso até [Painel de controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/subdomains-branding.html?lang=pt-BR) ou entre em contato com seu contato técnico da Adobe. Saiba mais sobre configuração de subdomínio [nesta página](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-domain-name-setup).

   >[!NOTE]
   >
   >O Painel de controle é acessível a todos os usuários administradores. As etapas para conceder acesso de Administrador a um usuário estão detalhadas [nesta página](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=pt-BR#discover-control-panel).

1. **Criar um template do delivery** - Quando a nova marca estiver disponível, a prática recomendada é criar pelo menos um novo template do delivery em branco que faça referência a essa nova marca. [Saiba mais](branding-assign.md).

1. **Verificar diretrizes de entrega** - Antes de começar a usar o novo domínio, a estratégia deve ser discutida com a equipe de avaliação do Adobe. Eles ajudarão a definir as práticas recomendadas, se uma nova afinidade deve ser criada para dividir os IPs entre domínios, por exemplo, e/ou se um plano de aumento deve ser definido.

