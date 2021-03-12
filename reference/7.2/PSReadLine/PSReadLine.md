---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: 9425f72ce4002fa871ef6b687d76f92ddf6b489e
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103193903"
---
# <span data-ttu-id="b1e38-102">Módulo PSReadLine</span><span class="sxs-lookup"><span data-stu-id="b1e38-102">PSReadLine Module</span></span>

## <span data-ttu-id="b1e38-103">Descrição</span><span class="sxs-lookup"><span data-stu-id="b1e38-103">Description</span></span>

<span data-ttu-id="b1e38-104">O módulo PSReadLine contém cmdlets que permitem personalizar o ambiente de edição de linha de comando no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1e38-104">The PSReadLine module contains cmdlets that let you customize the command-line editing environment in PowerShell.</span></span> <span data-ttu-id="b1e38-105">Estes artigos documentam a versão beta atual do PSReadLine v 2.2.0.</span><span class="sxs-lookup"><span data-stu-id="b1e38-105">These articles document the current beta version of PSReadLine v2.2.0.</span></span>

> [!NOTE]
> <span data-ttu-id="b1e38-106">A partir do PowerShell 7,0, o PowerShell ignora o carregamento automático de PSReadLine no Windows se um programa de leitor de tela for detectado.</span><span class="sxs-lookup"><span data-stu-id="b1e38-106">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="b1e38-107">Atualmente, o PSReadLine não funciona bem com os leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="b1e38-107">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="b1e38-108">A renderização e a formatação padrão do PowerShell 7,0 no Windows funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="b1e38-108">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="b1e38-109">Você pode carregar o módulo manualmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="b1e38-109">You can manually load the module if necessary.</span></span>

## <span data-ttu-id="b1e38-110">Cmdlets PSReadLine</span><span class="sxs-lookup"><span data-stu-id="b1e38-110">PSReadLine Cmdlets</span></span>

### [<span data-ttu-id="b1e38-111">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="b1e38-111">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="b1e38-112">O ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="b1e38-112">The main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="b1e38-113">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="b1e38-113">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)
<span data-ttu-id="b1e38-114">Obtém as funções de chave associadas para o módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="b1e38-114">Gets the bound key functions for the PSReadLine module.</span></span>

### [<span data-ttu-id="b1e38-115">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="b1e38-115">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)
<span data-ttu-id="b1e38-116">Obtém valores para as opções que podem ser configuradas.</span><span class="sxs-lookup"><span data-stu-id="b1e38-116">Gets values for the options that can be configured.</span></span>

### [<span data-ttu-id="b1e38-117">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="b1e38-117">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="b1e38-118">Essa função é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="b1e38-118">This function is the main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="b1e38-119">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="b1e38-119">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)
<span data-ttu-id="b1e38-120">Remove uma associação de chave.</span><span class="sxs-lookup"><span data-stu-id="b1e38-120">Removes a key binding.</span></span>

### [<span data-ttu-id="b1e38-121">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="b1e38-121">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
<span data-ttu-id="b1e38-122">Associa as chaves às funções de manipulador de chave definidas pelo usuário ou PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="b1e38-122">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

### [<span data-ttu-id="b1e38-123">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="b1e38-123">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
<span data-ttu-id="b1e38-124">Personaliza o comportamento da edição de linha de comando no **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="b1e38-124">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

