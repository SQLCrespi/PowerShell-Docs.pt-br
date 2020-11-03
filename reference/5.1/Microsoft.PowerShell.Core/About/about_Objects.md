---
description: Fornece informações essenciais sobre objetos no Windows PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_objects?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Objects
ms.openlocfilehash: 678eececc2625bf02a706e8ef61c83056443a12f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196188"
---
# <a name="about-objects"></a><span data-ttu-id="b3256-104">Sobre objetos</span><span class="sxs-lookup"><span data-stu-id="b3256-104">About Objects</span></span>

## <a name="short-description"></a><span data-ttu-id="b3256-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="b3256-105">Short Description</span></span>

<span data-ttu-id="b3256-106">Fornece informações essenciais sobre objetos no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3256-106">Provides essential information about objects in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="b3256-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="b3256-107">Long Description</span></span>

<span data-ttu-id="b3256-108">Cada ação tomada no Windows PowerShell ocorre dentro do contexto de objetos.</span><span class="sxs-lookup"><span data-stu-id="b3256-108">Every action you take in Windows PowerShell occurs within the context of objects.</span></span> <span data-ttu-id="b3256-109">À medida que os dados são movidos de um comando para o outro, ele é movido como um ou mais objetos identificáveis.</span><span class="sxs-lookup"><span data-stu-id="b3256-109">As data moves from one command to the next, it moves as one or more identifiable objects.</span></span> <span data-ttu-id="b3256-110">Um objeto, então, é uma coleção de dados que representa um item.</span><span class="sxs-lookup"><span data-stu-id="b3256-110">An object, then, is a collection of data that represents an item.</span></span> <span data-ttu-id="b3256-111">Um objeto é composto de três tipos de dados: o tipo Objects, seus métodos e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="b3256-111">An object is made up of three types of data: the objects type, its methods, and its properties.</span></span>

## <a name="types-methods-and-properties"></a><span data-ttu-id="b3256-112">Tipos, métodos e propriedades</span><span class="sxs-lookup"><span data-stu-id="b3256-112">Types, Methods, and Properties</span></span>

<span data-ttu-id="b3256-113">O tipo de objeto informa que tipo de objeto é.</span><span class="sxs-lookup"><span data-stu-id="b3256-113">The object type tells what kind of object it is.</span></span> <span data-ttu-id="b3256-114">Por exemplo, um objeto que representa um arquivo é um objeto FileInfo.</span><span class="sxs-lookup"><span data-stu-id="b3256-114">For example, an object that represents a file is a FileInfo object.</span></span>

<span data-ttu-id="b3256-115">Os métodos de objeto são ações que você pode executar no objeto.</span><span class="sxs-lookup"><span data-stu-id="b3256-115">The object methods are actions that you can perform on the object.</span></span>
<span data-ttu-id="b3256-116">Por exemplo, os objetos FileInfo têm um método CopyTo que você pode usar para copiar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b3256-116">For example, FileInfo objects have a CopyTo method that you can use to copy the file.</span></span>

<span data-ttu-id="b3256-117">As propriedades do objeto armazenam informações sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="b3256-117">Object properties store information about the object.</span></span> <span data-ttu-id="b3256-118">Por exemplo, os objetos FileInfo têm uma Propriedade LastWriteTime que armazena a data e a hora em que o arquivo foi acessado mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="b3256-118">For example, FileInfo objects have a LastWriteTime property that stores the date and time that the file was most recently accessed.</span></span>

<span data-ttu-id="b3256-119">Ao trabalhar com objetos, você pode usar seus métodos e propriedades em comandos para executar ações e gerenciar dados.</span><span class="sxs-lookup"><span data-stu-id="b3256-119">When working with objects, you can use their methods and properties in commands to take action and manage data.</span></span>

## <a name="objects-in-pipelines"></a><span data-ttu-id="b3256-120">Objetos em pipelines</span><span class="sxs-lookup"><span data-stu-id="b3256-120">Objects in Pipelines</span></span>

<span data-ttu-id="b3256-121">Quando os comandos são combinados em um pipeline, eles passam informações entre si como objetos.</span><span class="sxs-lookup"><span data-stu-id="b3256-121">When commands are combined in a pipeline, they pass information to each other as objects.</span></span> <span data-ttu-id="b3256-122">Quando o primeiro comando é executado, ele envia um ou mais objetos por meio do pipeline para o segundo comando.</span><span class="sxs-lookup"><span data-stu-id="b3256-122">When the first command runs, it sends one or more objects down the pipeline to the second command.</span></span> <span data-ttu-id="b3256-123">O segundo comando recebe os objetos do primeiro comando, processa os objetos e, em seguida, passa os objetos novos ou revisados para o próximo comando no pipeline.</span><span class="sxs-lookup"><span data-stu-id="b3256-123">The second command receives the objects from the first command, processes the objects, and then passes new or revised objects to the next command in the pipeline.</span></span>
<span data-ttu-id="b3256-124">Isso continuará até que todos os comandos no pipeline sejam executados.</span><span class="sxs-lookup"><span data-stu-id="b3256-124">This continues until all commands in the pipeline run.</span></span>

<span data-ttu-id="b3256-125">O exemplo a seguir demonstra como os objetos são passados de um comando para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b3256-125">The following example demonstrates how objects are passed from one command to the next:</span></span>

```powershell
Get-ChildItem C: | where { $_.PsIsContainer -eq $false } | Format-List
```

<span data-ttu-id="b3256-126">O primeiro comando `Get-ChildItem C:` retorna um objeto de arquivo ou diretório para cada item no diretório raiz do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b3256-126">The first command `Get-ChildItem C:` returns a file or directory object for each item in the root directory of the file system.</span></span> <span data-ttu-id="b3256-127">Os objetos de arquivo e diretório são passados para o pipeline para o segundo comando.</span><span class="sxs-lookup"><span data-stu-id="b3256-127">The file and directory objects are passed down the pipeline to the second command.</span></span>

<span data-ttu-id="b3256-128">O segundo comando `where { $_.PsIsContainer -eq $false }` usa a propriedade PsIsContainer de todos os objetos do sistema de arquivos para selecionar apenas os arquivos, que têm um valor de false ( \$ false) em sua propriedade PsIsContainer.</span><span class="sxs-lookup"><span data-stu-id="b3256-128">The second command `where { $_.PsIsContainer -eq $false }` uses the PsIsContainer property of all file system objects to select only files, which have a value of False (\$false) in their PsIsContainer property.</span></span> <span data-ttu-id="b3256-129">As pastas, que são contêineres e, portanto, têm um valor de true ( \$ true) em sua propriedade PsIsContainer, não são selecionadas.</span><span class="sxs-lookup"><span data-stu-id="b3256-129">Folders, which are containers and, thus, have a value of True (\$true) in their PsIsContainer property, are not selected.</span></span>

<span data-ttu-id="b3256-130">O segundo comando passa apenas os objetos File para o terceiro comando `Format-List` , que exibe os objetos de arquivo em uma lista.</span><span class="sxs-lookup"><span data-stu-id="b3256-130">The second command passes only the file objects to the third command `Format-List`, which displays the file objects in a list.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3256-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b3256-131">See Also</span></span>

[<span data-ttu-id="b3256-132">about_Methods</span><span class="sxs-lookup"><span data-stu-id="b3256-132">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="b3256-133">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="b3256-133">about_Object_Creation</span></span>](about_Object_Creation.md)

[<span data-ttu-id="b3256-134">about_Properties</span><span class="sxs-lookup"><span data-stu-id="b3256-134">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="b3256-135">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="b3256-135">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="b3256-136">Get-Member</span><span class="sxs-lookup"><span data-stu-id="b3256-136">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)
