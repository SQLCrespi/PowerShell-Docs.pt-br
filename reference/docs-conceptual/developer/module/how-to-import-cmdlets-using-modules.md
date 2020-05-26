---
title: Como importar cmdlets usando módulos | Microsoft Docs
ms.custom: ''
ms.date: 08/28/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41d9e5f-de6f-47b7-9601-c108609320d0
caps.latest.revision: 8
ms.openlocfilehash: 840c5bc92d718ec4e54d864dc5e012cd33f83905
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811315"
---
# <a name="how-to-import-cmdlets-using-modules"></a><span data-ttu-id="53bd4-102">Como importar cmdlets por meio de módulos</span><span class="sxs-lookup"><span data-stu-id="53bd4-102">How to Import Cmdlets Using Modules</span></span>

<span data-ttu-id="53bd4-103">Este artigo descreve como importar cmdlets para uma sessão do PowerShell usando um módulo binário.</span><span class="sxs-lookup"><span data-stu-id="53bd4-103">This article describes how to import cmdlets to a PowerShell session by using a binary module.</span></span>

> [!NOTE]
> <span data-ttu-id="53bd4-104">Os membros de módulos podem incluir cmdlets, provedores, funções, variáveis, aliases e muito mais.</span><span class="sxs-lookup"><span data-stu-id="53bd4-104">The members of modules can include cmdlets, providers, functions, variables, aliases, and much more.</span></span> <span data-ttu-id="53bd4-105">Os snap-ins podem conter apenas cmdlets e provedores.</span><span class="sxs-lookup"><span data-stu-id="53bd4-105">Snap-ins can contain only cmdlets and providers.</span></span>

## <a name="how-to-load-cmdlets-using-a-module"></a><span data-ttu-id="53bd4-106">Como carregar cmdlets usando um módulo</span><span class="sxs-lookup"><span data-stu-id="53bd4-106">How to load cmdlets using a module</span></span>

1. <span data-ttu-id="53bd4-107">Crie uma pasta de módulo que tenha o mesmo nome que o arquivo de assembly no qual os cmdlets são implementados.</span><span class="sxs-lookup"><span data-stu-id="53bd4-107">Create a module folder that has the same name as the assembly file in which the cmdlets are implemented.</span></span> <span data-ttu-id="53bd4-108">Neste procedimento, a pasta do módulo é criada na pasta do Windows `system32` .</span><span class="sxs-lookup"><span data-stu-id="53bd4-108">In this procedure, the module folder is created in the Windows `system32` folder.</span></span>

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

1. <span data-ttu-id="53bd4-109">Verifique se a `PSModulePath` variável de ambiente inclui o caminho para a nova pasta do módulo.</span><span class="sxs-lookup"><span data-stu-id="53bd4-109">Make sure that the `PSModulePath` environment variable includes the path to your new module folder.</span></span> <span data-ttu-id="53bd4-110">Por padrão, a pasta do sistema já foi adicionada à `PSModulePath` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="53bd4-110">By default, the system folder is already added to the `PSModulePath` environment variable.</span></span> <span data-ttu-id="53bd4-111">Para exibir o `PSModulePath` , digite: `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="53bd4-111">To view the `PSModulePath`, type: `$env:PSModulePath`.</span></span>

1. <span data-ttu-id="53bd4-112">Copie o assembly do cmdlet para a pasta do módulo.</span><span class="sxs-lookup"><span data-stu-id="53bd4-112">Copy the cmdlet assembly into the module folder.</span></span>

1. <span data-ttu-id="53bd4-113">Adicione um arquivo de manifesto de módulo ( `.psd1` ) na pasta raiz do módulo.</span><span class="sxs-lookup"><span data-stu-id="53bd4-113">Add a module manifest file (`.psd1`) in the module's root folder.</span></span> <span data-ttu-id="53bd4-114">O PowerShell usa o manifesto do módulo para importar o módulo.</span><span class="sxs-lookup"><span data-stu-id="53bd4-114">PowerShell uses the module manifest to import your module.</span></span> <span data-ttu-id="53bd4-115">Para obter mais informações, consulte [como escrever um manifesto de módulo do PowerShell](../module/how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="53bd4-115">For more information, see [How to Write a PowerShell Module Manifest](../module/how-to-write-a-powershell-module-manifest.md).</span></span>

1. <span data-ttu-id="53bd4-116">Execute o seguinte comando para adicionar os cmdlets à sessão:</span><span class="sxs-lookup"><span data-stu-id="53bd4-116">Run the following command to add the cmdlets to the session:</span></span>

   `Import-Module [Module_Name]`

   <span data-ttu-id="53bd4-117">Esse procedimento pode ser usado para testar seus cmdlets.</span><span class="sxs-lookup"><span data-stu-id="53bd4-117">This procedure can be used to test your cmdlets.</span></span> <span data-ttu-id="53bd4-118">Ele adiciona todos os cmdlets no assembly à sessão.</span><span class="sxs-lookup"><span data-stu-id="53bd4-118">It adds all the cmdlets in the assembly to the session.</span></span> <span data-ttu-id="53bd4-119">Para obter mais informações sobre módulos, consulte [escrevendo um módulo do Windows PowerShell](../module/writing-a-windows-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="53bd4-119">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="53bd4-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="53bd4-120">See also</span></span>

[<span data-ttu-id="53bd4-121">Como escrever um manifesto de módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53bd4-121">How to Write a PowerShell Module Manifest</span></span>](../module/how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="53bd4-122">Importar um módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="53bd4-122">Importing a PowerShell Module</span></span>](../module/importing-a-powershell-module.md)

[<span data-ttu-id="53bd4-123">Importar-módulo</span><span class="sxs-lookup"><span data-stu-id="53bd4-123">Import-Module</span></span>](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[<span data-ttu-id="53bd4-124">Instalando módulos</span><span class="sxs-lookup"><span data-stu-id="53bd4-124">Installing Modules</span></span>](../module/installing-a-powershell-module.md)

[<span data-ttu-id="53bd4-125">Modificar o caminho de instalação PSModulePath</span><span class="sxs-lookup"><span data-stu-id="53bd4-125">Modifying the PSModulePath Installation Path</span></span>](../module/modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="53bd4-126">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53bd4-126">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)
