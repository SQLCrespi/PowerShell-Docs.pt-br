---
title: Como escrever um manifesto de módulo do PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e082c2e3-12ce-4032-9caf-bf6b2e0dcf81
caps.latest.revision: 23
ms.openlocfilehash: 1265855b82b0bfaa7b2717c8eb348b822c19f561
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367095"
---
# <a name="how-to-write-a-powershell-module-manifest"></a>Como escrever um manifesto de módulo do Windows PowerShell

Depois de escrever o módulo do Windows PowerShell, você pode opcionalmente adicionar um manifesto de módulo. Um manifesto de módulo é um arquivo de script do PowerShell que você pode usar para incluir informações sobre o módulo. Por exemplo, você pode descrever o autor, especificar arquivos no módulo (como módulos aninhados), executar scripts para personalizar o ambiente do usuário, carregar tipos e formatar arquivos, definir requisitos de sistema e limitar os membros que o módulo exporta.

## <a name="creating-a-module-manifest"></a>Criando um manifesto de módulo

Um *manifesto de módulo* é um arquivo de dados do Windows PowerShell (. psd1) que descreve o conteúdo de um módulo e determina como um módulo é processado. O próprio arquivo de manifesto é um arquivo de texto que contém uma tabela de hash de chaves e valores. Vincule um arquivo de manifesto a um módulo, nomeando-o da mesma forma que o módulo e colocando-o na raiz do diretório do módulo.

Para módulos simples que contêm apenas um único assembly. psm1 ou binário, um manifesto de módulo é opcional. No entanto, é recomendável que você use um manifesto de módulo sempre que possível, pois eles são úteis para ajudá-lo a organizar seu código e a manter informações de controle de versão. Além disso, um manifesto de módulo é necessário para exportar um assembly que está instalado no cache de assembly global. Um manifesto de módulo também é necessário para módulos que dão suporte ao recurso de ajuda atualizável. Ou seja, a ajuda atualizável usa a chave **HelpInfoUri** no manifesto do módulo para localizar o arquivo de informações de ajuda (HelpInfo XML) que contém o local dos arquivos de ajuda atualizados para o módulo. Para obter mais informações sobre a ajuda atualizável, consulte [suporte à ajuda atualizável](./supporting-updatable-help.md).

### <a name="to-create-and-use-a-module-manifest"></a>Para criar e usar um manifesto de módulo

1. Para criar um manifesto de módulo, você tem várias opções:

   1. Crie diretamente a tabela de hash com as informações mínimas necessárias e salve-a em um arquivo. psd1 que tenha o mesmo nome que o seu módulo. Depois de fazer isso, você pode abrir o arquivo e adicionar os valores apropriados manualmente.

      `'@{ModuleVersion="1.0"}' > myModuleName.psd1`

   2. Ou, chame o cmdlet [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) , com um ou mais valores padrão passados como parâmetros. (Observe que o único nome do arquivo é necessário para gerar um manifesto, no entanto.) Isso criará um manifesto de módulo com todos os valores de manifesto fornecidos explicitamente declarados e com o restante que contém o valor padrão apropriado.

      `New-ModuleManifest myModuleName.psd1 -ModuleVersion "2.0" -Author "YourNameHere"`

   3. Por fim, você também pode criar um arquivo. psd1 vazio e copiar o modelo na parte inferior deste tópico para o arquivo e preencher os valores relevantes. O único requisito real nesse caso seria garantir que o arquivo tenha sido nomeado da mesma forma que o módulo.

2. Adicione qualquer elemento adicional ao manifesto que você deseja ter no arquivo.

   Em geral, isso provavelmente será feito em qualquer editor de texto que você preferir, como o bloco de notas. No entanto, isso tecnicamente é um arquivo de script que contém o código, portanto, talvez você queira editá-lo em um ambiente de script ou de desenvolvimento real, como Visual Studio Code. Novamente, observe que todos os elementos de um arquivo de manifesto são opcionais, exceto o número ModuleVersion.

   Para obter descrições das chaves e valores que você pode ter em um manifesto de módulo, consulte os **elementos de manifesto de módulo** abaixo. Para obter informações adicionais, consulte as descrições de parâmetro no cmdlet [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) .

3. Opcionalmente, você pode optar por adicionar código a seu manifesto de módulo para atender a quaisquer cenários que não seriam cobertos pelos elementos de manifesto do módulo base.

   Devido a questões de segurança, o PowerShell executará apenas um pequeno subconjunto das operações disponíveis em um arquivo de manifesto de módulo. Geralmente, você pode usar a instrução **If** , os operadores aritméticos e de comparação e os tipos de dados básicos do PowerShell.

4. Depois de criar o manifesto do módulo, você pode testá-lo (para confirmar se todos os caminhos descritos no manifesto estão corretos) com uma chamada para [Test-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/Test-ModuleManifest).

   `Test-ModuleManifest myModuleName.psd1`

5. Verifique se o manifesto do módulo está localizado no nível superior do diretório que contém o módulo.

   Quando você copiar o módulo para um sistema e importá-lo, o PowerShell usará o manifesto do módulo para importar o módulo.

6. Opcionalmente, você pode testar diretamente seu manifesto de módulo com uma chamada para [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) por dot sourcing do manifesto em si.

   `Import-Module .\myModuleName.psd1`

## <a name="module-manifest-elements"></a>Elementos de manifesto de módulo

A tabela a seguir descreve os elementos que você pode ter em um manifesto de módulo

|Elemento|Padrão|Descrição|
|-------------|-------------|-----------------|
|RootModule<br /><br /> Tipo: cadeia de caracteres|' '|Módulo de script ou arquivo de módulo binário associado a este manifesto. As versões anteriores do PowerShell chamaram esse elemento de ModuleToProcess.<br /><br /> Os tipos possíveis para o módulo raiz podem estar vazios (o que fará dele um módulo de **manifesto** ), o nome de um módulo de script (. psm1, que torna esse módulo de **script** ) ou o nome de um módulo binário (. exe ou. dll, que torna este módulo **binário** ). Colocar o nome de um manifesto de módulo (. psd1) ou um arquivo de script (. ps1) neste elemento causará a ocorrência de um erro.|
|ModuleVersion<br /><br /> Tipo: cadeia de caracteres|1.0|Número de versão deste módulo. A cadeia de caracteres deve ser capaz de converter em [System. Version]. Ou seja, ' #. #. #. #. # '. `Import-Module` carregará o primeiro módulo que encontrará no **$psModulePath** que corresponde ao nome e tem pelo menos o alto de ModuleVersion, como o parâmetro `-MinimumVersion`. Para importar uma versão específica, use o parâmetro @ no__t-0, em vez disso.<br /><br /> Exemplo: `ModuleVersion = '1.0'`|
|GUID<br /><br /> Tipo: cadeia de caracteres|GUID gerado automaticamente|ID usada para identificar exclusivamente este módulo. Observe que você não pode importar um módulo por GUID no momento.<br /><br /> Exemplo: `GUID = 'cfc45206-1e49-459d-a8ad-5b571ef94857'`|
|Autor<br /><br /> Tipo: cadeia de caracteres|Não|Autor deste módulo.<br /><br /> Exemplo: `Author = 'AuthorNameHere'`|
|CompanyName<br /><br /> Tipo: cadeia de caracteres|Unknown|Empresa ou fornecedor deste módulo.<br /><br /> Exemplo: `CompanyName = 'Fabrikam'`|
|Direitos Autorais<br /><br /> Tipo: cadeia de caracteres|(c) [currentYear] [Autor]. Todos os direitos reservados.|Declaração de direitos autorais deste módulo.<br /><br /> Exemplo: `Copyright = '2016 AuthorName. All rights reserved.'`|
|Descrição<br /><br /> Tipo: cadeia de caracteres|' '|Descrição da funcionalidade fornecida por este módulo.<br /><br /> Exemplo: `Description = 'This is a description of a module.'`|
|PowerShellVersion<br /><br /> Tipo: cadeia de caracteres|' '|Versão mínima do mecanismo do Windows PowerShell exigida por este módulo. Os valores válidos atuais são 1,0, 2,0, 3,0, 4,0 e 5,0.<br /><br /> Exemplo: `PowerShellVersion = '5.0'`|
|PowerShellHostName<br /><br /> Tipo: cadeia de caracteres|' '|Especifica o nome do host do Windows PowerShell que é exigido pelo módulo. Esse nome é fornecido pelo Windows PowerShell. Para localizar o nome de um programa de host, no programa, digite: `$host.name`.<br /><br /> Exemplo: `PowerShellHostName = 'Windows PowerShell ISE Host'`|
|PowerShellHostVersion<br /><br /> Tipo: cadeia de caracteres|' '|Versão mínima do host do Windows PowerShell exigida por este módulo.<br /><br /> Exemplo: `PowerShellHostVersion = '2.0'`|
|DotNetFrameworkVersion<br /><br /> Tipo: cadeia de caracteres|' '|Versão mínima do Microsoft .NET Framework exigida por este módulo.<br /><br /> Exemplo: `DotNetFrameworkVersion = '3.5'`|
|CLRVersion<br /><br /> Tipo: cadeia de caracteres|' '|Versão mínima do Common Language Runtime (CLR) exigido por este módulo.<br /><br /> Exemplo: `CLRVersion = '3.5'`|
|ProcessorArchitecture<br /><br /> Tipo: cadeia de caracteres|' '|Arquitetura do processador (nenhuma, x86, AMD64) exigida por este módulo. Os valores válidos são x86, AMD64 IA64 e Nenhum (desconhecido ou não especificado).<br /><br /> Exemplo: `ProcessorArchitecture = 'x86'`|
|RequiredModules<br /><br /> Tipo: [String []]|@()|Módulos que devem ser importados para o ambiente global antes da importação deste módulo. Isso carregará todos os módulos listados, a menos que eles já tenham sido carregados. Por exemplo, alguns módulos podem já ter sido carregados por um módulo diferente. Também é possível especificar uma versão específica para carregar usando `RequiredVersion` em vez de `ModuleVersion`. Ao usar `ModuleVersion` ele carregará a versão mais recente disponível com, no mínimo, a versão especificada.<br /><br /> Exemplo: `RequiredModules = @(@{ModuleName="myDependentModule"; ModuleVersion="2.0"; Guid="cfc45206-1e49-459d-a8ad-5b571ef94857"})`<br /><br /> Exemplo: `RequiredModules = @(@{ModuleName="myDependentModule"; RequiredVersion="1.5"; Guid="cfc45206-1e49-459d-a8ad-5b571ef94857"})`|
|RequiredAssemblies<br /><br /> Tipo: [String []]|@()|Assemblies que devem ser carregados antes da importação deste módulo.<br /><br /> Observe que, diferentemente do RequiredModules, o PowerShell carregará o RequiredAssemblies se eles ainda não estiverem carregados.|
|ScriptsToProcess<br /><br /> Tipo: [String []]|@()|Arquivos de script (. ps1) que são executados no estado de sessão do chamador quando o módulo é importado. Pode ser o estado de sessão global ou, para módulos aninhados, o estado de sessão de outro módulo. Você pode usar esses scripts para preparar um ambiente assim como você pode usar um script de logon.<br /><br /> Esses scripts são executados antes que qualquer um dos módulos listados no manifesto seja carregado.|
|TypesToProcess<br /><br /> Tipo: [String []]|@()|Digite os arquivos (. ps1xml) a serem carregados ao importar este módulo.|
|FormatsToProcess<br /><br /> Tipo: [String []]|@()|Arquivos de formato (. ps1xml) a serem carregados ao importar este módulo.|
|NestedModules<br /><br /> Tipo: [String []]|@()|Módulos a serem importados como módulos aninhados do módulo especificado em RootModule/ModuleToProcess.<br /><br /> Adicionar um nome de módulo a esse elemento é semelhante a chamar `Import-Module` de dentro do seu código de script ou assembly. A principal diferença é que é mais fácil ver o que você está carregando aqui no arquivo de manifesto. Além disso, se um módulo não for carregado aqui, você ainda não terá carregado seu módulo real.<br /><br /> Além de outros módulos, você também pode carregar arquivos de script (. ps1) aqui. Esses arquivos serão executados no contexto do módulo raiz. (Isso é equivalente a dot sourcing do script em seu módulo raiz.)|
|FunctionsToExport<br /><br /> Tipo: [String []]|@()|Especifica as funções que o módulo exporta (caracteres curinga são permitidos, mas desencorajados) para o estado de sessão do chamador. Por padrão, nenhuma função é exportada. Você pode usar essa chave para listar as funções que são exportadas pelo módulo.<br /><br /> O estado de sessão do chamador pode ser o estado de sessão global ou, para módulos aninhados, o estado de sessão de outro módulo. Ao encadear módulos aninhados, todas as funções exportadas por um módulo aninhado serão exportadas para o estado de sessão global, a menos que um módulo na cadeia restrinja a função usando a chave FunctionsToExport.<br /><br /> Se o manifesto também exportar aliases para as funções, essa chave poderá remover funções cujos aliases são listados na chave AliasesToExport, mas essa chave não pode adicionar aliases de função à lista.|
|CmdletsToExport<br /><br /> Tipo: [String []]|@()|Especifica os cmdlets que o módulo exporta (caracteres curinga são permitidos, mas desencorajados). Por padrão, nenhum cmdlet é exportado. Você pode usar essa chave para listar os cmdlets que são exportados pelo módulo.<br /><br /> O estado de sessão do chamador pode ser o estado de sessão global ou, para módulos aninhados, o estado de sessão de outro módulo. Quando você estiver encadeando módulos aninhados, todos os cmdlets exportados por um módulo aninhado serão exportados para o estado de sessão global, a menos que um módulo na cadeia restringe o cmdlet usando a chave CmdletsToExport.<br /><br /> Se o manifesto também exporta aliases para os cmdlets, essa chave pode remover cmdlets cujos aliases estão listados na chave AliasesToExport, mas essa chave não pode adicionar aliases de cmdlet à lista.|
|VariablesToExport<br /><br /> Tipo: cadeia de caracteres|'*'|Especifica as variáveis que o módulo exporta (caracteres curinga são permitidos) para o estado de sessão do chamador. Por padrão, todas as variáveis são exportadas. Você pode usar essa chave para restringir as variáveis exportadas pelo módulo.<br /><br /> O estado de sessão do chamador pode ser o estado de sessão global ou, para módulos aninhados, o estado de sessão de outro módulo. Quando você estiver encadeando módulos aninhados, todas as variáveis exportadas por um módulo aninhado serão exportadas para o estado de sessão global, a menos que um módulo na cadeia restringe a variável usando a chave VariablesToExport.<br /><br /> Se o manifesto também exportar aliases para as variáveis, essa chave poderá remover variáveis cujos aliases são listados na chave AliasesToExport, mas essa chave não pode adicionar aliases variáveis à lista.|
|AliasesToExport<br /><br /> Tipo: [String []]|@()|Especifica os aliases que o módulo exporta (caracteres curinga são permitidos, mas desencorajados) para o estado de sessão do chamador. Por padrão, nenhum alias é exportado. Você pode usar essa chave para listar os aliases exportados pelo módulo.<br /><br /> O estado de sessão do chamador pode ser o estado de sessão global ou, para módulos aninhados, o estado de sessão de outro módulo. Quando você estiver encadeando módulos aninhados, todos os aliases exportados por um módulo aninhado serão exportados para o estado de sessão global, a menos que um módulo na cadeia restrinja o alias usando a chave AliasesToExport.|
|Módulolist<br /><br /> Tipo: [String []]|@()|Especifica todos os módulos que são empacotados com este módulo. Esses módulos podem ser inseridos por nome (uma cadeia de caracteres separada por vírgula) ou como uma tabela de hash com ModuleName e chaves GUID. A tabela de hash também pode ter uma chave ModuleVersion opcional. A chave ModuleList foi projetada para atuar como um inventário de módulo. Esses módulos não são processados automaticamente.|
|File<br /><br /> Tipo: [String []]|@()|Lista de todos os arquivos empacotados com este módulo. Assim como com ModuleList, FileList é para ajudá-lo como uma lista de inventário e não é processado de outra forma.|
|PrivateData<br /><br /> Tipo: [objeto]|@{...}|Especifica todos os dados privados que precisam ser passados para o módulo raiz especificado pela chave RootModule/ModuleToProcess.|
|HelpInfoURI<br /><br /> Tipo: cadeia de caracteres|' '|HelpInfo URI deste módulo.|
|DefaultCommandPrefix<br /><br /> Tipo: cadeia de caracteres|' '|Prefixo padrão para comandos exportados deste módulo. Substitua o prefixo padrão usando `Import-Module`-Prefix.|

## <a name="sample-module-manifest"></a>Manifesto de módulo de exemplo

O manifesto de módulo de exemplo a seguir mostra as chaves e valores padrão em um manifesto de módulo. Este exemplo foi criado usando o cmdlet `New-ModuleManifest` no Windows PowerShell 3,0. Ao criar vários módulos, você pode usar este cmdlet para criar um modelo de manifesto que pode ser modificado para diferentes módulos.

```powershell
#
# Module manifest for module 'myManifest'
#
# Generated by: User01
#
# Generated on: 2019-10-09
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '1.0'

# Supported PSEditions
# CompatiblePSEditions = @()

# ID used to uniquely identify this module
GUID = 'b888e5a2-8578-4c0b-938d-0cd9b5b836ba'

# Author of this module
Author = 'User01'

# Company or vendor of this module
CompanyName = 'Unknown'

# Copyright statement for this module
Copyright = '(c) 2019 User01. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the Windows PowerShell engine required by this module
# PowerShellVersion = ''

# Name of the Windows PowerShell host required by this module
# PowerShellHostName = ''

# Minimum version of the Windows PowerShell host required by this module
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

    } # End of PSData hashtable

} # End of PrivateData hashtable

# HelpInfo URI of this module
# HelpInfoURI = ''

# Default prefix for commands exported from this module. Override the default prefix using Import-Module -Prefix.
# DefaultCommandPrefix = ''

}

```

## <a name="see-also"></a>Consulte Também

[Escrevendo um módulo do Windows PowerShell](./writing-a-windows-powershell-module.md)
