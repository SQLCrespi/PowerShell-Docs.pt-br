---
description: Edições diferentes do PowerShell são executadas em diferentes tempos de execução subjacentes.
Locale: en-US
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_editions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Editions
ms.openlocfilehash: 3b1b938874b36919a1a0627f3b492cbc961e4a2f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595375"
---
# <a name="about-powershell-editions"></a>Sobre as edições do PowerShell

## <a name="short-description"></a>Descrição breve
Edições diferentes do PowerShell são executadas em diferentes tempos de execução subjacentes.

## <a name="long-description"></a>Descrição longa

Do PowerShell 5,1, há várias *edições* do PowerShell que são executadas em um tempo de execução do .net diferente. A partir do PowerShell 6,2, há duas edições do PowerShell:

- **Desktop**, que é executado em .NET Framework. O PowerShell 4 e inferior, bem como o PowerShell 5,1 em edições completas do Windows, como Windows desktop, Windows Server, Windows Server Core e a maioria dos outros sistemas operacionais Windows são Desktop Edition.
  Esta é a edição original do PowerShell.
- **Núcleo**, que é executado no .NET Core. PowerShell 6,0 e superior, bem como o PowerShell 5,1 em algumas edições de superfície reduzida do Windows, como o Windows nano Server e o Windows IoT, onde .NET Framework não está disponível.

Como a edição do PowerShell corresponde a seu tempo de execução do .NET, é o principal indicador da API do .NET e da compatibilidade do módulo do PowerShell; algumas APIs, tipos ou métodos do .NET não estão disponíveis em tempos de execução do .NET e isso afeta scripts e módulos do PowerShell que dependem deles.

## <a name="the-psedition-automatic-variable"></a>A `$PSEdition` variável automática

No PowerShell 5,1 e superior, você pode descobrir qual edição está executando com a `$PSEdition` variável automática:

```powershell
$PSEdition
```

```Output
Core
```

No PowerShell 4 e abaixo, essa variável não existe. `$PSEdition` ser nulo deve ser tratado da mesma forma que o valor `Desktop` .

### <a name="edition-in-psversiontable"></a>Edição no `$PSVersionTable`

A `$PSVersionTable` variável automática também tem informações de edição no PowerShell 5,1 e superior:

```powershell
$PSVersionTable
```

```Output
Name                           Value
----                           -----
PSVersion                      6.2.0-rc.1
PSEdition                      Core           # <-- Edition information
GitCommitId                    6.2.0-rc.1
OS                             Microsoft Windows 10.0.18865
Platform                       Win32NT
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
WSManStackVersion              3.0
```

O `PSEdition` campo terá o mesmo valor que a `$PSEdition` variável automática.

## <a name="the-compatiblepseditions-module-manifest-field"></a>O `CompatiblePSEditions` campo manifesto do módulo

Os módulos do PowerShell podem declarar em quais edições do PowerShell eles são compatíveis usando o `CompatiblePSEditions` campo do manifesto do módulo.

Por exemplo, um manifesto de módulo declarando a compatibilidade com as `Desktop` `Core` edições e do PowerShell:

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop', 'Core')
}
```

Um exemplo de um manifesto de módulo com apenas `Desktop` compatibilidade:

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop')
}
```

Omitir o `CompatiblePSEditions` campo de um manifesto de módulo terá o mesmo efeito que defini-lo como `Desktop` , já que os módulos criados antes desse campo foi introduzido foram gravados implicitamente para esta edição.

Para módulos não fornecidos como parte do Windows (ou seja, módulos que você escreve ou instala da Galeria), esse campo é apenas informativo; O PowerShell não altera o comportamento com base no `CompatiblePSEditions` campo, mas o expõe no `PSModuleInfo` objeto (retornado por `Get-Module` ) para sua própria lógica:

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion '5.1'
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```Output
Desktop
Core
```

> [!NOTE]
> O `CompatiblePSEditions` campo de módulo só é compatível com o PowerShell 5,1 e superior.
> A inclusão deste campo fará com que um módulo seja incompatível com o PowerShell 4 e inferior.
> Como o campo é puramente informativo, ele pode ser omitido com segurança em versões posteriores do PowerShell.

No PowerShell 6,1, `Get-Module -ListAvailable` o formatador foi atualizado para exibir a compatibilidade de edição de cada módulo:

```PowerShell
Get-Module -ListAvailable
```

```Output

    Directory: C:\Users\me\Documents\PowerShell\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Script     1.4.0      Az                                  Core,Desk
Script     1.3.1      Az.Accounts                         Core,Desk {Disable-AzDataCollection, Disable-AzContextAutosave, E...
Script     1.0.1      Az.Aks                              Core,Desk {Get-AzAks, New-AzAks, Remove-AzAks, Import-AzAksCreden...

...

Script     4.4.0      Pester                              Desk      {Describe, Context, It, Should...}
Script     1.18.0     PSScriptAnalyzer                    Desk      {Get-ScriptAnalyzerRule, Invoke-ScriptAnalyzer, Invoke-...
Script     1.0.0      WindowsCompatibility                Core      {Initialize-WinSession, Add-WinFunction, Invoke-WinComm...

```

## <a name="edition-compatibility-for-modules-that-ship-as-part-of-windows"></a>Edição-compatibilidade para módulos que são fornecidos como parte do Windows

Para módulos que são fornecidos como parte do Windows (ou são instalados como parte de uma função ou recurso), o PowerShell 6,1 e superior tratam o `CompatiblePSEditions` campo de forma diferente. Esses módulos são encontrados no diretório de módulos do sistema do Windows PowerShell ( `%windir%\System\WindowsPowerShell\v1.0\Modules` ).

Para módulos carregados de ou encontrados neste diretório, o PowerShell 6,1 e superior usa o `CompatiblePSEditions` campo para determinar se o módulo será compatível com a sessão atual e se comporta de acordo.

Quando `Import-Module` for usado, um módulo sem `Core` no `CompatiblePSEditions` não será importado e um erro será exibido:

```powershell
Import-Module BitsTransfer
```

```Output
Import-Module : Module 'C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\BitsTransfer\BitsTransfer.psd1' does not support current PowerShell edition 'Core'. Its supported editions are 'Desktop'. Use 'Import-Module -SkipEditionCheck' to ignore the compatibility of this module.
At line:1 char:1
+ Import-Module BitsTransfer
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : ResourceUnavailable: (C:\WINDOWS\system32\u2026r\BitsTransfer.psd1:String) [Import-Module], InvalidOperationException
+ FullyQualifiedErrorId : Modules_PSEditionNotSupported,Microsoft.PowerShell.Commands.ImportModuleCommand
```

Quando `Get-Module -ListAvailable` é usado, os módulos sem `Core` no `CompatiblePSEditions` não serão exibidos:

```powershell
Get-Module -ListAvailable BitsTransfer
```

```Output
# No output
```

Em ambos os casos, o `-SkipEditionCheck` parâmetro switch pode ser usado para substituir esse comportamento:

```powershell
Get-Module -ListAvailable -SkipEditionCheck BitsTransfer
```

```Output

    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.0.0    BitsTransfer                        Desk      {Add-BitsFile, Complete-BitsTransfer, Get-BitsTransfer,...

```

> [!WARNING]
> `Import-Module -SkipEditionCheck` pode parecer ter sucesso para um módulo, mas usar esse módulo executa o risco de encontrar uma incompatibilidade posteriormente; ao carregar o módulo inicialmente, um comando pode chamar uma API incompatível e fazer uma falha espontaneamente.

## <a name="authoring-powershell-modules-for-edition-cross-compatibility"></a>Criando módulos do PowerShell para compatibilidade cruzada de edição

Ao gravar um módulo do PowerShell para direcionar as duas `Desktop` `Core` edições do PowerShell, há coisas que você pode fazer para garantir a compatibilidade entre as edições.

A única maneira verdadeira de confirmar e validar continuamente a compatibilidade no entanto é gravar testes para seu script ou módulo e executá-los em todas as versões e edições do PowerShell com as quais você precisa de compatibilidade. Uma estrutura de teste recomendada para isso é [Pester][].

### <a name="powershell-script"></a>Script do PowerShell

Como uma linguagem, o PowerShell funciona da mesma forma entre edições; são os cmdlets, módulos e APIs do .NET que você usa que são afetados pela compatibilidade de edição.

Em geral, os scripts que funcionam no PowerShell 6,1 e acima funcionarão com o Windows PowerShell 5,1, mas há algumas exceções.

A versão 1.18.0 módulo [PSScriptAnalyzer][] tem regras como [`PSUseCompatibleCommands`][] e [`PSUseCompatibleTypes`][] que são capazes de detectar o uso possivelmente incompatível de comandos e APIs .net em scripts do PowerShell.

### <a name="net-assemblies"></a>Assemblies .NET

Se você estiver escrevendo um módulo binário ou um módulo que incorpora os assemblies (DLLs) do .NET gerados a partir do código-fonte, você deve compilar em relação ao [.net Standard][] e ao [PowerShell Standard][] para validação de compatibilidade de tempo de compilação do .net e da compatibilidade de API do PowerShell.

Embora essas bibliotecas possam verificar alguma compatibilidade no tempo de compilação, elas não poderão capturar possíveis diferenças comportamentais entre as edições. Para isso, você ainda deve escrever testes.

## <a name="see-also"></a>Consulte também

- [about_Automatic_Variables](about_Automatic_Variables.md)
- [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)
- [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module)
- [Módulos com as edições compatíveis do PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support)

[Pester]: https://github.com/pester/Pester/wiki/Pester
[PSScriptAnalyzer]: https://github.com/PowerShell/PSScriptAnalyzer
['PSUseCompatibleCommands']: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleCommands.md
['PSUseCompatibleTypes']: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleTypes.md
[.NET Standard]: /dotnet/standard/net-standard
[Padrão do PowerShell]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
