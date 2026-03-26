---
title: Solução de problemas
description: Use o Workbench de implantações de experiência para diagnosticar problemas de avaliação de sinalizador de recursos para usuários específicos, incluindo a verificação de quais recursos estão ativados, desativados ou não correspondentes para uma determinada identidade de usuário.
exl-id: d64e9573-8e18-46a1-a75a-5ae5bfc7c82d
source-git-commit: 4a3133f014a9bb9d6ed26eb9d9f763db79ce63b3
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 0%

---

# Solução de problemas {#troubleshooting}

As Implantações de Experiência incluem uma ferramenta de diagnóstico integrada chamada **Bancada de Recursos** que ajuda você a entender exatamente quais sinalizadores de recursos um usuário específico recebe e por quê. Use-a para investigar relatórios de comportamento inesperado de recursos sem precisar reproduzir problemas no código.

## Acessar a Bancada de Recursos {#access-workbench}

Para abrir a Bancada de Recursos, siga estas etapas:

1. Faça logon no console Implantações de experiência.
2. Navegue até **Workbench > Usuários finais** no menu superior.
3. Selecione a guia **Recursos**.

## Inserir uma identidade de usuário {#input-identity}

Para pesquisar avaliações de indicador de recurso para um usuário específico, especifique as seguintes informações no form Bancada:

* **Tipo de ID** — Selecione o tipo de identificador que você está usando. Os tipos suportados incluem email, GUID e ID de visitante. Você também pode inserir um **sinalizador de liberação** diretamente para procurar quais versões foram habilitadas para um usuário com base em seu valor de sinalizador.
* **Valor de ID** — Insira o identificador do usuário. Se você selecionar email como tipo de ID, observe que várias GUIDs podem ser associadas ao mesmo endereço de email. Uma lista suspensa de GUID é fornecida para que você possa alternar entre GUIDs associados.
* **Tipo de origem de autenticação** — selecione se aplicável à sua integração.
* **Variáveis de contexto** — forneça opcionalmente pares de valores-chave de contexto que afetem a avaliação da regra de público-alvo (por exemplo, país, tipo de dispositivo).
* **Equipe e aplicativo** — Selecione a equipe e o aplicativo para os quais deseja buscar sinalizadores de recursos. Sua equipe atual e um de seus aplicativos são pré-selecionados por padrão.

Depois de preencher o formulário, selecione **Buscar Recursos**.

## Interpretar os resultados {#interpret-results}

Os resultados dependem do tipo de ID inserido.

### Pesquisa de email ou GUID {#email-guid-lookup}

Quando você pesquisa um usuário por email ou GUID, duas seções são exibidas nos resultados:

**Sinalizadores de versão**

Esta seção mostra três listas para a equipe e o aplicativo selecionados:

* **Habilitado** — Versões atualmente ativas para este usuário.
* **Desabilitado** — Versões que existem, mas não estão habilitadas para este usuário.
* **Não Utilizado** — Libera bits que não têm liberação anexada a eles.

As versões associadas à equipe e ao aplicativo selecionados no momento aparecem na parte superior de cada lista.

**Sinalizadores e grupos de recursos**

Esta seção lista todos os sinalizadores de recursos da equipe e do aplicativo selecionados que estão habilitados para o usuário no momento. Cada entrada mostra:

* Chave e nome do sinalizador de recurso
* Grupo de recursos (se o sinalizador pertencer a um)
* Variante (se o teste A/B estiver configurado)
* Se o sinalizador é vinculado ao público-alvo

Você também pode selecionar **Mostrar solicitação/resposta** para inspecionar a solicitação e a resposta exata da API que produziu os resultados.

### Email não próprio ou ID não GUID {#non-self-lookup}

Quando o email inserido não for seu ou quando um tipo de ID não GUID for usado, somente a seção **Sinalizadores e grupos de recursos** será exibida.

### Pesquisa de sinalizador de liberação {#release-flag-lookup}

Quando você insere um **sinalizador de liberação** como o tipo de ID, somente a seção **sinalizadores de liberação** é exibida, listando quais versões foram habilitadas e desabilitadas para o usuário associado a esse sinalizador.

## Problemas comuns {#common-issues}

A tabela a seguir descreve problemas comuns e como investigá-los usando a bancada.

| Sintoma | O que verificar |
|---|---|
| O usuário não recebe um sinalizador de recurso que deveria | Verifique a seleção do grupo e do aplicativo. Verifique se a ID do usuário corresponde ao tipo de regra de público-alvo (email, GUID etc.). Confirme se o recurso está no estado **Publicar** ou **Implantação Completa**. |
| O recurso está habilitado para todos os usuários inesperadamente | Confirme se o recurso não tem regras de público-alvo aplicadas ou se a porcentagem está definida como 100%. Verifique se o recurso está no estado **Implantação Completa**. |
| A regra de público-alvo não corresponde | Use o workbench com variáveis de contexto para confirmar que os valores transmitidos no tempo de execução correspondem ao que está configurado na regra de público-alvo. |
| O estado do sinalizador de recurso está correto, mas o usuário ainda vê um comportamento antigo | Verifique o TTL configurado para o aplicativo. O SDK armazena dados de recursos em cache e é atualizado somente no intervalo de pesquisa configurado. |

## Consulte também {#see-also}

* [Obter suporte](get-support.md)
* [Entrar em contato com o suporte](contact-support.md)
