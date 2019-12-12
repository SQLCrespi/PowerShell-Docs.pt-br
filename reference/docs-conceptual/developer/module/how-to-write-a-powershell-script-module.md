---
title: Como escrever um módulo de script do PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 11/21/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed7645ea-5e52-4a45-81a7-aa3c2d605cde
caps.latest.revision: 16
ms.openlocfilehash: 7742eedd67283535b9e5898adc74d0d48faf68fe
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74416265"
---
# <a name="how-to-write-a-powershell-script-module"></a><span data-ttu-id="8f274-102">Como escrever um módulo de script do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f274-102">How to Write a PowerShell Script Module</span></span>

<span data-ttu-id="8f274-103">Um módulo de script é qualquer script do PowerShell válido salvo em uma extensão `.psm1`.</span><span class="sxs-lookup"><span data-stu-id="8f274-103">A script module is any valid PowerShell script saved in a `.psm1` extension.</span></span> <span data-ttu-id="8f274-104">Essa extensão permite que o mecanismo do PowerShell use regras e cmdlets de módulo em seu arquivo.</span><span class="sxs-lookup"><span data-stu-id="8f274-104">This extension allows the PowerShell engine to use rules and module cmdlets on your file.</span></span> <span data-ttu-id="8f274-105">A maioria desses recursos está lá para ajudá-lo a instalar seu código em outros sistemas, bem como gerenciar o escopo.</span><span class="sxs-lookup"><span data-stu-id="8f274-105">Most of these capabilities are there to help you install your code on other systems, as well as manage scoping.</span></span> <span data-ttu-id="8f274-106">Você também pode usar um arquivo de manifesto de módulo, que descreve instalações e soluções mais complexas.</span><span class="sxs-lookup"><span data-stu-id="8f274-106">You can also use a module manifest file, which describes more complex installations and solutions.</span></span>

## <a name="writing-a-powershell-script-module"></a><span data-ttu-id="8f274-107">Gravando um módulo de script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f274-107">Writing a PowerShell script module</span></span>

<span data-ttu-id="8f274-108">Para criar um módulo de script, salve um script do PowerShell válido em um arquivo `.psm1`.</span><span class="sxs-lookup"><span data-stu-id="8f274-108">To create a script module, save a valid PowerShell script to a `.psm1` file.</span></span> <span data-ttu-id="8f274-109">O script e o diretório em que ele está armazenado devem usar o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="8f274-109">The script and the directory where it's stored must use the same name.</span></span> <span data-ttu-id="8f274-110">Por exemplo, um script chamado `MyPsScript.psm1` é armazenado em um diretório chamado `MyPsScript`.</span><span class="sxs-lookup"><span data-stu-id="8f274-110">For example, a script named `MyPsScript.psm1` is stored in a directory named `MyPsScript`.</span></span>

<span data-ttu-id="8f274-111">O diretório do módulo precisa estar em um caminho especificado em `$env:PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="8f274-111">The module's directory needs to be in a path specified in `$env:PSModulePath`.</span></span> <span data-ttu-id="8f274-112">O diretório do módulo pode conter todos os recursos necessários para executar o script e um arquivo de manifesto de módulo que descreve ao PowerShell como o módulo funciona.</span><span class="sxs-lookup"><span data-stu-id="8f274-112">The module's directory can contain any resources that are needed to run the script, and a module manifest file that describes to PowerShell how your module works.</span></span>

## <a name="create-a-basic-powershell-module"></a><span data-ttu-id="8f274-113">Criar um módulo do PowerShell básico</span><span class="sxs-lookup"><span data-stu-id="8f274-113">Create a basic PowerShell module</span></span>

<span data-ttu-id="8f274-114">As etapas a seguir descrevem como criar um módulo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f274-114">The following steps describe how to create a PowerShell module.</span></span>

1. <span data-ttu-id="8f274-115">Salve um script do PowerShell com uma extensão `.psm1`.</span><span class="sxs-lookup"><span data-stu-id="8f274-115">Save a PowerShell script with a `.psm1` extension.</span></span> <span data-ttu-id="8f274-116">Use o mesmo nome para o script e o diretório onde o script é salvo.</span><span class="sxs-lookup"><span data-stu-id="8f274-116">Use the same name for the script and the directory where the script is saved.</span></span>

   <span data-ttu-id="8f274-117">Salvar um script com a extensão `.psm1` significa que você pode usar os cmdlets do módulo, como [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span><span class="sxs-lookup"><span data-stu-id="8f274-117">Saving a script with the `.psm1` extension means that you can use the module cmdlets, such as [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span></span> <span data-ttu-id="8f274-118">Os cmdlets de módulo existem principalmente para que você possa importar e exportar seu código para os sistemas de outros usuários.</span><span class="sxs-lookup"><span data-stu-id="8f274-118">The module cmdlets exist primarily so that you can import and export your code onto other user's systems.</span></span> <span data-ttu-id="8f274-119">A solução alternativa seria carregar seu código em outros sistemas e, em seguida, criar uma origem de um ponto na memória ativa, o que não é uma solução escalonável.</span><span class="sxs-lookup"><span data-stu-id="8f274-119">The alternate solution would be to load your code on other systems and then dot-source it into active memory, which isn't a scalable solution.</span></span> <span data-ttu-id="8f274-120">Para obter mais informações, consulte [noções básicas sobre um módulo do Windows PowerShell](./understanding-a-windows-powershell-module.md#module-cmdlets-and-variables).</span><span class="sxs-lookup"><span data-stu-id="8f274-120">For more information, see [Understanding a Windows PowerShell Module](./understanding-a-windows-powershell-module.md#module-cmdlets-and-variables).</span></span>
   <span data-ttu-id="8f274-121">Por padrão, quando os usuários importam seu arquivo de `.psm1`, todas as funções em seu script são acessíveis, mas as variáveis não são.</span><span class="sxs-lookup"><span data-stu-id="8f274-121">By default, when users import your `.psm1` file, all functions in your script are accessible, but variables aren't.</span></span>

   <span data-ttu-id="8f274-122">Um exemplo de script do PowerShell, intitulado `Show-Calendar`, está disponível no final deste artigo.</span><span class="sxs-lookup"><span data-stu-id="8f274-122">An example PowerShell script, entitled `Show-Calendar`, is available at the end of this article.</span></span>

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

2. <span data-ttu-id="8f274-123">Para controlar o acesso do usuário a determinadas funções ou variáveis, chame [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) no final do script.</span><span class="sxs-lookup"><span data-stu-id="8f274-123">To control user access to certain functions or variables, call [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) at the end of your script.</span></span>

   <span data-ttu-id="8f274-124">O código de exemplo na parte inferior do artigo tem apenas uma função, que por padrão seria exposta.</span><span class="sxs-lookup"><span data-stu-id="8f274-124">The example code at the bottom of the article has only one function, which by default would be exposed.</span></span> <span data-ttu-id="8f274-125">No entanto, é recomendável chamar explicitamente quais funções você deseja expor, conforme descrito no código a seguir:</span><span class="sxs-lookup"><span data-stu-id="8f274-125">However, it's recommended you explicitly call out which functions you wish to expose, as described in the following code:</span></span>

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   <span data-ttu-id="8f274-126">Você pode restringir o que é importado usando um manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="8f274-126">You can restrict what's imported using a module manifest.</span></span> <span data-ttu-id="8f274-127">Para obter mais informações, consulte [importando um módulo do PowerShell](./importing-a-powershell-module.md) e [como escrever um manifesto de módulo do PowerShell](./how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="8f274-127">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [How to Write a PowerShell Module Manifest](./how-to-write-a-powershell-module-manifest.md).</span></span>

3. <span data-ttu-id="8f274-128">Se você tiver módulos que seu próprio módulo precisa carregar, você pode usar `Import-Module`, na parte superior do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f274-128">If you have modules that your own module needs to load, you can use `Import-Module`, at the top of your module.</span></span>

   <span data-ttu-id="8f274-129">O cmdlet `Import-Module` importa um módulo de destino para um sistema e pode ser usado em um ponto posterior no procedimento para instalar seu próprio módulo.</span><span class="sxs-lookup"><span data-stu-id="8f274-129">The `Import-Module` cmdlet imports a targeted module onto a system, and can be used at a later point in the procedure to install your own module.</span></span> <span data-ttu-id="8f274-130">O código de exemplo na parte inferior deste artigo não usa nenhum módulo de importação.</span><span class="sxs-lookup"><span data-stu-id="8f274-130">The sample code at the bottom of this article doesn't use any import modules.</span></span> <span data-ttu-id="8f274-131">Mas, se tiver feito isso, eles seriam listados na parte superior do arquivo, conforme mostrado no código a seguir:</span><span class="sxs-lookup"><span data-stu-id="8f274-131">But if it did, they would be listed at the top of the file, as shown in the following code:</span></span>

   ```powershell
   Import-Module GenericModule
   ```

4. <span data-ttu-id="8f274-132">Para descrever seu módulo para o sistema de ajuda do PowerShell, você pode usar comentários de ajuda padrão dentro do arquivo ou criar um arquivo de ajuda adicional.</span><span class="sxs-lookup"><span data-stu-id="8f274-132">To describe your module to the PowerShell Help system, you can either use standard help comments inside the file, or create an additional Help file.</span></span>

   <span data-ttu-id="8f274-133">O exemplo de código na parte inferior deste artigo inclui as informações de ajuda nos comentários.</span><span class="sxs-lookup"><span data-stu-id="8f274-133">The code sample at the bottom of this article includes the help information in the comments.</span></span> <span data-ttu-id="8f274-134">Você também pode gravar arquivos XML expandidos que contêm conteúdo de ajuda adicional.</span><span class="sxs-lookup"><span data-stu-id="8f274-134">You could also write expanded XML files that contain additional help content.</span></span> <span data-ttu-id="8f274-135">Para obter mais informações, consulte [escrevendo ajuda para módulos do Windows PowerShell](./writing-help-for-windows-powershell-modules.md).</span><span class="sxs-lookup"><span data-stu-id="8f274-135">For more information, see [Writing Help for Windows PowerShell Modules](./writing-help-for-windows-powershell-modules.md).</span></span>

5. <span data-ttu-id="8f274-136">Se você tiver módulos adicionais, arquivos XML ou outro conteúdo que deseja empacotar com seu módulo, poderá usar um manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="8f274-136">If you have additional modules, XML files, or other content you want to package with your module, you can use a module manifest.</span></span>

   <span data-ttu-id="8f274-137">Um manifesto de módulo é um arquivo que contém os nomes de outros módulos, layouts de diretório, números de versão, dados de criação e outras partes de informações.</span><span class="sxs-lookup"><span data-stu-id="8f274-137">A module manifest is a file that contains the names of other modules, directory layouts, versioning numbers, author data, and other pieces of information.</span></span> <span data-ttu-id="8f274-138">O PowerShell usa o arquivo de manifesto de módulo para organizar e implantar sua solução.</span><span class="sxs-lookup"><span data-stu-id="8f274-138">PowerShell uses the module manifest file to organize and deploy your solution.</span></span> <span data-ttu-id="8f274-139">Para obter mais informações, consulte [como escrever um manifesto de módulo do PowerShell](./how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="8f274-139">For more information, see [How to write a PowerShell module manifest](./how-to-write-a-powershell-module-manifest.md).</span></span>

6. <span data-ttu-id="8f274-140">Para instalar e executar o módulo, salve o módulo em um dos caminhos apropriados do PowerShell e use `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="8f274-140">To install and run your module, save the module to one of the appropriate PowerShell paths, and use `Import-Module`.</span></span>

   <span data-ttu-id="8f274-141">Os caminhos em que você pode instalar o módulo estão localizados na variável global `$env:PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="8f274-141">The paths where you can install your module are located in the `$env:PSModulePath` global variable.</span></span> <span data-ttu-id="8f274-142">Por exemplo, um caminho comum para salvar um módulo em um sistema seria `%SystemRoot%/users/<user>/Documents/PowerShell/Modules/<moduleName>`.</span><span class="sxs-lookup"><span data-stu-id="8f274-142">For example, a common path to save a module on a system would be `%SystemRoot%/users/<user>/Documents/PowerShell/Modules/<moduleName>`.</span></span> <span data-ttu-id="8f274-143">Certifique-se de criar um diretório para o módulo que usa o mesmo nome que o módulo de script, mesmo que ele seja apenas um único arquivo de `.psm1`.</span><span class="sxs-lookup"><span data-stu-id="8f274-143">Be sure to create a directory for your module that uses the same name as the script module, even if it's only a single `.psm1` file.</span></span> <span data-ttu-id="8f274-144">Se você não salvou o módulo em um desses caminhos, precisaria especificar o local do módulo no comando `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="8f274-144">If you didn't save your module to one of these paths, you would have to specify the module's location in the `Import-Module` command.</span></span> <span data-ttu-id="8f274-145">Caso contrário, o PowerShell não poderá encontrar o módulo.</span><span class="sxs-lookup"><span data-stu-id="8f274-145">Otherwise, PowerShell wouldn't be able to find the module.</span></span>

   <span data-ttu-id="8f274-146">A partir do PowerShell 3,0, se você colocou o módulo em um dos caminhos de módulo do PowerShell, não precisará importá-lo explicitamente.</span><span class="sxs-lookup"><span data-stu-id="8f274-146">Starting with PowerShell 3.0, if you've placed your module in one of the PowerShell module paths, you don't need to explicitly import it.</span></span> <span data-ttu-id="8f274-147">Seu módulo é carregado automaticamente quando um usuário chama sua função.</span><span class="sxs-lookup"><span data-stu-id="8f274-147">Your module is automatically loaded when a user calls your function.</span></span> <span data-ttu-id="8f274-148">Para obter mais informações sobre o caminho do módulo, consulte [importando um módulo do PowerShell](./importing-a-powershell-module.md) e [modificando o caminho de instalação do PSModulePath](./modifying-the-psmodulepath-installation-path.md).</span><span class="sxs-lookup"><span data-stu-id="8f274-148">For more information about the module path, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [Modifying the PSModulePath Installation Path](./modifying-the-psmodulepath-installation-path.md).</span></span>

7. <span data-ttu-id="8f274-149">Para remover um módulo do serviço ativo na sessão atual do PowerShell, use [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).</span><span class="sxs-lookup"><span data-stu-id="8f274-149">To remove a module from active service in the current PowerShell session, use [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).</span></span>

   > [!NOTE]
   > <span data-ttu-id="8f274-150">`Remove-Module` remove um módulo da sessão atual do PowerShell, mas não desinstala o módulo nem exclui os arquivos do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f274-150">`Remove-Module` removes a module from the current PowerShell session, but doesn't uninstall the module or delete the module's files.</span></span>

## <a name="show-calendar-code-example"></a><span data-ttu-id="8f274-151">Mostrar-exemplo de código do calendário</span><span class="sxs-lookup"><span data-stu-id="8f274-151">Show-Calendar code example</span></span>

<span data-ttu-id="8f274-152">O exemplo a seguir é um módulo de script que contém uma única função chamada `Show-Calendar`.</span><span class="sxs-lookup"><span data-stu-id="8f274-152">The following example is a script module that contains a single function named `Show-Calendar`.</span></span> <span data-ttu-id="8f274-153">Essa função exibe uma representação visual de um calendário.</span><span class="sxs-lookup"><span data-stu-id="8f274-153">This function displays a visual representation of a calendar.</span></span> <span data-ttu-id="8f274-154">O exemplo contém as cadeias de caracteres de ajuda do PowerShell para Sinopse, descrição, valores de parâmetro e código.</span><span class="sxs-lookup"><span data-stu-id="8f274-154">The sample contains the PowerShell Help strings for the synopsis, description, parameter values, and code.</span></span> <span data-ttu-id="8f274-155">Quando o módulo é importado, o comando `Export-ModuleMember` garante que a função `Show-Calendar` seja exportada como um membro do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f274-155">When the module is imported, the `Export-ModuleMember` command ensures that the `Show-Calendar` function is exported as a module member.</span></span>

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
