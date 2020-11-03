---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/set-logproperties?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LogProperties
ms.openlocfilehash: ff51e4c30c2554ba58aa28862c44bb5fdbfd78d1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193696"
---
# <span data-ttu-id="4b50f-102">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="4b50f-102">Set-LogProperties</span></span>

## <span data-ttu-id="4b50f-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4b50f-103">SYNOPSIS</span></span>
<span data-ttu-id="4b50f-104">Altera as propriedades de um log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="4b50f-104">Changes the properties of a Windows event log.</span></span>

## <span data-ttu-id="4b50f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4b50f-105">SYNTAX</span></span>

```
Set-LogProperties [-LogDetails] <LogDetails> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="4b50f-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4b50f-106">DESCRIPTION</span></span>

<span data-ttu-id="4b50f-107">Esse cmdlet altera as definições de configuração de um log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="4b50f-107">This cmdlet changes the configuration settings of a Windows event log.</span></span> <span data-ttu-id="4b50f-108">Esse cmdlet é usado pelos `Enable-PSTrace` `Disable-PSTrace` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="4b50f-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

<span data-ttu-id="4b50f-109">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="4b50f-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4b50f-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4b50f-110">EXAMPLES</span></span>

### <span data-ttu-id="4b50f-111">Exemplo 1: alterar a configuração de retenção do log de eventos do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b50f-111">Example 1: Change the retention setting of the Windows PowerShell event log</span></span>

```powershell
$logDetails = Get-LogProperties 'Windows PowerShell'
$logDetails.Retention = $True
Set-LogProperties -LogDetails $logDetails
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : True
AutoBackup : False
MaxLogSize : 15728640
```

## <span data-ttu-id="4b50f-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4b50f-112">PARAMETERS</span></span>

### <span data-ttu-id="4b50f-113">-Force</span><span class="sxs-lookup"><span data-stu-id="4b50f-113">-Force</span></span>

<span data-ttu-id="4b50f-114">Usado para forçar a alteração sem avisar.</span><span class="sxs-lookup"><span data-stu-id="4b50f-114">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="4b50f-115">-LogDetails</span><span class="sxs-lookup"><span data-stu-id="4b50f-115">-LogDetails</span></span>

<span data-ttu-id="4b50f-116">As definições de configuração atualizadas a serem atribuídas ao log de eventos.</span><span class="sxs-lookup"><span data-stu-id="4b50f-116">The updated configuration settings to be assigned to the event log.</span></span>

```yaml
Type: Microsoft.PowerShell.Diagnostics.LogDetails
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4b50f-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4b50f-117">CommonParameters</span></span>

<span data-ttu-id="4b50f-118">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4b50f-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4b50f-119">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4b50f-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4b50f-120">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4b50f-120">INPUTS</span></span>

### <span data-ttu-id="4b50f-121">Microsoft. PowerShell. Diagnostics. LogDetails</span><span class="sxs-lookup"><span data-stu-id="4b50f-121">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="4b50f-122">Você deve passar um objeto **LogDetails** totalmente configurado para o `Set-LogProperties` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4b50f-122">You must pass a fully configured **LogDetails** object to the `Set-LogProperties` cmdlet.</span></span>
<span data-ttu-id="4b50f-123">Portanto, para alterar uma configuração, você deve usar `Get-LogProperties` para recuperar a configuração atual.</span><span class="sxs-lookup"><span data-stu-id="4b50f-123">Therefore, to change one setting, you should use `Get-LogProperties` to retrieve the current configuration.</span></span>

## <span data-ttu-id="4b50f-124">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4b50f-124">OUTPUTS</span></span>

### <span data-ttu-id="4b50f-125">System.Object</span><span class="sxs-lookup"><span data-stu-id="4b50f-125">System.Object</span></span>

## <span data-ttu-id="4b50f-126">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4b50f-126">NOTES</span></span>

<span data-ttu-id="4b50f-127">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="4b50f-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4b50f-128">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4b50f-128">RELATED LINKS</span></span>

[<span data-ttu-id="4b50f-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="4b50f-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="4b50f-130">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="4b50f-130">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="4b50f-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="4b50f-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)
