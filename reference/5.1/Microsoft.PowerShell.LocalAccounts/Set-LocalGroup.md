---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LocalGroup
ms.openlocfilehash: 471c3c7bc01bf26dfe9d8eec26e4414464cae02e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194223"
---
# <span data-ttu-id="e09ac-103">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="e09ac-103">Set-LocalGroup</span></span>

## <span data-ttu-id="e09ac-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e09ac-104">SYNOPSIS</span></span>
<span data-ttu-id="e09ac-105">Altera um grupo de segurança local.</span><span class="sxs-lookup"><span data-stu-id="e09ac-105">Changes a local security group.</span></span>

## <span data-ttu-id="e09ac-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e09ac-106">SYNTAX</span></span>

### <span data-ttu-id="e09ac-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="e09ac-107">InputObject</span></span>

```
Set-LocalGroup -Description <String> [-InputObject] <LocalGroup> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e09ac-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="e09ac-108">Default</span></span>

```
Set-LocalGroup -Description <String> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e09ac-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="e09ac-109">SecurityIdentifier</span></span>

```
Set-LocalGroup -Description <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e09ac-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e09ac-110">DESCRIPTION</span></span>
<span data-ttu-id="e09ac-111">O cmdlet **set-local** Group altera um grupo de segurança local.</span><span class="sxs-lookup"><span data-stu-id="e09ac-111">The **Set-LocalGroup** cmdlet changes a local security group.</span></span>

## <span data-ttu-id="e09ac-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e09ac-112">EXAMPLES</span></span>

### <span data-ttu-id="e09ac-113">Exemplo 1: alterar uma descrição de grupo</span><span class="sxs-lookup"><span data-stu-id="e09ac-113">Example 1: Change a group description</span></span>

```
PS C:\> Set-LocalGroup -Name "SecurityGroup04" -Description "This is a sample description."
```

<span data-ttu-id="e09ac-114">Esse comando altera a descrição de um grupo local.</span><span class="sxs-lookup"><span data-stu-id="e09ac-114">This command changes the description of a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="e09ac-115">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e09ac-115">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="e09ac-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e09ac-116">PARAMETERS</span></span>

### <span data-ttu-id="e09ac-117">-Description</span><span class="sxs-lookup"><span data-stu-id="e09ac-117">-Description</span></span>
<span data-ttu-id="e09ac-118">Especifica um comentário para o grupo.</span><span class="sxs-lookup"><span data-stu-id="e09ac-118">Specifies a comment for the group.</span></span>
<span data-ttu-id="e09ac-119">O comprimento máximo é de 48 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e09ac-119">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e09ac-120">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e09ac-120">-InputObject</span></span>
<span data-ttu-id="e09ac-121">Especifica o grupo de segurança que esse cmdlet altera.</span><span class="sxs-lookup"><span data-stu-id="e09ac-121">Specifies the security group that this cmdlet changes.</span></span>
<span data-ttu-id="e09ac-122">Para obter um grupo de segurança, use o cmdlet Get-LocalGroup.</span><span class="sxs-lookup"><span data-stu-id="e09ac-122">To obtain a security group, use the Get-LocalGroup cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e09ac-123">-Name</span><span class="sxs-lookup"><span data-stu-id="e09ac-123">-Name</span></span>
<span data-ttu-id="e09ac-124">Especifica o nome do grupo de segurança que este cmdlet altera.</span><span class="sxs-lookup"><span data-stu-id="e09ac-124">Specifies the name of the security group that this cmdlet changes.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e09ac-125">-SID</span><span class="sxs-lookup"><span data-stu-id="e09ac-125">-SID</span></span>
<span data-ttu-id="e09ac-126">Especifica a ID de segurança (SID) do grupo de segurança que esse cmdlet altera.</span><span class="sxs-lookup"><span data-stu-id="e09ac-126">Specifies the security ID (SID) of the security group that this cmdlet changes.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e09ac-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e09ac-127">-Confirm</span></span>
<span data-ttu-id="e09ac-128">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e09ac-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e09ac-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e09ac-129">-WhatIf</span></span>
<span data-ttu-id="e09ac-130">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="e09ac-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e09ac-131">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e09ac-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e09ac-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e09ac-132">CommonParameters</span></span>
<span data-ttu-id="e09ac-133">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e09ac-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e09ac-134">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e09ac-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e09ac-135">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e09ac-135">INPUTS</span></span>

### <span data-ttu-id="e09ac-136">System. Management. Automation. SecurityAccountsManager. local, System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="e09ac-136">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="e09ac-137">É possível canalizar um grupo de segurança, uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e09ac-137">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="e09ac-138">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e09ac-138">OUTPUTS</span></span>

### <span data-ttu-id="e09ac-139">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e09ac-139">None</span></span>
<span data-ttu-id="e09ac-140">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="e09ac-140">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e09ac-141">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e09ac-141">NOTES</span></span>

* <span data-ttu-id="e09ac-142">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="e09ac-142">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="e09ac-143">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="e09ac-143">The possible sources are as follows:</span></span>

- <span data-ttu-id="e09ac-144">Local</span><span class="sxs-lookup"><span data-stu-id="e09ac-144">Local</span></span>
- <span data-ttu-id="e09ac-145">Active Directory</span><span class="sxs-lookup"><span data-stu-id="e09ac-145">Active Directory</span></span>
- <span data-ttu-id="e09ac-146">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="e09ac-146">Azure Active Directory group</span></span>
- <span data-ttu-id="e09ac-147">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e09ac-147">Microsoft Account</span></span>

<span data-ttu-id="e09ac-148">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="e09ac-148">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="e09ac-149">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="e09ac-149">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="e09ac-150">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e09ac-150">RELATED LINKS</span></span>

[<span data-ttu-id="e09ac-151">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="e09ac-151">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="e09ac-152">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="e09ac-152">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="e09ac-153">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="e09ac-153">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="e09ac-154">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="e09ac-154">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)
