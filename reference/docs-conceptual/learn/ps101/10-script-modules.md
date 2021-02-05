---
title: Script modules (Módulos de script)
description: Os módulos de script são um modo fácil de empacotar scripts e funções em uma ferramenta reutilizável.
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: c557c071bc202a4216a77e7e5ae0bd73b4bc014b
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "99598608"
---
# <a name="chapter-10---script-modules"></a>Capítulo 10 – Módulos de script

Transformar seus scripts e uma linha no PowerShell em ferramentas reutilizáveis torna-se ainda mais importante se é algo que você pretende usar com frequência. O empacotamento de suas funções em um módulo de script faz com que elas pareçam mais profissionais e facilitam o compartilhamento.

## <a name="dot-sourcing-functions"></a>Funções de fornecimento de ponto

Um assunto que não abordamos no capítulo anterior é funções de fornecimento de ponto. Quando uma função em um script não faz parte de um módulo, a única maneira de carregá-la na memória é a origem de ponto do arquivo `.PS1` em que ela foi salva.

A função a seguir foi salva como `Get-MrPSVersion.ps1`.

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}
```

Quando você executa o script, nada acontece.

```powershell
.\Get-MrPSVersion.ps1
```

Se você tentar chamar a função, ela vai gerar uma mensagem de erro.

```powershell
Get-MrPSVersion
```

```Output
Get-MrPSVersion : The term 'Get-MrPSVersion' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path
was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-MrPSVersion
    + CategoryInfo          : ObjectNotFound: (Get-MrPSVersion:String) [], CommandNotFou
   ndException
    + FullyQualifiedErrorId : CommandNotFoundException

```

Você pode determinar se as funções são carregadas na memória verificando se elas existem na PSDrive **Function**.

```powershell
Get-ChildItem -Path Function:\Get-MrPSVersion
```

```Output
Get-ChildItem : Cannot find path 'Get-MrPSVersion' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path Function:\Get-MrPSVersion
    + CategoryInfo          : ObjectNotFound: (Get-MrPSVersion:String) [Get-ChildItem],
   ItemNotFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
```

O problema de chamar o script que contém a função é que as funções são carregadas no escopo de _Script_. Quando o script for concluído, esse escopo será removido e a função será removida com ele.

A função precisa ser carregada no escopo _Global_. Isso pode ser feito adquirindo o ponto do script que contém a função. O caminho relativo pode ser usado.

```powershell
. .\Get-MrPSVersion.ps1
```

O caminho totalmente qualificado também pode ser usado.

```powershell
. C:\Demo\Get-MrPSVersion.ps1
```

Se uma parte do caminho for armazenada em uma variável, ela poderá ser combinada com o restante do caminho.
Não há motivo para usar a concatenação de cadeia de caracteres para combinar a variável junto com o restante do caminho.

```powershell
$Path = 'C:\'
. $Path\Get-MrPSVersion.ps1
```

Agora, quando verifico a PSDrive **Function**, a função `Get-MrPSVersion` existe.

```powershell
Get-ChildItem -Path Function:\Get-MrPSVersion
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-MrPSVersion
```

## <a name="script-modules"></a>Módulos de script

Um módulo de script no PowerShell é simplesmente um arquivo que contém uma ou mais funções que são salvas como um arquivo de `.PSM1` em vez de um arquivo de `.PS1`.

Como criar um módulo de script? Provavelmente, você está supondo com um comando chamado algo como `New-Module`. Sua suposição está incorreta. Embora haja um comando no PowerShell chamado `New-Module`, esse comando cria um módulo dinâmico, não um módulo de script. Sempre leia a ajuda para um comando mesmo quando você acreditar que encontrou o comando de que precisa.

```powershell
help New-Module
```

```Output
NAME
    New-Module

SYNOPSIS
    Creates a new dynamic module that exists only in memory.

SYNTAX
    New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-ArgumentList <Object[]>]
    [-AsCustomObject] [-Cmdlet <String[]>] [-Function <String[]>] [-ReturnResult]
    [<CommonParameters>]

DESCRIPTION
    The New-Module cmdlet creates a dynamic module from a script block. The members of
    the dynamic module, such as functions and variables, are immediately available in
    the session and remain available until you close the session.

    Like static modules, by default, the cmdlets and functions in a dynamic module are
    exported and the variables and aliases are not. However, you can use the
    Export-ModuleMember cmdlet and the parameters of New-Module to override the defaults.

    You can also use the AsCustomObject parameter of New-Module to return the dynamic
    module as a custom object. The members of the modules, such as functions, are
    implemented as script methods of the custom object instead of being imported into
    the session.

    Dynamic modules exist only in memory, not on disk. Like all modules, the members of
    dynamic modules run in a private module scope that is a child of the global scope.
    Get-Module cannot get a dynamic module, but Get-Command can get the exported members.

    To make a dynamic module available to Get-Module , pipe a New-Module command to
    Import-Module, or pipe the module object that New-Module returns to Import-Module .
    This action adds the dynamic module to the Get-Module list, but it does not save the
    module to disk or make it persistent.

RELATED LINKS
    Online Version: http://go.microsoft.com/fwlink/?LinkId=821495
    Export-ModuleMember
    Get-Module
    Import-Module
    Remove-Module

REMARKS
    To see the examples, type: "get-help New-Module -examples".
    For more information, type: "get-help New-Module -detailed".
    For technical information, type: "get-help New-Module -full".
    For online help, type: "get-help New-Module -online"
```

No capítulo anterior, mencionei que as funções devem usar verbos aprovados, caso contrário, gerarão uma mensagem de aviso quando o módulo for importado. O código a seguir usa o cmdlet `New-Module` para criar um módulo dinâmico na memória. Este módulo demonstra o aviso de verbo não aprovado.

```powershell
New-Module -Name MyModule -ScriptBlock {

    function Return-MrOsVersion {
        Get-CimInstance -ClassName Win32_OperatingSystem |
        Select-Object -Property @{label='OperatingSystem';expression={$_.Caption}}
    }

    Export-ModuleMember -Function Return-MrOsVersion

} | Import-Module
```

```Output
WARNING: The names of some imported commands from the module 'MyModule' include
unapproved verbs that might make them less discoverable. To find the commands with
unapproved verbs, run the Import-Module command again with the Verbose parameter. For a
list of approved verbs, type Get-Verb.
```

Apenas para reiterar, embora o cmdlet `New-Module` tenha sido usado no exemplo anterior, esse não é o comando para a criação de módulos de script no PowerShell.

Salve as duas funções a seguir em um arquivo chamado `MyScriptModule.psm1`.

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}

function Get-MrComputerName {
    $env:COMPUTERNAME
}
```

Tente chamar uma das funções.

```powershell
Get-MrComputerName
```

```Output
Get-MrComputerName : The term 'Get-MrComputerName' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-MrComputerName
    + CategoryInfo          : ObjectNotFound: (Get-MrComputerName:String) [], CommandNot
   FoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

Uma mensagem de erro é gerada dizendo que a função não pode ser encontrada. Você também pode verificar a PSDrive **Function** da mesma forma que antes e descobrirá que ela não existe.

Você pode importar manualmente o arquivo com o cmdlet `Import-Module`.

```powershell
Import-Module C:\MyScriptModule.psm1
```

O recurso de carregamento automático do módulo foi introduzido no PowerShell versão 3. Para aproveitar o carregamento automático de módulo, um módulo de script precisa ser salvo em uma pasta com o mesmo nome de base que o arquivo de `.PSM1` e em um local especificado em `$env:PSModulePath`.

```powershell
$env:PSModulePath
```

```Output
C:\Users\mike-ladm\Documents\WindowsPowerShell\Modules;C:\Program Files\WindowsPowerShell\
Modules;C:\Windows\system32\WindowsPowerShell\v1.0\Modules;C:\Program Files (x86)\Microsof
t SQL Server\130\Tools\PowerShell\Modules\
```

Os resultados são difíceis de ler. Como os caminhos são separados por ponto e vírgula, você pode dividir os resultados para retornar cada caminho em uma linha separada. Isso facilita a leitura.

```powershell
$env:PSModulePath -split ';'
```

```Output
C:\Users\mike-ladm\Documents\WindowsPowerShell\Modules
C:\Program Files\WindowsPowerShell\Modules
C:\Windows\system32\WindowsPowerShell\v1.0\Modules
C:\Program Files (x86)\Microsoft SQL Server\130\Tools\PowerShell\Modules\
```

Os três primeiros caminhos da lista são o padrão. Quando o SQL Server Management Studio foi instalado, ele adicionou o último caminho. Para que o carregamento automático de módulo funcione, o arquivo de `MyScriptModule.psm1` precisa estar localizado em uma pasta chamada `MyScriptModule` diretamente dentro de um desses caminhos.

Não tão rápido. Para mim, meu caminho de usuário atual não é o primeiro da lista. Eu quase nunca uso esse caminho, pois eu faço logon no Windows com um usuário diferente daquele que eu uso para executar o PowerShell. Isso significa que ele não está localizado na pasta meus documentos normais.

O segundo caminho é o caminho **AllUsers**. Esse é o local em que eu armazeno todos os meus módulos.

O terceiro caminho está abaixo de `C:\Windows\System32`. Somente a Microsoft deve armazenar módulos nesse local, pois ele reside na pasta de sistemas operacionais.

Depois que o arquivo de `.PSM1` estiver localizado no caminho correto, o módulo será carregado automaticamente quando um de seus comandos for chamado.

## <a name="module-manifests"></a>Manifestos de módulo

Todos os módulos devem ter um manifesto de módulo. Um manifesto de módulo contém metadados sobre seu módulo.
A extensão de arquivo para um arquivo de manifesto de módulo é `.PSD1`. Nem todos os arquivos com uma extensão `.PSD1` são manifestos de módulo. Eles também podem ser usados para armazenar a parte ambiental de uma configuração DSC, por exemplo. `New-ModuleManifest` é usado para criar um manifesto de módulo. **Path** é o único valor obrigatório. No entanto, o módulo não funcionará se **RootModule** não for especificado. É uma boa ideia especificar o **Autor** e a **Descrição**, caso você decida carregar seu módulo para um repositório do NuGet com PowerShellGet, já que esses valores são necessários nesse cenário.

A versão de um módulo sem um manifesto é 0.0. Esse é um indício de que o módulo não tem um manifesto.

```powershell
Get-Module -Name MyScriptModule
```

```Output
ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Script     0.0        myscriptmodule                      {Get-MrComputerName, Get-MrP...
```

O manifesto do módulo pode ser criado com todas as informações recomendadas.

```powershell
New-ModuleManifest -Path $env:ProgramFiles\WindowsPowerShell\Modules\MyScriptModule\MyScriptModule.psd1 -RootModule MyScriptModule -Author 'Mike F Robbins' -Description 'MyScriptModule' -CompanyName 'mikefrobbins.com'
```

Se qualquer uma dessas informações for perdida durante a criação inicial do manifesto do módulo, ela poderá ser adicionada ou atualizada posteriormente usando `Update-ModuleManifest`. Não recrie o manifesto usando `New-ModuleManifest` depois que ele já estiver criado, pois o GUID será alterado.

## <a name="defining-public-and-private-functions"></a>Como definir funções públicas e privadas

Você pode ter funções auxiliares que talvez queira que sejam privadas e estejam acessíveis somente a outras funções dentro do módulo. Elas não devem estar acessíveis aos usuários do seu módulo. Há algumas maneiras de fazer isso.

Se você não estiver seguindo as melhores práticas e tiver apenas um arquivo `.PSM1`, sua única opção será usar o cmdlet `Export-ModuleMember`.

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}

function Get-MrComputerName {
    $env:COMPUTERNAME
}

Export-ModuleMember -Function Get-MrPSVersion
```

No exemplo anterior, somente a função `Get-MrPSVersion` está disponível para os usuários do seu módulo, mas a função `Get-MrComputerName` está disponível para outras funções dentro do próprio módulo.

```powershell
Get-Command -Module MyScriptModule

CommandType     Name                        Version    Source
-----------     ----                        -------    ------
Function        Get-MrPSVersion             1.0        MyScript...
```

Se você tiver adicionado um manifesto de módulo ao seu módulo (e você deve fazer isso), recomendo especificar as funções individuais que deseja exportar na seção **FunctionsToExport** do manifesto do módulo.

```powershell
FunctionsToExport = 'Get-MrPSVersion'
```

Não é necessário usar tanto `Export-ModuleMember` no arquivo `.PSM1` quanto a seção **FunctionsToExport** do manifesto do módulo. Um ou outro é suficiente.

## <a name="summary"></a>Resumo

Neste capítulo, você aprendeu a transformar suas funções em um módulo de script no PowerShell. Você também aprendeu algumas das práticas recomendadas para a criação de módulos de script, como a criação de um manifesto de módulo para o módulo de script.

## <a name="review"></a>Revisão

1. Como criar um módulo de script no PowerShell?
1. Por que é importante que suas funções usem um verbo aprovado?
1. Como criar um manifesto de módulo no PowerShell?
1. Quais são as duas opções para exportar apenas determinadas funções do seu módulo?
1. O que é necessário para que os módulos sejam carregados automaticamente quando um comando é chamado?

## <a name="recommended-reading"></a>Leitura recomendada

- [Como criar módulos de script do PowerShell e manifestos de módulo][]
- [about_Modules][]
- [New-ModuleManifest][]
- [Export-ModuleMember][]

<!-- link references -->
[Como criar módulos de script do PowerShell e manifestos de módulo]: https://mikefrobbins.com/2013/07/04/how-to-create-powershell-script-modules-and-module-manifests/
[about_Modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[New-ModuleManifest]: /powershell/module/microsoft.powershell.core/new-modulemanifest
[Export-ModuleMember]: /powershell/module/microsoft.powershell.core/export-modulemember
