---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-modulemember?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ModuleMember
ms.openlocfilehash: 447cfe74c350286dcf396bde7ea8f442e39d637f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194768"
---
# <span data-ttu-id="bebc4-103">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="bebc4-103">Export-ModuleMember</span></span>

## <span data-ttu-id="bebc4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="bebc4-104">SYNOPSIS</span></span>
<span data-ttu-id="bebc4-105">Especifica os membros do módulo que são exportados.</span><span class="sxs-lookup"><span data-stu-id="bebc4-105">Specifies the module members that are exported.</span></span>

## <span data-ttu-id="bebc4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bebc4-106">SYNTAX</span></span>

```
Export-ModuleMember [[-Function] <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="bebc4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bebc4-107">DESCRIPTION</span></span>

<span data-ttu-id="bebc4-108">O cmdlet **Export-ModuleMember** especifica os membros do módulo que são exportados de um arquivo de módulo de script (. psm1) ou de um módulo dinâmico criado usando o cmdlet New-Module.</span><span class="sxs-lookup"><span data-stu-id="bebc4-108">The **Export-ModuleMember** cmdlet specifies the module members that are exported from a script module (.psm1) file, or from a dynamic module created by using the New-Module cmdlet.</span></span>
<span data-ttu-id="bebc4-109">Os membros do módulo incluem cmdlets, funções, variáveis e aliases.</span><span class="sxs-lookup"><span data-stu-id="bebc4-109">Module members include cmdlets, functions, variables, and aliases.</span></span>
<span data-ttu-id="bebc4-110">Esse cmdlet pode ser usado somente em um arquivo de módulo de script ou um módulo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="bebc4-110">This cmdlet can be used only in a script module file or a dynamic module.</span></span>

<span data-ttu-id="bebc4-111">Se um módulo de script não incluir um comando **Export-ModuleMember** , as funções e os aliases no módulo de script serão exportados, mas as variáveis não serão.</span><span class="sxs-lookup"><span data-stu-id="bebc4-111">If a script module does not include an **Export-ModuleMember** command, the functions and aliases in the script module are exported, but the variables are not.</span></span>
<span data-ttu-id="bebc4-112">Quando um módulo de script inclui comandos **Export-ModuleMember** , somente os membros especificados nos comandos **Export-ModuleMember** são exportados.</span><span class="sxs-lookup"><span data-stu-id="bebc4-112">When a script module includes **Export-ModuleMember** commands, only the members specified in the **Export-ModuleMember** commands are exported.</span></span>
<span data-ttu-id="bebc4-113">Você também pode usar **Export-ModuleMember** para suprimir ou exportar Membros que o módulo de script importa de outros módulos.</span><span class="sxs-lookup"><span data-stu-id="bebc4-113">You can also use **Export-ModuleMember** to suppress or export members that the script module imports from other modules.</span></span>

<span data-ttu-id="bebc4-114">Um comando **Export-ModuleMember** é opcional, mas é uma prática recomendada.</span><span class="sxs-lookup"><span data-stu-id="bebc4-114">An **Export-ModuleMember** command is optional, but it is a best practice.</span></span>
<span data-ttu-id="bebc4-115">Mesmo que o comando confirme os valores padrão, ele demonstra a intenção do autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="bebc4-115">Even if the command confirms the default values, it demonstrates the intention of the module author.</span></span>

## <span data-ttu-id="bebc4-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="bebc4-116">EXAMPLES</span></span>

### <span data-ttu-id="bebc4-117">Exemplo 1: exportar funções e aliases em um módulo de script</span><span class="sxs-lookup"><span data-stu-id="bebc4-117">Example 1: Export functions and aliases in a script module</span></span>

```powershell
Export-ModuleMember -Function * -Alias *
```

<span data-ttu-id="bebc4-118">Esse comando exporta todas as funções e aliases definidos no módulo de script.</span><span class="sxs-lookup"><span data-stu-id="bebc4-118">This command exports all the functions and aliases defined in the script module.</span></span>

### <span data-ttu-id="bebc4-119">Exemplo 2: exportar funções e aliases específicos</span><span class="sxs-lookup"><span data-stu-id="bebc4-119">Example 2: Export specific aliases and functions</span></span>

```powershell
Export-ModuleMember -Function Get-Test, New-Test, Start-Test -Alias gtt, ntt, stt
```

<span data-ttu-id="bebc4-120">Este comando exporta três aliases e três funções definidas no módulo de script.</span><span class="sxs-lookup"><span data-stu-id="bebc4-120">This command exports three aliases and three functions defined in the script module.</span></span>

<span data-ttu-id="bebc4-121">Você pode usar esse formato de comando para especificar os nomes dos membros do módulo.</span><span class="sxs-lookup"><span data-stu-id="bebc4-121">You can use this command format to specify the names of module members.</span></span>

### <span data-ttu-id="bebc4-122">Exemplo 3: exportar nenhum membro</span><span class="sxs-lookup"><span data-stu-id="bebc4-122">Example 3: Export no members</span></span>

```powershell
Export-ModuleMember
```

<span data-ttu-id="bebc4-123">Este comando especifica que nenhum membro definido no módulo de script é exportado.</span><span class="sxs-lookup"><span data-stu-id="bebc4-123">This command specifies that no members defined in the script module are exported.</span></span>

<span data-ttu-id="bebc4-124">Esse comando impede que os membros do módulo sejam exportados, mas não oculta os membros.</span><span class="sxs-lookup"><span data-stu-id="bebc4-124">This command prevents the module members from being exported, but it does not hide the members.</span></span>
<span data-ttu-id="bebc4-125">Os usuários podem ler e copiar membros de módulo ou use o operador de chamada (&) para chamar membros de módulo que não são exportados.</span><span class="sxs-lookup"><span data-stu-id="bebc4-125">Users can read and copy module members or use the call operator (&) to invoke module members that are not exported.</span></span>

### <span data-ttu-id="bebc4-126">Exemplo 4: exportar uma variável específica</span><span class="sxs-lookup"><span data-stu-id="bebc4-126">Example 4: Export a specific variable</span></span>

```powershell
Export-ModuleMember -Variable increment
```

<span data-ttu-id="bebc4-127">Este comando exporta apenas a variável $increment do módulo de script.</span><span class="sxs-lookup"><span data-stu-id="bebc4-127">This command exports only the $increment variable from the script module.</span></span>
<span data-ttu-id="bebc4-128">Nenhum outro membro é exportado.</span><span class="sxs-lookup"><span data-stu-id="bebc4-128">No other members are exported.</span></span>

<span data-ttu-id="bebc4-129">Se você quiser exportar uma variável, além de exportar as funções em um módulo, o comando **Export-ModuleMember** deverá incluir os nomes de todas as funções e o nome da variável.</span><span class="sxs-lookup"><span data-stu-id="bebc4-129">If you want to export a variable, in addition to exporting the functions in a module, the **Export-ModuleMember** command must include the names of all of the functions and the name of the variable.</span></span>

### <span data-ttu-id="bebc4-130">Exemplo 5: vários comandos de exportação</span><span class="sxs-lookup"><span data-stu-id="bebc4-130">Example 5: Multiple export commands</span></span>

```powershell
# From TestModule.psm1
Function New-Test
{
    Write-Output 'I am New-Test function'
}
Export-ModuleMember -Function New-Test

function Validate-Test
{
    Write-Output 'I am Validate-Test function'
}
function Start-Test
{
    Write-Output 'I am Start-Test function'
}
Set-Alias stt Start-Test
Export-ModuleMember -Function Start-Test -Alias stt
```

<span data-ttu-id="bebc4-131">Esses comandos mostram como vários comandos **Export-ModuleMember** são interpretados em um arquivo de módulo de script (. psm1).</span><span class="sxs-lookup"><span data-stu-id="bebc4-131">These commands show how multiple **Export-ModuleMember** commands are interpreted in a script module (.psm1) file.</span></span>

<span data-ttu-id="bebc4-132">Esses comandos criam um alias e três funções e, em seguida, exportam duas funções e o alias.</span><span class="sxs-lookup"><span data-stu-id="bebc4-132">These commands create three functions and one alias, and then they export two of the functions and the alias.</span></span>

<span data-ttu-id="bebc4-133">Sem os comandos **Export-ModuleMember** , todas as três funções e o alias seriam exportados.</span><span class="sxs-lookup"><span data-stu-id="bebc4-133">Without the **Export-ModuleMember** commands, all three of the functions and the alias would be exported.</span></span>
<span data-ttu-id="bebc4-134">Com os comandos **Export-ModuleMember** , somente as funções **New-Test** e **Start-Test** e o alias STT são exportados.</span><span class="sxs-lookup"><span data-stu-id="bebc4-134">With the **Export-ModuleMember** commands, only the **New-Test** and **Start-Test** functions and the STT alias are exported.</span></span>

### <span data-ttu-id="bebc4-135">Exemplo 6: exportar Membros em um módulo dinâmico</span><span class="sxs-lookup"><span data-stu-id="bebc4-135">Example 6: Export members in a dynamic module</span></span>

```powershell
New-Module -Script {function SayHello {"Hello!"}; Set-Alias Hi SayHello; Export-ModuleMember -Alias Hi -Function SayHello}
```

<span data-ttu-id="bebc4-136">Este comando mostra como usar Export-ModuleMember em um módulo dinâmico que é criado usando o cmdlet **New-Module** .</span><span class="sxs-lookup"><span data-stu-id="bebc4-136">This command shows how to use Export-ModuleMember in a dynamic module that is created by using the **New-Module** cmdlet.</span></span>

<span data-ttu-id="bebc4-137">Neste exemplo, **Export-ModuleMember** é usado para exportar o alias Hi e a função **SayHello** no módulo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="bebc4-137">In this example, **Export-ModuleMember** is used to export both the Hi alias and the **SayHello** function in the dynamic module.</span></span>

### <span data-ttu-id="bebc4-138">Exemplo 7: declarar e exportar uma função em um único comando</span><span class="sxs-lookup"><span data-stu-id="bebc4-138">Example 7: Declare and export a function in a single command</span></span>

```powershell
# From TestModule.psm1
function Export
{
  param (
    [Parameter(Mandatory=$true)]
    [ValidateSet("function","variable")]
    $Type,
    [Parameter(Mandatory=$true)]
    $Name,
    [Parameter(Mandatory=$true)]
    $Value
    )

    if ($Type -eq "function")
    {
        Set-item "function:script:$Name" $Value
        Export-ModuleMember $Name
    }
    else
    {
    Set-Variable -scope Script $Name $Value
    Export-ModuleMember -variable $Name
    }
}

Export function New-Test {Write-Output 'I am New-Test function'}
function helper {Write-Output 'I am helper function'}

Export variable Interval 0
$Interval = 2
```

<span data-ttu-id="bebc4-139">Este exemplo inclui uma função chamada **Export** que declara uma função ou cria uma variável e, em seguida, grava um `Export-ModuleMember` comando para a função ou variável.</span><span class="sxs-lookup"><span data-stu-id="bebc4-139">This example includes a function named **Export** that declares a function or creates a variable, and then writes an `Export-ModuleMember` command for the function or variable.</span></span>
<span data-ttu-id="bebc4-140">Isso permite declarar e exportar uma função ou variável em um único comando.</span><span class="sxs-lookup"><span data-stu-id="bebc4-140">This lets you declare and export a function or variable in a single command.</span></span>

<span data-ttu-id="bebc4-141">Para usar a função de **exportação** , inclua-a em seu módulo de script.</span><span class="sxs-lookup"><span data-stu-id="bebc4-141">To use the **Export** function, include it in your script module.</span></span>
<span data-ttu-id="bebc4-142">Para exportar uma função, digite `Export` antes da palavra-chave **Function** .</span><span class="sxs-lookup"><span data-stu-id="bebc4-142">To export a function, type `Export` before the **Function** keyword.</span></span>

<span data-ttu-id="bebc4-143">Para exportar uma variável, use o seguinte formato para declarar a variável e definir seu valor:</span><span class="sxs-lookup"><span data-stu-id="bebc4-143">To export a variable, use the following format to declare the variable and set its value:</span></span>

`Export variable <variable-name> <value>`

<span data-ttu-id="bebc4-144">Os comandos do exemplo mostram o formato correto.</span><span class="sxs-lookup"><span data-stu-id="bebc4-144">The commands in the example show the correct format.</span></span>
<span data-ttu-id="bebc4-145">Neste exemplo, somente a função **New-Test** e a variável $Interval são exportadas.</span><span class="sxs-lookup"><span data-stu-id="bebc4-145">In this example, only the **New-Test** function and the $Interval variable are exported.</span></span>

## <span data-ttu-id="bebc4-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bebc4-146">PARAMETERS</span></span>

### <span data-ttu-id="bebc4-147">-Alias</span><span class="sxs-lookup"><span data-stu-id="bebc4-147">-Alias</span></span>

<span data-ttu-id="bebc4-148">Especifica os aliases exportados por meio do arquivo do módulo de script.</span><span class="sxs-lookup"><span data-stu-id="bebc4-148">Specifies the aliases that are exported from the script module file.</span></span>
<span data-ttu-id="bebc4-149">Digite os nomes de alias.</span><span class="sxs-lookup"><span data-stu-id="bebc4-149">Enter the alias names.</span></span>
<span data-ttu-id="bebc4-150">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="bebc4-150">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="bebc4-151">-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="bebc4-151">-Cmdlet</span></span>

<span data-ttu-id="bebc4-152">Especifica os cmdlets exportados por meio do arquivo do módulo de script.</span><span class="sxs-lookup"><span data-stu-id="bebc4-152">Specifies the cmdlets that are exported from the script module file.</span></span>
<span data-ttu-id="bebc4-153">Digite os nomes de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bebc4-153">Enter the cmdlet names.</span></span>
<span data-ttu-id="bebc4-154">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="bebc4-154">Wildcard characters are permitted.</span></span>

<span data-ttu-id="bebc4-155">Não é possível criar cmdlets em um arquivo do módulo de script, mas você pode importar cmdlets de um módulo binário em um módulo de script e exportá-los novamente do módulo de script.</span><span class="sxs-lookup"><span data-stu-id="bebc4-155">You cannot create cmdlets in a script module file, but you can import cmdlets from a binary module into a script module and re-export them from the script module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="bebc4-156">-Função</span><span class="sxs-lookup"><span data-stu-id="bebc4-156">-Function</span></span>

<span data-ttu-id="bebc4-157">Especifica as funções exportadas por meio do arquivo do módulo de script.</span><span class="sxs-lookup"><span data-stu-id="bebc4-157">Specifies the functions that are exported from the script module file.</span></span>
<span data-ttu-id="bebc4-158">Digite os nomes de função.</span><span class="sxs-lookup"><span data-stu-id="bebc4-158">Enter the function names.</span></span>
<span data-ttu-id="bebc4-159">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="bebc4-159">Wildcard characters are permitted.</span></span>
<span data-ttu-id="bebc4-160">Você também pode canalizar cadeias de caracteres de nome de função para **Export-ModuleMember** .</span><span class="sxs-lookup"><span data-stu-id="bebc4-160">You can also pipe function name strings to **Export-ModuleMember** .</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="bebc4-161">-Variable</span><span class="sxs-lookup"><span data-stu-id="bebc4-161">-Variable</span></span>

<span data-ttu-id="bebc4-162">Especifica as variáveis exportadas por meio do arquivo do módulo de script.</span><span class="sxs-lookup"><span data-stu-id="bebc4-162">Specifies the variables that are exported from the script module file.</span></span>
<span data-ttu-id="bebc4-163">Insira os nomes de variáveis, sem um cifrão.</span><span class="sxs-lookup"><span data-stu-id="bebc4-163">Enter the variable names, without a dollar sign.</span></span>
<span data-ttu-id="bebc4-164">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="bebc4-164">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="bebc4-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bebc4-165">CommonParameters</span></span>

<span data-ttu-id="bebc4-166">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bebc4-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bebc4-167">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bebc4-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bebc4-168">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="bebc4-168">INPUTS</span></span>

### <span data-ttu-id="bebc4-169">System.String</span><span class="sxs-lookup"><span data-stu-id="bebc4-169">System.String</span></span>

<span data-ttu-id="bebc4-170">Você pode canalizar cadeias de caracteres de nome de função para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bebc4-170">You can pipe function name strings to this cmdlet.</span></span>

## <span data-ttu-id="bebc4-171">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="bebc4-171">OUTPUTS</span></span>

### <span data-ttu-id="bebc4-172">Nenhum</span><span class="sxs-lookup"><span data-stu-id="bebc4-172">None</span></span>

<span data-ttu-id="bebc4-173">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="bebc4-173">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bebc4-174">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="bebc4-174">NOTES</span></span>

* <span data-ttu-id="bebc4-175">Para excluir um membro da lista de membros exportados, adicione um comando **Export-ModuleMember** que lista todos os outros membros, mas omita o membro que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="bebc4-175">To exclude a member from the list of exported members, add an **Export-ModuleMember** command that lists all other members but omits the member that you want to exclude.</span></span>

## <span data-ttu-id="bebc4-176">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="bebc4-176">RELATED LINKS</span></span>

[<span data-ttu-id="bebc4-177">Get-Module</span><span class="sxs-lookup"><span data-stu-id="bebc4-177">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="bebc4-178">Import-Module</span><span class="sxs-lookup"><span data-stu-id="bebc4-178">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="bebc4-179">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="bebc4-179">Remove-Module</span></span>](Remove-Module.md)

