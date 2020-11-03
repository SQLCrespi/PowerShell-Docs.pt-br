---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/rename-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-LocalGroup
ms.openlocfilehash: 566d33bdeb52323cca41fa9757d36334b40f1654
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194222"
---
# <span data-ttu-id="38787-103">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="38787-103">Rename-LocalGroup</span></span>

## <span data-ttu-id="38787-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="38787-104">SYNOPSIS</span></span>
<span data-ttu-id="38787-105">Renomeia um grupo de segurança local.</span><span class="sxs-lookup"><span data-stu-id="38787-105">Renames a local security group.</span></span>

## <span data-ttu-id="38787-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="38787-106">SYNTAX</span></span>

### <span data-ttu-id="38787-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="38787-107">InputObject</span></span>

```
Rename-LocalGroup [-InputObject] <LocalGroup> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="38787-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="38787-108">Default</span></span>

```
Rename-LocalGroup [-Name] <String> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="38787-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="38787-109">SecurityIdentifier</span></span>

```
Rename-LocalGroup [-NewName] <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="38787-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="38787-110">DESCRIPTION</span></span>
<span data-ttu-id="38787-111">O cmdlet **Rename-local** renomeia um grupo de segurança local.</span><span class="sxs-lookup"><span data-stu-id="38787-111">The **Rename-LocalGroup** cmdlet renames a local security group.</span></span>

> [!NOTE]
> <span data-ttu-id="38787-112">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="38787-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="38787-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="38787-113">EXAMPLES</span></span>

### <span data-ttu-id="38787-114">Exemplo 1: alterar o nome de um grupo</span><span class="sxs-lookup"><span data-stu-id="38787-114">Example 1: Change the name of a group</span></span>

```
PS C:\> Rename-LocalGroup -Name "SecurityGroup" -NewName "SecurityGroup04"
```

<span data-ttu-id="38787-115">Esse comando renomeia um grupo de segurança chamado Group Security.</span><span class="sxs-lookup"><span data-stu-id="38787-115">This command renames a security group named SecurityGroup.</span></span>

## <span data-ttu-id="38787-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="38787-116">PARAMETERS</span></span>

### <span data-ttu-id="38787-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="38787-117">-InputObject</span></span>
<span data-ttu-id="38787-118">Especifica o grupo de segurança que esse cmdlet renomeia.</span><span class="sxs-lookup"><span data-stu-id="38787-118">Specifies the security group that this cmdlet renames.</span></span>
<span data-ttu-id="38787-119">Para obter um grupo de segurança, use o cmdlet Get-LocalGroup.</span><span class="sxs-lookup"><span data-stu-id="38787-119">To obtain a security group, use the Get-LocalGroup cmdlet.</span></span>

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

### <span data-ttu-id="38787-120">-Name</span><span class="sxs-lookup"><span data-stu-id="38787-120">-Name</span></span>
<span data-ttu-id="38787-121">Especifica o nome do grupo de segurança que esse cmdlet renomeia.</span><span class="sxs-lookup"><span data-stu-id="38787-121">Specifies the name of the security group that this cmdlet renames.</span></span>

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

### <span data-ttu-id="38787-122">-NewName</span><span class="sxs-lookup"><span data-stu-id="38787-122">-NewName</span></span>
<span data-ttu-id="38787-123">Especifica um novo nome para o grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="38787-123">Specifies a new name for the security group.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="38787-124">-SID</span><span class="sxs-lookup"><span data-stu-id="38787-124">-SID</span></span>
<span data-ttu-id="38787-125">Especifica a ID de segurança (SID) de um grupo de segurança que esse cmdlet renomeia.</span><span class="sxs-lookup"><span data-stu-id="38787-125">Specifies the security ID (SID) of a security group that this cmdlet renames.</span></span>

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

### <span data-ttu-id="38787-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="38787-126">-Confirm</span></span>
<span data-ttu-id="38787-127">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38787-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="38787-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="38787-128">-WhatIf</span></span>
<span data-ttu-id="38787-129">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="38787-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="38787-130">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="38787-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="38787-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="38787-131">CommonParameters</span></span>
<span data-ttu-id="38787-132">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="38787-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="38787-133">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="38787-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="38787-134">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="38787-134">INPUTS</span></span>

### <span data-ttu-id="38787-135">System. Management. Automation. SecurityAccountsManager. local, System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="38787-135">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="38787-136">É possível canalizar um grupo de segurança, uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38787-136">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="38787-137">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="38787-137">OUTPUTS</span></span>

### <span data-ttu-id="38787-138">Nenhum</span><span class="sxs-lookup"><span data-stu-id="38787-138">None</span></span>
<span data-ttu-id="38787-139">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="38787-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="38787-140">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="38787-140">NOTES</span></span>

* <span data-ttu-id="38787-141">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="38787-141">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="38787-142">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="38787-142">The possible sources are as follows:</span></span>

- <span data-ttu-id="38787-143">Local</span><span class="sxs-lookup"><span data-stu-id="38787-143">Local</span></span>
- <span data-ttu-id="38787-144">Active Directory</span><span class="sxs-lookup"><span data-stu-id="38787-144">Active Directory</span></span>
- <span data-ttu-id="38787-145">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="38787-145">Azure Active Directory group</span></span>
- <span data-ttu-id="38787-146">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="38787-146">Microsoft Account</span></span>

<span data-ttu-id="38787-147">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="38787-147">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="38787-148">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="38787-148">For earlier  versions, the property is blank.</span></span>

## <span data-ttu-id="38787-149">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="38787-149">RELATED LINKS</span></span>

[<span data-ttu-id="38787-150">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="38787-150">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="38787-151">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="38787-151">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="38787-152">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="38787-152">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="38787-153">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="38787-153">Set-LocalGroup</span></span>](Set-LocalGroup.md)
