---
ms.date: 12/14/2018
keywords: powershell, cmdlet
title: Gravação de módulos portáteis
ms.openlocfilehash: 7871f524495c1ce5283b30696a24185d427edebf
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417636"
---
# <a name="portable-modules"></a>Módulos portáteis

O Windows PowerShell é escrito para [.NET Framework][] enquanto o PowerShell Core é escrito para [.NET Core][]. Os módulos portáteis são módulos que funcionam no Windows PowerShell e no PowerShell Core. Embora o .NET Framework e .NET Core sejam altamente compatíveis, há diferenças entre os dois nas APIs disponíveis. Também há diferenças nas APIs disponíveis no Windows PowerShell e PowerShell Core. Os módulos destinados ao uso em ambos os ambientes precisam levar essas diferenças em consideração.

## <a name="porting-an-existing-module"></a>Fazendo a portabilidade de um módulo existente

### <a name="porting-a-pssnapin"></a>Fazendo a portabilidade de um PSSnapIn

Os PowerShell [SnapIns](/powershell/scripting/developer/cmdlet/modules-and-snap-ins) não são aceitos no PowerShell Core. No entanto, é comum converter um PSSnapIn em um módulo do PowerShell. Normalmente, o código de registro do PSSnapIn está em um único arquivo de origem de uma classe que deriva de [PSSnapIn][].
Remova esse arquivo de origem do build; ele não é mais necessário.

Use [New-ModuleManifest][] para criar um novo manifesto de módulo que substitui a necessidade do código de registro do PSSnapIn. Alguns dos valores do **PSSnapIn** (como **Descrição**) podem ser reutilizados no manifesto do módulo.

A propriedade **RootModule** no manifesto do módulo deve ser definida como o nome do assembly (dll) que implementa os cmdlets.

### <a name="the-net-portability-analyzer-aka-apiport"></a>.NET Portability Analyzer (também conhecido como APIPort)

Para fazer a portabilidade de módulos escritos para o Windows PowerShell de modo que funcionem com o PowerShell Core, comece com o [.NET Portability Analyzer][]. Execute essa ferramenta em seu assembly compilado para determinar se as APIs do .NET usadas no módulo são compatíveis com o .NET Framework, o .NET Core e outros runtimes do .NET. A ferramenta sugere APIs alternativas, se houver. Caso contrário, talvez você precise adicionar [verificações de runtime][] e restringir recursos não disponíveis em runtimes específicos.

## <a name="creating-a-new-module"></a>Criando um novo módulo

Se estiver criando um novo módulo, a recomendação é usar a [CLI do .NET][].

### <a name="installing-the-powershell-standard-module-template"></a>Instalando o modelo de módulo padrão do PowerShell

Depois que a CLI do .NET for instalada, instale uma biblioteca de modelos para gerar um módulo simples do PowerShell.
O módulo será compatível com Windows PowerShell, PowerShell Core, Windows, Linux e macOS.

O exemplo a seguir mostra como instalar o modelo:

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
```

```output
  Restoring packages for C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\restore.csproj...
  Installing Microsoft.PowerShell.Standard.Module.Template 0.1.3.
  Generating MSBuild file C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\obj\restore.csproj.nuget.g.props.
  Generating MSBuild file C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\obj\restore.csproj.nuget.g.targets.
  Restore completed in 1.66 sec for C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\restore.csproj.

Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.
  -n, --name          The name for the output being created. If no name is specified, the name of the current directory is used.
  -o, --output        Location to place the generated output.
  -i, --install       Installs a source or a template pack.
  -u, --uninstall     Uninstalls a source or a template pack.
  --nuget-source      Specifies a NuGet source to use during install.
  --type              Filters templates based on available types. Predefined values are "project", "item" or "other".
  --force             Forces content to be generated even if it would change existing files.
  -lang, --language   Filters templates based on language and specifies the language of the template to create.


Templates                                         Short Name         Language          Tags
----------------------------------------------------------------------------------------------------------------------------
Console Application                               console            [C#], F#, VB      Common/Console
Class library                                     classlib           [C#], F#, VB      Common/Library
PowerShell Standard Module                        psmodule           [C#]              Library/PowerShell/Module
...
```

### <a name="creating-a-new-module-project"></a>Criando um novo projeto de módulo

Depois que o modelo for instalado, é possível criar um novo projeto de módulo do PowerShell usando esse modelo. Neste exemplo, o módulo de exemplo é chamado de 'myModule'.

```
PS> mkdir myModule

    Directory: C:\Users\Steve

Mode LastWriteTime Length Name
---- ------------- ------ ----
d----- 8/3/2018 2:41 PM myModule

PS> cd myModule
PS C:\Users\Steve\myModule> dotnet new psmodule

The template "PowerShell Standard Module" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\Users\Steve\myModule\myModule.csproj...
  Restoring packages for C:\Users\Steve\myModule\myModule.csproj...
  Installing PowerShellStandard.Library 5.1.0.
  Generating MSBuild file C:\Users\Steve\myModule\obj\myModule.csproj.nuget.g.props.
  Generating MSBuild file C:\Users\Steve\myModule\obj\myModule.csproj.nuget.g.targets.
  Restore completed in 1.76 sec for C:\Users\Steve\myModule\myModule.csproj.

Restore succeeded.
```

### <a name="building-the-module"></a>Criando o módulo

Use comandos padrão da CLI do .NET para criar o projeto.

```powershell
dotnet build
```

```output
PS C:\Users\Steve\myModule> dotnet build
Microsoft (R) Build Engine version 15.7.179.6572 for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 76.85 ms for C:\Users\Steve\myModule\myModule.csproj.
  myModule -> C:\Users\Steve\myModule\bin\Debug\netstandard2.0\myModule.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:05.40
```

### <a name="testing-the-module"></a>Testando o módulo

Depois de criar o módulo, é possível importá-lo e executar o cmdlet de exemplo.

```powershell
ipmo .\bin\Debug\netstandard2.0\myModule.dll
Test-SampleCmdlet -?
Test-SampleCmdlet -FavoriteNumber 7 -FavoritePet Cat
```

```output
PS C:\Users\Steve\myModule> ipmo .\bin\Debug\netstandard2.0\myModule.dll
PS C:\Users\Steve\myModule> Test-SampleCmdlet -?

NAME
    Test-SampleCmdlet

SYNTAX
    Test-SampleCmdlet [-FavoriteNumber] <int> [[-FavoritePet] {Cat | Dog | Horse}] [<CommonParameters>]


ALIASES
    None


REMARKS
    None


PS C:\Users\Steve\myModule> Test-SampleCmdlet -FavoriteNumber 7 -FavoritePet Cat

FavoriteNumber FavoritePet
-------------- -----------
             7 Cat
```

As seções a seguir descrevem algumas das tecnologias usadas por esse modelo em detalhes.

## <a name="net-standard-library"></a>Biblioteca .NET Standard

[.NET Standard][] é uma especificação formal de APIs do .NET que estão disponíveis em todas as implementações do .NET. O código gerenciado que se destina ao .NET Standard funciona com as versões do .NET Framework e .NET Core compatíveis com essa versão do .NET Standard.

> [!NOTE]
> Embora possa existir uma API no .NET Standard, a implementação da API no .NET Core pode gerar uma `PlatformNotSupportedException` no runtime. Portanto, para verificar a compatibilidade com o Windows PowerShell e o PowerShell Core, a prática recomendada é executar testes para seu módulo em ambos os ambientes.
> Execute testes também no Linux e macOS se deseja usar seu módulo em mais de uma plataforma.

O direcionamento do .NET Standard ajuda a garantir que, à medida que o módulo evolui, as APIs incompatíveis não sejam acidentalmente introduzidas no módulo. As incompatibilidades são descobertas no tempo de compilação, e não no de execução.

No entanto, não é obrigatório direcionar o .NET Standard para que um módulo funcione com o Windows PowerShell e o PowerShell Core, desde que você use APIs compatíveis. A Linguagem Intermediária (IL) é compatível entre os dois runtimes. Você pode visar o .NET Framework 4.6.1, que é compatível com o .NET Standard 2.0. Se você não usar APIs fora do .NET Standard 2.0, seu módulo funcionará com o PowerShell Core 6 sem recompilação.

## <a name="powershell-standard-library"></a>Biblioteca Padrão do PowerShell

A biblioteca [Padrão do PowerShell][] é uma especificação formal das APIs do PowerShell disponíveis em todas as versões superiores ou iguais à versão desse padrão.

Por exemplo, o [Padrão 5.1 do PowerShell][] é compatível com o Windows PowerShell 5.1 e PowerShell Core 6.0 ou mais recente.

É recomendável compilar seu módulo usando a Biblioteca Padrão do PowerShell. A biblioteca garante que as APIs estejam disponíveis e sejam implementadas no Windows PowerShell e no PowerShell Core 6.
O Padrão do PowerShell destina-se a sempre ser compatível com versões posteriores. Um módulo compilado com a Biblioteca Padrão 5.1 do PowerShell sempre será compatível com versões futuras do PowerShell.

## <a name="module-manifest"></a>Manifesto de módulo

### <a name="indicating-compatibility-with-windows-powershell-and-powershell-core"></a>Indicando compatibilidade com o Windows PowerShell e o PowerShell Core

Depois de confirmar que o módulo funciona com o Windows PowerShell e o PowerShell Core, o manifesto do módulo deve indicar explicitamente a compatibilidade usando a propriedade [CompatiblePSEditions][]. Um valor `Desktop` significa que o módulo é compatível com o Windows PowerShell, enquanto um valor `Core` significa compatibilidade com o PowerShell Core. Incluir `Desktop` e `Core` significa que o módulo é compatível com o Windows PowerShell e o PowerShell Core.

> [!NOTE]
> `Core` não significa automaticamente que o módulo é compatível com Windows, Linux e macOS.
> A propriedade **CompatiblePSEditions** foi introduzida no PowerShell v5. Os manifestos do módulo que usam a propriedade **CompatiblePSEditions** falham ao carregar em versões anteriores ao PowerShell v5.

### <a name="indicating-os-compatibility"></a>Indicando a compatibilidade de SO

Primeiramente, confirme se o módulo funciona no Linux e no macOS. Em seguida, indique compatibilidade com esses sistemas operacionais no manifesto do módulo. Isso facilita para que os usuários encontrem o seu módulo para o sistema operacional deles após a publicação na [Galeria do PowerShell][].

No manifesto do módulo, a propriedade `PrivateData` tem uma subpropriedade `PSData`. A propriedade `Tags` opcional de `PSData` usa uma matriz de valores que é exibida na Galeria do PowerShell. A Galeria do PowerShell aceita os seguintes valores de compatibilidade:

| Tag               | Descrição                                |
|-------------------|--------------------------------------------|
| PSEdition_Core    | Compatível com o PowerShell Core 6          |
| PSEdition_Desktop | Compatível com o Windows PowerShell         |
| Windows           | Compatível com Windows                    |
| Linux             | Compatível com Linux (nenhuma distribuição específica) |
| macOS             | Compatível com macOS                      |

Exemplo:

```powershell
@{
    GUID = "4ae9fd46-338a-459c-8186-07f910774cb8"
    Author = "Microsoft Corporation"
    CompanyName = "Microsoft Corporation"
    Copyright = "(C) Microsoft Corporation. All rights reserved."
    HelpInfoUri = "https://go.microsoft.com/fwlink/?linkid=855962"
    ModuleVersion = "1.2.4"
    PowerShellVersion = "3.0"
    ClrVersion = "4.0"
    RootModule = "PackageManagement.psm1"
    Description = 'PackageManagement (a.k.a. OneGet) is a new way to discover and install software packages from around the web.
 It is a manager or multiplexer of existing package managers (also called package providers) that unifies Windows package management with a single Windows PowerShell interface. With PackageManagement, you can do the following.
  - Manage a list of software repositories in which packages can be searched, acquired and installed
  - Discover software packages
  - Seamlessly install, uninstall, and inventory packages from one or more software repositories'

    CmdletsToExport = @(
        'Find-Package',
        'Get-Package',
        'Get-PackageProvider',
        'Get-PackageSource',
        'Install-Package',
        'Import-PackageProvider'
        'Find-PackageProvider'
        'Install-PackageProvider'
        'Register-PackageSource',
        'Set-PackageSource',
        'Unregister-PackageSource',
        'Uninstall-Package'
        'Save-Package'
    )

    FormatsToProcess  = @('PackageManagement.format.ps1xml')

    PrivateData = @{
        PSData = @{
            Tags = @('PackageManagement', 'PSEdition_Core', 'PSEdition_Desktop', 'Windows', 'Linux', 'macOS')
            ProjectUri = 'https://oneget.org'
        }
    }
}
```

<!-- reference links -->
[.NET Framework]: /dotnet/framework/
[.NET Core]: /dotnet/core/
[PSSnapIn]: /dotnet/api/system.management.automation.pssnapin
[New-ModuleManifest]: /powershell/module/microsoft.powershell.core/new-modulemanifest
[verificações de runtime]: /dotnet/api/system.runtime.interopservices.runtimeinformation.frameworkdescription#System_Runtime_InteropServices_RuntimeInformation_FrameworkDescription
[CLI do .NET]: /dotnet/core/tools/?tabs=netcore2x
[.NET Standard]: /dotnet/standard/net-standard
[Padrão do PowerShell]: https://github.com/PowerShell/PowerShellStandard
[Padrão 5.1 do PowerShell]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[Galeria do PowerShell]: https://www.powershellgallery.com
[.NET Portability Analyzer]: https://github.com/Microsoft/dotnet-apiport
[CompatiblePSEditions]: /powershell/scripting/gallery/concepts/module-psedition-support
