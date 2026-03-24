---
title: Atualizar regras de lançamento de público-alvo
description: Saiba como configurar e atualizar os critérios de público-alvo para uma versão do nas implantações de experiência do Adobe, incluindo os tipos de regras compatíveis e como combiná-los.
source-git-commit: bb4541dd7a77edadded2edbc9c71905cf70f2e24
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 3%

---


# Atualizar regras de lançamento de público-alvo {#update-release-audience-rules}

## Acessar as configurações do público-alvo {#access}

Para começar a configurar quem recebe sua versão, navegue até as configurações de público-alvo no console:

1. Abra a versão no console Implantações de experiência.
2. Vá para a guia **Público-alvo**.
3. Habilite o botão de alternância ao lado de **Regras de público-alvo**.
4. Selecione se deseja adicionar **regras de inclusão** (quem deve receber a liberação) ou **regras de exclusão** (quem não deve).

## Critérios de público-alvo compatíveis {#criteria}

### Tipo de ID {#id-type}

Direcione usuários com base em seu tipo de conta (por exemplo, contas pessoais ou corporativas).

### País {#country}

Direcione usuários com base em seu país registrado.

### ID de usuário {#user-id}

Direcione usuários específicos por meio de seu identificador de usuário exclusivo (GUID).

### Endereço de email {#email}

Direcione os usuários pelo endereço de email exato. Para adicionar vários endereços de email de uma só vez, selecione **em** no menu suspenso do operador (em vez de **é**) e:

* Insira uma lista de endereços separada por vírgulas na caixa de texto ou
* Carregar um arquivo `.txt` com um endereço por linha, ou
* Carregar um arquivo `.csv` com a lista de endereços

Se a lista for muito grande, divida-a em lotes menores.

### Domínio de email {#email-domain}

Direcione todos os usuários cujo endereço de email pertença a um domínio específico (por exemplo, `yourcompany.com`).

### IP do cliente {#client-ip}

Direcione usuários com base no endereço IP do cliente.

### Porcentagem {#percentage}

Direcionar uma porcentagem aleatória de todos os usuários, incluindo usuários não autenticados.

### Porcentagem (somente autenticado) {#percentage-auth}

Direcione uma porcentagem aleatória de usuários autenticados somente. Os usuários não autenticados são excluídos.

## Combinação de várias regras {#combining-rules}

É possível combinar vários critérios de público-alvo usando a lógica E/OU.

**Exemplos:**

* Para direcionar somente contas corporativas de um domínio específico, combine a regra **Tipo de ID** com a regra **Domínio de email** usando AND.
* Para direcionar 10% dos usuários de um país específico, combine a regra **País** com a regra **Porcentagem**.

Use os ícones **+/-** para adicionar ou remover condições. Para duplicar uma condição, selecione o ícone de duplicação ao lado de uma regra existente. Para uma lógica aninhada complexa, habilite a **Lógica aninhada** e insira uma expressão válida na caixa de texto.

## Consulte também {#see-also}

* [Solicitar uma versão](request-a-release.md)
* [Liberar fluxo de trabalho de ponta a ponta](release-workflow-end-to-end.md)
* [Estados de lançamento](release-states.md)
