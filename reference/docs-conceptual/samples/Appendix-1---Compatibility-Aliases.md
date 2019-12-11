---
ms.date: 09/09/2019
keywords: powershell, cmdlet
title: Apêndice 1 Aliases de compatibilidade
ms.openlocfilehash: 2351fdf23711fe1417f7e3fc3cca5b642d5a59fc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "70848170"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="7ee5c-103">Apêndice 1: Alias de compatibilidade</span><span class="sxs-lookup"><span data-stu-id="7ee5c-103">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="7ee5c-104">O PowerShell tem vários aliases que permitem que os usuários do **UNIX** e **cmd.exe** usem comandos conhecidos.</span><span class="sxs-lookup"><span data-stu-id="7ee5c-104">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="7ee5c-105">Os comandos, seus cmdlets do PowerShell e alias do PowerShell relacionados são mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="7ee5c-105">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|<span data-ttu-id="7ee5c-106">comando cmd.exe</span><span class="sxs-lookup"><span data-stu-id="7ee5c-106">cmd.exe command</span></span>|<span data-ttu-id="7ee5c-107">Comando UNIX</span><span class="sxs-lookup"><span data-stu-id="7ee5c-107">UNIX command</span></span>|<span data-ttu-id="7ee5c-108">Cmdlet do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ee5c-108">PowerShell cmdlet</span></span>|<span data-ttu-id="7ee5c-109">Alias do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ee5c-109">PowerShell alias</span></span>|
|---------------|----------------|--------------|------------|
|<span data-ttu-id="7ee5c-110">**cls**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-110">**cls**</span></span>|<span data-ttu-id="7ee5c-111">**clear**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-111">**clear**</span></span>|<span data-ttu-id="7ee5c-112">`Clear-Host` (função)</span><span class="sxs-lookup"><span data-stu-id="7ee5c-112">`Clear-Host` (function)</span></span>|`cls`|
|<span data-ttu-id="7ee5c-113">**copy**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-113">**copy**</span></span>|<span data-ttu-id="7ee5c-114">**cp**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-114">**cp**</span></span>|`Copy-Item`|`cpi`|
|<span data-ttu-id="7ee5c-115">**dir**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-115">**dir**</span></span>|<span data-ttu-id="7ee5c-116">**ls**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-116">**ls**</span></span>|`Get-ChildItem`|`gci`|
|<span data-ttu-id="7ee5c-117">**type**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-117">**type**</span></span>|<span data-ttu-id="7ee5c-118">**cat**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-118">**cat**</span></span>|`Get-Content`|`gc`|
|<span data-ttu-id="7ee5c-119">**move**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-119">**move**</span></span>|<span data-ttu-id="7ee5c-120">**mv**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-120">**mv**</span></span>|`Move-Item`|`mi`|
|<span data-ttu-id="7ee5c-121">**md**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-121">**md**</span></span>|<span data-ttu-id="7ee5c-122">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-122">**mkdir**</span></span>|`New-Item`|`ni`|
|<span data-ttu-id="7ee5c-123">**pushd**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-123">**pushd**</span></span>|<span data-ttu-id="7ee5c-124">**pushd**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-124">**pushd**</span></span>|`Push-Location`|`pushd`|
|<span data-ttu-id="7ee5c-125">**popd**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-125">**popd**</span></span>|<span data-ttu-id="7ee5c-126">**popd**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-126">**popd**</span></span>|`Pop-Location`|`popd`|
|<span data-ttu-id="7ee5c-127">**del**, **erase**, **rd**, **rmdir**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-127">**del**, **erase**, **rd**, **rmdir**</span></span>|<span data-ttu-id="7ee5c-128">**rm**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-128">**rm**</span></span>|`Remove-Item`|`ri`|
|<span data-ttu-id="7ee5c-129">**ren**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-129">**ren**</span></span>|<span data-ttu-id="7ee5c-130">**mv**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-130">**mv**</span></span>|`Rename-Item`|`rni`|
|<span data-ttu-id="7ee5c-131">**cd**, **chdir**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-131">**cd**, **chdir**</span></span>|<span data-ttu-id="7ee5c-132">**cd**</span><span class="sxs-lookup"><span data-stu-id="7ee5c-132">**cd**</span></span>|`Set-Location`|`sl`|

<span data-ttu-id="7ee5c-133">Para localizar os aliases do PowerShell, use o cmdlet [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias).</span><span class="sxs-lookup"><span data-stu-id="7ee5c-133">To find the PowerShell aliases, use the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet.</span></span> <span data-ttu-id="7ee5c-134">Para exibir os aliases de um cmdlet, use o parâmetro **Definição** e especifique o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7ee5c-134">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="7ee5c-135">Ou, para localizar o nome do cmdlet de um alias, use o parâmetro **Name** e especifique o alias.</span><span class="sxs-lookup"><span data-stu-id="7ee5c-135">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

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
