---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalUser
ms.openlocfilehash: d83f3ad12481df0849ff2fe3f61d553a9ffdcdde
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193984"
---
# <span data-ttu-id="74089-103">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="74089-103">New-LocalUser</span></span>

## <span data-ttu-id="74089-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="74089-104">SYNOPSIS</span></span>

<span data-ttu-id="74089-105">Cria uma conta de usuário local.</span><span class="sxs-lookup"><span data-stu-id="74089-105">Creates a local user account.</span></span>

## <span data-ttu-id="74089-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="74089-106">SYNTAX</span></span>

### <span data-ttu-id="74089-107">Senha (padrão)</span><span class="sxs-lookup"><span data-stu-id="74089-107">Password (Default)</span></span>

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> -Password <SecureString> [-PasswordNeverExpires]
 [-UserMayNotChangePassword] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="74089-108">Senha não</span><span class="sxs-lookup"><span data-stu-id="74089-108">NoPassword</span></span>

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> [-NoPassword] [-UserMayNotChangePassword] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="74089-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="74089-109">DESCRIPTION</span></span>

<span data-ttu-id="74089-110">O `New-LocalUser` cmdlet cria uma conta de usuário local.</span><span class="sxs-lookup"><span data-stu-id="74089-110">The `New-LocalUser` cmdlet creates a local user account.</span></span> <span data-ttu-id="74089-111">Esse cmdlet cria uma conta de usuário local ou uma conta de usuário local que está conectada a um conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74089-111">This cmdlet creates a local user account or a local user account that is connected to a Microsoft account.</span></span>

> [!NOTE]
> <span data-ttu-id="74089-112">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="74089-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="74089-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="74089-113">EXAMPLES</span></span>

### <span data-ttu-id="74089-114">Exemplo 1: criar uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="74089-114">Example 1: Create a user account</span></span>

```
PS C:\> New-LocalUser -Name "User02" -Description "Description of this account." -NoPassword
Name    Enabled  Description
----    -------  -----------
User02  True     Description of this account.
```

<span data-ttu-id="74089-115">Este comando cria uma conta de usuário local e não especifica os parâmetros de **AccountExpires** ou **senha** .</span><span class="sxs-lookup"><span data-stu-id="74089-115">This command creates a local user account and does not specify the **AccountExpires** or **Password** parameters.</span></span> <span data-ttu-id="74089-116">Portanto, a conta não expira ou tem uma senha por padrão.</span><span class="sxs-lookup"><span data-stu-id="74089-116">Therefore, the account doesn't expire or have a password by default.</span></span>

### <span data-ttu-id="74089-117">Exemplo 2: criar uma conta de usuário que tenha uma senha</span><span class="sxs-lookup"><span data-stu-id="74089-117">Example 2: Create a user account that has a password</span></span>

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> New-LocalUser "User03" -Password $Password -FullName "Third User" -Description "Description of this account."
Name    Enabled  Description
----    -------  -----------
User03  True     Description of this account.
```

<span data-ttu-id="74089-118">O primeiro comando solicita uma senha usando o `Read-Host` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="74089-118">The first command prompts you for a password by using the `Read-Host` cmdlet.</span></span> <span data-ttu-id="74089-119">O comando armazena a senha como uma cadeia de caracteres segura na `$Password` variável.</span><span class="sxs-lookup"><span data-stu-id="74089-119">The command stores the password as a secure string in the `$Password` variable.</span></span>

<span data-ttu-id="74089-120">O segundo comando cria uma conta de usuário local usando a senha armazenada em `$Password` .</span><span class="sxs-lookup"><span data-stu-id="74089-120">The second command creates a local user account by using the password stored in `$Password`.</span></span> <span data-ttu-id="74089-121">O comando especifica um nome de usuário, nome completo e descrição para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="74089-121">The command specifies a user name, full name, and description for the user account.</span></span>

## <span data-ttu-id="74089-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="74089-122">PARAMETERS</span></span>

### <span data-ttu-id="74089-123">-AccountExpires</span><span class="sxs-lookup"><span data-stu-id="74089-123">-AccountExpires</span></span>

<span data-ttu-id="74089-124">Especifica quando a conta de usuário expira.</span><span class="sxs-lookup"><span data-stu-id="74089-124">Specifies when the user account expires.</span></span> <span data-ttu-id="74089-125">Para obter um objeto **DateTime** , use o `Get-Date` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="74089-125">To obtain a **DateTime** object, use the `Get-Date` cmdlet.</span></span>
<span data-ttu-id="74089-126">Se você não especificar esse parâmetro, a conta não expirará.</span><span class="sxs-lookup"><span data-stu-id="74089-126">If you do not specify this parameter, the account does not expire.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74089-127">-AccountNeverExpires</span><span class="sxs-lookup"><span data-stu-id="74089-127">-AccountNeverExpires</span></span>

<span data-ttu-id="74089-128">Indica que a conta não expira.</span><span class="sxs-lookup"><span data-stu-id="74089-128">Indicates that the account does not expire.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74089-129">-Description</span><span class="sxs-lookup"><span data-stu-id="74089-129">-Description</span></span>

<span data-ttu-id="74089-130">Especifica um comentário para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="74089-130">Specifies a comment for the user account.</span></span>
<span data-ttu-id="74089-131">O comprimento máximo é de 48 caracteres.</span><span class="sxs-lookup"><span data-stu-id="74089-131">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74089-132">-Desabilitado</span><span class="sxs-lookup"><span data-stu-id="74089-132">-Disabled</span></span>

<span data-ttu-id="74089-133">Indica que esse cmdlet cria a conta de usuário como desabilitada.</span><span class="sxs-lookup"><span data-stu-id="74089-133">Indicates that this cmdlet creates the user account as disabled.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74089-134">-FullName</span><span class="sxs-lookup"><span data-stu-id="74089-134">-FullName</span></span>

<span data-ttu-id="74089-135">Especifica o nome completo da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="74089-135">Specifies the full name for the user account.</span></span> <span data-ttu-id="74089-136">O nome completo é diferente do nome de usuário da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="74089-136">The full name differs from the user name of the user account.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74089-137">-Name</span><span class="sxs-lookup"><span data-stu-id="74089-137">-Name</span></span>

<span data-ttu-id="74089-138">Especifica o nome de usuário para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="74089-138">Specifies the user name for the user account.</span></span>

<span data-ttu-id="74089-139">Se você criar uma conta de usuário local para o sistema local, o nome de usuário poderá conter até 20 caracteres maiúsculos ou minúsculos.</span><span class="sxs-lookup"><span data-stu-id="74089-139">If you create a local user account for the local system, the user name can contain up to 20 uppercase characters or lowercase characters.</span></span> <span data-ttu-id="74089-140">Um nome de usuário não pode conter os seguintes caracteres:</span><span class="sxs-lookup"><span data-stu-id="74089-140">A user name cannot contain the following characters:</span></span>

<span data-ttu-id="74089-141">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span><span class="sxs-lookup"><span data-stu-id="74089-141">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span></span>

<span data-ttu-id="74089-142">Um nome de usuário não pode consistir apenas em pontos `.` ou espaços.</span><span class="sxs-lookup"><span data-stu-id="74089-142">A user name cannot consist only of periods `.` or spaces.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="74089-143">-Nosenha</span><span class="sxs-lookup"><span data-stu-id="74089-143">-NoPassword</span></span>

<span data-ttu-id="74089-144">Indica que a conta de usuário não tem uma senha.</span><span class="sxs-lookup"><span data-stu-id="74089-144">Indicates that the user account does not have a password.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoPassword
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74089-145">-Password</span><span class="sxs-lookup"><span data-stu-id="74089-145">-Password</span></span>

<span data-ttu-id="74089-146">Especifica uma senha para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="74089-146">Specifies a password for the user account.</span></span> <span data-ttu-id="74089-147">Você pode usar `Read-Host -GetCredential` , `Get-Credential` ou `ConvertTo-SecureString` para criar um objeto **SecureString** para a senha.</span><span class="sxs-lookup"><span data-stu-id="74089-147">You can use `Read-Host -GetCredential`, `Get-Credential`, or `ConvertTo-SecureString` to create a **SecureString** object for the password.</span></span>

<span data-ttu-id="74089-148">Se você omitir os parâmetros **password** e **NOPassword** , `New-LocalUser` o solicitará a senha do novo usuário.</span><span class="sxs-lookup"><span data-stu-id="74089-148">If you omit the **Password** and **NoPassword** parameters, `New-LocalUser` prompts you for the new user's password.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: Password
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74089-149">-PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="74089-149">-PasswordNeverExpires</span></span>

<span data-ttu-id="74089-150">Indica se a senha expira.</span><span class="sxs-lookup"><span data-stu-id="74089-150">Indicates whether the password expires.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Password
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74089-151">-UserMayNotChangePassword</span><span class="sxs-lookup"><span data-stu-id="74089-151">-UserMayNotChangePassword</span></span>

<span data-ttu-id="74089-152">Indica que o usuário não pode alterar a senha na conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="74089-152">Indicates that the user cannot change the password on the user account.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74089-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="74089-153">-Confirm</span></span>

<span data-ttu-id="74089-154">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="74089-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="74089-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="74089-155">-WhatIf</span></span>

<span data-ttu-id="74089-156">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="74089-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="74089-157">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="74089-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="74089-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="74089-158">CommonParameters</span></span>

<span data-ttu-id="74089-159">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="74089-159">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="74089-160">Para obter mais informações, confira [about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="74089-160">For more information, see [about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="74089-161">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="74089-161">INPUTS</span></span>

### <span data-ttu-id="74089-162">System. String, System. DateTime, System. booliano, System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="74089-162">System.String, System.DateTime, System.Boolean, System.Security.SecureString</span></span>

<span data-ttu-id="74089-163">É possível canalizar uma cadeia de caracteres, um objeto **DateTime** , um valor booliano ou uma cadeia de caracteres segura para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="74089-163">You can pipe a string, a **DateTime** object, a boolean value, or a secure string to this cmdlet.</span></span>

## <span data-ttu-id="74089-164">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="74089-164">OUTPUTS</span></span>

### <span data-ttu-id="74089-165">System. Management. Automation. SecurityAccountsManager. LocalUser</span><span class="sxs-lookup"><span data-stu-id="74089-165">System.Management.Automation.SecurityAccountsManager.LocalUser</span></span>

<span data-ttu-id="74089-166">Esse cmdlet retorna um objeto **LocalUser** .</span><span class="sxs-lookup"><span data-stu-id="74089-166">This cmdlet returns a **LocalUser** object.</span></span>
<span data-ttu-id="74089-167">Este objeto fornece informações sobre a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="74089-167">This object provides information about the user account.</span></span>

## <span data-ttu-id="74089-168">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="74089-168">NOTES</span></span>

- <span data-ttu-id="74089-169">Um nome de usuário não pode ser idêntico a nenhum outro nome de usuário ou nome de grupo no computador.</span><span class="sxs-lookup"><span data-stu-id="74089-169">A user name cannot be identical to any other user name or group name on the computer.</span></span> <span data-ttu-id="74089-170">Um nome de usuário não pode consistir apenas em pontos `.` ou espaços.</span><span class="sxs-lookup"><span data-stu-id="74089-170">A user name cannot consist only of periods `.` or spaces.</span></span> <span data-ttu-id="74089-171">Um nome de usuário pode conter até 20 caracteres maiúsculos ou minúsculos.</span><span class="sxs-lookup"><span data-stu-id="74089-171">A user name can contain up to 20 uppercase characters or lowercase characters.</span></span> <span data-ttu-id="74089-172">Um nome de usuário não pode conter os seguintes caracteres:</span><span class="sxs-lookup"><span data-stu-id="74089-172">A user name cannot contain the following characters:</span></span>

<span data-ttu-id="74089-173">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span><span class="sxs-lookup"><span data-stu-id="74089-173">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span></span>

- <span data-ttu-id="74089-174">Uma senha pode conter até 127 caracteres.</span><span class="sxs-lookup"><span data-stu-id="74089-174">A password can contain up to 127 characters.</span></span>
- <span data-ttu-id="74089-175">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="74089-175">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="74089-176">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="74089-176">The possible sources are as follows:</span></span>

  - <span data-ttu-id="74089-177">Local</span><span class="sxs-lookup"><span data-stu-id="74089-177">Local</span></span>
  - <span data-ttu-id="74089-178">Active Directory</span><span class="sxs-lookup"><span data-stu-id="74089-178">Active Directory</span></span>
  - <span data-ttu-id="74089-179">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="74089-179">Azure Active Directory group</span></span>
  - <span data-ttu-id="74089-180">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="74089-180">Microsoft Account</span></span>

> [!NOTE]
> <span data-ttu-id="74089-181">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="74089-181">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="74089-182">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="74089-182">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="74089-183">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="74089-183">RELATED LINKS</span></span>

[<span data-ttu-id="74089-184">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="74089-184">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="74089-185">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="74089-185">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="74089-186">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="74089-186">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="74089-187">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="74089-187">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="74089-188">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="74089-188">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="74089-189">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="74089-189">Set-LocalUser</span></span>](Set-LocalUser.md)
