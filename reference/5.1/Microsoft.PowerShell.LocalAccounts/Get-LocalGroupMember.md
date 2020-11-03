---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroupMember
ms.openlocfilehash: 200368c5d13bd027302ad824533e6c187906ed0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193289"
---
# <span data-ttu-id="28dce-103">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="28dce-103">Get-LocalGroupMember</span></span>

## <span data-ttu-id="28dce-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="28dce-104">SYNOPSIS</span></span>
<span data-ttu-id="28dce-105">Obtém membros de um grupo local.</span><span class="sxs-lookup"><span data-stu-id="28dce-105">Gets members from a local group.</span></span>

## <span data-ttu-id="28dce-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="28dce-106">SYNTAX</span></span>

### <span data-ttu-id="28dce-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="28dce-107">Default (Default)</span></span>

```
Get-LocalGroupMember [[-Member] <String>] [-Name] <String> [<CommonParameters>]
```

### <span data-ttu-id="28dce-108">Grupo</span><span class="sxs-lookup"><span data-stu-id="28dce-108">Group</span></span>

```
Get-LocalGroupMember [-Group] <LocalGroup> [[-Member] <String>] [<CommonParameters>]
```

### <span data-ttu-id="28dce-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="28dce-109">SecurityIdentifier</span></span>

```
Get-LocalGroupMember [[-Member] <String>] [-SID] <SecurityIdentifier> [<CommonParameters>]
```

## <span data-ttu-id="28dce-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28dce-110">DESCRIPTION</span></span>
<span data-ttu-id="28dce-111">O cmdlet **Get-LocalGroupMember** Obtém membros de um grupo local.</span><span class="sxs-lookup"><span data-stu-id="28dce-111">The **Get-LocalGroupMember** cmdlet gets members from a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="28dce-112">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="28dce-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="28dce-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="28dce-113">EXAMPLES</span></span>

### <span data-ttu-id="28dce-114">Exemplo 1: obter todos os membros do grupo de administradores</span><span class="sxs-lookup"><span data-stu-id="28dce-114">Example 1: Get all members of the Administrators group</span></span>

```
PS C:\> Get-LocalGroupMember -Group "Administrators"
ObjectClass Name                    PrincipalSource
----------- ----                    ---------------
User        CONTOSOPC\Administrator Local
User        CONTOSOPC\LocalAdmin    Local
```

<span data-ttu-id="28dce-115">Esse comando obtém todos os membros do grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="28dce-115">This command gets all the members of the local Administrators group.</span></span>

## <span data-ttu-id="28dce-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="28dce-116">PARAMETERS</span></span>

### <span data-ttu-id="28dce-117">-Grupo</span><span class="sxs-lookup"><span data-stu-id="28dce-117">-Group</span></span>
<span data-ttu-id="28dce-118">Especifica o grupo de segurança do qual este cmdlet obtém Membros.</span><span class="sxs-lookup"><span data-stu-id="28dce-118">Specifies the security group from which this cmdlet gets members.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="28dce-119">-Membro</span><span class="sxs-lookup"><span data-stu-id="28dce-119">-Member</span></span>
<span data-ttu-id="28dce-120">Especifica um usuário ou grupo que esse cmdlet obtém de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="28dce-120">Specifies a user or group that this cmdlet gets from a security group.</span></span>
<span data-ttu-id="28dce-121">Você pode especificar usuários ou grupos por nome ou ID de segurança (SID).</span><span class="sxs-lookup"><span data-stu-id="28dce-121">You can specify users or groups by name or security ID (SID).</span></span>
<span data-ttu-id="28dce-122">Especifique as cadeias de caracteres de SID em S-R-I-S-S.</span><span class="sxs-lookup"><span data-stu-id="28dce-122">Specify SID strings in S-R-I-S-S .</span></span>
<span data-ttu-id="28dce-123">.</span><span class="sxs-lookup"><span data-stu-id="28dce-123">.</span></span> <span data-ttu-id="28dce-124">.</span><span class="sxs-lookup"><span data-stu-id="28dce-124">.</span></span>
<span data-ttu-id="28dce-125">.</span><span class="sxs-lookup"><span data-stu-id="28dce-125">format.</span></span>
<span data-ttu-id="28dce-126">Você pode usar caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="28dce-126">You can use wildcard characters.</span></span>
<span data-ttu-id="28dce-127">Se você não especificar esse parâmetro, o cmdlet obterá todos os membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="28dce-127">If you do not specify this parameter, the cmdlet gets all members of the group.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28dce-128">-Name</span><span class="sxs-lookup"><span data-stu-id="28dce-128">-Name</span></span>
<span data-ttu-id="28dce-129">Especifica o nome do grupo de segurança do qual este cmdlet obtém Membros.</span><span class="sxs-lookup"><span data-stu-id="28dce-129">Specifies the name of the security group from which this cmdlet gets members.</span></span>

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

### <span data-ttu-id="28dce-130">-SID</span><span class="sxs-lookup"><span data-stu-id="28dce-130">-SID</span></span>
<span data-ttu-id="28dce-131">Especifica a ID de segurança do grupo de segurança do qual este cmdlet obtém Membros.</span><span class="sxs-lookup"><span data-stu-id="28dce-131">Specifies the security ID of the security group from which this cmdlet gets members.</span></span>

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

### <span data-ttu-id="28dce-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="28dce-132">CommonParameters</span></span>
<span data-ttu-id="28dce-133">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="28dce-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="28dce-134">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="28dce-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="28dce-135">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="28dce-135">INPUTS</span></span>

### <span data-ttu-id="28dce-136">System. Management. Automation. SecurityAccountsManager. local, System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="28dce-136">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="28dce-137">É possível canalizar um grupo local, uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="28dce-137">You can pipe a local group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="28dce-138">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="28dce-138">OUTPUTS</span></span>

### <span data-ttu-id="28dce-139">Microsoft. SecurityAccountsManager. LocalPrincipal</span><span class="sxs-lookup"><span data-stu-id="28dce-139">Microsoft.SecurityAccountsManager.LocalPrincipal</span></span>
<span data-ttu-id="28dce-140">Esse cmdlet retorna entidades de segurança locais.</span><span class="sxs-lookup"><span data-stu-id="28dce-140">This cmdlet returns local principals.</span></span>

## <span data-ttu-id="28dce-141">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="28dce-141">NOTES</span></span>

* <span data-ttu-id="28dce-142">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="28dce-142">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="28dce-143">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="28dce-143">The possible sources are as follows:</span></span>

- <span data-ttu-id="28dce-144">Local</span><span class="sxs-lookup"><span data-stu-id="28dce-144">Local</span></span>
- <span data-ttu-id="28dce-145">Active Directory</span><span class="sxs-lookup"><span data-stu-id="28dce-145">Active Directory</span></span>
- <span data-ttu-id="28dce-146">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="28dce-146">Azure Active Directory group</span></span>
- <span data-ttu-id="28dce-147">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="28dce-147">Microsoft Account</span></span>

<span data-ttu-id="28dce-148">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="28dce-148">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="28dce-149">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="28dce-149">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="28dce-150">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="28dce-150">RELATED LINKS</span></span>

[<span data-ttu-id="28dce-151">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="28dce-151">Add-LocalGroupMember</span></span>](Add-LocalGroupMember.md)

[<span data-ttu-id="28dce-152">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="28dce-152">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="28dce-153">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="28dce-153">Remove-LocalGroupMember</span></span>](Remove-LocalGroupMember.md)
