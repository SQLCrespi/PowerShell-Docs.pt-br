---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: bb3f2b78fecd33288a0febd2882277721d9cf289
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342674"
---
# <span data-ttu-id="f74ec-103">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="f74ec-103">Get-ComputerInfo</span></span>

## <span data-ttu-id="f74ec-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f74ec-104">SYNOPSIS</span></span>
<span data-ttu-id="f74ec-105">Obtém um objeto consolidado das propriedades sistema e sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="f74ec-105">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="f74ec-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f74ec-106">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="f74ec-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f74ec-107">DESCRIPTION</span></span>

<span data-ttu-id="f74ec-108">O `Get-ComputerInfo` cmdlet obtém um objeto consolidado das propriedades sistema e sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="f74ec-108">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="f74ec-109">Esse cmdlet foi introduzido no Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="f74ec-109">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="f74ec-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f74ec-110">EXAMPLES</span></span>

### <span data-ttu-id="f74ec-111">Exemplo 1: obter todas as propriedades do computador</span><span class="sxs-lookup"><span data-stu-id="f74ec-111">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="f74ec-112">Esse comando obtém todas as propriedades do sistema e do sistema operacional do computador.</span><span class="sxs-lookup"><span data-stu-id="f74ec-112">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="f74ec-113">Exemplo 2: obter todas as propriedades do sistema operacional do computador</span><span class="sxs-lookup"><span data-stu-id="f74ec-113">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="f74ec-114">Esse comando obtém todas as propriedades do sistema operacional do computador.</span><span class="sxs-lookup"><span data-stu-id="f74ec-114">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="f74ec-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f74ec-115">PARAMETERS</span></span>

### <span data-ttu-id="f74ec-116">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="f74ec-116">-Property</span></span>

<span data-ttu-id="f74ec-117">Especifica, como uma matriz de cadeia de caracteres, as propriedades do computador em que esse cmdlet é exibido.</span><span class="sxs-lookup"><span data-stu-id="f74ec-117">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="f74ec-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f74ec-118">CommonParameters</span></span>

<span data-ttu-id="f74ec-119">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f74ec-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f74ec-120">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="f74ec-120">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f74ec-121">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f74ec-121">INPUTS</span></span>

### <span data-ttu-id="f74ec-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="f74ec-122">System.String[]</span></span>

## <span data-ttu-id="f74ec-123">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f74ec-123">OUTPUTS</span></span>

### <span data-ttu-id="f74ec-124">Microsoft. PowerShell. Management. ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="f74ec-124">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="f74ec-125">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f74ec-125">NOTES</span></span>

## <span data-ttu-id="f74ec-126">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f74ec-126">RELATED LINKS</span></span>
