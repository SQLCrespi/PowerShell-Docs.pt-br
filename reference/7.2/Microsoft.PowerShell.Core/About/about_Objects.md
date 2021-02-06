---
description: Fornece informações essenciais sobre objetos no PowerShell.
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_objects?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Objects
ms.openlocfilehash: bfb66e72a74d20379123558b85047097dc801e9d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595992"
---
# <a name="about-objects"></a><span data-ttu-id="7b0b0-103">Sobre objetos</span><span class="sxs-lookup"><span data-stu-id="7b0b0-103">About Objects</span></span>

## <a name="short-description"></a><span data-ttu-id="7b0b0-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="7b0b0-104">Short Description</span></span>
<span data-ttu-id="7b0b0-105">Fornece informações essenciais sobre objetos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-105">Provides essential information about objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="7b0b0-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="7b0b0-106">Long Description</span></span>

<span data-ttu-id="7b0b0-107">Cada ação executada no PowerShell ocorre dentro do contexto de objetos.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-107">Every action you take in PowerShell occurs within the context of objects.</span></span> <span data-ttu-id="7b0b0-108">À medida que os dados são movidos de um comando para o outro, ele é movido como um ou mais objetos identificáveis.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-108">As data moves from one command to the next, it moves as one or more identifiable objects.</span></span> <span data-ttu-id="7b0b0-109">Um objeto, então, é uma coleção de dados que representa um item.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-109">An object, then, is a collection of data that represents an item.</span></span> <span data-ttu-id="7b0b0-110">Um objeto é composto de três tipos de dados: o tipo Objects, seus métodos e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-110">An object is made up of three types of data: the objects type, its methods, and its properties.</span></span>

## <a name="types-methods-and-properties"></a><span data-ttu-id="7b0b0-111">Tipos, métodos e propriedades</span><span class="sxs-lookup"><span data-stu-id="7b0b0-111">Types, Methods, and Properties</span></span>

<span data-ttu-id="7b0b0-112">O tipo de objeto informa que tipo de objeto é.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-112">The object type tells what kind of object it is.</span></span> <span data-ttu-id="7b0b0-113">Por exemplo, um objeto que representa um arquivo é um objeto FileInfo.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-113">For example, an object that represents a file is a FileInfo object.</span></span>

<span data-ttu-id="7b0b0-114">Os métodos de objeto são ações que você pode executar no objeto.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-114">The object methods are actions that you can perform on the object.</span></span>
<span data-ttu-id="7b0b0-115">Por exemplo, os objetos FileInfo têm um método CopyTo que você pode usar para copiar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-115">For example, FileInfo objects have a CopyTo method that you can use to copy the file.</span></span>

<span data-ttu-id="7b0b0-116">As propriedades do objeto armazenam informações sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-116">Object properties store information about the object.</span></span> <span data-ttu-id="7b0b0-117">Por exemplo, os objetos FileInfo têm uma Propriedade LastWriteTime que armazena a data e a hora em que o arquivo foi acessado mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-117">For example, FileInfo objects have a LastWriteTime property that stores the date and time that the file was most recently accessed.</span></span>

<span data-ttu-id="7b0b0-118">Ao trabalhar com objetos, você pode usar seus métodos e propriedades em comandos para executar ações e gerenciar dados.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-118">When working with objects, you can use their methods and properties in commands to take action and manage data.</span></span>

## <a name="objects-in-pipelines"></a><span data-ttu-id="7b0b0-119">Objetos em pipelines</span><span class="sxs-lookup"><span data-stu-id="7b0b0-119">Objects in Pipelines</span></span>

<span data-ttu-id="7b0b0-120">Quando os comandos são combinados em um pipeline, eles passam informações entre si como objetos.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-120">When commands are combined in a pipeline, they pass information to each other as objects.</span></span> <span data-ttu-id="7b0b0-121">Quando o primeiro comando é executado, ele envia um ou mais objetos por meio do pipeline para o segundo comando.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-121">When the first command runs, it sends one or more objects down the pipeline to the second command.</span></span> <span data-ttu-id="7b0b0-122">O segundo comando recebe os objetos do primeiro comando, processa os objetos e, em seguida, passa os objetos novos ou revisados para o próximo comando no pipeline.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-122">The second command receives the objects from the first command, processes the objects, and then passes new or revised objects to the next command in the pipeline.</span></span>
<span data-ttu-id="7b0b0-123">Isso continuará até que todos os comandos no pipeline sejam executados.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-123">This continues until all commands in the pipeline run.</span></span>

<span data-ttu-id="7b0b0-124">O exemplo a seguir demonstra como os objetos são passados de um comando para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7b0b0-124">The following example demonstrates how objects are passed from one command to the next:</span></span>

```powershell
Get-ChildItem C: | where { $_.PsIsContainer -eq $false } | Format-List
```

<span data-ttu-id="7b0b0-125">O primeiro comando `Get-ChildItem C:` retorna um objeto de arquivo ou diretório para cada item no diretório raiz do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-125">The first command `Get-ChildItem C:` returns a file or directory object for each item in the root directory of the file system.</span></span> <span data-ttu-id="7b0b0-126">Os objetos de arquivo e diretório são passados para o pipeline para o segundo comando.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-126">The file and directory objects are passed down the pipeline to the second command.</span></span>

<span data-ttu-id="7b0b0-127">O segundo comando `where { $_.PsIsContainer -eq $false }` usa a propriedade PsIsContainer de todos os objetos do sistema de arquivos para selecionar apenas os arquivos, que têm um valor de false ( \$ false) em sua propriedade PsIsContainer.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-127">The second command `where { $_.PsIsContainer -eq $false }` uses the PsIsContainer property of all file system objects to select only files, which have a value of False (\$false) in their PsIsContainer property.</span></span> <span data-ttu-id="7b0b0-128">As pastas, que são contêineres e, portanto, têm um valor de true ( \$ true) em sua propriedade PsIsContainer, não são selecionadas.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-128">Folders, which are containers and, thus, have a value of True (\$true) in their PsIsContainer property, are not selected.</span></span>

<span data-ttu-id="7b0b0-129">O segundo comando passa apenas os objetos File para o terceiro comando `Format-List` , que exibe os objetos de arquivo em uma lista.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-129">The second command passes only the file objects to the third command `Format-List`, which displays the file objects in a list.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b0b0-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7b0b0-130">See Also</span></span>

[<span data-ttu-id="7b0b0-131">about_Methods</span><span class="sxs-lookup"><span data-stu-id="7b0b0-131">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="7b0b0-132">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="7b0b0-132">about_Object_Creation</span></span>](about_Object_Creation.md)

[<span data-ttu-id="7b0b0-133">about_Properties</span><span class="sxs-lookup"><span data-stu-id="7b0b0-133">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="7b0b0-134">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="7b0b0-134">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="7b0b0-135">Get-Member</span><span class="sxs-lookup"><span data-stu-id="7b0b0-135">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

