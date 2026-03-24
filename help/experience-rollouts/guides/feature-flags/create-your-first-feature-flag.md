---
title: Criar o primeiro sinalizador de recurso
description: Saiba como criar um sinalizador de recurso em Implantações da Adobe Experience, definir um público-alvo e testá-lo antes de implantar para os usuários.
source-git-commit: ae420329b94b24fcd173734b414aecf1c5fc16ca
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 0%

---


# Criar o primeiro sinalizador de recurso {#create-feature-flag}

## Pré-requisitos {#prerequisites}

Antes de criar um sinalizador de recurso, conclua o seguinte:

* Você tem acesso ao console de Implantações de Experiência — consulte [Fazer logon no console](../console/log-in-to-the-console.md)
* Você pertence a uma equipe — consulte [Gerenciar equipes](../teams/manage-teams.md)
* Seu aplicativo está integrado — consulte [Integrar seu aplicativo](../applications/onboard-your-application.md)
* Você tem a função **Desenvolvedor** ou **Proprietário da Versão do Produto** — consulte [Funções do usuário](../teams/user-roles.md)

## Etapa 1: criar o sinalizador de recurso {#create}

Para criar um novo sinalizador de recurso, siga estas etapas no console:

1. Faça logon no console Implantações de Experiência e navegue até **Recursos e Versões > Sinalizadores de Recursos**.
2. Selecione seu aplicativo no menu suspenso **Aplicativo**.
3. Selecione **Novo Recurso**.
4. Forneça um título, chave, descrição e, opcionalmente, uma tag.
5. Opcionalmente, adicione um critério de público-alvo (consulte Etapa 2).
6. Salve as configurações do sinalizador de recurso.

## Etapa 2: adicionar um critério de público {#audience}

Os critérios de público-alvo controlam quais usuários veem o recurso. Você pode adicionar critérios com base em:

* Atributos de perfil (como país, domínio de email, ID de usuário)
* Variáveis de contexto
* Segmentos de público predefinidos

Para adicionar critérios de público-alvo, vá para a guia **Público-alvo** ao criar ou editar um sinalizador de recurso.

>[!NOTE]
>
>A função de **Desenvolvedor** está em modo seguro. Os desenvolvedores só podem expor um recurso a si mesmos adicionando sua própria ID de usuário em **Público-alvo > Perfil > ID de usuário**. Para expor um recurso a usuários externos, você precisa da função **Proprietário da Versão do Produto**.

## Etapa 3: Calcular tamanho do público {#audience-size}

Depois de adicionar os critérios de público-alvo, selecione **Calcular** na barra inferior para obter uma contagem estimada de usuários que se qualificam para o recurso. Isso ajuda a validar seu direcionamento antes de entrar em funcionamento.

## Etapa 4: programação (opcional) {#schedule}

Você pode agendar um sinalizador de recurso para ativação em uma data e hora futuras. Consulte [Agendamento](schedule.md) para obter detalhes.

## Perguntas frequentes: não consigo adicionar um sinalizador de recurso como Desenvolvedor {#faq}

A função de **Desenvolvedor** está em modo seguro. Os desenvolvedores podem testar os recursos de forma privada adicionando a ID do usuário ao público-alvo. Eles não podem expor recursos do a usuários externos. Use a função **Proprietário da Versão do Produto** para liberar recursos para usuários externos. Entre em contato com o administrador da equipe para atualizar sua função.

## Consulte também {#see-also}

* [Definir um recurso para implantação gradual](set-feature-gradual-rollout.md)
* [Criar um grupo de recursos](create-a-feature-group.md)
* [Funções do usuário](../teams/user-roles.md)
