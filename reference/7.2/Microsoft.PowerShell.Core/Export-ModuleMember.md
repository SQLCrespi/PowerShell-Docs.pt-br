---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-modulemember?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ModuleMember
ms.openlocfilehash: fcb9af654f9e95f44e49ea984294b80752aa3453
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598011"
---
# <span data-ttu-id="52f64-102">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="52f64-102">Export-ModuleMember</span></span>

## <span data-ttu-id="52f64-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="52f64-103">SYNOPSIS</span></span>
<span data-ttu-id="52f64-104">Especifica os membros do módulo que são exportados.</span><span class="sxs-lookup"><span data-stu-id="52f64-104">Specifies the module members that are exported.</span></span>

## <span data-ttu-id="52f64-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="52f64-105">SYNTAX</span></span>

```
Export-ModuleMember [[-Function] <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="52f64-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="52f64-106">DESCRIPTION</span></span>

<span data-ttu-id="52f64-107">O cmdlet **Export-ModuleMember** especifica os membros do módulo que são exportados de um arquivo de módulo de script (. psm1) ou de um módulo dinâmico criado usando o cmdlet New-Module.</span><span class="sxs-lookup"><span data-stu-id="52f64-107">The **Export-ModuleMember** cmdlet specifies the module members that are exported from a script module (.psm1) file, or from a dynamic module created by using the New-Module cmdlet.</span></span>
<span data-ttu-id="52f64-108">Os membros do módulo incluem cmdlets, funções, variáveis e aliases.</span><span class="sxs-lookup"><span data-stu-id="52f64-108">Module members include cmdlets, functions, variables, and aliases.</span></span>
<span data-ttu-id="52f64-109">Esse cmdlet pode ser usado somente em um arquivo de módulo de script ou um módulo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="52f64-109">This cmdlet can be used only in a script module file or a dynamic module.</span></span>

<span data-ttu-id="52f64-110">Se um módulo de script não incluir um comando **Export-ModuleMember** , as funções e os aliases no módulo de script serão exportados, mas as variáveis não serão.</span><span class="sxs-lookup"><span data-stu-id="52f64-110">If a script module does not include an **Export-ModuleMember** command, the functions and aliases in the script module are exported, but the variables are not.</span></span>
<span data-ttu-id="52f64-111">Quando um módulo de script inclui comandos **Export-ModuleMember** , somente os membros especificados nos comandos **Export-ModuleMember** são exportados.</span><span class="sxs-lookup"><span data-stu-id="52f64-111">When a script module includes **Export-ModuleMember** commands, only the members specified in the **Export-ModuleMember** commands are exported.</span></span>
<span data-ttu-id="52f64-112">Você também pode usar **Export-ModuleMember** para suprimir ou exportar Membros que o módulo de script importa de outros módulos.</span><span class="sxs-lookup"><span data-stu-id="52f64-112">You can also use **Export-ModuleMember** to suppress or export members that the script module imports from other modules.</span></span>

<span data-ttu-id="52f64-113">Um comando **Export-ModuleMember** é opcional, mas é uma prática recomendada.</span><span class="sxs-lookup"><span data-stu-id="52f64-113">An **Export-ModuleMember** command is optional, but it is a best practice.</span></span>
<span data-ttu-id="52f64-114">Mesmo que o comando confirme os valores padrão, ele demonstra a intenção do autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="52f64-114">Even if the command confirms the default values, it demonstrates the intention of the module author.</span></span>

## <span data-ttu-id="52f64-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="52f64-115">EXAMPLES</span></span>

### <span data-ttu-id="52f64-116">Exemplo 1: exportar funções e aliases em um módulo de script</span><span class="sxs-lookup"><span data-stu-id="52f64-116">Example 1: Export functions and aliases in a script module</span></span>

```powershell
Export-ModuleMember -Function * -Alias *
```

<span data-ttu-id="52f64-117">Esse comando exporta todas as funções e aliases definidos no módulo de script.</span><span class="sxs-lookup"><span data-stu-id="52f64-117">This command exports all the functions and aliases defined in the script module.</span></span>

### <span data-ttu-id="52f64-118">Exemplo 2: exportar funções e aliases específicos</span><span class="sxs-lookup"><span data-stu-id="52f64-118">Example 2: Export specific aliases and functions</span></span>

```powershell
Export-ModuleMember -Function Get-Test, New-Test, Start-Test -Alias gtt, ntt, stt
```

<span data-ttu-id="52f64-119">Este comando exporta três aliases e três funções definidas no módulo de script.</span><span class="sxs-lookup"><span data-stu-id="52f64-119">This command exports three aliases and three functions defined in the script module.</span></span>

<span data-ttu-id="52f64-120">Você pode usar esse formato de comando para especificar os nomes dos membros do módulo.</span><span class="sxs-lookup"><span data-stu-id="52f64-120">You can use this command format to specify the names of module members.</span></span>

### <span data-ttu-id="52f64-121">Exemplo 3: exportar nenhum membro</span><span class="sxs-lookup"><span data-stu-id="52f64-121">Example 3: Export no members</span></span>

```powershell
Export-ModuleMember
```

<span data-ttu-id="52f64-122">Este comando especifica que nenhum membro definido no módulo de script é exportado.</span><span class="sxs-lookup"><span data-stu-id="52f64-122">This command specifies that no members defined in the script module are exported.</span></span>

<span data-ttu-id="52f64-123">Esse comando impede que os membros do módulo sejam exportados, mas não oculta os membros.</span><span class="sxs-lookup"><span data-stu-id="52f64-123">This command prevents the module members from being exported, but it does not hide the members.</span></span>
<span data-ttu-id="52f64-124">Os usuários podem ler e copiar membros de módulo ou use o operador de chamada (&) para chamar membros de módulo que não são exportados.</span><span class="sxs-lookup"><span data-stu-id="52f64-124">Users can read and copy module members or use the call operator (&) to invoke module members that are not exported.</span></span>

### <span data-ttu-id="52f64-125">Exemplo 4: exportar uma variável específica</span><span class="sxs-lookup"><span data-stu-id="52f64-125">Example 4: Export a specific variable</span></span>

```powershell
Export-ModuleMember -Variable increment
```

<span data-ttu-id="52f64-126">Este comando exporta apenas a variável $increment do módulo de script.</span><span class="sxs-lookup"><span data-stu-id="52f64-126">This command exports only the $increment variable from the script module.</span></span>
<span data-ttu-id="52f64-127">Nenhum outro membro é exportado.</span><span class="sxs-lookup"><span data-stu-id="52f64-127">No other members are exported.</span></span>

<span data-ttu-id="52f64-128">Se você quiser exportar uma variável, além de exportar as funções em um módulo, o comando **Export-ModuleMember** deverá incluir os nomes de todas as funções e o nome da variável.</span><span class="sxs-lookup"><span data-stu-id="52f64-128">If you want to export a variable, in addition to exporting the functions in a module, the **Export-ModuleMember** command must include the names of all of the functions and the name of the variable.</span></span>

### <span data-ttu-id="52f64-129">Exemplo 5: vários comandos de exportação</span><span class="sxs-lookup"><span data-stu-id="52f64-129">Example 5: Multiple export commands</span></span>

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

<span data-ttu-id="52f64-130">Esses comandos mostram como vários comandos **Export-ModuleMember** são interpretados em um arquivo de módulo de script (. psm1).</span><span class="sxs-lookup"><span data-stu-id="52f64-130">These commands show how multiple **Export-ModuleMember** commands are interpreted in a script module (.psm1) file.</span></span>

<span data-ttu-id="52f64-131">Esses comandos criam um alias e três funções e, em seguida, exportam duas funções e o alias.</span><span class="sxs-lookup"><span data-stu-id="52f64-131">These commands create three functions and one alias, and then they export two of the functions and the alias.</span></span>

<span data-ttu-id="52f64-132">Sem os comandos **Export-ModuleMember** , todas as três funções e o alias seriam exportados.</span><span class="sxs-lookup"><span data-stu-id="52f64-132">Without the **Export-ModuleMember** commands, all three of the functions and the alias would be exported.</span></span>
<span data-ttu-id="52f64-133">Com os comandos **Export-ModuleMember** , somente as funções **New-Test** e **Start-Test** e o alias STT são exportados.</span><span class="sxs-lookup"><span data-stu-id="52f64-133">With the **Export-ModuleMember** commands, only the **New-Test** and **Start-Test** functions and the STT alias are exported.</span></span>

### <span data-ttu-id="52f64-134">Exemplo 6: exportar Membros em um módulo dinâmico</span><span class="sxs-lookup"><span data-stu-id="52f64-134">Example 6: Export members in a dynamic module</span></span>

```powershell
New-Module -Script {function SayHello {"Hello!"}; Set-Alias Hi SayHello; Export-ModuleMember -Alias Hi -Function SayHello}
```

<span data-ttu-id="52f64-135">Este comando mostra como usar Export-ModuleMember em um módulo dinâmico que é criado usando o cmdlet **New-Module** .</span><span class="sxs-lookup"><span data-stu-id="52f64-135">This command shows how to use Export-ModuleMember in a dynamic module that is created by using the **New-Module** cmdlet.</span></span>

<span data-ttu-id="52f64-136">Neste exemplo, **Export-ModuleMember** é usado para exportar o alias Hi e a função **SayHello** no módulo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="52f64-136">In this example, **Export-ModuleMember** is used to export both the Hi alias and the **SayHello** function in the dynamic module.</span></span>

### <span data-ttu-id="52f64-137">Exemplo 7: declarar e exportar uma função em um único comando</span><span class="sxs-lookup"><span data-stu-id="52f64-137">Example 7: Declare and export a function in a single command</span></span>

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

<span data-ttu-id="52f64-138">Este exemplo inclui uma função chamada **Export** que declara uma função ou cria uma variável e, em seguida, grava um `Export-ModuleMember` comando para a função ou variável.</span><span class="sxs-lookup"><span data-stu-id="52f64-138">This example includes a function named **Export** that declares a function or creates a variable, and then writes an `Export-ModuleMember` command for the function or variable.</span></span>
<span data-ttu-id="52f64-139">Isso permite declarar e exportar uma função ou variável em um único comando.</span><span class="sxs-lookup"><span data-stu-id="52f64-139">This lets you declare and export a function or variable in a single command.</span></span>

<span data-ttu-id="52f64-140">Para usar a função de **exportação** , inclua-a em seu módulo de script.</span><span class="sxs-lookup"><span data-stu-id="52f64-140">To use the **Export** function, include it in your script module.</span></span>
<span data-ttu-id="52f64-141">Para exportar uma função, digite `Export` antes da palavra-chave **Function** .</span><span class="sxs-lookup"><span data-stu-id="52f64-141">To export a function, type `Export` before the **Function** keyword.</span></span>

<span data-ttu-id="52f64-142">Para exportar uma variável, use o seguinte formato para declarar a variável e definir seu valor:</span><span class="sxs-lookup"><span data-stu-id="52f64-142">To export a variable, use the following format to declare the variable and set its value:</span></span>

`Export variable <variable-name> <value>`

<span data-ttu-id="52f64-143">Os comandos do exemplo mostram o formato correto.</span><span class="sxs-lookup"><span data-stu-id="52f64-143">The commands in the example show the correct format.</span></span>
<span data-ttu-id="52f64-144">Neste exemplo, somente a função **New-Test** e a variável $Interval são exportadas.</span><span class="sxs-lookup"><span data-stu-id="52f64-144">In this example, only the **New-Test** function and the $Interval variable are exported.</span></span>

## <span data-ttu-id="52f64-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="52f64-145">PARAMETERS</span></span>

### <span data-ttu-id="52f64-146">-Alias</span><span class="sxs-lookup"><span data-stu-id="52f64-146">-Alias</span></span>

<span data-ttu-id="52f64-147">Especifica os aliases exportados por meio do arquivo do módulo de script.</span><span class="sxs-lookup"><span data-stu-id="52f64-147">Specifies the aliases that are exported from the script module file.</span></span>
<span data-ttu-id="52f64-148">Digite os nomes de alias.</span><span class="sxs-lookup"><span data-stu-id="52f64-148">Enter the alias names.</span></span>
<span data-ttu-id="52f64-149">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="52f64-149">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="52f64-150">-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="52f64-150">-Cmdlet</span></span>

<span data-ttu-id="52f64-151">Especifica os cmdlets exportados por meio do arquivo do módulo de script.</span><span class="sxs-lookup"><span data-stu-id="52f64-151">Specifies the cmdlets that are exported from the script module file.</span></span>
<span data-ttu-id="52f64-152">Digite os nomes de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="52f64-152">Enter the cmdlet names.</span></span>
<span data-ttu-id="52f64-153">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="52f64-153">Wildcard characters are permitted.</span></span>

<span data-ttu-id="52f64-154">Não é possível criar cmdlets em um arquivo do módulo de script, mas você pode importar cmdlets de um módulo binário em um módulo de script e exportá-los novamente do módulo de script.</span><span class="sxs-lookup"><span data-stu-id="52f64-154">You cannot create cmdlets in a script module file, but you can import cmdlets from a binary module into a script module and re-export them from the script module.</span></span>

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

### <span data-ttu-id="52f64-155">-Função</span><span class="sxs-lookup"><span data-stu-id="52f64-155">-Function</span></span>

<span data-ttu-id="52f64-156">Especifica as funções exportadas por meio do arquivo do módulo de script.</span><span class="sxs-lookup"><span data-stu-id="52f64-156">Specifies the functions that are exported from the script module file.</span></span>
<span data-ttu-id="52f64-157">Digite os nomes de função.</span><span class="sxs-lookup"><span data-stu-id="52f64-157">Enter the function names.</span></span>
<span data-ttu-id="52f64-158">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="52f64-158">Wildcard characters are permitted.</span></span>
<span data-ttu-id="52f64-159">Você também pode canalizar cadeias de caracteres de nome de função para **Export-ModuleMember**.</span><span class="sxs-lookup"><span data-stu-id="52f64-159">You can also pipe function name strings to **Export-ModuleMember**.</span></span>

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

### <span data-ttu-id="52f64-160">-Variable</span><span class="sxs-lookup"><span data-stu-id="52f64-160">-Variable</span></span>

<span data-ttu-id="52f64-161">Especifica as variáveis exportadas por meio do arquivo do módulo de script.</span><span class="sxs-lookup"><span data-stu-id="52f64-161">Specifies the variables that are exported from the script module file.</span></span>
<span data-ttu-id="52f64-162">Insira os nomes de variáveis, sem um cifrão.</span><span class="sxs-lookup"><span data-stu-id="52f64-162">Enter the variable names, without a dollar sign.</span></span>
<span data-ttu-id="52f64-163">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="52f64-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="52f64-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="52f64-164">CommonParameters</span></span>

<span data-ttu-id="52f64-165">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="52f64-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="52f64-166">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="52f64-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="52f64-167">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="52f64-167">INPUTS</span></span>

### <span data-ttu-id="52f64-168">System.String</span><span class="sxs-lookup"><span data-stu-id="52f64-168">System.String</span></span>

<span data-ttu-id="52f64-169">Você pode canalizar cadeias de caracteres de nome de função para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="52f64-169">You can pipe function name strings to this cmdlet.</span></span>

## <span data-ttu-id="52f64-170">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="52f64-170">OUTPUTS</span></span>

### <span data-ttu-id="52f64-171">Nenhum</span><span class="sxs-lookup"><span data-stu-id="52f64-171">None</span></span>

<span data-ttu-id="52f64-172">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="52f64-172">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="52f64-173">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="52f64-173">NOTES</span></span>

* <span data-ttu-id="52f64-174">Para excluir um membro da lista de membros exportados, adicione um comando **Export-ModuleMember** que lista todos os outros membros, mas omita o membro que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="52f64-174">To exclude a member from the list of exported members, add an **Export-ModuleMember** command that lists all other members but omits the member that you want to exclude.</span></span>

## <span data-ttu-id="52f64-175">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="52f64-175">RELATED LINKS</span></span>

[<span data-ttu-id="52f64-176">Get-Module</span><span class="sxs-lookup"><span data-stu-id="52f64-176">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="52f64-177">Import-Module</span><span class="sxs-lookup"><span data-stu-id="52f64-177">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="52f64-178">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="52f64-178">Remove-Module</span></span>](Remove-Module.md)

