---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-Item
ms.openlocfilehash: 4c15ea0fd9c3fb3837ec2a23e8278016858df09d
ms.sourcegitcommit: 33ac34789e86ffb4e7e69453ae38fc0bd24933dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "93195273"
---
# <span data-ttu-id="54bce-103">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="54bce-103">Copy-Item</span></span>

## <span data-ttu-id="54bce-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="54bce-104">SYNOPSIS</span></span>
<span data-ttu-id="54bce-105">Copia um item de um local para outro.</span><span class="sxs-lookup"><span data-stu-id="54bce-105">Copies an item from one location to another.</span></span>

## <span data-ttu-id="54bce-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="54bce-106">SYNTAX</span></span>

### <span data-ttu-id="54bce-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="54bce-107">Path (Default)</span></span>

```
Copy-Item [-Path] <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [-FromSession <PSSession>] [-ToSession <PSSession>]
 [<CommonParameters>]
```

### <span data-ttu-id="54bce-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="54bce-108">LiteralPath</span></span>

```
Copy-Item -LiteralPath <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [-FromSession <PSSession>] [-ToSession <PSSession>]
 [<CommonParameters>]
```

## <span data-ttu-id="54bce-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="54bce-109">DESCRIPTION</span></span>

<span data-ttu-id="54bce-110">O `Copy-Item` cmdlet copia um item de um local para outro local no mesmo namespace.</span><span class="sxs-lookup"><span data-stu-id="54bce-110">The `Copy-Item` cmdlet copies an item from one location to another location in the same namespace.</span></span>
<span data-ttu-id="54bce-111">Por exemplo, ele pode copiar um arquivo para uma pasta, mas não pode copiar um arquivo para uma unidade de certificado.</span><span class="sxs-lookup"><span data-stu-id="54bce-111">For instance, it can copy a file to a folder, but it can't copy a file to a certificate drive.</span></span>

<span data-ttu-id="54bce-112">Esse cmdlet não recorta nem exclui os itens que estão sendo copiados.</span><span class="sxs-lookup"><span data-stu-id="54bce-112">This cmdlet doesn't cut or delete the items being copied.</span></span> <span data-ttu-id="54bce-113">Os itens específicos que o cmdlet pode copiar dependem do provedor do PowerShell que expõe o item.</span><span class="sxs-lookup"><span data-stu-id="54bce-113">The particular items that the cmdlet can copy depend on the PowerShell provider that exposes the item.</span></span> <span data-ttu-id="54bce-114">Por exemplo, ele pode copiar arquivos e diretórios em uma unidade do sistema de arquivos e chaves do registro e entradas na unidade do registro.</span><span class="sxs-lookup"><span data-stu-id="54bce-114">For instance, it can copy files and directories in a file system drive and registry keys and entries in the registry drive.</span></span>

<span data-ttu-id="54bce-115">Esse cmdlet pode copiar e renomear itens no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="54bce-115">This cmdlet can copy and rename items in the same command.</span></span> <span data-ttu-id="54bce-116">Para renomear um item, insira o novo nome no valor do parâmetro de **destino** .</span><span class="sxs-lookup"><span data-stu-id="54bce-116">To rename an item, enter the new name in the value of the **Destination** parameter.</span></span> <span data-ttu-id="54bce-117">Para renomear um item e não copiá-lo, use o `Rename-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="54bce-117">To rename an item and not copy it, use the `Rename-Item` cmdlet.</span></span>

## <span data-ttu-id="54bce-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="54bce-118">EXAMPLES</span></span>

### <span data-ttu-id="54bce-119">Exemplo 1: copiar um arquivo para o diretório especificado</span><span class="sxs-lookup"><span data-stu-id="54bce-119">Example 1: Copy a file to the specified directory</span></span>

<span data-ttu-id="54bce-120">Este exemplo copia o `mar1604.log.txt` arquivo para o `C:\Presentation` diretório.</span><span class="sxs-lookup"><span data-stu-id="54bce-120">This example copies the `mar1604.log.txt` file to the `C:\Presentation` directory.</span></span> <span data-ttu-id="54bce-121">O arquivo original não é excluído.</span><span class="sxs-lookup"><span data-stu-id="54bce-121">The original file isn't deleted.</span></span>

```powershell
Copy-Item "C:\Wabash\Logfiles\mar1604.log.txt" -Destination "C:\Presentation"
```

### <span data-ttu-id="54bce-122">Exemplo 2: copiar o conteúdo do diretório para um diretório existente</span><span class="sxs-lookup"><span data-stu-id="54bce-122">Example 2: Copy directory contents to an existing directory</span></span>

<span data-ttu-id="54bce-123">Este exemplo copia o conteúdo do `C:\Logfiles` diretório para o diretório existente `C:\Drawings` .</span><span class="sxs-lookup"><span data-stu-id="54bce-123">This example copies the contents of the `C:\Logfiles` directory into the existing `C:\Drawings` directory.</span></span> <span data-ttu-id="54bce-124">O `Logfiles` diretório não é copiado.</span><span class="sxs-lookup"><span data-stu-id="54bce-124">The `Logfiles` directory isn't copied.</span></span>

<span data-ttu-id="54bce-125">Se o `Logfiles` diretório contiver arquivos em subdiretórios, esses subdiretórios serão copiados com suas árvores de arquivo intactas.</span><span class="sxs-lookup"><span data-stu-id="54bce-125">If the `Logfiles` directory contains files in subdirectories, those subdirectories are copied with their file trees intact.</span></span> <span data-ttu-id="54bce-126">Por padrão, o parâmetro de **contêiner** é definido como **true** , o que preserva a estrutura de diretórios.</span><span class="sxs-lookup"><span data-stu-id="54bce-126">By default, the **Container** parameter is set to **True** , which preserves the directory structure.</span></span>

```powershell
Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings" -Recurse
```

> [!NOTE]
> <span data-ttu-id="54bce-127">Se você precisar incluir o `Logfiles` diretório na cópia, remova o `\*` do **caminho** .</span><span class="sxs-lookup"><span data-stu-id="54bce-127">If you need to include the `Logfiles` directory in the copy, remove the `\*` from the **Path** .</span></span>
> <span data-ttu-id="54bce-128">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="54bce-128">For example:</span></span>
>
> `Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings" -Recurse`

### <span data-ttu-id="54bce-129">Exemplo 3: copiar diretório e conteúdo para um novo diretório</span><span class="sxs-lookup"><span data-stu-id="54bce-129">Example 3: Copy directory and contents to a new directory</span></span>

<span data-ttu-id="54bce-130">Este exemplo copia o conteúdo do `C:\Logfiles` diretório de origem e cria um novo diretório de destino.</span><span class="sxs-lookup"><span data-stu-id="54bce-130">This example copies the contents of the `C:\Logfiles` source directory and creates a new destination directory.</span></span> <span data-ttu-id="54bce-131">O novo diretório de destino, `\Logs` é criado no `C:\Drawings` .</span><span class="sxs-lookup"><span data-stu-id="54bce-131">The new destination directory, `\Logs` is created in `C:\Drawings`.</span></span>

<span data-ttu-id="54bce-132">Para incluir o nome do diretório de origem, copie para um diretório de destino existente, conforme mostrado no **exemplo 2** .</span><span class="sxs-lookup"><span data-stu-id="54bce-132">To include the source directory's name, copy to an existing destination directory as shown in **Example 2** .</span></span> <span data-ttu-id="54bce-133">Ou, nomeie o novo diretório de destino com o mesmo diretório de origem.</span><span class="sxs-lookup"><span data-stu-id="54bce-133">Or, name the new destination directory with the same as the source directory.</span></span>

```powershell
Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings\Logs" -Recurse
```

> [!NOTE]
> <span data-ttu-id="54bce-134">Se o **caminho** incluir `\*` , todo o conteúdo do arquivo do diretório, incluindo as árvores de subdiretórios, será copiado para o novo diretório de destino.</span><span class="sxs-lookup"><span data-stu-id="54bce-134">If the **Path** includes `\*`, all the directory's file contents, including the subdirectory trees, are copied to the new destination directory.</span></span> <span data-ttu-id="54bce-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="54bce-135">For example:</span></span>
>
> `Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings\Logs" -Recurse`

### <span data-ttu-id="54bce-136">Exemplo 4: copiar um arquivo para o diretório especificado e renomear o arquivo</span><span class="sxs-lookup"><span data-stu-id="54bce-136">Example 4: Copy a file to the specified directory and rename the file</span></span>

<span data-ttu-id="54bce-137">Este exemplo usa o `Copy-Item` cmdlet para copiar o `Get-Widget.ps1` script do `\\Server01\Share` diretório para o `\\Server12\ScriptArchive` diretório.</span><span class="sxs-lookup"><span data-stu-id="54bce-137">This example uses the `Copy-Item` cmdlet to copy the `Get-Widget.ps1` script from the `\\Server01\Share` directory to the `\\Server12\ScriptArchive` directory.</span></span> <span data-ttu-id="54bce-138">Como parte da operação de cópia, o comando altera o nome do item de `Get-Widget.ps1` para `Get-Widget.ps1.txt` , para que ele possa ser anexado a mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="54bce-138">As part of the copy operation, the command changes the item name from `Get-Widget.ps1` to `Get-Widget.ps1.txt`, so it can be attached to email messages.</span></span>

```powershell
Copy-Item "\\Server01\Share\Get-Widget.ps1" -Destination "\\Server12\ScriptArchive\Get-Widget.ps1.txt"
```

### <span data-ttu-id="54bce-139">Exemplo 5: copiar um arquivo para um computador remoto</span><span class="sxs-lookup"><span data-stu-id="54bce-139">Example 5: Copy a file to a remote computer</span></span>

<span data-ttu-id="54bce-140">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="54bce-140">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="54bce-141">O `Copy-Item` cmdlet copia `test.log` da `D:\Folder001` pasta para a `C:\Folder001_Copy` pasta no computador remoto usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="54bce-141">The `Copy-Item` cmdlet copies `test.log` from the `D:\Folder001` folder to the `C:\Folder001_Copy` folder on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="54bce-142">O arquivo original não é excluído.</span><span class="sxs-lookup"><span data-stu-id="54bce-142">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "D:\Folder001\test.log" -Destination "C:\Folder001_Copy\" -ToSession $Session
```

### <span data-ttu-id="54bce-143">Exemplo 6: copiar uma pasta para um computador remoto</span><span class="sxs-lookup"><span data-stu-id="54bce-143">Example 6: Copy a folder to a remote computer</span></span>

<span data-ttu-id="54bce-144">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="54bce-144">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="54bce-145">O `Copy-Item` cmdlet copia a `D:\Folder002` pasta para o `C:\Folder002_Copy` diretório no computador remoto usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="54bce-145">The `Copy-Item` cmdlet copies the `D:\Folder002` folder to the `C:\Folder002_Copy` directory on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="54bce-146">Todas as subpastas ou arquivos não são copiados sem usar a opção **recurse** .</span><span class="sxs-lookup"><span data-stu-id="54bce-146">Any subfolders or files are not copied without using the **Recurse** switch.</span></span>
<span data-ttu-id="54bce-147">A operação criará a `Folder002_Copy` pasta se ela ainda não existir.</span><span class="sxs-lookup"><span data-stu-id="54bce-147">The operation creates the `Folder002_Copy` folder if it doesn't already exist.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server02" -Credential "Contoso\User01"
Copy-Item "D:\Folder002\" -Destination "C:\Folder002_Copy\" -ToSession $Session
```

### <span data-ttu-id="54bce-148">Exemplo 7: copiar recursivamente todo o conteúdo de uma pasta para um computador remoto</span><span class="sxs-lookup"><span data-stu-id="54bce-148">Example 7: Recursively copy the entire contents of a folder to a remote computer</span></span>

<span data-ttu-id="54bce-149">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="54bce-149">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="54bce-150">O `Copy-Item` cmdlet copia todo o conteúdo da `D:\Folder003` pasta para o `C:\Folder003_Copy` diretório no computador remoto usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="54bce-150">The `Copy-Item` cmdlet copies the entire contents from the `D:\Folder003` folder to the `C:\Folder003_Copy` directory on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="54bce-151">As subpastas são copiadas com suas árvores de arquivo intactas.</span><span class="sxs-lookup"><span data-stu-id="54bce-151">The subfolders are copied with their file trees intact.</span></span> <span data-ttu-id="54bce-152">A operação criará a `Folder003_Copy` pasta se ela ainda não existir.</span><span class="sxs-lookup"><span data-stu-id="54bce-152">The operation creates the `Folder003_Copy` folder if it doesn't already exist.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder003\" -Destination "C:\Folder003_Copy\" -ToSession $Session -Recurse
```

### <span data-ttu-id="54bce-153">Exemplo 8: copiar um arquivo para um computador remoto e, em seguida, renomear o arquivo</span><span class="sxs-lookup"><span data-stu-id="54bce-153">Example 8: Copy a file to a remote computer and then rename the file</span></span>

<span data-ttu-id="54bce-154">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="54bce-154">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="54bce-155">O `Copy-Item` cmdlet copia `scriptingexample.ps1` da `D:\Folder004` pasta para a `C:\Folder004_Copy` pasta no computador remoto usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="54bce-155">The `Copy-Item` cmdlet copies `scriptingexample.ps1` from the `D:\Folder004` folder to the `C:\Folder004_Copy` folder on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="54bce-156">Como parte da operação de cópia, o comando altera o nome do item de `scriptingexample.ps1` para `scriptingexample_copy.ps1` , para que ele possa ser anexado a mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="54bce-156">As part of the copy operation, the command changes the item name from `scriptingexample.ps1` to `scriptingexample_copy.ps1`, so it can be attached to email messages.</span></span> <span data-ttu-id="54bce-157">O arquivo original não é excluído.</span><span class="sxs-lookup"><span data-stu-id="54bce-157">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder004\scriptingexample.ps1" -Destination "C:\Folder004_Copy\scriptingexample_copy.ps1" -ToSession $Session
```

### <span data-ttu-id="54bce-158">Exemplo 9: copiar um arquivo remoto para o computador local</span><span class="sxs-lookup"><span data-stu-id="54bce-158">Example 9: Copy a remote file to the local computer</span></span>

<span data-ttu-id="54bce-159">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="54bce-159">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="54bce-160">O `Copy-Item` cmdlet copia `test.log` do controle remoto `C:\MyRemoteData\` para a `D:\MyLocalData` pasta local usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="54bce-160">The `Copy-Item` cmdlet copies `test.log` from the remote `C:\MyRemoteData\` to the local `D:\MyLocalData` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="54bce-161">O arquivo original não é excluído.</span><span class="sxs-lookup"><span data-stu-id="54bce-161">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\test.log" -Destination "D:\MyLocalData\" -FromSession $Session
```

### <span data-ttu-id="54bce-162">Exemplo 10: copiar todo o conteúdo de uma pasta remota para o computador local</span><span class="sxs-lookup"><span data-stu-id="54bce-162">Example 10: Copy the entire contents of a remote folder to the local computer</span></span>

<span data-ttu-id="54bce-163">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="54bce-163">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="54bce-164">O `Copy-Item` cmdlet copia todo o conteúdo da pasta remota `C:\MyRemoteData\scripts` para a pasta local `D:\MyLocalData` usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="54bce-164">The `Copy-Item` cmdlet copies the entire contents from the remote `C:\MyRemoteData\scripts` folder to the local `D:\MyLocalData` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="54bce-165">Se a pasta scripts contiver arquivos em subpastas, essas subpastas serão copiadas com suas árvores de arquivo intactas.</span><span class="sxs-lookup"><span data-stu-id="54bce-165">If the scripts folder contains files in subfolders, those subfolders are copied with their file trees intact.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\" -FromSession $Session
```

### <span data-ttu-id="54bce-166">Exemplo 11: copiar recursivamente todo o conteúdo de uma pasta remota para o computador local</span><span class="sxs-lookup"><span data-stu-id="54bce-166">Example 11: Recursively copy the entire contents of a remote folder to the local computer</span></span>

<span data-ttu-id="54bce-167">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="54bce-167">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="54bce-168">O `Copy-Item` cmdlet copia todo o conteúdo da pasta remota `C:\MyRemoteData\scripts` para a pasta local `D:\MyLocalData\scripts` usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="54bce-168">The `Copy-Item` cmdlet copies the entire contents from the remote `C:\MyRemoteData\scripts` folder to the local `D:\MyLocalData\scripts` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="54bce-169">Como o parâmetro **recurse** é usado, a operação cria a pasta scripts, caso ela ainda não exista.</span><span class="sxs-lookup"><span data-stu-id="54bce-169">Because the **Recurse** parameter is used, the operation creates the scripts folder if it doesn't already exist.</span></span> <span data-ttu-id="54bce-170">Se a pasta scripts contiver arquivos em subpastas, essas subpastas serão copiadas com suas árvores de arquivo intactas.</span><span class="sxs-lookup"><span data-stu-id="54bce-170">If the scripts folder contains files in subfolders, those subfolders are copied with their file trees intact.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\scripts" -FromSession $Session -Recurse
```

### <span data-ttu-id="54bce-171">Exemplo 12: copiar arquivos recursivamente de uma árvore de pastas para a pasta atual</span><span class="sxs-lookup"><span data-stu-id="54bce-171">Example 12: Recursively copy files from a folder tree into the current folder</span></span>

<span data-ttu-id="54bce-172">Este exemplo mostra como copiar arquivos de uma estrutura de pasta de vários níveis em uma única pasta simples.</span><span class="sxs-lookup"><span data-stu-id="54bce-172">This example shows how to copy files from a multilevel folder structure into a single flat folder.</span></span>
<span data-ttu-id="54bce-173">Os três primeiros comandos mostram a estrutura de pastas existente e o conteúdo de dois arquivos, ambos os nomes `file3.txt` .</span><span class="sxs-lookup"><span data-stu-id="54bce-173">The first three commands show the existing folder structure and the contents of two files, both names `file3.txt`.</span></span>

```powershell
PS C:\temp\test> (Get-ChildItem C:\temp\tree -Recurse).FullName
C:\temp\tree\subfolder
C:\temp\tree\file1.txt
C:\temp\tree\file2.txt
C:\temp\tree\file3.txt
C:\temp\tree\subfolder\file3.txt
C:\temp\tree\subfolder\file4.txt
C:\temp\tree\subfolder\file5.txt

PS C:\temp\test> Get-Content C:\temp\tree\file3.txt
This is file3.txt in the root folder

PS C:\temp\test> Get-Content C:\temp\tree\subfolder\file3.txt
This is file3.txt in the subfolder

PS C:\temp\test> Copy-Item -Path C:\temp\tree -Filter *.txt -Recurse -Container:$false
PS C:\temp\test> (Get-ChildItem . -Recurse).FullName
C:\temp\test\subfolder
C:\temp\test\file1.txt
C:\temp\test\file2.txt
C:\temp\test\file3.txt
C:\temp\test\file4.txt
C:\temp\test\file5.txt

PS C:\temp\test> Get-Content .\file3.txt
This is file3.txt in the subfolder
```

<span data-ttu-id="54bce-174">O `Copy-Item` cmdlet tem o parâmetro de **contêiner** definido como `$false` .</span><span class="sxs-lookup"><span data-stu-id="54bce-174">The `Copy-Item` cmdlet has the **Container** parameter set to `$false`.</span></span> <span data-ttu-id="54bce-175">Isso faz com que o conteúdo da pasta de origem seja copiado, mas não preserva a estrutura de pastas.</span><span class="sxs-lookup"><span data-stu-id="54bce-175">This causes the contents of the source folder to be copied but does not preserve the folder structure.</span></span> <span data-ttu-id="54bce-176">Observe que os arquivos com o mesmo nome são substituídos na pasta de destino.</span><span class="sxs-lookup"><span data-stu-id="54bce-176">Notice that files with the same name are overwritten in the destination folder.</span></span>

## <span data-ttu-id="54bce-177">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="54bce-177">PARAMETERS</span></span>

### <span data-ttu-id="54bce-178">-Confirm</span><span class="sxs-lookup"><span data-stu-id="54bce-178">-Confirm</span></span>

<span data-ttu-id="54bce-179">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="54bce-179">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54bce-180">-Contêiner</span><span class="sxs-lookup"><span data-stu-id="54bce-180">-Container</span></span>

<span data-ttu-id="54bce-181">Indica que esse cmdlet preserva objetos de contêiner durante a operação de cópia.</span><span class="sxs-lookup"><span data-stu-id="54bce-181">Indicates that this cmdlet preserves container objects during the copy operation.</span></span> <span data-ttu-id="54bce-182">Por padrão, o parâmetro de **contêiner** é definido como **true** .</span><span class="sxs-lookup"><span data-stu-id="54bce-182">By default, the **Container** parameter is set to **True** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54bce-183">-Credential</span><span class="sxs-lookup"><span data-stu-id="54bce-183">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="54bce-184">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54bce-184">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="54bce-185">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="54bce-185">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="54bce-186">-Destino</span><span class="sxs-lookup"><span data-stu-id="54bce-186">-Destination</span></span>

<span data-ttu-id="54bce-187">Especifica o caminho para o local de destino.</span><span class="sxs-lookup"><span data-stu-id="54bce-187">Specifies the path to the new location.</span></span> <span data-ttu-id="54bce-188">O padrão é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="54bce-188">The default is the current directory.</span></span>

<span data-ttu-id="54bce-189">Para renomear o item que está sendo copiado, especifique um novo nome no valor do parâmetro de **destino** .</span><span class="sxs-lookup"><span data-stu-id="54bce-189">To rename the item being copied, specify a new name in the value of the **Destination** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="54bce-190">-Excluir</span><span class="sxs-lookup"><span data-stu-id="54bce-190">-Exclude</span></span>

<span data-ttu-id="54bce-191">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="54bce-191">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="54bce-192">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="54bce-192">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="54bce-193">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="54bce-193">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="54bce-194">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="54bce-194">Wildcard characters are permitted.</span></span> <span data-ttu-id="54bce-195">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="54bce-195">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="54bce-196">-Filter</span><span class="sxs-lookup"><span data-stu-id="54bce-196">-Filter</span></span>

<span data-ttu-id="54bce-197">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="54bce-197">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="54bce-198">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="54bce-198">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="54bce-199">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="54bce-199">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="54bce-200">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="54bce-200">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="54bce-201">-Force</span><span class="sxs-lookup"><span data-stu-id="54bce-201">-Force</span></span>

<span data-ttu-id="54bce-202">Indica que esse cmdlet copia itens que não podem ser alterados de outra forma, como copiar por um arquivo somente leitura ou alias.</span><span class="sxs-lookup"><span data-stu-id="54bce-202">Indicates that this cmdlet copies items that can't otherwise be changed, such as copying over a read-only file or alias.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54bce-203">-FromSession</span><span class="sxs-lookup"><span data-stu-id="54bce-203">-FromSession</span></span>

<span data-ttu-id="54bce-204">Especifica o objeto **PSSession** do qual um arquivo remoto está sendo copiado.</span><span class="sxs-lookup"><span data-stu-id="54bce-204">Specifies the **PSSession** object from which a remote file is being copied.</span></span> <span data-ttu-id="54bce-205">Quando você usa esse parâmetro, os parâmetros **Path** e **LiteralPath** referem-se ao caminho local no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="54bce-205">When you use this parameter, the **Path** and **LiteralPath** parameters refer to the local path on the remote machine.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54bce-206">-Incluir</span><span class="sxs-lookup"><span data-stu-id="54bce-206">-Include</span></span>

<span data-ttu-id="54bce-207">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="54bce-207">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="54bce-208">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="54bce-208">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="54bce-209">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="54bce-209">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="54bce-210">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="54bce-210">Wildcard characters are permitted.</span></span> <span data-ttu-id="54bce-211">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="54bce-211">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="54bce-212">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="54bce-212">-LiteralPath</span></span>

<span data-ttu-id="54bce-213">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="54bce-213">Specifies a path to one or more locations.</span></span> <span data-ttu-id="54bce-214">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="54bce-214">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="54bce-215">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="54bce-215">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="54bce-216">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="54bce-216">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="54bce-217">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="54bce-217">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="54bce-218">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="54bce-218">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="54bce-219">-PassThru</span><span class="sxs-lookup"><span data-stu-id="54bce-219">-PassThru</span></span>

<span data-ttu-id="54bce-220">Retorna um objeto que representa o item com o qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="54bce-220">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="54bce-221">Por padrão, esse cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="54bce-221">By default, this cmdlet doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54bce-222">-Path</span><span class="sxs-lookup"><span data-stu-id="54bce-222">-Path</span></span>

<span data-ttu-id="54bce-223">Especifica, como uma matriz de cadeia de caracteres, o caminho para os itens a serem copiados.</span><span class="sxs-lookup"><span data-stu-id="54bce-223">Specifies, as a string array, the path to the items to copy.</span></span> <span data-ttu-id="54bce-224">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="54bce-224">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="54bce-225">-Recurse</span><span class="sxs-lookup"><span data-stu-id="54bce-225">-Recurse</span></span>

<span data-ttu-id="54bce-226">Indica que esse cmdlet faz uma cópia recursiva.</span><span class="sxs-lookup"><span data-stu-id="54bce-226">Indicates that this cmdlet does a recursive copy.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54bce-227">-Tosession</span><span class="sxs-lookup"><span data-stu-id="54bce-227">-ToSession</span></span>

<span data-ttu-id="54bce-228">Especifica o objeto **PSSession** ao qual um arquivo remoto está sendo copiado.</span><span class="sxs-lookup"><span data-stu-id="54bce-228">Specifies the **PSSession** object to which a remote file is being copied.</span></span> <span data-ttu-id="54bce-229">Quando você usa esse parâmetro, o parâmetro de **destino** refere-se ao caminho local no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="54bce-229">When you use this parameter, the **Destination** parameter refers to the local path on the remote machine.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54bce-230">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="54bce-230">-UseTransaction</span></span>

<span data-ttu-id="54bce-231">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="54bce-231">Includes the command in the active transaction.</span></span> <span data-ttu-id="54bce-232">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="54bce-232">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="54bce-233">Para obter mais informações, consulte [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="54bce-233">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54bce-234">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="54bce-234">-WhatIf</span></span>

<span data-ttu-id="54bce-235">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="54bce-235">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="54bce-236">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="54bce-236">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54bce-237">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="54bce-237">CommonParameters</span></span>

<span data-ttu-id="54bce-238">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="54bce-238">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="54bce-239">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="54bce-239">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="54bce-240">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="54bce-240">INPUTS</span></span>

### <span data-ttu-id="54bce-241">System.String</span><span class="sxs-lookup"><span data-stu-id="54bce-241">System.String</span></span>

<span data-ttu-id="54bce-242">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="54bce-242">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="54bce-243">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="54bce-243">OUTPUTS</span></span>

### <span data-ttu-id="54bce-244">Nenhum ou um objeto que representa o item copiado</span><span class="sxs-lookup"><span data-stu-id="54bce-244">None or an object representing the copied item</span></span>

<span data-ttu-id="54bce-245">Quando você usa o parâmetro **PassThru** , esse cmdlet retorna um objeto que representa o item copiado.</span><span class="sxs-lookup"><span data-stu-id="54bce-245">When you use the **PassThru** parameter, this cmdlet returns an object that represents the copied item.</span></span> <span data-ttu-id="54bce-246">Caso contrário, esse cmdlet não gerará nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="54bce-246">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="54bce-247">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="54bce-247">NOTES</span></span>

<span data-ttu-id="54bce-248">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="54bce-248">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="54bce-249">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="54bce-249">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="54bce-250">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="54bce-250">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="54bce-251">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="54bce-251">RELATED LINKS</span></span>

[<span data-ttu-id="54bce-252">about_Providers</span><span class="sxs-lookup"><span data-stu-id="54bce-252">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="54bce-253">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="54bce-253">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="54bce-254">Get-Item</span><span class="sxs-lookup"><span data-stu-id="54bce-254">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="54bce-255">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="54bce-255">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="54bce-256">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="54bce-256">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="54bce-257">Move-Item</span><span class="sxs-lookup"><span data-stu-id="54bce-257">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="54bce-258">New-Item</span><span class="sxs-lookup"><span data-stu-id="54bce-258">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="54bce-259">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="54bce-259">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="54bce-260">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="54bce-260">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="54bce-261">Set-Item</span><span class="sxs-lookup"><span data-stu-id="54bce-261">Set-Item</span></span>](Set-Item.md)
