---
title: Perguntas frequentes sobre gerenciamento de versão
description: Encontre respostas para perguntas comuns sobre o gerenciamento de versões do nas Implantações de experiência do Adobe.
exl-id: 802b99bd-85ee-4f4d-afca-88d1297f8782
source-git-commit: 4a3133f014a9bb9d6ed26eb9d9f763db79ce63b3
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 1%

---

# Perguntas frequentes sobre gerenciamento de versão {#release-management-faqs}

## Como faço para solicitar uma versão? {#request-release}

Entre em contato com o suporte de Implantações de experiência para solicitar uma versão. Forneça o nome da sua equipe, os detalhes do aplicativo, o público-alvo e a linha do tempo de implantação desejada.

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

É possível combinar várias regras usando a lógica AND/OR, incluindo condições aninhadas.

## Como adicionar um aplicativo a uma versão? {#onboard-application}

Depois que a versão for criada, abra-a no console e adicione seu aplicativo à configuração de versão. O Proprietário da versão do produto de cada aplicativo pode então adicionar os sinalizadores de recursos relevantes.

## Um recurso não está sendo retornado para um usuário que deve se qualificar. Como solucionar problemas? {#troubleshoot}

Siga estas etapas para depurar:

1. **Verificar o estado da versão.** A versão deve estar no estado **Publicado** ou **Implantação completa** para atender aos recursos.
2. **Verifique o sinalizador do aplicativo e do recurso.** Verifique se o sinalizador de recurso foi criado para o aplicativo correto e se o aplicativo está associado à versão correta.
3. **Verifique se o sinalizador de recurso está habilitado.** Um sinalizador desativado não será distribuído, mesmo se a versão estiver ativa.
4. **Revise os critérios de público-alvo.** Confirme se o usuário atende a todas as condições definidas nas regras de público-alvo. Verifique novamente os critérios da versão específica à qual o recurso está associado.

## Consulte também {#see-also}

* [Entrar em contato com o suporte](../support/contact-support.md)
