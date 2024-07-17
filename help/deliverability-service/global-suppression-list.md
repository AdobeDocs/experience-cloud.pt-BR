---
title: Lista de supressão global
description: Conheça a lista de supressão global
hide: true
exl-id: 40aef987-52a3-470b-88ca-c716a116bdfc
source-git-commit: b66e2525694c771ebb7ac5190b7259ef5658d81a
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 100%

---

# Lista de supressão global {#global-suppression-list}

A lista de supressão consiste em endereços de email que clientes desejam excluir de suas entregas, pois enviar para esses contatos poderia prejudicar sua reputação de envio e as taxas de entrega. Atualmente, a Adobe mantém uma lista atualizada de endereços de email inadequados conhecidos que comprovadamente são prejudiciais ao engajamento e à reputação de envio, e garante que os emails não sejam entregues a eles. Essa lista é gerenciada em uma lista de supressão global comum a todos os clientes da Adobe. Os endereços e os nomes de domínio contidos na lista de supressão global estão ocultos. Somente o número de destinatários excluídos é indicado nos relatórios de entrega.

Agora é possível gerenciar a lista de supressão global a partir de uma interface que está disponível internamente. Essa lista será mantida somente por consultores de capacidade de entrega. A lista de supressão global pode incluir endereços de email ou de domínio.

## Acessar a lista de supressão global

Para acessar a lista detalhada de endereços de email e domínios excluídos, acesse **[!UICONTROL Lista de supressão global]**.

>[!CAUTION]
>
>As permissões para visualizar, exportar e gerenciar a lista de supressão global dependem da lista de distribuição à qual você está atribuído. Saiba mais

Duas guias são exibidas: **[!UICONTROL Email]** e **[!UICONTROL Domínio]**.

Há filtros disponíveis para ajudar na navegação pela lista.

## Adicionar endereços e domínios

Atualmente, há duas maneiras de se adicionar endereços à lista de supressão global:

* Uma lista preparada pela equipe de capacidade de entrega.
* Uma lista fornecida pelo provedor de serviços de terceiros Blackbox.

Você pode adicionar os endereços de email ou domínios [um de cada vez](#add-one-address-or-domain) ou [em massa](#upload-csv-file) por meio do upload de um arquivo CSV.

Para fazer isso, clique no botão **[!UICONTROL Adicionar email ou domínio]** e siga um dos métodos abaixo.

### Adicionar um endereço ou domínio {#add-one-address-or-domain}

1. Selecione a opção **[!UICONTROL Um por um]**.

1. Escolha o tipo de endereço: **[!UICONTROL Endereço de email]** ou **[!UICONTROL Endereço de domínio]**.

1. Insira o endereço de email ou domínio que deseja excluir do envio.

   >[!NOTE]
   >
   >Certifique-se de inserir um endereço de email (como abc@empresa.com) ou de domínio (como abc.empresa.com) válido.

1. Especifique um motivo, se necessário.

   >[!NOTE]
   >
   >Todos os caracteres ASCII imprimíveis compreendidos entre 32 e 126 são permitidos neste campo. Para referência, a lista completa pode ser encontrada [nesta página](https://en.wikipedia.org/wiki/Wikipedia:ASCII#ASCII_printable_characters){target="_blank"}.

1. Clique em **[!UICONTROL Enviar]** para confirmar.

### Fazer upload de um arquivo CSV {#upload-csv-file}

1. Selecione a opção **[!UICONTROL Fazer upload de CSV]**.

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
   >O tamanho do arquivo não pode exceder a 1 MB.

1. Preencha o modelo CSV com os endereços de email e/ou domínios que deseja adicionar à lista de supressão.

   >[!NOTE]
   >
   >Todos os caracteres ASCII compreendidos entre 32 e 126 são permitidos na coluna **Comentário**. Para referência, a lista completa pode ser encontrada [nesta página](https://en.wikipedia.org/wiki/Wikipedia:ASCII#ASCII_printable_characters){target="_blank"}.

1. Após concluído, arraste e solte seu arquivo CSV e clique em **[!UICONTROL Enviar]** para confirmar.

>[!NOTE]
>
>Quando o upload estiver concluído, verifique se ele foi bem-sucedido consultando o status na interface. [Saiba como](#recent-uploads)

### Verificar o status de uploads recentes {#recent-uploads}

Clique no botão **[!UICONTROL Uploads recentes]** para verificar o status dos arquivos CSV mais recentes que você enviou.

Os status possíveis são:

* **[!UICONTROL Pendente]**: o upload do arquivo está sendo processado.
* **[!UICONTROL Erro]**: o processo de upload do arquivo falhou devido a um problema técnico ou a um erro no formato do arquivo.
* **[!UICONTROL Concluído]**: o processo de upload de arquivo foi concluído com sucesso.

Durante o upload, se alguns endereços não estiverem no formato correto, eles não serão adicionados à lista de supressão global.

Nesse caso, quando o upload é concluído, ele é associado a um relatório. Você pode baixá-lo para verificar os erros encontrados.

## Remover endereços

Para remover um endereço da lista de supressão global, use o botão **[!UICONTROL Excluir]**.

>[!CAUTION]
>
>Os endereços ou domínios adicionados automaticamente pelo provedor de serviços de terceiros Blackbox não podem ser removidos pelos consultores por meio da interface. Isso pode ser feito somente por meio de um tíquete no back-end.
