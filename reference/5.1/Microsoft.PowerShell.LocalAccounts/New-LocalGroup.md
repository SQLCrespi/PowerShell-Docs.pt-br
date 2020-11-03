---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalGroup
ms.openlocfilehash: de66ad724d3cfee2d296d3b431618768a9cd38da
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193988"
---
# <span data-ttu-id="090fd-103">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="090fd-103">New-LocalGroup</span></span>

## <span data-ttu-id="090fd-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="090fd-104">SYNOPSIS</span></span>
<span data-ttu-id="090fd-105">Cria um grupo de segurança local.</span><span class="sxs-lookup"><span data-stu-id="090fd-105">Creates a local security group.</span></span>

## <span data-ttu-id="090fd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="090fd-106">SYNTAX</span></span>

```
New-LocalGroup [-Description <String>] [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="090fd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="090fd-107">DESCRIPTION</span></span>
<span data-ttu-id="090fd-108">O cmdlet **New-local** Group cria um grupo de segurança local no Gerenciador de contas de segurança.</span><span class="sxs-lookup"><span data-stu-id="090fd-108">The **New-LocalGroup** cmdlet creates a local security group in the Security Account Manager.</span></span>

> [!NOTE]
> <span data-ttu-id="090fd-109">O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="090fd-109">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="090fd-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="090fd-110">EXAMPLES</span></span>

### <span data-ttu-id="090fd-111">Exemplo 1: criar um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="090fd-111">Example 1: Create a security group</span></span>

```
PS C:\> New-LocalGroup -Name "SecurityGroup04"
```

<span data-ttu-id="090fd-112">Este comando cria um grupo chamado SecurityGroup04.</span><span class="sxs-lookup"><span data-stu-id="090fd-112">This command creates a group named SecurityGroup04.</span></span>

## <span data-ttu-id="090fd-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="090fd-113">PARAMETERS</span></span>

### <span data-ttu-id="090fd-114">-Description</span><span class="sxs-lookup"><span data-stu-id="090fd-114">-Description</span></span>
<span data-ttu-id="090fd-115">Especifica um comentário para o grupo.</span><span class="sxs-lookup"><span data-stu-id="090fd-115">Specifies a comment for the group.</span></span>
<span data-ttu-id="090fd-116">O comprimento máximo é de 48 caracteres.</span><span class="sxs-lookup"><span data-stu-id="090fd-116">The maximum length is 48 characters.</span></span>

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

### <span data-ttu-id="090fd-117">-Name</span><span class="sxs-lookup"><span data-stu-id="090fd-117">-Name</span></span>
<span data-ttu-id="090fd-118">Especifica um nome para o grupo.</span><span class="sxs-lookup"><span data-stu-id="090fd-118">Specifies a name for the group.</span></span>
<span data-ttu-id="090fd-119">O tamanho máximo é de 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="090fd-119">The maximum length is 256 characters.</span></span>

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

### <span data-ttu-id="090fd-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="090fd-120">-Confirm</span></span>
<span data-ttu-id="090fd-121">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="090fd-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="090fd-122">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="090fd-122">-WhatIf</span></span>
<span data-ttu-id="090fd-123">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="090fd-123">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="090fd-124">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="090fd-124">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="090fd-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="090fd-125">CommonParameters</span></span>
<span data-ttu-id="090fd-126">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="090fd-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="090fd-127">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="090fd-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="090fd-128">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="090fd-128">INPUTS</span></span>

### <span data-ttu-id="090fd-129">System.String</span><span class="sxs-lookup"><span data-stu-id="090fd-129">System.String</span></span>
<span data-ttu-id="090fd-130">É possível canalizar uma cadeia de caracteres para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="090fd-130">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="090fd-131">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="090fd-131">OUTPUTS</span></span>

### <span data-ttu-id="090fd-132">System. Management. Automation. SecurityAccountsManager. local</span><span class="sxs-lookup"><span data-stu-id="090fd-132">System.Management.Automation.SecurityAccountsManager.LocalGroup</span></span>
<span data-ttu-id="090fd-133">Esse cmdlet retorna um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="090fd-133">This cmdlet returns a security group.</span></span>

## <span data-ttu-id="090fd-134">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="090fd-134">NOTES</span></span>

* <span data-ttu-id="090fd-135">A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto.</span><span class="sxs-lookup"><span data-stu-id="090fd-135">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="090fd-136">As fontes possíveis são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="090fd-136">The possible sources are as follows:</span></span>

- <span data-ttu-id="090fd-137">Local</span><span class="sxs-lookup"><span data-stu-id="090fd-137">Local</span></span>
- <span data-ttu-id="090fd-138">Active Directory</span><span class="sxs-lookup"><span data-stu-id="090fd-138">Active Directory</span></span>
- <span data-ttu-id="090fd-139">Grupo do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="090fd-139">Azure Active Directory group</span></span>
- <span data-ttu-id="090fd-140">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="090fd-140">Microsoft Account</span></span>

<span data-ttu-id="090fd-141">A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="090fd-141">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="090fd-142">Para versões anteriores, a propriedade fica em branco.</span><span class="sxs-lookup"><span data-stu-id="090fd-142">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="090fd-143">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="090fd-143">RELATED LINKS</span></span>

[<span data-ttu-id="090fd-144">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="090fd-144">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="090fd-145">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="090fd-145">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="090fd-146">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="090fd-146">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="090fd-147">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="090fd-147">Set-LocalGroup</span></span>](Set-LocalGroup.md)
