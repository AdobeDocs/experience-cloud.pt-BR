---
title: Importar sinalizadores de recursos
description: Saiba como importar sinalizadores de recursos de um ambiente inferior para um ambiente superior em implantações do Adobe Experience para evitar a recriação manual das configurações de sinalizador.
source-git-commit: 5c99061a7f2aaaad98190166ea6fd79b7eb26dec
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 1%

---


# Importar sinalizadores de recursos {#import-feature-flags}

As Implantações de experiência permitem importar sinalizadores de recursos de um ambiente inferior (por exemplo, Preparo) para um ambiente superior (por exemplo, Produção). Isso evita a necessidade de recriar as configurações de sinalizador manualmente e reduz o risco de descompasso entre os ambientes.

## Pré-requisitos {#prerequisites}

Para usar o workflow de importação, as instâncias do aplicativo devem estar vinculadas entre os ambientes. Consulte [Associar ambientes a um aplicativo](associate-environments.md).

## Etapa 1: Ir para o ambiente e aplicativo de destino {#step-1}

Faça logon no console do ambiente **de destino** — o ambiente para o qual você deseja importar os sinalizadores *de*. Selecione o aplicativo para o qual você deseja importar sinalizadores no menu suspenso do aplicativo na página Sinalizadores de recursos.

>[!IMPORTANT]
>
>O ambiente atual e o aplicativo selecionado devem ser o **destino** — não a origem. Por exemplo, para importar um sinalizador do Preparo para a Produção, faça logon no console Produção e selecione o aplicativo Produção.

## Etapa 2: abrir a caixa de diálogo de importação {#step-2}

Selecione **Importar Sinalizadores de Recursos**. Uma caixa de diálogo é aberta mostrando o ambiente e o aplicativo de origem, pré-preenchidos com base nos ambientes vinculados configurados para seu aplicativo. Se necessário, você pode alterar o ambiente de origem e o aplicativo dos menus suspensos na caixa de diálogo.

## Etapa 3: Selecionar os sinalizadores de recurso a serem importados {#step-3}

Na lista de sinalizadores de recursos no ambiente de origem, selecione os sinalizadores que deseja importar. Você pode selecionar um, vários ou todos os sinalizadores de uma só vez.

## Etapa 4: Manipular sinalizadores existentes (se necessário) {#step-4}

Se um sinalizador de recurso com a mesma chave já existir no ambiente de destino, as implantações de experiência solicitarão que você confirme se deve substituí-lo. Revise a configuração do sinalizador existente antes de confirmar, pois a substituição substituirá as configurações do sinalizador de destino pelas da origem.

## Observações importantes {#important-notes}

Lembre-se do seguinte ao importar sinalizadores de recursos:

* Os sinalizadores importados são sempre definidos para o estado **OFF** no ambiente de destino, independentemente do estado no ambiente de origem. Você deve habilitá-los manualmente após a importação.
* Se um sinalizador foi agendado para ser ativado em uma data e hora futuras no ambiente de origem, esse agendamento é **não** transportado. Você deve definir um novo agendamento no ambiente de destino, se necessário.

## Consulte também {#see-also}

* [Associar ambientes a um aplicativo](associate-environments.md)
* [Exibir sinalizadores de recursos entre ambientes](view-feature-flags-across-environments.md)
* [Conceito entre ambientes](cross-environment-concept.md)
