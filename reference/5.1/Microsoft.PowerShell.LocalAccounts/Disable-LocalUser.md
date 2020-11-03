---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/disable-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-LocalUser
ms.openlocfilehash: a62242251da00688d3299c60e4cdae7aae6f581a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193297"
---
# <span data-ttu-id="8d845-103">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="8d845-103">Disable-LocalUser</span></span>

## <span data-ttu-id="8d845-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8d845-104">SYNOPSIS</span></span>
<span data-ttu-id="8d845-105">Desabilita uma conta de usuário local.</span><span class="sxs-lookup"><span data-stu-id="8d845-105">Disables a local user account.</span></span>

## <span data-ttu-id="8d845-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8d845-106">SYNTAX</span></span>

### <span data-ttu-id="8d845-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="8d845-107">InputObject</span></span>

```
Disable-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8d845-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="8d845-108">Default</span></span>

```
Disable-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8d845-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="8d845-109">SecurityIdentifier</span></span>

```
Disable-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8d845-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8d845-110">DESCRIPTION</span></span>
<span data-ttu-id="8d845-111">O cmdlet **Disable-LocalUser** desabilita as contas de usuário locais.</span><span class="sxs-lookup"><span data-stu-id="8d845-111">The **Disable-LocalUser** cmdlet disables local user accounts.</span></span>
<span data-ttu-id="8d845-112">Quando uma conta de usuário é desabilitada, o usuário não pode fazer logon.</span><span class="sxs-lookup"><span data-stu-id="8d845-112">When a user account is disabled, the user cannot log on.</span></span>
<span data-ttu-id="8d845-113">Quando uma conta de usuário é habilitada, o usuário pode fazer logon.</span><span class="sxs-lookup"><span data-stu-id="8d845-113">When a user account is enabled, the user can log on.</span></span>

> [!NOTE]
> <span data-ttu-id="8d845-114">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="8d845-114">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="8d845-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8d845-115">EXAMPLES</span></span>

### <span data-ttu-id="8d845-116">Exemplo 1: desabilitar uma conta especificando um nome</span><span class="sxs-lookup"><span data-stu-id="8d845-116">Example 1: Disable an account by specifying a name</span></span>

```
PS C:\> Disable-LocalUser -Name "Admin02"
```

<span data-ttu-id="8d845-117">Este comando desabilita a conta de usuário chamada Admin02.</span><span class="sxs-lookup"><span data-stu-id="8d845-117">This command disables the user account named Admin02.</span></span>

### <span data-ttu-id="8d845-118">Exemplo 2: desabilitar uma conta usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="8d845-118">Example 2: Disable an account by using the pipeline</span></span>

```
PS C:\> Get-LocalUser Guest | Disable-LocalUser
```

<span data-ttu-id="8d845-119">Esse comando obtém a conta de convidado interna usando **Get-LocalUser** e, em seguida, a passa para o cmdlet atual usando o operador de pipeline.</span><span class="sxs-lookup"><span data-stu-id="8d845-119">This command gets the built-in Guest account by using **Get-LocalUser** , and then passes it to the current cmdlet by using the pipeline operator.</span></span>
<span data-ttu-id="8d845-120">Esse cmdlet desabilita essa conta.</span><span class="sxs-lookup"><span data-stu-id="8d845-120">That cmdlet disables that account.</span></span>

## <span data-ttu-id="8d845-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8d845-121">PARAMETERS</span></span>

### <span data-ttu-id="8d845-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="8d845-122">-InputObject</span></span>
<span data-ttu-id="8d845-123">Especifica uma matriz de contas de usuário que este cmdlet desabilita.</span><span class="sxs-lookup"><span data-stu-id="8d845-123">Specifies an array of user accounts that this cmdlet disables.</span></span>
<span data-ttu-id="8d845-124">Para obter uma conta de usuário, use o cmdlet Get-LocalUser.</span><span class="sxs-lookup"><span data-stu-id="8d845-124">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

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

### <span data-ttu-id="8d845-125">-Name</span><span class="sxs-lookup"><span data-stu-id="8d845-125">-Name</span></span>
<span data-ttu-id="8d845-126">Especifica uma matriz de nomes das contas de usuário que esse cmdlet desabilita.</span><span class="sxs-lookup"><span data-stu-id="8d845-126">Specifies an array of names of the user accounts that this cmdlet disables.</span></span>

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

### <span data-ttu-id="8d845-127">-SID</span><span class="sxs-lookup"><span data-stu-id="8d845-127">-SID</span></span>
<span data-ttu-id="8d845-128">Especifica uma matriz de contas de usuário que este cmdlet desabilita.</span><span class="sxs-lookup"><span data-stu-id="8d845-128">Specifies an array of user accounts that this cmdlet disables.</span></span>

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

### <span data-ttu-id="8d845-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8d845-129">-Confirm</span></span>
<span data-ttu-id="8d845-130">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8d845-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8d845-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8d845-131">-WhatIf</span></span>
<span data-ttu-id="8d845-132">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="8d845-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8d845-133">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="8d845-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8d845-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8d845-134">CommonParameters</span></span>
<span data-ttu-id="8d845-135">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8d845-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8d845-136">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8d845-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8d845-137">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8d845-137">INPUTS</span></span>

### <span data-ttu-id="8d845-138">System. Management. Automation. SecurityAccountsManager. LocalUser, System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="8d845-138">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="8d845-139">É possível canalizar um usuário local, uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8d845-139">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="8d845-140">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8d845-140">OUTPUTS</span></span>

### <span data-ttu-id="8d845-141">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8d845-141">None</span></span>
<span data-ttu-id="8d845-142">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="8d845-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="8d845-143">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8d845-143">NOTES</span></span>

* <span data-ttu-id="8d845-144">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="8d845-144">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="8d845-145">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="8d845-145">The possible sources are as follows:</span></span>

- <span data-ttu-id="8d845-146">Local</span><span class="sxs-lookup"><span data-stu-id="8d845-146">Local</span></span>
- <span data-ttu-id="8d845-147">Active Directory</span><span class="sxs-lookup"><span data-stu-id="8d845-147">Active Directory</span></span>
- <span data-ttu-id="8d845-148">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="8d845-148">Azure Active Directory group</span></span>
- <span data-ttu-id="8d845-149">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8d845-149">Microsoft Account</span></span>

<span data-ttu-id="8d845-150">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="8d845-150">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="8d845-151">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="8d845-151">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="8d845-152">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8d845-152">RELATED LINKS</span></span>

[<span data-ttu-id="8d845-153">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="8d845-153">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="8d845-154">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="8d845-154">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="8d845-155">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="8d845-155">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="8d845-156">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="8d845-156">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="8d845-157">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="8d845-157">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="8d845-158">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="8d845-158">Set-LocalUser</span></span>](Set-LocalUser.md)
