---
ms.date: 09/12/2016
ms.topic: reference
title: Exemplos de ajuda baseada em comentários
description: Exemplos de ajuda baseada em comentários
ms.openlocfilehash: 35fe9103a261483c56af629f620dbd6b3c642e68
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667633"
---
# <a name="examples-of-comment-based-help"></a>Exemplos de ajuda baseada em comentários

Este tópico inclui um exemplo que demonstra como usar a ajuda baseada em comentários para scripts e funções.

## <a name="example-1-comment-based-help-for-a-function"></a>Exemplo 1: Comment-Based ajuda para uma função

 A função de exemplo a seguir inclui ajuda baseada em comentários.

```powershell
function Add-Extension
{
    param ([string]$Name,[string]$Extension = "txt")
    $name = $name + "." + $extension
    $name

    <#
        .SYNOPSIS
        Adds a file name extension to a supplied name.

        .DESCRIPTION
        Adds a file name extension to a supplied name.
        Takes any strings for the file name or extension.

        .PARAMETER Name
        Specifies the file name.

        .PARAMETER Extension
        Specifies the extension. "Txt" is the default.

        .INPUTS
        None. You cannot pipe objects to Add-Extension.

        .OUTPUTS
        System.String. Add-Extension returns a string with the extension or file name.

        .EXAMPLE
        C:\PS> extension -name "File"
        File.txt

        .EXAMPLE
        C:\PS> extension -name "File" -extension "doc"
        File.doc

        .EXAMPLE
        C:\PS> extension "File" "doc"
        File.doc

        .LINK
        Online version: http://www.fabrikam.com/extension.html

        .LINK
        Set-Item
    #>
}
```

A saída a seguir mostra os resultados de um `Get-Help` comando que exibe a ajuda para a `Add-Extension` função.

```powershell
C:\PS> get-help add-extension -full
```

```Output
        NAME
            Add-Extension

        SYNOPSIS
            Adds a file name extension to a supplied name.

        SYNTAX
            Add-Extension [[-Name] <String>] [[-Extension] <String>] [<CommonParameters>]

        DESCRIPTION
            Adds a file name extension to a supplied name. Takes any strings for the file name or extension.

        PARAMETERS
           -Name
               Specifies the file name.

               Required?                    false
               Position?                    0
               Default value
               Accept pipeline input?       false
               Accept wildcard characters?

           -Extension
               Specifies the extension. "Txt" is the default.

               Required?                    false
               Position?                    1
               Default value
               Accept pipeline input?       false
               Accept wildcard characters?

            <CommonParameters>
               This cmdlet supports the common parameters: -Verbose, -Debug,
               -ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
               -OutBuffer and -OutVariable. For more information, type
               "get-help about_commonparameters".

        INPUTS
            None. You cannot pipe objects to Add-Extension.

        OUTPUTS
            System.String. Add-Extension returns a string with the extension or file name.

            -------------------------- EXAMPLE 1 --------------------------

            C:\PS> extension -name "File"
            File.txt

            -------------------------- EXAMPLE 2 --------------------------

            C:\PS> extension -name "File" -extension "doc"
            File.doc

            -------------------------- EXAMPLE 3 --------------------------

            C:\PS> extension "File" "doc"
            File.doc

        RELATED LINKS
            Online version: http://www.fabrikam.com/extension.html
            Set-Item
```

## <a name="example-2-comment-based-help-for-a-script"></a>Exemplo 2: Comment-Based ajuda para um script

A função de exemplo a seguir inclui ajuda baseada em comentários.

Observe as linhas em branco entre o fechamento **#>** e a `Param` instrução. Em um script que não tem uma `Param` instrução, deve haver pelo menos duas linhas em branco entre o comentário final no tópico da ajuda e a primeira declaração da função. Sem essas linhas em branco, `Get-Help` o associa o tópico da ajuda com a função, em vez do script.

```powershell
<#
  .SYNOPSIS
  Performs monthly data updates.

  .DESCRIPTION
  The Update-Month.ps1 script updates the registry with new data generated
  during the past month and generates a report.

  .PARAMETER InputPath
  Specifies the path to the CSV-based input file.

  .PARAMETER OutputPath
  Specifies the name and path for the CSV-based output file. By default,
  MonthlyUpdates.ps1 generates a name from the date and time it runs, and
  saves the output in the local directory.

  .INPUTS
  None. You cannot pipe objects to Update-Month.ps1.

  .OUTPUTS
  None. Update-Month.ps1 does not generate any output.

  .EXAMPLE
  C:\PS> .\Update-Month.ps1

  .EXAMPLE
  C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

  .EXAMPLE
  C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
```

O comando a seguir obtém a ajuda do script. Como o script não está em um diretório listado na variável de ambiente Path, o `Get-Help` comando que obtém a ajuda do script deve especificar o caminho do script.

```powershell
C:\PS> get-help c:\ps-test\update-month.ps1 -full
```

```Output
            NAME
                C:\ps-test\Update-Month.ps1

            SYNOPSIS
                Performs monthly data updates.

            SYNTAX
                C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
                <String>] [<CommonParameters>]

            DESCRIPTION
                The Update-Month.ps1 script updates the registry with new data
                generated during the past month and generates a report.

            PARAMETERS
               -InputPath
                   Specifies the path to the CSV-based input file.

                   Required?                    true
                   Position?                    0
                   Default value
                   Accept pipeline input?       false
                   Accept wildcard characters?

               -OutputPath
                   Specifies the name and path for the CSV-based output file. By
                   default, MonthlyUpdates.ps1 generates a name from the date
                   and time it runs, and saves the output in the local directory.

                   Required?                    false
                   Position?                    1
                   Default value
                   Accept pipeline input?       false
                   Accept wildcard characters?

               <CommonParameters>
                   This cmdlet supports the common parameters: -Verbose, -Debug,
                   -ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
                   -OutBuffer and -OutVariable. For more information, type,
                   "get-help about_commonparameters".

            INPUTS
                   None. You cannot pipe objects to Update-Month.ps1.

            OUTPUTS
                   None. Update-Month.ps1 does not generate any output.

            -------------------------- EXAMPLE 1 --------------------------

            C:\PS> .\Update-Month.ps1

            -------------------------- EXAMPLE 2 --------------------------

            C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

            -------------------------- EXAMPLE 3 --------------------------

            C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
            C:\Reports\2009\January.csv

            RELATED LINKS
```

## <a name="example-3-parameter-descriptions-in-a-param-statement"></a>Exemplo 3: descrições de parâmetro em uma instrução param

Este exemplo mostra como inserir descrições de parâmetro na `Param` instrução de uma função ou script. Esse formato é mais útil quando as descrições de parâmetro são breves.

```powershell
function Add-Extension
{
    param
    (
        [string]
        # Specifies the file name.
        $name,

        [string]
        # Specifies the file name extension. "Txt" is the default.
        $extension = "txt"
    )
    $name = $name + "." + $extension
    $name

    <#
        .SYNOPSIS
        Adds a file name extension to a supplied name.
...
    #>
```

Os resultados são os mesmos dos resultados, por exemplo 1. `Get-Help` interpreta as descrições de parâmetro como se elas estivessem acompanhadas pela `.Parameter` palavra-chave.

## <a name="example-4--redirecting-to-an-xml-file"></a>Exemplo 4: redirecionando para um arquivo XML

Você pode escrever tópicos de ajuda baseados em XML para funções e scripts. Embora a ajuda baseada em comentários seja mais fácil de implementar, a ajuda baseada em XML é necessária se você quiser um controle mais preciso sobre o conteúdo da ajuda ou se estiver traduzindo tópicos da ajuda em vários idiomas. O exemplo a seguir mostra as primeiras linhas do `Update-Month.ps1` script. O script usa a `.ExternalHelp` palavra-chave para especificar o caminho para um tópico de ajuda baseado em XML para o script.

```powershell
#  .ExternalHelp C:\MyScripts\Update-Month-Help.xml

    param ([string]$InputPath, [string]$OutPutPath)

    function Get-Data { }
```

O exemplo a seguir mostra o uso da `.ExternalHelp` palavra-chave em uma função.

```powershell
function Add-Extension
{
    param ([string] $name, [string]$extension = "txt")
    $name = $name + "." + $extension
    $name

    # .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

## <a name="example-5--redirecting-to-a-different-help-topic"></a>Exemplo 5: redirecionando para um tópico de ajuda diferente

O código a seguir é um trecho do início da `Help` função interna no PowerShell, que exibe uma tela de texto de ajuda de cada vez. Como o tópico da ajuda para o cmdlet Get-Help descreve a função Help, a função Help usa `.ForwardHelpTargetName` as `.ForwardHelpCategory` palavras-chave e para redirecionar o usuário para o tópico de ajuda do cmdlet Get-Help.

```powershell
function help
{

    <#
      .FORWARDHELPTARGETNAME Get-Help
      .FORWARDHELPCATEGORY Cmdlet
    #>
    [CmdletBinding(DefaultParameterSetName='AllUsersView')]
    param(
            [Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
            [System.String]
            ${Name},
    ...
```

O comando a seguir usa esse recurso. Quando um usuário digita um `Get-Help` comando para a `Help` função, `Get-Help` o exibe o tópico da ajuda para o `Get-Help` cmdlet.

```powershell
C:\PS> get-help help
```

```Output
            NAME
                Get-Help

            SYNOPSIS
                Displays information about Windows PowerShell cmdlets and concepts.
            ...
```
