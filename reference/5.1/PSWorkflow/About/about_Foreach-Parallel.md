---
description: Descreve a `ForEach -Parallel` construção de linguagem no fluxo de trabalho do Windows PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_foreach-parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach paralelo
ms.openlocfilehash: 1012b45396b65d424dacac067c2af8d3b6823f92
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195811"
---
# <a name="about-foreach-parallel"></a><span data-ttu-id="38129-104">Sobre Foreach-Parallel</span><span class="sxs-lookup"><span data-stu-id="38129-104">About Foreach-Parallel</span></span>

## <a name="short-description"></a><span data-ttu-id="38129-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="38129-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="38129-106">Descreve a `ForEach -Parallel` construção de linguagem no fluxo de trabalho do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38129-106">Describes the `ForEach -Parallel` language construct in Windows PowerShell Workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="38129-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="38129-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="38129-108">O parâmetro **Parallel** da `ForEach` palavra-chave executa os comandos em um bloco de `ForEach` script uma vez para cada item em uma coleção especificada.</span><span class="sxs-lookup"><span data-stu-id="38129-108">The **Parallel** parameter of the `ForEach` keyword runs the commands in a `ForEach` script block once for each item in a specified collection.</span></span>

<span data-ttu-id="38129-109">Os itens na coleção, como um disco em uma coleção de discos, são processados em paralelo.</span><span class="sxs-lookup"><span data-stu-id="38129-109">The items in the collection, such as a disk in a collection of disks, are processed in parallel.</span></span> <span data-ttu-id="38129-110">Os comandos no bloco de script são executados em sequência em cada item da coleção.</span><span class="sxs-lookup"><span data-stu-id="38129-110">The commands in the script block run sequentially on each item in the collection.</span></span>

<span data-ttu-id="38129-111">`ForEach -Parallel` é válido somente em um fluxo de trabalho do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38129-111">`ForEach -Parallel` is valid only in a Windows PowerShell Workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="38129-112">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="38129-112">SYNTAX</span></span>

```
ForEach -Parallel ($<item> in $<collection>)
{
    [<Activity1>]
    [<Activity2>]
    ...
}
```

### <a name="detailed-description"></a><span data-ttu-id="38129-113">DESCRIÇÃO DETALHADA</span><span class="sxs-lookup"><span data-stu-id="38129-113">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="38129-114">Assim como a instrução ForEach no Windows PowerShell, a variável que contém a coleção `$<collection>` deve ser definida antes da `ForEach -Parallel` instrução, mas a variável que representa o item atual `$<item>` é definida na `ForEach -Parallel` instrução.</span><span class="sxs-lookup"><span data-stu-id="38129-114">Like the ForEach statement in Windows PowerShell, the variable that contains collection `$<collection>` must be defined before the `ForEach -Parallel` statement, but the variable that represents the current item `$<item>` is defined in the `ForEach -Parallel` statement.</span></span>

<span data-ttu-id="38129-115">A `ForEach -Parallel` construção é diferente da `ForEach` palavra-chave e do parâmetro **paralelo** .</span><span class="sxs-lookup"><span data-stu-id="38129-115">The `ForEach -Parallel` construct is different from the `ForEach` keyword and the **Parallel** parameter.</span></span> <span data-ttu-id="38129-116">A `ForEach` palavra-chave processa os itens na coleção em sequência.</span><span class="sxs-lookup"><span data-stu-id="38129-116">The `ForEach` keyword processes the items in the collection in sequence.</span></span> <span data-ttu-id="38129-117">O parâmetro **Parallel** executa comandos em um bloco de script em paralelo.</span><span class="sxs-lookup"><span data-stu-id="38129-117">The **Parallel** parameter runs commands in a script block in parallel.</span></span> <span data-ttu-id="38129-118">Você pode colocar um bloco de script paralelo em um `ForEach -Parallel` bloco de script.</span><span class="sxs-lookup"><span data-stu-id="38129-118">You can enclose a Parallel script block in a `ForEach -Parallel` script block.</span></span>

<span data-ttu-id="38129-119">Os computadores de destino em um fluxo de trabalho, como aqueles especificados pelo parâmetro comum do fluxo de trabalho **PSComputerName** , são sempre processados em paralelo.</span><span class="sxs-lookup"><span data-stu-id="38129-119">The target computers in a workflow, such as those specified by the **PSComputerName** workflow common parameter, are always processed in parallel.</span></span>
<span data-ttu-id="38129-120">Você não precisa especificar a `ForEach -Parallel` palavra-chave para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="38129-120">You do not need to specify the `ForEach -Parallel` keyword for this purpose.</span></span>

### <a name="examples"></a><span data-ttu-id="38129-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="38129-121">EXAMPLES</span></span>

<span data-ttu-id="38129-122">O fluxo de trabalho a seguir contém uma `ForEach -Parallel` instrução que processa os discos que a `Get-Disk` atividade obtém.</span><span class="sxs-lookup"><span data-stu-id="38129-122">The following workflow contains a `ForEach -Parallel` statement that processes the disks that the `Get-Disk` activity gets.</span></span> <span data-ttu-id="38129-123">Os comandos no `ForEach -Parallel` bloco de script são executados em sequência, mas eles são executados nos discos em paralelo.</span><span class="sxs-lookup"><span data-stu-id="38129-123">The commands in the `ForEach -Parallel` script block run sequentially, but they run on the disks in parallel.</span></span> <span data-ttu-id="38129-124">Os discos podem ser processados simultaneamente e em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="38129-124">The disks might be processed concurrently and in any order.</span></span>

```powershell
workflow Test-Workflow
{
    $Disks = Get-Disk

    # The disks are processed in parallel.
    ForEach -Parallel ($Disk in $Disks)
    {
        # The commands run sequentially on each disk.
        $DiskPath = $Disk.Path
        $Disk | Initialize-Disk
        Set-Disk -Path $DiskPath
    }
}

workflow Test-Workflow
{
    #Run commands in parallel.
    Parallel
    {
        Get-Process
        Get-Service
    }

   $Disks = Get-Disk

   # The disks are processed in parallel.
   ForEach -Parallel ($Disk in $Disks)
   {
       # The commands run in parallel on each disk.
       Parallel
       {
           Initialize-Disk
           InlineScript {.\Get-DiskInventory}
       }
   }
}
```

## <a name="see-also"></a><span data-ttu-id="38129-125">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="38129-125">SEE ALSO</span></span>

[<span data-ttu-id="38129-126">Writing a Script Workflow</span><span class="sxs-lookup"><span data-stu-id="38129-126">Writing a Script Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)

[<span data-ttu-id="38129-127">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="38129-127">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_ForEach.md)

[<span data-ttu-id="38129-128">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="38129-128">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="38129-129">about_Parallel</span><span class="sxs-lookup"><span data-stu-id="38129-129">about_Parallel</span></span>](about_Parallel.md)

[<span data-ttu-id="38129-130">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="38129-130">about_Workflows</span></span>](about_Workflows.md)
