---
ms.date: 09/09/2019
keywords: powershell, cmdlet
title: Apêndice 1 Aliases de compatibilidade
ms.openlocfilehash: 2351fdf23711fe1417f7e3fc3cca5b642d5a59fc
ms.sourcegitcommit: 00083f07b13c73b86936e7d7307397df27c63c04
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848170"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="f92b1-103">Apêndice 1: Alias de compatibilidade</span><span class="sxs-lookup"><span data-stu-id="f92b1-103">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="f92b1-104">O PowerShell tem vários aliases que permitem que os usuários do **UNIX** e **cmd.exe** usem comandos conhecidos.</span><span class="sxs-lookup"><span data-stu-id="f92b1-104">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="f92b1-105">Os comandos, seus cmdlets do PowerShell e alias do PowerShell relacionados são mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="f92b1-105">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|<span data-ttu-id="f92b1-106">comando cmd.exe</span><span class="sxs-lookup"><span data-stu-id="f92b1-106">cmd.exe command</span></span>|<span data-ttu-id="f92b1-107">Comando UNIX</span><span class="sxs-lookup"><span data-stu-id="f92b1-107">UNIX command</span></span>|<span data-ttu-id="f92b1-108">Cmdlet do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f92b1-108">PowerShell cmdlet</span></span>|<span data-ttu-id="f92b1-109">Alias do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f92b1-109">PowerShell alias</span></span>|
|---------------|----------------|--------------|------------|
|<span data-ttu-id="f92b1-110">**cls**</span><span class="sxs-lookup"><span data-stu-id="f92b1-110">**cls**</span></span>|<span data-ttu-id="f92b1-111">**clear**</span><span class="sxs-lookup"><span data-stu-id="f92b1-111">**clear**</span></span>|<span data-ttu-id="f92b1-112">`Clear-Host` (função)</span><span class="sxs-lookup"><span data-stu-id="f92b1-112">`Clear-Host` (function)</span></span>|`cls`|
|<span data-ttu-id="f92b1-113">**copy**</span><span class="sxs-lookup"><span data-stu-id="f92b1-113">**copy**</span></span>|<span data-ttu-id="f92b1-114">**cp**</span><span class="sxs-lookup"><span data-stu-id="f92b1-114">**cp**</span></span>|`Copy-Item`|`cpi`|
|<span data-ttu-id="f92b1-115">**dir**</span><span class="sxs-lookup"><span data-stu-id="f92b1-115">**dir**</span></span>|<span data-ttu-id="f92b1-116">**ls**</span><span class="sxs-lookup"><span data-stu-id="f92b1-116">**ls**</span></span>|`Get-ChildItem`|`gci`|
|<span data-ttu-id="f92b1-117">**type**</span><span class="sxs-lookup"><span data-stu-id="f92b1-117">**type**</span></span>|<span data-ttu-id="f92b1-118">**cat**</span><span class="sxs-lookup"><span data-stu-id="f92b1-118">**cat**</span></span>|`Get-Content`|`gc`|
|<span data-ttu-id="f92b1-119">**move**</span><span class="sxs-lookup"><span data-stu-id="f92b1-119">**move**</span></span>|<span data-ttu-id="f92b1-120">**mv**</span><span class="sxs-lookup"><span data-stu-id="f92b1-120">**mv**</span></span>|`Move-Item`|`mi`|
|<span data-ttu-id="f92b1-121">**md**</span><span class="sxs-lookup"><span data-stu-id="f92b1-121">**md**</span></span>|<span data-ttu-id="f92b1-122">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="f92b1-122">**mkdir**</span></span>|`New-Item`|`ni`|
|<span data-ttu-id="f92b1-123">**pushd**</span><span class="sxs-lookup"><span data-stu-id="f92b1-123">**pushd**</span></span>|<span data-ttu-id="f92b1-124">**pushd**</span><span class="sxs-lookup"><span data-stu-id="f92b1-124">**pushd**</span></span>|`Push-Location`|`pushd`|
|<span data-ttu-id="f92b1-125">**popd**</span><span class="sxs-lookup"><span data-stu-id="f92b1-125">**popd**</span></span>|<span data-ttu-id="f92b1-126">**popd**</span><span class="sxs-lookup"><span data-stu-id="f92b1-126">**popd**</span></span>|`Pop-Location`|`popd`|
|<span data-ttu-id="f92b1-127">**del**, **erase**, **rd**, **rmdir**</span><span class="sxs-lookup"><span data-stu-id="f92b1-127">**del**, **erase**, **rd**, **rmdir**</span></span>|<span data-ttu-id="f92b1-128">**rm**</span><span class="sxs-lookup"><span data-stu-id="f92b1-128">**rm**</span></span>|`Remove-Item`|`ri`|
|<span data-ttu-id="f92b1-129">**ren**</span><span class="sxs-lookup"><span data-stu-id="f92b1-129">**ren**</span></span>|<span data-ttu-id="f92b1-130">**mv**</span><span class="sxs-lookup"><span data-stu-id="f92b1-130">**mv**</span></span>|`Rename-Item`|`rni`|
|<span data-ttu-id="f92b1-131">**cd**, **chdir**</span><span class="sxs-lookup"><span data-stu-id="f92b1-131">**cd**, **chdir**</span></span>|<span data-ttu-id="f92b1-132">**cd**</span><span class="sxs-lookup"><span data-stu-id="f92b1-132">**cd**</span></span>|`Set-Location`|`sl`|

<span data-ttu-id="f92b1-133">Para localizar os aliases do PowerShell, use o cmdlet [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias).</span><span class="sxs-lookup"><span data-stu-id="f92b1-133">To find the PowerShell aliases, use the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet.</span></span> <span data-ttu-id="f92b1-134">Para exibir os aliases de um cmdlet, use o parâmetro **Definição** e especifique o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f92b1-134">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="f92b1-135">Ou, para localizar o nome do cmdlet de um alias, use o parâmetro **Name** e especifique o alias.</span><span class="sxs-lookup"><span data-stu-id="f92b1-135">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

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
