---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/set-logproperties?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LogProperties
ms.openlocfilehash: a852a3016d7e63d17b86cf2efb3c928d2f7b901c
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194538"
---
# <span data-ttu-id="8fcf3-102">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="8fcf3-102">Set-LogProperties</span></span>

## <span data-ttu-id="8fcf3-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8fcf3-103">SYNOPSIS</span></span>
<span data-ttu-id="8fcf3-104">Altera as propriedades de um log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="8fcf3-104">Changes the properties of a Windows event log.</span></span>

## <span data-ttu-id="8fcf3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8fcf3-105">SYNTAX</span></span>

```
Set-LogProperties [-LogDetails] <LogDetails> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="8fcf3-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8fcf3-106">DESCRIPTION</span></span>

<span data-ttu-id="8fcf3-107">Esse cmdlet altera as definições de configuração de um log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="8fcf3-107">This cmdlet changes the configuration settings of a Windows event log.</span></span> <span data-ttu-id="8fcf3-108">Esse cmdlet é usado pelos `Enable-PSTrace` `Disable-PSTrace` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="8fcf3-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

<span data-ttu-id="8fcf3-109">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="8fcf3-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="8fcf3-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8fcf3-110">EXAMPLES</span></span>

### <span data-ttu-id="8fcf3-111">Exemplo 1: alterar a configuração de retenção do log de eventos do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8fcf3-111">Example 1: Change the retention setting of the Windows PowerShell event log</span></span>

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

## <span data-ttu-id="8fcf3-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8fcf3-112">PARAMETERS</span></span>

### <span data-ttu-id="8fcf3-113">-Force</span><span class="sxs-lookup"><span data-stu-id="8fcf3-113">-Force</span></span>

<span data-ttu-id="8fcf3-114">Usado para forçar a alteração sem avisar.</span><span class="sxs-lookup"><span data-stu-id="8fcf3-114">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="8fcf3-115">-LogDetails</span><span class="sxs-lookup"><span data-stu-id="8fcf3-115">-LogDetails</span></span>

<span data-ttu-id="8fcf3-116">As definições de configuração atualizadas a serem atribuídas ao log de eventos.</span><span class="sxs-lookup"><span data-stu-id="8fcf3-116">The updated configuration settings to be assigned to the event log.</span></span>

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

### <span data-ttu-id="8fcf3-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8fcf3-117">CommonParameters</span></span>

<span data-ttu-id="8fcf3-118">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8fcf3-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8fcf3-119">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8fcf3-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8fcf3-120">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8fcf3-120">INPUTS</span></span>

### <span data-ttu-id="8fcf3-121">Microsoft. PowerShell. Diagnostics. LogDetails</span><span class="sxs-lookup"><span data-stu-id="8fcf3-121">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="8fcf3-122">Você deve passar um objeto **LogDetails** totalmente configurado para o `Set-LogProperties` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8fcf3-122">You must pass a fully configured **LogDetails** object to the `Set-LogProperties` cmdlet.</span></span>
<span data-ttu-id="8fcf3-123">Portanto, para alterar uma configuração, você deve usar `Get-LogProperties` para recuperar a configuração atual.</span><span class="sxs-lookup"><span data-stu-id="8fcf3-123">Therefore, to change one setting, you should use `Get-LogProperties` to retrieve the current configuration.</span></span>

## <span data-ttu-id="8fcf3-124">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8fcf3-124">OUTPUTS</span></span>

### <span data-ttu-id="8fcf3-125">System.Object</span><span class="sxs-lookup"><span data-stu-id="8fcf3-125">System.Object</span></span>

## <span data-ttu-id="8fcf3-126">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8fcf3-126">NOTES</span></span>

<span data-ttu-id="8fcf3-127">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="8fcf3-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="8fcf3-128">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8fcf3-128">RELATED LINKS</span></span>

[<span data-ttu-id="8fcf3-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="8fcf3-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="8fcf3-130">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="8fcf3-130">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="8fcf3-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="8fcf3-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)
