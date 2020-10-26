---
ms.date: 08/03/2020
keywords: powershell, cmdlet
title: Apêndice 1 Aliases de compatibilidade
description: O PowerShell tem vários aliases que permitem que os usuários do UNIX e cmd.exe usem comandos conhecidos.
ms.openlocfilehash: 8cbbd5a358de9018fcb5c840e711cd76f7a9a353
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500735"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="30ef8-104">Apêndice 1: Alias de compatibilidade</span><span class="sxs-lookup"><span data-stu-id="30ef8-104">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="30ef8-105">O PowerShell tem vários aliases que permitem que os usuários do **UNIX** e **cmd.exe** usem comandos conhecidos.</span><span class="sxs-lookup"><span data-stu-id="30ef8-105">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="30ef8-106">Os comandos, seus cmdlets do PowerShell e alias do PowerShell relacionados são mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="30ef8-106">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|            <span data-ttu-id="30ef8-107">comando cmd.exe</span><span class="sxs-lookup"><span data-stu-id="30ef8-107">cmd.exe command</span></span>            | <span data-ttu-id="30ef8-108">Comando UNIX</span><span class="sxs-lookup"><span data-stu-id="30ef8-108">UNIX command</span></span> | <span data-ttu-id="30ef8-109">Cmdlet do PowerShell</span><span class="sxs-lookup"><span data-stu-id="30ef8-109">PowerShell cmdlet</span></span> | <span data-ttu-id="30ef8-110">Alias do PowerShell</span><span class="sxs-lookup"><span data-stu-id="30ef8-110">PowerShell alias</span></span> |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| <span data-ttu-id="30ef8-111">**cd** , **chdir**</span><span class="sxs-lookup"><span data-stu-id="30ef8-111">**cd** , **chdir**</span></span>                     | <span data-ttu-id="30ef8-112">**cd**</span><span class="sxs-lookup"><span data-stu-id="30ef8-112">**cd**</span></span>       | `Set-Location`    | `sl`             |
| <span data-ttu-id="30ef8-113">**cls**</span><span class="sxs-lookup"><span data-stu-id="30ef8-113">**cls**</span></span>                               | <span data-ttu-id="30ef8-114">**clear**</span><span class="sxs-lookup"><span data-stu-id="30ef8-114">**clear**</span></span>    | `Clear-Host`      | `cls`            |
| <span data-ttu-id="30ef8-115">**copy**</span><span class="sxs-lookup"><span data-stu-id="30ef8-115">**copy**</span></span>                              | <span data-ttu-id="30ef8-116">**cp**</span><span class="sxs-lookup"><span data-stu-id="30ef8-116">**cp**</span></span>       | `Copy-Item`       | `cpi`            |
| <span data-ttu-id="30ef8-117">**del** , **erase** , **rd** , **rmdir**</span><span class="sxs-lookup"><span data-stu-id="30ef8-117">**del** , **erase** , **rd** , **rmdir**</span></span> | <span data-ttu-id="30ef8-118">**rm**</span><span class="sxs-lookup"><span data-stu-id="30ef8-118">**rm**</span></span>       | `Remove-Item`     | `ri`             |
| <span data-ttu-id="30ef8-119">**dir**</span><span class="sxs-lookup"><span data-stu-id="30ef8-119">**dir**</span></span>                               | <span data-ttu-id="30ef8-120">**ls**</span><span class="sxs-lookup"><span data-stu-id="30ef8-120">**ls**</span></span>       | `Get-ChildItem`   | `gci`            |
| <span data-ttu-id="30ef8-121">**echo**</span><span class="sxs-lookup"><span data-stu-id="30ef8-121">**echo**</span></span>                              | <span data-ttu-id="30ef8-122">**echo**</span><span class="sxs-lookup"><span data-stu-id="30ef8-122">**echo**</span></span>     | `Write-Output`    | `write`          |
| <span data-ttu-id="30ef8-123">**md**</span><span class="sxs-lookup"><span data-stu-id="30ef8-123">**md**</span></span>                                | <span data-ttu-id="30ef8-124">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="30ef8-124">**mkdir**</span></span>    | `New-Item`        | `ni`             |
| <span data-ttu-id="30ef8-125">**move**</span><span class="sxs-lookup"><span data-stu-id="30ef8-125">**move**</span></span>                              | <span data-ttu-id="30ef8-126">**mv**</span><span class="sxs-lookup"><span data-stu-id="30ef8-126">**mv**</span></span>       | `Move-Item`       | `mi`             |
| <span data-ttu-id="30ef8-127">**popd**</span><span class="sxs-lookup"><span data-stu-id="30ef8-127">**popd**</span></span>                              | <span data-ttu-id="30ef8-128">**popd**</span><span class="sxs-lookup"><span data-stu-id="30ef8-128">**popd**</span></span>     | `Pop-Location`    | `popd`           |
| <span data-ttu-id="30ef8-129">**pushd**</span><span class="sxs-lookup"><span data-stu-id="30ef8-129">**pushd**</span></span>                             | <span data-ttu-id="30ef8-130">**pushd**</span><span class="sxs-lookup"><span data-stu-id="30ef8-130">**pushd**</span></span>    | `Push-Location`   | `pushd`          |
| <span data-ttu-id="30ef8-131">**ren**</span><span class="sxs-lookup"><span data-stu-id="30ef8-131">**ren**</span></span>                               | <span data-ttu-id="30ef8-132">**mv**</span><span class="sxs-lookup"><span data-stu-id="30ef8-132">**mv**</span></span>       | `Rename-Item`     | `rni`            |
| <span data-ttu-id="30ef8-133">**tipo**</span><span class="sxs-lookup"><span data-stu-id="30ef8-133">**type**</span></span>                              | <span data-ttu-id="30ef8-134">**cat**</span><span class="sxs-lookup"><span data-stu-id="30ef8-134">**cat**</span></span>      | `Get-Content`     | `gc`             |

<span data-ttu-id="30ef8-135">Para localizar os aliases do PowerShell, use o cmdlet [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias).</span><span class="sxs-lookup"><span data-stu-id="30ef8-135">To find the PowerShell aliases, use the [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet.</span></span> <span data-ttu-id="30ef8-136">Para exibir os aliases de um cmdlet, use o parâmetro **Definição** e especifique o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="30ef8-136">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="30ef8-137">Ou, para localizar o nome do cmdlet de um alias, use o parâmetro **Name** e especifique o alias.</span><span class="sxs-lookup"><span data-stu-id="30ef8-137">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

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
