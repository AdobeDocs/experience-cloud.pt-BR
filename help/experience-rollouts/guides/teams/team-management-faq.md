---
title: Perguntas frequentes sobre gerenciamento de equipe
description: Encontre respostas para perguntas comuns sobre o gerenciamento de equipes, membros e funções em implantações da Adobe Experience.
source-git-commit: 53edbee220e7ef17c4a3ea066743192c1e9681f4
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 1%

---


# Perguntas frequentes sobre gerenciamento de equipe {#team-management-faq}

## Estou tentando adicionar um usuário, mas a pesquisa não retorna nenhum resultado {#user-not-found}

Isso pode ocorrer no ambiente de preparo se o usuário nunca tiver feito logon no preparo antes. Para resolver isso, peça ao usuário que faça logon no console do Stage pelo menos uma vez para criar sua conta no sistema de identidade do Stage. Depois que eles entrarem, tente pesquisá-los novamente.

## Sou um Administrador, mas não posso criar ou editar sinalizadores de recursos {#admin-cannot-edit-flags}

As funções nas Implantações de experiência são mutuamente exclusivas. A função **Administrador** concede permissões de gerenciamento de equipe, mas não inclui as permissões de um **Proprietário da versão do produto**. Para criar e editar sinalizadores de recursos, um membro precisa da função **Proprietário da Versão do Produto**, além da função **Administrador**.

Entre em contato com o administrador da equipe para obter funções adicionais atribuídas. Consulte [Funções de usuário](user-roles.md) para obter um detalhamento completo do que cada função pode fazer.

## Os administradores têm uma hierarquia? Um administrador pode substituir outro? {#admin-hierarchy}

Não. As equipes em implantações de experiência têm uma estrutura plana. Todos os membros com a função **Administrador** têm permissões iguais e podem gerenciar as configurações uns dos outros. Não há fluxo de trabalho hierárquico de aprovação entre administradores.

## Como remover um membro da minha equipe? {#remove-member}

Os membros são removidos por meio do sistema de gerenciamento de acesso. Como Administrador, pesquise o registro de acesso do membro para sua equipe e revogue a função dele. Se não tiver certeza sobre como fazer isso, entre em contato com a equipe de gerenciamento de acesso de sua organização.

## Um membro pode ter mais de uma função? {#multiple-roles}

Sim. Atribua várias funções a um membro quando suas responsabilidades abrangerem mais de uma função. Por exemplo, um membro da equipe que gerencia a equipe e cria sinalizadores de recursos deve ter as funções de **Administrador** e **Proprietário da versão do produto**.

## Consulte também {#see-also}

* [Funções do usuário](user-roles.md)
* [Adicionar membros à sua equipe](add-team-members.md)
* [Gerenciar equipes](manage-teams.md)
