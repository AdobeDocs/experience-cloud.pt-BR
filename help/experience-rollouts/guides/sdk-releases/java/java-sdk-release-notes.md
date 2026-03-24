---
title: Notas de versão do Java SDK
description: Notas de versão do Java SDK de Implantações de experiência, incluindo um changelog de novos recursos, melhorias e correções de erros em todas as versões publicadas.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 2%

---


# Notas de versão do Java SDK {#java-sdk-release-notes}

Esta página lista o histórico de versões do Java SDK de implantações de experiência. Para configuração da integração, consulte o [guia de integração do Java SDK](java-sdk-integration-guide.md).

## Versão 4.0.6 {#v4-0-6}

**Dados do grupo de controle em respostas**

Agora você pode recuperar dados de variante e grupo de controle na resposta do SDK, correspondendo ao comportamento das APIs do recurso REST. Para habilitar, adicione `.includeControlGroup()` ao seu construtor de `FloodgateConfiguration`.

## Versão 4.0.5 {#v4-0-5}

**Melhorias de estabilidade e desempenho**

Pequenas melhorias internas na confiabilidade da atualização do cache e no tratamento de conexões.

## Versão 4.0.4 {#v4-0-4}

**Repetir melhorias na política**

Comportamento de repetição padrão aprimorado em erros de serviço transitórios.

## Versão 4.0.3 {#v4-0-3}

**Correções de erros**

Correções gerais de estabilidade para casos de borda na inicialização assíncrona.

## Versão 4.0.1 (Beta) {#v4-0-1-beta}

**Versão Beta do SDK 4.x**

Introdução ao suporte a cliente DX, configuração de região DX e suporte a AEP (sandbox).

## Versão 3.1.0 {#v3-1-0}

**Suporte a streaming para clientes DX**

Adição do recurso de transmissão baseado em SSE para notificar os clientes da SDK sobre atualizações de sinalizadores em tempo quase real.

## Versão 3.0.x {#v3-0-x}

**Requisito do Java 11 introduzido**

A partir da versão 3.0.0, o SDK exige o JDK 11 ou posterior. As versões principais anteriores são compatíveis com o JDK 8+.

Introdução do suporte público-alvo por referência para clientes DX, permitindo que as definições de público reutilizáveis fossem referenciadas pela ID em entidades de recurso.

## Versão 2.x {#v2-x}

**Suporte a cliente não armazenável em cache (de 0.8)**

Os clientes que não podem ser armazenados em cache podem chamar `getFeature()` em tempo real, em vez de ler a partir do cache do SDK. O SDK continua a pesquisa em segundo plano e alterna para o serviço baseado em cache quando o cliente se torna armazenável em cache.

As melhorias adicionais na versão 2.x incluíram novas opções do construtor (`alwaysCache()`, `neverCache()`, suporte personalizado a cliente e executor HTTP), filtragem de chaves de lançamento e recursos e recuperação de usuários representados.

## Versão 1.x {#v1-x}

Série da versão inicial. JDK 8+ compatível, integração de dependência Maven e recuperação básica de sinalizador de recursos autenticados e anônimos.

## Consulte também {#see-also}

* [Guia de integração do Java SDK](java-sdk-integration-guide.md)
* [Notas de versão do Node.js SDK](../../sdk-releases/nodejs/nodejs-sdk-release-notes.md)
* [SDKs](../../integrate/sdks.md)
