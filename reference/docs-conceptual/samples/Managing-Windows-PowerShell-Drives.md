---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Gerenciando unidades do Windows PowerShell
description: Uma unidade do PowerShell é um local de armazenamento de dados que pode ser acessado como uma unidade de sistema de arquivos no PowerShell. Por padrão, o PowerShell inclui provedores que dão suporte ao sistema de arquivos, ao Registro, aos repositórios de certificados e a outros.
ms.openlocfilehash: e4e5347c3f3458f25cea31c8e5a499474985220a
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500327"
---
# <a name="managing-windows-powershell-drives"></a><span data-ttu-id="aeecd-105">Gerenciando unidades do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aeecd-105">Managing Windows PowerShell Drives</span></span>

<span data-ttu-id="aeecd-106">Uma *unidade do Windows PowerShell* é um local de armazenamento de dados que pode ser acessado como uma unidade de sistema de arquivos no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aeecd-106">A *Windows PowerShell drive* is a data store location that you can access like a file system drive in Windows PowerShell.</span></span> <span data-ttu-id="aeecd-107">Provedores do Windows PowerShell criam algumas unidades, como unidades de sistema de arquivos (inclusive C: e D:), as unidades do registro (HKCU: e HKLM:) e a unidade de certificado (Cert:), e você também pode criar suas próprias unidades no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aeecd-107">The Windows PowerShell providers create some drives for you, such as the file system drives (including C: and D:), the registry drives (HKCU: and HKLM:), and the certificate drive (Cert:), and you can create your own Windows PowerShell drives.</span></span> <span data-ttu-id="aeecd-108">Essas unidades são muito úteis, mas estão disponíveis apenas no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aeecd-108">These drives are very useful, but they are available only within Windows PowerShell.</span></span> <span data-ttu-id="aeecd-109">Você não poderá acessá-las usando outras ferramentas do Windows, como o Explorador de Arquivos ou Cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="aeecd-109">You cannot access them by using other Windows tools, such as File Explorer or Cmd.exe.</span></span>

<span data-ttu-id="aeecd-110">O Windows PowerShell usa o substantivo **PSDrive** para comandos que funcionam com o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aeecd-110">Windows PowerShell uses the noun, **PSDrive** , for commands that work with Windows PowerShell drives.</span></span> <span data-ttu-id="aeecd-111">Para ver uma lista de unidades do Windows PowerShell presentes na sua sessão do Windows PowerShell, use o cmdlet **Get-PSDrive** .</span><span class="sxs-lookup"><span data-stu-id="aeecd-111">For a list of the Windows PowerShell drives in your Windows PowerShell session, use the **Get-PSDrive** cmdlet.</span></span>

```
PS> Get-PSDrive

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
A          FileSystem    A:\
Alias      Alias
C          FileSystem    C:\                                 ...And Settings\me
cert       Certificate   \
D          FileSystem    D:\
Env        Environment
Function   Function
HKCU       Registry      HKEY_CURRENT_USER
HKLM       Registry      HKEY_LOCAL_MACHINE
Variable   Variable
```

<span data-ttu-id="aeecd-112">Embora as unidades na exibição variem de acordo com as unidades no sistema, a listagem será semelhante à saída do comando **Get-PSDrive** mostrado acima.</span><span class="sxs-lookup"><span data-stu-id="aeecd-112">Although the drives in the display vary with the drives on your system, the listing will look similar to the output of the **Get-PSDrive** command shown above.</span></span>

<span data-ttu-id="aeecd-113">Unidades do sistema de arquivos são um subconjunto das unidades do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aeecd-113">File system drives are a subset of the Windows PowerShell drives.</span></span> <span data-ttu-id="aeecd-114">Você pode identificar as unidades de sistema de arquivo pela entrada FileSystem na coluna de Provider.</span><span class="sxs-lookup"><span data-stu-id="aeecd-114">You can identify the file system drives by the FileSystem entry in the Provider column.</span></span> <span data-ttu-id="aeecd-115">(As unidades do sistema de arquivo no Windows PowerShell têm suporte no provedor do sistema de arquivos do Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="aeecd-115">(The file system drives in Windows PowerShell are supported by the Windows PowerShell FileSystem provider.)</span></span>

<span data-ttu-id="aeecd-116">Para ver a sintaxe do cmdlet **Get-PSDrive** , digite um comando **Get-Command** com o parâmetro **Syntax** :</span><span class="sxs-lookup"><span data-stu-id="aeecd-116">To see the syntax of the **Get-PSDrive** cmdlet, type a **Get-Command** command with the **Syntax** parameter:</span></span>

```
PS> Get-Command -Name Get-PSDrive -Syntax

Get-PSDrive [[-Name] <String[]>] [-Scope <String>] [-PSProvider <String[]>] [-V
erbose] [-Debug] [-ErrorAction <ActionPreference>] [-ErrorVariable <String>] [-
OutVariable <String>] [-OutBuffer <Int32>]
```

<span data-ttu-id="aeecd-117">O parâmetro **PSProvider** permite exibir somente as unidades do Windows PowerShell suportadas por um provedor específico.</span><span class="sxs-lookup"><span data-stu-id="aeecd-117">The **PSProvider** parameter lets you display only the Windows PowerShell drives that are supported by a particular provider.</span></span> <span data-ttu-id="aeecd-118">Por exemplo, para exibir somente unidades do Windows PowerShell suportadas pelo provedor do Sistema de Arquivos do Windows PowerShell, digite um comando **Get-PSDrive** com o parâmetro **PSProvider** e valor **FileSystem** :</span><span class="sxs-lookup"><span data-stu-id="aeecd-118">For example, to display only the Windows PowerShell drives that are supported by the Windows PowerShell FileSystem provider, type a **Get-PSDrive** command with the **PSProvider** parameter and the **FileSystem** value:</span></span>

```
PS> Get-PSDrive -PSProvider FileSystem

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
A          FileSystem    A:\
C          FileSystem    C:\                           ...nd Settings\PowerUser
D          FileSystem    D:\
```

<span data-ttu-id="aeecd-119">Para exibir as unidades do Windows PowerShell que representam os hives do registro, use o parâmetro **PSProvider** para exibir somente as unidades do Windows PowerShell que possuem suporte no provedor de registro do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="aeecd-119">To view the Windows PowerShell drives that represent registry hives, use the **PSProvider** parameter to display only the Windows PowerShell drives that are supported by the Windows PowerShell Registry provider:</span></span>

```
PS> Get-PSDrive -PSProvider Registry

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
HKCU       Registry      HKEY_CURRENT_USER
HKLM       Registry      HKEY_LOCAL_MACHINE
```

<span data-ttu-id="aeecd-120">Você também pode usar o cmdlets Location padrão com as unidades do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="aeecd-120">You can also use the standard Location cmdlets with the Windows PowerShell drives:</span></span>

```
PS> Set-Location HKLM:\SOFTWARE
PS> Push-Location .\Microsoft
PS> Get-Location

Path
----
HKLM:\SOFTWARE\Microsoft
```

## <a name="adding-new-windows-powershell-drives-new-psdrive"></a><span data-ttu-id="aeecd-121">Adicionando novas unidades do Windows PowerShell (New-PSDrive)</span><span class="sxs-lookup"><span data-stu-id="aeecd-121">Adding New Windows PowerShell Drives (New-PSDrive)</span></span>

<span data-ttu-id="aeecd-122">Você pode adicionar suas próprias unidades do Windows PowerShell usando o comando **New-PSDrive** .</span><span class="sxs-lookup"><span data-stu-id="aeecd-122">You can add your own Windows PowerShell drives by using the **New-PSDrive** command.</span></span> <span data-ttu-id="aeecd-123">Para ver a sintaxe do comando **New-PSDrive** , digite o comando **Get-Command** com o parâmetro **Syntax** :</span><span class="sxs-lookup"><span data-stu-id="aeecd-123">To get the syntax for the **New-PSDrive** command, enter the **Get-Command** command with the **Syntax** parameter:</span></span>

```
PS> Get-Command -Name New-PSDrive -Syntax

New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Descript
ion <String>] [-Scope <String>] [-Credential <PSCredential>] [-Verbose] [-Debug
] [-ErrorAction <ActionPreference>] [-ErrorVariable <String>] [-OutVariable <St
ring>] [-OutBuffer <Int32>] [-WhatIf] [-Confirm]
```

<span data-ttu-id="aeecd-124">Para criar uma nova unidade do Windows PowerShell, você deve fornecer três parâmetros:</span><span class="sxs-lookup"><span data-stu-id="aeecd-124">To create a new Windows PowerShell drive, you must supply three parameters:</span></span>

- <span data-ttu-id="aeecd-125">Um nome para a unidade (você pode usar qualquer nome válido do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="aeecd-125">A name for the drive (you can use any valid Windows PowerShell name)</span></span>

- <span data-ttu-id="aeecd-126">O PSProvider (use "FileSystem" para locais de sistema de arquivos e "Registry" para locais de registro)</span><span class="sxs-lookup"><span data-stu-id="aeecd-126">The PSProvider (use "FileSystem" for file system locations and "Registry" for registry locations)</span></span>

- <span data-ttu-id="aeecd-127">A raiz, ou seja, o caminho para a raiz da unidade nova</span><span class="sxs-lookup"><span data-stu-id="aeecd-127">The root, that is, the path to the root of the new drive</span></span>

<span data-ttu-id="aeecd-128">Por exemplo, você pode criar uma unidade chamada “Office” mapeada para a pasta que contém os aplicativos do Microsoft Office em seu computador, como **C:\\Arquivos de Programas\\Microsoft Office\\OFFICE11** .</span><span class="sxs-lookup"><span data-stu-id="aeecd-128">For example, you can create a drive named "Office" that is mapped to the folder that contains the Microsoft Office applications on your computer, such as **C:\\Program Files\\Microsoft Office\\OFFICE11** .</span></span> <span data-ttu-id="aeecd-129">Para criar a unidade, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="aeecd-129">To create the drive, type the following command:</span></span>

```
PS> New-PSDrive -Name Office -PSProvider FileSystem -Root "C:\Program Files\Microsoft Office\OFFICE11"

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
Office     FileSystem    C:\Program Files\Microsoft Offic...
```

> [!NOTE]
> <span data-ttu-id="aeecd-130">Em geral, os caminhos não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="aeecd-130">In general, paths are not case-sensitive.</span></span>

<span data-ttu-id="aeecd-131">Referencie a nova unidade do Windows PowerShell como todas as demais unidades do Windows PowerShell: pelo nome seguido por dois pontos ( **:** ).</span><span class="sxs-lookup"><span data-stu-id="aeecd-131">You refer to the new Windows PowerShell drive as you do all Windows PowerShell drives -- by its name followed by a colon ( **:** ).</span></span>

<span data-ttu-id="aeecd-132">Uma unidade do Windows PowerShell pode tornar diversas tarefas muito mais simples.</span><span class="sxs-lookup"><span data-stu-id="aeecd-132">A Windows PowerShell drive can make many tasks much simpler.</span></span> <span data-ttu-id="aeecd-133">Por exemplo, algumas das chaves mais importantes no registro do Windows têm caminhos extremamente longos, tornando-os complicados de acessar e difíceis de serem lembradas.</span><span class="sxs-lookup"><span data-stu-id="aeecd-133">For example, some of the most important keys in the Windows registry have extremely long paths, making them cumbersome to access and difficult to remember.</span></span> <span data-ttu-id="aeecd-134">Informações de configuração crítica residem em **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion** .</span><span class="sxs-lookup"><span data-stu-id="aeecd-134">Critical configuration information resides under **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion** .</span></span> <span data-ttu-id="aeecd-135">Para exibir e alterar itens na chave do registro CurrentVersion, você pode criar uma unidade do Windows PowerShell que está enraizada na chave digitando:</span><span class="sxs-lookup"><span data-stu-id="aeecd-135">To view and change items in the CurrentVersion registry key, you can create a Windows PowerShell drive that is rooted in that key by typing:</span></span>

```
PS> New-PSDrive -Name cvkey -PSProvider Registry -Root HKLM\Software\Microsoft\Windows\CurrentVersion

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
cvkey      Registry      HKLM\Software\Microsoft\Windows\...
```

<span data-ttu-id="aeecd-136">Você poderá então alterar o local para a unidade **cvkey:** , tal como faria com qualquer outra unidade:</span><span class="sxs-lookup"><span data-stu-id="aeecd-136">You can then change location to the **cvkey:** drive as you would any other drive:</span></span>

```
PS> cd cvkey:
```

<span data-ttu-id="aeecd-137">ou:</span><span class="sxs-lookup"><span data-stu-id="aeecd-137">or:</span></span>

```
PS> Set-Location cvkey: -PassThru

Path
----
cvkey:\
```

<span data-ttu-id="aeecd-138">O cmdlet New-PsDrive adiciona a nova unidade apenas à sessão atual do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aeecd-138">The New-PsDrive cmdlet adds the new drive only to the current Windows PowerShell session.</span></span> <span data-ttu-id="aeecd-139">Se você fechar a janela do Windows PowerShell, a nova unidade será perdida.</span><span class="sxs-lookup"><span data-stu-id="aeecd-139">If you close the Windows PowerShell window, the new drive is lost.</span></span> <span data-ttu-id="aeecd-140">Para salvar uma unidade do Windows PowerShell, use o cmdlet Export-Console para exportar a sessão atual do Windows PowerShell e use o parâmetro **PSConsoleFile** do PowerShell.exe para importá-la.</span><span class="sxs-lookup"><span data-stu-id="aeecd-140">To save a Windows PowerShell drive, use the Export-Console cmdlet to export the current Windows PowerShell session, and then use the PowerShell.exe **PSConsoleFile** parameter to import it.</span></span> <span data-ttu-id="aeecd-141">Ou então, adicione a nova unidade ao seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aeecd-141">Or, add the new drive to your Windows PowerShell profile.</span></span>

## <a name="deleting-windows-powershell-drives-remove-psdrive"></a><span data-ttu-id="aeecd-142">Excluindo unidades do Windows PowerShell (Remove-PSDrive)</span><span class="sxs-lookup"><span data-stu-id="aeecd-142">Deleting Windows PowerShell Drives (Remove-PSDrive)</span></span>

<span data-ttu-id="aeecd-143">Você pode excluir unidades do Windows PowerShell usando o cmdlet **Remove-PSDrive** .</span><span class="sxs-lookup"><span data-stu-id="aeecd-143">You can delete drives from Windows PowerShell by using the **Remove-PSDrive** cmdlet.</span></span> <span data-ttu-id="aeecd-144">O cmdlet **Remove-PSDrive** é fácil de usar. Para excluir uma unidade específica do Windows PowerShell, basta fornecer o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="aeecd-144">The **Remove-PSDrive** cmdlet is easy to use; to delete a specific Windows PowerShell drive, you just supply the Windows PowerShell drive name.</span></span>

<span data-ttu-id="aeecd-145">Por exemplo, se adicionar a unidade **Office:** ao Windows PowerShell, como mostrado no tópico **New-PSDrive** , você poderá excluí-la digitando:</span><span class="sxs-lookup"><span data-stu-id="aeecd-145">For example, if you added the **Office:** Windows PowerShell drive, as shown in the **New-PSDrive** topic, you can delete it by typing:</span></span>

```powershell
Remove-PSDrive -Name Office
```

<span data-ttu-id="aeecd-146">Para excluir a unidade **cvkey:** do Windows PowerShell, também mostrada no tópico **New-PSDrive** , use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="aeecd-146">To delete the **cvkey:** Windows PowerShell drive, also shown in the **New-PSDrive** topic, use the following command:</span></span>

```powershell
Remove-PSDrive -Name cvkey
```

<span data-ttu-id="aeecd-147">É muito fácil excluir uma unidade do Windows PowerShell, mas não é possível excluí-la enquanto você estiver na unidade.</span><span class="sxs-lookup"><span data-stu-id="aeecd-147">It's easy to delete a Windows PowerShell drive, but you can't delete it while you are in the drive.</span></span> <span data-ttu-id="aeecd-148">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="aeecd-148">For example:</span></span>

```
PS> cd office:
PS Office:\> remove-psdrive -name office
Remove-PSDrive : Cannot remove drive 'Office' because it is in use.
At line:1 char:15
+ remove-psdrive  <<<< -name office
```

## <a name="adding-and-removing-drives-outside-windows-powershell"></a><span data-ttu-id="aeecd-149">Adicionando e removendo unidades externas ao Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aeecd-149">Adding and Removing Drives Outside Windows PowerShell</span></span>

<span data-ttu-id="aeecd-150">O Windows PowerShell detecta as unidades do sistema de arquivos que foram adicionados ou removidas no Windows, incluindo unidades de rede mapeadas, unidades USB conectadas e unidades excluídas usando o comando **net use** ou os métodos **WScript.NetworkMapNetworkDrive** e **RemoveNetworkDrive** de um script do Windows Script Host (WSH).</span><span class="sxs-lookup"><span data-stu-id="aeecd-150">Windows PowerShell detects file system drives that are added or removed in Windows, including network drives that are mapped, USB drives that are attached, and drives that are deleted by using either the **net use** command or the **WScript.NetworkMapNetworkDrive** and **RemoveNetworkDrive** methods from a Windows Script Host (WSH) script.</span></span>
