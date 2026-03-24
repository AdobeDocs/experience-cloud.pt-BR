---
title: Benchmarking SDK
description: Analise os resultados da avaliação de desempenho do Java SDK para implantações da Adobe Experience, incluindo medidas de tempo de resposta em vários números de sinalizadores de recursos em condições de carga típicas.
source-git-commit: 8b8b5db1a28af3a3ac29aecf26482f70eb84c714
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 7%

---


# Benchmarking SDK {#sdk-benchmarking}

O Java SDK das implantações de experiência é testado para fornecer às equipes de integração uma estimativa confiável dos recursos e tempos de resposta que devem ser esperados quando a SDK for executada dentro de sua infraestrutura.

## Ambiente de teste {#test-environment}

A avaliação de desempenho foi executada em um aplicativo Spring Boot com a seguinte configuração fixa:

* **CPU cores:** 8
* **Memória JVM:** 4096 MB

## Suposições de teste {#test-assumptions}

As seguintes condições foram mantidas constantes em todas as execuções de benchmark:

* Sinalizadores de recursos testados: 8 a 128
* Variáveis de contexto por sinalizador de recurso: 2 (tipo `STRING`, comprimento de 36 caracteres)
* Carga média: 15.000 solicitações por minuto (RPM)
* Threads ativos: 100

## Resultados {#results}

A tabela abaixo mostra o tempo de resposta do percentil 99,99 para chamadas `getFeatures()` à medida que o número de sinalizadores de recursos aumenta:

| Número de sinalizadores de recursos | Variáveis de contexto por sinalizador | Tempo de resposta (ms, p99.99) |
|---|---|---|
| 8 | 2 | &lt; 0.5 |
| 16 | 2 | &lt; 0.5 |
| 32 | 2 | &lt; 0.5 |
| 64 | 2 | &lt; 1 |
| 128 | 2 | &lt; 1 |

## Interpretação dos resultados {#interpretation}

Os parâmetros de referência acima representam o desempenho nas condições de ensaio específicas descritas. Como o SDK é executado na infraestrutura de seu aplicativo, os tempos de resposta reais variam com base em fatores específicos de seu ambiente:

* CPU disponível e número de núcleos
* Tamanho do heap de JVM e comportamento da coleta de lixo
* Disponibilidade da thread e alternância de contexto
* Carga atual do sistema no momento da solicitação

Use esses números como uma linha de base de planejamento em vez de metas de desempenho garantidas para seu ambiente de produção.

## Consulte também {#see-also}

* [Guia de integração do Java SDK](java/java-sdk-integration-guide.md)
* [Notas de versão do Java SDK](java/java-sdk-release-notes.md)
* [SDKs](../integrate/sdks.md)
