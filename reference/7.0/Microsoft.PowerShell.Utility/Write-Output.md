---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-output?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Output
ms.openlocfilehash: be2c506a928a96f66fd7318bdb0da1c57c5474b8
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196440"
---
# <span data-ttu-id="600ac-103">Write-Output</span><span class="sxs-lookup"><span data-stu-id="600ac-103">Write-Output</span></span>

## <span data-ttu-id="600ac-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="600ac-104">SYNOPSIS</span></span>
<span data-ttu-id="600ac-105">Envia os objetos especificados para o próximo comando no pipeline.</span><span class="sxs-lookup"><span data-stu-id="600ac-105">Sends the specified objects to the next command in the pipeline.</span></span> <span data-ttu-id="600ac-106">Se o comando for o último no pipeline, os objetos serão exibidos no console.</span><span class="sxs-lookup"><span data-stu-id="600ac-106">If the command is the last command in the pipeline, the objects are displayed in the console.</span></span>

## <span data-ttu-id="600ac-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="600ac-107">SYNTAX</span></span>

```
Write-Output [-InputObject] <PSObject[]> [-NoEnumerate] [<CommonParameters>]
```

## <span data-ttu-id="600ac-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="600ac-108">DESCRIPTION</span></span>

<span data-ttu-id="600ac-109">O `Write-Output` cmdlet envia o objeto especificado para baixo no pipeline para o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="600ac-109">The `Write-Output` cmdlet sends the specified object down the pipeline to the next command.</span></span>
<span data-ttu-id="600ac-110">Se o comando for o último no pipeline, o objeto é exibido no console.</span><span class="sxs-lookup"><span data-stu-id="600ac-110">If the command is the last command in the pipeline, the object is displayed in the console.</span></span>

<span data-ttu-id="600ac-111">`Write-Output` envia objetos para baixo do pipeline primário, também conhecido como "fluxo de saída" ou "pipeline de sucesso".</span><span class="sxs-lookup"><span data-stu-id="600ac-111">`Write-Output` sends objects down the primary pipeline, also known as the "output stream" or the "success pipeline."</span></span> <span data-ttu-id="600ac-112">Para enviar objetos de erro pelo pipeline de erro, use Write-Error.</span><span class="sxs-lookup"><span data-stu-id="600ac-112">To send error objects down the error pipeline, use Write-Error.</span></span>

<span data-ttu-id="600ac-113">Esse cmdlet é usado normalmente em scripts para exibir cadeias de caracteres e outros objetos no console.</span><span class="sxs-lookup"><span data-stu-id="600ac-113">This cmdlet is typically used in scripts to display strings and other objects on the console.</span></span> <span data-ttu-id="600ac-114">Um dos aliases internos do `Write-Output` é `echo` e semelhante a outros shells que usam `echo` , o comportamento padrão é exibir a saída no final de um pipeline.</span><span class="sxs-lookup"><span data-stu-id="600ac-114">One of the built-in aliases for `Write-Output` is `echo` and similar to other shells that use `echo`, the default behavior is to display the output at the end of a pipeline.</span></span> <span data-ttu-id="600ac-115">No PowerShell, geralmente não é necessário usar o cmdlet em instâncias em que a saída é exibida por padrão.</span><span class="sxs-lookup"><span data-stu-id="600ac-115">In PowerShell, it is generally not necessary to use the cmdlet in instances where the output is displayed by default.</span></span> <span data-ttu-id="600ac-116">Por exemplo, `Get-Process | Write-Output` é equivalente a `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="600ac-116">For example, `Get-Process | Write-Output` is equivalent to `Get-Process`.</span></span> <span data-ttu-id="600ac-117">Ou, `echo "Home directory: $HOME"` pode ser escrito, `"Home directory: $HOME"` .</span><span class="sxs-lookup"><span data-stu-id="600ac-117">Or, `echo "Home directory: $HOME"` can be written, `"Home directory: $HOME"`.</span></span>

<span data-ttu-id="600ac-118">Por padrão, o `Write-Output` enumera por meio de coleções fornecidas para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="600ac-118">By default, `Write-Output` enumerates through collections provided to the cmdlet.</span></span> <span data-ttu-id="600ac-119">No entanto, `Write-Output` também pode ser usado para passar as coleções para o pipeline como um único objeto com o parâmetro **noenumerate** .</span><span class="sxs-lookup"><span data-stu-id="600ac-119">However, `Write-Output` can also be used to pass collections down the pipeline as a single object with the **NoEnumerate** parameter.</span></span>

## <span data-ttu-id="600ac-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="600ac-120">EXAMPLES</span></span>

### <span data-ttu-id="600ac-121">Exemplo 1: obter objetos e gravá-los no console</span><span class="sxs-lookup"><span data-stu-id="600ac-121">Example 1: Get objects and write them to the console</span></span>

```powershell
$P = Get-Process
Write-Output $P
```

<span data-ttu-id="600ac-122">O primeiro comando obtém os processos em execução no computador e os armazena na `$P` variável.</span><span class="sxs-lookup"><span data-stu-id="600ac-122">The first command gets processes running on the computer and stores them in the `$P` variable.</span></span>

<span data-ttu-id="600ac-123">O segundo e o terceiro comandos exibem os objetos de processo no `$P` console do.</span><span class="sxs-lookup"><span data-stu-id="600ac-123">The second and third commands display the process objects in `$P` on the console.</span></span>

### <span data-ttu-id="600ac-124">Exemplo 2: passar a saída para outro cmdlet</span><span class="sxs-lookup"><span data-stu-id="600ac-124">Example 2: Pass output to another cmdlet</span></span>

```powershell
Write-Output "test output" | Get-Member
```

<span data-ttu-id="600ac-125">Esse comando canaliza a cadeia de caracteres de "saída de teste" para o `Get-Member` cmdlet, que exibe os membros da classe **System. String** , demonstrando que a cadeia de caracteres foi passada ao longo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="600ac-125">This command pipes the "test output" string to the `Get-Member` cmdlet, which displays the members of the **System.String** class, demonstrating that the string was passed along the pipeline.</span></span>

### <span data-ttu-id="600ac-126">Exemplo 3: suprimir enumeração na saída</span><span class="sxs-lookup"><span data-stu-id="600ac-126">Example 3: Suppress enumeration in output</span></span>

```powershell
Write-Output 1,2,3 | Measure-Object
```

```Output
Count    : 3
...
```

```powershell
Write-Output 1,2,3 -NoEnumerate | Measure-Object
```

```Output
Count    : 1
...
```

<span data-ttu-id="600ac-127">Esse comando adiciona o parâmetro **Noenumerate** para tratar uma coleção ou matriz como um único objeto por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="600ac-127">This command adds the **NoEnumerate** parameter to treat a collection or array as a single object through the pipeline.</span></span>

## <span data-ttu-id="600ac-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="600ac-128">PARAMETERS</span></span>

### <span data-ttu-id="600ac-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="600ac-129">-InputObject</span></span>

<span data-ttu-id="600ac-130">Especifica os objetos para envio pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="600ac-130">Specifies the objects to send down the pipeline.</span></span> <span data-ttu-id="600ac-131">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="600ac-131">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="600ac-132">-Noenumerate</span><span class="sxs-lookup"><span data-stu-id="600ac-132">-NoEnumerate</span></span>

<span data-ttu-id="600ac-133">Por padrão, o `Write-Output` cmdlet sempre enumera sua saída.</span><span class="sxs-lookup"><span data-stu-id="600ac-133">By default, the `Write-Output` cmdlet always enumerates its output.</span></span> <span data-ttu-id="600ac-134">O parâmetro **Noenumerate** suprime o comportamento padrão e impede a `Write-Output` enumeração da saída.</span><span class="sxs-lookup"><span data-stu-id="600ac-134">The **NoEnumerate** parameter suppresses the default behavior, and prevents `Write-Output` from enumerating output.</span></span> <span data-ttu-id="600ac-135">O parâmetro **Noenumerate** não terá nenhum efeito se o comando for encapsulado entre parênteses, porque os parênteses forçam a enumeração.</span><span class="sxs-lookup"><span data-stu-id="600ac-135">The **NoEnumerate** parameter has no effect if the command is wrapped in parentheses, because the parentheses force enumeration.</span></span> <span data-ttu-id="600ac-136">Por exemplo, `(Write-Output 1,2,3)` o ainda enumera a matriz.</span><span class="sxs-lookup"><span data-stu-id="600ac-136">For example, `(Write-Output 1,2,3)` still enumerates the array.</span></span>

> [!NOTE]
> <span data-ttu-id="600ac-137">Essa opção funciona apenas corretamente com o PowerShell Core 6,2 e mais recente.</span><span class="sxs-lookup"><span data-stu-id="600ac-137">This switch only works correctly with PowerShell Core 6.2 and newer.</span></span> <span data-ttu-id="600ac-138">Em versões mais antigas do PowerShell Core, a coleção ainda é enumerada mesmo com o uso dessa opção.</span><span class="sxs-lookup"><span data-stu-id="600ac-138">On older versions of PowerShell Core, the collection is still enumerated even with use of this switch.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="600ac-139">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="600ac-139">CommonParameters</span></span>

<span data-ttu-id="600ac-140">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="600ac-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="600ac-141">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="600ac-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="600ac-142">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="600ac-142">INPUTS</span></span>

### <span data-ttu-id="600ac-143">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="600ac-143">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="600ac-144">Você pode canalizar objetos para `Write-Output` .</span><span class="sxs-lookup"><span data-stu-id="600ac-144">You can pipe objects to `Write-Output`.</span></span>

## <span data-ttu-id="600ac-145">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="600ac-145">OUTPUTS</span></span>

### <span data-ttu-id="600ac-146">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="600ac-146">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="600ac-147">`Write-Output` Retorna os objetos que são enviados como entrada.</span><span class="sxs-lookup"><span data-stu-id="600ac-147">`Write-Output` returns the objects that are submitted as input.</span></span>

## <span data-ttu-id="600ac-148">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="600ac-148">NOTES</span></span>

## <span data-ttu-id="600ac-149">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="600ac-149">RELATED LINKS</span></span>

[<span data-ttu-id="600ac-150">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="600ac-150">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="600ac-151">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="600ac-151">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="600ac-152">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="600ac-152">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="600ac-153">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="600ac-153">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="600ac-154">Erro de gravação</span><span class="sxs-lookup"><span data-stu-id="600ac-154">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="600ac-155">Write-Host</span><span class="sxs-lookup"><span data-stu-id="600ac-155">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="600ac-156">Write-Information</span><span class="sxs-lookup"><span data-stu-id="600ac-156">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="600ac-157">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="600ac-157">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="600ac-158">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="600ac-158">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="600ac-159">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="600ac-159">Write-Warning</span></span>](Write-Warning.md)
