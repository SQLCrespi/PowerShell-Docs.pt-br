---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/add-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-LocalGroupMember
ms.openlocfilehash: 06993c8f6618472f4809e37fbf83d298d13ae515
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193298"
---
# <span data-ttu-id="b5c95-103">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="b5c95-103">Add-LocalGroupMember</span></span>

## <span data-ttu-id="b5c95-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b5c95-104">SYNOPSIS</span></span>
<span data-ttu-id="b5c95-105">Adiciona membros a um grupo local.</span><span class="sxs-lookup"><span data-stu-id="b5c95-105">Adds members to a local group.</span></span>

## <span data-ttu-id="b5c95-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b5c95-106">SYNTAX</span></span>

### <span data-ttu-id="b5c95-107">Grupo</span><span class="sxs-lookup"><span data-stu-id="b5c95-107">Group</span></span>

```
Add-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="b5c95-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="b5c95-108">Default</span></span>

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b5c95-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="b5c95-109">SecurityIdentifier</span></span>

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="b5c95-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b5c95-110">DESCRIPTION</span></span>

<span data-ttu-id="b5c95-111">O `Add-LocalGroupMember` cmdlet adiciona usuários ou grupos a um grupo de segurança local.</span><span class="sxs-lookup"><span data-stu-id="b5c95-111">The `Add-LocalGroupMember` cmdlet adds users or groups to a local security group.</span></span> <span data-ttu-id="b5c95-112">Todos os direitos e permissões atribuídos ao grupo são atribuídos a todos os membros desse grupo.</span><span class="sxs-lookup"><span data-stu-id="b5c95-112">All the rights and permissions that are assigned to a group are assigned to all members of that group.</span></span>

<span data-ttu-id="b5c95-113">Os membros do grupo Administradores em um computador local têm permissões de Controle Total nesse computador.</span><span class="sxs-lookup"><span data-stu-id="b5c95-113">Members of the Administrators group on a local computer have Full Control permissions on that computer.</span></span> <span data-ttu-id="b5c95-114">Limite o número de usuários em um grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="b5c95-114">Limit the number of users in the Administrators group.</span></span>

<span data-ttu-id="b5c95-115">Se o computador fizer parte de um domínio, é possível adicionar contas de usuário, de computador e de grupo desse domínio e de domínios confiáveis a um grupo local.</span><span class="sxs-lookup"><span data-stu-id="b5c95-115">If the computer is joined to a domain, you can add user accounts, computer accounts, and group accounts from that domain and from trusted domains to a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="b5c95-116">Se o computador tiver ingressado em um domínio e você tentar adicionar um usuário local que tenha o mesmo nome que um membro do domínio, ele adicionará o membro do domínio.</span><span class="sxs-lookup"><span data-stu-id="b5c95-116">If the computer is joined to a domain and you try to add a local user that has the same name as a member of the domain it adds the domain member.</span></span>

## <span data-ttu-id="b5c95-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b5c95-117">EXAMPLES</span></span>

### <span data-ttu-id="b5c95-118">Exemplo 1: adicionar membros ao grupo de administradores</span><span class="sxs-lookup"><span data-stu-id="b5c95-118">Example 1: Add members to the Administrators group</span></span>

<span data-ttu-id="b5c95-119">Esse comando adiciona vários membros ao grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="b5c95-119">This command adds several members to the local Administrators group.</span></span> <span data-ttu-id="b5c95-120">Os novos membros incluem uma conta de usuário local, uma conta Microsoft, uma conta de Azure Active Directory e um grupo de domínio.</span><span class="sxs-lookup"><span data-stu-id="b5c95-120">The new members include a local user account, a Microsoft account, an Azure Active Directory account, and a domain group.</span></span> <span data-ttu-id="b5c95-121">Este exemplo usa um valor de espaço reservado para o nome de usuário de uma conta em Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b5c95-121">This example uses a placeholder value for the user name of an account at Outlook.com.</span></span>

```powershell
Add-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

## <span data-ttu-id="b5c95-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b5c95-122">PARAMETERS</span></span>

### <span data-ttu-id="b5c95-123">-Grupo</span><span class="sxs-lookup"><span data-stu-id="b5c95-123">-Group</span></span>

<span data-ttu-id="b5c95-124">Especifica o grupo de segurança ao qual este cmdlet adiciona membros.</span><span class="sxs-lookup"><span data-stu-id="b5c95-124">Specifies the security group to which this cmdlet adds members.</span></span>

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

### <span data-ttu-id="b5c95-125">-Membro</span><span class="sxs-lookup"><span data-stu-id="b5c95-125">-Member</span></span>

<span data-ttu-id="b5c95-126">Especifica uma matriz de usuários ou grupos que este cmdlet adiciona a um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="b5c95-126">Specifies an array of users or groups that this cmdlet adds to a security group.</span></span> <span data-ttu-id="b5c95-127">Você pode especificar usuários ou grupos por nome, ID de segurança (SID) ou objetos **LocalPrincipal** .</span><span class="sxs-lookup"><span data-stu-id="b5c95-127">You can specify users or groups by name, security ID (SID), or **LocalPrincipal** objects.</span></span>

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

### <span data-ttu-id="b5c95-128">-Name</span><span class="sxs-lookup"><span data-stu-id="b5c95-128">-Name</span></span>

<span data-ttu-id="b5c95-129">Especifica o nome do grupo de segurança ao qual este cmdlet adiciona membros.</span><span class="sxs-lookup"><span data-stu-id="b5c95-129">Specifies the name of the security group to which this cmdlet adds members.</span></span>

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

### <span data-ttu-id="b5c95-130">-SID</span><span class="sxs-lookup"><span data-stu-id="b5c95-130">-SID</span></span>

<span data-ttu-id="b5c95-131">Especifica a ID de segurança do grupo de segurança ao qual este cmdlet adiciona membros.</span><span class="sxs-lookup"><span data-stu-id="b5c95-131">Specifies the security ID of the security group to which this cmdlet adds members.</span></span>

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

### <span data-ttu-id="b5c95-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b5c95-132">-Confirm</span></span>

<span data-ttu-id="b5c95-133">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b5c95-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b5c95-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b5c95-134">-WhatIf</span></span>

<span data-ttu-id="b5c95-135">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="b5c95-135">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b5c95-136">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="b5c95-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b5c95-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b5c95-137">CommonParameters</span></span>

<span data-ttu-id="b5c95-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b5c95-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b5c95-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b5c95-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b5c95-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b5c95-140">INPUTS</span></span>

### <span data-ttu-id="b5c95-141">System. Management. Automation. SecurityAccountsManager. local, System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="b5c95-141">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>

<span data-ttu-id="b5c95-142">É possível canalizar uma entidade de segurança local, uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b5c95-142">You can pipe a local principal, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="b5c95-143">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b5c95-143">OUTPUTS</span></span>

### <span data-ttu-id="b5c95-144">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b5c95-144">None</span></span>

<span data-ttu-id="b5c95-145">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="b5c95-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b5c95-146">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b5c95-146">NOTES</span></span>

<span data-ttu-id="b5c95-147">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b5c95-147">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

<span data-ttu-id="b5c95-148">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="b5c95-148">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="b5c95-149">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="b5c95-149">The possible sources are as follows:</span></span>

- <span data-ttu-id="b5c95-150">Local</span><span class="sxs-lookup"><span data-stu-id="b5c95-150">Local</span></span>
- <span data-ttu-id="b5c95-151">Active Directory</span><span class="sxs-lookup"><span data-stu-id="b5c95-151">Active Directory</span></span>
- <span data-ttu-id="b5c95-152">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="b5c95-152">Azure Active Directory group</span></span>
- <span data-ttu-id="b5c95-153">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5c95-153">Microsoft Account</span></span>

<span data-ttu-id="b5c95-154">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="b5c95-154">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="b5c95-155">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="b5c95-155">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="b5c95-156">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b5c95-156">RELATED LINKS</span></span>

[<span data-ttu-id="b5c95-157">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="b5c95-157">Get-LocalGroupMember</span></span>](Get-LocalGroupMember.md)

[<span data-ttu-id="b5c95-158">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="b5c95-158">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="b5c95-159">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="b5c95-159">Remove-LocalGroupMember</span></span>](Remove-LocalGroupMember.md)
