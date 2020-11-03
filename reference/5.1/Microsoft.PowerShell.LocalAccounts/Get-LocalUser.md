---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalUser
ms.openlocfilehash: 34210145bcddc8d9420552d637a6cd6e5f8e61cc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193288"
---
# <span data-ttu-id="31479-103">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="31479-103">Get-LocalUser</span></span>

## <span data-ttu-id="31479-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="31479-104">SYNOPSIS</span></span>
<span data-ttu-id="31479-105">Obtém as contas de usuário local.</span><span class="sxs-lookup"><span data-stu-id="31479-105">Gets local user accounts.</span></span>

## <span data-ttu-id="31479-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="31479-106">SYNTAX</span></span>

### <span data-ttu-id="31479-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="31479-107">Default (Default)</span></span>

```
Get-LocalUser [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="31479-108">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="31479-108">SecurityIdentifier</span></span>

```
Get-LocalUser [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## <span data-ttu-id="31479-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="31479-109">DESCRIPTION</span></span>

<span data-ttu-id="31479-110">O `Get-LocalUser` cmdlet obtém contas de usuário local.</span><span class="sxs-lookup"><span data-stu-id="31479-110">The `Get-LocalUser` cmdlet gets local user accounts.</span></span> <span data-ttu-id="31479-111">Esse cmdlet obtém as contas de usuário internas padrão, as contas de usuário locais que você criou e as contas locais que você conectou às contas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="31479-111">This cmdlet gets default built-in user accounts, local user accounts that you created, and local accounts that you connected to Microsoft accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="31479-112">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="31479-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="31479-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="31479-113">EXAMPLES</span></span>

### <span data-ttu-id="31479-114">Exemplo 1: obter uma conta usando seu nome</span><span class="sxs-lookup"><span data-stu-id="31479-114">Example 1: Get an account by using its name</span></span>

<span data-ttu-id="31479-115">Este exemplo obtém uma conta de usuário chamada AdminContoso02.</span><span class="sxs-lookup"><span data-stu-id="31479-115">This example gets a user account named AdminContoso02.</span></span>

```powershell
Get-LocalUser -Name "AdminContoso02"
```

```Output
Name             Enabled Description
----             ------- -----------
AdminContoso02   True    Description of this account.
```

### <span data-ttu-id="31479-116">Exemplo 2: obter uma conta que está conectada a um conta Microsoft</span><span class="sxs-lookup"><span data-stu-id="31479-116">Example 2: Get an account that is connected to a Microsoft account</span></span>

<span data-ttu-id="31479-117">Este exemplo obtém uma conta de usuário que está conectada a um conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="31479-117">This example gets a user account that is connected to a Microsoft account.</span></span> <span data-ttu-id="31479-118">Este exemplo usa um valor de espaço reservado para o nome de usuário de uma conta em Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="31479-118">This example uses a placeholder value for the username of an account at Outlook.com.</span></span>

```powershell
Get-LocalUser -Name "MicrosoftAccount\username@Outlook.com"
```

```Output
Name                                    Enabled  Description
----                                    -------  -----------
MicrosoftAccount\username@outlook.com  True     Description of this account.
```

### <span data-ttu-id="31479-119">Exemplo 3: obter uma conta que está conectada a um conta Microsoft</span><span class="sxs-lookup"><span data-stu-id="31479-119">Example 3: Get an account that is connected to a Microsoft account</span></span>

<span data-ttu-id="31479-120">Este exemplo obtém uma conta de usuário local que tem o SID especificado.</span><span class="sxs-lookup"><span data-stu-id="31479-120">This example gets a local user account that has the specified SID.</span></span>

```powershell
Get-LocalUser -SID S-1-5-21-9526073513-1762370368-3942940353-500
```

```Output
Name          Enabled Description
----          ------- -----------
Administrator True    Built-in account for administering the computer/domain
```

## <span data-ttu-id="31479-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="31479-121">PARAMETERS</span></span>

### <span data-ttu-id="31479-122">-Name</span><span class="sxs-lookup"><span data-stu-id="31479-122">-Name</span></span>

<span data-ttu-id="31479-123">Especifica uma matriz de nomes de contas de usuário que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="31479-123">Specifies an array of names of user accounts that this cmdlet gets.</span></span> <span data-ttu-id="31479-124">Você pode usar o caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="31479-124">You can use the wildcard character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="31479-125">-SID</span><span class="sxs-lookup"><span data-stu-id="31479-125">-SID</span></span>

<span data-ttu-id="31479-126">Especifica uma matriz de IDs de segurança (SIDs) de contas de usuário que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="31479-126">Specifies an array of security IDs (SIDs) of user accounts that this cmdlet gets.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="31479-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="31479-127">CommonParameters</span></span>

<span data-ttu-id="31479-128">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="31479-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="31479-129">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="31479-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="31479-130">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="31479-130">INPUTS</span></span>

### <span data-ttu-id="31479-131">System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="31479-131">System.String, System.Security.Principal.SecurityIdentifier</span></span>

<span data-ttu-id="31479-132">É possível canalizar uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="31479-132">You can pipe a string or SID to this cmdlet.</span></span>

## <span data-ttu-id="31479-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="31479-133">OUTPUTS</span></span>

### <span data-ttu-id="31479-134">System. Management. Automation. SecurityAccountsManager. LocalUser []</span><span class="sxs-lookup"><span data-stu-id="31479-134">System.Management.Automation.SecurityAccountsManager.LocalUser[]</span></span>

<span data-ttu-id="31479-135">Esse cmdlet retorna contas de usuário local.</span><span class="sxs-lookup"><span data-stu-id="31479-135">This cmdlet returns local user accounts.</span></span>

## <span data-ttu-id="31479-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="31479-136">NOTES</span></span>

<span data-ttu-id="31479-137">A propriedade **Principado** nos objetos **LocalUser** , **local** e **LocalPrincipal** descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="31479-137">The **PrincipalSource** property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects describes the source of the object.</span></span> <span data-ttu-id="31479-138">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="31479-138">The possible sources are as follows:</span></span>

- <span data-ttu-id="31479-139">Local</span><span class="sxs-lookup"><span data-stu-id="31479-139">Local</span></span>
- <span data-ttu-id="31479-140">Active Directory</span><span class="sxs-lookup"><span data-stu-id="31479-140">Active Directory</span></span>
- <span data-ttu-id="31479-141">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="31479-141">Azure Active Directory group</span></span>
- <span data-ttu-id="31479-142">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="31479-142">Microsoft Account</span></span>

<span data-ttu-id="31479-143">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="31479-143">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="31479-144">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="31479-144">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="31479-145">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="31479-145">RELATED LINKS</span></span>

[<span data-ttu-id="31479-146">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="31479-146">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="31479-147">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="31479-147">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="31479-148">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="31479-148">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="31479-149">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="31479-149">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="31479-150">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="31479-150">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="31479-151">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="31479-151">Set-LocalUser</span></span>](Set-LocalUser.md)
