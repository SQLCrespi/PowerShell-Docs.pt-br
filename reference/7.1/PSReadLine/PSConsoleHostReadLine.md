---
external help file: PSReadLine-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/psconsolehostreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSConsoleHostReadLine
ms.openlocfilehash: 10e79223801a32a2409de253daabe1019ae1b64b
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196594"
---
# <span data-ttu-id="efa8f-103">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="efa8f-103">PSConsoleHostReadLine</span></span>

## <span data-ttu-id="efa8f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="efa8f-104">SYNOPSIS</span></span>
<span data-ttu-id="efa8f-105">Essa função é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="efa8f-105">This function is the main entry point for PSReadLine.</span></span>

## <span data-ttu-id="efa8f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="efa8f-106">SYNTAX</span></span>

```
PSConsoleHostReadLine
```

## <span data-ttu-id="efa8f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="efa8f-107">DESCRIPTION</span></span>

<span data-ttu-id="efa8f-108">`PSConsoleHostReadLine` é o ponto de entrada principal para o módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="efa8f-108">`PSConsoleHostReadLine` is the main entry point for the PSReadLine module.</span></span> <span data-ttu-id="efa8f-109">O host do console do PowerShell carrega automaticamente o módulo PSReadLine e chama essa função.</span><span class="sxs-lookup"><span data-stu-id="efa8f-109">The PowerShell console host automatically loads the PSReadLine module and calls this function.</span></span> <span data-ttu-id="efa8f-110">Em condições normais de operação, essa função não se destina a ser usada na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="efa8f-110">Under normal operating conditions, this function is not intended to be used from the command line.</span></span>

<span data-ttu-id="efa8f-111">O ponto de extensão `PSConsoleHostReadLine` é especial para o host do console.</span><span class="sxs-lookup"><span data-stu-id="efa8f-111">The extension point `PSConsoleHostReadLine` is special to the console host.</span></span> <span data-ttu-id="efa8f-112">O host chama qualquer alias, função ou script com esse nome.</span><span class="sxs-lookup"><span data-stu-id="efa8f-112">The host calls any alias, function, or script with this name.</span></span> <span data-ttu-id="efa8f-113">PSReadLine define essa função para que ela seja chamada a partir do host do console.</span><span class="sxs-lookup"><span data-stu-id="efa8f-113">PSReadLine defines this function so that it is called from the console host.</span></span>

## <span data-ttu-id="efa8f-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="efa8f-114">EXAMPLES</span></span>

### <span data-ttu-id="efa8f-115">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="efa8f-115">Example 1</span></span>

<span data-ttu-id="efa8f-116">Esta função não se destina a ser usada na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="efa8f-116">This function is not intended to be used from the command line.</span></span>

## <span data-ttu-id="efa8f-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="efa8f-117">PARAMETERS</span></span>

## <span data-ttu-id="efa8f-118">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="efa8f-118">INPUTS</span></span>

### <span data-ttu-id="efa8f-119">Nenhum</span><span class="sxs-lookup"><span data-stu-id="efa8f-119">None</span></span>

## <span data-ttu-id="efa8f-120">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="efa8f-120">OUTPUTS</span></span>

### <span data-ttu-id="efa8f-121">Nenhum</span><span class="sxs-lookup"><span data-stu-id="efa8f-121">None</span></span>

## <span data-ttu-id="efa8f-122">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="efa8f-122">NOTES</span></span>

## <span data-ttu-id="efa8f-123">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="efa8f-123">RELATED LINKS</span></span>

[<span data-ttu-id="efa8f-124">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="efa8f-124">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

