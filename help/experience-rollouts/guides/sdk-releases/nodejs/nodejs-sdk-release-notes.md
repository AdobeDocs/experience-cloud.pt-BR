---
title: Notas de versão do Node.js SDK
description: Notas de versão da SDK Node.js de Implantações de experiência, incluindo um changelog de novos recursos, melhorias e correções de erros em todas as versões publicadas.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 1%

---


# Notas de versão do Node.js SDK {#nodejs-sdk-release-notes}

Esta página lista o histórico de versões do SDK Node.js de implantações de experiência. Para configuração de integração, consulte o [guia de integração do Node.js com o SDK](nodejs-sdk-integration-guide.md).

## Versão 1.0.10 {#v1-0-10}

**Correções de erros e melhorias no soquete**

* Correção da exceção `ESOCKETTIMEDOUT` acionada durante atualizações de cache agendadas. Parâmetro `maxSockets` removido de `featureRequestHttpParams` e `ingestAnalyticsHttpParams` em `createInstance()`.
* Correção de um erro em que os clientes armazenáveis em cache eram marcados incorretamente como não armazenáveis em cache após respostas HTTP 304 (Não modificado).
* Removido `isReleaseBitEnabled()` — este método não é mais suportado.
* Saída de registro aprimorada para melhorar o diagnóstico.
* As pastas de teste e cobertura não são mais incluídas no pacote npm publicado.

## Versão 1.0.5 {#v1-0-5}

**Melhorias de estabilidade**

Correções gerais para o tratamento de atualização do cache e casos de borda de inicialização do SDK.

## Versão 1.0.3 {#v1-0-3}

**Versão estável inicial**

Primeira versão de produção do SDK Node.js que oferece suporte à recuperação autenticada, anônima e padrão do sinalizador de recurso de implantação completa.

## Consulte também {#see-also}

* [Guia de integração do SDK Node.js](nodejs-sdk-integration-guide.md)
* [Notas de versão do Java SDK](../../sdk-releases/java/java-sdk-release-notes.md)
* [SDKs](../../integrate/sdks.md)
