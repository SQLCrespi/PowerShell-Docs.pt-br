---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-verbose?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Verbose
ms.openlocfilehash: 07289eb2f43a0527ab523a10319777d3ef0e8ddf
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196390"
---
# <span data-ttu-id="e1d76-103">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="e1d76-103">Write-Verbose</span></span>

## <span data-ttu-id="e1d76-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e1d76-104">SYNOPSIS</span></span>
<span data-ttu-id="e1d76-105">Grava o texto para o fluxo de mensagem detalhada.</span><span class="sxs-lookup"><span data-stu-id="e1d76-105">Writes text to the verbose message stream.</span></span>

## <span data-ttu-id="e1d76-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e1d76-106">SYNTAX</span></span>

```
Write-Verbose [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="e1d76-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e1d76-107">DESCRIPTION</span></span>

<span data-ttu-id="e1d76-108">O `Write-Verbose` cmdlet grava o texto no fluxo de mensagens detalhadas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1d76-108">The `Write-Verbose` cmdlet writes text to the verbose message stream in PowerShell.</span></span> <span data-ttu-id="e1d76-109">Normalmente, o fluxo de mensagens detalhados é usado para fornecer informações mais detalhadas sobre o processamento de comandos.</span><span class="sxs-lookup"><span data-stu-id="e1d76-109">Typically, the verbose message stream is used to deliver more in depth information about command processing.</span></span>

<span data-ttu-id="e1d76-110">Por padrão, o fluxo de mensagens detalhadas não é exibido, mas você pode exibi-lo alterando o valor da `$VerbosePreference` variável ou usando o parâmetro comum **detalhado** em qualquer comando.</span><span class="sxs-lookup"><span data-stu-id="e1d76-110">By default, the verbose message stream is not displayed, but you can display it by changing the value of the `$VerbosePreference` variable or using the **Verbose** common parameter in any command.</span></span>

## <span data-ttu-id="e1d76-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e1d76-111">EXAMPLES</span></span>

### <span data-ttu-id="e1d76-112">Exemplo 1: gravar uma mensagem de status</span><span class="sxs-lookup"><span data-stu-id="e1d76-112">Example 1: Write a status message</span></span>

```powershell
Write-Verbose -Message "Searching the Application Event Log."
Write-Verbose -Message "Searching the Application Event Log." -Verbose
```

<span data-ttu-id="e1d76-113">Esses comandos usam o `Write-Verbose` cmdlet para exibir uma mensagem de status.</span><span class="sxs-lookup"><span data-stu-id="e1d76-113">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="e1d76-114">Por padrão, a mensagem não é exibida.</span><span class="sxs-lookup"><span data-stu-id="e1d76-114">By default, the message is not displayed.</span></span>

<span data-ttu-id="e1d76-115">O segundo comando usa o parâmetro comum **Verbose** , que exibe todas as mensagens detalhadas, independentemente do valor da `$VerbosePreference` variável.</span><span class="sxs-lookup"><span data-stu-id="e1d76-115">The second command uses the **Verbose** common parameter, which displays any verbose messages, regardless of the value of the `$VerbosePreference` variable.</span></span>

### <span data-ttu-id="e1d76-116">Exemplo 2: definir $VerbosePreference e gravar uma mensagem de status</span><span class="sxs-lookup"><span data-stu-id="e1d76-116">Example 2: Set $VerbosePreference and write a status message</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose "Copying file $filename"
```

<span data-ttu-id="e1d76-117">Esses comandos usam o `Write-Verbose` cmdlet para exibir uma mensagem de status.</span><span class="sxs-lookup"><span data-stu-id="e1d76-117">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="e1d76-118">Por padrão, a mensagem não é exibida.</span><span class="sxs-lookup"><span data-stu-id="e1d76-118">By default, the message is not displayed.</span></span>

<span data-ttu-id="e1d76-119">O primeiro comando atribui um valor de continuar à `$VerbosePreference` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="e1d76-119">The first command assigns a value of Continue to the `$VerbosePreference` preference variable.</span></span> <span data-ttu-id="e1d76-120">O valor padrão, `SilentlyContinue` , suprime as mensagens detalhadas.</span><span class="sxs-lookup"><span data-stu-id="e1d76-120">The default value, `SilentlyContinue`, suppresses verbose messages.</span></span> <span data-ttu-id="e1d76-121">O segundo comando grava uma mensagem detalhada.</span><span class="sxs-lookup"><span data-stu-id="e1d76-121">The second command writes a verbose message.</span></span>

## <span data-ttu-id="e1d76-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e1d76-122">PARAMETERS</span></span>

### <span data-ttu-id="e1d76-123">-Mensagem</span><span class="sxs-lookup"><span data-stu-id="e1d76-123">-Message</span></span>

<span data-ttu-id="e1d76-124">Especifica a mensagem a ser exibida.</span><span class="sxs-lookup"><span data-stu-id="e1d76-124">Specifies the message to display.</span></span> <span data-ttu-id="e1d76-125">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="e1d76-125">This parameter is required.</span></span> <span data-ttu-id="e1d76-126">Você também pode canalizar uma cadeia de caracteres de mensagem para `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="e1d76-126">You can also pipe a message string to `Write-Verbose`.</span></span>

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

### <span data-ttu-id="e1d76-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e1d76-127">CommonParameters</span></span>

<span data-ttu-id="e1d76-128">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e1d76-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e1d76-129">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e1d76-129">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e1d76-130">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e1d76-130">INPUTS</span></span>

### <span data-ttu-id="e1d76-131">System.String</span><span class="sxs-lookup"><span data-stu-id="e1d76-131">System.String</span></span>

<span data-ttu-id="e1d76-132">É possível canalizar uma cadeia de caracteres que contém a mensagem para `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="e1d76-132">You can pipe a string that contains the message to `Write-Verbose`.</span></span>

## <span data-ttu-id="e1d76-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e1d76-133">OUTPUTS</span></span>

### <span data-ttu-id="e1d76-134">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e1d76-134">None</span></span>

<span data-ttu-id="e1d76-135">`Write-Verbose` grava somente no fluxo de mensagens detalhadas.</span><span class="sxs-lookup"><span data-stu-id="e1d76-135">`Write-Verbose` writes only to the verbose message stream.</span></span>

## <span data-ttu-id="e1d76-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e1d76-136">NOTES</span></span>

- <span data-ttu-id="e1d76-137">As mensagens detalhadas são retornadas somente quando o comando usa o parâmetro **Verbose** comum.</span><span class="sxs-lookup"><span data-stu-id="e1d76-137">Verbose messages are returned only when the command uses the **Verbose** common parameter.</span></span> <span data-ttu-id="e1d76-138">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e1d76-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>
- <span data-ttu-id="e1d76-139">Em trabalhos em segundo plano do Windows PowerShell e em comandos remotos, a `$VerbosePreference` variável na sessão de trabalho e na sessão remota determinam se a mensagem detalhada é exibida por padrão.</span><span class="sxs-lookup"><span data-stu-id="e1d76-139">In Windows PowerShell background jobs and remote commands, the `$VerbosePreference` variable in the job session and remote session determine whether the verbose message is displayed by default.</span></span>
  <span data-ttu-id="e1d76-140">Para obter mais informações sobre a `$VerbosePreference` variável, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="e1d76-140">For more information about the `$VerbosePreference` variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="e1d76-141">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e1d76-141">RELATED LINKS</span></span>

[<span data-ttu-id="e1d76-142">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="e1d76-142">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="e1d76-143">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="e1d76-143">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="e1d76-144">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="e1d76-144">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="e1d76-145">Erro de gravação</span><span class="sxs-lookup"><span data-stu-id="e1d76-145">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="e1d76-146">Write-Host</span><span class="sxs-lookup"><span data-stu-id="e1d76-146">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="e1d76-147">Write-Information</span><span class="sxs-lookup"><span data-stu-id="e1d76-147">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="e1d76-148">Write-Output</span><span class="sxs-lookup"><span data-stu-id="e1d76-148">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="e1d76-149">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="e1d76-149">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="e1d76-150">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="e1d76-150">Write-Warning</span></span>](Write-Warning.md)
