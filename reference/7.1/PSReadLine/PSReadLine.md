---
Download Help Link: https://aka.ms/powershell71-help
Help Version: 7.1.0.0
keywords: powershell
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: 3adfa4be7aae03120d2334a57c39d7e6351bcb16
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103196204"
---
# <span data-ttu-id="ab191-103">Módulo PSReadLine</span><span class="sxs-lookup"><span data-stu-id="ab191-103">PSReadLine Module</span></span>

## <span data-ttu-id="ab191-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="ab191-104">Description</span></span>

<span data-ttu-id="ab191-105">O módulo PSReadLine contém cmdlets que permitem personalizar o ambiente de edição de linha de comando no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab191-105">The PSReadLine module contains cmdlets that let you customize the command-line editing environment in PowerShell.</span></span> <span data-ttu-id="ab191-106">O PowerShell 7,1 foi fornecido com o PSReadLine v 2.1.</span><span class="sxs-lookup"><span data-stu-id="ab191-106">PowerShell 7.1 shipped with PSReadLine v2.1.</span></span> <span data-ttu-id="ab191-107">Estes artigos documentam o PSReadLine v 2.1.</span><span class="sxs-lookup"><span data-stu-id="ab191-107">These articles document PSReadLine v2.1.</span></span>

> [!NOTE]
> <span data-ttu-id="ab191-108">A partir do PowerShell 7,0, o PowerShell ignora o carregamento automático de PSReadLine no Windows se um programa de leitor de tela for detectado.</span><span class="sxs-lookup"><span data-stu-id="ab191-108">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="ab191-109">Atualmente, o PSReadLine não funciona bem com os leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="ab191-109">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="ab191-110">A renderização e a formatação padrão do PowerShell 7,0 no Windows funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="ab191-110">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="ab191-111">Você pode carregar o módulo manualmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ab191-111">You can manually load the module if necessary.</span></span>

## <span data-ttu-id="ab191-112">Cmdlets PSReadLine</span><span class="sxs-lookup"><span data-stu-id="ab191-112">PSReadLine Cmdlets</span></span>

### [<span data-ttu-id="ab191-113">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="ab191-113">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="ab191-114">O ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="ab191-114">The main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="ab191-115">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="ab191-115">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)
<span data-ttu-id="ab191-116">Obtém as funções de chave associadas para o módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="ab191-116">Gets the bound key functions for the PSReadLine module.</span></span>

### [<span data-ttu-id="ab191-117">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="ab191-117">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)
<span data-ttu-id="ab191-118">Obtém valores para as opções que podem ser configuradas.</span><span class="sxs-lookup"><span data-stu-id="ab191-118">Gets values for the options that can be configured.</span></span>

### [<span data-ttu-id="ab191-119">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="ab191-119">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="ab191-120">Essa função é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="ab191-120">This function is the main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="ab191-121">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="ab191-121">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)
<span data-ttu-id="ab191-122">Remove uma associação de chave.</span><span class="sxs-lookup"><span data-stu-id="ab191-122">Removes a key binding.</span></span>

### [<span data-ttu-id="ab191-123">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="ab191-123">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
<span data-ttu-id="ab191-124">Associa as chaves às funções de manipulador de chave definidas pelo usuário ou PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="ab191-124">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

### [<span data-ttu-id="ab191-125">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="ab191-125">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
<span data-ttu-id="ab191-126">Personaliza o comportamento da edição de linha de comando no **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="ab191-126">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

