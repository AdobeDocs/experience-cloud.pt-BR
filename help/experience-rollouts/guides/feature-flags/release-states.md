---
title: Estados de lançamento
description: Saiba mais sobre os estados de ciclo de vida de uma versão nas implantações de experiência do Adobe, incluindo o que cada estado significa e quais transições são permitidas.
source-git-commit: ae420329b94b24fcd173734b414aecf1c5fc16ca
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 3%

---


# Estados de lançamento {#release-states}

Um Gerenciador de versão pode atualizar o estado de uma versão diretamente na barra de navegação do console. O estado controla se a versão está ativa, limitada a testes, totalmente implantada ou fechada.

## Estados disponíveis {#states}

| # | Estado | Descrição | Alterações permitidas |
|---|---|---|---|
| 1 | **Rascunho** | A versão é salva no sistema, mas ainda não está ativa. Nenhuma regra de público é aplicada. | Todas as alterações permitidas (lançamento, recursos, público-alvo). |
| 2 | **Salvo** | A versão é registrada e um slot é alocado para ela. A versão ainda não está visível para os usuários. | Todas as alterações são permitidas. |
| 3 | **Publicado** | A versão está disponível para o público-alvo especificado. Os usuários que atendem aos critérios de público-alvo recebem os recursos. | Todas as alterações são permitidas. |
| 4 | **Implantação completa** | A versão está disponível para todos os usuários, independentemente das regras de público-alvo. Todas as regras de público-alvo são removidas. | Alterações de recursos permitidas. O público-alvo não pode ser alterado. |
| 5 | **Linha de base** | Todos os usuários agora têm os recursos desta versão como comportamento padrão. O código condicional pode ser removido. O slot de liberação está liberado. | Nenhuma alteração permitida. |
| 6 | **Anulado** | A versão foi interrompida. Nenhum usuário recebe recursos desta versão. O slot de liberação está liberado. | Nenhuma alteração permitida. |

## Transições permitidas {#transitions}

Nem todas as transições de estado são permitidas. Entender os caminhos permitidos ajuda a planejar a implantação e evitar erros ao gerenciar alterações de estado:

* Uma versão pode avançar pelos estados: Rascunho → Salvo → Publicado → Implantação completa → Incluído na linha de base
* Uma versão pode ser cancelada do rascunho, salva, publicada ou implantação completa
* Depois de incluído na linha de base ou abortado, nenhuma outra alteração será permitida

## Capacidade de liberação {#capacity}

O número de versões ativas (salvas ou publicadas) a qualquer momento é limitado. Para liberar capacidade:

* Mover versões concluídas para **Incluído na Linha de Base** assim que todos os aplicativos participantes removerem seus códigos condicionais.
* **Anular** versões que não tiveram êxito e não continuarão.

Planeje incluir na baseline ou cancelar suas versões em três meses.

## Consulte também {#see-also}

* [Solicitar uma versão](request-a-release.md)
* [Liberar fluxo de trabalho de ponta a ponta](release-workflow-end-to-end.md)
* [Atualizar regras de lançamento de público-alvo](update-release-audience-rules.md)
