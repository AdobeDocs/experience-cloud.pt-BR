---
title: Associar ambientes a um aplicativo
description: Saiba como vincular as instâncias do aplicativo entre ambientes em implantações de experiência do Adobe para gerenciar sinalizadores de recursos de forma consistente, do desenvolvimento à produção.
exl-id: 53080db1-f257-4369-82ab-57c84395a40a
source-git-commit: 454b5c719a5f8be82d1ed835da58bfca6316def2
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 1%

---

# Associar ambientes a um aplicativo {#associate-environments}

Vincular as instâncias do aplicativo entre ambientes permite a visibilidade entre ambientes e importar workflows. Você deve ter a função de **Administrador** para configurar isso. Entre em contato com o administrador da equipe se precisar verificar ou atualizar sua função.

Para obter informações sobre por que isso é útil, consulte [Conceito entre ambientes](cross-environment-concept.md).

## Etapa 1: abrir as configurações do aplicativo {#step-1}

1. Faça logon no console Implantações de experiência.
2. Navegue até **Administrador > Aplicativos**.
3. Selecione **Novo aplicativo** para integrar um novo aplicativo ou selecione um aplicativo existente para editá-lo.

## Etapa 2: configurar a seção Ambientes associados {#step-2}

No formulário do aplicativo, role até a seção **Ambientes Associados**. Cada linha desta seção define um dos ambientes de implantação do aplicativo. Para cada ambiente, configure os seguintes campos:

| Campo | Descrição |
|---|---|
| **Ambiente** | Selecione um identificador de ambiente padrão na lista: QA1, QA2, STG1, STG2, PROD1 ou PROD2. Isso informa às implantações de experiência se o ambiente é de produção ou não e determina a codificação de cores usada no console. |
| **Rótulo do ambiente** | Um nome personalizado para este ambiente como sua equipe se refere a ele — por exemplo, `Dev`, `Staging` ou `Production`. Este é um formato livre e não precisa corresponder ao identificador padrão. |
| **Ambiente de implantações de experiência** | O ambiente de plataforma (Preparo ou Produção) em que esta instância do aplicativo está hospedada. Preenchido previamente com base no console em que você está no momento. |
| **ID do aplicativo** | A ID do cliente da instância do aplicativo neste ambiente. Preenchido automaticamente ao selecionar um aplicativo no menu suspenso. |

## Etapa 3: vincular instâncias do aplicativo em vários ambientes {#step-3}

Para vincular instâncias em ambientes, siga estas etapas para cada ambiente adicional:

1. Crie a instância do aplicativo em seu ambiente de destino (por exemplo, crie o aplicativo de controle de qualidade no console Preparo).
2. Retorne ao aplicativo que você está configurando e adicione uma nova linha em **Ambientes Associados**.
3. No menu suspenso **ID do Aplicativo**, selecione a instância do aplicativo que você acabou de criar. A tag de ambiente e o rótulo são preenchidos automaticamente.
4. Selecione **Atualizar** para salvar.

Repita esse processo para cada ambiente que deseja vincular — por exemplo, vinculando instâncias de controle de qualidade, Preparo e Produção do mesmo aplicativo.

## Observações importantes {#important-notes}

* Os ambientes de controle de qualidade e Preparo podem ser hospedados no ambiente da plataforma de Preparo de implantações de experiência ou de Produção.
* Os ambientes de produção (PROD1, PROD2) só podem ser hospedados no ambiente de produção de implantações de experiência.
* Você só pode vincular a um ambiente inferior a partir de um ambiente superior. Por exemplo, a partir da produção, é possível vincular a uma instância de Preparo ou Controle de qualidade, mas o inverso é somente leitura.

## Consulte também {#see-also}

* [Conceito entre ambientes](cross-environment-concept.md)
* [Exibir sinalizadores de recursos entre ambientes](view-feature-flags-across-environments.md)
* [Importar sinalizadores de recursos](import-feature-flags.md)
