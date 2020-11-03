---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LocalUser
ms.openlocfilehash: a6352611b757dae828a2efef07f9ce65abaa5e2e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194220"
---
# <span data-ttu-id="1d718-103">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="1d718-103">Set-LocalUser</span></span>

## <span data-ttu-id="1d718-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1d718-104">SYNOPSIS</span></span>
<span data-ttu-id="1d718-105">Modifica uma conta de usuário local.</span><span class="sxs-lookup"><span data-stu-id="1d718-105">Modifies a local user account.</span></span>

## <span data-ttu-id="1d718-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1d718-106">SYNTAX</span></span>

### <span data-ttu-id="1d718-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="1d718-107">Name (Default)</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-Name] <String> [-Password <SecureString>] [-PasswordNeverExpires <Boolean>]
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1d718-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="1d718-108">InputObject</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-InputObject] <LocalUser> [-Password <SecureString>] [-PasswordNeverExpires <Boolean>]
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1d718-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="1d718-109">SecurityIdentifier</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-Password <SecureString>] [-PasswordNeverExpires <Boolean>] [-SID] <SecurityIdentifier>
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1d718-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1d718-110">DESCRIPTION</span></span>
<span data-ttu-id="1d718-111">O cmdlet **set-LocalUser** modifica uma conta de usuário local.</span><span class="sxs-lookup"><span data-stu-id="1d718-111">The **Set-LocalUser** cmdlet modifies a local user account.</span></span>
<span data-ttu-id="1d718-112">Esse cmdlet pode redefinir a senha de uma conta de usuário local.</span><span class="sxs-lookup"><span data-stu-id="1d718-112">This cmdlet can reset the password of a local user account.</span></span>

> [!NOTE]
> <span data-ttu-id="1d718-113">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="1d718-113">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="1d718-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1d718-114">EXAMPLES</span></span>

### <span data-ttu-id="1d718-115">Exemplo 1: alterar uma descrição de uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="1d718-115">Example 1: Change a description of a user account</span></span>

```
PS C:\> Set-LocalUser -Name "Admin07" -Description "Description of this account."
```

<span data-ttu-id="1d718-116">Esse comando altera a descrição de uma conta de usuário chamada Admin07.</span><span class="sxs-lookup"><span data-stu-id="1d718-116">This command changes the description of a user account named Admin07.</span></span>

### <span data-ttu-id="1d718-117">Exemplo 2: alterar a senha em uma conta</span><span class="sxs-lookup"><span data-stu-id="1d718-117">Example 2: Change the password on an account</span></span>

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> $UserAccount = Get-LocalUser -Name "User02"
PS C:\> $UserAccount | Set-LocalUser -Password $Password
```

<span data-ttu-id="1d718-118">O primeiro comando solicita uma senha usando o cmdlet Read-Host.</span><span class="sxs-lookup"><span data-stu-id="1d718-118">The first command prompts you for a password by using the Read-Host cmdlet.</span></span>
<span data-ttu-id="1d718-119">O comando armazena a senha como uma cadeia de caracteres segura na variável $Password.</span><span class="sxs-lookup"><span data-stu-id="1d718-119">The command stores the password as a secure string in the $Password variable.</span></span>

<span data-ttu-id="1d718-120">O segundo comando obtém uma conta de usuário chamada User02 usando **Get-LocalUser** .</span><span class="sxs-lookup"><span data-stu-id="1d718-120">The second command gets a user account named User02 by using **Get-LocalUser** .</span></span>
<span data-ttu-id="1d718-121">O comando armazena a conta na variável $UserAccount.</span><span class="sxs-lookup"><span data-stu-id="1d718-121">The command stores the account in the $UserAccount variable.</span></span>

<span data-ttu-id="1d718-122">O terceiro comando define a nova senha na conta de usuário armazenada em $UserAccount.</span><span class="sxs-lookup"><span data-stu-id="1d718-122">The third command sets the new password on the user account stored in $UserAccount.</span></span>

## <span data-ttu-id="1d718-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1d718-123">PARAMETERS</span></span>

### <span data-ttu-id="1d718-124">-AccountExpires</span><span class="sxs-lookup"><span data-stu-id="1d718-124">-AccountExpires</span></span>
<span data-ttu-id="1d718-125">Especifica quando a conta de usuário expira.</span><span class="sxs-lookup"><span data-stu-id="1d718-125">Specifies when the user account expires.</span></span>
<span data-ttu-id="1d718-126">Para obter um objeto **DateTime** , use o cmdlet Get-Date.</span><span class="sxs-lookup"><span data-stu-id="1d718-126">To obtain a **DateTime** object, use the Get-Date cmdlet.</span></span>

<span data-ttu-id="1d718-127">Se você não quiser que a conta expire, especifique o parâmetro *AccountNeverExpires* .</span><span class="sxs-lookup"><span data-stu-id="1d718-127">If you do not want the account to expire, specify the *AccountNeverExpires* parameter.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d718-128">-AccountNeverExpires</span><span class="sxs-lookup"><span data-stu-id="1d718-128">-AccountNeverExpires</span></span>
<span data-ttu-id="1d718-129">Indica que a conta não expira.</span><span class="sxs-lookup"><span data-stu-id="1d718-129">Indicates that the account does not expire.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d718-130">-Description</span><span class="sxs-lookup"><span data-stu-id="1d718-130">-Description</span></span>
<span data-ttu-id="1d718-131">Especifica um comentário para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="1d718-131">Specifies a comment for the user account.</span></span>
<span data-ttu-id="1d718-132">O comprimento máximo é de 48 caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d718-132">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d718-133">-FullName</span><span class="sxs-lookup"><span data-stu-id="1d718-133">-FullName</span></span>
<span data-ttu-id="1d718-134">Especifica o nome completo da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="1d718-134">Specifies the full name for the user account.</span></span>
<span data-ttu-id="1d718-135">O nome completo é diferente do nome de usuário da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="1d718-135">The full name differs from the user name of the user account.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d718-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1d718-136">-InputObject</span></span>
<span data-ttu-id="1d718-137">Especifica a conta de usuário que esse cmdlet altera.</span><span class="sxs-lookup"><span data-stu-id="1d718-137">Specifies the user account that this cmdlet changes.</span></span>
<span data-ttu-id="1d718-138">Para obter uma conta de usuário, use o cmdlet Get-LocalUser.</span><span class="sxs-lookup"><span data-stu-id="1d718-138">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

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

### <span data-ttu-id="1d718-139">-Name</span><span class="sxs-lookup"><span data-stu-id="1d718-139">-Name</span></span>
<span data-ttu-id="1d718-140">Especifica o nome da conta de usuário que esse cmdlet altera.</span><span class="sxs-lookup"><span data-stu-id="1d718-140">Specifies the name of the user account that this cmdlet changes.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1d718-141">-Password</span><span class="sxs-lookup"><span data-stu-id="1d718-141">-Password</span></span>
<span data-ttu-id="1d718-142">Especifica uma senha para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="1d718-142">Specifies a password for the user account.</span></span>
<span data-ttu-id="1d718-143">Se a conta de usuário estiver conectada a um conta Microsoft, não defina uma senha.</span><span class="sxs-lookup"><span data-stu-id="1d718-143">If the user account is connected to a Microsoft account, do not set a password.</span></span>

<span data-ttu-id="1d718-144">Você pode usar `Read-Host -GetCredential` , Get-Credential ou ConvertTo-SecureString para criar um objeto **SecureString** para a senha.</span><span class="sxs-lookup"><span data-stu-id="1d718-144">You can use `Read-Host -GetCredential`, Get-Credential, or ConvertTo-SecureString to create a **SecureString** object for the password.</span></span>

<span data-ttu-id="1d718-145">Se você omitir os parâmetros *password* e *NOPassword* , **set-LocalUser** solicitará a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="1d718-145">If you omit the *Password* and *NoPassword* parameters, **Set-LocalUser** prompts you for the user's password.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d718-146">-PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="1d718-146">-PasswordNeverExpires</span></span>
<span data-ttu-id="1d718-147">Indica se a senha expira.</span><span class="sxs-lookup"><span data-stu-id="1d718-147">Indicates whether the password expires.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d718-148">-SID</span><span class="sxs-lookup"><span data-stu-id="1d718-148">-SID</span></span>
<span data-ttu-id="1d718-149">Especifica a ID de segurança (SID) da conta de usuário que esse cmdlet altera.</span><span class="sxs-lookup"><span data-stu-id="1d718-149">Specifies the security ID (SID) of the user account that this cmdlet changes.</span></span>

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

### <span data-ttu-id="1d718-150">-UserMayChangePassword</span><span class="sxs-lookup"><span data-stu-id="1d718-150">-UserMayChangePassword</span></span>
<span data-ttu-id="1d718-151">Indica que o usuário pode alterar a senha na conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="1d718-151">Indicates that the user can change the password on the user account.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d718-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1d718-152">-Confirm</span></span>
<span data-ttu-id="1d718-153">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1d718-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1d718-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1d718-154">-WhatIf</span></span>
<span data-ttu-id="1d718-155">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="1d718-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1d718-156">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="1d718-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1d718-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1d718-157">CommonParameters</span></span>
<span data-ttu-id="1d718-158">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1d718-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1d718-159">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1d718-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1d718-160">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1d718-160">INPUTS</span></span>

### <span data-ttu-id="1d718-161">System. Management. Automation. SecurityAccountsManager. LocalUser, System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="1d718-161">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="1d718-162">É possível canalizar um usuário local, uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1d718-162">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="1d718-163">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1d718-163">OUTPUTS</span></span>

### <span data-ttu-id="1d718-164">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1d718-164">None</span></span>
<span data-ttu-id="1d718-165">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="1d718-165">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1d718-166">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1d718-166">NOTES</span></span>

* <span data-ttu-id="1d718-167">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="1d718-167">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="1d718-168">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="1d718-168">The possible sources are as follows:</span></span>

- <span data-ttu-id="1d718-169">Local</span><span class="sxs-lookup"><span data-stu-id="1d718-169">Local</span></span>
- <span data-ttu-id="1d718-170">Active Directory</span><span class="sxs-lookup"><span data-stu-id="1d718-170">Active Directory</span></span>
- <span data-ttu-id="1d718-171">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="1d718-171">Azure Active Directory group</span></span>
- <span data-ttu-id="1d718-172">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1d718-172">Microsoft Account</span></span>

<span data-ttu-id="1d718-173">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="1d718-173">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="1d718-174">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="1d718-174">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="1d718-175">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1d718-175">RELATED LINKS</span></span>

[<span data-ttu-id="1d718-176">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="1d718-176">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="1d718-177">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="1d718-177">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="1d718-178">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="1d718-178">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="1d718-179">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="1d718-179">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="1d718-180">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="1d718-180">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="1d718-181">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="1d718-181">Rename-LocalUser</span></span>](Rename-LocalUser.md)
