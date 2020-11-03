---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: ''
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-host?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Host
ms.openlocfilehash: d4fd2908f5577765d4f453589c5ac325723e2e3a
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192622"
---
# <span data-ttu-id="3371b-103">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="3371b-103">Clear-Host</span></span>

## <span data-ttu-id="3371b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3371b-104">SYNOPSIS</span></span>

<span data-ttu-id="3371b-105">Limpa o visor no programa host.</span><span class="sxs-lookup"><span data-stu-id="3371b-105">Clears the display in the host program.</span></span>

## <span data-ttu-id="3371b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3371b-106">SYNTAX</span></span>

```
Clear-Host [<CommonParameters>]
```

## <span data-ttu-id="3371b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3371b-107">DESCRIPTION</span></span>

<span data-ttu-id="3371b-108">A `Clear-Host` função remove todo o texto da exibição atual, incluindo comandos e saídas que podem ter acumulado.</span><span class="sxs-lookup"><span data-stu-id="3371b-108">The `Clear-Host` function removes all text from the current display, including commands and output that might have accumulated.</span></span> <span data-ttu-id="3371b-109">Ao concluir, ela exibe o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="3371b-109">When complete, it displays the command prompt.</span></span> <span data-ttu-id="3371b-110">Você pode usar o nome da função ou seu alias, `cls` .</span><span class="sxs-lookup"><span data-stu-id="3371b-110">You can use the function name or its alias, `cls`.</span></span>

<span data-ttu-id="3371b-111">`Clear-Host` afeta apenas a exibição atual.</span><span class="sxs-lookup"><span data-stu-id="3371b-111">`Clear-Host` affects only the current display.</span></span> <span data-ttu-id="3371b-112">Ele não exclui os resultados salvos nem remove quaisquer itens da sessão.</span><span class="sxs-lookup"><span data-stu-id="3371b-112">It does not delete saved results or remove any items from the session.</span></span> <span data-ttu-id="3371b-113">Os itens de sessão específica, como variáveis e funções, não são afetados por essa função.</span><span class="sxs-lookup"><span data-stu-id="3371b-113">Session-specific items, such as variables and functions, are not affected by this function.</span></span>

<span data-ttu-id="3371b-114">Como o comportamento da `Clear-Host` função é determinado pelo programa host, o `Clear-Host` pode funcionar de forma diferente em programas host diferentes.</span><span class="sxs-lookup"><span data-stu-id="3371b-114">Because the behavior of the `Clear-Host` function is determined by the host program, `Clear-Host` might work differently in different host programs.</span></span>

## <span data-ttu-id="3371b-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3371b-115">EXAMPLES</span></span>

### <span data-ttu-id="3371b-116">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="3371b-116">Example 1</span></span>

```
# Before

PS C:\> Get-Process

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    843      33    14428      22556    99    17.41   1688 CcmExec
     44       6     2196       4964    52     0.23    692 conhost
    646      12     2332       4896    49     1.12    388 csrss
    189      11     2860       7084   114     0.66   2896 csrss
     78      11     1876       4008    42     0.22   4000 csrss
     76       7     1848       5064    54     0.08   1028 dwm
    610      41    23952      44048   208     4.40   2080 explorer
      0       0        0         24     0               0 Idle
    182      32     7692      15980    91     0.23   3056 LogonUI
    186      25     7832      16068    91     0.27   3996 LogonUI
   1272      32    11512      20432    58    25.07    548 lsass
    267      10     3536       6736    34     0.80    556 lsm
    137      17     3520       7472    61     0.05   1220 msdtc
    447      31    70316      84476   201 1,429.67    836 MsMpEng
    265      18     7136      15628   134     2.20   3544 msseces
    248      16     6476       4076    76     0.22   1592 NisSrv
    368      25    61312      65508   614     1.78    848 powershell
    101       8     2304       6624    70     0.64   3648 rdpclip
    258      15     6804      12156    50     2.65    536 services
...

PS C:\> cls
#After

PS C:>
```

<span data-ttu-id="3371b-117">Esse comando usa o `cls` alias de `Clear-Host` para limpar a exibição atual.</span><span class="sxs-lookup"><span data-stu-id="3371b-117">This command uses the `cls` alias of `Clear-Host` to clear the current display.</span></span>

## <span data-ttu-id="3371b-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3371b-118">PARAMETERS</span></span>

### <span data-ttu-id="3371b-119">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3371b-119">CommonParameters</span></span>
<span data-ttu-id="3371b-120">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3371b-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3371b-121">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3371b-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3371b-122">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3371b-122">INPUTS</span></span>

### <span data-ttu-id="3371b-123">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3371b-123">None</span></span>

<span data-ttu-id="3371b-124">Não é possível canalizar a entrada para `Clear-Host` .</span><span class="sxs-lookup"><span data-stu-id="3371b-124">You cannot pipe input to `Clear-Host`.</span></span>

## <span data-ttu-id="3371b-125">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3371b-125">OUTPUTS</span></span>

### <span data-ttu-id="3371b-126">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3371b-126">None</span></span>

<span data-ttu-id="3371b-127">`Clear-Host` não gera nenhuma saída</span><span class="sxs-lookup"><span data-stu-id="3371b-127">`Clear-Host` does not generate any output</span></span>

## <span data-ttu-id="3371b-128">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3371b-128">NOTES</span></span>

<span data-ttu-id="3371b-129">`Clear-Host` é uma função simples, não uma função avançada.</span><span class="sxs-lookup"><span data-stu-id="3371b-129">`Clear-Host` is a simple function, not an advanced function.</span></span> <span data-ttu-id="3371b-130">Dessa forma, você não pode usar parâmetros comuns, como **debug** , em um `Clear-Host` comando.</span><span class="sxs-lookup"><span data-stu-id="3371b-130">As such, you cannot use common parameters, such as **Debug** , in a `Clear-Host` command.</span></span>

## <span data-ttu-id="3371b-131">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3371b-131">RELATED LINKS</span></span>

[<span data-ttu-id="3371b-132">Get-Host</span><span class="sxs-lookup"><span data-stu-id="3371b-132">Get-Host</span></span>](../Microsoft.PowerShell.Utility/Get-Host.md)

[<span data-ttu-id="3371b-133">Out-Host</span><span class="sxs-lookup"><span data-stu-id="3371b-133">Out-Host</span></span>](Out-Host.md)

[<span data-ttu-id="3371b-134">Read-Host</span><span class="sxs-lookup"><span data-stu-id="3371b-134">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)

[<span data-ttu-id="3371b-135">Write-Host</span><span class="sxs-lookup"><span data-stu-id="3371b-135">Write-Host</span></span>](../Microsoft.PowerShell.Utility/Write-Host.md)
