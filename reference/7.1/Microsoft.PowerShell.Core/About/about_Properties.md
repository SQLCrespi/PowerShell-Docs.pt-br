---
description: Descreve como usar propriedades de objeto no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Properties
ms.openlocfilehash: d4d3cd93e6b177e80d85315f125c647219fc4a45
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196343"
---
# <a name="about-properties"></a>Sobre propriedades

## <a name="short-description"></a>Descrição breve
Descreve como usar propriedades de objeto no PowerShell.

## <a name="long-description"></a>Descrição longa

O PowerShell usa coleções estruturadas de informações chamadas de objetos para representar os itens em armazenamentos de dados ou o estado do computador. Normalmente, você trabalha com objetos que fazem parte do Microsoft .NET Framework, mas também pode criar objetos personalizados no PowerShell.

A associação entre um item e seu objeto é muito próxima. Ao alterar um objeto, você geralmente altera o item que ele representa. Por exemplo, quando você recebe um arquivo no PowerShell, não obtém o arquivo real. Em vez disso, você recebe um objeto FileInfo que representa o arquivo. Quando você altera o objeto FileInfo, o arquivo também é alterado.

A maioria dos objetos tem propriedades. Propriedades são os dados associados a um objeto. Tipos diferentes de objeto têm propriedades diferentes. Por exemplo, um objeto FileInfo, que representa um arquivo, tem uma propriedade **IsReadOnly** que contém $true se o arquivo for o atributo somente leitura e $false se não tiver.
Um objeto DirectoryInfo, que representa um diretório do sistema de arquivos, tem uma propriedade Parent que contém o caminho até o diretório pai.

### <a name="object-properties"></a>Propriedades do objeto

Para obter as propriedades de um objeto, use o `Get-Member` cmdlet. Por exemplo, para obter as propriedades de um objeto **FileInfo** , use o `Get-ChildItem` cmdlet para obter o objeto FileInfo que representa um arquivo. Em seguida, use um operador de pipeline (&#124;) para o qual enviar o objeto **FileInfo** `Get-Member` . O comando a seguir obtém o arquivo PowerShell.exe e o envia para o `Get-Member` .
A \$ variável automática pshome contém o caminho do diretório de instalação do PowerShell.

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member
```

A saída do comando lista os membros do objeto **FileInfo** .
Os membros incluem propriedades e métodos. Quando você trabalha no PowerShell, tem acesso a todos os membros dos objetos.

Para obter apenas as propriedades de um objeto e não os métodos, use o parâmetro MemberType do `Get-Member` cmdlet com um valor de "Property", conforme mostrado no exemplo a seguir.

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member -MemberType property
```

```Output
TypeName: System.IO.FileInfo

Name              MemberType Definition
----              ---------- ----------
Attributes        Property   System.IO.FileAttributes Attributes {get;set;}
CreationTime      Property   System.DateTime CreationTime {get;set;}
CreationTimeUtc   Property   System.DateTime CreationTimeUtc {get;set;}
Directory         Property   System.IO.DirectoryInfo Directory {get;}
DirectoryName     Property   System.String DirectoryName {get;}
Exists            Property   System.Boolean Exists {get;}
Extension         Property   System.String Extension {get;}
FullName          Property   System.String FullName {get;}
IsReadOnly        Property   System.Boolean IsReadOnly {get;set;}
LastAccessTime    Property   System.DateTime LastAccessTime {get;set;}
LastAccessTimeUtc Property   System.DateTime LastAccessTimeUtc {get;set;}
LastWriteTime     Property   System.DateTime LastWriteTime {get;set;}
LastWriteTimeUtc  Property   System.DateTime LastWriteTimeUtc {get;set;}
Length            Property   System.Int64 Length {get;}
Name              Property   System.String Name {get;}
```

Depois de localizar as propriedades, você pode usá-las em seus comandos do PowerShell.

## <a name="property-values"></a>Valores de propriedade

Embora todo objeto de um tipo específico tenha as mesmas propriedades, os valores dessas propriedades descrevem o objeto específico. Por exemplo, cada objeto FileInfo tem uma propriedade CreationTime, mas o valor dessa propriedade é diferente para cada arquivo.

A maneira mais comum para obter os valores das propriedades de um objeto é usar o método de ponto. Digite uma referência ao objeto, como uma variável que contém o objeto, ou um comando que obtém o objeto. Em seguida, digite um ponto (.) seguido pelo nome da propriedade.

Por exemplo, o comando a seguir exibe o valor da propriedade CreationTime do arquivo PowerShell.exe. O `Get-ChildItem` comando retorna um objeto FileInfo que representa o arquivo de PowerShell.exe. O comando é colocado entre parênteses para garantir sua execução antes que qualquer propriedade seja acessada. O `Get-ChildItem` comando é seguido por um ponto e o nome da propriedade CreationTime, da seguinte maneira:

```powershell
(Get-ChildItem $pshome\PowerShell.exe).creationtime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

Você pode também salvar um objeto em uma variável e, em seguida, obter suas propriedades usando o método do ponto, conforme mostra o exemplo a seguir:

```powershell
$a = Get-ChildItem $pshome\PowerShell.exe
$a.CreationTime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

Você também pode usar os `Select-Object` `Format-List` cmdlets e para exibir os valores de propriedade de um objeto. `Select-Object` e `Format-List` cada um tem um parâmetro **Property** . Você pode usar o parâmetro **Property** para especificar uma ou mais propriedades e seus valores. Ou você pode usar o caractere curinga (\*) para representar todas as propriedades.

Por exemplo, o comando a seguir exibe os valores de todas as propriedades do arquivo PowerShell.exe.

```powershell
Get-ChildItem $pshome\PowerShell.exe | Format-List -Property *
```

```output
PSPath            : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0\PowerShell.exe
PSParentPath      : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0
PSChildName       : PowerShell.exe
PSDrive           : C
PSProvider        : Microsoft.PowerShell.Core\FileSystem
PSIsContainer     : False
Mode              : -a----
VersionInfo       : File:             C:\Windows\System32\WindowsPowerShell\
                    v1.0\PowerShell.exe
                    InternalName:     POWERSHELL
                    OriginalFilename: PowerShell.EXE.MUI
                    FileVersion:      10.0.16299.15 (WinBuild.160101.0800)
                    FileDescription:  Windows PowerShell
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.16299.15
                    Debug:            False
                    Patched:          False
                    PreRelease:       False
                    PrivateBuild:     False
                    SpecialBuild:     False
                    Language:         English (United States)

BaseName          : PowerShell
Target            : {C:\Windows\WinSxS\amd64_microsoft-windows-powershell-ex
                    e_31bf3856ad364e35_10.0.16299.15_none_8c022aa6735716ae\p
                    owershell.exe}
LinkType          : HardLink
Name              : PowerShell.exe
Length            : 449024
DirectoryName     : C:\Windows\System32\WindowsPowerShell\v1.0
Directory         : C:\Windows\System32\WindowsPowerShell\v1.0
IsReadOnly        : False
Exists            : True
FullName          : C:\Windows\System32\WindowsPowerShell\v1.0\PowerShell.ex
Extension         : .exe
CreationTime      : 9/29/2017 6:43:19 AM
CreationTimeUtc   : 9/29/2017 1:43:19 PM
LastAccessTime    : 9/29/2017 6:43:19 AM
LastAccessTimeUtc : 9/29/2017 1:43:19 PM
LastWriteTime     : 9/29/2017 6:43:19 AM
LastWriteTimeUtc  : 9/29/2017 1:43:19 PM
Attributes        : Archive
```

### <a name="static-properties"></a>Propriedades estáticas

Você pode usar as propriedades estáticas de classes .NET no PowerShell. Propriedades estáticas são propriedades de classe, ao contrário das propriedades padrão, que são propriedades de um objeto.

Para obter as propriedades estáticas de uma classe, use o parâmetro Static do cmdlet Get-Member.

Por exemplo, o comando a seguir obtém as propriedades estáticas da `System.DateTime` classe.

```powershell
Get-Date | Get-Member -MemberType Property -Static
```

```Output
TypeName: System.DateTime

Name     MemberType Definition
----     ---------- ----------
MaxValue Property   static datetime MaxValue {get;}
MinValue Property   static datetime MinValue {get;}
Now      Property   datetime Now {get;}
Today    Property   datetime Today {get;}
UtcNow   Property   datetime UtcNow {get;}
```

Para obter o valor de uma propriedade estática, use a sintaxe a seguir.

```
[<ClassName>]::<Property>
```

Por exemplo, o comando a seguir obtém o valor da propriedade estática UtcNow da `System.DateTime` classe.

```powershell
[System.DateTime]::UtcNow
```

### <a name="properties-of-scalar-objects-and-collections"></a>Propriedades de objetos e coleções escalares

Normalmente, as propriedades de um objeto ("escalar") de um tipo específico são diferentes das propriedades de uma coleção de objetos do mesmo tipo.
Por exemplo, cada serviço tem como propriedade **DisplayName** , mas uma coleção de serviços não tem uma propriedade **DisplayName** .

O comando a seguir obtém o valor da propriedade **DisplayName** do serviço ' AudioSrv '.

```powershell
(Get-Service Audiosrv).DisplayName
```

```output
Windows Audio
```

A partir do PowerShell 3,0, o PowerShell tenta evitar erros de script que resultam das diferentes propriedades de coleções e objetos escalares. O mesmo comando retorna o valor da propriedade **DisplayName** de cada serviço que `Get-Service` retorna.

```powershell
(Get-Service).DisplayName
```

```output
Application Experience
Application Layer Gateway Service
Windows All-User Install Agent
Application Identity
Application Information
...
```

Quando você envia uma coleção, mas solicita uma propriedade que existe somente em objetos únicos ("escalares"), o PowerShell retorna o valor dessa propriedade para cada objeto na coleção.

Todas as coleções têm uma propriedade **Count** que retorna quantos objetos estão na coleção.

```powershell
(Get-Service).Count
```

```output
176
```

A partir do PowerShell 3,0, se você solicitar a propriedade Count ou length de zero Objects ou um objeto, o PowerShell retornará o valor correto.

```powershell
(Get-Service Audiosrv).Count
```

```output
1
```

Se uma propriedade existir nos objetos individuais e na coleção, somente a propriedade da coleção será retornada.

 ```powershell
 $collection = @(
 [pscustomobject]@{length = "foo"}
 [pscustomobject]@{length = "bar"}
 )
 # PowerShell returns the collection's Length.
 $collection.length
 ```

 ```output
 2
 ```

Esse recurso também funciona em métodos de objetos escalares e de coleções. Para obter mais informações, consulte [about_Methods](about_methods.md).

## <a name="see-also"></a>Confira também

[about_Methods](about_Methods.md)

[about_Objects](about_Objects.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)

[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object)

[Format-List](xref:Microsoft.PowerShell.Utility.Format-List)

