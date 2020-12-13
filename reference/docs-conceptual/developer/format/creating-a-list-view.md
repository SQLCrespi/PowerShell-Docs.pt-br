---
ms.date: 09/13/2016
ms.topic: reference
title: Criar uma exibição de lista
description: Criar uma exibição de lista
ms.openlocfilehash: c34c4fddc27d4fd016fba37fc465924d693756a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655634"
---
# <a name="creating-a-list-view"></a>Criar uma exibição de lista

Um modo de exibição de lista exibe dados em uma única coluna (em ordem sequencial). Os dados exibidos na lista podem ser o valor de uma propriedade do .NET ou o valor de um script.

## <a name="a-list-view-display"></a>Exibição de uma exibição de lista

A saída a seguir mostra como o Windows PowerShell exibe as propriedades de [System. ServiceProcess. ServiceController? Objetos createplayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) que são retornados pelo cmdlet [Get-Service](/powershell/module/microsoft.powershell.management/get-service) . Neste exemplo, três objetos foram retornados, com cada objeto separado do objeto anterior por uma linha em branco.

```powershell
Get-Service | format-list
```

```output
Name                : AEADIFilters
DisplayName         : Andrea ADI Filters Service
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess

Name                : AeLookupSvc
DisplayName         : Application Experience
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32ShareProcess

Name                : AgereModemAudio
DisplayName         : Agere Modem Call Progress Audio
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess
...
```

## <a name="defining-the-list-view"></a>Definindo o modo de exibição de lista

O XML a seguir mostra o esquema de exibição de lista para exibir várias propriedades do [System. ServiceProcess. ServiceController? Displayproperty = objeto FullName](/dotnet/api/System.ServiceProcess.ServiceController) . Você deve especificar cada propriedade que deseja exibir na exibição de lista.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

Os seguintes elementos XML são usados para definir um modo de exibição de lista:

- O elemento [View](./view-element-format.md) é o elemento pai da exibição de lista. (Esse é o mesmo elemento pai das exibições de controle de tabela, largo e personalizado.)

- O elemento [Name](./name-element-for-view-format.md) especifica o nome da exibição. Esse elemento é necessário para todas as exibições.

- O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define os objetos que usam a exibição. Este elemento é obrigatório.

- O elemento [GroupBy](./groupby-element-for-view-format.md) define quando um novo grupo de objetos é exibido. Um novo grupo é iniciado sempre que o valor de uma propriedade ou script específico é alterado. Esse elemento é opcional.

- O elemento [Controls](./controls-element-for-view-format.md) define os controles personalizados que são definidos pelo modo de exibição de lista. Os controles oferecem uma maneira de especificar como os dados são exibidos. Esse elemento é opcional. Uma exibição pode definir seus próprios controles personalizados ou pode usar controles comuns que podem ser usados por qualquer exibição no arquivo de formatação. Para obter mais informações sobre controles personalizados, consulte [criando controles personalizados](./creating-custom-controls.md).

- O elemento [ListControl](./listcontrol-element-format.md) define o que é exibido na exibição e como ele é formatado. Semelhante a todas as outras exibições, um modo de exibição de lista pode exibir os valores de propriedades de objeto ou valores gerados pelo script.

Para obter um exemplo de um arquivo de formatação completo que define uma exibição de lista simples, consulte [modo de exibição de lista (básico)](./list-view-basic.md).

## <a name="providing-definitions-for-your-list-view"></a>Fornecendo definições para o modo de exibição de lista

As exibições de lista podem fornecer uma ou mais definições usando os elementos filho do elemento [ListControl](./listcontrol-element-format.md) . Normalmente, uma exibição terá apenas uma definição. No exemplo a seguir, a exibição fornece uma única definição que exibe várias propriedades do [System. Diagnostics. Process? Displayproperty = objeto FullName](/dotnet/api/System.Diagnostics.Process) . Um modo de exibição de lista pode exibir o valor de uma propriedade ou o valor de um script (não mostrado no exemplo).

```xml
<ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>

```

Os seguintes elementos XML podem ser usados para fornecer definições para uma exibição de lista:

- O elemento [ListControl](./listcontrol-element-format.md) e seus elementos filho definem o que é exibido na exibição.

- O elemento [ListEntries](./listentries-element-for-listcontrol-format.md) fornece as definições da exibição. Na maioria dos casos, uma exibição terá apenas uma definição. Este elemento é obrigatório.

- O elemento [ListEntry](./listentry-element-for-listcontrol-format.md) fornece uma definição da exibição. Pelo menos um [ListEntry](./listentry-element-for-listcontrol-format.md) é necessário; no entanto, não há nenhum limite máximo para o número de elementos que você pode adicionar. Na maioria dos casos, uma exibição terá apenas uma definição.

- O elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) especifica os objetos que são exibidos por uma definição específica. Esse elemento é opcional e só é necessário quando você define vários elementos [ListEntry](./listentry-element-for-listcontrol-format.md) que exibem objetos diferentes.

- O elemento [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) especifica as propriedades e os scripts cujos valores são exibidos nas linhas da exibição de lista.

- O elemento [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) especifica uma propriedade ou um script cujo valor é exibido em uma linha da exibição de lista. Um modo de exibição de lista deve especificar pelo menos uma propriedade ou script. Não há nenhum limite máximo para o número de linhas que podem ser especificadas.

- O elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) especifica a propriedade cujo valor é exibido na linha. Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.

- O elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) especifica o script cujo valor é exibido na linha. Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.

- O elemento [Label](./label-element-for-listitem-for-listcontrol-format.md) especifica o rótulo que é exibido à esquerda da propriedade ou do valor do script na linha. Esse elemento é opcional. Se um rótulo não for especificado, o nome da propriedade ou do script será exibido. Para obter um exemplo completo, consulte [exibição de lista (rótulos)](./list-view-labels.md).

- O elemento [ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) especifica uma condição que deve existir para que a linha seja exibida. Para obter mais informações sobre como adicionar condições ao modo de exibição de lista, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md). Esse elemento é opcional.

- O elemento [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) especifica um padrão que é usado para exibir o valor da propriedade ou do script. Esse elemento é opcional.

Para obter um exemplo de um arquivo de formatação completo que define uma exibição de lista simples, consulte [modo de exibição de lista (básico)](./list-view-basic.md).

## <a name="defining-the-objects-that-use-the-list-view"></a>Definindo os objetos que usam o modo de exibição de lista

Há duas maneiras de definir quais objetos .NET usam o modo de exibição de lista. Você pode usar o elemento [ViewSelectedBy](./viewselectedby-element-format.md) para definir os objetos que podem ser exibidos por todas as definições da exibição ou pode usar o elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) para definir quais objetos são exibidos por uma definição específica da exibição. Na maioria dos casos, uma exibição tem apenas uma definição, portanto, os objetos são normalmente definidos pelo elemento [ViewSelectedBy](./viewselectedby-element-format.md) .

O exemplo a seguir mostra como definir os objetos que são exibidos pelo modo de exibição de lista usando os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [TypeName](./typename-element-for-viewselectedby-format.md) . Não há nenhum limite para o número de elementos [TypeName](./typename-element-for-viewselectedby-format.md) que você pode especificar, e sua ordem não é significativa.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pelo modo de exibição de lista:

- O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição de lista.

- O elemento [TypeName](./typename-element-for-viewselectedby-format.md) especifica o objeto .NET que é exibido pela exibição. O nome do tipo .NET totalmente qualificado é necessário. Você deve especificar pelo menos um tipo ou seleção definida para a exibição, mas não há um número máximo de elementos que possam ser especificados.

Para obter um exemplo de um arquivo de formatação completo, consulte [exibição de lista (básico)](./list-view-basic.md).

O exemplo a seguir usa os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) . Use conjuntos de seleção em que você tenha um conjunto de objetos relacionado que são exibidos usando várias exibições, como quando você define uma exibição de lista e uma exibição de tabela para os mesmos objetos. Para obter mais informações sobre como criar um conjunto de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pelo modo de exibição de lista:

- O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição de lista.

- O elemento [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) especifica um conjunto de objetos que podem ser exibidos pela exibição. Você deve especificar pelo menos um conjunto de seleção ou tipo para a exibição, mas não há um número máximo de elementos que possam ser especificados.

O exemplo a seguir mostra como definir os objetos exibidos por uma definição específica da exibição de lista usando o elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) . Usando esse elemento, você pode especificar o nome do tipo .NET do objeto, um conjunto de objetos de seleção ou uma condição de seleção que especifica quando a definição é usada. Para obter mais informações sobre como criar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</ListEntry>
```

Os seguintes elementos XML podem ser usados para especificar os objetos que são usados por uma definição específica da exibição de lista:

- O elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) define quais objetos são exibidos pela definição.

- O elemento [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) especifica o objeto .NET que é exibido pela definição. Ao usar esse elemento, o nome do tipo .NET totalmente qualificado é necessário. Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.

- O elemento [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (não mostrado) especifica um conjunto de objetos que podem ser exibidos por essa definição. Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.

- O elemento [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (não mostrado) especifica uma condição que deve existir para que essa definição seja usada. Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados. Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

## <a name="displaying-groups-of-objects-in-a-list-view"></a>Exibindo grupos de objetos em um modo de exibição de lista

Você pode separar os objetos que são exibidos pelo modo de exibição de lista em grupos. Isso não significa que você defina um grupo, somente se o Windows PowerShell iniciar um novo grupo sempre que o valor de uma propriedade ou script específico for alterado. No exemplo a seguir, um novo grupo é iniciado sempre que o valor da propriedade [System. ServiceProcess. ServiceController. ServiceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) é alterado.

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Os seguintes elementos XML são usados para definir quando um grupo é iniciado:

- O elemento [GroupBy](./groupby-element-for-view-format.md) define a propriedade ou o script que inicia o novo grupo e define como o grupo é exibido.

- O elemento [PropertyName](./propertyname-element-for-groupby-format.md) especifica a propriedade que inicia um novo grupo sempre que seu valor é alterado. Você deve especificar uma propriedade ou um script para iniciar o grupo, mas não pode especificar ambos.

- O elemento [scriptblock](./scriptblock-element-for-groupby-format.md) especifica o script que inicia um novo grupo sempre que seu valor é alterado. Você deve especificar um script ou uma propriedade para iniciar o grupo, mas não pode especificar ambos.

- O elemento [Label](./label-element-for-groupby-format.md) define um rótulo que é exibido no início de cada grupo. Além do texto especificado por esse elemento, o Windows PowerShell exibe o valor que disparou o novo grupo e adiciona uma linha em branco antes e depois do rótulo. Esse elemento é opcional.

- O elemento [CustomControl](./customcontrol-element-for-groupby-format.md) define um controle que é usado para exibir os dados. Esse elemento é opcional.

- O elemento [CustomControlName](./customcontrolname-element-for-groupby-format.md) especifica um controle comum ou de exibição que é usado para exibir os dados. Esse elemento é opcional.

Para obter um exemplo de um arquivo de formatação completo que define grupos, consulte [modo de exibição de lista (GroupBy)](./list-view-groupby.md).

## <a name="using-format-strings"></a>Usando cadeias de caracteres de formato

As cadeias de caracteres de formatação podem ser adicionadas a uma exibição para definir ainda mais como os dados são exibidos. O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

Os seguintes elementos XML podem ser usados para especificar um padrão de formato:

- O elemento [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) especifica os dados que são exibidos pela exibição.

- O elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) especifica a propriedade cujo valor é exibido pela exibição. Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.

- O elemento [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição.

- O elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (não mostrado) especifica o script cujo valor é exibido pela exibição. Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.

No exemplo a seguir, o `ToString` método é chamado para formatar o valor do script. Os scripts podem chamar qualquer método de um objeto. Portanto, se um objeto tiver um método, como `ToString` , que tem parâmetros de formatação, o script poderá chamar esse método para formatar o valor de saída do script.

```xml
<ListItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

O elemento XML a seguir pode ser usado para chamar o `ToString` método:

- O elemento [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) especifica os dados que são exibidos pela exibição.

- O elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (não mostrado) especifica o script cujo valor é exibido pela exibição. Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md)
