---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroup
ms.openlocfilehash: 2cd77c2766840527825b0ccf68abaac3c2ea6c16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193292"
---
# <span data-ttu-id="a0d71-103">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="a0d71-103">Get-LocalGroup</span></span>

## <span data-ttu-id="a0d71-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a0d71-104">SYNOPSIS</span></span>
<span data-ttu-id="a0d71-105">Obtém os grupos de segurança locais.</span><span class="sxs-lookup"><span data-stu-id="a0d71-105">Gets the local security groups.</span></span>

## <span data-ttu-id="a0d71-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a0d71-106">SYNTAX</span></span>

### <span data-ttu-id="a0d71-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="a0d71-107">Default (Default)</span></span>

```
Get-LocalGroup [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="a0d71-108">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="a0d71-108">SecurityIdentifier</span></span>

```
Get-LocalGroup [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## <span data-ttu-id="a0d71-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a0d71-109">DESCRIPTION</span></span>
<span data-ttu-id="a0d71-110">O cmdlet **Get-local** Obtém grupos de segurança locais no Gerenciador de contas de segurança.</span><span class="sxs-lookup"><span data-stu-id="a0d71-110">The **Get-LocalGroup** cmdlet gets local security groups in Security Account Manager.</span></span>
<span data-ttu-id="a0d71-111">Esse cmdlet obtém grupos internos padrão e grupos de segurança locais que você cria.</span><span class="sxs-lookup"><span data-stu-id="a0d71-111">This cmdlet gets default built-in groups and local security groups that you create.</span></span>

> [!NOTE]
> <span data-ttu-id="a0d71-112">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="a0d71-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="a0d71-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a0d71-113">EXAMPLES</span></span>

### <span data-ttu-id="a0d71-114">Exemplo 1: obter o grupo de administradores</span><span class="sxs-lookup"><span data-stu-id="a0d71-114">Example 1: Get the Administrators group</span></span>

```
PS C:\> Get-LocalGroup -Name "Administrators"
Name           Description
----           -----------
Administrators Administrators have complete and unrestricted access to the computer/domain
```

<span data-ttu-id="a0d71-115">Esse comando obtém o grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="a0d71-115">This command gets the local Administrators group.</span></span>
<span data-ttu-id="a0d71-116">O comando exibe as propriedades do grupo no console.</span><span class="sxs-lookup"><span data-stu-id="a0d71-116">The command displays properties of the group in the console.</span></span>

## <span data-ttu-id="a0d71-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a0d71-117">PARAMETERS</span></span>

### <span data-ttu-id="a0d71-118">-Name</span><span class="sxs-lookup"><span data-stu-id="a0d71-118">-Name</span></span>
<span data-ttu-id="a0d71-119">Especifica uma matriz de nomes de grupos de segurança que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="a0d71-119">Specifies an array of names of security groups that this cmdlet gets.</span></span>
<span data-ttu-id="a0d71-120">Você pode usar o caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="a0d71-120">You can use the wildcard character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a0d71-121">-SID</span><span class="sxs-lookup"><span data-stu-id="a0d71-121">-SID</span></span>
<span data-ttu-id="a0d71-122">Especifica uma matriz de IDs de segurança (SIDs) de grupos de segurança que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="a0d71-122">Specifies an array of security IDs (SIDs) of security groups that this cmdlet gets.</span></span>

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

### <span data-ttu-id="a0d71-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a0d71-123">CommonParameters</span></span>
<span data-ttu-id="a0d71-124">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a0d71-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a0d71-125">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a0d71-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a0d71-126">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a0d71-126">INPUTS</span></span>

### <span data-ttu-id="a0d71-127">System. String, System. Security. principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="a0d71-127">System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="a0d71-128">É possível canalizar uma cadeia de caracteres ou um SID para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a0d71-128">You can pipe a string or a SID to this cmdlet.</span></span>

## <span data-ttu-id="a0d71-129">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a0d71-129">OUTPUTS</span></span>

### <span data-ttu-id="a0d71-130">System. Management. Automation. SecurityAccountsManager. local</span><span class="sxs-lookup"><span data-stu-id="a0d71-130">System.Management.Automation.SecurityAccountsManager.LocalGroup</span></span>
<span data-ttu-id="a0d71-131">Esse cmdlet retorna um grupo local.</span><span class="sxs-lookup"><span data-stu-id="a0d71-131">This cmdlet returns a local group.</span></span>

## <span data-ttu-id="a0d71-132">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a0d71-132">NOTES</span></span>

* <span data-ttu-id="a0d71-133">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="a0d71-133">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="a0d71-134">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="a0d71-134">The possible sources are as follows:</span></span>

- <span data-ttu-id="a0d71-135">Local</span><span class="sxs-lookup"><span data-stu-id="a0d71-135">Local</span></span>
- <span data-ttu-id="a0d71-136">Active Directory</span><span class="sxs-lookup"><span data-stu-id="a0d71-136">Active Directory</span></span>
- <span data-ttu-id="a0d71-137">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="a0d71-137">Azure Active Directory group</span></span>
- <span data-ttu-id="a0d71-138">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a0d71-138">Microsoft Account</span></span>

<span data-ttu-id="a0d71-139">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="a0d71-139">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="a0d71-140">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="a0d71-140">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="a0d71-141">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a0d71-141">RELATED LINKS</span></span>

[<span data-ttu-id="a0d71-142">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="a0d71-142">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="a0d71-143">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="a0d71-143">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="a0d71-144">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="a0d71-144">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="a0d71-145">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="a0d71-145">Set-LocalGroup</span></span>](Set-LocalGroup.md)
