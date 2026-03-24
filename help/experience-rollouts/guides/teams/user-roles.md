---
title: Funções do usuário
description: Saiba mais sobre as cinco funções de usuário disponíveis nas implantações de experiência da Adobe e como escolher a função correta para cada membro da equipe.
source-git-commit: 53edbee220e7ef17c4a3ea066743192c1e9681f4
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 2%

---


# Funções do usuário {#user-roles}

As Implantações de experiência fornecem cinco funções. Cada função é projetada para um conjunto específico de responsabilidades. Por padrão, as funções são mutuamente exclusivas — um membro com a função Administrador não tem automaticamente permissões de Proprietário da versão do produto. Atribua várias funções a um membro quando for necessário um acesso mais amplo.

## Funções disponíveis {#roles}

| Função | Responsabilidades |
|---|---|
| **Admin** | Incorpora aplicativos ao console, gerencia membros da equipe e aprova ou rejeita solicitações de acesso. Necessário antes que a equipe possa começar a usar sinalizadores de recursos. |
| **Proprietário da versão do produto** | Cria e atualiza sinalizadores de recursos e grupos de recursos para seus aplicativos. Pode vincular públicos a sinalizadores de recursos para disponibilizar recursos para usuários externos. |
| **Desenvolvedor** | Funciona em um contexto em sandbox para testar recursos por trás de sinalizadores de recursos sem afetar outros usuários. Pode expor um sinalizador de recurso a um público-alvo privado (como uma ID de usuário ou endereço de email específico) no Preparo ou na Produção. |
| **Administrador de recursos** | Cria e gerencia grupos de recursos entre equipes. Use essa função ao coordenar sinalizadores entre aplicativos de propriedade de equipes diferentes. |
| **Gerenciador de versões** | Gerencia versões de várias equipes e vários aplicativos e atualiza as regras de público-alvo que definem quem recebe uma versão. |

## Escolhendo a função certa {#choosing}

Use a orientação a seguir para atribuir funções:

* **Adicionando ou atualizando sinalizadores de recursos para seu aplicativo** → **Proprietário da Versão do Produto**
* **Testando recursos de forma privada sem afetar outros** → **Desenvolvedor**
* **Gerenciamento de grupos de recursos entre equipes** → **Administrador de Recursos**
* **Gerenciamento de versões em várias equipes e aplicativos** → **Gerenciador de Versões**
* **Integração de aplicativos e gerenciamento da associação à equipe** → **Administrador**

>[!NOTE]
>
>Um membro pode ter mais de uma função. Por exemplo, um engenheiro que testa recursos e gerencia os aplicativos da equipe deve ter ambas as funções de **Desenvolvedor** e **Administrador**.

## Erro de permissões {#permissions-error}

Se um membro encontrar um erro de &quot;permissões insuficientes&quot; ao tentar atualizar um recurso ou grupo, ele precisará da função **Proprietário da versão do produto**. Entre em contato com o administrador de equipe para adicionar essa função.

## Consulte também {#see-also}

* [Adicionar membros à sua equipe](add-team-members.md)
* [Gerenciar equipes](manage-teams.md)
