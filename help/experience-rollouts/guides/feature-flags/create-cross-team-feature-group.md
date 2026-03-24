---
title: Criar um grupo de recursos entre equipes
description: Saiba como criar um grupo de recursos entre equipes em implantações de experiência do Adobe para coordenar sinalizadores de recursos entre aplicativos de propriedade de equipes diferentes.
source-git-commit: a1ed4582217001ffcf500cd7b634d9959adbe028
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 2%

---


# Criar um grupo de recursos entre equipes {#create-cross-team-feature-group}

## Pré-requisitos {#prerequisites}

Antes de criar um grupo de recursos entre equipes, confirme o seguinte:

* Você tem acesso ao console — consulte [Fazer logon no console](../console/log-in-to-the-console.md)
* Você pertence a uma equipe e seu aplicativo é integrado
* Você tem a função de **Administrador de Recursos** — consulte [Funções de usuário](../teams/user-roles.md)
* Você criou os sinalizadores de recursos para incluir — consulte [Criar seu primeiro sinalizador de recursos](create-your-first-feature-flag.md)

Um grupo de recursos entre equipes permite agrupar sinalizadores de recursos de aplicativos em várias equipes com direcionamento avançado de público-alvo. Ao contrário das versões do, ele é totalmente automatizado e não tem limite de número que você pode criar. Consulte [Versões e grupos de recursos entre equipes](releases-and-cross-team-feature-groups.md) para obter uma comparação.

## Etapa 1: criar o grupo de recursos entre equipes {#create}

Inicie o processo de criação na seção Versões do console:

1. Navegue até **Recursos e versões > Versões** no console.
2. Selecione **Novo Grupo De Recursos (Entre Equipes)**.

## Etapa 2: Detalhes básicos {#basic-details}

Forneça um título, chave, descrição e, opcionalmente, uma tag. Configure as seguintes opções:

* **Porcentagem de implantação** — Defina quanto do público-alvo recebe o recurso.
* **Tipo de implantação** — escolha Manual ou Automatizada. Consulte [implantações automatizadas](../automated-rollouts/automated-rollout-concept.md) para obter detalhes sobre como as implantações automatizadas funcionam.

>[!NOTE]
>
>O teste A/B não é compatível com grupos de recursos entre equipes. Para executar testes A/B, use um [grupo de recursos](create-a-feature-group.md) padrão (os aplicativos devem estar na mesma equipe).

## Etapa 3: Público-alvo {#audience}

Na guia **Público-alvo**, habilite as **Regras de Público-alvo** e configure:

* **Segmentos** — Selecione um segmento de público-alvo predefinido.
* **Filtros adicionais** — Adicione diretamente critérios baseados em perfil ou em contexto.
* **Aplicativos** — Selecione um ou mais aplicativos de sua equipe ou de outras equipes.

>[!IMPORTANT]
>
>Adicionar um aplicativo de outra equipe concede aos Administradores de recursos dessa equipe o direito de adicionar sinalizadores de recursos para seu aplicativo a este grupo de recursos entre equipes. Você não pode adicionar os sinalizadores de recursos a si mesmo.

## Etapa 4: recursos {#features}

Na guia **Recursos**, você verá uma caixa para cada aplicativo incluído:

* Para aplicativos em sua própria equipe, você pode adicionar sinalizadores de recursos diretamente.
* Para aplicativos de outras equipes, essas caixas estão esmaecidas — os Administradores de recursos das respectivas equipes devem adicionar seus sinalizadores.

>[!IMPORTANT]
>
>Um sinalizador de recurso só pode ser distribuído por meio de um método por vez. Adicionar um sinalizador a um grupo de recursos entre equipes remove diretamente qualquer público-alvo ou implantação de porcentagem definida no sinalizador. Os sinalizadores que já estão em outra versão ou grupo de recursos não serão exibidos.

## Etapa 5: programação (opcional) {#schedule}

Você pode agendar a ativação do grupo de recursos entre equipes em uma data e hora futuras. Consulte [Agendamento](schedule.md) para obter detalhes.

## Gerenciamento de estados {#states}

A equipe que cria o grupo de recursos entre equipes é proprietária dele e pode gerenciar seu estado. Os membros do Administrador de recursos da equipe proprietária podem fazer a transição entre estados usando a lista suspensa de estados:

| Estado | Descrição |
|---|---|
| **Salvar** | Salvo e não ativo. Todas as alterações são permitidas. |
| **Publicar** | Ao vivo para o público-alvo configurado. Os administradores de recursos podem continuar atualizando os critérios de público-alvo e a porcentagem de implantação. |
| **Implantação completa** | Disponível para todos os usuários. Não é possível restringir ainda mais o público após este ponto. |
| **Linha de base** | Os recursos agora são o padrão. O grupo de recursos entre equipes está fechado. |
| **Anular** | A implantação foi interrompida. Nenhum usuário recebe recursos deste grupo. |

## Perguntas frequentes {#faqs}

**Há um limite para o número de grupos de recursos entre equipes?**
Não. Ao contrário das versões do, não há limite. Entretanto, arquive ou desative grupos quando não for mais necessário.

**Qual é a diferença entre uma versão e um grupo de recursos entre equipes?**
Consulte [Versões e grupos de recursos entre equipes](releases-and-cross-team-feature-groups.md) para obter uma comparação detalhada.

## Consulte também {#see-also}

* [Versões e grupos de recursos entre equipes](releases-and-cross-team-feature-groups.md)
* [Criar um grupo de recursos](create-a-feature-group.md)
* [Criar uma implantação automatizada](../automated-rollouts/create-automated-rollout.md)
