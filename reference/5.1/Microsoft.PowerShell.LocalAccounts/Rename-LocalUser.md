---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/rename-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-LocalUser
ms.openlocfilehash: fc5740e52e08ad2146981799a4e1659cd420b321
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194224"
---
# <span data-ttu-id="2acf9-103">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="2acf9-103">Rename-LocalUser</span></span>

## <span data-ttu-id="2acf9-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2acf9-104">SYNOPSIS</span></span>
<span data-ttu-id="2acf9-105">Renomeia uma conta de usuário local.</span><span class="sxs-lookup"><span data-stu-id="2acf9-105">Renames a local user account.</span></span>

## <span data-ttu-id="2acf9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2acf9-106">SYNTAX</span></span>

### <span data-ttu-id="2acf9-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="2acf9-107">InputObject</span></span>

```
Rename-LocalUser [-InputObject] <LocalUser> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2acf9-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="2acf9-108">Default</span></span>

```
Rename-LocalUser [-Name] <String> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2acf9-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="2acf9-109">SecurityIdentifier</span></span>

```
Rename-LocalUser [-NewName] <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2acf9-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2acf9-110">DESCRIPTION</span></span>
<span data-ttu-id="2acf9-111">O cmdlet **renomear-LocalUser** renomeia uma conta de usuário local.</span><span class="sxs-lookup"><span data-stu-id="2acf9-111">The **Rename-LocalUser** cmdlet renames a local user account.</span></span>

> [!NOTE]
> <span data-ttu-id="2acf9-112">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="2acf9-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="2acf9-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2acf9-113">EXAMPLES</span></span>

### <span data-ttu-id="2acf9-114">Exemplo 1: renomear uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="2acf9-114">Example 1: Rename a user account</span></span>

```
PS C:\> Rename-LocalUser -Name "Admin02" -NewName "AdminContoso02"
```

<span data-ttu-id="2acf9-115">Esse comando renomeia a conta de usuário chamada Admin02.</span><span class="sxs-lookup"><span data-stu-id="2acf9-115">This command renames the user account named Admin02.</span></span>

## <span data-ttu-id="2acf9-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2acf9-116">PARAMETERS</span></span>

### <span data-ttu-id="2acf9-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2acf9-117">-InputObject</span></span>
<span data-ttu-id="2acf9-118">Especifica a conta de usuário que esse cmdlet renomeia.</span><span class="sxs-lookup"><span data-stu-id="2acf9-118">Specifies the user account that this cmdlet renames.</span></span>
<span data-ttu-id="2acf9-119">Para obter uma conta de usuário, use o cmdlet Get-LocalUser.</span><span class="sxs-lookup"><span data-stu-id="2acf9-119">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2acf9-120">-Name</span><span class="sxs-lookup"><span data-stu-id="2acf9-120">-Name</span></span>
<span data-ttu-id="2acf9-121">Especifica o nome da conta de usuário que esse cmdlet renomeia.</span><span class="sxs-lookup"><span data-stu-id="2acf9-121">Specifies the name of the user account that this cmdlet renames.</span></span>

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

### <span data-ttu-id="2acf9-122">-NewName</span><span class="sxs-lookup"><span data-stu-id="2acf9-122">-NewName</span></span>
<span data-ttu-id="2acf9-123">Especifica um novo nome para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="2acf9-123">Specifies a new name for the user account.</span></span>

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

### <span data-ttu-id="2acf9-124">-SID</span><span class="sxs-lookup"><span data-stu-id="2acf9-124">-SID</span></span>
<span data-ttu-id="2acf9-125">Especifica a ID de segurança (SID) de uma conta de usuário que esse cmdlet renomeia.</span><span class="sxs-lookup"><span data-stu-id="2acf9-125">Specifies the security ID (SID) of a user accounts that this cmdlet renames.</span></span>

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

### <span data-ttu-id="2acf9-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2acf9-126">-Confirm</span></span>
<span data-ttu-id="2acf9-127">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2acf9-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2acf9-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2acf9-128">-WhatIf</span></span>
<span data-ttu-id="2acf9-129">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="2acf9-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2acf9-130">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="2acf9-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2acf9-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2acf9-131">CommonParameters</span></span>
<span data-ttu-id="2acf9-132">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2acf9-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2acf9-133">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2acf9-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2acf9-134">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2acf9-134">INPUTS</span></span>

### <span data-ttu-id="2acf9-135">System. Management. Automation. SecurityAccountsManager. LocalUser, System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="2acf9-135">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="2acf9-136">É possível canalizar um usuário local, uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2acf9-136">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="2acf9-137">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2acf9-137">OUTPUTS</span></span>

### <span data-ttu-id="2acf9-138">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2acf9-138">None</span></span>
<span data-ttu-id="2acf9-139">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="2acf9-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2acf9-140">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2acf9-140">NOTES</span></span>

* <span data-ttu-id="2acf9-141">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="2acf9-141">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="2acf9-142">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="2acf9-142">The possible sources are as follows:</span></span>

- <span data-ttu-id="2acf9-143">Local</span><span class="sxs-lookup"><span data-stu-id="2acf9-143">Local</span></span>
- <span data-ttu-id="2acf9-144">Active Directory</span><span class="sxs-lookup"><span data-stu-id="2acf9-144">Active Directory</span></span>
- <span data-ttu-id="2acf9-145">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="2acf9-145">Azure Active Directory group</span></span>
- <span data-ttu-id="2acf9-146">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2acf9-146">Microsoft Account</span></span>

<span data-ttu-id="2acf9-147">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="2acf9-147">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="2acf9-148">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="2acf9-148">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="2acf9-149">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2acf9-149">RELATED LINKS</span></span>

[<span data-ttu-id="2acf9-150">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="2acf9-150">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="2acf9-151">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="2acf9-151">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="2acf9-152">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="2acf9-152">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="2acf9-153">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="2acf9-153">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="2acf9-154">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="2acf9-154">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="2acf9-155">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="2acf9-155">Set-LocalUser</span></span>](Set-LocalUser.md)
