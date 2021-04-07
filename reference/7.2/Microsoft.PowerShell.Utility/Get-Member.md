---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-member?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Member
ms.openlocfilehash: 15b546623f5b4287a8b1d30b63ba419d0744ea93
ms.sourcegitcommit: d95a7255f6775b2973aa9473611185a5583881ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "106555177"
---
# Get-Member

## Sinopse
Obtém as propriedades e métodos de objetos.

## Sintaxe

```
Get-Member [-InputObject <PSObject>] [[-Name] <String[]>] [-MemberType <PSMemberTypes>]
 [-View <PSMemberViewTypes>] [-Static] [-Force] [<CommonParameters>]
```

## Descrição

O `Get-Member` cmdlet obtém os membros, as propriedades e os métodos de objetos.

Para especificar o objeto, use o parâmetro **InputObject** ou redirecione um objeto para `Get-Member` . Para obter informações sobre membros estáticos, os membros da classe, não da instância, usam o parâmetro **static** . Para obter apenas determinados tipos de membros, como **NoteProperties**, use o parâmetro **MemberType** .

## Exemplos

### Exemplo 1: obter os membros de objetos de processo

Esse comando exibe as propriedades e os métodos dos objetos de serviço gerados pelo `Get-Service` cmdlet.

Como a `Get-Member` parte do comando não tem parâmetros, ela usa valores padrão para os parâmetros. Por padrão, `Get-Member` o não obtém membros estáticos ou intrínsecos.

```powershell
Get-Service | Get-Member
```

```Output
   TypeName: System.Service.ServiceController#StartupType

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, System.EventArgs)
Close                     Method        void Close()
Continue                  Method        void Continue()
Dispose                   Method        void Dispose(), void IDisposable.Dispose()
Equals                    Method        bool Equals(System.Object obj)
ExecuteCommand            Method        void ExecuteCommand(int command)
GetHashCode               Method        int GetHashCode()
GetLifetimeService        Method        System.Object GetLifetimeService()
GetType                   Method        type GetType()
InitializeLifetimeService Method        System.Object InitializeLifetimeService()
Pause                     Method        void Pause()
Refresh                   Method        void Refresh()
Start                     Method        void Start(), void Start(string[] args)
Stop                      Method        void Stop()
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.ServiceControllerSt...
BinaryPathName            Property      System.String {get;set;}
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DelayedAutoStart          Property      System.Boolean {get;set;}
DependentServices         Property      System.ServiceProcess.ServiceController[] DependentServices {get;}
Description               Property      System.String {get;set;}
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle ServiceHandle {get;}
ServiceName               Property      string ServiceName {get;set;}
ServicesDependedOn        Property      System.ServiceProcess.ServiceController[] ServicesDependedOn {get;}
ServiceType               Property      System.ServiceProcess.ServiceType ServiceType {get;}
Site                      Property      System.ComponentModel.ISite Site {get;set;}
StartType                 Property      System.ServiceProcess.ServiceStartMode StartType {get;}
StartupType               Property      Microsoft.PowerShell.Commands.ServiceStartupType {get;set;}
Status                    Property      System.ServiceProcess.ServiceControllerStatus Status {get;}
UserName                  Property      System.String {get;set;}
ToString                  ScriptMethod  System.Object ToString();
```

### Exemplo 2: obter membros de objetos de serviço

Este exemplo obtém todos os membros (Propriedades e métodos) dos objetos de serviço recuperados pelo `Get-Service` cmdlet, incluindo os membros intrínsecos, como **PSBase**, **PSObject** e os métodos **get_** e **Set_** .

```powershell
Get-Service | Get-Member -Force
(Get-Service Schedule).PSBase
```

O `Get-Member` comando usa o parâmetro **Force** para adicionar os membros intrínsecos e membros gerados pelo compilador dos objetos à exibição. Você pode usar essas propriedades e métodos da mesma maneira que usaria um método adaptado do objeto. O segundo comando mostra como exibir o valor da propriedade PSBase do serviço de agendamento.

### Exemplo 3: obter Membros estendidos de objetos de serviço

Este exemplo obtém os métodos e as propriedades dos objetos de serviço que foram estendidos usando um `Types.ps1xml` arquivo ou o `Add-Member` cmdlet.

```powershell
Get-Service | Get-Member -View Extended
```

```Output
   TypeName: System.Service.ServiceController#StartupType

Name             MemberType    Definition
----             ----------    ----------
Name             AliasProperty Name = ServiceName
RequiredServices AliasProperty RequiredServices = ServicesDependedOn
ToString         ScriptMethod  System.Object ToString();
```

O `Get-Member` comando usa o parâmetro **View** para obter somente os membros estendidos dos objetos de serviço. Nesse caso, o membro estendido é a propriedade **Name** , que é uma propriedade alias da propriedade **ServiceName** .

### Exemplo 4: obter propriedades de script de objetos de log de eventos

Este exemplo obtém as propriedades de script dos objetos de log de eventos no log do sistema em Visualizador de Eventos.

```powershell
Get-WinEvent -LogName System -MaxEvents 1 | Get-Member -MemberType NoteProperty
```

```Output
   TypeName: System.Diagnostics.Eventing.Reader.EventLogRecord

Name    MemberType   Definition
----    ----------   ----------
Message NoteProperty string Message=The machine-default permission settings do not grant Local ...
```

O parâmetro **MemberType** obtém somente objetos com um valor de `NoteProperty` para sua propriedade **MemberType** .

O comando retorna a propriedade **Message** do objeto **EventLogRecord** .

### Exemplo 5: obter objetos com uma propriedade especificada

Este exemplo obtém objetos que têm uma propriedade **MachineName** na saída de uma lista de cmdlets.

A `$list` variável contém uma lista de cmdlets a serem avaliados. A instrução **foreach** invoca cada comando e envia os resultados para `Get-Member` . O parâmetro **Name** limita os resultados de `Get-Member` para membros que têm o nome **MachineName**.

```powershell
$list = "Get-Process", "Get-Service", "Get-Culture", "Get-PSDrive", "Get-ExecutionPolicy"
foreach ($cmdlet in $list) {& $cmdlet | Get-Member -Name MachineName}
```

```Output
   TypeName: System.Diagnostics.Process

Name        MemberType Definition
----        ---------- ----------
MachineName Property   string MachineName {get;}

   TypeName: System.Service.ServiceController#StartupType

Name        MemberType Definition
----        ---------- ----------
MachineName Property   string MachineName {get;set;}
```

Os resultados mostram que apenas objetos de processo e objetos de serviço têm uma propriedade **MachineName** .

### Exemplo 6: obter Membros para uma matriz

Este exemplo demonstra como localizar os membros de uma matriz de objetos. Quando você canaliza e matriz de objetos para `Get-Member` , o cmdlet retorna uma lista de membros para cada tipo de objeto exclusivo na matriz.
Se você passar a matriz usando o parâmetro **InputObject** , a matriz será tratada como um único objeto.

```powershell
$array = @(1,'hello')
$array | Get-Member
```

```Output
   TypeName: System.Int32

Name        MemberType Definition
----        ---------- ----------
CompareTo   Method     int CompareTo(System.Object value), int CompareTo(int value), int ICompar...
Equals      Method     bool Equals(System.Object obj), bool Equals(int obj), bool IEquatable[int...
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
GetTypeCode Method     System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean   Method     bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte      Method     byte IConvertible.ToByte(System.IFormatProvider provider)
...

   TypeName: System.String

Name                 MemberType            Definition
----                 ----------            ----------
Clone                Method                System.Object Clone(), System.Object ICloneable.Clone()
CompareTo            Method                int CompareTo(System.Object value), int CompareTo(str...
Contains             Method                bool Contains(string value), bool Contains(string val...
CopyTo               Method                void CopyTo(int sourceIndex, char[] destination, int ...
EndsWith             Method                bool EndsWith(string value), bool EndsWith(string val...
EnumerateRunes       Method                System.Text.StringRuneEnumerator EnumerateRunes()
Equals               Method                bool Equals(System.Object obj), bool Equals(string va...
GetEnumerator        Method                System.CharEnumerator GetEnumerator(), System.Collect...
GetHashCode          Method                int GetHashCode(), int GetHashCode(System.StringCompa...
...
```

```powershell
Get-Member -InputObject $array
```

```Output
   TypeName: System.Object[]

Name           MemberType            Definition
----           ----------            ----------
Add            Method                int IList.Add(System.Object value)
Address        Method                System.Object&, System.Private.CoreLib, Version=4.0.0.0, Cu...
Clear          Method                void IList.Clear()
Clone          Method                System.Object Clone(), System.Object ICloneable.Clone()
CompareTo      Method                int IStructuralComparable.CompareTo(System.Object other, Sy...
...
```

A `$array` variável contém um objeto **Int32** e um objeto **String** , como visto quando a matriz é canalizada para `Get-Member` . Quando `$array` é passado usando o parâmetro **InputObject** `Get-Member` retorna os membros do tipo **Object []** .

### Exemplo 7: determinar quais propriedades de objeto você pode definir

Este exemplo mostra como determinar quais propriedades de um objeto podem ser alteradas.

```powershell
$File = Get-Item c:\test\textFile.txt
$File.PSObject.Properties | Where-Object isSettable | Select-Object -Property Name
```

```Output
Name
----
PSPath
PSParentPath
PSChildName
PSDrive
PSProvider
PSIsContainer
IsReadOnly
CreationTime
CreationTimeUtc
LastAccessTime
LastAccessTimeUtc
LastWriteTime
LastWriteTimeUtc
Attributes
```

## Parâmetros

### -Force

Adiciona os membros intrínsecos e os **get_** gerados pelo compilador e os métodos de **Set_** à exibição.
A lista a seguir descreve as propriedades que são adicionadas quando você usa o parâmetro **Force** :

- `PSBase`: As propriedades originais do objeto .NET sem extensão ou adaptação. Essas são as propriedades definidas para a classe de objeto.
- `PSAdapted`: As propriedades e os métodos definidos no sistema de tipos estendido do PowerShell.
- `PSExtended`: As propriedades e os métodos que foram adicionados nos `Types.ps1xml` arquivos ou usando o `Add-Member` cmdlet.
- `PSObject`: O adaptador que converte o objeto base em um objeto **PSObject** do PowerShell.
- `PSTypeNames`: Uma lista de tipos de objeto que descrevem o objeto, em ordem de especificidade. Ao Formatar o objeto, o PowerShell pesquisa os tipos nos `Format.ps1xml` arquivos no diretório de instalação do PowerShell ( `$PSHOME` ). Ele usa a definição de formatação para o primeiro tipo que encontrar.

Por padrão, `Get-Member` o obtém essas propriedades em todas as exibições, exceto **base** e **adaptada**, mas não as exibe.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica o objeto cujos membros são recuperados.

Usar o parâmetro **InputObject** não é o mesmo que canalizar um objeto para `Get-Member` . As diferenças são:

- Quando você canaliza uma coleção de objetos para `Get-Member` , `Get-Member` o Obtém os membros dos objetos individuais na coleção, como as propriedades de cada cadeia de caracteres em uma matriz de cadeias de caracteres.
- Quando você usa **InputObject** para enviar uma coleção de objetos, `Get-Member` Obtém os membros da coleção, como as propriedades da matriz em uma matriz de cadeias de caracteres.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MemberType

Especifica o tipo de membro que esse cmdlet obtém. O padrão é `All`.

Os valores aceitáveis para esse parâmetro são:

- `AliasProperty`
- `CodeProperty`
- `Property`
- `NoteProperty`
- `ScriptProperty`
- `Properties`
- `PropertySet`
- `Method`
- `CodeMethod`
- `ScriptMethod`
- `Methods`
- `ParameterizedProperty`
- `MemberSet`
- `Event`
- `Dynamic`
- `All`

Esses valores são definidos como uma enumeração baseada em sinalizador. Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro. Os valores podem ser passados para o parâmetro **MemberType** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores. O cmdlet combinará os valores usando uma operação binary ou. Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.

Para obter informações sobre esses valores, consulte [Enumeração PSMemberTypes](/dotnet/api/system.management.automation.psmembertypes).

Nem todos os objetos têm todos os tipos de membros. Se você especificar um tipo de membro que o objeto não tem, o PowerShell retornará um valor nulo. Para obter tipos relacionados de membros, como todos os membros estendidos, use o parâmetro **View**. Se você usar o parâmetro **MemberType** com os parâmetros **estáticos** ou de **exibição** , `Get-Member` o obterá os membros que pertencem a ambos os conjuntos.

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, Event, Dynamic, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica os nomes de uma ou mais propriedades ou métodos do objeto. `Get-Member` Obtém apenas as propriedades e os métodos especificados.

Se você usar o parâmetro **Name** com o parâmetro **MemberType**, **View** ou **static** , `Get-Member` o obterá somente os membros que atendem aos critérios de todos os parâmetros.

Para obter um membro estático por nome, use o parâmetro **static** com o parâmetro **Name** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Static

Indica que esse cmdlet obtém apenas as propriedades e os métodos estáticos do objeto. Propriedades e métodos estáticos são definidos na classe de objetos, não em qualquer instância específica da classe.

Se você usar o parâmetro **static** com o parâmetro **View** , o parâmetro **View** será ignorado.
Se você usar o parâmetro **static** com o parâmetro **MemberType** , `Get-Member` o obterá somente os membros que pertencem a ambos os conjuntos.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exibição

Especifica que esse cmdlet obtém apenas métodos e propriedades de tipos específicos. Especifique um ou mais valores. O padrão é **adaptado**, **estendido**.

Os valores aceitáveis para esse parâmetro são:

- Base. Obtém somente as propriedades e os métodos originais do objeto .NET (sem extensão ou adaptação).
- Quer. Obtém somente as propriedades e os métodos definidos no sistema de tipos estendido do PowerShell.
- Tensível. Obtém somente as propriedades e os métodos que foram adicionados em um `Types.ps1xml` arquivo ou usando o `Add-Member` cmdlet.
- Todos. Obtém os membros nas exibições de Base, Adaptado e Estendido.

O parâmetro **View** determina os membros recuperados, não apenas a exibição desses membros.

Para obter tipos de membros específicos, como propriedades de script, use o parâmetro **MemberType** . Se você usar os parâmetros **MemberType** e **View** no mesmo comando, `Get-Member` o obterá os membros que pertencem a ambos os conjuntos. Se você usar os parâmetros **estáticos** e de **exibição** no mesmo comando, o parâmetro de **exibição** será ignorado.

```yaml
Type: System.Management.Automation.PSMemberViewTypes
Parameter Sets: (All)
Aliases:
Accepted values: Extended, Adapted, Base, All

Required: False
Position: Named
Default value: Adapted, Extended
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Entradas

### System. Management. Automation. PSObject

Você pode canalizar qualquer objeto para `Get-Member` .

## Saídas

### Microsoft. PowerShell. Commands. MemberDefinition

`Get-Member` Retorna um objeto para cada propriedade ou método que seu obtém.

## Observações

Você pode obter informações sobre um objeto de coleção usando o parâmetro **InputObject** ou canalizando o objeto, precedido por uma vírgula, para `Get-Member` .

Você pode usar a `$This` variável automática em blocos de script que definem os valores de novas propriedades e métodos. A `$This` variável refere-se à instância do objeto ao qual as propriedades e os métodos estão sendo adicionados. Para obter mais informações sobre a `$This` variável, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

Se você passar um objeto que representa um _tipo_, como um literal de tipo, como `[int]` , `Get-Member` retornará informações sobre o `[System.RuntimeType]` tipo. No entanto, quando você usa o parâmetro **estático** , `Get-Member` o retorna os membros estáticos do tipo específico representado pela `System.RuntimeType` instância.

## Links Relacionados

[Add-Member](Add-Member.md)
