---
title: Exibir sinalizadores de recursos entre ambientes
description: Saiba como visualizar o status de sinalizadores de recursos em todos os ambientes vinculados para um aplicativo em implantações do Adobe Experience.
source-git-commit: 5c99061a7f2aaaad98190166ea6fd79b7eb26dec
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 3%

---


# Exibir sinalizadores de recursos entre ambientes {#view-flags-across-environments}

Depois de vincular as instâncias do aplicativo entre os ambientes, as Implantações de experiência exibem o status de cada sinalizador de recurso em todos os ambientes vinculados diretamente na página da lista de sinalizadores de recurso. Isso oferece uma única visualização para comparar estados de sinalizador — por exemplo, se um sinalizador está ATIVADO no preparo e DESATIVADO na produção — sem alternar ambientes.

## Pré-requisitos {#prerequisites}

As instâncias do aplicativo devem ser vinculadas entre ambientes para que o status entre ambientes fique visível. Consulte [Associar ambientes a um aplicativo](associate-environments.md) para obter instruções de configuração.

## Como funciona {#how-it-works}

Ao navegar até **Recursos e versões > Sinalizadores de recursos** e selecionar um aplicativo que tenha instâncias vinculadas, a página de listagem mostra colunas adicionais para cada ambiente vinculado. Cada coluna exibe o estado atual do sinalizador de recurso nesse ambiente.

Os sinalizadores de recursos são correspondidos entre ambientes pela **chave** — não pelo nome. Isso significa:

* Um sinalizador pode ter um nome de exibição diferente em cada ambiente, desde que a chave seja a mesma.
* O nome mostrado em cada coluna de ambiente é o nome usado nesse ambiente.

## Caso de uso {#use-case}

Um fluxo de trabalho típico é desenvolver e testar um sinalizador de recurso em um ambiente inferior (por exemplo, Preparo) e, em seguida, verificar seu status antes de promover a configuração para produção. A visibilidade entre ambientes permite confirmar se o sinalizador está configurado corretamente no Palco antes de importá-lo para produção, tudo a partir do console de Produção.

## Consulte também {#see-also}

* [Associar ambientes a um aplicativo](associate-environments.md)
* [Importar sinalizadores de recursos](import-feature-flags.md)
* [Conceito entre ambientes](cross-environment-concept.md)
