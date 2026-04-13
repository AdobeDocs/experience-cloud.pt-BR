---
title: O que é um sinalizador de recurso
description: Saiba o que são sinalizadores de recursos e como eles permitem ativar ou desativar recursos do aplicativo no tempo de execução sem reimplantação.
hide: true
exl-id: c4ed4ab5-0d73-4697-b05c-476d6e4010ce
source-git-commit: 12032cbed45e694a3f25f16afe80308b3eb82924
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# O que é um sinalizador de recurso {#what-is-a-feature-flag}

Um sinalizador de recurso é um mecanismo que permite ativar ou desativar os recursos do aplicativo no tempo de execução — sem reimplantar o código.

Os sinalizadores de recursos dissociam a **implantação de código** da **disponibilidade de recursos**. Você pode enviar o novo código para produção com o recurso oculto atrás de um sinalizador e, em seguida, ativá-lo sempre que estiver pronto — para todos os usuários ou para um subconjunto direcionado.

Essa separação reduz significativamente o risco. Os desenvolvedores podem criar e enviar continuamente com interrupção mínima, enquanto as equipes de produtos mantêm controle total sobre quando e para quem um recurso se torna visível.

>[!NOTE]
>
>Nas implantações da experiência, um sinalizador de recurso é a unidade mais atômica de controle de recurso. Ele pode ser usado sozinho para direcionar um único recurso ou combinado com outros sinalizadores em um [grupo de recursos](feature-groups-to-control-multiple-features.md).

<!-- -->
