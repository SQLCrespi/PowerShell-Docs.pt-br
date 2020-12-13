---
ms.date: 10/16/2019
ms.topic: reference
title: Como escrever um manifesto de módulo do Windows PowerShell
description: Como escrever um manifesto de módulo do Windows PowerShell
ms.openlocfilehash: 42db71968ccac1cc3c1c05c5be2e72327e5e28d9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647696"
---
# <a name="how-to-write-a-powershell-module-manifest"></a>Como escrever um manifesto de módulo do PowerShell

Depois de escrever o módulo do PowerShell, você pode adicionar um manifesto de módulo opcional que inclui informações sobre o módulo. Por exemplo, você pode descrever o autor, especificar arquivos no módulo (como módulos aninhados), executar scripts para personalizar o ambiente do usuário, carregar tipos e formatar arquivos, definir requisitos de sistema e limitar os membros que o módulo exporta.

## <a name="creating-a-module-manifest"></a>Criando um manifesto de módulo

Um **manifesto de módulo** é um arquivo de dados `.psd1` do PowerShell () que descreve o conteúdo de um módulo e determina como um módulo é processado. O arquivo de manifesto é um arquivo de texto que contém uma tabela de hash de chaves e valores. Vincule um arquivo de manifesto a um módulo, nomeando o manifesto da mesma forma que o módulo e armazenando o manifesto no diretório raiz do módulo.

Para módulos simples que contêm apenas um `.psm1` assembly binário ou único, um manifesto de módulo é opcional. Mas, a recomendação é usar um manifesto de módulo sempre que possível, pois eles são úteis para ajudá-lo a organizar seu código e manter informações de controle de versão. E um manifesto de módulo é necessário para exportar um assembly que está instalado no [cache de assembly global](/dotnet/framework/app-domains/gac). Um manifesto de módulo também é necessário para módulos que dão suporte ao recurso de ajuda atualizável. A ajuda atualizável usa a chave **HelpInfoUri** no manifesto do módulo para localizar o arquivo de informações de ajuda (HelpInfo XML) que contém o local dos arquivos de ajuda atualizados para o módulo. Para obter mais informações sobre a ajuda atualizável, consulte [suporte à ajuda atualizável](./supporting-updatable-help.md).

### <a name="to-create-and-use-a-module-manifest"></a>Para criar e usar um manifesto de módulo

1. A prática recomendada para criar um manifesto de módulo é usar o cmdlet [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) . Você pode usar parâmetros para especificar uma ou mais das chaves e valores padrão do manifesto. O único requisito é nomear o arquivo. `New-ModuleManifest` Cria um manifesto de módulo com os valores especificados e inclui as chaves restantes e seus valores padrão. Se você precisar criar vários módulos, use `New-ModuleManifest` para criar um modelo de manifesto de módulo que possa ser modificado para seus módulos diferentes. Para obter um exemplo de um manifesto de módulo padrão, consulte o [manifesto do módulo de exemplo](#sample-module-manifest).

   `New-ModuleManifest -Path C:\myModuleName.psd1 -ModuleVersion "2.0" -Author "YourNameHere"`

   Uma alternativa é criar manualmente a tabela de hash do manifesto do módulo usando as informações mínimas necessárias, o **ModuleVersion**. Você salva o arquivo com o mesmo nome que o seu módulo e usa a `.psd1` extensão de arquivo. Em seguida, você pode editar o arquivo e adicionar as chaves e os valores apropriados.

1. Adicione quaisquer elementos adicionais que desejar no arquivo de manifesto.

   Para editar o arquivo de manifesto, use qualquer editor de texto que preferir. No entanto, o arquivo de manifesto é um arquivo de script que contém o código, portanto, talvez você queira editá-lo em um ambiente de script ou de desenvolvimento, como Visual Studio Code. Todos os elementos de um arquivo de manifesto são opcionais, exceto pelo número **ModuleVersion** .

   Para obter descrições das chaves e valores que você pode incluir em um manifesto de módulo, consulte a tabela [elementos de manifesto de módulo](#module-manifest-elements) . Para obter mais informações, consulte as descrições de parâmetro no cmdlet [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) .

1. Para resolver os cenários que podem não ser cobertos pelos elementos de manifesto de módulo base, você tem a opção de adicionar código adicional ao manifesto do módulo.

   Para questões de segurança, o PowerShell executa apenas um pequeno subconjunto das operações disponíveis em um arquivo de manifesto de módulo. Em geral, você pode usar a `if` instrução, os operadores aritméticos e de comparação e os tipos de dados básicos do PowerShell.

1. Depois de criar o manifesto do módulo, você pode testá-lo para confirmar se os caminhos descritos no manifesto estão corretos. Para testar o manifesto do módulo, use [Test-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/Test-ModuleManifest).

   `Test-ModuleManifest myModuleName.psd1`

1. Verifique se o manifesto do módulo está localizado no nível superior do diretório que contém o módulo.

   Quando você copia o módulo em um sistema e o importa, o PowerShell usa o manifesto do módulo para importar o módulo.

1. Opcionalmente, você pode testar diretamente seu manifesto de módulo com uma chamada para [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) por dot sourcing do manifesto em si.

   `Import-Module .\myModuleName.psd1`

## <a name="module-manifest-elements"></a>Elementos de manifesto de módulo

A tabela a seguir descreve os elementos que você pode incluir em um manifesto de módulo.

|Elemento|Padrão|Descrição|
|-------------|-------------|-----------------|
|**RootModule**<br /> Digite: `String`|`<empty string>`|Módulo de script ou arquivo de módulo binário associado a este manifesto. As versões anteriores do PowerShell chamaram esse elemento de **ModuleToProcess**.<br /> Os tipos possíveis para o módulo raiz podem estar vazios, o que cria um módulo de **manifesto** , o nome de um módulo de script ( `.psm1` ) ou o nome de um módulo binário ( `.exe` ou `.dll` ). Colocar o nome de um manifesto de módulo ( `.psd1` ) ou um arquivo de script ( `.ps1` ) neste elemento causa um erro. <br /> Exemplo: `RootModule = 'ScriptModule.psm1'`|
|**ModuleVersion**<br /> Digite: `Version`|`'0.0.1'`|Número de versão deste módulo. Se um valor não for especificado, `New-ModuleManifest`   o usará o padrão. A cadeia de caracteres deve ser capaz de converter para o tipo, `Version` por exemplo `#.#.#.#.#` . `Import-Module` carrega o primeiro módulo encontrado no **$PSModulePath** que corresponde ao nome e tem pelo menos o alto de **ModuleVersion**, como o parâmetro **MinimumVersion** . Para importar uma versão específica, use o `Import-Module` parâmetro **RequiredVersion** do cmdlet.<br /> Exemplo: `ModuleVersion = '1.0'`|
|**GUID**<br /> Digite: `GUID`|`'<GUID>'`|ID usada para identificar exclusivamente este módulo. Se um valor não for especificado, `New-ModuleManifest` o gerará o valor. No momento, não é possível importar um módulo pelo **GUID**. <br /> Exemplo: `GUID = 'cfc45206-1e49-459d-a8ad-5b571ef94857'`|
|**Autor**<br /> Digite: `String`|`'<Current user>'`|Autor deste módulo. Se um valor não for especificado, `New-ModuleManifest` o usará o usuário atual. <br /> Exemplo: `Author = 'AuthorNameHere'`|
|**CompanyName**<br /> Digite: `String`|`'Unknown'`|Empresa ou fornecedor deste módulo. Se um valor não for especificado, `New-ModuleManifest` o usará o padrão.<br /> Exemplo: `CompanyName = 'Fabrikam'`|
|**Direitos autorais**<br /> Digite: `String`|`'(c) <Author>. All rights reserved.'`| Declaração de direitos autorais deste módulo. Se um valor não for especificado, o `New-ModuleManifest` usará o padrão com o usuário atual como o `<Author>` . Para especificar um autor, use o parâmetro **Author** . <br /> Exemplo: `Copyright = '2019 AuthorName. All rights reserved.'`|
|**Descrição**<br /> Digite: `String`|`<empty string>`|Descrição da funcionalidade fornecida por este módulo.<br /> Exemplo: `Description = 'This is the module's description.'`|
|**PowerShellVersion**<br /> Digite: `Version`|`<empty string>`|Versão mínima do mecanismo do PowerShell exigida por este módulo. Os valores válidos são 1,0, 2,0, 3,0, 4,0, 5,0, 5,1, 6 e 7.<br /> Exemplo: `PowerShellVersion = '5.0'`|
|**PowerShellHostName**<br /> Digite: `String`|`<empty string>`|Nome do host do PowerShell exigido por este módulo. Esse nome é fornecido pelo PowerShell. Para localizar o nome de um programa de host, no programa, digite: `$host.name` .<br /> Exemplo: `PowerShellHostName = 'ConsoleHost'`|
|**PowerShellHostVersion**<br /> Digite: `Version`|`<empty string>`|Versão mínima do host do PowerShell exigida por este módulo.<br /> Exemplo: `PowerShellHostVersion = '2.0'`|
|**DotNetFrameworkVersion**<br /> Digite: `Version`|`<empty string>`|Versão mínima do Microsoft .NET Framework exigida por este módulo. Esse pré-requisito é válido somente para a edição do PowerShell desktop, como o PowerShell 5,1.<br /> Exemplo: `DotNetFrameworkVersion = '3.5'`|
|**CLRVersion**<br /> Digite: `Version`|`<empty string>`|Versão mínima do Common Language Runtime (CLR) exigido por este módulo. Esse pré-requisito é válido somente para a edição do PowerShell desktop, como o PowerShell 5,1.<br /> Exemplo: `CLRVersion = '3.5'`|
|**ProcessorArchitecture**<br /> Digite: `ProcessorArchitecture`|`<empty string>`|Arquitetura do processador (nenhuma, x86, AMD64) exigida por este módulo. Os valores válidos são x86, AMD64, ARM, IA64, MSIL e None (desconhecido ou não especificado).<br /> Exemplo: `ProcessorArchitecture = 'x86'`|
|**RequiredModules**<br /> Digite: `Object[]`|`@()`|Módulos que devem ser importados para o ambiente global antes da importação deste módulo. Isso carregará todos os módulos listados, a menos que eles já tenham sido carregados. Por exemplo, alguns módulos podem já ter sido carregados por um módulo diferente. É possível especificar uma versão específica para carregar usando `RequiredVersion` em vez de `ModuleVersion` . Quando `ModuleVersion` for usado, ele carregará a versão mais recente disponível com, no mínimo, a versão especificada. Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.<br /> Exemplo: `RequiredModules = @("MyModule", @{ModuleName="MyDependentModule"; ModuleVersion="2.0"; GUID="cfc45206-1e49-459d-a8ad-5b571ef94857"})`<br /> Exemplo: `RequiredModules = @("MyModule", @{ModuleName="MyDependentModule"; RequiredVersion="1.5"; GUID="cfc45206-1e49-459d-a8ad-5b571ef94857"})`|
|**RequiredAssemblies**<br /> Digite: `String[]`|`@()`|Assemblies que devem ser carregados antes da importação deste módulo. Especifica os nomes de arquivo de assembly ( `.dll` ) que o módulo requer.<br /> O PowerShell carrega os assemblies especificados antes de atualizar os tipos ou formatos, importando módulos aninhados ou importando o arquivo de módulo especificado no valor da chave RootModule. Use esse parâmetro para listar todos os assemblies que o módulo requer.<br /> Exemplo: `RequiredAssemblies = @("assembly1.dll", "assembly2.dll", "assembly3.dll")`|
|**ScriptsToProcess**<br /> Digite: `String[]`|`@()`|Arquivos de script ( `.ps1` ) que são executados no estado de sessão do chamador quando o módulo é importado. Pode ser o estado de sessão global ou, para módulos aninhados, o estado de sessão de outro módulo. Você pode usar esses scripts para preparar um ambiente assim como você pode usar um script de logon.<br /> Esses scripts são executados antes que qualquer um dos módulos listados no manifesto seja carregado. <br /> Exemplo: `ScriptsToProcess = @("script1.ps1", "script2.ps1", "script3.ps1")`|
|**TypesToProcess**<br /> Digite: `String[]`|`@()`|Digite os arquivos ( `.ps1xml` ) a serem carregados ao importar este módulo. <br /> Exemplo: `TypesToProcess = @("type1.ps1xml", "type2.ps1xml", "type3.ps1xml")`|
|**FormatsToProcess**<br /> Digite: `String[]`|`@()`|Arquivos de formato ( `.ps1xml` ) a serem carregados ao importar este módulo. <br /> Exemplo: `FormatsToProcess = @("format1.ps1xml", "format2.ps1xml", "format3.ps1xml")`|
|**NestedModules**<br /> Digite: `Object[]`|`@()`|Módulos a serem importados como módulos aninhados do módulo especificado em **RootModule** (alias:**ModuleToProcess**).<br /> A adição de um nome de módulo a esse elemento é semelhante à chamada `Import-Module` de dentro de seu código de script ou assembly. A principal diferença ao usar um arquivo de manifesto é que é mais fácil ver o que você está carregando. E, se um módulo não for carregado, você ainda não terá carregado seu módulo real.<br /> Além de outros módulos, você também pode carregar arquivos de script ( `.ps1` ) aqui. Esses arquivos serão executados no contexto do módulo raiz. Isso é equivalente a dot sourcing do script em seu módulo raiz. <br /> Exemplo: `NestedModules = @("script.ps1", @{ModuleName="MyModule"; ModuleVersion="1.0.0.0"; GUID="50cdb55f-5ab7-489f-9e94-4ec21ff51e59"})`|
|**FunctionsToExport**<br /> Digite: `String[]`|`@()`|Especifica as funções a serem exportadas deste módulo, para melhor desempenho, não use curingas e não exclua a entrada, use uma matriz vazia se não houver funções a serem exportadas. Por padrão, nenhuma função é exportada. Você pode usar essa chave para listar as funções que são exportadas pelo módulo.<br /> O módulo exporta as funções para o estado de sessão do chamador. O estado de sessão do chamador pode ser o estado de sessão global ou, para módulos aninhados, o estado de sessão de outro módulo. Ao encadear módulos aninhados, todas as funções exportadas por um módulo aninhado serão exportadas para o estado de sessão global, a menos que um módulo na cadeia restrinja a função usando a chave **FunctionsToExport** .<br /> Se o manifesto exportar aliases para as funções, essa chave poderá remover funções cujos aliases são listados na chave **AliasesToExport** , mas essa chave não pode adicionar aliases de função à lista. <br /> Exemplo: `FunctionsToExport = @("function1", "function2", "function3")`|
|**CmdletsToExport**<br /> Digite: `String[]`|`@()`|Especifica os cmdlets a serem exportados deste módulo, para melhor desempenho, não use curingas e não exclua a entrada, use uma matriz vazia se não houver cmdlets a serem exportados. Por padrão, nenhum cmdlet é exportado. Você pode usar essa chave para listar os cmdlets que são exportados pelo módulo.<br /> O estado de sessão do chamador pode ser o estado de sessão global ou, para módulos aninhados, o estado de sessão de outro módulo. Quando você estiver encadeando módulos aninhados, todos os cmdlets exportados por um módulo aninhado serão exportados para o estado de sessão global, a menos que um módulo na cadeia restringe o cmdlet usando a chave **CmdletsToExport** .<br /> Se o manifesto exporta aliases para os cmdlets, essa chave pode remover cmdlets cujos aliases são listados na chave **AliasesToExport** , mas essa chave não pode adicionar aliases de cmdlet à lista. <br /> Exemplo: `CmdletsToExport = @("Get-MyCmdlet", "Set-MyCmdlet", "Test-MyCmdlet")`|
|**VariablesToExport**<br /> Digite: `String[]`|`'*'`|Especifica as variáveis que o módulo exporta para o estado de sessão do chamador. Caracteres curinga são permitidos. Por padrão, todas as variáveis ( `'*'` ) são exportadas. Você pode usar essa chave para restringir as variáveis exportadas pelo módulo.<br /> O estado de sessão do chamador pode ser o estado de sessão global ou, para módulos aninhados, o estado de sessão de outro módulo. Quando você estiver encadeando módulos aninhados, todas as variáveis exportadas por um módulo aninhado serão exportadas para o estado de sessão global, a menos que um módulo na cadeia restringe a variável usando a chave **VariablesToExport** .<br /> Se o manifesto também exportar aliases para as variáveis, essa chave poderá remover variáveis cujos aliases são listados na chave **AliasesToExport** , mas essa chave não pode adicionar aliases variáveis à lista. <br /> Exemplo: `VariablesToExport = @('$MyVariable1', '$MyVariable2', '$MyVariable3')`|
|**AliasesToExport**<br /> Digite: `String[]`|`@()`|Especifica os aliases a serem exportados deste módulo, para melhor desempenho, não use curingas e não exclua a entrada, use uma matriz vazia se não houver aliases a serem exportados. Por padrão, nenhum alias é exportado. Você pode usar essa chave para listar os aliases exportados pelo módulo.<br /> O módulo exporta os aliases para o estado de sessão do chamador. O estado de sessão do chamador pode ser o estado de sessão global ou, para módulos aninhados, o estado de sessão de outro módulo. Quando você estiver encadeando módulos aninhados, todos os aliases exportados por um módulo aninhado serão exportados para o estado de sessão global, a menos que um módulo na cadeia restrinja o alias usando a chave **AliasesToExport** . <br /> Exemplo: `AliasesToExport = @("MyAlias1", "MyAlias2", "MyAlias3")`|
|**DscResourcesToExport**<br /> Digite: `String[]`|`@()`|Especifica os recursos DSC a serem exportados deste módulo. Caracteres curinga são permitidos. <br /> Exemplo: `DscResourcesToExport = @("DscResource1", "DscResource2", "DscResource3")`|
|**Módulolist**<br /> Digite: `Object[]`|`@()`|Especifica todos os módulos que são empacotados com este módulo. Esses módulos podem ser inseridos por nome, usando uma cadeia de caracteres separada por vírgulas ou como uma tabela de hash com nome de **módulo** e chaves de **GUID** . A tabela de hash também pode ter uma chave **ModuleVersion** opcional. A chave **ModuleList** foi projetada para atuar como um inventário de módulo. Esses módulos não são processados automaticamente. <br /> Exemplo: `ModuleList = @("SampleModule", "MyModule", @{ModuleName="MyModule"; ModuleVersion="1.0.0.0"; GUID="50cdb55f-5ab7-489f-9e94-4ec21ff51e59"})`|
|**FileList**<br /> Digite: `String[]`|`@()`|Lista de todos os arquivos empacotados com este módulo. Assim como com **ModuleList**, **FileList** é uma lista de inventário e não é processado de outra forma. <br /> Exemplo: `FileList = @("File1", "File2", "File3")`|
|**PrivateData**<br /> Digite: `Object`|`@{...}`|Especifica todos os dados privados que precisam ser passados para o módulo raiz especificado pela chave **RootModule** (alias: **ModuleToProcess**). **PrivateData** é uma tabela de hash que compreende vários elementos: **Tags**, **LicenseUri**, **ProjectURI**, **IconUri**, **releasenotes**, **pré-lançamento**, **RequireLicenseAcceptance** e **ExternalModuleDependencies**. |
|**Marcas** <br /> Digite: `String[]` |`@()`| Marcas ajudam com a descoberta de módulo em galerias online. <br /> Exemplo: `Tags = "PackageManagement", "PowerShell", "Manifest"`|
|**LicenseUri**<br /> Digite: `Uri` |`<empty string>`| Uma URL para a licença deste módulo. <br /> Exemplo: `LicenseUri = 'https://www.contoso.com/license'`|
|**ProjectUri**<br /> Digite: `Uri` |`<empty string>`| Uma URL para o site principal deste projeto. <br /> Exemplo: `ProjectUri = 'https://www.contoso.com/project'`|
|**IconUri**<br /> Digite: `Uri` |`<empty string>`| Uma URL para um ícone que representa este módulo. <br /> Exemplo: `IconUri = 'https://www.contoso.com/icons/icon.png'`|
|**ReleaseNotes**<br /> Digite: `String` |`<empty string>`| Especifica as notas de versão do módulo. <br /> Exemplo: `ReleaseNotes = 'The release notes provide information about the module.`|
|**Pré-lançamento**<br /> Digite: `String` |`<empty string>`| Esse parâmetro foi adicionado em PowerShellGet 1.6.6. Uma cadeia de caracteres de **pré-lançamento** que identifica o módulo como uma versão de pré-lançamento em galerias online. <br /> Exemplo: `PreRelease = 'This module is a prerelease version.`|
|**RequireLicenseAcceptance**<br /> Digite: `Boolean`|`$true`| Esse parâmetro foi adicionado no PowerShellGet 1,5. Sinalizador para indicar se o módulo requer aceitação explícita do usuário para instalar, atualizar ou salvar. <br /> Exemplo: `RequireLicenseAcceptance = $false`|
|**ExternalModuleDependencies**<br /> Digite: `String[]` |`@()`| Esse parâmetro foi adicionado no PowerShellGet v2. Uma lista de módulos externos que dependem deste módulo. <br /> Exemplo: `ExternalModuleDependencies =  @("ExtModule1", "ExtModule2", "ExtModule3")`|
|**HelpInfoURI**<br /> Digite: `String`|`<empty string>`|HelpInfo URI deste módulo. <br /> Exemplo: `HelpInfoURI = 'https://www.contoso.com/help'`|
|**DefaultCommandPrefix**<br /> Digite: `String`|`<empty string>`|Prefixo padrão para comandos exportados deste módulo. Substitua o prefixo padrão usando `Import-Module -Prefix` . <br /> Exemplo: `DefaultCommandPrefix = 'My'`|

## <a name="sample-module-manifest"></a>Manifesto de módulo de exemplo

O manifesto de módulo de exemplo a seguir foi criado com `New-ModuleManifest` o no PowerShell 7 e contém as chaves e valores padrão.

```powershell
#
# Module manifest for module 'SampleModuleManifest'
#
# Generated by: User01
#
# Generated on: 10/15/2019
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '0.0.1'

# Supported PSEditions
# CompatiblePSEditions = @()

# ID used to uniquely identify this module
GUID = 'b632e90c-df3d-4340-9f6c-3b832646bf87'

# Author of this module
Author = 'User01'

# Company or vendor of this module
CompanyName = 'Unknown'

# Copyright statement for this module
Copyright = '(c) User01. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the PowerShell engine required by this module
# PowerShellVersion = ''

# Name of the PowerShell host required by this module
# PowerShellHostName = ''

# Minimum version of the PowerShell host required by this module
# PowerShellHostVersion = ''

# Minimum version of Microsoft .NET Framework required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# DotNetFrameworkVersion = ''

# Minimum version of the common language runtime (CLR) required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# CLRVersion = ''

# Processor architecture (None, X86, Amd64) required by this module
# ProcessorArchitecture = ''

# Modules that must be imported into the global environment prior to importing this module
# RequiredModules = @()

# Assemblies that must be loaded prior to importing this module
# RequiredAssemblies = @()

# Script files (.ps1) that are run in the caller's environment prior to importing this module.
# ScriptsToProcess = @()

# Type files (.ps1xml) to be loaded when importing this module
# TypesToProcess = @()

# Format files (.ps1xml) to be loaded when importing this module
# FormatsToProcess = @()

# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
# NestedModules = @()

# Functions to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no functions to export.
FunctionsToExport = @()

# Cmdlets to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no cmdlets to export.
CmdletsToExport = @()

# Variables to export from this module
VariablesToExport = '*'

# Aliases to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no aliases to export.
AliasesToExport = @()

# DSC resources to export from this module
# DscResourcesToExport = @()

# List of all modules packaged with this module
# ModuleList = @()

# List of all files packaged with this module
# FileList = @()

# Private data to pass to the module specified in RootModule/ModuleToProcess. This may also contain a PSData hashtable with additional module metadata used by PowerShell.
PrivateData = @{

    PSData = @{

        # Tags applied to this module. These help with module discovery in online galleries.
        # Tags = @()

        # A URL to the license for this module.
        # LicenseUri = ''

        # A URL to the main website for this project.
        # ProjectUri = ''

        # A URL to an icon representing this module.
        # IconUri = ''

        # ReleaseNotes of this module
        # ReleaseNotes = ''

        # Prerelease string of this module
        # Prerelease = ''

        # Flag to indicate whether the module requires explicit user acceptance for install/update/save
        RequireLicenseAcceptance = $true

        # External dependent modules of this module
        # ExternalModuleDependencies = @()

    } # End of PSData hashtable

} # End of PrivateData hashtable

# HelpInfo URI of this module
# HelpInfoURI = ''

# Default prefix for commands exported from this module. Override the default prefix using Import-Module -Prefix.
# DefaultCommandPrefix = ''

}
```

## <a name="see-also"></a>Veja também

[about_Comparison_Operators](/powershell/module/microsoft.powershell.core/about/about_comparison_operators)

[about_If](/powershell/module/microsoft.powershell.core/about/about_if)

[Cache de assemblies global](/dotnet/framework/app-domains/gac)

[Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[New-ModuleManifest](/powershell/module/microsoft.powershell.core/new-modulemanifest)

[Test-ModuleManifest](/powershell/module/microsoft.powershell.core/test-modulemanifest)

[Update-ModuleManifest](/powershell/module/powershellget/update-modulemanifest)

[Escrever um módulo do Windows PowerShell](./writing-a-windows-powershell-module.md)
