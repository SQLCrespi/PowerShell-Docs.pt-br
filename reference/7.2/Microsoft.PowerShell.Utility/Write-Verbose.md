---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-verbose?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Verbose
ms.openlocfilehash: 177e32106f37c59593bbecac13843f6603327cc9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595589"
---
# <span data-ttu-id="b61f9-102">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="b61f9-102">Write-Verbose</span></span>

## <span data-ttu-id="b61f9-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b61f9-103">SYNOPSIS</span></span>
<span data-ttu-id="b61f9-104">Grava o texto para o fluxo de mensagem detalhada.</span><span class="sxs-lookup"><span data-stu-id="b61f9-104">Writes text to the verbose message stream.</span></span>

## <span data-ttu-id="b61f9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b61f9-105">SYNTAX</span></span>

```
Write-Verbose [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="b61f9-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b61f9-106">DESCRIPTION</span></span>

<span data-ttu-id="b61f9-107">O `Write-Verbose` cmdlet grava o texto no fluxo de mensagens detalhadas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b61f9-107">The `Write-Verbose` cmdlet writes text to the verbose message stream in PowerShell.</span></span> <span data-ttu-id="b61f9-108">Normalmente, o fluxo de mensagens detalhados é usado para fornecer informações mais detalhadas sobre o processamento de comandos.</span><span class="sxs-lookup"><span data-stu-id="b61f9-108">Typically, the verbose message stream is used to deliver more in depth information about command processing.</span></span>

<span data-ttu-id="b61f9-109">Por padrão, o fluxo de mensagens detalhadas não é exibido, mas você pode exibi-lo alterando o valor da `$VerbosePreference` variável ou usando o parâmetro comum **detalhado** em qualquer comando.</span><span class="sxs-lookup"><span data-stu-id="b61f9-109">By default, the verbose message stream is not displayed, but you can display it by changing the value of the `$VerbosePreference` variable or using the **Verbose** common parameter in any command.</span></span>

## <span data-ttu-id="b61f9-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b61f9-110">EXAMPLES</span></span>

### <span data-ttu-id="b61f9-111">Exemplo 1: gravar uma mensagem de status</span><span class="sxs-lookup"><span data-stu-id="b61f9-111">Example 1: Write a status message</span></span>

```powershell
Write-Verbose -Message "Searching the Application Event Log."
Write-Verbose -Message "Searching the Application Event Log." -Verbose
```

<span data-ttu-id="b61f9-112">Esses comandos usam o `Write-Verbose` cmdlet para exibir uma mensagem de status.</span><span class="sxs-lookup"><span data-stu-id="b61f9-112">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="b61f9-113">Por padrão, a mensagem não é exibida.</span><span class="sxs-lookup"><span data-stu-id="b61f9-113">By default, the message is not displayed.</span></span>

<span data-ttu-id="b61f9-114">O segundo comando usa o parâmetro comum **Verbose** , que exibe todas as mensagens detalhadas, independentemente do valor da `$VerbosePreference` variável.</span><span class="sxs-lookup"><span data-stu-id="b61f9-114">The second command uses the **Verbose** common parameter, which displays any verbose messages, regardless of the value of the `$VerbosePreference` variable.</span></span>

### <span data-ttu-id="b61f9-115">Exemplo 2: definir $VerbosePreference e gravar uma mensagem de status</span><span class="sxs-lookup"><span data-stu-id="b61f9-115">Example 2: Set $VerbosePreference and write a status message</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose "Copying file $filename"
```

<span data-ttu-id="b61f9-116">Esses comandos usam o `Write-Verbose` cmdlet para exibir uma mensagem de status.</span><span class="sxs-lookup"><span data-stu-id="b61f9-116">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="b61f9-117">Por padrão, a mensagem não é exibida.</span><span class="sxs-lookup"><span data-stu-id="b61f9-117">By default, the message is not displayed.</span></span>

<span data-ttu-id="b61f9-118">O primeiro comando atribui um valor de continuar à `$VerbosePreference` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="b61f9-118">The first command assigns a value of Continue to the `$VerbosePreference` preference variable.</span></span> <span data-ttu-id="b61f9-119">O valor padrão, `SilentlyContinue` , suprime as mensagens detalhadas.</span><span class="sxs-lookup"><span data-stu-id="b61f9-119">The default value, `SilentlyContinue`, suppresses verbose messages.</span></span> <span data-ttu-id="b61f9-120">O segundo comando grava uma mensagem detalhada.</span><span class="sxs-lookup"><span data-stu-id="b61f9-120">The second command writes a verbose message.</span></span>

## <span data-ttu-id="b61f9-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b61f9-121">PARAMETERS</span></span>

### <span data-ttu-id="b61f9-122">-Mensagem</span><span class="sxs-lookup"><span data-stu-id="b61f9-122">-Message</span></span>

<span data-ttu-id="b61f9-123">Especifica a mensagem a ser exibida.</span><span class="sxs-lookup"><span data-stu-id="b61f9-123">Specifies the message to display.</span></span> <span data-ttu-id="b61f9-124">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="b61f9-124">This parameter is required.</span></span> <span data-ttu-id="b61f9-125">Você também pode canalizar uma cadeia de caracteres de mensagem para `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="b61f9-125">You can also pipe a message string to `Write-Verbose`.</span></span>

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

### <span data-ttu-id="b61f9-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b61f9-126">CommonParameters</span></span>

<span data-ttu-id="b61f9-127">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b61f9-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b61f9-128">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b61f9-128">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b61f9-129">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b61f9-129">INPUTS</span></span>

### <span data-ttu-id="b61f9-130">System.String</span><span class="sxs-lookup"><span data-stu-id="b61f9-130">System.String</span></span>

<span data-ttu-id="b61f9-131">É possível canalizar uma cadeia de caracteres que contém a mensagem para `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="b61f9-131">You can pipe a string that contains the message to `Write-Verbose`.</span></span>

## <span data-ttu-id="b61f9-132">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b61f9-132">OUTPUTS</span></span>

### <span data-ttu-id="b61f9-133">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b61f9-133">None</span></span>

<span data-ttu-id="b61f9-134">`Write-Verbose` grava somente no fluxo de mensagens detalhadas.</span><span class="sxs-lookup"><span data-stu-id="b61f9-134">`Write-Verbose` writes only to the verbose message stream.</span></span>

## <span data-ttu-id="b61f9-135">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b61f9-135">NOTES</span></span>

- <span data-ttu-id="b61f9-136">As mensagens detalhadas são retornadas somente quando o comando usa o parâmetro **Verbose** comum.</span><span class="sxs-lookup"><span data-stu-id="b61f9-136">Verbose messages are returned only when the command uses the **Verbose** common parameter.</span></span> <span data-ttu-id="b61f9-137">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b61f9-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>
- <span data-ttu-id="b61f9-138">Em trabalhos em segundo plano do Windows PowerShell e em comandos remotos, a `$VerbosePreference` variável na sessão de trabalho e na sessão remota determinam se a mensagem detalhada é exibida por padrão.</span><span class="sxs-lookup"><span data-stu-id="b61f9-138">In Windows PowerShell background jobs and remote commands, the `$VerbosePreference` variable in the job session and remote session determine whether the verbose message is displayed by default.</span></span>
  <span data-ttu-id="b61f9-139">Para obter mais informações sobre a `$VerbosePreference` variável, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b61f9-139">For more information about the `$VerbosePreference` variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="b61f9-140">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b61f9-140">RELATED LINKS</span></span>

[<span data-ttu-id="b61f9-141">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="b61f9-141">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="b61f9-142">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="b61f9-142">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="b61f9-143">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="b61f9-143">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="b61f9-144">Write-Error</span><span class="sxs-lookup"><span data-stu-id="b61f9-144">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="b61f9-145">Write-Host</span><span class="sxs-lookup"><span data-stu-id="b61f9-145">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="b61f9-146">Write-Information</span><span class="sxs-lookup"><span data-stu-id="b61f9-146">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="b61f9-147">Write-Output</span><span class="sxs-lookup"><span data-stu-id="b61f9-147">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="b61f9-148">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="b61f9-148">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="b61f9-149">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="b61f9-149">Write-Warning</span></span>](Write-Warning.md)
