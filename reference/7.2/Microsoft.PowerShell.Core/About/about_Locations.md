---
description: Descreve como acessar itens do local de trabalho no PowerShell.
Locale: en-US
ms.date: 03/15/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_locations?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Locations
ms.openlocfilehash: e454fe3148ff3e7fdecb52f9fd3b6cdf583b8644
ms.sourcegitcommit: 15f759ca68d17acecab46b52250298d4f2037c4d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2021
ms.locfileid: "103575756"
---
# <a name="about_locations"></a><span data-ttu-id="2732e-103">about_Locations</span><span class="sxs-lookup"><span data-stu-id="2732e-103">about_Locations</span></span>

## <a name="short-description"></a><span data-ttu-id="2732e-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="2732e-104">Short description</span></span>
<span data-ttu-id="2732e-105">Descreve como acessar itens do local de trabalho no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2732e-105">Describes how to access items from the working location in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="2732e-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="2732e-106">Long description</span></span>

<span data-ttu-id="2732e-107">O local de trabalho atual é o local padrão para o qual os comandos apontam.</span><span class="sxs-lookup"><span data-stu-id="2732e-107">The current working location is the default location to which commands point.</span></span>
<span data-ttu-id="2732e-108">Em outras palavras, esse é o local que o PowerShell usa se você não fornecer um caminho explícito para o item ou o local que é afetado pelo comando.</span><span class="sxs-lookup"><span data-stu-id="2732e-108">In other words, this is the location that PowerShell uses if you do not supply an explicit path to the item or location that is affected by the command.</span></span>

> [!NOTE]
> <span data-ttu-id="2732e-109">O PowerShell dá suporte a vários Runspaces por processo.</span><span class="sxs-lookup"><span data-stu-id="2732e-109">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="2732e-110">Cada runspace tem seu próprio _diretório atual_.</span><span class="sxs-lookup"><span data-stu-id="2732e-110">Each runspace has its own _current directory_.</span></span> <span data-ttu-id="2732e-111">Isso não é o mesmo que o diretório atual do processo: `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="2732e-111">This is not the same as the current directory of the process: `[System.Environment]::CurrentDirectory`.</span></span>

<span data-ttu-id="2732e-112">Na maioria dos casos, o local de trabalho atual é uma unidade acessada por meio do provedor de sistema de arquivos do PowerShell e, em alguns casos, um diretório nessa unidade.</span><span class="sxs-lookup"><span data-stu-id="2732e-112">In most cases, the current working location is a drive accessed through the PowerShell FileSystem provider and, in some cases, a directory on that drive.</span></span>
<span data-ttu-id="2732e-113">Por exemplo, você pode definir seu local de trabalho atual para o seguinte local:</span><span class="sxs-lookup"><span data-stu-id="2732e-113">For example, you might set your current working location to the following location:</span></span>

```powershell
C:\Program Files\Windows PowerShell
```

<span data-ttu-id="2732e-114">Como resultado, todos os comandos são processados desse local, a menos que outro caminho seja explicitamente fornecido.</span><span class="sxs-lookup"><span data-stu-id="2732e-114">As a result, all commands are processed from this location unless another path is explicitly provided.</span></span>

<span data-ttu-id="2732e-115">O PowerShell mantém o local de trabalho atual para cada unidade, mesmo quando a unidade não é a unidade atual.</span><span class="sxs-lookup"><span data-stu-id="2732e-115">PowerShell maintains the current working location for each drive even when the drive is not the current drive.</span></span> <span data-ttu-id="2732e-116">Isso permite que você acesse itens do local de trabalho atual fazendo referência apenas à unidade de outro local.</span><span class="sxs-lookup"><span data-stu-id="2732e-116">This allows you to access items from the current working location by referring only to the drive of another location.</span></span>
<span data-ttu-id="2732e-117">Por exemplo, suponha que o local de trabalho atual seja `C:\Windows` .</span><span class="sxs-lookup"><span data-stu-id="2732e-117">For example, suppose that your current working location is `C:\Windows`.</span></span> <span data-ttu-id="2732e-118">Agora, suponha que você use o seguinte comando para alterar o local de trabalho atual para a unidade HKLM:</span><span class="sxs-lookup"><span data-stu-id="2732e-118">Now, suppose you use the following command to change your current working location to the HKLM: drive:</span></span>

```powershell
Set-Location HKLM:
```

<span data-ttu-id="2732e-119">Embora seu local atual agora seja a unidade do registro, você ainda pode acessar itens no `C:\Windows` diretório simplesmente usando a unidade C:, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="2732e-119">Although your current location is now the registry drive, you can still access items in the `C:\Windows` directory simply by using the C: drive, as shown in the following example:</span></span>

```powershell
Get-ChildItem C:
```

<span data-ttu-id="2732e-120">O PowerShell lembra que o seu local de trabalho atual para essa unidade é o diretório do Windows, então ele recupera os itens desse diretório.</span><span class="sxs-lookup"><span data-stu-id="2732e-120">PowerShell remembers that your current working location for that drive is the Windows directory, so it retrieves items from that directory.</span></span> <span data-ttu-id="2732e-121">Os resultados seriam os mesmos se você executou o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2732e-121">The results would be the same if you ran the following command:</span></span>

```powershell
Get-ChildItem C:\Windows
```

<span data-ttu-id="2732e-122">No PowerShell, você pode usar o comando Get-Location para determinar o local de trabalho atual e pode usar o comando Set-Location para definir o local de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="2732e-122">In PowerShell, you can use the Get-Location command to determine the current working location, and you can use the Set-Location command to set the current working location.</span></span> <span data-ttu-id="2732e-123">Por exemplo, o comando a seguir define o local de trabalho atual como o diretório do Windows da unidade C::</span><span class="sxs-lookup"><span data-stu-id="2732e-123">For example, the following command sets the current working location to the Windows directory of the C: drive:</span></span>

```powershell
Set-Location c:\windows
```

<span data-ttu-id="2732e-124">Depois de definir o local de trabalho atual, você ainda pode acessar itens de outras unidades simplesmente incluindo o nome da unidade (seguido por dois-pontos) no comando, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="2732e-124">After you set the current working location, you can still access items from other drives simply by including the drive name (followed by a colon) in the command, as shown in the following example:</span></span>

```powershell
Get-ChildItem HKLM:\software
```

<span data-ttu-id="2732e-125">O comando de exemplo recupera uma lista de itens no contêiner de software do hive do computador local HKEY no registro.</span><span class="sxs-lookup"><span data-stu-id="2732e-125">The example command retrieves a list of items in the Software container of the HKEY Local Machine hive in the registry.</span></span>

<span data-ttu-id="2732e-126">O PowerShell também permite que você use caracteres especiais para representar o local de trabalho atual e seu local pai.</span><span class="sxs-lookup"><span data-stu-id="2732e-126">PowerShell also allows you to use special characters to represent the current working location and its parent location.</span></span> <span data-ttu-id="2732e-127">Para representar o local de trabalho atual, use um único período.</span><span class="sxs-lookup"><span data-stu-id="2732e-127">To represent the current working location, use a single period.</span></span> <span data-ttu-id="2732e-128">Para representar o pai do local de trabalho atual, use dois pontos.</span><span class="sxs-lookup"><span data-stu-id="2732e-128">To represent the parent of the current working location, use two periods.</span></span> <span data-ttu-id="2732e-129">Por exemplo, o seguinte especifica o subdiretório do sistema no local de trabalho atual:</span><span class="sxs-lookup"><span data-stu-id="2732e-129">For example, the following specifies the System subdirectory in the current working location:</span></span>

```powershell
Get-ChildItem .\system
```

<span data-ttu-id="2732e-130">Se o local de trabalho atual for `C:\Windows` , esse comando retornará uma lista de todos os itens em `C:\Windows\System` .</span><span class="sxs-lookup"><span data-stu-id="2732e-130">If the current working location is `C:\Windows`, this command returns a list of all the items in `C:\Windows\System`.</span></span> <span data-ttu-id="2732e-131">No entanto, se você usar dois pontos, o diretório pai do diretório de trabalho atual será usado, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="2732e-131">However, if you use two periods, the parent directory of the current working directory is used, as shown in the following example:</span></span>

```powershell
Get-ChildItem ..\"program files"
```

<span data-ttu-id="2732e-132">Nesse caso, o PowerShell trata os dois períodos como a unidade C:, portanto, o comando recupera todos os itens no `C:\Program Files` diretório.</span><span class="sxs-lookup"><span data-stu-id="2732e-132">In this case, PowerShell treats the two periods as the C: drive, so the command retrieves all the items in the `C:\Program Files` directory.</span></span>

<span data-ttu-id="2732e-133">Um caminho que começa com uma barra identifica um caminho da raiz da unidade atual.</span><span class="sxs-lookup"><span data-stu-id="2732e-133">A path beginning with a slash identifies a path from the root of the current drive.</span></span> <span data-ttu-id="2732e-134">Por exemplo, se o local de trabalho atual for `C:\Program Files\PowerShell` , a raiz da unidade será C. Portanto, o comando a seguir lista todos os itens no `C:\Windows` diretório:</span><span class="sxs-lookup"><span data-stu-id="2732e-134">For example, if your current working location is `C:\Program Files\PowerShell`, the root of your drive is C. Therefore, the following command lists all items in the `C:\Windows` directory:</span></span>

```powershell
Get-ChildItem \windows
```

<span data-ttu-id="2732e-135">Se você não especificar um caminho começando com um nome de unidade, barra ou ponto ao fornecer o nome de um contêiner ou item, presume-se que o contêiner ou item esteja localizado no local de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="2732e-135">If you do not specify a path beginning with a drive name, slash, or period when supplying the name of a container or item, the container or item is assumed to be located in the current working location.</span></span> <span data-ttu-id="2732e-136">Por exemplo, se o local de trabalho atual for `C:\Windows` , o comando a seguir retornará todos os itens no `C:\Windows\System` diretório:</span><span class="sxs-lookup"><span data-stu-id="2732e-136">For example, if your current working location is `C:\Windows`, the following command returns all the items in the `C:\Windows\System` directory:</span></span>

```powershell
Get-ChildItem system
```

<span data-ttu-id="2732e-137">Se você especificar um nome de arquivo em vez de um nome de diretório, o PowerShell retornará detalhes sobre esse arquivo (supondo que esse arquivo esteja localizado no local de trabalho atual).</span><span class="sxs-lookup"><span data-stu-id="2732e-137">If you specify a file name rather than a directory name, PowerShell returns details about that file (assuming that file is located in the current working location).</span></span>

## <a name="see-also"></a><span data-ttu-id="2732e-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="2732e-138">See also</span></span>

[<span data-ttu-id="2732e-139">Set-Location</span><span class="sxs-lookup"><span data-stu-id="2732e-139">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

[<span data-ttu-id="2732e-140">about_Providers</span><span class="sxs-lookup"><span data-stu-id="2732e-140">about_Providers</span></span>](about_Providers.md)

[<span data-ttu-id="2732e-141">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="2732e-141">about_Path_Syntax</span></span>](about_Path_Syntax.md)
