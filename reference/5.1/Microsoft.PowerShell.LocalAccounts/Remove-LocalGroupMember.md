---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroupMember
ms.openlocfilehash: 6e6264a65c343657c2f2f87384d76cc3f1554d3d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193986"
---
# <span data-ttu-id="bd0a6-103">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="bd0a6-103">Remove-LocalGroupMember</span></span>

## <span data-ttu-id="bd0a6-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="bd0a6-104">SYNOPSIS</span></span>
<span data-ttu-id="bd0a6-105">Remove membros de um grupo local.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-105">Removes members from a local group.</span></span>

## <span data-ttu-id="bd0a6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd0a6-106">SYNTAX</span></span>

### <span data-ttu-id="bd0a6-107">Grupo</span><span class="sxs-lookup"><span data-stu-id="bd0a6-107">Group</span></span>

```
Remove-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="bd0a6-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="bd0a6-108">Default</span></span>

```
Remove-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bd0a6-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="bd0a6-109">SecurityIdentifier</span></span>

```
Remove-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="bd0a6-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd0a6-110">DESCRIPTION</span></span>
<span data-ttu-id="bd0a6-111">O cmdlet **Remove-LocalGroupMember** remove usuários ou grupos de um grupo local.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-111">The **Remove-LocalGroupMember** cmdlet removes users or groups from a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="bd0a6-112">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="bd0a6-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="bd0a6-113">EXAMPLES</span></span>

### <span data-ttu-id="bd0a6-114">Exemplo 1: remover membros do grupo de administradores</span><span class="sxs-lookup"><span data-stu-id="bd0a6-114">Example 1: Remove members from the Administrators group</span></span>

```
PS C:\> Remove-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

<span data-ttu-id="bd0a6-115">Esse comando Remove vários membros do grupo Administradores local.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-115">This command removes several members from the local Administrators group.</span></span>
<span data-ttu-id="bd0a6-116">Os membros que esse cmdlet Remove incluem uma conta de usuário local, uma conta Microsoft, uma conta de Azure Active Directory e um grupo de domínio.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-116">The members that this cmdlet removes include a local user account, a Microsoft account, an Azure Active Directory account, and a domain group.</span></span>
<span data-ttu-id="bd0a6-117">Este exemplo usa um valor de espaço reservado para o nome de usuário de uma conta em Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-117">This example uses a placeholder value for the user name of an account at Outlook.com.</span></span>

## <span data-ttu-id="bd0a6-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd0a6-118">PARAMETERS</span></span>

### <span data-ttu-id="bd0a6-119">-Grupo</span><span class="sxs-lookup"><span data-stu-id="bd0a6-119">-Group</span></span>
<span data-ttu-id="bd0a6-120">Especifica o grupo de segurança do qual este cmdlet Remove Membros.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-120">Specifies the security group from which this cmdlet removes members.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd0a6-121">-Membro</span><span class="sxs-lookup"><span data-stu-id="bd0a6-121">-Member</span></span>
<span data-ttu-id="bd0a6-122">Especifica uma matriz de usuários ou grupos que este cmdlet Remove de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-122">Specifies an array of users or groups that this cmdlet removes from a security group.</span></span>
<span data-ttu-id="bd0a6-123">Você pode especificar usuários ou grupos por nome, ID de segurança (SID) ou objetos **LocalPrincipal** .</span><span class="sxs-lookup"><span data-stu-id="bd0a6-123">You can specify users or groups by name, security ID (SID), or **LocalPrincipal** objects.</span></span>
<span data-ttu-id="bd0a6-124">Especifique as cadeias de caracteres de SID em S-R-I-S-S.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-124">Specify SID strings in S-R-I-S-S .</span></span>
<span data-ttu-id="bd0a6-125">.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-125">.</span></span> <span data-ttu-id="bd0a6-126">.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-126">.</span></span>
<span data-ttu-id="bd0a6-127">.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-127">format.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalPrincipal[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bd0a6-128">-Name</span><span class="sxs-lookup"><span data-stu-id="bd0a6-128">-Name</span></span>
<span data-ttu-id="bd0a6-129">Especifica o nome do grupo de segurança do qual este cmdlet Remove Membros.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-129">Specifies the name of the security group from which this cmdlet removes members.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd0a6-130">-SID</span><span class="sxs-lookup"><span data-stu-id="bd0a6-130">-SID</span></span>
<span data-ttu-id="bd0a6-131">Especifica a ID de segurança do grupo de segurança do qual este cmdlet Remove Membros.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-131">Specifies the security ID of the security group from which this cmdlet removes members.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd0a6-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bd0a6-132">-Confirm</span></span>
<span data-ttu-id="bd0a6-133">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bd0a6-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bd0a6-134">-WhatIf</span></span>
<span data-ttu-id="bd0a6-135">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-135">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bd0a6-136">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bd0a6-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bd0a6-137">CommonParameters</span></span>
<span data-ttu-id="bd0a6-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd0a6-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bd0a6-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bd0a6-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="bd0a6-140">INPUTS</span></span>

### <span data-ttu-id="bd0a6-141">System. Management. Automation. SecurityAccountsManager. LocalPrincipal, System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="bd0a6-141">System.Management.Automation.SecurityAccountsManager.LocalPrincipal, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="bd0a6-142">É possível canalizar uma entidade de segurança local, uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-142">You can pipe a local principal, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="bd0a6-143">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="bd0a6-143">OUTPUTS</span></span>

### <span data-ttu-id="bd0a6-144">Nenhum</span><span class="sxs-lookup"><span data-stu-id="bd0a6-144">None</span></span>
<span data-ttu-id="bd0a6-145">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bd0a6-146">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="bd0a6-146">NOTES</span></span>

* <span data-ttu-id="bd0a6-147">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-147">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="bd0a6-148">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="bd0a6-148">The possible sources are as follows:</span></span>

- <span data-ttu-id="bd0a6-149">Local</span><span class="sxs-lookup"><span data-stu-id="bd0a6-149">Local</span></span>
- <span data-ttu-id="bd0a6-150">Active Directory</span><span class="sxs-lookup"><span data-stu-id="bd0a6-150">Active Directory</span></span>
- <span data-ttu-id="bd0a6-151">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="bd0a6-151">Azure Active Directory group</span></span>
- <span data-ttu-id="bd0a6-152">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="bd0a6-152">Microsoft Account</span></span>

<span data-ttu-id="bd0a6-153">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-153">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="bd0a6-154">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="bd0a6-154">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="bd0a6-155">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="bd0a6-155">RELATED LINKS</span></span>

[<span data-ttu-id="bd0a6-156">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="bd0a6-156">Add-LocalGroupMember</span></span>](Add-LocalGroupMember.md)

[<span data-ttu-id="bd0a6-157">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="bd0a6-157">Get-LocalGroupMember</span></span>](Get-LocalGroupMember.md)

[<span data-ttu-id="bd0a6-158">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="bd0a6-158">New-LocalGroup</span></span>](New-LocalGroup.md)
