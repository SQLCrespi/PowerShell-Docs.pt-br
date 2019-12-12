---
title: Elemento TableControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1550b068-dfbc-4ae0-9aa1-72c9a680ec59
caps.latest.revision: 15
ms.openlocfilehash: 3942c008e026b0b99db3c77af4a0152b50fffc4e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368195"
---
# <a name="tablecontrol-element-format"></a>Elemento TableControl (formato)

Define um formato de tabela para uma exibição.

Elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format)

## <a name="syntax"></a>Sintaxe

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `TableControl`. Você deve especificar as linhas da tabela. Todos os outros elementos filho são opcionais.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento AutoSize para TableControl (Format)](./autosize-element-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.|
|[Elemento HideTableHeaders para TableControl (Format)](./hidetableheaders-element-format.md)|Elemento opcional.<br /><br /> Indica se o cabeçalho da tabela não é exibido.|
|[Elemento TableHeaders para TableControl (Format)](./tableheaders-element-format.md)|Elemento obrigatório.<br /><br /> Define os rótulos, as larguras e o alinhamento dos dados para as colunas da exibição de tabela.|
|[Elemento TableRowEntries para TableControl (Format)](./tablerowentries-element-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Fornece as definições do modo de exibição de tabela.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição que é usada para exibir os membros de um ou mais objetos.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="example"></a>Exemplo

Este exemplo mostra um elemento `TableControl` que é usado para exibir as propriedades do objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>...</TableHeaders>
    <TableRowEntries>...</TableRowEntries>
  </TableControl>
</View>

```

## <a name="see-also"></a>Consulte Também

[Criando uma exibição de tabela](./creating-a-table-view.md)

[Elemento View (formato)](./view-element-format.md)

[Elemento AutoSize para TableControl (Format)](./autosize-element-for-tablecontrol-format.md)

[Elemento HideTableHeaders (Format)](./hidetableheaders-element-format.md)

[Elemento TableHeaders (Format)](./tableheaders-element-format.md)

[Elemento TableRowEntries (Format)](./tablerowentries-element-for-tablecontrol-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
