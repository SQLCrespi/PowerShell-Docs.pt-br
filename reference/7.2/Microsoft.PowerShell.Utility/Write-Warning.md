---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-warning?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Warning
ms.openlocfilehash: 18c168e894989fea8b26fe000a624f91d7345332
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595781"
---
# <span data-ttu-id="796b9-102">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="796b9-102">Write-Warning</span></span>

## <span data-ttu-id="796b9-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="796b9-103">SYNOPSIS</span></span>
<span data-ttu-id="796b9-104">Grava uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="796b9-104">Writes a warning message.</span></span>

## <span data-ttu-id="796b9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="796b9-105">SYNTAX</span></span>

```
Write-Warning [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="796b9-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="796b9-106">DESCRIPTION</span></span>

<span data-ttu-id="796b9-107">O `Write-Warning` cmdlet grava uma mensagem de aviso no host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="796b9-107">The `Write-Warning` cmdlet writes a warning message to the PowerShell host.</span></span> <span data-ttu-id="796b9-108">A resposta ao aviso depende do valor da variável do usuário `$WarningPreference` e do uso do parâmetro de **aviso** comum.</span><span class="sxs-lookup"><span data-stu-id="796b9-108">The response to the warning depends on the value of the user's `$WarningPreference` variable and the use of the **WarningAction** common parameter.</span></span>

## <span data-ttu-id="796b9-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="796b9-109">EXAMPLES</span></span>

### <span data-ttu-id="796b9-110">Exemplo 1: gravar uma mensagem de aviso</span><span class="sxs-lookup"><span data-stu-id="796b9-110">Example 1: Write a warning message</span></span>

<span data-ttu-id="796b9-111">Esse comando exibe a mensagem "aviso: Este é apenas um aviso de teste".</span><span class="sxs-lookup"><span data-stu-id="796b9-111">This command displays the message "WARNING: This is only a test warning."</span></span>

```powershell
Write-Warning "This is only a test warning."
```

### <span data-ttu-id="796b9-112">Exemplo 2: passar uma cadeia de caracteres para Write-Warning</span><span class="sxs-lookup"><span data-stu-id="796b9-112">Example 2: Pass a string to Write-Warning</span></span>

<span data-ttu-id="796b9-113">Esse comando mostra que você pode usar um operador de pipeline ( `|` ) para enviar uma cadeia de caracteres para `Write-Warning` .</span><span class="sxs-lookup"><span data-stu-id="796b9-113">This command shows that you can use a pipeline operator (`|`) to send a string to `Write-Warning`.</span></span>
<span data-ttu-id="796b9-114">Você pode salvar a cadeia de caracteres em uma variável, conforme mostrado neste comando, ou canalizar a cadeia de caracteres diretamente para `Write-Warning` .</span><span class="sxs-lookup"><span data-stu-id="796b9-114">You can save the string in a variable, as shown in this command, or pipe the string directly to `Write-Warning`.</span></span>

```powershell
$w = "This is only a test warning."
$w | Write-Warning
```

### <span data-ttu-id="796b9-115">Exemplo 3: definir a variável $WarningPreference e gravar um aviso</span><span class="sxs-lookup"><span data-stu-id="796b9-115">Example 3: Set the $WarningPreference variable and write a warning</span></span>

<span data-ttu-id="796b9-116">Este exemplo mostra o efeito do valor da `$WarningPreference` variável em um `Write-Warning` comando.</span><span class="sxs-lookup"><span data-stu-id="796b9-116">This example shows the effect of the value of the `$WarningPreference` variable on a `Write-Warning` command.</span></span>

```powershell
PS> $WarningPreference
Continue
PS> Write-Warning "This is only a test warning."
This is only a test warning.
PS> $WarningPreference = "SilentlyContinue"
PS> Write-Warning "This is only a test warning."
PS> $WarningPreference = "Stop"
PS> Write-Warning "This is only a test warning."
WARNING: This is only a test message.
Write-Warning : Command execution stopped because the shell variable "WarningPreference" is set to Stop.
At line:1 char:14
     + Write-Warning <<<<  "This is only a test message."
```

<span data-ttu-id="796b9-117">O primeiro comando exibe o valor padrão da `$WarningPreference` variável, que é `Continue` .</span><span class="sxs-lookup"><span data-stu-id="796b9-117">The first command displays the default value of the `$WarningPreference` variable, which is `Continue`.</span></span> <span data-ttu-id="796b9-118">Como resultado, quando você escreve um aviso, a mensagem de aviso será exibida e a execução continuará.</span><span class="sxs-lookup"><span data-stu-id="796b9-118">As a result, when you write a warning, the warning message is displayed and execution continues.</span></span>

<span data-ttu-id="796b9-119">Quando você altera o valor da `$WarningPreference` variável, o efeito do comando é `Write-Warning` alterado novamente.</span><span class="sxs-lookup"><span data-stu-id="796b9-119">When you change the value of the `$WarningPreference` variable, the effect of the `Write-Warning` command changes again.</span></span> <span data-ttu-id="796b9-120">Um valor de `SilentlyContinue` suprime o aviso.</span><span class="sxs-lookup"><span data-stu-id="796b9-120">A value of `SilentlyContinue` suppresses the warning.</span></span> <span data-ttu-id="796b9-121">Um valor `Stop` exibe o aviso e, em seguida, interrompe a execução do comando.</span><span class="sxs-lookup"><span data-stu-id="796b9-121">A value of `Stop` displays the warning and then stops execution of the command.</span></span>

<span data-ttu-id="796b9-122">Para obter mais informações sobre a `$WarningPreference` variável, consulte [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="796b9-122">For more information about the `$WarningPreference` variable, see [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="796b9-123">Exemplo 4: definir o parâmetro WarningAction e gravar um aviso</span><span class="sxs-lookup"><span data-stu-id="796b9-123">Example 4: Set the WarningAction parameter and write a warning</span></span>

<span data-ttu-id="796b9-124">Este exemplo mostra o efeito do parâmetro comum **WarningAction** em um `Write-Warning` comando.</span><span class="sxs-lookup"><span data-stu-id="796b9-124">This example shows the effect of the **WarningAction** common parameter on a `Write-Warning` command.</span></span> <span data-ttu-id="796b9-125">Você pode usar o parâmetro de **aviso** comum com qualquer cmdlet para determinar como o PowerShell responde a avisos resultantes desse comando.</span><span class="sxs-lookup"><span data-stu-id="796b9-125">You can use the **WarningAction** common parameter with any cmdlet to determine how PowerShell responds to warnings resulting from that command.</span></span> <span data-ttu-id="796b9-126">O parâmetro de **aviso** comum substitui o valor do `$WarningPreference` somente para esse comando específico.</span><span class="sxs-lookup"><span data-stu-id="796b9-126">The **WarningAction** common parameter overrides the value of the `$WarningPreference` only for that particular command.</span></span>

```powershell
PS> Write-Warning "This is only a test warning." -WarningAction Inquire
WARNING: This is only a test warning.
Confirm
Continue with this operation?
 [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="796b9-127">Esse comando usa o `Write-Warning` cmdlet para exibir um aviso.</span><span class="sxs-lookup"><span data-stu-id="796b9-127">This command uses the `Write-Warning` cmdlet to display a warning.</span></span> <span data-ttu-id="796b9-128">O parâmetro de **aviso** comum com um valor de consulta instrui o sistema a solicitar o usuário quando o comando exibir um aviso.</span><span class="sxs-lookup"><span data-stu-id="796b9-128">The **WarningAction** common parameter with a value of Inquire directs the system to prompt the user when the command displays a warning.</span></span>

<span data-ttu-id="796b9-129">Para obter mais informações sobre o parâmetro de **aviso** comum, consulte [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="796b9-129">For more information about the **WarningAction** common parameter, see [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="796b9-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="796b9-130">PARAMETERS</span></span>

### <span data-ttu-id="796b9-131">-Mensagem</span><span class="sxs-lookup"><span data-stu-id="796b9-131">-Message</span></span>
<span data-ttu-id="796b9-132">Especifica a mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="796b9-132">Specifies the warning message.</span></span>

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

### <span data-ttu-id="796b9-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="796b9-133">CommonParameters</span></span>

<span data-ttu-id="796b9-134">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="796b9-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="796b9-135">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="796b9-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="796b9-136">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="796b9-136">INPUTS</span></span>

### <span data-ttu-id="796b9-137">System.String</span><span class="sxs-lookup"><span data-stu-id="796b9-137">System.String</span></span>

<span data-ttu-id="796b9-138">É possível canalizar uma cadeia de caracteres que contém o aviso para `Write-Warning` .</span><span class="sxs-lookup"><span data-stu-id="796b9-138">You can pipe a string that contains the warning to `Write-Warning`.</span></span>

## <span data-ttu-id="796b9-139">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="796b9-139">OUTPUTS</span></span>

### <span data-ttu-id="796b9-140">Nenhum</span><span class="sxs-lookup"><span data-stu-id="796b9-140">None</span></span>

<span data-ttu-id="796b9-141">`Write-Warning` grava somente no fluxo de aviso.</span><span class="sxs-lookup"><span data-stu-id="796b9-141">`Write-Warning` writes only to the warning stream.</span></span> <span data-ttu-id="796b9-142">Ele não gera outras saídas.</span><span class="sxs-lookup"><span data-stu-id="796b9-142">It does not generate any other output.</span></span>

## <span data-ttu-id="796b9-143">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="796b9-143">NOTES</span></span>

<span data-ttu-id="796b9-144">O valor padrão para a `$WarningPreference` variável é `Continue` , que exibe o aviso e, em seguida, continua executando o comando.</span><span class="sxs-lookup"><span data-stu-id="796b9-144">The default value for the `$WarningPreference` variable is `Continue`, which displays the warning and then continues executing the command.</span></span> <span data-ttu-id="796b9-145">Para determinar os valores válidos para uma variável de preferência, como `$WarningPreference` , defina-o como uma cadeia de caracteres aleatórios, como "ABC".</span><span class="sxs-lookup"><span data-stu-id="796b9-145">To determine valid values for a preference variable such as `$WarningPreference`, set it to a string of random characters, such as "abc".</span></span> <span data-ttu-id="796b9-146">A mensagem de erro resultante lista os valores válidos.</span><span class="sxs-lookup"><span data-stu-id="796b9-146">The resulting error message lists the valid values.</span></span>

## <span data-ttu-id="796b9-147">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="796b9-147">RELATED LINKS</span></span>

[<span data-ttu-id="796b9-148">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="796b9-148">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="796b9-149">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="796b9-149">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="796b9-150">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="796b9-150">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="796b9-151">Write-Error</span><span class="sxs-lookup"><span data-stu-id="796b9-151">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="796b9-152">Write-Host</span><span class="sxs-lookup"><span data-stu-id="796b9-152">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="796b9-153">Write-Information</span><span class="sxs-lookup"><span data-stu-id="796b9-153">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="796b9-154">Write-Output</span><span class="sxs-lookup"><span data-stu-id="796b9-154">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="796b9-155">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="796b9-155">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="796b9-156">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="796b9-156">Write-Verbose</span></span>](Write-Verbose.md)
