---
title: Visão geral do arquivo de formatação | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe888fee-1fe9-459f-9d62-35732c19a7f8
caps.latest.revision: 13
ms.openlocfilehash: d418cff70c1197aa3c331eed909f49198da139e9
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363685"
---
# <a name="formatting-file-overview"></a>Visão geral do arquivo de formatação

O formato de exibição para os objetos que são retornados por comandos (cmdlets, funções e scripts) são definidos usando arquivos de formatação (arquivos Format. ps1xml). Vários desses arquivos são fornecidos pelo PowerShell para definir o formato de exibição para os objetos retornados pelos comandos fornecidos pelo PowerShell, como o objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) retornado pelo cmdlet `Get-Process`. No entanto, você também pode criar seus próprios arquivos de formatação personalizados para substituir os formatos de exibição padrão ou pode escrever um arquivo de formatação personalizado para definir a exibição de objetos retornados por seus próprios comandos.

> [!IMPORTANT]
> Os arquivos de formatação não determinam os elementos de um objeto que são retornados para o pipeline. Quando um objeto é retornado para o pipeline, todos os membros desse objeto ficam disponíveis mesmo que alguns não sejam exibidos.

O PowerShell usa os dados nesses arquivos de formatação para determinar o que é exibido e como os dados exibidos são formatados. Os dados exibidos podem incluir as propriedades de um objeto ou o valor de um script. Os scripts serão usados se você quiser exibir algum valor que não esteja disponível diretamente das propriedades de um objeto, como adicionar o valor de duas propriedades de um objeto e, em seguida, exibir a soma como um dado. A formatação dos dados exibidos é feita com a definição de modos de exibição para os objetos que você deseja exibir. Você pode definir uma única exibição para cada objeto, pode definir uma única exibição para vários objetos ou pode definir várias exibições para o mesmo objeto. Não há nenhum limite para o número de exibições que você pode definir.

## <a name="common-features-of-formatting-files"></a>Recursos comuns de formatação de arquivos

Cada arquivo de formatação pode definir os seguintes componentes que podem ser compartilhados entre todas as exibições definidas pelo arquivo:

- Definição de configuração padrão, como se os dados exibidos nas linhas das tabelas serão exibidos na próxima linha se os dados forem maiores do que a largura da coluna. Para obter mais informações sobre essas configurações, consulte [definindo definições de configuração comuns](./defining-common-configuration-features.md).

- Conjuntos de objetos que podem ser exibidos por qualquer uma das exibições do arquivo de formatação. Para obter mais informações sobre esses conjuntos (chamados de *conjuntos de seleção*), consulte [definindo conjuntos de objetos](./defining-selection-sets.md).

- Controles comuns que podem ser usados por todas as exibições do arquivo de formatação. Os controles oferecem um melhor controle sobre como os dados são exibidos. Para obter mais informações sobre controles, consulte [definindo controles personalizados](./creating-custom-controls.md).

## <a name="formatting-views"></a>Exibições de formatação

As exibições de formatação podem exibir objetos em formato de tabela, formato de lista, formato largo e formato personalizado. Para a maior parte, cada definição de formatação é descrita por um conjunto de marcas XML que descrevem a exibição. Cada exibição contém o nome da exibição, os objetos que usam a exibição e os elementos da exibição, como as informações de coluna e linha de uma exibição de tabela.

Exibição de tabela lista as propriedades de um objeto ou um valor de bloco de script em uma ou mais colunas. Cada coluna representa uma única propriedade do objeto ou um valor de script. Você pode definir um modo de exibição de tabela que exibe todas as propriedades de um objeto, um subconjunto das propriedades de um objeto ou uma combinação de propriedades e valores de script. Cada linha da tabela representa um objeto retornado. Criar uma exibição de tabela é muito semelhante ao quando você canaliza um objeto para o cmdlet `Format-Table`. Para obter mais informações sobre essa exibição, consulte [exibição de tabela](./creating-a-table-view.md).

Exibição de lista lista as propriedades de um objeto ou um valor de script em uma única coluna. Cada linha da lista exibe um rótulo opcional ou o nome da propriedade seguido pelo valor da propriedade ou do script. Criar um modo de exibição de lista é muito semelhante a canalizar um objeto para o cmdlet `Format-List`. Para obter mais informações sobre essa exibição, consulte [exibição de lista](./creating-a-list-view.md).

Exibição ampla lista uma única propriedade de um objeto ou um valor de script em uma ou mais colunas. Não há rótulo ou cabeçalho para esta exibição. Criar uma exibição ampla é muito semelhante a canalizar um objeto para o cmdlet `Format-Wide`. Para obter mais informações sobre essa exibição, consulte [Wide View](./creating-a-wide-view.md).

Exibição personalizada exibe uma exibição personalizável de propriedades de objeto ou valores de script que não aderem à estrutura rígida de exibições de tabela, exibições de lista ou exibições amplas. Você pode definir uma exibição personalizada autônoma ou pode definir uma exibição personalizada que é usada por outra exibição, como uma exibição de tabela ou exibição de lista. Criar uma exibição personalizada é muito semelhante a canalizar um objeto para o cmdlet `Format-Custom`. Para obter mais informações sobre essa exibição, consulte [modo de exibição personalizado](./creating-custom-controls.md).

## <a name="components-of-a-view"></a>Componentes de uma exibição

Os exemplos de XML a seguir mostram os componentes XML básicos de uma exibição. Os elementos XML individuais variam de acordo com a exibição que você deseja criar, mas os componentes básicos das exibições são os mesmos.

Para começar, cada exibição tem um elemento `Name` que especifica um nome amigável de usuário que é usado para fazer referência à exibição. um elemento `ViewSelectedBy` que define quais objetos .NET são exibidos pela exibição e um elemento de *controle* que define a exibição.

```xml
<ViewDefinitions>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <ListControl>...</ListControl>
  <View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <WideControl>...</WideControl>
  <View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <CustomControl>...</CustomControl>
  </View>
</ViewDefinitions>

```

Dentro do elemento Control, você pode definir um ou mais elementos *entry* . Se você usar várias definições, deverá especificar quais objetos .NET usam cada definição. Normalmente, apenas uma entrada, com apenas uma definição, é necessária para cada controle.

```xml
<ListControl>
  <ListEntries>
    <ListEntry>
      <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
    <ListEntry>
        <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
    <ListEntry>
        <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
  </ListEntries>
</ListControl>

```

Dentro de cada elemento de entrada de uma exibição, você especifica os elementos do *Item* que definem as propriedades ou os scripts do .net exibidos por essa exibição.

```xml

<ListItems>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
</ListItems>

```

Conforme mostrado nos exemplos anteriores, o arquivo de formatação pode conter várias exibições, uma exibição pode conter várias definições e cada definição pode conter vários itens.

## <a name="example-of-a-table-view"></a>Exemplo de uma exibição de tabela

O exemplo a seguir mostra as marcas XML usadas para definir um modo de exibição de tabela que contém duas colunas. O elemento [ViewDefinitions](./viewdefinitions-element-format.md) é o elemento contêiner para todas as exibições definidas no arquivo de formatação. O elemento [View](./view-element-format.md) define a tabela, lista, largura ou exibição personalizada específica. Dentro de cada elemento [View](./view-element-format.md) , o elemento [Name](./name-element-for-view-format.md) especifica o nome da exibição, o elemento [ViewSelectedBy](./viewselectedby-element-format.md) define os objetos que usam a exibição e os elementos de controle diferentes (como o elemento `TableControl` mostrado no exemplo a seguir) definem o tipo da exibição.

```xml
<ViewDefinitions>
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

[Criando um modo de exibição de lista](./creating-a-list-view.md)

[Criando uma exibição de tabela](./creating-a-table-view.md)

[Criando uma exibição ampla](./creating-a-wide-view.md)

[Criar controles personalizados](./creating-custom-controls.md)

[Gravando um arquivo de tipos e formatação do PowerShell](./writing-a-powershell-formatting-file.md)
