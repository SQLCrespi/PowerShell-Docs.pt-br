---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-output?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Output
ms.openlocfilehash: 7e0c958201dbd1b42d1f4c4ee286b8aca1f8595a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596787"
---
# <span data-ttu-id="247c8-102">Write-Output</span><span class="sxs-lookup"><span data-stu-id="247c8-102">Write-Output</span></span>

## <span data-ttu-id="247c8-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="247c8-103">SYNOPSIS</span></span>
<span data-ttu-id="247c8-104">Envia os objetos especificados para o próximo comando no pipeline.</span><span class="sxs-lookup"><span data-stu-id="247c8-104">Sends the specified objects to the next command in the pipeline.</span></span> <span data-ttu-id="247c8-105">Se o comando for o último no pipeline, os objetos serão exibidos no console.</span><span class="sxs-lookup"><span data-stu-id="247c8-105">If the command is the last command in the pipeline, the objects are displayed in the console.</span></span>

## <span data-ttu-id="247c8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="247c8-106">SYNTAX</span></span>

```
Write-Output [-InputObject] <PSObject[]> [-NoEnumerate] [<CommonParameters>]
```

## <span data-ttu-id="247c8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="247c8-107">DESCRIPTION</span></span>

<span data-ttu-id="247c8-108">O `Write-Output` cmdlet envia o objeto especificado para baixo no pipeline para o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="247c8-108">The `Write-Output` cmdlet sends the specified object down the pipeline to the next command.</span></span>
<span data-ttu-id="247c8-109">Se o comando for o último no pipeline, o objeto é exibido no console.</span><span class="sxs-lookup"><span data-stu-id="247c8-109">If the command is the last command in the pipeline, the object is displayed in the console.</span></span>

<span data-ttu-id="247c8-110">`Write-Output` envia objetos para baixo do pipeline primário, também conhecido como "fluxo de saída" ou "pipeline de sucesso".</span><span class="sxs-lookup"><span data-stu-id="247c8-110">`Write-Output` sends objects down the primary pipeline, also known as the "output stream" or the "success pipeline."</span></span> <span data-ttu-id="247c8-111">Para enviar objetos de erro pelo pipeline de erro, use Write-Error.</span><span class="sxs-lookup"><span data-stu-id="247c8-111">To send error objects down the error pipeline, use Write-Error.</span></span>

<span data-ttu-id="247c8-112">Esse cmdlet é usado normalmente em scripts para exibir cadeias de caracteres e outros objetos no console.</span><span class="sxs-lookup"><span data-stu-id="247c8-112">This cmdlet is typically used in scripts to display strings and other objects on the console.</span></span> <span data-ttu-id="247c8-113">Um dos aliases internos do `Write-Output` é `echo` e semelhante a outros shells que usam `echo` , o comportamento padrão é exibir a saída no final de um pipeline.</span><span class="sxs-lookup"><span data-stu-id="247c8-113">One of the built-in aliases for `Write-Output` is `echo` and similar to other shells that use `echo`, the default behavior is to display the output at the end of a pipeline.</span></span> <span data-ttu-id="247c8-114">No PowerShell, geralmente não é necessário usar o cmdlet em instâncias em que a saída é exibida por padrão.</span><span class="sxs-lookup"><span data-stu-id="247c8-114">In PowerShell, it is generally not necessary to use the cmdlet in instances where the output is displayed by default.</span></span> <span data-ttu-id="247c8-115">Por exemplo, `Get-Process | Write-Output` é equivalente a `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="247c8-115">For example, `Get-Process | Write-Output` is equivalent to `Get-Process`.</span></span> <span data-ttu-id="247c8-116">Ou, `echo "Home directory: $HOME"` pode ser escrito, `"Home directory: $HOME"` .</span><span class="sxs-lookup"><span data-stu-id="247c8-116">Or, `echo "Home directory: $HOME"` can be written, `"Home directory: $HOME"`.</span></span>

<span data-ttu-id="247c8-117">Por padrão, o `Write-Output` enumera por meio de coleções fornecidas para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="247c8-117">By default, `Write-Output` enumerates through collections provided to the cmdlet.</span></span> <span data-ttu-id="247c8-118">No entanto, `Write-Output` também pode ser usado para passar as coleções para o pipeline como um único objeto com o parâmetro **noenumerate** .</span><span class="sxs-lookup"><span data-stu-id="247c8-118">However, `Write-Output` can also be used to pass collections down the pipeline as a single object with the **NoEnumerate** parameter.</span></span>

## <span data-ttu-id="247c8-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="247c8-119">EXAMPLES</span></span>

### <span data-ttu-id="247c8-120">Exemplo 1: obter objetos e gravá-los no console</span><span class="sxs-lookup"><span data-stu-id="247c8-120">Example 1: Get objects and write them to the console</span></span>

```powershell
$P = Get-Process
Write-Output $P
```

<span data-ttu-id="247c8-121">O primeiro comando obtém os processos em execução no computador e os armazena na `$P` variável.</span><span class="sxs-lookup"><span data-stu-id="247c8-121">The first command gets processes running on the computer and stores them in the `$P` variable.</span></span>

<span data-ttu-id="247c8-122">O segundo e o terceiro comandos exibem os objetos de processo no `$P` console do.</span><span class="sxs-lookup"><span data-stu-id="247c8-122">The second and third commands display the process objects in `$P` on the console.</span></span>

### <span data-ttu-id="247c8-123">Exemplo 2: passar a saída para outro cmdlet</span><span class="sxs-lookup"><span data-stu-id="247c8-123">Example 2: Pass output to another cmdlet</span></span>

```powershell
Write-Output "test output" | Get-Member
```

<span data-ttu-id="247c8-124">Esse comando canaliza a cadeia de caracteres de "saída de teste" para o `Get-Member` cmdlet, que exibe os membros da classe **System. String** , demonstrando que a cadeia de caracteres foi passada ao longo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="247c8-124">This command pipes the "test output" string to the `Get-Member` cmdlet, which displays the members of the **System.String** class, demonstrating that the string was passed along the pipeline.</span></span>

### <span data-ttu-id="247c8-125">Exemplo 3: suprimir enumeração na saída</span><span class="sxs-lookup"><span data-stu-id="247c8-125">Example 3: Suppress enumeration in output</span></span>

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

<span data-ttu-id="247c8-126">Esse comando adiciona o parâmetro **Noenumerate** para tratar uma coleção ou matriz como um único objeto por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="247c8-126">This command adds the **NoEnumerate** parameter to treat a collection or array as a single object through the pipeline.</span></span>

## <span data-ttu-id="247c8-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="247c8-127">PARAMETERS</span></span>

### <span data-ttu-id="247c8-128">-InputObject</span><span class="sxs-lookup"><span data-stu-id="247c8-128">-InputObject</span></span>

<span data-ttu-id="247c8-129">Especifica os objetos para envio pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="247c8-129">Specifies the objects to send down the pipeline.</span></span> <span data-ttu-id="247c8-130">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="247c8-130">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="247c8-131">-Noenumerate</span><span class="sxs-lookup"><span data-stu-id="247c8-131">-NoEnumerate</span></span>

<span data-ttu-id="247c8-132">Por padrão, o `Write-Output` cmdlet sempre enumera sua saída.</span><span class="sxs-lookup"><span data-stu-id="247c8-132">By default, the `Write-Output` cmdlet always enumerates its output.</span></span> <span data-ttu-id="247c8-133">O parâmetro **Noenumerate** suprime o comportamento padrão e impede a `Write-Output` enumeração da saída.</span><span class="sxs-lookup"><span data-stu-id="247c8-133">The **NoEnumerate** parameter suppresses the default behavior, and prevents `Write-Output` from enumerating output.</span></span> <span data-ttu-id="247c8-134">O parâmetro **Noenumerate** não terá nenhum efeito se o comando for encapsulado entre parênteses, porque os parênteses forçam a enumeração.</span><span class="sxs-lookup"><span data-stu-id="247c8-134">The **NoEnumerate** parameter has no effect if the command is wrapped in parentheses, because the parentheses force enumeration.</span></span> <span data-ttu-id="247c8-135">Por exemplo, `(Write-Output 1,2,3)` o ainda enumera a matriz.</span><span class="sxs-lookup"><span data-stu-id="247c8-135">For example, `(Write-Output 1,2,3)` still enumerates the array.</span></span>

> [!NOTE]
> <span data-ttu-id="247c8-136">Essa opção funciona apenas corretamente com o PowerShell Core 6,2 e mais recente.</span><span class="sxs-lookup"><span data-stu-id="247c8-136">This switch only works correctly with PowerShell Core 6.2 and newer.</span></span> <span data-ttu-id="247c8-137">Em versões mais antigas do PowerShell Core, a coleção ainda é enumerada mesmo com o uso dessa opção.</span><span class="sxs-lookup"><span data-stu-id="247c8-137">On older versions of PowerShell Core, the collection is still enumerated even with use of this switch.</span></span>

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

### <span data-ttu-id="247c8-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="247c8-138">CommonParameters</span></span>

<span data-ttu-id="247c8-139">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="247c8-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="247c8-140">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="247c8-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="247c8-141">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="247c8-141">INPUTS</span></span>

### <span data-ttu-id="247c8-142">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="247c8-142">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="247c8-143">Você pode canalizar objetos para `Write-Output` .</span><span class="sxs-lookup"><span data-stu-id="247c8-143">You can pipe objects to `Write-Output`.</span></span>

## <span data-ttu-id="247c8-144">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="247c8-144">OUTPUTS</span></span>

### <span data-ttu-id="247c8-145">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="247c8-145">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="247c8-146">`Write-Output` Retorna os objetos que são enviados como entrada.</span><span class="sxs-lookup"><span data-stu-id="247c8-146">`Write-Output` returns the objects that are submitted as input.</span></span>

## <span data-ttu-id="247c8-147">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="247c8-147">NOTES</span></span>

## <span data-ttu-id="247c8-148">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="247c8-148">RELATED LINKS</span></span>

[<span data-ttu-id="247c8-149">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="247c8-149">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="247c8-150">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="247c8-150">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="247c8-151">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="247c8-151">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="247c8-152">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="247c8-152">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="247c8-153">Write-Error</span><span class="sxs-lookup"><span data-stu-id="247c8-153">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="247c8-154">Write-Host</span><span class="sxs-lookup"><span data-stu-id="247c8-154">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="247c8-155">Write-Information</span><span class="sxs-lookup"><span data-stu-id="247c8-155">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="247c8-156">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="247c8-156">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="247c8-157">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="247c8-157">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="247c8-158">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="247c8-158">Write-Warning</span></span>](Write-Warning.md)
