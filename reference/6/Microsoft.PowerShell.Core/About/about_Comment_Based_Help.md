---
description: Descreve como escrever tópicos de ajuda baseados em comentários para funções e scripts.
keywords: powershell, cmdlet
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comment_based_help?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comment_Based_Help
ms.openlocfilehash: 3860f6aa8a494b696d78433ec23c100c1d57fca2
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195774"
---
# <a name="about-comment-based-help"></a>Sobre a ajuda baseada em comentários

## <a name="short-description"></a>Descrição breve
Descreve como escrever tópicos de ajuda baseados em comentários para funções e scripts.

## <a name="long-description"></a>Descrição longa

Você pode escrever tópicos de ajuda baseados em comentários para funções e scripts usando palavras-chave de comentário de ajuda especial.

O cmdlet [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) exibe a ajuda baseada em comentários no mesmo formato em que ele exibe os tópicos de ajuda do cmdlet que são gerados a partir de arquivos XML. Os usuários podem usar todos os parâmetros do `Get-Help` , como **detalhado** , **completo** , **exemplos** e **online** , para exibir o conteúdo da ajuda baseada em comentários.

Você também pode gravar arquivos de ajuda baseados em XML para funções e scripts. Para habilitar o `Get-Help` cmdlet para localizar o arquivo de ajuda baseado em XML para uma função ou um script, use a `.ExternalHelp` palavra-chave. Sem essa palavra-chave, `Get-Help` não é possível encontrar tópicos de ajuda baseados em XML para funções ou scripts.

Este tópico explica como escrever tópicos de ajuda para funções e scripts. Para obter informações sobre como exibir tópicos da ajuda para funções e scripts, consulte [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help).

Os cmdlets [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help) e [Save-Help](xref:Microsoft.PowerShell.Core.Save-Help) funcionam apenas em arquivos XML. A ajuda atualizável não oferece suporte a tópicos de ajuda baseados em comentários.

## <a name="syntax-for-comment-based-help"></a>Sintaxe para ajuda baseada em comentários

A sintaxe da ajuda baseada em comentários é a seguinte:

```
# .<help keyword>
# <help content>
```

ou

```
<#
.<help keyword>
<help content>
#>
```

A ajuda baseada em comentários é escrita como uma série de comentários. Você pode digitar um símbolo de comentário `#` antes de cada linha de comentários ou pode usar os `<#` `#>` símbolos e para criar um bloco de comentários. Todas as linhas dentro do bloco de comentários são interpretadas como comentários.

Todas as linhas em um tópico de ajuda com base em comentários devem ser contíguas. Se um tópico de ajuda baseado em comentário seguir um comentário que não faz parte do tópico da ajuda, deve haver pelo menos uma linha em branco entre a última linha de comentário de não ajuda e o início da ajuda baseada em comentários.

As palavras-chave definem cada seção da ajuda baseada em comentários. Cada palavra-chave de ajuda baseada em comentários é precedida por um ponto `.` . As palavras-chave podem aparecer em qualquer ordem. Os nomes de palavra-chave não diferenciam maiúsculas de minúsculas.

Por exemplo, a `.Description` palavra-chave precede uma descrição de uma função ou script.

```
<#
.Description
Get-Function displays the name and syntax of all functions in the session.
#>
```

O bloco de comentário deve conter pelo menos uma palavra-chave. Algumas das palavras-chave, como `.EXAMPLE` , podem aparecer muitas vezes no mesmo bloco de comentário. O conteúdo da ajuda para cada palavra-chave começa na linha após a palavra-chave e pode abranger várias linhas.

## <a name="syntax-for-comment-based-help-in-functions"></a>Sintaxe para ajuda baseada em comentários em funções

A ajuda baseada em comentários para uma função pode aparecer em um dos três locais:

- No início do corpo da função.
- No final do corpo da função.
- Antes da `function` palavra-chave. Não pode haver mais de uma linha em branco entre a última linha da ajuda da função e a `function` palavra-chave.

Por exemplo:

```powershell
function Get-Function
{
<#
.<help keyword>
<help content>
#>

  # function logic
}
```

ou

```powershell
function Get-Function
{
   # function logic

<#
.<help keyword>
<help content>
#>
}
```

ou

```powershell
<#
.<help keyword>
<help content>
#>
function Get-Function { }
```

## <a name="syntax-for-comment-based-help-in-scripts"></a>Sintaxe para ajuda baseada em comentários em scripts

A ajuda baseada em comentários para um script pode aparecer em um dos dois locais a seguir no script.

- No início do arquivo de script. A ajuda do script pode ser precedida no script somente por comentários e linhas em branco.

  Se o primeiro item no corpo do script (após a ajuda) for uma declaração de função, deve haver pelo menos duas linhas em branco entre o final da ajuda do script e a declaração da função. Caso contrário, a ajuda será interpretada como sendo ajuda para a função, não ajuda para o script.

- No final do arquivo de script. No entanto, se o script for assinado, coloque a ajuda baseada em comentários no início do arquivo de script. O final do script é ocupado pelo bloco de assinatura.

Por exemplo:

```powershell
<#
.<help keyword>
<help content>
#>


function Get-Function { }
```

ou

```powershell
function Get-Function { }

<#
.<help keyword>
<help content>
#>
```

## <a name="syntax-for-comment-based-help-in-script-modules"></a>Sintaxe para ajuda baseada em comentários em módulos de script

Em um módulo de script `.psm1` , a ajuda baseada em comentários usa a sintaxe para funções, não a sintaxe para scripts. Você não pode usar a sintaxe de script para fornecer ajuda para todas as funções definidas em um módulo de script.

Por exemplo, se você estiver usando a `.ExternalHelp` palavra-chave para identificar os arquivos de ajuda baseados em XML para as funções em um módulo de script, deverá adicionar um `.ExternalHelp` comentário a cada função.

```powershell
# .ExternalHelp <XML-file-name>
function <function-name>
{
  ...
}
```

## <a name="comment-based-help-keywords"></a>Palavras-chave de ajuda com base em comentários

Veja a seguir as palavras-chave de ajuda com base em comentários válidas. Eles são listados na ordem em que normalmente aparecem em um tópico da ajuda junto com o uso pretendido. Essas palavras-chave podem aparecer em qualquer ordem na Ajuda baseada em comentários e não diferenciam maiúsculas de minúsculas.

### <a name="synopsis"></a>. Resumo

Uma breve descrição da função ou do script. Essa palavra-chave pode ser usada apenas uma vez em cada tópico.

### <a name="description"></a>. NDESCRIÇÃO

Uma descrição detalhada da função ou do script. Essa palavra-chave pode ser usada apenas uma vez em cada tópico.

### <a name="parameter"></a>. METER

A descrição de um parâmetro. Adicione uma `.PARAMETER` palavra-chave para cada parâmetro na sintaxe da função ou do script.

Digite o nome do parâmetro na mesma linha que a `.PARAMETER` palavra-chave. Digite a descrição do parâmetro nas linhas que seguem a `.PARAMETER` palavra-chave. O Windows PowerShell interpreta todo o texto entre a `.PARAMETER` linha e a palavra-chave Next ou o final do bloco de comentários como parte da descrição do parâmetro.
A descrição pode incluir quebras de parágrafo.

```
.PARAMETER  <Parameter-Name>
```

As palavras-chave do parâmetro podem aparecer em qualquer ordem no bloco de comentários, mas a sintaxe da função ou do script determina a ordem na qual os parâmetros (e suas descrições) aparecem no tópico da ajuda. Para alterar a ordem, altere a sintaxe.

Você também pode especificar uma descrição de parâmetro colocando um comentário na sintaxe da função ou do script imediatamente antes do nome da variável de parâmetro. Para que isso funcione, você também deve ter um bloco de comentário com pelo menos uma palavra-chave.

Se você usar um comentário de sintaxe e uma `.PARAMETER` palavra-chave, a descrição associada à `.PARAMETER` palavra-chave será usada e o comentário de sintaxe será ignorado.

```powershell
<#
.SYNOPSIS
    Short description here
#>
function Verb-Noun {
    [CmdletBinding()]
    param (
        # This is the same as .Parameter
        [string]$Computername
    )
    # Verb the Noun on the computer
}
```

### <a name="example"></a>. EXEMPLO

Um comando de exemplo que usa a função ou o script, opcionalmente seguido por saída de exemplo e uma descrição. Repita essa palavra-chave para cada exemplo.

### <a name="inputs"></a>. INFORMAÇÕES

Os tipos .NET de objetos que podem ser canalizados para a função ou o script. Você também pode incluir uma descrição dos objetos de entrada.

### <a name="outputs"></a>. PRODUZ

O tipo .NET dos objetos que o cmdlet retorna. Você também pode incluir uma descrição dos objetos retornados.

### <a name="notes"></a>. REGISTRA

Informações adicionais sobre a função ou o script.

### <a name="link"></a>. CRIAR

O nome de um tópico relacionado. O valor aparece na linha abaixo da ". LINK "palavra-chave e deve ser precedido por um símbolo de comentário `#` ou incluído no bloco de comentários.

Repita a `.LINK` palavra-chave para cada tópico relacionado.

Esse conteúdo aparece na seção links relacionados do tópico da ajuda.

O `.Link` conteúdo da palavra-chave também pode incluir um URI (Uniform Resource Identifier) em uma versão online do mesmo tópico da ajuda. A versão online é aberta quando você usa o parâmetro **online** do `Get-Help` . O URI deve começar com "http" ou "https".

### <a name="component"></a>. COMPONENTE

O nome da tecnologia ou do recurso que a função ou o script usa, ou ao qual ele está relacionado. O parâmetro de **componente** do `Get-Help` usa esse valor para filtrar os resultados da pesquisa retornados por `Get-Help` .

### <a name="role"></a>. CARGO

O nome da função de usuário para o tópico da ajuda. O parâmetro de **função** de `Get-Help` usa esse valor para filtrar os resultados de pesquisa retornados por `Get-Help` .

### <a name="functionality"></a>. FUNÇÃO

As palavras-chave que descrevem o uso pretendido da função. O parâmetro de **funcionalidade** do `Get-Help` usa esse valor para filtrar os resultados da pesquisa retornados por `Get-Help` .

### <a name="forwardhelptargetname"></a>. FORWARDHELPTARGETNAME

Redireciona para o tópico da ajuda para o comando especificado. Você pode redirecionar os usuários para qualquer tópico da ajuda, incluindo tópicos de ajuda para uma função, script, cmdlet ou provedor.

```powershell
# .FORWARDHELPTARGETNAME <Command-Name>
```

### <a name="forwardhelpcategory"></a>. FORWARDHELPCATEGORY

Especifica a categoria de ajuda do item no `.ForwardHelpTargetName` . Os valores válidos são,,,,,,, `Alias` `Cmdlet` `HelpFile` `Function` `Provider` `General` `FAQ` `Glossary` , `ScriptCommand` , `ExternalScript` , `Filter` ou `All` . Use essa palavra-chave para evitar conflitos quando houver comandos com o mesmo nome.

```powershell
# .FORWARDHELPCATEGORY <Category>
```

### <a name="remotehelprunspace"></a>. REMOTEHELPRUNSPACE

Especifica uma sessão que contém o tópico da ajuda. Insira uma variável que contenha um objeto **PSSession** . Essa palavra-chave é usada pelo cmdlet [Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession) para localizar os tópicos da ajuda para os comandos exportados.

```powershell
# .REMOTEHELPRUNSPACE <PSSession-variable>
```

### <a name="externalhelp"></a>. EXTERNALHELP

Especifica um arquivo de ajuda baseado em XML para o script ou função.

```powershell
# .EXTERNALHELP <XML Help File>
```

A `.ExternalHelp` palavra-chave é necessária quando uma função ou script é documentado em arquivos XML. Sem essa palavra-chave, `Get-Help` não é possível encontrar o arquivo de ajuda baseado em XML para a função ou o script.

A `.ExternalHelp` palavra-chave tem precedência sobre outras palavras-chaves de ajuda baseadas em comentários. Se `.ExternalHelp` estiver presente, `Get-Help` o não exibirá a ajuda baseada em comentários, mesmo que ele não encontre um tópico de ajuda que corresponda ao valor da `.ExternalHelp` palavra-chave.

Se a função for exportada por um módulo, defina o valor da `.ExternalHelp` palavra-chave como um nome de arquivo sem um caminho. `Get-Help` procura o nome de arquivo especificado em um subdiretório específico do idioma do diretório do módulo. Não há requisitos para o nome do arquivo de ajuda baseado em XML para uma função, mas uma prática recomendada é usar o seguinte formato:

```
<ScriptModule.psm1>-help.xml
```

Se a função não estiver incluída em um módulo, inclua um caminho para o arquivo de ajuda baseado em XML. Se o valor incluir um caminho e o caminho contiver subdiretórios específicos da cultura da interface do usuário, `Get-Help` o pesquisará os subdiretórios recursivamente para um arquivo XML com o nome do script ou função de acordo com os padrões de fallback de idioma estabelecidos para o Windows, assim como em um diretório de módulo.

Para obter mais informações sobre o formato de arquivo de ajuda baseado em XML da ajuda do cmdlet, consulte [como gravar a ajuda do cmdlet](https://go.microsoft.com/fwlink/?LinkID=123415) na biblioteca do MSDN.

## <a name="autogenerated-content"></a>Conteúdo gerado automaticamente

O nome, a sintaxe, a lista de parâmetros, a tabela de atributo de parâmetro, os parâmetros comuns e os comentários são gerados automaticamente pelo `Get-Help` cmdlet.

### <a name="name"></a>Name

A seção **nome** de um tópico da ajuda da função é extraída do nome da função na sintaxe da função. O **nome** de um tópico de ajuda de script é obtido do nome de arquivo do script. Para alterar o nome ou sua capitalização, altere a sintaxe da função ou o nome de arquivo do script.

### <a name="syntax"></a>Syntax

A seção de **sintaxe** do tópico da ajuda é gerada a partir da sintaxe da função ou do script. Para adicionar detalhes à sintaxe do tópico da ajuda, como o tipo .NET de um parâmetro, adicione os detalhes à sintaxe. Se você não especificar um tipo de parâmetro, o tipo de **objeto** será inserido como o valor padrão.

### <a name="parameter-list"></a>Lista de parâmetros

A lista de parâmetros no tópico da ajuda é gerada a partir da sintaxe da função ou do script e das descrições que você adiciona usando a `.Parameter` palavra-chave. Os parâmetros de função aparecem na seção de **parâmetros** do tópico da ajuda na mesma ordem em que aparecem na sintaxe da função ou do script. A grafia e a capitalização dos nomes de parâmetro também são extraídas da sintaxe. Ele não é afetado pelo nome do parâmetro especificado pela `.Parameter` palavra-chave.

### <a name="common-parameters"></a>Parâmetros comuns

Os **parâmetros comuns** são adicionados à sintaxe e à lista de parâmetros do tópico da ajuda, mesmo que eles não tenham efeito. Para obter mais informações sobre os parâmetros comuns, consulte [about_CommonParameters](about_CommonParameters.md).

### <a name="parameter-attribute-table"></a>Tabela de atributos de parâmetro

`Get-Help` gera a tabela de atributos de parâmetro que aparece quando você usa o parâmetro **Full** **ou Parameter** de `Get-Help` . O valor dos atributos **obrigatório** , **posição** e valor **padrão** é obtido da sintaxe da função ou do script.

Os valores padrão e um valor para **aceitar caracteres curinga** não aparecem na tabela de atributos de parâmetro mesmo quando eles são definidos na função ou script. Para ajudar os usuários, forneça essas informações na descrição do parâmetro.

### <a name="remarks"></a>Comentários

A seção **comentários** do tópico da ajuda é gerada automaticamente a partir do nome da função ou do script. Você não pode alterar ou afetar seu conteúdo.

## <a name="examples"></a>Exemplos

### <a name="comment-based-help-for-a-function"></a>Ajuda baseada em comentários para uma função

A seguinte função de exemplo inclui ajuda baseada em comentários:

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

System.String. Add-Extension returns a string with the extension
or file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

Os resultados são os seguintes:

```powershell
Get-Help -Name "Add-Extension" -Full
```

```Output
NAME

Add-Extension

SYNOPSIS

Adds a file name extension to a supplied name.

SYNTAX

Add-Extension [[-Name] <String>] [[-Extension] <String>]
[<CommonParameters>]

DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

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

System.String. Add-Extension returns a string with the extension or
file name.

Example 1

PS> extension -name "File"
File.txt

Example 2

PS> extension -name "File" -extension "doc"
File.doc

Example 3

PS> extension "File" "doc"
File.doc

RELATED LINKS

http://www.fabrikam.com/extension.html
Set-Item
```

### <a name="parameter-descriptions-in-function-syntax"></a>Descrições de parâmetro na sintaxe de função

Este exemplo é o mesmo que o anterior, exceto que as descrições de parâmetro são inseridas na sintaxe da função. Esse formato é mais útil quando as descrições são breves.

```powershell
function Add-Extension
{
param
(

[string]
#Specifies the file name.
$name,

[string]
#Specifies the file name extension. "Txt" is the default.
$extension = "txt"
)

$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

### <a name="comment-based-help-for-a-script"></a>Ajuda baseada em comentários para um script

O script de exemplo a seguir inclui ajuda baseada em comentários. Observe as linhas em branco entre o fechamento `#>` e a `Param` instrução. Em um script que não tem uma `Param` instrução, deve haver pelo menos duas linhas em branco entre o comentário final no tópico da ajuda e a primeira declaração da função. Sem essas linhas em branco, `Get-Help` o associa o tópico da ajuda à função, não ao script.

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

PS> .\Update-Month.ps1

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath `
C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
...
```

O comando a seguir obtém a ajuda do script. Como o script não está em um diretório listado na `$env:Path` variável de ambiente, o `Get-Help` comando que obtém a ajuda do script deve especificar o caminho do script.

```powershell
Get-Help -Path .\update-month.ps1 -Full
```

```Output
# NAME

C:\ps-test\Update-Month.ps1

# SYNOPSIS

Performs monthly data updates.

# SYNTAX

C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
<String>] [<CommonParameters>]

# DESCRIPTION

The Update-Month.ps1 script updates the registry with new data
generated during the past month and generates a report.

# PARAMETERS

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

# INPUTS

None. You cannot pipe objects to Update-Month.ps1.

# OUTPUTS

None. Update-Month.ps1 does not generate any output.

Example 1

PS> .\Update-Month.ps1

Example 2

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

Example 3

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
C:\Reports\2009\January.csv

# RELATED LINKS
```

### <a name="redirecting-to-an-xml-file"></a>Redirecionando para um arquivo XML

Você pode escrever tópicos de ajuda baseados em XML para funções e scripts. Embora a ajuda baseada em comentários seja mais fácil de implementar, a ajuda baseada em XML é necessária para a ajuda atualizável e para fornecer tópicos de ajuda em vários idiomas.

O exemplo a seguir mostra as primeiras linhas do script de Update-Month.ps1.
O script usa a `.ExternalHelp` palavra-chave para especificar o caminho para um tópico de ajuda baseado em XML para o script.

Observe que o valor da `.ExternalHelp` palavra-chave é exibido na mesma linha que a palavra-chave. Qualquer outro posicionamento é ineficaz.

```powershell
# .ExternalHelp C:\MyScripts\Update-Month-Help.xml

param ([string]$InputPath, [string]$OutPutPath)
function Get-Data { }
...
```

Os exemplos a seguir mostram três posicionamentos válidos da `.ExternalHelp` palavra-chave em uma função.

```powershell
function Add-Extension
{
# .ExternalHelp C:\ps-test\Add-Extension.xml

param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

```powershell
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name

# .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

```powershell
# .ExternalHelp C:\ps-test\Add-Extension.xml
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

### <a name="redirecting-to-a-different-help-topic"></a>Redirecionando para um tópico de ajuda diferente

O código a seguir é um trecho do início da função de ajuda interna no PowerShell, que exibe uma tela de texto de ajuda de cada vez.
Como o tópico da ajuda para o `Get-Help` cmdlet descreve a função de ajuda, a função de ajuda usa as `.ForwardHelpTargetName` `.ForwardHelpCategory` palavras-chave e para redirecionar o usuário para o `Get-Help` tópico de ajuda do cmdlet.

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

O comando a seguir usa esse recurso:

```powershell
Get-Help -Name help
```

```Output
NAME

Get-Help

SYNOPSIS

Displays information about PowerShell cmdlets and concepts.
...
```

## <a name="see-also"></a>Confira também

[about_Functions](about_Functions.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Scripts](about_Scripts.md)

[Como escrever ajuda de cmdlet](https://go.microsoft.com/fwlink/?LinkID=123415)
