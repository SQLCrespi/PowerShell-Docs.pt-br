---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: da71d4ef896befaadd7ed64f9a013dc19508a54c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597192"
---
# <span data-ttu-id="14fb4-102">Módulo PSReadLine</span><span class="sxs-lookup"><span data-stu-id="14fb4-102">PSReadLine Module</span></span>

## <span data-ttu-id="14fb4-103">Descrição</span><span class="sxs-lookup"><span data-stu-id="14fb4-103">Description</span></span>

<span data-ttu-id="14fb4-104">O módulo PSReadLine contém cmdlets que permitem personalizar o ambiente de edição de linha de comando no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14fb4-104">The PSReadLine module contains cmdlets that let you customize the command-line editing environment in PowerShell.</span></span> <span data-ttu-id="14fb4-105">Estes artigos documentam o PSReadLine v 2.0.</span><span class="sxs-lookup"><span data-stu-id="14fb4-105">These articles documents PSReadLine v2.0.</span></span> <span data-ttu-id="14fb4-106">Esta versão é fornecida no PowerShell V6 e na atualização de outubro de 2018 do Windows 10 (Build 1809).</span><span class="sxs-lookup"><span data-stu-id="14fb4-106">This version ships in PowerShell v6 and the Windows 10 October 2018 Update (Build 1809).</span></span>

> [!NOTE]
> <span data-ttu-id="14fb4-107">A partir do PowerShell 7,0, o PowerShell ignora o carregamento automático de PSReadLine no Windows se um programa de leitor de tela for detectado.</span><span class="sxs-lookup"><span data-stu-id="14fb4-107">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="14fb4-108">Atualmente, o PSReadLine não funciona bem com os leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="14fb4-108">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="14fb4-109">A renderização e a formatação padrão do PowerShell 7,0 no Windows funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="14fb4-109">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="14fb4-110">Você pode carregar o módulo manualmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="14fb4-110">You can manually load the module if necessary.</span></span>

## <span data-ttu-id="14fb4-111">Cmdlets PSReadLine</span><span class="sxs-lookup"><span data-stu-id="14fb4-111">PSReadLine Cmdlets</span></span>

### [<span data-ttu-id="14fb4-112">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="14fb4-112">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="14fb4-113">O ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="14fb4-113">The main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="14fb4-114">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="14fb4-114">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)
<span data-ttu-id="14fb4-115">Obtém as funções de chave associadas para o módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="14fb4-115">Gets the bound key functions for the PSReadLine module.</span></span>

### [<span data-ttu-id="14fb4-116">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="14fb4-116">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)
<span data-ttu-id="14fb4-117">Obtém valores para as opções que podem ser configuradas.</span><span class="sxs-lookup"><span data-stu-id="14fb4-117">Gets values for the options that can be configured.</span></span>

### [<span data-ttu-id="14fb4-118">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="14fb4-118">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="14fb4-119">Essa função é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="14fb4-119">This function is the main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="14fb4-120">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="14fb4-120">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)
<span data-ttu-id="14fb4-121">Remove uma associação de chave.</span><span class="sxs-lookup"><span data-stu-id="14fb4-121">Removes a key binding.</span></span>

### [<span data-ttu-id="14fb4-122">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="14fb4-122">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
<span data-ttu-id="14fb4-123">Associa as chaves às funções de manipulador de chave definidas pelo usuário ou PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="14fb4-123">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

### [<span data-ttu-id="14fb4-124">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="14fb4-124">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
<span data-ttu-id="14fb4-125">Personaliza o comportamento da edição de linha de comando no **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="14fb4-125">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

