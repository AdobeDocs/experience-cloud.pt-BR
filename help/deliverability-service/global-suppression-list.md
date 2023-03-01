---
title: Lista de supressão global
description: Conheça a lista de supressão global
hide: true
exl-id: 40aef987-52a3-470b-88ca-c716a116bdfc
source-git-commit: b66e2525694c771ebb7ac5190b7259ef5658d81a
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 2%

---

# Lista de supressão global {#global-suppression-list}

A lista de supressão consiste em endereços de email que os clientes desejam excluir de suas entregas, pois o envio para esses contatos pode prejudicar sua reputação de envio e as taxas de entrega. Atualmente, o Adobe mantém uma lista atualizada de endereços de email inválidos conhecidos que comprovadamente prejudicam a reputação de engajamento e mala direta, e garante que os emails não sejam entregues a eles. Essa lista é gerenciada em uma lista de supressão global que é comum em todos os clientes do Adobe. Os endereços e os nomes de domínio contidos na lista de supressão global estão ocultos. Somente o número de recipients excluídos é indicado nos relatórios de delivery.

Agora é possível gerenciar a lista de supressão global por meio de uma interface disponível internamente. Esta lista será mantida somente por consultores de avaliação de entrega. A lista de supressão global pode incluir endereços de email ou de domínio.

## Acessar a lista de supressão global

Para acessar a lista detalhada de domínios e endereços de email excluídos, acesse **[!UICONTROL Lista de supressão global]**.

>[!CAUTION]
>
>As permissões para exibir, exportar e gerenciar a lista de supressão global dependem da lista de distribuição à qual você está atribuído. Saiba mais

Duas guias são exibidas: **[!UICONTROL E-mail]** e **[!UICONTROL Domínio]**.

Os filtros estão disponíveis para ajudá-lo a navegar pela lista.

## Adicionar endereços e domínios

Atualmente, há duas maneiras de adicionar endereços à lista de supressão global:

* Lista com curadoria da equipe de avaliação do delivery.
* Lista fornecida pelo provedor de serviços terceirizado Blackbox.

Você pode adicionar endereços de email ou domínios [um de cada vez](#add-one-address-or-domain)ou [no modo em massa](#upload-csv-file) por meio de um upload de arquivo CSV.

Para fazer isso, selecione a variável **[!UICONTROL Adicionar email ou domínio]** e siga um dos métodos abaixo.

### Adicionar um endereço ou domínio {#add-one-address-or-domain}

1. Selecione o **[!UICONTROL Um por um]** opção.

1. Escolha o tipo de endereço: **[!UICONTROL Endereço de email]** ou **[!UICONTROL Endereço do domínio]**.

1. Insira o endereço de email ou domínio que deseja excluir do envio.

   >[!NOTE]
   >
   >Insira um endereço de email válido (como abc@company.com) ou domínio (como abc.company.com).

1. Especifique um motivo, se necessário.

   >[!NOTE]
   >
   >Todos os caracteres ASCII imprimíveis compreendidos entre 32 e 126 são permitidos neste campo. A lista completa pode ser encontrada em [esta página](https://en.wikipedia.org/wiki/Wikipedia:ASCII#ASCII_printable_characters){target="_blank"} por exemplo.

1. Clique em **[!UICONTROL Enviar]** para confirmar.

### Carregar um arquivo CSV {#upload-csv-file}

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

1. Preencha o modelo CSV com os domínios e/ou endereços de email que deseja adicionar à lista de supressão.

   >[!NOTE]
   >
   >Todos os caracteres ASCII entre 32 e 126 são permitidos na variável **Comentário** coluna. A lista completa pode ser encontrada em [esta página](https://en.wikipedia.org/wiki/Wikipedia:ASCII#ASCII_printable_characters){target="_blank"} por exemplo.

1. Depois de concluído, arraste e solte seu arquivo CSV e clique em **[!UICONTROL Enviar]** para confirmar.

>[!NOTE]
>
>Depois que o upload for concluído, verifique se ele foi bem-sucedido verificando o status na interface. [Saiba como](#recent-uploads)

### Verificar status de uploads recentes {#recent-uploads}

Clique em **[!UICONTROL Uploads recentes]** botão para verificar o status dos arquivos CSV mais recentes carregados.

Os possíveis status são:

* **[!UICONTROL Pending]**: o upload do arquivo está sendo processado.
* **[!UICONTROL Erro]**: o processo de upload de arquivo falhou devido a um problema técnico ou a um erro de formato de arquivo.
* **[!UICONTROL Concluído]**: o processo de upload de arquivo foi concluído com êxito.

Durante o upload, se alguns endereços não estiverem no formato correto, eles não serão adicionados à lista de supressão global.

Nesse caso, quando o upload é concluído, ele é associado a um relatório. Você pode baixá-lo para verificar os erros encontrados.

## Remover endereços

Para remover um endereço da lista de supressão global, use o **[!UICONTROL Excluir]** botão.

>[!CAUTION]
>
>Endereços ou domínios adicionados automaticamente pelo provedor de serviços de terceiros Blackbox não podem ser removidos por consultores por meio da interface. Isso pode ser feito somente por meio de um tíquete de back-end.
