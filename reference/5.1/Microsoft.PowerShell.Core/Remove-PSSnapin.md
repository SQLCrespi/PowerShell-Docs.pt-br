---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSnapin
ms.openlocfilehash: e74aff3e52c61f41a54664efbab9c0f195b0d409
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193511"
---
# <span data-ttu-id="352d5-103">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="352d5-103">Remove-PSSnapin</span></span>

## <span data-ttu-id="352d5-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="352d5-104">SYNOPSIS</span></span>
<span data-ttu-id="352d5-105">Remove os snap-ins do Windows PowerShell da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="352d5-105">Removes Windows PowerShell snap-ins from the current session.</span></span>

## <span data-ttu-id="352d5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="352d5-106">SYNTAX</span></span>

```
Remove-PSSnapin [-Name] <String[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="352d5-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="352d5-107">DESCRIPTION</span></span>
<span data-ttu-id="352d5-108">O cmdlet **Remove-PsSnapin** remove um snap-in do Windows PowerShell da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="352d5-108">The **Remove-PSSnapin** cmdlet removes a Windows PowerShell snap-in from the current session.</span></span>
<span data-ttu-id="352d5-109">Você pode usá-lo para remover snap-ins que você adicionou ao Windows PowerShell. você não pode usar este cmdlet para remover os snap-ins instalados com o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="352d5-109">You can use it to remove snap-ins that you have added to Windows PowerShell You cannot use this cmdlet to remove the snap-ins that are installed with Windows PowerShell.</span></span>

<span data-ttu-id="352d5-110">Depois de remover um snap-in da sessão atual, o snap-in ainda é carregado, mas os cmdlets e provedores no snap-in não estão mais disponíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="352d5-110">After you remove a snap-in from the current session, the snap-in is still loaded, but the cmdlets and providers in the snap-in are no longer available in the session.</span></span>

## <span data-ttu-id="352d5-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="352d5-111">EXAMPLES</span></span>

### <span data-ttu-id="352d5-112">Exemplo 1: remover um snap-in</span><span class="sxs-lookup"><span data-stu-id="352d5-112">Example 1: Remove a snap-in</span></span>

```
PS C:\> remove-pssnapin -Name Microsoft.Exchange
```

<span data-ttu-id="352d5-113">Esse comando Remove o snap-in **Microsoft. Exchange** da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="352d5-113">This command removes the **Microsoft.Exchange** snap-in from the current session.</span></span>
<span data-ttu-id="352d5-114">Quando o comando for concluído, os cmdlets e provedores suportados pelo snap-in não estarão disponíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="352d5-114">When the command is complete, the cmdlets and providers that the snap-in supported are not available in the session.</span></span>

### <span data-ttu-id="352d5-115">Exemplo 2: remover snap-ins usando nomes com o pipeline</span><span class="sxs-lookup"><span data-stu-id="352d5-115">Example 2: Remove snap-ins by using names with the pipeline</span></span>

```
PS C:\> Get-PSSnapIn smp* | Remove-PSSnapIn
```

<span data-ttu-id="352d5-116">Esse comando remove os snap-ins do Windows PowerShell que têm nomes que iniciam com o SMP da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="352d5-116">This command removes the Windows PowerShell snap-ins that have names that start with smp from the current session.</span></span>

<span data-ttu-id="352d5-117">O comando usa o cmdlet **Get-PSSnapin** para obter objetos que representam os snap-ins. O operador de pipeline (|) envia os resultados para o cmdlet **Remove-PsSnapin** , que os remove da sessão.</span><span class="sxs-lookup"><span data-stu-id="352d5-117">The command uses the **Get-PSSnapin** cmdlet to get objects that represent the snap-ins. The pipeline operator (|) sends the results to the **Remove-PSSnapin** cmdlet, which removes them from the session.</span></span>
<span data-ttu-id="352d5-118">Os provedores e cmdlets que esse snap-in suporta não estão mais disponíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="352d5-118">The providers and cmdlets that this snap-in supports are no longer available in the session.</span></span>

<span data-ttu-id="352d5-119">Quando você canaliza objetos para **Remove-PsSnapin** , os nomes dos objetos são associados ao parâmetro *Name* , que aceita objetos do pipeline que têm uma propriedade **Name** .</span><span class="sxs-lookup"><span data-stu-id="352d5-119">When you pipe objects to **Remove-PSSnapin** , the names of the objects are associated with the *Name* parameter, which accepts objects from the pipeline that have a **Name** property.</span></span>

### <span data-ttu-id="352d5-120">Exemplo 3: remover snap-ins usando nomes</span><span class="sxs-lookup"><span data-stu-id="352d5-120">Example 3: Remove snap-ins by using names</span></span>

```
PS C:\> Remove-PSSnapin -Name *event*
```

<span data-ttu-id="352d5-121">Esse comando Remove todos os snap-ins do Windows PowerShell que têm nomes que incluem o evento.</span><span class="sxs-lookup"><span data-stu-id="352d5-121">This command removes all Windows PowerShell snap-ins that have names that include event.</span></span>

## <span data-ttu-id="352d5-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="352d5-122">PARAMETERS</span></span>

### <span data-ttu-id="352d5-123">-Name</span><span class="sxs-lookup"><span data-stu-id="352d5-123">-Name</span></span>
<span data-ttu-id="352d5-124">Especifica os nomes dos snap-ins do Windows PowerShell a remover da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="352d5-124">Specifies the names of Windows PowerShell snap-ins to remove from the current session.</span></span>
<span data-ttu-id="352d5-125">Caracteres curinga (\*) são permitidos.</span><span class="sxs-lookup"><span data-stu-id="352d5-125">Wildcard characters (\*) are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="352d5-126">-PassThru</span><span class="sxs-lookup"><span data-stu-id="352d5-126">-PassThru</span></span>
<span data-ttu-id="352d5-127">Retorna um objeto que representa o snap-in.</span><span class="sxs-lookup"><span data-stu-id="352d5-127">Returns an object that represents the snap-in.</span></span>
<span data-ttu-id="352d5-128">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="352d5-128">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="352d5-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="352d5-129">-Confirm</span></span>
<span data-ttu-id="352d5-130">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="352d5-130">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="352d5-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="352d5-131">-WhatIf</span></span>
<span data-ttu-id="352d5-132">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="352d5-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="352d5-133">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="352d5-133">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="352d5-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="352d5-134">CommonParameters</span></span>
<span data-ttu-id="352d5-135">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="352d5-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="352d5-136">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="352d5-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="352d5-137">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="352d5-137">INPUTS</span></span>

### <span data-ttu-id="352d5-138">System. Management. Automation. PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="352d5-138">System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="352d5-139">É possível canalizar um objeto de snap-in para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="352d5-139">You can pipe a snap-in object to this cmdlet.</span></span>

## <span data-ttu-id="352d5-140">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="352d5-140">OUTPUTS</span></span>

### <span data-ttu-id="352d5-141">Nenhum, System. Management. Automation. PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="352d5-141">None, System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="352d5-142">Esse cmdlet gera um objeto **System. Management. Automation. PSSnapInInfo** que representa o snap-in, se você especificar o parâmetro *PassThru* .</span><span class="sxs-lookup"><span data-stu-id="352d5-142">This cmdlet generates a **System.Management.Automation.PSSnapInInfo** object that represents the snap-in, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="352d5-143">Por padrão, **Remove-PsSnapin** não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="352d5-143">By default, **Remove-PSSnapin** does not generate any output.</span></span>

## <span data-ttu-id="352d5-144">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="352d5-144">NOTES</span></span>

* <span data-ttu-id="352d5-145">**Remove-PsSnapin** não verifica a versão do Windows PowerShell antes de remover um snap-in da sessão.</span><span class="sxs-lookup"><span data-stu-id="352d5-145">**Remove-PSSnapin** does not check the version of Windows PowerShell before removing a snap-in from the session.</span></span> <span data-ttu-id="352d5-146">Se um snap-in não pode ser removido, um aviso é exibido e o comando falha.</span><span class="sxs-lookup"><span data-stu-id="352d5-146">If a snap-in cannot be removed, a warning appears and the command fails.</span></span>
* <span data-ttu-id="352d5-147">**Remove-PsSnapin** afeta apenas a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="352d5-147">**Remove-PSSnapin** affects only the current session.</span></span> <span data-ttu-id="352d5-148">Se tiver adicionado um comando Add-PSSnapin para seu perfil do Windows PowerShell, você deve excluir o comando para remover o snap-in de futuras sessões.</span><span class="sxs-lookup"><span data-stu-id="352d5-148">If you have added an Add-PSSnapin command to your Windows PowerShell profile, you should delete the command to remove the snap-in from future sessions.</span></span> <span data-ttu-id="352d5-149">Para obter instruções, digite `Get-Help about_Profiles` .</span><span class="sxs-lookup"><span data-stu-id="352d5-149">For instructions, type `Get-Help about_Profiles`.</span></span>

## <span data-ttu-id="352d5-150">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="352d5-150">RELATED LINKS</span></span>

[<span data-ttu-id="352d5-151">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="352d5-151">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="352d5-152">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="352d5-152">Get-PSSnapin</span></span>](Get-PSSnapin.md)
