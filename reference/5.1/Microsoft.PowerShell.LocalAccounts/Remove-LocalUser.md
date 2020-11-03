---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalUser
ms.openlocfilehash: de1054971dab19f8cfae654208488ca9ce5e17e4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194225"
---
# <span data-ttu-id="bb6e2-103">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="bb6e2-103">Remove-LocalUser</span></span>

## <span data-ttu-id="bb6e2-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="bb6e2-104">SYNOPSIS</span></span>
<span data-ttu-id="bb6e2-105">Exclui contas de usuário local.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-105">Deletes local user accounts.</span></span>

## <span data-ttu-id="bb6e2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bb6e2-106">SYNTAX</span></span>

### <span data-ttu-id="bb6e2-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="bb6e2-107">InputObject</span></span>

```
Remove-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bb6e2-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="bb6e2-108">Default</span></span>

```
Remove-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bb6e2-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="bb6e2-109">SecurityIdentifier</span></span>

```
Remove-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bb6e2-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bb6e2-110">DESCRIPTION</span></span>
<span data-ttu-id="bb6e2-111">O cmdlet **Remove-LocalUser** exclui contas de usuário local.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-111">The **Remove-LocalUser** cmdlet deletes local user accounts.</span></span>

## <span data-ttu-id="bb6e2-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="bb6e2-112">EXAMPLES</span></span>

### <span data-ttu-id="bb6e2-113">Exemplo 1: excluir uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="bb6e2-113">Example 1: Delete a user account</span></span>

```
PS C:\> Remove-LocalUser -Name "AdminContoso02"
```

<span data-ttu-id="bb6e2-114">Esse comando exclui a conta de usuário chamada AdminContoso02.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-114">This command deletes the user account named AdminContoso02.</span></span>

> [!NOTE]
> <span data-ttu-id="bb6e2-115">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-115">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="bb6e2-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bb6e2-116">PARAMETERS</span></span>

### <span data-ttu-id="bb6e2-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="bb6e2-117">-InputObject</span></span>
<span data-ttu-id="bb6e2-118">Especifica uma matriz de contas de usuário que este cmdlet exclui.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-118">Specifies an array of user accounts that this cmdlet deletes.</span></span>
<span data-ttu-id="bb6e2-119">Para obter uma conta de usuário, use o cmdlet Get-LocalUser.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-119">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bb6e2-120">-Name</span><span class="sxs-lookup"><span data-stu-id="bb6e2-120">-Name</span></span>
<span data-ttu-id="bb6e2-121">Especifica uma matriz de nomes das contas de usuário que este cmdlet exclui.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-121">Specifies an array of names of the user accounts that this cmdlet deletes.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bb6e2-122">-SID</span><span class="sxs-lookup"><span data-stu-id="bb6e2-122">-SID</span></span>
<span data-ttu-id="bb6e2-123">Especifica uma matriz de IDs de segurança (SIDs) de contas de usuário que este cmdlet exclui.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-123">Specifies an array of security IDs (SIDs) of user accounts that this cmdlet deletes.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bb6e2-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bb6e2-124">-Confirm</span></span>
<span data-ttu-id="bb6e2-125">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-125">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bb6e2-126">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bb6e2-126">-WhatIf</span></span>
<span data-ttu-id="bb6e2-127">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-127">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bb6e2-128">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-128">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bb6e2-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bb6e2-129">CommonParameters</span></span>
<span data-ttu-id="bb6e2-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bb6e2-131">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bb6e2-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bb6e2-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="bb6e2-132">INPUTS</span></span>

### <span data-ttu-id="bb6e2-133">System. Management. Automation. SecurityAccountsManager. LocalUser, System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="bb6e2-133">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="bb6e2-134">É possível canalizar um usuário local, uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-134">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="bb6e2-135">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="bb6e2-135">OUTPUTS</span></span>

### <span data-ttu-id="bb6e2-136">Nenhum</span><span class="sxs-lookup"><span data-stu-id="bb6e2-136">None</span></span>
<span data-ttu-id="bb6e2-137">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-137">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bb6e2-138">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="bb6e2-138">NOTES</span></span>

* <span data-ttu-id="bb6e2-139">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-139">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="bb6e2-140">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="bb6e2-140">The possible sources are as follows:</span></span>

- <span data-ttu-id="bb6e2-141">Local</span><span class="sxs-lookup"><span data-stu-id="bb6e2-141">Local</span></span>
- <span data-ttu-id="bb6e2-142">Active Directory</span><span class="sxs-lookup"><span data-stu-id="bb6e2-142">Active Directory</span></span>
- <span data-ttu-id="bb6e2-143">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="bb6e2-143">Azure Active Directory group</span></span>
- <span data-ttu-id="bb6e2-144">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="bb6e2-144">Microsoft Account</span></span>

<span data-ttu-id="bb6e2-145">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-145">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="bb6e2-146">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="bb6e2-146">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="bb6e2-147">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="bb6e2-147">RELATED LINKS</span></span>

[<span data-ttu-id="bb6e2-148">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="bb6e2-148">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="bb6e2-149">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="bb6e2-149">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="bb6e2-150">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="bb6e2-150">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="bb6e2-151">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="bb6e2-151">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="bb6e2-152">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="bb6e2-152">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="bb6e2-153">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="bb6e2-153">Set-LocalUser</span></span>](Set-LocalUser.md)
