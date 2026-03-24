---
title: Liberar fluxo de trabalho de ponta a ponta
description: Saiba mais sobre o fluxo de trabalho completo para gerenciar uma versão coordenada em implantações de experiência do Adobe, desde a definição de sinalizadores de recursos até a ativação.
source-git-commit: d311efb995b20ffc17370d68d57dd84a8605896c
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 1%

---


# Liberar fluxo de trabalho de ponta a ponta {#release-workflow}

Esta página descreve a sequência completa de atividades envolvidas em uma versão coordenada gerenciada por um Gerenciador de versões.

## &#x200B;1. Definir sinalizadores de recursos por aplicativo {#define-flags}

Cada equipe de produtos atribui um **Proprietário da versão do produto** que faz logon no console Implantações de Experiência e cria sinalizadores de recursos para os aplicativos que possui. A equipe de produtos implementa a lógica condicional em seu código, colocando recursos por trás desses sinalizadores.

## &#x200B;2. Criar a versão {#create-release}

A criação de uma nova versão requer uma solicitação de suporte, mas não é totalmente automatizada. Entre em contato com o suporte de Implantações de experiência para criar a versão. Forneça o nome da versão, a equipe proprietária, o ambiente de destino, o objetivo, os aplicativos participantes e a duração esperada.

Quando a versão for confirmada, o Gerenciador de versão abrirá o console e concluirá a configuração da versão.

## &#x200B;3. Adicionar sinalizadores de recursos à versão {#add-flags}

Para cada aplicativo adicionado à versão, o Proprietário da versão do produto do aplicativo faz logon e adiciona os sinalizadores de recursos relevantes à versão. Esses sinalizadores representam os recursos que entrarão em funcionamento com a versão.

## &#x200B;4. Configurar o público {#configure-audience}

O Release Manager seleciona o público-alvo para a versão — por exemplo, 1% dos usuários em um país específico, todos os usuários com um domínio de email específico ou uma lista de IDs de usuário específicas. Depois de configurado, o Gerenciador de versão salva e publica a versão, o que a envia em tempo real para o público-alvo especificado.

## &#x200B;5. Expandir e gerenciar a implantação {#expand}

Depois que a versão for ativada, o Release Manager poderá ajustar as regras de público-alvo para expandir a implantação gradualmente, monitorar problemas e usar os controles de estado de lançamento para gerenciar o ciclo de vida. Consulte [Estados de versão](release-states.md) para obter detalhes.

## Pontos principais {#key-points}

* Todos os aplicativos participantes implantam seus códigos na produção independentemente por trás dos sinalizadores de recursos — não é necessário um tempo de implantação coordenado.
* A versão é o ponto único de controle que ativa todos os sinalizadores entre grupos simultaneamente.
* O direcionamento de público-alvo para versões do é baseado em atributos de token de autenticação (país, email, ID de usuário, porcentagem).

## Consulte também {#see-also}

* [Solicitar uma versão](request-a-release.md)
* [Atualizar regras de lançamento de público-alvo](update-release-audience-rules.md)
* [Estados de lançamento](release-states.md)
