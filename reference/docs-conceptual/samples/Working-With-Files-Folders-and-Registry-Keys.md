---
ms.date: 07/28/2020
keywords: powershell, cmdlet
title: Trabalhando com pastas de arquivos e chaves de Registro
ms.openlocfilehash: 7ead5d0e82feb852845468fb3a012a0908a4ce75
ms.sourcegitcommit: 339e5fc8a4cc18b4ff6956fe5180343588e40e30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87410182"
---
# <a name="working-with-files-folders-and-registry-keys"></a><span data-ttu-id="d8035-103">Trabalhando com arquivos, pastas e chaves do Registro</span><span class="sxs-lookup"><span data-stu-id="d8035-103">Working With Files, Folders and Registry Keys</span></span>

<span data-ttu-id="d8035-104">O Windows PowerShell usa o substantivo **Item** para se referir a itens encontrados em uma unidade do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8035-104">Windows PowerShell uses the noun **Item** to refer to items found on a Windows PowerShell drive.</span></span>
<span data-ttu-id="d8035-105">Ao lidar com o provedor do Sistema de arquivos do Windows PowerShell, um **Item** pode ser um arquivo, uma pasta ou uma unidade do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8035-105">When dealing with the Windows PowerShell FileSystem provider, an **Item** might be a file, a folder, or the Windows PowerShell drive.</span></span> <span data-ttu-id="d8035-106">Listar e trabalhar com esses itens são tarefas críticas básicas na maioria das configurações administrativas, por isso abordaremos essas tarefas com mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="d8035-106">Listing and working with these items is a critical basic task in most administrative settings, so we want to discuss these tasks in detail.</span></span>

## <a name="enumerating-files-folders-and-registry-keys-get-childitem"></a><span data-ttu-id="d8035-107">Enumerando arquivos, pastas e chaves do registro (Get-ChildItem)</span><span class="sxs-lookup"><span data-stu-id="d8035-107">Enumerating Files, Folders, and Registry Keys (Get-ChildItem)</span></span>

<span data-ttu-id="d8035-108">Como a obtenção de uma coleção de itens de uma localização específica é uma tarefa comum, o cmdlet `Get-ChildItem` foi desenvolvido especificamente para retornar todos os itens encontrados em um contêiner, como uma pasta.</span><span class="sxs-lookup"><span data-stu-id="d8035-108">Since getting a collection of items from a particular location is such a common task, the `Get-ChildItem` cmdlet is designed specifically to return all items found within a container such as a folder.</span></span>

<span data-ttu-id="d8035-109">Se você quiser retornar todos os arquivos e pastas contidos diretamente na pasta C:\\Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="d8035-109">If you want to return all files and folders that are contained directly within the folder C:\\Windows, type:</span></span>

```
PS> Get-ChildItem -Path C:\Windows
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2006-05-16   8:10 AM          0 0.log
-a---        2005-11-29   3:16 PM         97 acc1.txt
-a---        2005-10-23  11:21 PM       3848 actsetup.log
...
```

<span data-ttu-id="d8035-110">A listagem é semelhante ao que seria exibido quando você inserisse o comando `dir` no **Cmd.exe** ou o comando `ls` em um shell de comando do UNIX.</span><span class="sxs-lookup"><span data-stu-id="d8035-110">The listing looks similar to what you would see when you enter the `dir` command in **Cmd.exe**, or the `ls` command in a UNIX command shell.</span></span>

<span data-ttu-id="d8035-111">Você pode executar listagens muito complexas usando parâmetros do cmdlet `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="d8035-111">You can perform very complex listings by using parameters of the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="d8035-112">Examinaremos alguns cenários em seguida.</span><span class="sxs-lookup"><span data-stu-id="d8035-112">We will look at a few scenarios next.</span></span> <span data-ttu-id="d8035-113">É possível ver a sintaxe do cmdlet `Get-ChildItem` digitando:</span><span class="sxs-lookup"><span data-stu-id="d8035-113">You can see the syntax the `Get-ChildItem` cmdlet by typing:</span></span>

```powershell
Get-Command -Name Get-ChildItem -Syntax
```

<span data-ttu-id="d8035-114">Esses parâmetros podem ser misturados e combinados para obter uma saída altamente personalizável.</span><span class="sxs-lookup"><span data-stu-id="d8035-114">These parameters can be mixed and matched to get highly customized output.</span></span>

### <a name="listing-all-contained-items--recurse"></a><span data-ttu-id="d8035-115">Listando todos os itens contidos (-Recurse)</span><span class="sxs-lookup"><span data-stu-id="d8035-115">Listing all Contained Items (-Recurse)</span></span>

<span data-ttu-id="d8035-116">Para ver tanto os itens em uma pasta do Windows e os itens contidos em subpastas, use o parâmetro **Recurse** de `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="d8035-116">To see both the items inside a Windows folder and any items that are contained within the subfolders, use the **Recurse** parameter of `Get-ChildItem`.</span></span> <span data-ttu-id="d8035-117">A lista exibe tudo dentro da pasta do Windows, bem como os itens em suas subpastas.</span><span class="sxs-lookup"><span data-stu-id="d8035-117">The listing displays everything within the Windows folder and the items in its subfolders.</span></span> <span data-ttu-id="d8035-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d8035-118">For example:</span></span>

```
PS> Get-ChildItem -Path C:\WINDOWS -Recurse

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS\AppPatch
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM    1852416 AcGenral.dll
...
```

### <a name="filtering-items-by-name--name"></a><span data-ttu-id="d8035-119">Filtrar itens por nome (-Name)</span><span class="sxs-lookup"><span data-stu-id="d8035-119">Filtering Items by Name (-Name)</span></span>

<span data-ttu-id="d8035-120">Para exibir somente os nomes dos itens, use o parâmetro **Name** de `Get-Childitem`:</span><span class="sxs-lookup"><span data-stu-id="d8035-120">To display only the names of items, use the **Name** parameter of `Get-Childitem`:</span></span>

```
PS> Get-ChildItem -Path C:\WINDOWS -Name
addins
AppPatch
assembly
...
```

### <a name="forcibly-listing-hidden-items--force"></a><span data-ttu-id="d8035-121">Forçar a listagem de itens ocultos (-Force)</span><span class="sxs-lookup"><span data-stu-id="d8035-121">Forcibly Listing Hidden Items (-Force)</span></span>

<span data-ttu-id="d8035-122">Itens que são normalmente invisíveis no Explorador de Arquivos ou no Cmd.exe não são exibidos na saída de um comando `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="d8035-122">Items that are normally invisible in File Explorer or Cmd.exe are not displayed in the output of a `Get-ChildItem` command.</span></span> <span data-ttu-id="d8035-123">Para exibir itens ocultos, use o parâmetro **Force** do `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="d8035-123">To display hidden items, use the **Force** parameter of `Get-ChildItem`.</span></span>
<span data-ttu-id="d8035-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d8035-124">For example:</span></span>

```powershell
Get-ChildItem -Path C:\Windows -Force
```

<span data-ttu-id="d8035-125">Esse parâmetro é chamado Force porque com ele você pode forçar a substituição do comportamento normal do comando `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="d8035-125">This parameter is named Force because you can forcibly override the normal behavior of the `Get-ChildItem` command.</span></span> <span data-ttu-id="d8035-126">O Force é um parâmetro amplamente usado que força uma ação que um cmdlet normalmente não executa, embora ele não executará qualquer ação que comprometa a segurança do sistema.</span><span class="sxs-lookup"><span data-stu-id="d8035-126">Force is a widely used parameter that forces an action that a cmdlet would not normally perform, although it will not perform any action that compromises the security of the system.</span></span>

### <a name="matching-item-names-with-wildcards"></a><span data-ttu-id="d8035-127">Correspondendo nomes de itens com curingas</span><span class="sxs-lookup"><span data-stu-id="d8035-127">Matching Item Names with Wildcards</span></span>

<span data-ttu-id="d8035-128">O comando `Get-ChildItem` aceita curingas no caminho dos itens a serem listados.</span><span class="sxs-lookup"><span data-stu-id="d8035-128">The `Get-ChildItem` command accepts wildcards in the path of the items to list.</span></span>

<span data-ttu-id="d8035-129">Como a correspondência de curingas é identificada pelo mecanismo do Windows PowerShell, todos os cmdlets que aceitam curingas usam a mesma notação e têm o mesmo comportamento de correspondência.</span><span class="sxs-lookup"><span data-stu-id="d8035-129">Because wildcard matching is handled by the Windows PowerShell engine, all cmdlets that accepts wildcards use the same notation and have the same matching behavior.</span></span> <span data-ttu-id="d8035-130">A notação de curinga do Windows PowerShell inclui:</span><span class="sxs-lookup"><span data-stu-id="d8035-130">The Windows PowerShell wildcard notation includes:</span></span>

- <span data-ttu-id="d8035-131">O asterisco (`*`) corresponde a zero ou a mais ocorrências de qualquer caractere.</span><span class="sxs-lookup"><span data-stu-id="d8035-131">Asterisk (`*`) matches zero or more occurrences of any character.</span></span>

- <span data-ttu-id="d8035-132">O ponto de interrogação (`?`) corresponde exatamente a um caractere.</span><span class="sxs-lookup"><span data-stu-id="d8035-132">Question mark (`?`) matches exactly one character.</span></span>

- <span data-ttu-id="d8035-133">Os caracteres de colchete esquerdo (`[`) e de colchete direito (`]`) envolvem um conjunto de caracteres a serem correspondidos.</span><span class="sxs-lookup"><span data-stu-id="d8035-133">Left bracket (`[`) character and right bracket (`]`) character surround a set of characters to be matched.</span></span>

<span data-ttu-id="d8035-134">Aqui estão alguns exemplos de como a especificação de curinga funciona.</span><span class="sxs-lookup"><span data-stu-id="d8035-134">Here are some examples of how wildcard specification works.</span></span>

<span data-ttu-id="d8035-135">Para localizar todos os arquivos no diretório do Windows com o sufixo `.log` e exatamente cinco caracteres no nome de base, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d8035-135">To find all files in the Windows directory with the suffix `.log` and exactly five characters in the base name, enter the following command:</span></span>

```
PS> Get-ChildItem -Path C:\Windows\?????.log

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
...
-a---        2006-05-11   6:31 PM     204276 ocgen.log
-a---        2006-05-11   6:31 PM      22365 ocmsn.log
...
-a---        2005-11-11   4:55 AM         64 setup.log
-a---        2005-12-15   2:24 PM      17719 VxSDM.log
...
```

<span data-ttu-id="d8035-136">Para localizar todos os arquivos que começam com a letra `x` no diretório do Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="d8035-136">To find all files that begin with the letter `x` in the Windows directory, type:</span></span>

```powershell
Get-ChildItem -Path C:\Windows\x*
```

<span data-ttu-id="d8035-137">Para localizar todos os arquivos cujos nomes começam com "x" ou "z", digite:</span><span class="sxs-lookup"><span data-stu-id="d8035-137">To find all files whose names begin with "x" or "z", type:</span></span>

```powershell
Get-ChildItem -Path C:\Windows\[xz]*
```

<span data-ttu-id="d8035-138">Para obter mais informações sobre curingas, confira [about_Wildcards](/powershell/module/microsoft.powershell.core/about/about_wildcards).</span><span class="sxs-lookup"><span data-stu-id="d8035-138">For more information about wildcards, see [about_Wildcards](/powershell/module/microsoft.powershell.core/about/about_wildcards).</span></span>

### <a name="excluding-items--exclude"></a><span data-ttu-id="d8035-139">Excluindo itens (-Exclude)</span><span class="sxs-lookup"><span data-stu-id="d8035-139">Excluding Items (-Exclude)</span></span>

<span data-ttu-id="d8035-140">Você pode excluir itens específicos usando o parâmetro **Exclude** de `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="d8035-140">You can exclude specific items by using the **Exclude** parameter of `Get-ChildItem`.</span></span> <span data-ttu-id="d8035-141">Isso permite executar filtragem complexa em uma única instrução.</span><span class="sxs-lookup"><span data-stu-id="d8035-141">This lets you perform complex filtering in a single statement.</span></span>

<span data-ttu-id="d8035-142">Por exemplo, suponha que você está tentando localizar a DLL de Serviço de Tempo do Windows na pasta **System32**, e tudo o que você lembra do nome da DLL é que começa com "W" e contém "32".</span><span class="sxs-lookup"><span data-stu-id="d8035-142">For example, suppose you are trying to find the Windows Time Service DLL in the **System32** folder, and all you can remember about the DLL name is that it begins with "W" and has "32" in it.</span></span>

<span data-ttu-id="d8035-143">Uma expressão como `w*32*.dll` encontrará todas as DLLs que atendem às condições, mas talvez seja interessante filtrar ainda mais os arquivos e omitir arquivos win32.</span><span class="sxs-lookup"><span data-stu-id="d8035-143">An expression like `w*32*.dll` will find all DLLs that satisfy the conditions, but you may want to further filter out the files and omit any win32 files.</span></span> <span data-ttu-id="d8035-144">Você pode omitir esses arquivos usando o parâmetro **Exclude** com o padrão `win*`:</span><span class="sxs-lookup"><span data-stu-id="d8035-144">You can omit these files by using the **Exclude** parameter with the pattern `win*`:</span></span>

```
PS> Get-ChildItem -Path C:\WINDOWS\System32\w*32*.dll -Exclude win*

    Directory: C:\WINDOWS\System32

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           3/18/2019  9:43 PM         495616 w32time.dll
-a---           3/18/2019  9:44 PM          35328 w32topl.dll
-a---           1/24/2020  5:44 PM         401920 Wldap32.dll
-a---          10/10/2019  5:40 PM         442704 ws2_32.dll
-a---           3/18/2019  9:44 PM          66048 wsnmp32.dll
-a---           3/18/2019  9:44 PM          18944 wsock32.dll
-a---           3/18/2019  9:44 PM          64792 wtsapi32.dll
```

### <a name="mixing-get-childitem-parameters"></a><span data-ttu-id="d8035-145">Mesclando parâmetros do Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d8035-145">Mixing Get-ChildItem Parameters</span></span>

<span data-ttu-id="d8035-146">Você pode usar vários parâmetros do cmdlet `Get-ChildItem` no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="d8035-146">You can use several of the parameters of the `Get-ChildItem` cmdlet in the same command.</span></span> <span data-ttu-id="d8035-147">Antes de mesclar parâmetros, certifique-se de que você compreende a correspondência de curingas.</span><span class="sxs-lookup"><span data-stu-id="d8035-147">Before you mix parameters, be sure that you understand wildcard matching.</span></span> <span data-ttu-id="d8035-148">Por exemplo, o comando a seguir não retorna nenhum resultado:</span><span class="sxs-lookup"><span data-stu-id="d8035-148">For example, the following command returns no results:</span></span>

```powershell
Get-ChildItem -Path C:\Windows\*.dll -Recurse -Exclude [a-y]*.dll
```

<span data-ttu-id="d8035-149">Não haverá nenhum resultado, mesmo que haja duas DLLs que comecem com a letra "z" na pasta Windows.</span><span class="sxs-lookup"><span data-stu-id="d8035-149">There are no results, even though there are two DLLs that begin with the letter "z" in the Windows folder.</span></span>

<span data-ttu-id="d8035-150">Nenhum resultado foi retornado, pois especificamos o curinga como parte do caminho.</span><span class="sxs-lookup"><span data-stu-id="d8035-150">No results were returned because we specified the wildcard as part of the path.</span></span> <span data-ttu-id="d8035-151">Mesmo que o comando seja recursivo, o cmdlet `Get-ChildItem` restringiu os itens àqueles que estão na pasta do Windows com nomes que terminam com `.dll`.</span><span class="sxs-lookup"><span data-stu-id="d8035-151">Even though the command was recursive, the `Get-ChildItem` cmdlet restricted the items to those that are in the Windows folder with names ending with `.dll`.</span></span>

<span data-ttu-id="d8035-152">Para especificar uma pesquisa recursiva de arquivos cujos nomes correspondem a um padrão especial, use o parâmetro **Include**.</span><span class="sxs-lookup"><span data-stu-id="d8035-152">To specify a recursive search for files whose names match a special pattern, use the **Include** parameter.</span></span>

```
PS> Get-ChildItem -Path C:\Windows -Include *.dll -Recurse -Exclude [a-y]*.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32\Setup

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM       8261 zoneoc.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM     337920 zipfldr.dll
```
