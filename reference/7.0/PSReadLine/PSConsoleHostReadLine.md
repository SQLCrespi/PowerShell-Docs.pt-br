---
external help file: PSReadLine-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/psconsolehostreadline?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSConsoleHostReadLine
ms.openlocfilehash: 47d97fd50294a0dda1064bad123dc17931f8a470
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196601"
---
# <span data-ttu-id="97a25-103">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="97a25-103">PSConsoleHostReadLine</span></span>

## <span data-ttu-id="97a25-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="97a25-104">SYNOPSIS</span></span>
<span data-ttu-id="97a25-105">Essa função é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="97a25-105">This function is the main entry point for PSReadLine.</span></span>

## <span data-ttu-id="97a25-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="97a25-106">SYNTAX</span></span>

```
PSConsoleHostReadLine
```

## <span data-ttu-id="97a25-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="97a25-107">DESCRIPTION</span></span>

<span data-ttu-id="97a25-108">`PSConsoleHostReadLine` é o ponto de entrada principal para o módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="97a25-108">`PSConsoleHostReadLine` is the main entry point for the PSReadLine module.</span></span> <span data-ttu-id="97a25-109">O host do console do PowerShell carrega automaticamente o módulo PSReadLine e chama essa função.</span><span class="sxs-lookup"><span data-stu-id="97a25-109">The PowerShell console host automatically loads the PSReadLine module and calls this function.</span></span> <span data-ttu-id="97a25-110">Em condições normais de operação, essa função não se destina a ser usada na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="97a25-110">Under normal operating conditions, this function is not intended to be used from the command line.</span></span>

<span data-ttu-id="97a25-111">O ponto de extensão `PSConsoleHostReadLine` é especial para o host do console.</span><span class="sxs-lookup"><span data-stu-id="97a25-111">The extension point `PSConsoleHostReadLine` is special to the console host.</span></span> <span data-ttu-id="97a25-112">O host chama qualquer alias, função ou script com esse nome.</span><span class="sxs-lookup"><span data-stu-id="97a25-112">The host calls any alias, function, or script with this name.</span></span> <span data-ttu-id="97a25-113">PSReadLine define essa função para que ela seja chamada a partir do host do console.</span><span class="sxs-lookup"><span data-stu-id="97a25-113">PSReadLine defines this function so that it is called from the console host.</span></span>

## <span data-ttu-id="97a25-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="97a25-114">EXAMPLES</span></span>

### <span data-ttu-id="97a25-115">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="97a25-115">Example 1</span></span>

<span data-ttu-id="97a25-116">Esta função não se destina a ser usada na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="97a25-116">This function is not intended to be used from the command line.</span></span>

## <span data-ttu-id="97a25-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="97a25-117">PARAMETERS</span></span>

## <span data-ttu-id="97a25-118">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="97a25-118">INPUTS</span></span>

### <span data-ttu-id="97a25-119">Nenhum</span><span class="sxs-lookup"><span data-stu-id="97a25-119">None</span></span>

## <span data-ttu-id="97a25-120">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="97a25-120">OUTPUTS</span></span>

### <span data-ttu-id="97a25-121">Nenhum</span><span class="sxs-lookup"><span data-stu-id="97a25-121">None</span></span>

## <span data-ttu-id="97a25-122">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="97a25-122">NOTES</span></span>

## <span data-ttu-id="97a25-123">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="97a25-123">RELATED LINKS</span></span>

[<span data-ttu-id="97a25-124">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="97a25-124">about_PSReadLine</span></span>](./About/about_PSReadLine.md)
