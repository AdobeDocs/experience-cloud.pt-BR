---
title: Lista de supressão global
description: Descubra a lista de supressão global
hide: true
source-git-commit: a946cfb1027896f6e45aaf88d25ad7114d6b5ac6
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 2%

---

# Lista de supressão global {#global-suppression-list}

Uma lista de supressão consiste em endereços de email que os clientes desejam excluir de seus deliveries, pois o envio para esses contatos pode prejudicar a reputação de envio e as taxas de delivery. Atualmente, o Adobe mantém uma lista atualizada de endereços de email inválidos conhecidos que comprovadamente são prejudiciais ao engajamento e à reputação de endereçamento, e garante que os emails não sejam entregues a eles. Essa lista é gerenciada em uma lista de supressão global comum em todos os clientes do Adobe. Os endereços e os nomes de domínio contidos na lista de supressão global estão ocultos. Somente o número de recipients excluídos é indicado nos relatórios de delivery.

Agora é possível gerenciar a lista de supressão global de uma interface que está disponível internamente. Essa lista será mantida somente por consultores de Deliverability . A lista de supressão global pode incluir emails ou endereços de domínio.

## Acessar a lista de supressão global

Para acessar a lista detalhada de domínios e endereços de email excluídos, acesse **[!UICONTROL Lista global de supressão]**.

>[!CAUTION]
>
>As permissões para visualizar, exportar e gerenciar a lista de supressão global dependem da lista de distribuição à qual você está atribuído. Saiba mais

Duas guias são exibidas: **[!UICONTROL Email]** e **[!UICONTROL Domínio]**.

Os filtros estão disponíveis para ajudar você a navegar pela lista.

## Adicionar endereços e domínios

Atualmente, há duas maneiras de adicionar endereços à lista de supressão global:

* Lista preparada pela equipe de deliverability.
* Lista fornecida pelo Blackbox do provedor de serviços de terceiros.

Você pode adicionar endereços de email ou domínios [uma de cada vez](#add-one-address-or-domain)ou [no modo em massa](#upload-csv-file) por meio de um upload de arquivo CSV.

Para fazer isso, selecione o **[!UICONTROL Adicionar email ou domínio]** , em seguida, siga um dos métodos abaixo.

### Adicionar um endereço ou domínio {#add-one-address-or-domain}

1. Selecione o **[!UICONTROL Um por um]** opção.

1. Escolha o tipo de endereço: **[!UICONTROL Endereço de email]** ou **[!UICONTROL Endereço do domínio]**.

1. Insira o endereço de email ou domínio que deseja excluir do envio.

   >[!NOTE]
   >
   >Certifique-se de inserir um endereço de email válido (como abc@company.com) ou domínio (como abc.company.com).

1. Especifique um motivo, se necessário.

   >[!NOTE]
   >
   >Todos os caracteres de impressão ASCII compreendidos entre 32 e 126 são permitidos neste campo. A lista completa pode ser encontrada em [esta página](https://en.wikipedia.org/wiki/Wikipedia:ASCII#ASCII_printable_characters){target="_blank"} por exemplo.

1. Clique em **[!UICONTROL Enviar]** para confirmar.

### Fazer upload de um arquivo CSV {#upload-csv-file}

1. Selecione o **[!UICONTROL Fazer upload de CSV]** opção.

1. Baixe o modelo CSV a ser usado, que inclui as colunas e o formato abaixo:

   ```
   TYPE,VALUE,COMMENT
   EMAIL,abc@somedomain.com,Comment
   DOMAIN,somedomain.com,Comment
   ```
   >[!CAUTION]
   >
   >Não altere os nomes das colunas no modelo CSV.
   >
   >O tamanho do arquivo não deve exceder 1 MB.

1. Preencha o modelo CSV com os endereços de email e/ou domínios que deseja adicionar à lista de supressão.

   >[!NOTE]
   >
   >Todos os caracteres ASCII compreendidos entre 32 e 126 são permitidos no **Comentário** coluna. A lista completa pode ser encontrada em [esta página](https://en.wikipedia.org/wiki/Wikipedia:ASCII#ASCII_printable_characters){target="_blank"} por exemplo.

1. Depois de concluído, arraste e solte seu arquivo CSV e clique em **[!UICONTROL Enviar]** para confirmar.

>[!NOTE]
>
>Quando o upload estiver concluído, verifique se ele foi bem-sucedido verificando o status na interface. [Saiba como](#recent-uploads)

### Verificar o status de uploads recentes {#recent-uploads}

Clique no botão **[!UICONTROL Uploads recentes]** para verificar o status dos arquivos CSV mais recentes que você carregou.

Os status possíveis são:

* **[!UICONTROL Pending]**: O upload do arquivo está sendo processado.
* **[!UICONTROL Erro]**: O processo de upload do arquivo falhou devido a um problema técnico ou a um erro de formato de arquivo.
* **[!UICONTROL Concluído]**: O processo de upload de arquivo foi concluído com êxito.

Durante o upload, se alguns endereços não estiverem no formato correto, eles não serão adicionados à lista de supressão global.

Nesse caso, quando o upload é concluído, ele é associado a um relatório. Você pode baixá-lo para verificar os erros encontrados.

## Remover endereços

Para remover um endereço da lista de supressão global, use o **[!UICONTROL Excluir]** botão.

>[!CAUTION]
>
>Os endereços ou domínios adicionados automaticamente pelo Blackbox do provedor de serviços de terceiros não podem ser removidos pelos consultores por meio da interface. Isso pode ser feito somente por meio de um tíquete de back-end.

