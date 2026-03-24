---
title: Regra de público-alvo com variável de contexto de IP do cliente
description: Saiba como usar a variável de contexto IP do cliente em regras de público-alvo em implantações de experiência do Adobe, incluindo suporte para endereços IP, blocos CIDR e intervalos de rede.
source-git-commit: 3f3f7145b3c58dc721cbeb850e9e8571e3255bb1
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 1%

---


# Regra de público-alvo com variável de contexto de IP do cliente {#clientip-rule}

A variável de contexto `clientip` permite que você direcione usuários com base em seus endereços IP de cliente. Isso é útil para restringir ou ativar recursos com base na rede da qual os usuários estão acessando seu aplicativo — por exemplo, limitando o acesso antecipado a usuários em uma rede corporativa.

## Tipos de entrada compatíveis {#input-types}

A variável de contexto `clientip` dá suporte a três tipos de valores de entrada:

| Tipo de entrada | Descrição | Operadores compatíveis |
|---|---|---|
| **Endereço IP** | Um único endereço IPv4 ou IPv6 | É, Não é igual a, Em |
| **Bloco CIDR** | Um intervalo de endereços IP na notação CIDR (por exemplo, `192.168.1.0/24`) | Is, In, Não é igual a |
| **Intervalo de rede** | Um intervalo de rede nomeado predefinido mantido pela plataforma | Faz parte de |

## Adição de uma regra de IP do cliente {#adding-rule}

1. Abra o sinalizador de recurso, o grupo de recursos ou o grupo de recursos entre equipes no console.
2. Vá para a guia **Público-alvo**.
3. Em **Context**, adicione uma condição usando a variável **clientip**.
4. Selecione o operador e insira o valor (endereço IP, bloco CIDR ou selecione um intervalo de rede predefinido).

## Consulte também {#see-also}

* [Usar contexto nas regras de público](using-context-in-audience-rules.md)
* [Público-alvo em sinalizadores e grupos de recursos](audience-in-feature-flags-and-feature-groups.md)
* [Regras complexas de público](complex-rules.md)
