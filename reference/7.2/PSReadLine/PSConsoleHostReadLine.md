---
external help file: PSReadLine-help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/psconsolehostreadline?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSConsoleHostReadLine
ms.openlocfilehash: e02f06137395e187cfe86eb1aeb4b30dbb3f09f1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597613"
---
# <span data-ttu-id="736f5-102">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="736f5-102">PSConsoleHostReadLine</span></span>

## <span data-ttu-id="736f5-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="736f5-103">SYNOPSIS</span></span>
<span data-ttu-id="736f5-104">Essa função é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="736f5-104">This function is the main entry point for PSReadLine.</span></span>

## <span data-ttu-id="736f5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="736f5-105">SYNTAX</span></span>

```
PSConsoleHostReadLine
```

## <span data-ttu-id="736f5-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="736f5-106">DESCRIPTION</span></span>

<span data-ttu-id="736f5-107">`PSConsoleHostReadLine` é o ponto de entrada principal para o módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="736f5-107">`PSConsoleHostReadLine` is the main entry point for the PSReadLine module.</span></span> <span data-ttu-id="736f5-108">O host do console do PowerShell carrega automaticamente o módulo PSReadLine e chama essa função.</span><span class="sxs-lookup"><span data-stu-id="736f5-108">The PowerShell console host automatically loads the PSReadLine module and calls this function.</span></span> <span data-ttu-id="736f5-109">Em condições normais de operação, essa função não se destina a ser usada na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="736f5-109">Under normal operating conditions, this function is not intended to be used from the command line.</span></span>

<span data-ttu-id="736f5-110">O ponto de extensão `PSConsoleHostReadLine` é especial para o host do console.</span><span class="sxs-lookup"><span data-stu-id="736f5-110">The extension point `PSConsoleHostReadLine` is special to the console host.</span></span> <span data-ttu-id="736f5-111">O host chama qualquer alias, função ou script com esse nome.</span><span class="sxs-lookup"><span data-stu-id="736f5-111">The host calls any alias, function, or script with this name.</span></span> <span data-ttu-id="736f5-112">PSReadLine define essa função para que ela seja chamada a partir do host do console.</span><span class="sxs-lookup"><span data-stu-id="736f5-112">PSReadLine defines this function so that it is called from the console host.</span></span>

## <span data-ttu-id="736f5-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="736f5-113">EXAMPLES</span></span>

### <span data-ttu-id="736f5-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="736f5-114">Example 1</span></span>

<span data-ttu-id="736f5-115">Esta função não se destina a ser usada na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="736f5-115">This function is not intended to be used from the command line.</span></span>

## <span data-ttu-id="736f5-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="736f5-116">PARAMETERS</span></span>

## <span data-ttu-id="736f5-117">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="736f5-117">INPUTS</span></span>

### <span data-ttu-id="736f5-118">Nenhum</span><span class="sxs-lookup"><span data-stu-id="736f5-118">None</span></span>

## <span data-ttu-id="736f5-119">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="736f5-119">OUTPUTS</span></span>

### <span data-ttu-id="736f5-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="736f5-120">None</span></span>

## <span data-ttu-id="736f5-121">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="736f5-121">NOTES</span></span>

## <span data-ttu-id="736f5-122">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="736f5-122">RELATED LINKS</span></span>

[<span data-ttu-id="736f5-123">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="736f5-123">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

