---
description: Explica como criar objetos no PowerShell.
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_object_creation?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Object_Creation
ms.openlocfilehash: 72c0d763fe7f3838c8b2ca68930521e24d0e6139
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597837"
---
# <a name="about-object-creation"></a>Sobre a criação de objeto

## <a name="short-description"></a>Descrição breve

Explica como criar objetos no PowerShell.

## <a name="long-description"></a>Descrição longa

Você pode criar objetos no PowerShell e usar os objetos que você cria em comandos e scripts.

Há várias maneiras de criar objetos, essa lista não é definitiva:

- [New-Object](xref:Microsoft.PowerShell.Utility.New-Object): cria uma instância de um objeto de .NET Framework ou objeto com.
- [Importar-CSV](xref:Microsoft.PowerShell.Utility.Import-Csv) /
   [ConvertFrom-CSV](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): cria objetos personalizados (**PSCustomObject**) a partir dos itens definidos como valores separados por vírgula.
- [ConvertFrom-JSON](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): cria objetos personalizados definidos em JavaScript Object Notation (JSON).
- [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): cria objetos personalizados definidos como pares chave-valor.
- [Adicionar tipo](xref:Microsoft.PowerShell.Utility.Add-Type): permite que você defina uma classe em sua sessão do PowerShell com a qual você pode criar uma instância `New-Object` .
- [New-Module](xref:Microsoft.PowerShell.Core.New-Module): o parâmetro **AsCustomObject** cria um objeto personalizado que você define usando o bloco de script.
- [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member): Adiciona propriedades a objetos existentes. Você pode usar `Add-Member` para criar um objeto personalizado a partir de um tipo simples, como `[System.Int32]` .
- [Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object): seleciona as propriedades em um objeto. Você pode usar `Select-Object` para criar propriedades personalizadas e calculadas em um objeto já instanciado.

Os seguintes métodos adicionais são abordados neste artigo:

- Chamando o construtor de um tipo usando um `new()` método estático
- Por tabelas de hash typecasting de nomes de propriedade e valores de propriedade

## <a name="static-new-method"></a>Método New () estático

Todos os tipos .NET têm um `new()` método que permite construir instâncias mais facilmente. Você também pode ver todos os construtores disponíveis para um determinado tipo.

Para ver os construtores de um tipo, especifique o `new` nome do método após o nome do tipo e pressione `<ENTER>` .

```powershell
[System.Uri]::new
```

```Output
OverloadDefinitions
-------------------
uri new(string uriString)
uri new(string uriString, bool dontEscape)
uri new(uri baseUri, string relativeUri, bool dontEscape)
uri new(string uriString, System.UriKind uriKind)
uri new(uri baseUri, string relativeUri)
uri new(uri baseUri, uri relativeUri)
```

Agora, você pode criar um **System. URI** especificando o construtor apropriado.

```powershell
[System.Uri]::new("https://www.bing.com")
```

```Output
AbsolutePath   : /
AbsoluteUri    : https://www.bing.com/
LocalPath      : /
Authority      : www.bing.com
...
```

Você pode usar o exemplo a seguir para determinar quais tipos .NET estão atualmente carregados para instanciar.

```powershell
[AppDomain]::CurrentDomain.GetAssemblies() |
  ForEach-Object {
    $_.GetExportedTypes() |
      ForEach-Object { $_.FullName }
  }
```

Objetos criados usando o `new()` método podem não ter as mesmas propriedades que objetos do mesmo tipo que são criados por cmdlets do PowerShell. Os cmdlets, provedores e o sistema de tipos estendidos do PowerShell podem adicionar propriedades extras à instância.

Por exemplo, o provedor FileSystem no PowerShell adiciona seis valores **NoteProperty** ao objeto **DirectoryInfo** retornado por `Get-Item` .

```powershell
$PSDirInfo = Get-Item /
$PSDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    6 NoteProperty
    1 ScriptProperty
   18 Method
```

Quando você cria um objeto **DirectoryInfo** diretamente, ele não tem esses seis valores de **notaproperty** .

```powershell
$NewDirInfo = [System.IO.DirectoryInfo]::new('/')
$NewDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    1 ScriptProperty
   18 Method
```

Para obter mais informações sobre o sistema de tipo estendido, consulte [about_Types.ps1XML](about_Types.ps1xml.md).

Esse recurso foi adicionado no PowerShell 5,0

## <a name="create-objects-from-hash-tables"></a>Criar objetos a partir de tabelas de hash

Você pode criar um objeto de uma tabela de hash de propriedades e valores de propriedade.

A sintaxe dela é a seguinte:

```
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

Esse método funciona somente para classes que têm um construtor sem parâmetros. As propriedades do objeto devem ser públicas e configurável.

Esse recurso foi adicionado no PowerShell versão 3,0

## <a name="create-custom-objects-from-hash-tables"></a>Criar objetos personalizados a partir de tabelas de hash

Os objetos personalizados são muito úteis e são fáceis de criar usando o método de tabela de hash. A classe **PSCustomObject** foi projetada especificamente para essa finalidade.

Os objetos personalizados são uma excelente maneira de retornar a saída personalizada de uma função ou script. Isso é mais útil do que retornar a saída formatada que não pode ser reformatada ou canalizada para outros comandos.

Os comandos no `Test-Object function` definem alguns valores de variáveis e, em seguida, usam esses valores para criar um objeto personalizado. Você pode ver esse objeto em uso na seção de exemplo do `Update-Help` tópico de ajuda do cmdlet.

```powershell
function Test-Object {
  $ModuleName = "PSScheduledJob"
  $HelpCulture = "en-us"
  $HelpVersion = "3.1.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
  $ModuleName = "PSWorkflow"
  $HelpCulture = "en-us"
  $HelpVersion = "3.0.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
}
Test-Object
```

A saída dessa função é uma coleção de objetos personalizados formatados como uma tabela por padrão.

```Output
ModuleName        UICulture      Version
---------         ---------      -------
PSScheduledJob    en-us          3.1.0.0
PSWorkflow        en-us          3.0.0.0
```

Os usuários podem gerenciar as propriedades dos objetos personalizados da mesma forma como fazem com objetos padrão.

```powershell
(Test-Object).ModuleName
```

```Output
 PSScheduledJob
 PSWorkflow
```

## <a name="create-non-custom-objects-from-hash-tables"></a>Criar objetos não personalizados a partir de tabelas de hash

Você também pode usar tabelas de hash para criar objetos para classes não personalizadas. Quando você cria um objeto para uma classe não personalizada, o nome do tipo qualificado para namespace é necessário, embora você possa omitir qualquer componente de namespace de **sistema** inicial.

Por exemplo, o comando a seguir cria um objeto de opção de sessão.

```powershell
[System.Management.Automation.Remoting.PSSessionOption]@{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
```

Os requisitos do recurso de tabela de hash, especialmente o requisito de construtor sem parâmetros, eliminam muitas classes existentes. No entanto, a maioria das classes de _opção_ do PowerShell é projetada para trabalhar com esse recurso, bem como outras classes muito úteis, como a classe **ProcessStartInfo** .

```powershell
[System.Diagnostics.ProcessStartInfo]@{
  CreateNoWindow="$true"
  Verb="run as"
}
```

```Output
Arguments               :
ArgumentList            : {}
CreateNoWindow          : True
EnvironmentVariables    : {OneDriveConsumer, PROCESSOR_ARCHITECTURE,
                           CommonProgramFiles(x86), APPDATA...}
Environment             : {[OneDriveConsumer, C:\Users\user1\OneDrive],
                           [PROCESSOR_ARCHITECTURE, AMD64],
                           [CommonProgramFiles(x86),
                           C:\Program Files (x86)\Common Files],
                           [APPDATA, C:\Users\user1\AppData\Roaming]...}
RedirectStandardInput   : False
RedirectStandardOutput  : False
RedirectStandardError   : False
...
```

Você também pode usar o recurso de tabela de hash ao definir valores de parâmetro. Por exemplo, o valor do parâmetro **SessionOption** do `New-PSSession` .
o cmdlet pode ser uma tabela de hash.

```powershell
New-PSSession -ComputerName Server01 -SessionOption @{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
Register-ScheduledJob Name Test -FilePath .\Get-Inventory.ps1 -Trigger @{
  Frequency="Daily"
  At="15:00"
}
```

## <a name="generic-objects"></a>Objetos genéricos

Você também pode criar objetos genéricos no PowerShell. Genéricos são classes, estruturas, interfaces e métodos que possuem espaços reservados (parâmetros de tipo) para um ou mais dos tipos que eles armazenam ou usam.

O exemplo a seguir cria um objeto **Dictionary** .

```powershell
$dict = New-Object 'System.Collections.Generic.Dictionary[String,Int]'
$dict.Add("One", 1)
$dict
```

```Output
Key Value
--- -----
One     1
```

Para obter mais informações sobre os genéricos, consulte [genéricos no .net](/dotnet/standard/generics).

## <a name="see-also"></a>Consulte também

[about_Objects](about_Objects.md)

[about_Methods](about_Methods.md)

[about_Properties](about_Properties.md)

[about_Pipelines](about_Pipelines.md)

[about_Types.ps1xml](about_Types.ps1xml.md)
