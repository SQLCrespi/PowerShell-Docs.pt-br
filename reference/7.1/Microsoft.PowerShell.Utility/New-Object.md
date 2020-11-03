---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-object?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Object
ms.openlocfilehash: 3c34022c84c26ee0d8395fc589e8d1da957979b1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194683"
---
# New-Object

## SINOPSE
Cria uma instância de um objeto Microsoft .NET Framework ou COM.

## SYNTAX

### NET (padrão)

```
New-Object [-TypeName] <String> [[-ArgumentList] <Object[]>] [-Property <IDictionary>] [<CommonParameters>]
```

### Interfaces

```
New-Object [-ComObject] <String> [-Strict] [-Property <IDictionary>] [<CommonParameters>]
```

## DESCRIPTION

O `New-Object` cmdlet cria uma instância de um objeto .NET Framework ou com.

Você pode especificar o tipo de uma classe do .NET Framework ou um ProgID de um objeto COM. Por padrão, você digita o nome totalmente qualificado de uma classe do .NET Framework e o cmdlet retorna uma referência a uma instância dessa classe. Para criar uma instância de um objeto COM, use o parâmetro **ComObject** e especifique o ProgID do objeto como seu valor.

## EXEMPLOS

### Exemplo 1: criar um objeto System. Version

Este exemplo cria um objeto **System. Version** usando a cadeia de caracteres "1.2.3.4" como o construtor.

```powershell
New-Object -TypeName System.Version -ArgumentList "1.2.3.4"
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
1      2      3      4
```

### Exemplo 2: criar um objeto COM do Internet Explorer

Este exemplo cria duas instâncias do objeto COM que representa o aplicativo do Internet Explorer. A primeira instância usa a tabela de hash de parâmetro de **Propriedade** para chamar o método **Navigate2** e definir a propriedade **Visible** do objeto como `$True` para tornar o aplicativo visível.
A segunda instância obtém os mesmos resultados com comandos individuais.

```powershell
$IE1 = New-Object -COMObject InternetExplorer.Application -Property @{Navigate2="www.microsoft.com"; Visible = $True}

# The following command gets the same results as the example above.
$IE2 = New-Object -COMObject InternetExplorer.Application`
$IE2.Navigate2("www.microsoft.com")`
$IE2.Visible = $True`
```

### Exemplo 3: usar o parâmetro estrito para gerar um erro de não finalização

Este exemplo demonstra que a adição do parâmetro **estrito** faz com que o `New-Object` cmdlet gere um erro de não finalização quando o objeto com usa um assembly de interoperabilidade.

```powershell
$A = New-Object -COMObject Word.Application -Strict -Property @{Visible = $True}
```

```Output
New-Object : The object written to the pipeline is an instance of the type
"Microsoft.Office.Interop.Word.ApplicationClass" from the component's primary interop assembly. If
this type exposes different members than the IDispatch members, scripts written to work with this
object might not work if the primary interop assembly is not installed.

At line:1 char:14
+ $A = New-Object  <<<< -COM Word.Application -Strict; $a.visible=$true
```

### Exemplo 4: criar um objeto COM para gerenciar o Windows Desktop

Este exemplo mostra como criar e usar um objeto COM para gerenciar sua área de trabalho do Windows.

O primeiro comando usa o parâmetro **ComObject** do `New-Object` cmdlet para criar um objeto com com o **shell. Application** ProgID. Ele armazena o objeto resultante na `$ObjShell` variável. O segundo comando canaliza a `$ObjShell` variável para o `Get-Member` cmdlet, que exibe as propriedades e os métodos do objeto com. Entre os métodos está o método **ToggleDesktop** . O terceiro comando chama o método **ToggleDesktop** do objeto para minimizar as janelas abertas na sua área de trabalho.

```powershell
$Objshell = New-Object -COMObject "Shell.Application"
$objshell | Get-Member
$objshell.ToggleDesktop()
```

```Output
   TypeName: System.__ComObject#{866738b9-6cf2-4de8-8767-f794ebe74f4e}

Name                 MemberType Definition
----                 ---------- ----------
AddToRecent          Method     void AddToRecent (Variant, string)
BrowseForFolder      Method     Folder BrowseForFolder (int, string, int, Variant)
CanStartStopService  Method     Variant CanStartStopService (string)
CascadeWindows       Method     void CascadeWindows ()
ControlPanelItem     Method     void ControlPanelItem (string)
EjectPC              Method     void EjectPC ()
Explore              Method     void Explore (Variant)
ExplorerPolicy       Method     Variant ExplorerPolicy (string)
FileRun              Method     void FileRun ()
FindComputer         Method     void FindComputer ()
FindFiles            Method     void FindFiles ()
FindPrinter          Method     void FindPrinter (string, string, string)
GetSetting           Method     bool GetSetting (int)
GetSystemInformation Method     Variant GetSystemInformation (string)
Help                 Method     void Help ()
IsRestricted         Method     int IsRestricted (string, string)
IsServiceRunning     Method     Variant IsServiceRunning (string)
MinimizeAll          Method     void MinimizeAll ()
NameSpace            Method     Folder NameSpace (Variant)
Open                 Method     void Open (Variant)
RefreshMenu          Method     void RefreshMenu ()
ServiceStart         Method     Variant ServiceStart (string, Variant)
ServiceStop          Method     Variant ServiceStop (string, Variant)
SetTime              Method     void SetTime ()
ShellExecute         Method     void ShellExecute (string, Variant, Variant, Variant, Variant)
ShowBrowserBar       Method     Variant ShowBrowserBar (string, Variant)
ShutdownWindows      Method     void ShutdownWindows ()
Suspend              Method     void Suspend ()
TileHorizontally     Method     void TileHorizontally ()
TileVertically       Method     void TileVertically ()
ToggleDesktop        Method     void ToggleDesktop ()
TrayProperties       Method     void TrayProperties ()
UndoMinimizeALL      Method     void UndoMinimizeALL ()
Windows              Method     IDispatch Windows ()
WindowsSecurity      Method     void WindowsSecurity ()
WindowSwitcher       Method     void WindowSwitcher ()
Application          Property   IDispatch Application () {get}
Parent               Property   IDispatch Parent () {get}
```

### Exemplo 5: passar vários argumentos para um construtor

Este exemplo mostra como criar um objeto com um construtor que usa vários parâmetros. Os parâmetros devem ser colocados em uma matriz ao usar o parâmetro **ArgumentList** .

```powershell
$array = @('One', 'Two', 'Three')
$parameters = @{
    TypeName = 'System.Collections.Generic.HashSet[string]'
    ArgumentList = ([string[]]$array, [System.StringComparer]::OrdinalIgnoreCase)
}
$set = New-Object @parameters
```

O PowerShell associa cada membro da matriz a um parâmetro do construtor.

> [!NOTE]
> Este exemplo usa o parâmetro nivelamento para facilitar a leitura. Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

### Exemplo 6: chamando um construtor que usa uma matriz como um único parâmetro

Este exemplo mostra como criar um objeto com um construtor que usa um parâmetro que é uma matriz ou coleção. O parâmetro de matriz deve ser colocado em um encapsulamento dentro de outra matriz.

```powershell
$array = @('One', 'Two', 'Three')
# This command throws an exception.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList $array
# This command succeeds.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList (,[string[]]$array)
$set
```

```Output
New-Object : Cannot find an overload for "HashSet`1" and the argument count: "3".
At line:1 char:8
+ $set = New-Object -TypeName 'System.Collections.Generic.HashSet[strin ...
+        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidOperation: (:) [New-Object], MethodException
+ FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Commands.NewObjectCommand

One
Two
Three
```

A primeira tentativa de criar o objeto neste exemplo falha. O PowerShell tentou associar os três membros de `$array` aos parâmetros do Construtor, mas o construtor não ocupa três parâmetros. O encapsulamento `$array` em outra matriz impede que o PowerShell tente associar os três membros de `$array` aos parâmetros do construtor.

## PARAMETERS

### -ArgumentList

Especifica uma matriz de argumentos a serem passados para o construtor da classe .NET Framework. Se o construtor usa um único parâmetro que é uma matriz, você deve encapsular esse parâmetro dentro de outra matriz. Por exemplo:

`$cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate -ArgumentList (,$bytes)`

Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).

O alias para **ArgumentList** é **Args** .

```yaml
Type: System.Object[]
Parameter Sets: Net
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComObject

Especifica o identificador programático (ProgID) do objeto COM.

```yaml
Type: System.String
Parameter Sets: Com
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Propriedade

Define valores de propriedade e invoca métodos do novo objeto.

Insira uma tabela de hash na qual as chaves são os nomes das propriedades ou métodos e os valores são valores de propriedade ou argumentos de método. `New-Object` cria o objeto e define cada valor de propriedade e invoca cada método na ordem em que eles aparecem na tabela de hash.

Se o novo objeto for derivado da classe **PSObject** e você especificar uma propriedade que não exista no objeto, `New-Object` o adicionará a propriedade especificada ao objeto como uma NoteProperty. Se o objeto não for um **PSObject** , o comando gerará um erro de não finalização.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Estrito

Indica que o cmdlet gera um erro de não finalização quando um objeto COM que você tenta criar usa um assembly de interoperabilidade. Esse recurso distingue objetos reais de objetos do .NET Framework com COM callable wrappers.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Com
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeName

Especifica o nome totalmente qualificado da classe do .NET Framework. Você não pode especificar o parâmetro **TypeName** e o parâmetro **ComObject** .

```yaml
Type: System.String
Parameter Sets: Net
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Objeto

`New-Object` Retorna o objeto que é criado.

## OBSERVAÇÕES

- `New-Object` fornece a funcionalidade mais comumente usada da função do VBScript CreateObject. Uma instrução como `Set objShell = CreateObject("Shell.Application")` no VBScript pode ser convertida em `$objShell = New-Object -COMObject "Shell.Application"` no PowerShell.
- `New-Object` expande sobre a funcionalidade disponível no ambiente do Windows Script Host, facilitando o trabalho com .NET Framework objetos da linha de comando e em scripts.

## LINKS RELACIONADOS

[about_Object_Creation](../Microsoft.PowerShell.Core/About/about_Object_Creation.md)

[Compare-Object](Compare-Object.md)

[Group-Object](Group-Object.md)

[Measure-Object](Measure-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

