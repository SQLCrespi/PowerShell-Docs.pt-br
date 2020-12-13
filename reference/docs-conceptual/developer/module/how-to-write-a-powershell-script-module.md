---
ms.date: 11/21/2019
ms.topic: reference
title: Como escrever um módulo de script do Windows PowerShell
description: Como escrever um módulo de script do Windows PowerShell
ms.openlocfilehash: c44b09a915501fb10773ab11cf13136d5035ba69
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649152"
---
# <a name="how-to-write-a-powershell-script-module"></a>Como escrever um módulo de script do Windows PowerShell

Um módulo de script é qualquer script do PowerShell válido salvo em uma `.psm1` extensão. Essa extensão permite que o mecanismo do PowerShell use regras e cmdlets de módulo em seu arquivo. A maioria desses recursos está lá para ajudá-lo a instalar seu código em outros sistemas, bem como gerenciar o escopo. Você também pode usar um arquivo de manifesto de módulo, que descreve instalações e soluções mais complexas.

## <a name="writing-a-powershell-script-module"></a>Gravando um módulo de script do PowerShell

Para criar um módulo de script, salve um script do PowerShell válido em um `.psm1` arquivo. O script e o diretório em que ele está armazenado devem usar o mesmo nome. Por exemplo, um script chamado `MyPsScript.psm1` é armazenado em um diretório chamado `MyPsScript` .

O diretório do módulo precisa estar em um caminho especificado em `$env:PSModulePath` . O diretório do módulo pode conter todos os recursos necessários para executar o script e um arquivo de manifesto de módulo que descreve ao PowerShell como o módulo funciona.

## <a name="create-a-basic-powershell-module"></a>Criar um módulo do PowerShell básico

As etapas a seguir descrevem como criar um módulo do PowerShell.

1. Salve um script do PowerShell com uma `.psm1` extensão. Use o mesmo nome para o script e o diretório onde o script é salvo.

   Salvar um script com a `.psm1` extensão significa que você pode usar os cmdlets do módulo, como [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module). Os cmdlets de módulo existem principalmente para que você possa importar e exportar seu código para os sistemas de outros usuários. A solução alternativa seria carregar seu código em outros sistemas e, em seguida, criar uma origem de um ponto na memória ativa, o que não é uma solução escalonável. Para obter mais informações, consulte [noções básicas sobre um módulo do Windows PowerShell](./understanding-a-windows-powershell-module.md#module-cmdlets-and-variables).
   Por padrão, quando os usuários importam o `.psm1` arquivo, todas as funções em seu script são acessíveis, mas as variáveis não são.

   Um exemplo de script do PowerShell, intitulado `Show-Calendar` , está disponível no final deste artigo.

   ```powershell
   function Show-Calendar {
   param(
       [DateTime] $start = [DateTime]::Today,
       [DateTime] $end = $start,
       $firstDayOfWeek,
       [int[]] $highlightDay,
       [string[]] $highlightDate = [DateTime]::Today.ToString()
       )

       #actual code for the function goes here see the end of the topic for the complete code sample
   }
   ```

2. Para controlar o acesso do usuário a determinadas funções ou variáveis, chame [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) no final do script.

   O código de exemplo na parte inferior do artigo tem apenas uma função, que por padrão seria exposta. No entanto, é recomendável chamar explicitamente quais funções você deseja expor, conforme descrito no código a seguir:

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   Você pode restringir o que é importado usando um manifesto de módulo. Para obter mais informações, consulte [importando um módulo do PowerShell](./importing-a-powershell-module.md) e [como escrever um manifesto de módulo do PowerShell](./how-to-write-a-powershell-module-manifest.md).

3. Se você tiver módulos que seu próprio módulo precisa carregar, você pode usar `Import-Module` , na parte superior do módulo.

   O `Import-Module` cmdlet importa um módulo de destino para um sistema e pode ser usado em um ponto posterior no procedimento para instalar seu próprio módulo. O código de exemplo na parte inferior deste artigo não usa nenhum módulo de importação. Mas, se tiver feito isso, eles seriam listados na parte superior do arquivo, conforme mostrado no código a seguir:

   ```powershell
   Import-Module GenericModule
   ```

4. Para descrever seu módulo para o sistema de ajuda do PowerShell, você pode usar comentários de ajuda padrão dentro do arquivo ou criar um arquivo de ajuda adicional.

   O exemplo de código na parte inferior deste artigo inclui as informações de ajuda nos comentários. Você também pode gravar arquivos XML expandidos que contêm conteúdo de ajuda adicional. Para obter mais informações, consulte [escrevendo ajuda para módulos do Windows PowerShell](./writing-help-for-windows-powershell-modules.md).

5. Se você tiver módulos adicionais, arquivos XML ou outro conteúdo que deseja empacotar com seu módulo, poderá usar um manifesto de módulo.

   Um manifesto de módulo é um arquivo que contém os nomes de outros módulos, layouts de diretório, números de versão, dados de criação e outras partes de informações. O PowerShell usa o arquivo de manifesto de módulo para organizar e implantar sua solução. Para obter mais informações, consulte [como escrever um manifesto de módulo do PowerShell](./how-to-write-a-powershell-module-manifest.md).

6. Para instalar e executar o módulo, salve o módulo em um dos caminhos apropriados do PowerShell e use o `Import-Module` .

   Os caminhos em que você pode instalar o módulo estão localizados na `$env:PSModulePath` variável global. Por exemplo, um caminho comum para salvar um módulo em um sistema seria `%SystemRoot%/users/<user>/Documents/PowerShell/Modules/<moduleName>` . Certifique-se de criar um diretório para o módulo que usa o mesmo nome que o módulo de script, mesmo que ele seja apenas um único `.psm1` arquivo. Se você não salvou o módulo em um desses caminhos, precisaria especificar o local do módulo no `Import-Module` comando. Caso contrário, o PowerShell não poderá encontrar o módulo.

   A partir do PowerShell 3,0, se você colocou o módulo em um dos caminhos de módulo do PowerShell, não precisará importá-lo explicitamente. Seu módulo é carregado automaticamente quando um usuário chama sua função. Para obter mais informações sobre o caminho do módulo, consulte [importando um módulo do PowerShell](./importing-a-powershell-module.md) e [modificando o caminho de instalação do PSModulePath](./modifying-the-psmodulepath-installation-path.md).

7. Para remover um módulo do serviço ativo na sessão atual do PowerShell, use [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).

   > [!NOTE]
   > `Remove-Module` Remove um módulo da sessão atual do PowerShell, mas não desinstala o módulo nem exclui os arquivos do módulo.

## <a name="show-calendar-code-example"></a>Exemplo de código de Show-Calendar

O exemplo a seguir é um módulo de script que contém uma única função denominada `Show-Calendar` . Essa função exibe uma representação visual de um calendário. O exemplo contém as cadeias de caracteres de ajuda do PowerShell para Sinopse, descrição, valores de parâmetro e código. Quando o módulo é importado, o `Export-ModuleMember` comando garante que a `Show-Calendar` função seja exportada como um membro do módulo.

```powershell
<#
 .Synopsis
  Displays a visual representation of a calendar.

 .Description
  Displays a visual representation of a calendar. This function supports multiple months
  and lets you highlight specific date ranges or days.

 .Parameter Start
  The first month to display.

 .Parameter End
  The last month to display.

 .Parameter FirstDayOfWeek
  The day of the month on which the week begins.

 .Parameter HighlightDay
  Specific days (numbered) to highlight. Used for date ranges like (25..31).
  Date ranges are specified by the Windows PowerShell range syntax. These dates are
  enclosed in square brackets.

 .Parameter HighlightDate
  Specific days (named) to highlight. These dates are surrounded by asterisks.

 .Example
   # Show a default display of this month.
   Show-Calendar

 .Example
   # Display a date range.
   Show-Calendar -Start "March, 2010" -End "May, 2010"

 .Example
   # Highlight a range of days.
   Show-Calendar -HighlightDay (1..10 + 22) -HighlightDate "December 25, 2008"
#>
function Show-Calendar {
param(
    [DateTime] $start = [DateTime]::Today,
    [DateTime] $end = $start,
    $firstDayOfWeek,
    [int[]] $highlightDay,
    [string[]] $highlightDate = [DateTime]::Today.ToString()
    )

## Determine the first day of the start and end months.
$start = New-Object DateTime $start.Year,$start.Month,1
$end = New-Object DateTime $end.Year,$end.Month,1

## Convert the highlighted dates into real dates.
[DateTime[]] $highlightDate = [DateTime[]] $highlightDate

## Retrieve the DateTimeFormat information so that the
## calendar can be manipulated.
$dateTimeFormat  = (Get-Culture).DateTimeFormat
if($firstDayOfWeek)
{
    $dateTimeFormat.FirstDayOfWeek = $firstDayOfWeek
}

$currentDay = $start

## Process the requested months.
while($start -le $end)
{
    ## Return to an earlier point in the function if the first day of the month
    ## is in the middle of the week.
    while($currentDay.DayOfWeek -ne $dateTimeFormat.FirstDayOfWeek)
    {
        $currentDay = $currentDay.AddDays(-1)
    }

    ## Prepare to store information about this date range.
    $currentWeek = New-Object PsObject
    $dayNames = @()
    $weeks = @()

    ## Continue processing dates until the function reaches the end of the month.
    ## The function continues until the week is completed with
    ## days from the next month.
    while(($currentDay -lt $start.AddMonths(1)) -or
        ($currentDay.DayOfWeek -ne $dateTimeFormat.FirstDayOfWeek))
    {
        ## Determine the day names to use to label the columns.
        $dayName = "{0:ddd}" -f $currentDay
        if($dayNames -notcontains $dayName)
        {
            $dayNames += $dayName
        }

        ## Pad the day number for display, highlighting if necessary.
        $displayDay = " {0,2} " -f $currentDay.Day

        ## Determine whether to highlight a specific date.
        if($highlightDate)
        {
            $compareDate = New-Object DateTime $currentDay.Year,
                $currentDay.Month,$currentDay.Day
            if($highlightDate -contains $compareDate)
            {
                $displayDay = "*" + ("{0,2}" -f $currentDay.Day) + "*"
            }
        }

        ## Otherwise, highlight as part of a date range.
        if($highlightDay -and ($highlightDay[0] -eq $currentDay.Day))
        {
            $displayDay = "[" + ("{0,2}" -f $currentDay.Day) + "]"
            $null,$highlightDay = $highlightDay
        }

        ## Add the day of the week and the day of the month as note properties.
        $currentWeek | Add-Member NoteProperty $dayName $displayDay

        ## Move to the next day of the month.
        $currentDay = $currentDay.AddDays(1)

        ## If the function reaches the next week, store the current week
        ## in the week list and continue.
        if($currentDay.DayOfWeek -eq $dateTimeFormat.FirstDayOfWeek)
        {
            $weeks += $currentWeek
            $currentWeek = New-Object PsObject
        }
    }

    ## Format the weeks as a table.
    $calendar = $weeks | Format-Table $dayNames -AutoSize | Out-String

    ## Add a centered header.
    $width = ($calendar.Split("`n") | Measure-Object -Maximum Length).Maximum
    $header = "{0:MMMM yyyy}" -f $start
    $padding = " " * (($width - $header.Length) / 2)
    $displayCalendar = " `n" + $padding + $header + "`n " + $calendar
    $displayCalendar.TrimEnd()

    ## Move to the next month.
    $start = $start.AddMonths(1)

}
}
Export-ModuleMember -Function Show-Calendar
```
