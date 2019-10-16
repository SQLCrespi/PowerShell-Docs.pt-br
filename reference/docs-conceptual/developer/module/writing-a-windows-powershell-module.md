---
title: Escrevendo um módulo do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bfbccc5b-2b2b-432a-a971-9f8ab503cdc3
caps.latest.revision: 17
ms.openlocfilehash: 0b7263ea19745e902fff04b993933e443d4d6333
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360615"
---
# <a name="writing-a-windows-powershell-module"></a><span data-ttu-id="5b0da-102">Escrever um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b0da-102">Writing a Windows PowerShell Module</span></span>

<span data-ttu-id="5b0da-103">Este documento foi escrito para administradores, desenvolvedores de scripts e desenvolvedores de cmdlets que precisam empacotar e distribuir seus cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b0da-103">This document is written for administrators, script developers, and cmdlet developers who need to package and distribute their Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5b0da-104">Usando os módulos do Windows PowerShell, você pode empacotar e distribuir suas soluções do Windows PowerShell sem usar uma linguagem compilada.</span><span class="sxs-lookup"><span data-stu-id="5b0da-104">By using Windows PowerShell modules, you can package and distribute your Windows PowerShell solutions without using a compiled language.</span></span>

<span data-ttu-id="5b0da-105">Os módulos do Windows PowerShell permitem particionar, organizar e abstrair o código do Windows PowerShell em unidades independentes e reutilizáveis.</span><span class="sxs-lookup"><span data-stu-id="5b0da-105">Windows PowerShell modules enable you to partition, organize, and abstract your Windows PowerShell code into self-contained, reusable units.</span></span> <span data-ttu-id="5b0da-106">Com essas unidades reutilizáveis, você pode facilmente compartilhar seus módulos diretamente com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="5b0da-106">With these reusable units, you can easily share your modules directly with others.</span></span> <span data-ttu-id="5b0da-107">Se você for um desenvolvedor de scripts, também poderá reempacotar módulos de terceiros para criar aplicativos personalizados baseados em script.</span><span class="sxs-lookup"><span data-stu-id="5b0da-107">If you are a script developer, you can also repackage third-party modules to create custom script-based applications.</span></span> <span data-ttu-id="5b0da-108">Módulos, semelhantes a módulos em outras linguagens de script, como Perl e Python, permitem soluções de script prontas para produção que usam componentes reutilizáveis e redistribuíveis, com o benefício adicional de permitir que você reempacote e abstraia vários componentes para Crie soluções personalizadas.</span><span class="sxs-lookup"><span data-stu-id="5b0da-108">Modules, similar to modules in other scripting languages such as Perl and Python, enable production-ready scripting solutions that use reusable, redistributable components, with the added benefit of enabling you to repackage and abstract multiple components to create custom solutions.</span></span>

<span data-ttu-id="5b0da-109">No seu mais básico, o Windows PowerShell tratará qualquer código de script válido do Windows PowerShell salvo em um arquivo. psm1 como um módulo.</span><span class="sxs-lookup"><span data-stu-id="5b0da-109">At their most basic, Windows PowerShell will treat any valid Windows PowerShell script code saved in a .psm1 file as a module.</span></span> <span data-ttu-id="5b0da-110">O PowerShell também tratará automaticamente qualquer assembly de cmdlet binário como um módulo.</span><span class="sxs-lookup"><span data-stu-id="5b0da-110">PowerShell will also automatically treat any binary cmdlet assembly as a module.</span></span> <span data-ttu-id="5b0da-111">No entanto, você também pode usar um módulo (ou mais especificamente um manifesto de módulo) para agrupar uma solução inteira.</span><span class="sxs-lookup"><span data-stu-id="5b0da-111">However, you can also use a module (or more specifically, a module manifest) to bundle an entire solution together.</span></span> <span data-ttu-id="5b0da-112">Os cenários a seguir descrevem usos típicos para módulos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b0da-112">The following scenarios describe typical uses for Windows PowerShell modules.</span></span>

### <a name="libraries"></a><span data-ttu-id="5b0da-113">Bibliotecas</span><span class="sxs-lookup"><span data-stu-id="5b0da-113">Libraries</span></span>

<span data-ttu-id="5b0da-114">Os módulos podem ser usados para empacotar e distribuir bibliotecas coesas de funções que executam tarefas comuns.</span><span class="sxs-lookup"><span data-stu-id="5b0da-114">Modules can be used to package and distribute cohesive libraries of functions that perform common tasks.</span></span> <span data-ttu-id="5b0da-115">Normalmente, os nomes dessas funções compartilham um ou mais substantivos que refletem a tarefa comum para a qual são usados.</span><span class="sxs-lookup"><span data-stu-id="5b0da-115">Typically, the names of these functions share one or more nouns that reflect the common task that they are used for.</span></span> <span data-ttu-id="5b0da-116">Essas funções também podem ser semelhantes a .NET Framework classes, pois podem ter membros públicos e privados.</span><span class="sxs-lookup"><span data-stu-id="5b0da-116">These functions can also be similar to .NET Framework classes in that they can have public and private members.</span></span> <span data-ttu-id="5b0da-117">Por exemplo, uma biblioteca pode conter um conjunto de funções para transferências de arquivos.</span><span class="sxs-lookup"><span data-stu-id="5b0da-117">For example, a library can contain a set of functions for file transfers.</span></span> <span data-ttu-id="5b0da-118">Nesse caso, o substantivo que reflete a tarefa comum pode ser "File".</span><span class="sxs-lookup"><span data-stu-id="5b0da-118">In this case, the noun reflecting the common task might be "file."</span></span>

### <a name="configuration"></a><span data-ttu-id="5b0da-119">Configuração</span><span class="sxs-lookup"><span data-stu-id="5b0da-119">Configuration</span></span>

<span data-ttu-id="5b0da-120">Os módulos podem ser usados para personalizar seu ambiente adicionando cmdlets, provedores, funções e variáveis específicos.</span><span class="sxs-lookup"><span data-stu-id="5b0da-120">Modules can be used to customize your environment by adding specific cmdlets, providers, functions, and variables.</span></span>

### <a name="compiled-code-development-and-distribution"></a><span data-ttu-id="5b0da-121">Desenvolvimento e distribuição de código compilados</span><span class="sxs-lookup"><span data-stu-id="5b0da-121">Compiled Code Development and Distribution</span></span>

<span data-ttu-id="5b0da-122">Os desenvolvedores de cmdlets e provedores podem usar módulos para testar e distribuir seu código compilado sem a necessidade de criar snap-ins. Eles podem importar o assembly que contém o código compilado como um módulo (um módulo binário) sem a necessidade de criar e registrar snap-ins.</span><span class="sxs-lookup"><span data-stu-id="5b0da-122">Cmdlet and provider developers can use modules to test and distribute their compiled code without needing to create snap-ins. They can import the assembly that contains the compiled code as a module (a binary module) without needing to create and register snap-ins.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b0da-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5b0da-123">See Also</span></span>

[<span data-ttu-id="5b0da-124">Noções básicas sobre um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b0da-124">Understanding a Windows PowerShell Module</span></span>](./understanding-a-windows-powershell-module.md)

[<span data-ttu-id="5b0da-125">Como escrever um módulo de script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b0da-125">How to Write a PowerShell Script Module</span></span>](./how-to-write-a-powershell-script-module.md)

[<span data-ttu-id="5b0da-126">Como escrever um módulo binário do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b0da-126">How to Write a PowerShell Binary Module</span></span>](./how-to-write-a-powershell-binary-module.md)

[<span data-ttu-id="5b0da-127">Como escrever um manifesto de módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b0da-127">How to Write a PowerShell Module Manifest</span></span>](how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="5b0da-128">Modificando o caminho de instalação do PSModulePath</span><span class="sxs-lookup"><span data-stu-id="5b0da-128">Modifying the PSModulePath Installation Path</span></span>](./modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="5b0da-129">Importando um módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b0da-129">Importing a PowerShell Module</span></span>](./importing-a-powershell-module.md)

[<span data-ttu-id="5b0da-130">Instalando um módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b0da-130">Installing a PowerShell Module</span></span>](./installing-a-powershell-module.md)
