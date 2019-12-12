---
title: Arquivos de formatação personalizados | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85d27545-8097-4010-9947-6d8b3ce2eac0
caps.latest.revision: 15
ms.openlocfilehash: 71c1c181058c5646c817b90d9832976a78c6c7de
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369825"
---
# <a name="custom-formatting-files"></a>Arquivos de formatação personalizada

O formato de exibição dos objetos retornados por cmdlets, funções e scripts é definido usando arquivos de formatação (arquivos Format. ps1xml). Vários desses arquivos são fornecidos pelo Windows PowerShell para definir o formato de exibição padrão para os objetos retornados pelos cmdlets do Windows PowerShell. No entanto, você também pode criar seus próprios arquivos de formatação personalizados para substituir os formatos de exibição padrão ou para definir a exibição de objetos retornados por seus próprios comandos.

O Windows PowerShell usa os dados nesses arquivos de formatação para determinar o que é exibido e como os dados são formatados. Os dados exibidos podem incluir as propriedades de um objeto ou o valor de um bloco de script.  Blocos de script são usados se você quiser exibir algum valor que não esteja disponível diretamente das propriedades de um objeto. Por exemplo, talvez você queira adicionar o valor de duas propriedades de um objeto e exibir a soma como uma parte separada dos dados. Ao escrever seu próprio arquivo de formatação, você precisará definir *modos* de exibição para os objetos que deseja exibir. Você pode definir uma única exibição para cada objeto, pode definir uma única exibição para vários objetos ou pode definir várias exibições para o mesmo objeto. Não há nenhum limite para o número de exibições que você pode definir.

> [!IMPORTANT]
> Os arquivos de formatação não determinam os elementos de um objeto que são retornados para o pipeline. Quando um objeto é retornado para o pipeline, todos os membros desse objeto estão disponíveis.

## <a name="format-views"></a>Exibições de formato

As exibições de formatação podem exibir objetos em um formato de tabela, um formato de lista, um formato amplo e um formato personalizado. Na maior parte, cada definição de formatação é descrita por um conjunto de marcas XML que descrevem uma exibição. Cada exibição contém o nome da exibição, os objetos que usam a exibição e os elementos da exibição, como as informações de coluna e linha de uma exibição de tabela.

As exibições a seguir estão disponíveis.

Exibição de tabela lista as propriedades de um objeto ou um valor de bloco de script em uma ou mais colunas. Cada coluna representa uma propriedade do objeto ou um valor de bloco de script. Você pode definir um modo de exibição de tabela que exibe todas as propriedades de um objeto, um subconjunto das propriedades de um objeto ou uma combinação de propriedades e valores de bloco de script. Cada linha da tabela representa um objeto retornado. Para obter mais informações sobre essa exibição, consulte [exibição de tabela](../format/creating-a-table-view.md).

A exibição de lista lista as propriedades de um objeto ou um valor de bloco de script em uma única coluna. Cada linha da lista exibe um rótulo opcional ou o nome da propriedade seguido pelo valor da propriedade ou bloco de script. Para obter mais informações sobre essa exibição, consulte [exibição de lista](../format/creating-a-list-view.md).

Exibição ampla lista uma única propriedade de um objeto ou um valor de bloco de script em uma ou mais colunas. Não há rótulo ou cabeçalho para esta exibição. Para obter mais informações sobre essa exibição, consulte [Wide View](../format/creating-a-wide-view.md).

Exibição personalizada exibe uma exibição personalizável de propriedades de objeto ou valores de bloco de script que não aderem à estrutura rígida de exibições de tabela, exibições de lista ou exibições amplas. Você pode definir uma exibição personalizada autônoma ou pode definir uma exibição personalizada que é usada por outra exibição, como uma exibição de tabela ou exibição de lista. Para obter mais informações sobre essa exibição, consulte [modo de exibição personalizado](../format/creating-custom-controls.md).

## <a name="view-xml-elements"></a>Exibir elementos XML

O exemplo a seguir mostra as marcas XML usadas para definir um modo de exibição de tabela que contém duas colunas. O elemento [ViewDefinitions](../format/viewdefinitions-element-format.md) é o elemento contêiner para todas as exibições definidas no arquivo de formatação. O elemento [View](../format/view-element-format.md) define a tabela, lista, largura ou exibição personalizada específica. Dentro de cada exibição, o elemento [Name](../format/name-element-for-view-format.md) especifica o nome da exibição, o elemento [ViewSelectedBy](../format/viewselectedby-element-format.md) define os objetos que usam a exibição e os elementos de controle diferentes (como o elemento `TableControl`) definem o formato da exibição.

```xml
ViewDefinitions
  <View>
    <Name>Name of View</Name>
    <ViewSelectedBy>
      <TypeName>Object to display using this view</TypeName>
      <TypeName>Object to display using this view</TypeName>
    </ViewSelectedBy>
    <TableControl>
      <TableHeaders>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
      </TableHeaders>
      <TableRowEntries>
        <TableRowEntry>
          <TableColumnItems>
            <TableColumnItem>
              <PropertyName>Header for column 1</PropertyName>
            </TableColumnItem>
            <TableColumnItem>
              <PropertyName>Header for column 2</PropertyName>
            </TableColumnItem>
          </TableColumnItems>
        </TableRowEntry>
      </TableRowEntries>
    </TableControl)
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a>Consulte Também

[Exibição de tabela](../format/creating-a-table-view.md)

[Exibição de Lista](../format/creating-a-list-view.md)

[Exibição ampla](../format/creating-a-wide-view.md)

[Exibição personalizada](../format/creating-custom-controls.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
