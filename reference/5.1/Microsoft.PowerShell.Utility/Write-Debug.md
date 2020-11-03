---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 7e622367f1753fc15bed26fe083e9f343fd82b85
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196421"
---
# <span data-ttu-id="511fd-103">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="511fd-103">Write-Debug</span></span>

## <span data-ttu-id="511fd-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="511fd-104">SYNOPSIS</span></span>
<span data-ttu-id="511fd-105">Grava uma mensagem de depuração para o console.</span><span class="sxs-lookup"><span data-stu-id="511fd-105">Writes a debug message to the console.</span></span>

## <span data-ttu-id="511fd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="511fd-106">SYNTAX</span></span>

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="511fd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="511fd-107">DESCRIPTION</span></span>

<span data-ttu-id="511fd-108">O `Write-Debug` cmdlet grava mensagens de depuração no host a partir de um script ou comando.</span><span class="sxs-lookup"><span data-stu-id="511fd-108">The `Write-Debug` cmdlet writes debug messages to the host from a script or command.</span></span>

<span data-ttu-id="511fd-109">Por padrão, as mensagens de depuração não são exibidas no console do, mas você pode exibi-las usando o parâmetro de **depuração** ou a `$DebugPreference` variável.</span><span class="sxs-lookup"><span data-stu-id="511fd-109">By default, debug messages are not displayed in the console, but you can display them by using the **Debug** parameter or the `$DebugPreference` variable.</span></span>

## <span data-ttu-id="511fd-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="511fd-110">EXAMPLES</span></span>

### <span data-ttu-id="511fd-111">Exemplo 1: entender $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="511fd-111">Example 1: Understand $DebugPreference</span></span>

<span data-ttu-id="511fd-112">Este exemplo grava uma mensagem de depuração.</span><span class="sxs-lookup"><span data-stu-id="511fd-112">This example writes a debug message.</span></span>

```powershell
Write-Debug "Cannot open file."
```

<span data-ttu-id="511fd-113">O valor padrão de `$DebugPreference` é **SilentlyContinue** .</span><span class="sxs-lookup"><span data-stu-id="511fd-113">The default value of `$DebugPreference` is **SilentlyContinue** .</span></span> <span data-ttu-id="511fd-114">Portanto, a mensagem não é exibida no console do.</span><span class="sxs-lookup"><span data-stu-id="511fd-114">Therefore, the message is not displayed in the console.</span></span>

### <span data-ttu-id="511fd-115">Exemplo 2: alterar o valor de $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="511fd-115">Example 2: Change the value of $DebugPreference</span></span>

<span data-ttu-id="511fd-116">Este exemplo mostra o efeito da alteração do valor da `$DebugPreference` variável.</span><span class="sxs-lookup"><span data-stu-id="511fd-116">This example shows the effect of changing the value of the `$DebugPreference` variable.</span></span> <span data-ttu-id="511fd-117">Primeiro, exibimos o valor atual de `$DebugPreference` e tentamos gravar uma mensagem de depuração.</span><span class="sxs-lookup"><span data-stu-id="511fd-117">First, we display the current value of `$DebugPreference` and attempt to write a debug message.</span></span> <span data-ttu-id="511fd-118">Em seguida, alteramos o valor de `$DebugPreference` para **continuar** , o que permite que as mensagens de depuração sejam exibidas.</span><span class="sxs-lookup"><span data-stu-id="511fd-118">Then we change the value of `$DebugPreference` to **Continue** , which allows debug messages to be displayed.</span></span>

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

<span data-ttu-id="511fd-119">Para obter mais informações sobre o `$DebugPreference` , consulte [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span><span class="sxs-lookup"><span data-stu-id="511fd-119">For more information about `$DebugPreference`, see [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span></span>

### <span data-ttu-id="511fd-120">Exemplo 3: usar o parâmetro de depuração para substituir $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="511fd-120">Example 3: Use the Debug parameter to override $DebugPreference</span></span>

<span data-ttu-id="511fd-121">A `Test-Debug` função grava o valor da `$DebugPreference` variável para o host do PowerShell e para o fluxo de depuração.</span><span class="sxs-lookup"><span data-stu-id="511fd-121">The `Test-Debug` function writes the value of the `$DebugPreference` variable to the PowerShell host and to the Debug stream.</span></span> <span data-ttu-id="511fd-122">Neste exemplo, usamos o parâmetro **debug** para substituir o `$DebugPreference` valor.</span><span class="sxs-lookup"><span data-stu-id="511fd-122">In this example, we use the **Debug** parameter to override the `$DebugPreference` value.</span></span>

```powershell
function Test-Debug {
    [CmdletBinding()]
    param()
    Write-Debug ('$DebugPreference is ' + $DebugPreference)
    Write-Host ('$DebugPreference is ' + $DebugPreference)
}
```

```
PS> Test-Debug
$DebugPreference is SilentlyContinue

PS> Test-Debug -Debug
DEBUG: $DebugPreference is Inquire

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
$DebugPreference is Inquire
PS> $DebugPreference
SilentlyContinue
```

<span data-ttu-id="511fd-123">Observe que o valor de é `$DebugPreference` alterado quando você usa o parâmetro de **depuração** .</span><span class="sxs-lookup"><span data-stu-id="511fd-123">Notice that the value of `$DebugPreference` changes when you use the **Debug** parameter.</span></span> <span data-ttu-id="511fd-124">Essa alteração afeta apenas o escopo da função.</span><span class="sxs-lookup"><span data-stu-id="511fd-124">This change only affects the scope of the function.</span></span> <span data-ttu-id="511fd-125">O valor não é afetado fora da função.</span><span class="sxs-lookup"><span data-stu-id="511fd-125">The value is not affected outside the function.</span></span>

> [!NOTE]
> <span data-ttu-id="511fd-126">Quando o valor de `$DebugPreference` é **consultado** , o PowerShell interrompe a execução para perguntar se a execução deve continuar.</span><span class="sxs-lookup"><span data-stu-id="511fd-126">When the value of `$DebugPreference` is **Inquire** , PowerShell halts execution to ask if execution should continue.</span></span>

<span data-ttu-id="511fd-127">Para obter mais informações sobre o parâmetro comum de **depuração** , consulte [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="511fd-127">For more information about the **Debug** common parameter, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="511fd-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="511fd-128">PARAMETERS</span></span>

### <span data-ttu-id="511fd-129">-Mensagem</span><span class="sxs-lookup"><span data-stu-id="511fd-129">-Message</span></span>

<span data-ttu-id="511fd-130">Especifica a mensagem de depuração para enviar para o console.</span><span class="sxs-lookup"><span data-stu-id="511fd-130">Specifies the debug message to send to the console.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="511fd-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="511fd-131">CommonParameters</span></span>

<span data-ttu-id="511fd-132">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="511fd-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="511fd-133">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="511fd-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="511fd-134">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="511fd-134">INPUTS</span></span>

### <span data-ttu-id="511fd-135">System.String</span><span class="sxs-lookup"><span data-stu-id="511fd-135">System.String</span></span>

<span data-ttu-id="511fd-136">É possível canalizar uma cadeia de caracteres que contém uma mensagem de depuração para `Write-Debug` .</span><span class="sxs-lookup"><span data-stu-id="511fd-136">You can pipe a string that contains a debug message to `Write-Debug`.</span></span>

## <span data-ttu-id="511fd-137">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="511fd-137">OUTPUTS</span></span>

### <span data-ttu-id="511fd-138">Nenhum</span><span class="sxs-lookup"><span data-stu-id="511fd-138">None</span></span>

<span data-ttu-id="511fd-139">`Write-Debug` grava somente no fluxo de depuração.</span><span class="sxs-lookup"><span data-stu-id="511fd-139">`Write-Debug` only writes to the debug stream.</span></span> <span data-ttu-id="511fd-140">Ele não grava nenhum objeto no pipeline.</span><span class="sxs-lookup"><span data-stu-id="511fd-140">It does not write any objects to the pipeline.</span></span>

## <span data-ttu-id="511fd-141">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="511fd-141">NOTES</span></span>

## <span data-ttu-id="511fd-142">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="511fd-142">RELATED LINKS</span></span>

[<span data-ttu-id="511fd-143">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="511fd-143">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="511fd-144">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="511fd-144">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="511fd-145">Erro de gravação</span><span class="sxs-lookup"><span data-stu-id="511fd-145">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="511fd-146">Write-Host</span><span class="sxs-lookup"><span data-stu-id="511fd-146">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="511fd-147">Write-Output</span><span class="sxs-lookup"><span data-stu-id="511fd-147">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="511fd-148">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="511fd-148">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="511fd-149">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="511fd-149">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="511fd-150">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="511fd-150">Write-Warning</span></span>](Write-Warning.md)
