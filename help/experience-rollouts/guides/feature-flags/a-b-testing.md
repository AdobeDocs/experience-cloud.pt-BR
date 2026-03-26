---
title: Teste A/B com sinalizadores de recursos
description: Saiba como executar testes A/B usando grupos de recursos em implantações de experiência do Adobe, configurando várias variantes para um conjunto de sinalizadores de recursos.
exl-id: bb849049-229c-40ff-bbfe-7996f868bcc3
source-git-commit: 454b5c719a5f8be82d1ed835da58bfca6316def2
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 1%

---

# Teste A/B com sinalizadores de recursos {#a-b-testing}

Os testes A/B em implantações de experiência são executados usando **grupos de recursos**. Ao configurar mais de uma variante em um grupo de recursos, você pode distribuir diferentes versões de um recurso para diferentes subconjuntos do público-alvo e comparar os resultados.

## Pré-requisitos {#prerequisites}

* Você tem acesso ao console — consulte [Fazer logon no console](../console/log-in-to-the-console.md)
* Você pertence a uma equipe e seu aplicativo é integrado
* Você tem a função **Desenvolvedor** ou **Proprietário da Versão do Produto**
* Você criou os sinalizadores de recursos para testar — consulte [Criar seu primeiro sinalizador de recursos](create-your-first-feature-flag.md)

## Etapa 1: criar um grupo de recursos com várias variantes {#create}

1. Navegue até **Teste de Recursos > Grupos de Recursos** e selecione **Novo Grupo de Recursos**.
2. Em **Detalhes Básicos**, forneça um título, uma chave e uma descrição.
3. Defina uma **porcentagem de implantação** para definir quanto do seu público-alvo participa do teste.
4. Defina **Variants** com um valor maior que um (por exemplo, duas variantes para um teste A/B clássico).
5. Consulte [Definir um grupo de recursos para implantação gradual](set-feature-group-gradual-rollout.md) para entender como a porcentagem de exposição é distribuída entre variantes.

## Etapa 2: definir o público {#audience}

Na guia **Público-alvo**, adicione os critérios de público-alvo e selecione os aplicativos a serem incluídos. Os grupos de recursos podem abranger vários aplicativos na mesma equipe.

>[!NOTE]
>
>Para direcionar usuários externos em um teste A/B, você deve ter a função **Proprietário da versão do produto**. A função de Desenvolvedor está em sandbox e limitada a testes privados.

## Etapa 3: adicionar recursos por variante {#features}

Na guia **Recursos**, cada variante tem sua própria guia. Adicione os sinalizadores de recursos apropriados a cada variante para definir as diferentes experiências que você deseja comparar.

>[!IMPORTANT]
>
>Um sinalizador de recurso só pode ser distribuído por meio de um método de cada vez — sinalizador de recurso, grupo de recurso ou versão. Adicionar um sinalizador a um grupo de recursos remove qualquer público ou conjunto de implantação de porcentagem diretamente no sinalizador.

## Etapa 4: salvar e ativar {#save}

Salve as configurações do grupo de recursos. Quando estiver pronto para iniciar o teste, defina o grupo de recursos para o estado ativo.

## Consulte também {#see-also}

* [Criar um grupo de recursos](create-a-feature-group.md)
* [Definir um grupo de recursos para implantação gradual](set-feature-group-gradual-rollout.md)
* [Analytics](analytics.md)
