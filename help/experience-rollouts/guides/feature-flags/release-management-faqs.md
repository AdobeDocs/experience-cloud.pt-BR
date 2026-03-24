---
title: Perguntas frequentes sobre gerenciamento de versão
description: Encontre respostas para perguntas comuns sobre o gerenciamento de versões do nas Implantações de experiência do Adobe.
source-git-commit: d311efb995b20ffc17370d68d57dd84a8605896c
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 1%

---


# Perguntas frequentes sobre gerenciamento de versão {#release-management-faqs}

## Como faço para solicitar uma versão? {#request-release}

Consulte [Solicitar uma versão](request-a-release.md) para obter o processo completo e as informações que você precisa fornecer.

## Quais critérios de público-alvo são compatíveis com as versões do? {#audience-criteria}

As versões são compatíveis com as seguintes regras de público-alvo:

* Tipo de ID (tipo de conta)
* País
* ID de usuário (GUID)
* Endereço de email (lista individual ou em massa)
* Domínio de email
* IP do cliente
* Porcentagem (todos os usuários)
* Porcentagem (somente usuários autenticados)

É possível combinar várias regras usando a lógica AND/OR, incluindo condições aninhadas. Consulte [Atualizar regras de público-alvo da versão](update-release-audience-rules.md) para obter instruções de configuração passo a passo.

## Como adicionar um aplicativo a uma versão? {#onboard-application}

Depois que a versão for criada, abra-a no console e adicione seu aplicativo à configuração de versão. O Proprietário da versão do produto de cada aplicativo pode então adicionar os sinalizadores de recursos relevantes. Consulte [Fluxo de trabalho de versão de ponta a ponta](release-workflow-end-to-end.md) para obter a sequência completa.

## Um recurso não está sendo retornado para um usuário que deve se qualificar. Como solucionar problemas? {#troubleshoot}

Siga estas etapas para depurar:

1. **Verificar o estado da versão.** A versão deve estar no estado **Publicado** ou **Implantação completa** para atender aos recursos. Consulte [Estados de versão](release-states.md).
2. **Verifique o sinalizador do aplicativo e do recurso.** Verifique se o sinalizador de recurso foi criado para o aplicativo correto e se o aplicativo está associado à versão correta.
3. **Verifique se o sinalizador de recurso está habilitado.** Um sinalizador desativado não será distribuído, mesmo se a versão estiver ativa.
4. **Revise os critérios de público-alvo.** Confirme se o usuário atende a todas as condições definidas nas regras de público-alvo. Verifique novamente os critérios da versão específica à qual o recurso está associado.

## Consulte também {#see-also}

* [Solicitar uma versão](request-a-release.md)
* [Atualizar regras de lançamento de público-alvo](update-release-audience-rules.md)
* [Estados de lançamento](release-states.md)
* [Liberar fluxo de trabalho de ponta a ponta](release-workflow-end-to-end.md)
