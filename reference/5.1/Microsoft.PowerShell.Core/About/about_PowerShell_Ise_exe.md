---
description: Explica como usar a ferramenta de linha de comando PowerShell_Ise.exe.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_ise_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Ise_exe
ms.openlocfilehash: c7500eb6d8586b9dca568edc4e805c577e94bec4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196169"
---
# <a name="about-powershell-iseexe"></a><span data-ttu-id="bb8ad-104">Sobre Ise.exe do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb8ad-104">About PowerShell Ise.exe</span></span>

## <a name="short-description"></a><span data-ttu-id="bb8ad-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="bb8ad-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="bb8ad-106">Explica como usar a ferramenta de linha de comando PowerShell_Ise.exe.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-106">Explains how to use the PowerShell_Ise.exe command-line tool.</span></span>

## <a name="long-description"></a><span data-ttu-id="bb8ad-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="bb8ad-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="bb8ad-108">PowerShell_Ise.exe inicia uma sessão de Ambiente de Script Integrado do Windows PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="bb8ad-108">PowerShell_Ise.exe starts a Windows PowerShell Integrated Scripting Environment (ISE) session.</span></span> <span data-ttu-id="bb8ad-109">Você pode executá-lo em Cmd.exe e no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-109">You can run it in Cmd.exe and in Windows PowerShell.</span></span>

<span data-ttu-id="bb8ad-110">Para executar PowerShell_ISE.exe, digite PowerShell_ISE.exe, PowerShell_ISE ou ISE.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-110">To run PowerShell_ISE.exe, type PowerShell_ISE.exe, PowerShell_ISE, or ISE.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb8ad-111">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bb8ad-111">SYNTAX</span></span>

```
PowerShell_Ise[.exe]
PowerShell_ISE[.exe]
ISE[.exe]
[-File]<FilePath[]> [-NoProfile] [-MTA]
-Help | ? | -? | /? Displays the syntax and describes the command-line switches.
```

## <a name="parameters"></a><span data-ttu-id="bb8ad-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bb8ad-112">PARAMETERS</span></span>

### <a name="-file"></a><span data-ttu-id="bb8ad-113">-File</span><span class="sxs-lookup"><span data-stu-id="bb8ad-113">-File</span></span>

<span data-ttu-id="bb8ad-114">Abre os arquivos especificados no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-114">Opens the specified files in Windows PowerShell ISE.</span></span> <span data-ttu-id="bb8ad-115">O nome do parâmetro ("-File") é opcional.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-115">The parameter name ("-File") is optional.</span></span> <span data-ttu-id="bb8ad-116">Para listar mais de um arquivo, insira uma cadeia de caracteres de texto entre aspas.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-116">To list more than one file, enter one text string enclosed in quotation marks.</span></span> <span data-ttu-id="bb8ad-117">Use vírgulas para separar os nomes de arquivo dentro da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-117">Use commas to separate the file names within the string.</span></span>

<span data-ttu-id="bb8ad-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bb8ad-118">For example:</span></span>

<span data-ttu-id="bb8ad-119">PowerShell_ISE-File "File1.ps1, File2.ps1 File3.xml".</span><span class="sxs-lookup"><span data-stu-id="bb8ad-119">PowerShell_ISE -File "File1.ps1,File2.ps1,File3.xml".</span></span>

<span data-ttu-id="bb8ad-120">Os espaços entre os nomes de arquivo são permitidos no Windows PowerShell, mas podem não ser interpretados corretamente por outros programas, como Cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-120">Spaces between the file names are permitted in Windows PowerShell, but might not be interpreted correctly by other programs, such as Cmd.exe.</span></span>

<span data-ttu-id="bb8ad-121">Você pode usar esse parâmetro para abrir qualquer arquivo de texto, incluindo arquivos de script do Windows PowerShell e arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-121">You can use this parameter to open any text file, including Windows PowerShell script files and XML files.</span></span>

### <a name="-mta"></a><span data-ttu-id="bb8ad-122">-Mta</span><span class="sxs-lookup"><span data-stu-id="bb8ad-122">-Mta</span></span>

<span data-ttu-id="bb8ad-123">Inicia ISE do Windows PowerShell usando um apartamento multi-threaded.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-123">Starts Windows PowerShell ISE using a multi-threaded apartment.</span></span> <span data-ttu-id="bb8ad-124">Este parâmetro é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-124">This parameter is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="bb8ad-125">STA (single-threaded apartment) é o padrão.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-125">Single-threaded apartment (STA) is the default.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="bb8ad-126">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="bb8ad-126">-NoProfile</span></span>

<span data-ttu-id="bb8ad-127">Não executa perfis do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-127">Does not run Windows PowerShell profiles.</span></span> <span data-ttu-id="bb8ad-128">Por padrão, os perfis do Windows PowerShell são executados em cada sessão.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-128">By default, Windows PowerShell profiles are run in every session.</span></span>

<span data-ttu-id="bb8ad-129">Esse parâmetro é recomendado quando você está gravando conteúdo compartilhado, como funções e scripts que serão executados em sistemas com perfis diferentes.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-129">This parameter is recommended when you are writing shared content, such as functions and scripts that will be run on systems with different profiles.</span></span>
<span data-ttu-id="bb8ad-130">Para obter mais informações, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="bb8ad-130">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="-help---"></a><span data-ttu-id="bb8ad-131">-Ajuda-?,/?</span><span class="sxs-lookup"><span data-stu-id="bb8ad-131">-Help -?, /?</span></span>

<span data-ttu-id="bb8ad-132">Exibe a ajuda para PowerShell_ISE.exe.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-132">Displays help for PowerShell_ISE.exe.</span></span>

## <a name="examples"></a><span data-ttu-id="bb8ad-133">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="bb8ad-133">EXAMPLES</span></span>

<span data-ttu-id="bb8ad-134">Esses comandos iniciam ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-134">These commands start Windows PowerShell ISE.</span></span> <span data-ttu-id="bb8ad-135">Os comandos são equivalentes e podem ser usados intercambiavelmente.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-135">The commands are equivalent and can be used interchangeably.</span></span>

```
PS C:> PowerShell_ISE.exe
PS C:> PowerShell_ISE
PS C:> ISE
```

<span data-ttu-id="bb8ad-136">Esses comandos abrem o script Get-Profile.ps1 no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-136">These commands open the Get-Profile.ps1 script in Windows PowerShell ISE.</span></span>
<span data-ttu-id="bb8ad-137">Os comandos são equivalentes e podem ser usados intercambiavelmente.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-137">The commands are equivalent and can be used interchangeably.</span></span>

```
PS C:> PowerShell_ISE.exe -File .\Get-Profile.ps1
PS C:> ISE -File .\Get-Profile.ps1
PS C:> ISE .\Get-Profile.ps1
```

<span data-ttu-id="bb8ad-138">Esse comando abre o Get-Backups.ps1 e Get-BackupInstance.ps1 scripts no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-138">This command opens the Get-Backups.ps1 and Get-BackupInstance.ps1 scripts in Windows PowerShell ISE.</span></span> <span data-ttu-id="bb8ad-139">Para abrir mais de um arquivo, use uma vírgula para separar os nomes de arquivo e coloque o valor do nome de arquivo inteiro entre aspas.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-139">To open more than one file, use a comma to separate the file names and enclose the entire file name value in quotation marks.</span></span>

```
PS C:> ISE -File ".\Get-Backups.ps1,Get-BackupInstance.ps1"
```

<span data-ttu-id="bb8ad-140">Este comando inicia ISE do Windows PowerShell sem perfis.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-140">This command starts Windows PowerShell ISE with no profiles.</span></span>

```
PS C:> ISE -NoProfile
```

<span data-ttu-id="bb8ad-141">Este comando obtém ajuda para PowerShell_ISE.exe.</span><span class="sxs-lookup"><span data-stu-id="bb8ad-141">This command gets help for PowerShell_ISE.exe.</span></span>

```
PS C:> ISE -help
```

## <a name="see-also"></a><span data-ttu-id="bb8ad-142">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="bb8ad-142">SEE ALSO</span></span>

[<span data-ttu-id="bb8ad-143">about_PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="bb8ad-143">about_PowerShell.exe</span></span>](about_PowerShell_exe.md)

[<span data-ttu-id="bb8ad-144">about_Windows_PowerShell_ISE</span><span class="sxs-lookup"><span data-stu-id="bb8ad-144">about_Windows_PowerShell_ISE</span></span>](about_Windows_PowerShell_ISE.md)

[<span data-ttu-id="bb8ad-145">Ambiente de Script Integrado do Windows PowerShell (ISE)</span><span class="sxs-lookup"><span data-stu-id="bb8ad-145">Windows PowerShell Integrated Scripting Environment (ISE)</span></span>](/powershell/scripting/windows-powershell/ise/introducing-the-windows-powershell-ise)
