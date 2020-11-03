---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroup
ms.openlocfilehash: 6a2f921972fef1794581b301df6e7439e56c7f47
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193985"
---
# <span data-ttu-id="b9cbe-103">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="b9cbe-103">Remove-LocalGroup</span></span>

## <span data-ttu-id="b9cbe-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b9cbe-104">SYNOPSIS</span></span>
<span data-ttu-id="b9cbe-105">Exclui grupos de segurança locais.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-105">Deletes local security groups.</span></span>

## <span data-ttu-id="b9cbe-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b9cbe-106">SYNTAX</span></span>

### <span data-ttu-id="b9cbe-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="b9cbe-107">InputObject</span></span>

```
Remove-LocalGroup [-InputObject] <LocalGroup[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b9cbe-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="b9cbe-108">Default</span></span>

```
Remove-LocalGroup [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b9cbe-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="b9cbe-109">SecurityIdentifier</span></span>

```
Remove-LocalGroup [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b9cbe-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9cbe-110">DESCRIPTION</span></span>
<span data-ttu-id="b9cbe-111">O cmdlet **Remove-local** Group exclui grupos de segurança locais.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-111">The **Remove-LocalGroup** cmdlet deletes local security groups.</span></span>
<span data-ttu-id="b9cbe-112">Este cmdlet exclui apenas um grupo local.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-112">This cmdlet deletes only a local group.</span></span>
<span data-ttu-id="b9cbe-113">Ele não exclui as contas de usuário, contas de computador ou contas de grupo que pertencem a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-113">It does not delete the user accounts, computer accounts, or group accounts that belong to that group.</span></span>
<span data-ttu-id="b9cbe-114">Não é possível recuperar um grupo excluído.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-114">You cannot recover a deleted group.</span></span>

<span data-ttu-id="b9cbe-115">Se você excluir um grupo e, em seguida, criar outro grupo com o mesmo nome de grupo, deverá definir novas permissões para o novo grupo.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-115">If you delete a group and then create another group that has the same group name, you must set new permissions for the new group.</span></span>
<span data-ttu-id="b9cbe-116">O novo grupo não herda as permissões que foram atribuídas ao grupo.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-116">The new group does not inherit the permissions that were assigned to the group.</span></span>

> [!NOTE]
> <span data-ttu-id="b9cbe-117">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-117">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="b9cbe-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b9cbe-118">EXAMPLES</span></span>

### <span data-ttu-id="b9cbe-119">Exemplo 1: excluir um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="b9cbe-119">Example 1: Delete a security group</span></span>

```
PS C:\> Remove-LocalGroup -Name "SecurityGroup04"
```

<span data-ttu-id="b9cbe-120">Este comando exclui o grupo chamado SecurityGroup04.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-120">This command deletes the group named SecurityGroup04.</span></span>

## <span data-ttu-id="b9cbe-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b9cbe-121">PARAMETERS</span></span>

### <span data-ttu-id="b9cbe-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b9cbe-122">-InputObject</span></span>
<span data-ttu-id="b9cbe-123">Especifica uma matriz de grupos de segurança que este cmdlet exclui.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-123">Specifies an array of security groups that this cmdlet deletes.</span></span>
<span data-ttu-id="b9cbe-124">Para obter grupos, use o cmdlet Get-LocalGroup.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-124">To obtain groups, use the Get-LocalGroup cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b9cbe-125">-Name</span><span class="sxs-lookup"><span data-stu-id="b9cbe-125">-Name</span></span>
<span data-ttu-id="b9cbe-126">Especifica uma matriz de nomes dos grupos de segurança que este cmdlet exclui.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-126">Specifies an array of names of the security groups that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="b9cbe-127">-SID</span><span class="sxs-lookup"><span data-stu-id="b9cbe-127">-SID</span></span>
<span data-ttu-id="b9cbe-128">Especifica uma matriz de IDs de segurança (SIDs) de grupos de segurança que este cmdlet exclui.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-128">Specifies an array of security IDs (SIDs) of security groups that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="b9cbe-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b9cbe-129">-Confirm</span></span>
<span data-ttu-id="b9cbe-130">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b9cbe-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b9cbe-131">-WhatIf</span></span>
<span data-ttu-id="b9cbe-132">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b9cbe-133">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b9cbe-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b9cbe-134">CommonParameters</span></span>
<span data-ttu-id="b9cbe-135">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b9cbe-136">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b9cbe-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b9cbe-137">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b9cbe-137">INPUTS</span></span>

### <span data-ttu-id="b9cbe-138">System. Management. Automation. SecurityAccountsManager. local, System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="b9cbe-138">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="b9cbe-139">É possível canalizar um grupo de segurança, uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-139">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="b9cbe-140">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b9cbe-140">OUTPUTS</span></span>

### <span data-ttu-id="b9cbe-141">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b9cbe-141">None</span></span>
<span data-ttu-id="b9cbe-142">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b9cbe-143">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b9cbe-143">NOTES</span></span>

* <span data-ttu-id="b9cbe-144">Este cmdlet não pode excluir os seguintes grupos padrão:</span><span class="sxs-lookup"><span data-stu-id="b9cbe-144">This cmdlet cannot delete the following default groups:</span></span>

- <span data-ttu-id="b9cbe-145">Administradores</span><span class="sxs-lookup"><span data-stu-id="b9cbe-145">Administrators</span></span>
- <span data-ttu-id="b9cbe-146">Operadores de cópia</span><span class="sxs-lookup"><span data-stu-id="b9cbe-146">Backup Operators</span></span>
- <span data-ttu-id="b9cbe-147">Operadores criptográficos</span><span class="sxs-lookup"><span data-stu-id="b9cbe-147">Cryptographic Operators</span></span>
- <span data-ttu-id="b9cbe-148">Usuários COM Distribuídos</span><span class="sxs-lookup"><span data-stu-id="b9cbe-148">Distributed COM Users</span></span>
- <span data-ttu-id="b9cbe-149">Leitores de Log de Eventos</span><span class="sxs-lookup"><span data-stu-id="b9cbe-149">Event Log Readers</span></span>
- <span data-ttu-id="b9cbe-150">Convidados</span><span class="sxs-lookup"><span data-stu-id="b9cbe-150">Guests</span></span>
- <span data-ttu-id="b9cbe-151">Administradores do Hyper-V</span><span class="sxs-lookup"><span data-stu-id="b9cbe-151">Hyper-V Administrators</span></span>
- <span data-ttu-id="b9cbe-152">IIS_IUSRS</span><span class="sxs-lookup"><span data-stu-id="b9cbe-152">IIS_IUSRS</span></span>
- <span data-ttu-id="b9cbe-153">Operadores de configuração de rede</span><span class="sxs-lookup"><span data-stu-id="b9cbe-153">Network Configuration Operators</span></span>
- <span data-ttu-id="b9cbe-154">Usuários do Log de Desempenho</span><span class="sxs-lookup"><span data-stu-id="b9cbe-154">Performance Log Users</span></span>
- <span data-ttu-id="b9cbe-155">Usuários do monitor de desempenho</span><span class="sxs-lookup"><span data-stu-id="b9cbe-155">Performance Monitor Users</span></span>
- <span data-ttu-id="b9cbe-156">Usuários avançados</span><span class="sxs-lookup"><span data-stu-id="b9cbe-156">Power Users</span></span>
- <span data-ttu-id="b9cbe-157">Usuários da Área de Trabalho Remota</span><span class="sxs-lookup"><span data-stu-id="b9cbe-157">Remote Desktop Users</span></span>
- <span data-ttu-id="b9cbe-158">Usuários do gerenciamento remoto</span><span class="sxs-lookup"><span data-stu-id="b9cbe-158">Remote Management Users</span></span>
- <span data-ttu-id="b9cbe-159">Replicador</span><span class="sxs-lookup"><span data-stu-id="b9cbe-159">Replicator</span></span>
- <span data-ttu-id="b9cbe-160">Usuários</span><span class="sxs-lookup"><span data-stu-id="b9cbe-160">Users</span></span>
- <span data-ttu-id="b9cbe-161">WinRMRemoteWMIUsers__</span><span class="sxs-lookup"><span data-stu-id="b9cbe-161">WinRMRemoteWMIUsers__</span></span>

* <span data-ttu-id="b9cbe-162">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-162">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="b9cbe-163">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="b9cbe-163">The possible sources are as follows:</span></span>

- <span data-ttu-id="b9cbe-164">Local</span><span class="sxs-lookup"><span data-stu-id="b9cbe-164">Local</span></span>
- <span data-ttu-id="b9cbe-165">Active Directory</span><span class="sxs-lookup"><span data-stu-id="b9cbe-165">Active Directory</span></span>
- <span data-ttu-id="b9cbe-166">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="b9cbe-166">Azure Active Directory group</span></span>
- <span data-ttu-id="b9cbe-167">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b9cbe-167">Microsoft Account</span></span>

<span data-ttu-id="b9cbe-168">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-168">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="b9cbe-169">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="b9cbe-169">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="b9cbe-170">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b9cbe-170">RELATED LINKS</span></span>

[<span data-ttu-id="b9cbe-171">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="b9cbe-171">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="b9cbe-172">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="b9cbe-172">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="b9cbe-173">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="b9cbe-173">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="b9cbe-174">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="b9cbe-174">Set-LocalGroup</span></span>](Set-LocalGroup.md)
