---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: 447d8a07c6e5d6ba4f47685819907937c75711db
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103193981"
---
# <span data-ttu-id="ef6a6-102">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="ef6a6-102">Get-LogProperties</span></span>

## <span data-ttu-id="ef6a6-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ef6a6-103">SYNOPSIS</span></span>
<span data-ttu-id="ef6a6-104">Recupera as propriedades de um log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="ef6a6-104">Retrieves the properties of a Windows event log.</span></span>

## <span data-ttu-id="ef6a6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ef6a6-105">SYNTAX</span></span>

```
Get-LogProperties [-Name] <string> [<CommonParameters>]
```

## <span data-ttu-id="ef6a6-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ef6a6-106">DESCRIPTION</span></span>

<span data-ttu-id="ef6a6-107">Esse cmdlet obtém as definições de configuração de um log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="ef6a6-107">This cmdlet gets the configuration settings of a Windows event log.</span></span> <span data-ttu-id="ef6a6-108">Esse cmdlet é usado pelos `Enable-PSTrace` `Disable-PSTrace` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="ef6a6-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

## <span data-ttu-id="ef6a6-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ef6a6-109">EXAMPLES</span></span>

### <span data-ttu-id="ef6a6-110">Exemplo 1: obter as definições de configuração do log de eventos do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef6a6-110">Example 1: Get the configuration settings of the Windows PowerShell event log</span></span>

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

## <span data-ttu-id="ef6a6-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ef6a6-111">PARAMETERS</span></span>

### <span data-ttu-id="ef6a6-112">-Name</span><span class="sxs-lookup"><span data-stu-id="ef6a6-112">-Name</span></span>

<span data-ttu-id="ef6a6-113">O nome do provedor de eventos.</span><span class="sxs-lookup"><span data-stu-id="ef6a6-113">The name of the event provider.</span></span>

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

### <span data-ttu-id="ef6a6-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ef6a6-114">CommonParameters</span></span>

<span data-ttu-id="ef6a6-115">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ef6a6-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ef6a6-116">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ef6a6-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ef6a6-117">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ef6a6-117">INPUTS</span></span>

### <span data-ttu-id="ef6a6-118">System.Object</span><span class="sxs-lookup"><span data-stu-id="ef6a6-118">System.Object</span></span>

## <span data-ttu-id="ef6a6-119">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ef6a6-119">OUTPUTS</span></span>

### <span data-ttu-id="ef6a6-120">Microsoft. PowerShell. Diagnostics. LogDetails</span><span class="sxs-lookup"><span data-stu-id="ef6a6-120">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="ef6a6-121">O módulo **PSDiagnostics** adiciona a classe **LogDetails** ao `Microsoft.PowerShell.Diagnostics` namespace.</span><span class="sxs-lookup"><span data-stu-id="ef6a6-121">The **PSDiagnostics** module adds the **LogDetails** class to the `Microsoft.PowerShell.Diagnostics` namespace.</span></span>

## <span data-ttu-id="ef6a6-122">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ef6a6-122">NOTES</span></span>

## <span data-ttu-id="ef6a6-123">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ef6a6-123">RELATED LINKS</span></span>

[<span data-ttu-id="ef6a6-124">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="ef6a6-124">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="ef6a6-125">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="ef6a6-125">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="ef6a6-126">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="ef6a6-126">Disable-PSTrace</span></span>](Disable-PSTrace.md)
