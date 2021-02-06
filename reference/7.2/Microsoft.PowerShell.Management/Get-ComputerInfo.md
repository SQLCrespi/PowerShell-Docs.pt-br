---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: abc820bd6f8f5c8cd8c6301aacee268c82161d7e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597417"
---
# <span data-ttu-id="eefa6-102">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="eefa6-102">Get-ComputerInfo</span></span>

## <span data-ttu-id="eefa6-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="eefa6-103">SYNOPSIS</span></span>
<span data-ttu-id="eefa6-104">Obtém um objeto consolidado das propriedades sistema e sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="eefa6-104">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="eefa6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eefa6-105">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="eefa6-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="eefa6-106">DESCRIPTION</span></span>

<span data-ttu-id="eefa6-107">O `Get-ComputerInfo` cmdlet obtém um objeto consolidado das propriedades sistema e sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="eefa6-107">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="eefa6-108">Esse cmdlet foi introduzido no Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="eefa6-108">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="eefa6-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="eefa6-109">EXAMPLES</span></span>

### <span data-ttu-id="eefa6-110">Exemplo 1: obter todas as propriedades do computador</span><span class="sxs-lookup"><span data-stu-id="eefa6-110">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="eefa6-111">Esse comando obtém todas as propriedades do sistema e do sistema operacional do computador.</span><span class="sxs-lookup"><span data-stu-id="eefa6-111">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="eefa6-112">Exemplo 2: obter todas as propriedades do sistema operacional do computador</span><span class="sxs-lookup"><span data-stu-id="eefa6-112">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="eefa6-113">Esse comando obtém todas as propriedades do sistema operacional do computador.</span><span class="sxs-lookup"><span data-stu-id="eefa6-113">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="eefa6-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="eefa6-114">PARAMETERS</span></span>

### <span data-ttu-id="eefa6-115">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="eefa6-115">-Property</span></span>

<span data-ttu-id="eefa6-116">Especifica, como uma matriz de cadeia de caracteres, as propriedades do computador em que esse cmdlet é exibido.</span><span class="sxs-lookup"><span data-stu-id="eefa6-116">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

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

### <span data-ttu-id="eefa6-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="eefa6-117">CommonParameters</span></span>

<span data-ttu-id="eefa6-118">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="eefa6-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eefa6-119">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="eefa6-119">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="eefa6-120">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="eefa6-120">INPUTS</span></span>

### <span data-ttu-id="eefa6-121">System.String[]</span><span class="sxs-lookup"><span data-stu-id="eefa6-121">System.String[]</span></span>

## <span data-ttu-id="eefa6-122">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="eefa6-122">OUTPUTS</span></span>

### <span data-ttu-id="eefa6-123">Microsoft. PowerShell. Management. ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="eefa6-123">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="eefa6-124">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="eefa6-124">NOTES</span></span>

<span data-ttu-id="eefa6-125">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="eefa6-125">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="eefa6-126">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="eefa6-126">RELATED LINKS</span></span>
