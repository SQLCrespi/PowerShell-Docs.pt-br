---
ms.date: 03/22/2021
keywords: powershell, cmdlet
title: O que é o PowerShell?
description: Este artigo é uma introdução ao ambiente de script do PowerShell e seus recursos.
ms.openlocfilehash: 3e1c2cae4b8d6507057ee8136265710a8dfe74f3
ms.sourcegitcommit: 719debaed3cc32ba463b1d4cc56a491d8ecbce26
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "105029682"
---
# <a name="what-is-powershell"></a><span data-ttu-id="25b21-104">O que é o PowerShell?</span><span class="sxs-lookup"><span data-stu-id="25b21-104">What is PowerShell?</span></span>

<span data-ttu-id="25b21-105">O PowerShell é uma solução de automação de tarefas multiplataforma que consiste em um shell de linha de comando, em uma linguagem de script e uma estrutura de gerenciamento de configuração.</span><span class="sxs-lookup"><span data-stu-id="25b21-105">PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting language, and a configuration management framework.</span></span> <span data-ttu-id="25b21-106">O PowerShell pode ser executado no Windows, Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="25b21-106">PowerShell runs on Windows, Linux, and macOS.</span></span>

## <a name="shell"></a><span data-ttu-id="25b21-107">Shell</span><span class="sxs-lookup"><span data-stu-id="25b21-107">Shell</span></span>

<span data-ttu-id="25b21-108">O PowerShell é um shell de comando moderno que inclui os melhores recursos de outros shells populares.</span><span class="sxs-lookup"><span data-stu-id="25b21-108">PowerShell is modern command shell that includes the best features of other popular shells.</span></span> <span data-ttu-id="25b21-109">Ao contrário da maioria dos shells que só aceita e retorna texto, o PowerShell aceita e retorna objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="25b21-109">Unlike most shells that only accept and return text, PowerShell accepts and returns .NET objects.</span></span> <span data-ttu-id="25b21-110">O shell inclui os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="25b21-110">The shell includes the following features:</span></span>

- <span data-ttu-id="25b21-111">[Histórico][] de linha de comando robusto</span><span class="sxs-lookup"><span data-stu-id="25b21-111">Robust command-line [history][]</span></span>
- <span data-ttu-id="25b21-112">Previsão de comando e conclusão da guia (confira [about_PSReadLine][])</span><span class="sxs-lookup"><span data-stu-id="25b21-112">Tab completion and command prediction (See [about_PSReadLine][])</span></span>
- <span data-ttu-id="25b21-113">Suporte a [aliases][] de parâmetro e de comando</span><span class="sxs-lookup"><span data-stu-id="25b21-113">Supports command and parameter [aliases][]</span></span>
- <span data-ttu-id="25b21-114">[Pipeline][] para comandos de encadeamento</span><span class="sxs-lookup"><span data-stu-id="25b21-114">[Pipeline][] for chaining commands</span></span>
- <span data-ttu-id="25b21-115">Sistema de [ajuda][] no console, semelhante a páginas `man` UNIX</span><span class="sxs-lookup"><span data-stu-id="25b21-115">In-console [help][] system, similar to Unix `man` pages</span></span>

## <a name="scripting-language"></a><span data-ttu-id="25b21-116">Idioma do script</span><span class="sxs-lookup"><span data-stu-id="25b21-116">Scripting language</span></span>

<span data-ttu-id="25b21-117">Como uma linguagem de script, o PowerShell é normalmente usado para automatizar o gerenciamento de sistemas.</span><span class="sxs-lookup"><span data-stu-id="25b21-117">As a scripting language, PowerShell is commonly used for automating the management of systems.</span></span> <span data-ttu-id="25b21-118">Ele também é usado para compilar, testar e implantar soluções, geralmente em ambientes de CI/CD.</span><span class="sxs-lookup"><span data-stu-id="25b21-118">It is also used to build, test, and deploy solutions, often in CI/CD environments.</span></span> <span data-ttu-id="25b21-119">O PowerShell é criado no CLR (Common Language Runtime) do .NET.</span><span class="sxs-lookup"><span data-stu-id="25b21-119">PowerShell is built on the .NET Common Language Runtime (CLR).</span></span> <span data-ttu-id="25b21-120">Todas as entradas e saídas são objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="25b21-120">All inputs and outputs are .NET objects.</span></span> <span data-ttu-id="25b21-121">Não é necessário analisar a saída de texto para extrair informações da saída.</span><span class="sxs-lookup"><span data-stu-id="25b21-121">No need to parse text output to extract information from output.</span></span> <span data-ttu-id="25b21-122">A linguagem de script do PowerShell inclui os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="25b21-122">The PowerShell scripting language includes the following features:</span></span>

- <span data-ttu-id="25b21-123">Extensível por meio de [funções][], [classes][], [scripts][] e [módulos][]</span><span class="sxs-lookup"><span data-stu-id="25b21-123">Extensible through [functions][], [classes][], [scripts][], and [modules][]</span></span>
- <span data-ttu-id="25b21-124">[Sistema de formatação][formatting] extensível para saída fácil</span><span class="sxs-lookup"><span data-stu-id="25b21-124">Extensible [formatting system][formatting] for easy output</span></span>
- <span data-ttu-id="25b21-125">[Sistema de tipos][types] extensível para a criação de tipos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="25b21-125">Extensible [type system][types] for creating dynamic types</span></span>
- <span data-ttu-id="25b21-126">Suporte integrado para formatos de dados comuns como [CSV][], [JSON][] e [XML][]</span><span class="sxs-lookup"><span data-stu-id="25b21-126">Built-in support for common data formats like [CSV][], [JSON][], and [XML][]</span></span>

## <a name="configuration-management"></a><span data-ttu-id="25b21-127">Gerenciamento de configuração</span><span class="sxs-lookup"><span data-stu-id="25b21-127">Configuration management</span></span>

<span data-ttu-id="25b21-128">O [DSC][] (Desired State Configuration) do PowerShell é uma estrutura de gerenciamento no PowerShell que permite gerenciar a infraestrutura empresarial com a configuração como código.</span><span class="sxs-lookup"><span data-stu-id="25b21-128">PowerShell Desired State Configuration ([DSC][]) is a management framework in PowerShell that enables you to manage your enterprise infrastructure with configuration as code.</span></span> <span data-ttu-id="25b21-129">Com o DSC, você pode:</span><span class="sxs-lookup"><span data-stu-id="25b21-129">With DSC, you can:</span></span>

- <span data-ttu-id="25b21-130">Criar [configurações][] declarativas e scripts personalizados para implantações repetíveis</span><span class="sxs-lookup"><span data-stu-id="25b21-130">Create declarative [configurations][] and custom scripts for repeatable deployments</span></span>
- <span data-ttu-id="25b21-131">Impor definições de configuração e relatar sobre descompasso de configuração</span><span class="sxs-lookup"><span data-stu-id="25b21-131">Enforce configuration settings and report on configuration drift</span></span>
- <span data-ttu-id="25b21-132">Implantar a configuração usando modelos [push ou pull][push-pull]</span><span class="sxs-lookup"><span data-stu-id="25b21-132">Deploy configuration using [push or pull][push-pull] models</span></span>

## <a name="next-steps"></a><span data-ttu-id="25b21-133">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="25b21-133">Next steps</span></span>

### <a name="getting-started"></a><span data-ttu-id="25b21-134">Introdução</span><span class="sxs-lookup"><span data-stu-id="25b21-134">Getting started</span></span>

<span data-ttu-id="25b21-135">Você é novo no PowerShell e não sabe por onde começar?</span><span class="sxs-lookup"><span data-stu-id="25b21-135">Are you new to PowerShell and don't know where to start?</span></span> <span data-ttu-id="25b21-136">Confira estes recursos.</span><span class="sxs-lookup"><span data-stu-id="25b21-136">Take a look at these resources.</span></span>

- <span data-ttu-id="25b21-137">[Instalando o PowerShell][install]</span><span class="sxs-lookup"><span data-stu-id="25b21-137">[Installing PowerShell][install]</span></span>
- <span data-ttu-id="25b21-138">[Introdução ao PowerShell][PS101]</span><span class="sxs-lookup"><span data-stu-id="25b21-138">[PowerShell 101][PS101]</span></span>
- <span data-ttu-id="25b21-139">[Tutoriais de Bits do PowerShell][tutorials]</span><span class="sxs-lookup"><span data-stu-id="25b21-139">[PowerShell Bits tutorials][tutorials]</span></span>
- <span data-ttu-id="25b21-140">[Módulos do Learn do PowerShell][learn]</span><span class="sxs-lookup"><span data-stu-id="25b21-140">[PowerShell Learn modules][learn]</span></span>

### <a name="powershell-in-action"></a><span data-ttu-id="25b21-141">PowerShell em ação</span><span class="sxs-lookup"><span data-stu-id="25b21-141">PowerShell in action</span></span>

<span data-ttu-id="25b21-142">Confira como o PowerShell está sendo usado em diferentes cenários e diferentes plataformas.</span><span class="sxs-lookup"><span data-stu-id="25b21-142">Take a look at how PowerShell is being used in different scenarios and on different platforms.</span></span>

- <span data-ttu-id="25b21-143">[Comunicação remota do PowerShell por SSH][remoting]</span><span class="sxs-lookup"><span data-stu-id="25b21-143">[PowerShell remoting over SSH][remoting]</span></span>
- <span data-ttu-id="25b21-144">[Introdução ao Azure PowerShell][azure]</span><span class="sxs-lookup"><span data-stu-id="25b21-144">[Getting started with Azure PowerShell][azure]</span></span>
- <span data-ttu-id="25b21-145">[Criar um pipeline de CI/CD com o DSC][devops]</span><span class="sxs-lookup"><span data-stu-id="25b21-145">[Building a CI/CD pipeline with DSC][devops]</span></span>
- <span data-ttu-id="25b21-146">[Gerenciar o Microsoft Exchange][exchange]</span><span class="sxs-lookup"><span data-stu-id="25b21-146">[Managing Microsoft Exchange][exchange]</span></span>

<!-- link references -->

[história]: /powershell/module/microsoft.powershell.core/about/about_history
[history]: /powershell/module/microsoft.powershell.core/about/about_history
[about_PSReadLine]: /powershell/module/psreadline/about/about_psreadline
[aliases]: /powershell/module/microsoft.powershell.core/about/about_aliases
[Pipeline]: /powershell/module/microsoft.powershell.core/about/about_pipelines
[help]: /powershell/module/microsoft.powershell.core/get-help
[modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[funções]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced
[functions]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced
[classes]: /powershell/module/microsoft.powershell.core/about/about_classes
[scripts]: /powershell/module/microsoft.powershell.core/about/about_scripts
[formatting]: /powershell/module/microsoft.powershell.core/about/about_format.ps1xml
[types]: /powershell/module/microsoft.powershell.core/about/about_types.ps1xml
[CSV]: /powershell/module/microsoft.powershell.utility/convertfrom-csv
[JSON]: /powershell/module/microsoft.powershell.utility/convertfrom-json
[XML]: /powershell/module/microsoft.powershell.utility/convertto-xml
[configurações]: /powershell/scripting/dsc/configurations/configurations
[configurations]: /powershell/scripting/dsc/configurations/configurations
[DSC]: /powershell/scripting/dsc/overview/dscforengineers
[push-pull]: /powershell/scripting/dsc/pull-server/enactingconfigurations
[install]: /powershell/scripting/install/installing-powershell
[PS101]: /powershell/scripting/learn/ps101/00-introduction
[tutorials]: /powershell/scripting/learn/tutorials/00-introduction
[learn]: /learn/browse/?terms=PowerShell
[azure]: /powershell/azure/get-started-azureps
[devops]: /azure/devops/pipelines/release/dsc-cicd
[exchange]: /powershell/exchange/exchange-management-shell
[remoting]: /powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core
