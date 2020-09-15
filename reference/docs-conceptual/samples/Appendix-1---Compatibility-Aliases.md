---
ms.date: 08/03/2020
keywords: powershell, cmdlet
title: Apêndice 1 Aliases de compatibilidade
ms.openlocfilehash: e5bd170fea6b6109d2ef4fd58863d6cc8a0e3ae1
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87758492"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="48278-103">Apêndice 1: Alias de compatibilidade</span><span class="sxs-lookup"><span data-stu-id="48278-103">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="48278-104">O PowerShell tem vários aliases que permitem que os usuários do **UNIX** e **cmd.exe** usem comandos conhecidos.</span><span class="sxs-lookup"><span data-stu-id="48278-104">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="48278-105">Os comandos, seus cmdlets do PowerShell e alias do PowerShell relacionados são mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="48278-105">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|            <span data-ttu-id="48278-106">comando cmd.exe</span><span class="sxs-lookup"><span data-stu-id="48278-106">cmd.exe command</span></span>            | <span data-ttu-id="48278-107">Comando UNIX</span><span class="sxs-lookup"><span data-stu-id="48278-107">UNIX command</span></span> | <span data-ttu-id="48278-108">Cmdlet do PowerShell</span><span class="sxs-lookup"><span data-stu-id="48278-108">PowerShell cmdlet</span></span> | <span data-ttu-id="48278-109">Alias do PowerShell</span><span class="sxs-lookup"><span data-stu-id="48278-109">PowerShell alias</span></span> |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| <span data-ttu-id="48278-110">**cd**, **chdir**</span><span class="sxs-lookup"><span data-stu-id="48278-110">**cd**, **chdir**</span></span>                     | <span data-ttu-id="48278-111">**cd**</span><span class="sxs-lookup"><span data-stu-id="48278-111">**cd**</span></span>       | `Set-Location`    | `sl`             |
| <span data-ttu-id="48278-112">**cls**</span><span class="sxs-lookup"><span data-stu-id="48278-112">**cls**</span></span>                               | <span data-ttu-id="48278-113">**clear**</span><span class="sxs-lookup"><span data-stu-id="48278-113">**clear**</span></span>    | `Clear-Host`      | `cls`            |
| <span data-ttu-id="48278-114">**copy**</span><span class="sxs-lookup"><span data-stu-id="48278-114">**copy**</span></span>                              | <span data-ttu-id="48278-115">**cp**</span><span class="sxs-lookup"><span data-stu-id="48278-115">**cp**</span></span>       | `Copy-Item`       | `cpi`            |
| <span data-ttu-id="48278-116">**del**, **erase**, **rd**, **rmdir**</span><span class="sxs-lookup"><span data-stu-id="48278-116">**del**, **erase**, **rd**, **rmdir**</span></span> | <span data-ttu-id="48278-117">**rm**</span><span class="sxs-lookup"><span data-stu-id="48278-117">**rm**</span></span>       | `Remove-Item`     | `ri`             |
| <span data-ttu-id="48278-118">**dir**</span><span class="sxs-lookup"><span data-stu-id="48278-118">**dir**</span></span>                               | <span data-ttu-id="48278-119">**ls**</span><span class="sxs-lookup"><span data-stu-id="48278-119">**ls**</span></span>       | `Get-ChildItem`   | `gci`            |
| <span data-ttu-id="48278-120">**echo**</span><span class="sxs-lookup"><span data-stu-id="48278-120">**echo**</span></span>                              | <span data-ttu-id="48278-121">**echo**</span><span class="sxs-lookup"><span data-stu-id="48278-121">**echo**</span></span>     | `Write-Output`    | `write`          |
| <span data-ttu-id="48278-122">**md**</span><span class="sxs-lookup"><span data-stu-id="48278-122">**md**</span></span>                                | <span data-ttu-id="48278-123">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="48278-123">**mkdir**</span></span>    | `New-Item`        | `ni`             |
| <span data-ttu-id="48278-124">**move**</span><span class="sxs-lookup"><span data-stu-id="48278-124">**move**</span></span>                              | <span data-ttu-id="48278-125">**mv**</span><span class="sxs-lookup"><span data-stu-id="48278-125">**mv**</span></span>       | `Move-Item`       | `mi`             |
| <span data-ttu-id="48278-126">**popd**</span><span class="sxs-lookup"><span data-stu-id="48278-126">**popd**</span></span>                              | <span data-ttu-id="48278-127">**popd**</span><span class="sxs-lookup"><span data-stu-id="48278-127">**popd**</span></span>     | `Pop-Location`    | `popd`           |
| <span data-ttu-id="48278-128">**pushd**</span><span class="sxs-lookup"><span data-stu-id="48278-128">**pushd**</span></span>                             | <span data-ttu-id="48278-129">**pushd**</span><span class="sxs-lookup"><span data-stu-id="48278-129">**pushd**</span></span>    | `Push-Location`   | `pushd`          |
| <span data-ttu-id="48278-130">**ren**</span><span class="sxs-lookup"><span data-stu-id="48278-130">**ren**</span></span>                               | <span data-ttu-id="48278-131">**mv**</span><span class="sxs-lookup"><span data-stu-id="48278-131">**mv**</span></span>       | `Rename-Item`     | `rni`            |
| <span data-ttu-id="48278-132">**tipo**</span><span class="sxs-lookup"><span data-stu-id="48278-132">**type**</span></span>                              | <span data-ttu-id="48278-133">**cat**</span><span class="sxs-lookup"><span data-stu-id="48278-133">**cat**</span></span>      | `Get-Content`     | `gc`             |

<span data-ttu-id="48278-134">Para localizar os aliases do PowerShell, use o cmdlet [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias).</span><span class="sxs-lookup"><span data-stu-id="48278-134">To find the PowerShell aliases, use the [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet.</span></span> <span data-ttu-id="48278-135">Para exibir os aliases de um cmdlet, use o parâmetro **Definição** e especifique o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="48278-135">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="48278-136">Ou, para localizar o nome do cmdlet de um alias, use o parâmetro **Name** e especifique o alias.</span><span class="sxs-lookup"><span data-stu-id="48278-136">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

```Output
CommandType     Name
-----------     ----
Alias           dir -> Get-ChildItem
Alias           gci -> Get-ChildItem
Alias           ls -> Get-ChildItem
```

```powershell
Get-Alias -Name gci
```

```Output
CommandType     Name
-----------     ----
Alias           gci -> Get-ChildItem
```
