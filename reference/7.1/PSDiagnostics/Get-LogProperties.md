---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
Locale: en-US
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: 5b95fe3bc643c9e12a3d216523c086d9b0cdf901
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193242"
---
# <span data-ttu-id="fffd2-102">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="fffd2-102">Get-LogProperties</span></span>

## <span data-ttu-id="fffd2-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fffd2-103">SYNOPSIS</span></span>
<span data-ttu-id="fffd2-104">Recupera as propriedades de um log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="fffd2-104">Retrieves the properties of a Windows event log.</span></span>

## <span data-ttu-id="fffd2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fffd2-105">SYNTAX</span></span>

```
Get-LogProperties [-Name] <Object> [<CommonParameters>]
```

## <span data-ttu-id="fffd2-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fffd2-106">DESCRIPTION</span></span>

<span data-ttu-id="fffd2-107">Esse cmdlet obtém as definições de configuração de um log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="fffd2-107">This cmdlet gets the configuration settings of a Windows event log.</span></span> <span data-ttu-id="fffd2-108">Esse cmdlet é usado pelos `Enable-PSTrace` `Disable-PSTrace` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="fffd2-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

## <span data-ttu-id="fffd2-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fffd2-109">EXAMPLES</span></span>

### <span data-ttu-id="fffd2-110">Exemplo 1: obter as definições de configuração do log de eventos do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fffd2-110">Example 1: Get the configuration settings of the Windows PowerShell event log</span></span>

```powershell
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : False
AutoBackup : False
MaxLogSize : 15728640
```

## <span data-ttu-id="fffd2-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fffd2-111">PARAMETERS</span></span>

### <span data-ttu-id="fffd2-112">-Name</span><span class="sxs-lookup"><span data-stu-id="fffd2-112">-Name</span></span>

<span data-ttu-id="fffd2-113">O nome do provedor de eventos.</span><span class="sxs-lookup"><span data-stu-id="fffd2-113">The name of the event provider.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fffd2-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fffd2-114">CommonParameters</span></span>

<span data-ttu-id="fffd2-115">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fffd2-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fffd2-116">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fffd2-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fffd2-117">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fffd2-117">INPUTS</span></span>

### <span data-ttu-id="fffd2-118">System.String</span><span class="sxs-lookup"><span data-stu-id="fffd2-118">System.String</span></span>

## <span data-ttu-id="fffd2-119">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fffd2-119">OUTPUTS</span></span>

### <span data-ttu-id="fffd2-120">Microsoft. PowerShell. Diagnostics. LogDetails</span><span class="sxs-lookup"><span data-stu-id="fffd2-120">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="fffd2-121">O módulo **PSDiagnostics** adiciona a classe **LogDetails** ao `Microsoft.PowerShell.Diagnostics` namespace.</span><span class="sxs-lookup"><span data-stu-id="fffd2-121">The **PSDiagnostics** module adds the **LogDetails** class to the `Microsoft.PowerShell.Diagnostics` namespace.</span></span>

## <span data-ttu-id="fffd2-122">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fffd2-122">NOTES</span></span>

## <span data-ttu-id="fffd2-123">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fffd2-123">RELATED LINKS</span></span>

[<span data-ttu-id="fffd2-124">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="fffd2-124">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="fffd2-125">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="fffd2-125">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="fffd2-126">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="fffd2-126">Disable-PSTrace</span></span>](Disable-PSTrace.md)

