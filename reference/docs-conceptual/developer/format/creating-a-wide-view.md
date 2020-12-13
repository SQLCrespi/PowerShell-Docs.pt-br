---
ms.date: 09/13/2016
ms.topic: reference
title: Criar uma exibição ampla
description: Criar uma exibição ampla
ms.openlocfilehash: 4230ef91a3612e962b2773b12e8016df6f760eae
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655601"
---
# <a name="creating-a-wide-view"></a>Criar uma exibição ampla

Uma exibição ampla exibe um único valor para cada objeto que é exibido. O valor exibido pode ser o valor de uma propriedade de objeto .NET ou o valor de um script. Por padrão, não há nenhum rótulo ou cabeçalho para essa exibição.

## <a name="a-wide-view-display"></a>Uma exibição ampla

O exemplo a seguir mostra como o Windows PowerShell exibe o objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) que é retornado pelo cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) quando sua saída é canalizada para o cmdlet [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) . (Por padrão, o cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) retorna um modo de exibição de tabela.) Neste exemplo, as duas colunas são usadas para exibir o nome do processo para cada objeto retornado. O nome da Propriedade do objeto não é exibido, somente o valor da propriedade.

```
Get-Process | format-wide
AEADISRV                     agrsmsvc
Ati2evxx                     Ati2evxx
audiodg                      CCC
CcmExec                      communicator
Crypserv                     csrss
csrss                        DevDtct2
DM1Service                   dpupdchk
dwm                          DxStudio
EXCEL                        explorer
GoogleToolbarNotifier        GrooveMonitor
hpqwmiex                     hpservice
Idle                         InoRpc
InoRT                        InoTask
ipoint                       lsass
lsm                          MOM
MSASCui                      notepad
...                          ...

```

## <a name="defining-the-wide-view"></a>Definindo a exibição ampla

O XML a seguir mostra o esquema de exibição ampla para o objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <GroupBy>...</GroupBy>
  <Controls>...</Controls>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

Os seguintes elementos XML são usados para definir uma exibição ampla:

- O elemento [View](./view-element-format.md) é o elemento pai da exibição larga. (Este é o mesmo elemento pai para a tabela, lista e exibições de controle personalizado.)

- O elemento [Name](./name-element-for-view-format.md) especifica o nome da exibição. Esse elemento é necessário para todas as exibições.

- O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define os objetos que usam a exibição. Este elemento é obrigatório.

- O elemento [GroupBy](./groupby-element-for-view-format.md) define quando um novo grupo de objetos é exibido. Um novo grupo é iniciado sempre que o valor de uma propriedade ou script específico é alterado. Esse elemento é opcional.

- Os elementos [Controls](./controls-element-for-view-format.md) definem os controles personalizados que são definidos pela exibição larga. Os controles oferecem uma maneira de especificar como os dados são exibidos. Esse elemento é opcional. Uma exibição pode definir seus próprios controles personalizados ou pode usar controles comuns que podem ser usados por qualquer exibição no arquivo de formatação. Para obter mais informações sobre controles personalizados, consulte [criando controles personalizados](./creating-custom-controls.md).

- O elemento [WideControl](./widecontrol-element-format.md) e seus elementos filho definem o que é exibido na exibição. No exemplo anterior, a exibição foi projetada para exibir a propriedade [System. Diagnostics. Process. ProcessName](/dotnet/api/System.Diagnostics.Process.ProcessName) .

Para obter um exemplo de um arquivo de formatação completo que define uma exibição larga simples, consulte [Wide View (básica)](./wide-view-basic.md).

## <a name="providing-definitions-for-your-wide-view"></a>Fornecendo definições para sua ampla exibição

Exibições amplas podem fornecer uma ou mais definições usando os elementos filho do elemento [WideControl](./widecontrol-element-format.md) . Normalmente, uma exibição terá apenas uma definição. No exemplo a seguir, a exibição fornece uma única definição que exibe o valor da propriedade [System. Diagnostics. Process. ProcessName](/dotnet/api/System.Diagnostics.Process.ProcessName) . Uma exibição ampla pode exibir o valor de uma propriedade ou o valor de um script (não mostrado no exemplo).

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber></ColumnNumber>
  <WideEntries>
    <WideEntry>
      <WideItem>
        <PropertyName>ProcessName</PropertyName>
      </WideItem>
    </WideEntry>
  </WideEntries>
</WideControl>
```

Os seguintes elementos XML podem ser usados para fornecer definições para uma exibição ampla:

- O elemento [WideControl](./widecontrol-element-format.md) e seus elementos filho definem o que é exibido na exibição.

- O elemento [AutoSize](./autosize-element-for-widecontrol-format.md) especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados. Esse elemento é opcional.

- O elemento [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) especifica o número de colunas exibidas na exibição ampla. Esse elemento é opcional.

- O elemento [WideEntries](./wideentries-element-for-widecontrol-format.md) fornece as definições da exibição. Na maioria dos casos, uma exibição terá apenas uma definição. Este elemento é obrigatório.

- O elemento [WideEntry](./wideentry-element-for-widecontrol-format.md) fornece uma definição da exibição. Pelo menos um [WideEntry](./wideentry-element-for-widecontrol-format.md) é necessário; no entanto, não há nenhum limite máximo para o número de elementos que você pode adicionar. Na maioria dos casos, uma exibição terá apenas uma definição.

- O elemento [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) especifica os objetos que são exibidos por uma definição específica. Esse elemento é opcional e só é necessário quando você define vários elementos [WideEntry](./wideentry-element-for-widecontrol-format.md) que exibem objetos diferentes.

- O elemento [WideItem](./wideitem-element-for-widecontrol-format.md) especifica os dados que são exibidos pela exibição. Ao contrário de outros tipos de exibições, um controle amplo pode exibir apenas um item.

- O elemento [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) especifica a propriedade cujo valor é exibido pela exibição. Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.

- O elemento [scriptblock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) especifica o script cujo valor é exibido pela exibição. Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.

- O elemento [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) especifica um padrão que é usado para exibir os dados. Esse elemento é opcional.

Para obter um exemplo de um arquivo de formatação completo que define uma ampla definição de exibição, consulte [Wide View (básica)](./wide-view-basic.md).

## <a name="defining-the-objects-that-use-the-wide-view"></a>Definindo os objetos que usam a exibição ampla

Há duas maneiras de definir quais objetos .NET usam a exibição ampla. Você pode usar o elemento [ViewSelectedBy](./viewselectedby-element-format.md) para definir os objetos que podem ser exibidos por todas as definições da exibição ou pode usar o elemento [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) para definir quais objetos são exibidos por uma definição específica da exibição. Na maioria dos casos, uma exibição tem apenas uma definição, portanto, os objetos são normalmente definidos pelo elemento [ViewSelectedBy](./viewselectedby-element-format.md) .

O exemplo a seguir mostra como definir os objetos que são exibidos pela exibição ampla usando os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [TypeName](./typename-element-for-viewselectedby-format.md) . Não há nenhum limite para o número de elementos [TypeName](./typename-element-for-viewselectedby-format.md) que você pode especificar, e sua ordem não é significativa.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pela exibição ampla:

- O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição larga.

- O elemento [TypeName](./typename-element-for-viewselectedby-format.md) especifica o .NET que é exibido pela exibição. O nome do tipo .NET totalmente qualificado é necessário. Você deve especificar pelo menos um tipo ou seleção definida para a exibição, mas não há um número máximo de elementos que possam ser especificados.

Para obter um exemplo de um arquivo de formatação completo, consulte [Wide View (básica)](./wide-view-basic.md).

O exemplo a seguir usa os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) . Use conjuntos de seleção em que você tenha um conjunto de objetos relacionado que são exibidos usando várias exibições, como quando você define uma exibição ampla e uma exibição de tabela para os mesmos objetos. Para obter mais informações sobre como criar um conjunto de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pela exibição ampla:

- O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição larga.

- O elemento [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) especifica um conjunto de objetos que podem ser exibidos pela exibição. Você deve especificar pelo menos um conjunto de seleção ou tipo para a exibição, mas não há um número máximo de elementos que possam ser especificados.

O exemplo a seguir mostra como definir os objetos exibidos por uma definição específica da exibição ampla usando o elemento [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) . Usando esse elemento, você pode especificar o nome do tipo .NET do objeto, um conjunto de objetos de seleção ou uma condição de seleção que especifica quando a definição é usada. Para obter mais informações sobre como criar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

```xml
<WideEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</WideEntry>
```

Os seguintes elementos XML podem ser usados para especificar os objetos que são usados por uma definição específica da exibição ampla:

- O elemento [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) define quais objetos são exibidos pela definição.

- O elemento [TypeName](./typename-element-for-viewselectedby-format.md) especifica o .NET que é exibido pela definição. Ao usar esse elemento, o nome do tipo .NET totalmente qualificado é necessário. Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.

- O elemento [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) (não mostrado) especifica um conjunto de objetos que podem ser exibidos por essa definição. Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.

- O elemento [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) (não mostrado) especifica uma condição que deve existir para que essa definição seja usada. Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados. Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

## <a name="displaying-groups-of-objects-in-a-wide-view"></a>Exibindo grupos de objetos em uma exibição ampla

Você pode separar os objetos que são exibidos pela exibição ampla em grupos. Isso não significa que você defina um grupo, somente se o Windows PowerShell iniciar um novo grupo sempre que o valor de uma propriedade ou script específico for alterado. No exemplo a seguir, um novo grupo é iniciado sempre que o valor da propriedade [System. ServiceProcess. ServiceController. ServiceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) é alterado.

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

Para obter um exemplo de um arquivo de formatação completo que define grupos, consulte [Wide View (GroupBy)](./wide-view-groupby.md).

## <a name="using-format-strings"></a>Usando cadeias de caracteres de formato

As cadeias de caracteres de formatação podem ser adicionadas a uma exibição ampla para definir ainda mais como os dados são exibidos. O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

Os seguintes elementos XML podem ser usados para especificar um padrão de formato:

- O elemento [WideItem](./wideitem-element-for-widecontrol-format.md) especifica os dados que são exibidos pela exibição.

- O elemento [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) especifica a propriedade cujo valor é exibido pela exibição. Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.

- O elemento [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição

- O elemento [scriptblock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) (não mostrado) especifica o script cujo valor é exibido pela exibição. Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.

No exemplo a seguir, o `ToString` método é chamado para formatar o valor do script. Os scripts podem chamar qualquer método de um objeto. Portanto, se um objeto tiver um método, como `ToString` , que tem parâmetros de formatação, o script poderá chamar esse método para formatar o valor de saída do script.

```xml
<WideItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</WideItem>
```

O elemento XML a seguir pode ser usado para chamar o `ToString` método:

- O elemento [WideItem](./wideitem-element-for-widecontrol-format.md) especifica os dados que são exibidos pela exibição.

- O elemento [scriptblock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) (não mostrado) especifica o script cujo valor é exibido pela exibição. Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.

## <a name="see-also"></a>Consulte Também

[Exibição ampla (Básica)](./wide-view-basic.md)

[Exibição ampla (GroupBy)](./wide-view-groupby.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
