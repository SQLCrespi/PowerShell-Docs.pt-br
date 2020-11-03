---
description: Descreve como acessar itens do local de trabalho no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_locations?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Locations
ms.openlocfilehash: 56af758f06e365eb070786e50d8f8309d8f608fd
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195447"
---
# <a name="about_locations"></a><span data-ttu-id="e9a2c-104">about_Locations</span><span class="sxs-lookup"><span data-stu-id="e9a2c-104">about_Locations</span></span>

## <a name="short-description"></a><span data-ttu-id="e9a2c-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="e9a2c-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="e9a2c-106">Descreve como acessar itens do local de trabalho no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-106">Describes how to access items from the working location in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="e9a2c-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="e9a2c-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="e9a2c-108">O local de trabalho atual é o local padrão para o qual os comandos apontam.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-108">The current working location is the default location to which commands point.</span></span>
<span data-ttu-id="e9a2c-109">Em outras palavras, esse é o local que o PowerShell usa se você não fornecer um caminho explícito para o item ou o local que é afetado pelo comando.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-109">In other words, this is the location that PowerShell uses if you do not supply an explicit path to the item or location that is affected by the command.</span></span> <span data-ttu-id="e9a2c-110">Na maioria dos casos, o local de trabalho atual é uma unidade acessada por meio do provedor de sistema de arquivos do PowerShell e, em alguns casos, um diretório nessa unidade.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-110">In most cases, the current working location is a drive accessed through the PowerShell FileSystem provider and, in some cases, a directory on that drive.</span></span>
<span data-ttu-id="e9a2c-111">Por exemplo, você pode definir seu local de trabalho atual para o seguinte local:</span><span class="sxs-lookup"><span data-stu-id="e9a2c-111">For example, you might set your current working location to the following location:</span></span>

```powershell
C:\Program Files\Windows PowerShell
```

<span data-ttu-id="e9a2c-112">Como resultado, todos os comandos são processados desse local, a menos que outro caminho seja explicitamente fornecido.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-112">As a result, all commands are processed from this location unless another path is explicitly provided.</span></span>

<span data-ttu-id="e9a2c-113">O PowerShell mantém o local de trabalho atual para cada unidade, mesmo quando a unidade não é a unidade atual.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-113">PowerShell maintains the current working location for each drive even when the drive is not the current drive.</span></span> <span data-ttu-id="e9a2c-114">Isso permite que você acesse itens do local de trabalho atual fazendo referência apenas à unidade de outro local.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-114">This allows you to access items from the current working location by referring only to the drive of another location.</span></span>
<span data-ttu-id="e9a2c-115">Por exemplo, suponha que o local de trabalho atual seja C: \\ Windows.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-115">For example, suppose that your current working location is C:\\Windows.</span></span> <span data-ttu-id="e9a2c-116">Agora, suponha que você use o seguinte comando para alterar o local de trabalho atual para a unidade HKLM:</span><span class="sxs-lookup"><span data-stu-id="e9a2c-116">Now, suppose you use the following command to change your current working location to the HKLM: drive:</span></span>

```powershell
Set-Location HKLM:
```

<span data-ttu-id="e9a2c-117">Embora seu local atual agora seja a unidade do registro, você ainda pode acessar itens no diretório C: \\ Windows simplesmente usando a unidade c:, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="e9a2c-117">Although your current location is now the registry drive, you can still access items in the C:\\Windows directory simply by using the C: drive, as shown in the following example:</span></span>

```powershell
Get-ChildItem C:
```

<span data-ttu-id="e9a2c-118">O PowerShell lembra que o seu local de trabalho atual para essa unidade é o diretório do Windows, então ele recupera os itens desse diretório.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-118">PowerShell remembers that your current working location for that drive is the Windows directory, so it retrieves items from that directory.</span></span> <span data-ttu-id="e9a2c-119">Os resultados seriam os mesmos se você executou o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e9a2c-119">The results would be the same if you ran the following command:</span></span>

```powershell
Get-ChildItem C:\Windows
```

<span data-ttu-id="e9a2c-120">No PowerShell, você pode usar o comando Get-Location para determinar o local de trabalho atual e pode usar o comando Set-Location para definir o local de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-120">In PowerShell, you can use the Get-Location command to determine the current working location, and you can use the Set-Location command to set the current working location.</span></span> <span data-ttu-id="e9a2c-121">Por exemplo, o comando a seguir define o local de trabalho atual como o diretório do Windows da unidade C::</span><span class="sxs-lookup"><span data-stu-id="e9a2c-121">For example, the following command sets the current working location to the Windows directory of the C: drive:</span></span>

```powershell
Set-Location c:\windows
```

<span data-ttu-id="e9a2c-122">Depois de definir o local de trabalho atual, você ainda pode acessar itens de outras unidades simplesmente incluindo o nome da unidade (seguido por dois-pontos) no comando, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="e9a2c-122">After you set the current working location, you can still access items from other drives simply by including the drive name (followed by a colon) in the command, as shown in the following example:</span></span>

```powershell
Get-ChildItem HKLM:\software
```

<span data-ttu-id="e9a2c-123">O comando de exemplo recupera uma lista de itens no contêiner de software do hive do computador local HKEY no registro.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-123">The example command retrieves a list of items in the Software container of the HKEY Local Machine hive in the registry.</span></span>

<span data-ttu-id="e9a2c-124">O PowerShell também permite que você use caracteres especiais para representar o local de trabalho atual e seu local pai.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-124">PowerShell also allows you to use special characters to represent the current working location and its parent location.</span></span> <span data-ttu-id="e9a2c-125">Para representar o local de trabalho atual, use um único período.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-125">To represent the current working location, use a single period.</span></span> <span data-ttu-id="e9a2c-126">Para representar o pai do local de trabalho atual, use dois pontos.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-126">To represent the parent of the current working location, use two periods.</span></span> <span data-ttu-id="e9a2c-127">Por exemplo, o seguinte especifica o subdiretório do sistema no local de trabalho atual:</span><span class="sxs-lookup"><span data-stu-id="e9a2c-127">For example, the following specifies the System subdirectory in the current working location:</span></span>

```powershell
Get-ChildItem .\system
```

<span data-ttu-id="e9a2c-128">Se o local de trabalho atual for C: \\ Windows, esse comando retornará uma lista de todos os itens em c: \\ Windows \\ System.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-128">If the current working location is C:\\Windows, this command returns a list of all the items in C:\\Windows\\System.</span></span> <span data-ttu-id="e9a2c-129">No entanto, se você usar dois pontos, o diretório pai do diretório de trabalho atual será usado, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="e9a2c-129">However, if you use two periods, the parent directory of the current working directory is used, as shown in the following example:</span></span>

```powershell
Get-ChildItem ..\"program files"
```

<span data-ttu-id="e9a2c-130">Nesse caso, o PowerShell trata os dois períodos como a unidade C:, portanto, o comando recupera todos os itens no diretório C: \\ arquivos de programas.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-130">In this case, PowerShell treats the two periods as the C: drive, so the command retrieves all the items in the C:\\Program Files directory.</span></span>

<span data-ttu-id="e9a2c-131">Um caminho que começa com uma barra identifica um caminho da raiz da unidade atual.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-131">A path beginning with a slash identifies a path from the root of the current drive.</span></span> <span data-ttu-id="e9a2c-132">Por exemplo, se o local de trabalho atual for C: \\ arquivos de programas do \\ PowerShell, a raiz da unidade será c. Portanto, o comando a seguir lista todos os itens no diretório C: \\ Windows:</span><span class="sxs-lookup"><span data-stu-id="e9a2c-132">For example, if your current working location is C:\\Program Files\\PowerShell, the root of your drive is C. Therefore, the following command lists all items in the C:\\Windows directory:</span></span>

```powershell
Get-ChildItem \windows
```

<span data-ttu-id="e9a2c-133">Se você não especificar um caminho começando com um nome de unidade, barra ou ponto ao fornecer o nome de um contêiner ou item, presume-se que o contêiner ou item esteja localizado no local de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="e9a2c-133">If you do not specify a path beginning with a drive name, slash, or period when supplying the name of a container or item, the container or item is assumed to be located in the current working location.</span></span> <span data-ttu-id="e9a2c-134">Por exemplo, se o local de trabalho atual for C: \\ Windows, o comando a seguir retornará todos os itens no diretório c: \\ Windows \\ System:</span><span class="sxs-lookup"><span data-stu-id="e9a2c-134">For example, if your current working location is C:\\Windows, the following command returns all the items in the C:\\Windows\\System directory:</span></span>

```powershell
Get-ChildItem system
```

<span data-ttu-id="e9a2c-135">Se você especificar um nome de arquivo em vez de um nome de diretório, o PowerShell retornará detalhes sobre esse arquivo (supondo que esse arquivo esteja localizado no local de trabalho atual).</span><span class="sxs-lookup"><span data-stu-id="e9a2c-135">If you specify a file name rather than a directory name, PowerShell returns details about that file (assuming that file is located in the current working location).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9a2c-136">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="e9a2c-136">SEE ALSO</span></span>

[<span data-ttu-id="e9a2c-137">Set-Location</span><span class="sxs-lookup"><span data-stu-id="e9a2c-137">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

[<span data-ttu-id="e9a2c-138">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e9a2c-138">about_Providers</span></span>](about_Providers.md)

[<span data-ttu-id="e9a2c-139">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="e9a2c-139">about_Path_Syntax</span></span>](about_Path_Syntax.md)

