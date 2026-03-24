---
title: Modos de implantações de experiência
description: Saiba mais sobre os dois modos de direcionamento de recursos nas Implantações de experiência do Adobe — direcionamento no nível do usuário e direcionamento no nível da organização — e quando usar cada um.
source-git-commit: bb4541dd7a77edadded2edbc9c71905cf70f2e24
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 3%

---


# Modos de implantações de experiência {#modes}

As Implantações de experiência fornecem dois modos distintos de direcionamento de recursos. Cada uma serve a uma finalidade de controle de versão diferente e foi projetada para um tipo específico de aplicativo ou caso de uso.

>[!TIP]
>
>Escolha o modo com base no que você está controlando: sessões de usuário individuais ou escopo de organização e ambiente.

## Direcionamento no nível do usuário {#user-level}

### Visão geral {#user-level-overview}

O direcionamento no nível do usuário permite a implantação de recursos no nível do usuário individual. Ela suporta o direcionamento preciso de usuários específicos, testadores internos, usuários canários e implantações graduais com base em porcentagem.

Esse modo é mais adequado para aplicativos que precisam variar a experiência com base em quem está conectado.

### Quando usar {#user-level-when}

Use o direcionamento no nível do usuário quando quiser:

* Ativar um recurso para usuários específicos
* Executar experimentos A/B
* Realizar testes canários com um grupo pequeno antes de uma implantação mais ampla
* Implantar gradualmente um recurso por porcentagem de usuários
* Ajuste a experiência com base em atributos de usuário individuais (como domínio de email ou dados de perfil)

### Limitações {#user-level-limitations}

O direcionamento no nível do usuário não foi projetado para os seguintes cenários:

* Não controla recursos no nível de organização, ambiente ou região
* Não destinado a habilitação de recursos em todo o locatário ou marcação de direitos

## Org e direcionamento no nível do ambiente {#org-level}

### Visão geral {#org-level-overview}

O direcionamento no nível da organização permite a implantação de recursos na organização, no ambiente e no escopo da região. Ele controla a disponibilidade de recursos em organizações inteiras ou ambientes de implantação específicos, e não para usuários individuais.

Esse modo foi projetado para distribuição de recursos de nível empresarial e implantações específicas do ambiente.

### Quando usar {#org-level-when}

Use o direcionamento no nível da organização quando desejar:

* Habilitar um recurso para uma organização inteira
* Controlar a disponibilidade de recursos por ambiente (por exemplo, preparo versus produção)
* Executar uma implantação regional
* Recursos de porta com base no nível de direito ou assinatura

### Limitações {#org-level-limitations}

O direcionamento no nível da organização e do ambiente não foi projetado para os seguintes cenários:

* Não suporta direcionamento baseado em perfil de usuário avançado
* Não suporta implantação baseada em porcentagem no nível de usuário individual
* Não destinado a experimentação ou teste A/B

## Comparação {#comparison}

| Dimensão | Direcionamento no nível do usuário | Org e direcionamento no nível do ambiente |
|---|---|---|
| Escopo do controle | Usuário individual | Organização, ambiente, região |
| Base de direcionamento | Perfil do usuário e atributos | Contexto de organização e ambiente |
| Porcentagem de implantação | Sim | Não |
| Teste AB | Sim | Não |
| Compartimentalização corporativa | Não | Sim |

## Escolha do modo correto {#choosing}

* Se a sua pergunta for *&quot;Quais usuários devem ver este recurso?&quot;* → Use **direcionamento no nível do usuário**
* Se a sua pergunta for *&quot;Quais organizações ou ambientes devem ter esse recurso?&quot;* → Use **org e direcionamento no nível do ambiente**
