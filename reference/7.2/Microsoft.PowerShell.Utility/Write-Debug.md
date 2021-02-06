---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 3d23f76dbf8e1c9a21805a4914038c8c4f319852
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597829"
---
# <span data-ttu-id="ea193-102">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="ea193-102">Write-Debug</span></span>

## <span data-ttu-id="ea193-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ea193-103">SYNOPSIS</span></span>
<span data-ttu-id="ea193-104">Grava uma mensagem de depuração para o console.</span><span class="sxs-lookup"><span data-stu-id="ea193-104">Writes a debug message to the console.</span></span>

## <span data-ttu-id="ea193-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ea193-105">SYNTAX</span></span>

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="ea193-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ea193-106">DESCRIPTION</span></span>

<span data-ttu-id="ea193-107">O `Write-Debug` cmdlet grava mensagens de depuração no host a partir de um script ou comando.</span><span class="sxs-lookup"><span data-stu-id="ea193-107">The `Write-Debug` cmdlet writes debug messages to the host from a script or command.</span></span>

<span data-ttu-id="ea193-108">Por padrão, as mensagens de depuração não são exibidas no console do, mas você pode exibi-las usando o parâmetro de **depuração** ou a `$DebugPreference` variável.</span><span class="sxs-lookup"><span data-stu-id="ea193-108">By default, debug messages are not displayed in the console, but you can display them by using the **Debug** parameter or the `$DebugPreference` variable.</span></span>

## <span data-ttu-id="ea193-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ea193-109">EXAMPLES</span></span>

### <span data-ttu-id="ea193-110">Exemplo 1: entender $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="ea193-110">Example 1: Understand $DebugPreference</span></span>

<span data-ttu-id="ea193-111">Este exemplo grava uma mensagem de depuração.</span><span class="sxs-lookup"><span data-stu-id="ea193-111">This example writes a debug message.</span></span>

```powershell
Write-Debug "Cannot open file."
```

<span data-ttu-id="ea193-112">O valor padrão de `$DebugPreference` é **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="ea193-112">The default value of `$DebugPreference` is **SilentlyContinue**.</span></span> <span data-ttu-id="ea193-113">Portanto, a mensagem não é exibida no console do.</span><span class="sxs-lookup"><span data-stu-id="ea193-113">Therefore, the message is not displayed in the console.</span></span>

### <span data-ttu-id="ea193-114">Exemplo 2: alterar o valor de $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="ea193-114">Example 2: Change the value of $DebugPreference</span></span>

<span data-ttu-id="ea193-115">Este exemplo mostra o efeito da alteração do valor da `$DebugPreference` variável.</span><span class="sxs-lookup"><span data-stu-id="ea193-115">This example shows the effect of changing the value of the `$DebugPreference` variable.</span></span> <span data-ttu-id="ea193-116">Primeiro, exibimos o valor atual de `$DebugPreference` e tentamos gravar uma mensagem de depuração.</span><span class="sxs-lookup"><span data-stu-id="ea193-116">First, we display the current value of `$DebugPreference` and attempt to write a debug message.</span></span> <span data-ttu-id="ea193-117">Em seguida, alteramos o valor de `$DebugPreference` para **continuar**, o que permite que as mensagens de depuração sejam exibidas.</span><span class="sxs-lookup"><span data-stu-id="ea193-117">Then we change the value of `$DebugPreference` to **Continue**, which allows debug messages to be displayed.</span></span>

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

<span data-ttu-id="ea193-118">Para obter mais informações sobre o `$DebugPreference` , consulte [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span><span class="sxs-lookup"><span data-stu-id="ea193-118">For more information about `$DebugPreference`, see [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span></span>

### <span data-ttu-id="ea193-119">Exemplo 3: usar o parâmetro de depuração para substituir $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="ea193-119">Example 3: Use the Debug parameter to override $DebugPreference</span></span>

<span data-ttu-id="ea193-120">A `Test-Debug` função grava o valor da `$DebugPreference` variável para o host do PowerShell e para o fluxo de depuração.</span><span class="sxs-lookup"><span data-stu-id="ea193-120">The `Test-Debug` function writes the value of the `$DebugPreference` variable to the PowerShell host and to the Debug stream.</span></span> <span data-ttu-id="ea193-121">Neste exemplo, usamos o parâmetro **debug** para substituir o `$DebugPreference` valor.</span><span class="sxs-lookup"><span data-stu-id="ea193-121">In this example, we use the **Debug** parameter to override the `$DebugPreference` value.</span></span>

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
DEBUG: $DebugPreference is Continue
$DebugPreference is Continue
PS> $DebugPreference
SilentlyContinue
```

<span data-ttu-id="ea193-122">Observe que o valor de é `$DebugPreference` alterado quando você usa o parâmetro de **depuração** .</span><span class="sxs-lookup"><span data-stu-id="ea193-122">Notice that the value of `$DebugPreference` changes when you use the **Debug** parameter.</span></span> <span data-ttu-id="ea193-123">Essa alteração afeta apenas o escopo da função.</span><span class="sxs-lookup"><span data-stu-id="ea193-123">This change only affects the scope of the function.</span></span> <span data-ttu-id="ea193-124">O valor não é afetado fora da função.</span><span class="sxs-lookup"><span data-stu-id="ea193-124">The value is not affected outside the function.</span></span>

<span data-ttu-id="ea193-125">Para obter mais informações sobre o parâmetro comum de **depuração** , consulte [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ea193-125">For more information about the **Debug** common parameter, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ea193-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ea193-126">PARAMETERS</span></span>

### <span data-ttu-id="ea193-127">-Mensagem</span><span class="sxs-lookup"><span data-stu-id="ea193-127">-Message</span></span>

<span data-ttu-id="ea193-128">Especifica a mensagem de depuração para enviar para o console.</span><span class="sxs-lookup"><span data-stu-id="ea193-128">Specifies the debug message to send to the console.</span></span>

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

### <span data-ttu-id="ea193-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ea193-129">CommonParameters</span></span>

<span data-ttu-id="ea193-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ea193-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ea193-131">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ea193-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ea193-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ea193-132">INPUTS</span></span>

### <span data-ttu-id="ea193-133">System.String</span><span class="sxs-lookup"><span data-stu-id="ea193-133">System.String</span></span>

<span data-ttu-id="ea193-134">É possível canalizar uma cadeia de caracteres que contém uma mensagem de depuração para `Write-Debug` .</span><span class="sxs-lookup"><span data-stu-id="ea193-134">You can pipe a string that contains a debug message to `Write-Debug`.</span></span>

## <span data-ttu-id="ea193-135">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ea193-135">OUTPUTS</span></span>

### <span data-ttu-id="ea193-136">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ea193-136">None</span></span>

<span data-ttu-id="ea193-137">`Write-Debug` grava somente no fluxo de depuração.</span><span class="sxs-lookup"><span data-stu-id="ea193-137">`Write-Debug` only writes to the debug stream.</span></span> <span data-ttu-id="ea193-138">Ele não grava nenhum objeto no pipeline.</span><span class="sxs-lookup"><span data-stu-id="ea193-138">It does not write any objects to the pipeline.</span></span>

## <span data-ttu-id="ea193-139">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ea193-139">NOTES</span></span>

## <span data-ttu-id="ea193-140">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ea193-140">RELATED LINKS</span></span>

[<span data-ttu-id="ea193-141">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="ea193-141">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="ea193-142">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="ea193-142">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="ea193-143">Write-Error</span><span class="sxs-lookup"><span data-stu-id="ea193-143">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="ea193-144">Write-Host</span><span class="sxs-lookup"><span data-stu-id="ea193-144">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="ea193-145">Write-Output</span><span class="sxs-lookup"><span data-stu-id="ea193-145">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="ea193-146">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="ea193-146">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="ea193-147">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="ea193-147">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="ea193-148">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="ea193-148">Write-Warning</span></span>](Write-Warning.md)
