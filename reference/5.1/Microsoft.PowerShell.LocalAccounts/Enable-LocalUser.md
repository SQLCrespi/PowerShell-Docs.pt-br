---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/enable-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-LocalUser
ms.openlocfilehash: 80d062578e7114b69e5cb5f3367b56da3871b9df
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193295"
---
# <span data-ttu-id="ff8bf-103">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ff8bf-103">Enable-LocalUser</span></span>

## <span data-ttu-id="ff8bf-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ff8bf-104">SYNOPSIS</span></span>
<span data-ttu-id="ff8bf-105">Habilita uma conta de usuário local.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-105">Enables a local user account.</span></span>

## <span data-ttu-id="ff8bf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ff8bf-106">SYNTAX</span></span>

### <span data-ttu-id="ff8bf-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="ff8bf-107">InputObject</span></span>

```
Enable-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ff8bf-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="ff8bf-108">Default</span></span>

```
Enable-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ff8bf-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="ff8bf-109">SecurityIdentifier</span></span>

```
Enable-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ff8bf-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ff8bf-110">DESCRIPTION</span></span>
<span data-ttu-id="ff8bf-111">O cmdlet **Enable-LocalUser** habilita contas de usuário local.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-111">The **Enable-LocalUser** cmdlet enables local user accounts.</span></span>
<span data-ttu-id="ff8bf-112">Quando uma conta de usuário é desabilitada, o usuário não pode fazer logon.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-112">When a user account is disabled, the user cannot log on.</span></span>
<span data-ttu-id="ff8bf-113">Quando uma conta de usuário é habilitada, o usuário pode fazer logon.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-113">When a user account is enabled, the user can log on.</span></span>

> [!NOTE]
> <span data-ttu-id="ff8bf-114">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-114">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="ff8bf-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ff8bf-115">EXAMPLES</span></span>

### <span data-ttu-id="ff8bf-116">Exemplo 1: habilitar uma conta especificando um nome</span><span class="sxs-lookup"><span data-stu-id="ff8bf-116">Example 1: Enable an account by specifying a name</span></span>

```
PS C:\> Enable-LocalUser -Name "Admin02"
```

<span data-ttu-id="ff8bf-117">Esse comando habilita a conta de usuário chamada Admin02.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-117">This command enables the user account named Admin02.</span></span>

### <span data-ttu-id="ff8bf-118">Exemplo 2: habilitar uma conta usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="ff8bf-118">Example 2: Enable an account by using the pipeline</span></span>

```
PS C:\> Get-LocalUser -Name "Administrator" | Enable-LocalUser
```

<span data-ttu-id="ff8bf-119">Esse comando obtém a conta de administrador interno usando **Get-LocalUser** e, em seguida, a passa para o cmdlet atual usando o operador de pipeline.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-119">This command gets the built-in Administrator account by using **Get-LocalUser** , and then passes it to the current cmdlet by using the pipeline operator.</span></span>
<span data-ttu-id="ff8bf-120">Esse cmdlet habilita essa conta.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-120">That cmdlet enables that account.</span></span>

## <span data-ttu-id="ff8bf-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ff8bf-121">PARAMETERS</span></span>

### <span data-ttu-id="ff8bf-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ff8bf-122">-InputObject</span></span>
<span data-ttu-id="ff8bf-123">Especifica uma matriz de contas de usuário que esse cmdlet habilita.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-123">Specifies an array of user accounts that this cmdlet enables.</span></span>
<span data-ttu-id="ff8bf-124">Para obter uma conta de usuário, use o cmdlet Get-LocalUser.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-124">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

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

### <span data-ttu-id="ff8bf-125">-Name</span><span class="sxs-lookup"><span data-stu-id="ff8bf-125">-Name</span></span>
<span data-ttu-id="ff8bf-126">Especifica uma matriz de nomes das contas de usuário que esse cmdlet habilita.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-126">Specifies an array of names of the user accounts that this cmdlet enables.</span></span>

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

### <span data-ttu-id="ff8bf-127">-SID</span><span class="sxs-lookup"><span data-stu-id="ff8bf-127">-SID</span></span>
<span data-ttu-id="ff8bf-128">Especifica uma matriz de contas de usuário que esse cmdlet habilita.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-128">Specifies an array of user accounts that this cmdlet enables.</span></span>

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

### <span data-ttu-id="ff8bf-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ff8bf-129">-Confirm</span></span>
<span data-ttu-id="ff8bf-130">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ff8bf-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ff8bf-131">-WhatIf</span></span>
<span data-ttu-id="ff8bf-132">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ff8bf-133">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ff8bf-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ff8bf-134">CommonParameters</span></span>
<span data-ttu-id="ff8bf-135">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ff8bf-136">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ff8bf-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ff8bf-137">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ff8bf-137">INPUTS</span></span>

### <span data-ttu-id="ff8bf-138">System. Management. Automation. SecurityAccountsManager. LocalUser, System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="ff8bf-138">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="ff8bf-139">É possível canalizar um usuário local, uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-139">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="ff8bf-140">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ff8bf-140">OUTPUTS</span></span>

### <span data-ttu-id="ff8bf-141">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ff8bf-141">None</span></span>
<span data-ttu-id="ff8bf-142">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ff8bf-143">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ff8bf-143">NOTES</span></span>

* <span data-ttu-id="ff8bf-144">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-144">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="ff8bf-145">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="ff8bf-145">The possible sources are as follows:</span></span>

- <span data-ttu-id="ff8bf-146">Local</span><span class="sxs-lookup"><span data-stu-id="ff8bf-146">Local</span></span>
- <span data-ttu-id="ff8bf-147">Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff8bf-147">Active Directory</span></span>
- <span data-ttu-id="ff8bf-148">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="ff8bf-148">Azure Active Directory group</span></span>
- <span data-ttu-id="ff8bf-149">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ff8bf-149">Microsoft Account</span></span>

<span data-ttu-id="ff8bf-150">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-150">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="ff8bf-151">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="ff8bf-151">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="ff8bf-152">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ff8bf-152">RELATED LINKS</span></span>

[<span data-ttu-id="ff8bf-153">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ff8bf-153">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="ff8bf-154">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ff8bf-154">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="ff8bf-155">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ff8bf-155">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="ff8bf-156">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ff8bf-156">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="ff8bf-157">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ff8bf-157">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="ff8bf-158">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ff8bf-158">Set-LocalUser</span></span>](Set-LocalUser.md)
