---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-Item
ms.openlocfilehash: ee2d8b8a3b736a59b5af4a81710a0d29dd2238d5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597201"
---
# <span data-ttu-id="67818-102">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="67818-102">Copy-Item</span></span>

## <span data-ttu-id="67818-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="67818-103">SYNOPSIS</span></span>
<span data-ttu-id="67818-104">Copia um item de um local para outro.</span><span class="sxs-lookup"><span data-stu-id="67818-104">Copies an item from one location to another.</span></span>

## <span data-ttu-id="67818-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="67818-105">SYNTAX</span></span>

### <span data-ttu-id="67818-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="67818-106">Path (Default)</span></span>

```
Copy-Item [-Path] <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="67818-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="67818-107">LiteralPath</span></span>

```
Copy-Item -LiteralPath <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

## <span data-ttu-id="67818-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="67818-108">DESCRIPTION</span></span>

<span data-ttu-id="67818-109">O `Copy-Item` cmdlet copia um item de um local para outro local no mesmo namespace.</span><span class="sxs-lookup"><span data-stu-id="67818-109">The `Copy-Item` cmdlet copies an item from one location to another location in the same namespace.</span></span>
<span data-ttu-id="67818-110">Por exemplo, ele pode copiar um arquivo para uma pasta, mas não pode copiar um arquivo para uma unidade de certificado.</span><span class="sxs-lookup"><span data-stu-id="67818-110">For instance, it can copy a file to a folder, but it can't copy a file to a certificate drive.</span></span>

<span data-ttu-id="67818-111">Esse cmdlet não recorta nem exclui os itens que estão sendo copiados.</span><span class="sxs-lookup"><span data-stu-id="67818-111">This cmdlet doesn't cut or delete the items being copied.</span></span> <span data-ttu-id="67818-112">Os itens específicos que o cmdlet pode copiar dependem do provedor do PowerShell que expõe o item.</span><span class="sxs-lookup"><span data-stu-id="67818-112">The particular items that the cmdlet can copy depend on the PowerShell provider that exposes the item.</span></span> <span data-ttu-id="67818-113">Por exemplo, ele pode copiar arquivos e diretórios em uma unidade do sistema de arquivos e chaves do registro e entradas na unidade do registro.</span><span class="sxs-lookup"><span data-stu-id="67818-113">For instance, it can copy files and directories in a file system drive and registry keys and entries in the registry drive.</span></span>

<span data-ttu-id="67818-114">Esse cmdlet pode copiar e renomear itens no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="67818-114">This cmdlet can copy and rename items in the same command.</span></span> <span data-ttu-id="67818-115">Para renomear um item, insira o novo nome no valor do parâmetro de **destino** .</span><span class="sxs-lookup"><span data-stu-id="67818-115">To rename an item, enter the new name in the value of the **Destination** parameter.</span></span> <span data-ttu-id="67818-116">Para renomear um item e não copiá-lo, use o `Rename-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="67818-116">To rename an item and not copy it, use the `Rename-Item` cmdlet.</span></span>

## <span data-ttu-id="67818-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="67818-117">EXAMPLES</span></span>

### <span data-ttu-id="67818-118">Exemplo 1: copiar um arquivo para o diretório especificado</span><span class="sxs-lookup"><span data-stu-id="67818-118">Example 1: Copy a file to the specified directory</span></span>

<span data-ttu-id="67818-119">Este exemplo copia o `mar1604.log.txt` arquivo para o `C:\Presentation` diretório.</span><span class="sxs-lookup"><span data-stu-id="67818-119">This example copies the `mar1604.log.txt` file to the `C:\Presentation` directory.</span></span> <span data-ttu-id="67818-120">O arquivo original não é excluído.</span><span class="sxs-lookup"><span data-stu-id="67818-120">The original file isn't deleted.</span></span>

```powershell
Copy-Item "C:\Wabash\Logfiles\mar1604.log.txt" -Destination "C:\Presentation"
```

### <span data-ttu-id="67818-121">Exemplo 2: copiar o conteúdo do diretório para um diretório existente</span><span class="sxs-lookup"><span data-stu-id="67818-121">Example 2: Copy directory contents to an existing directory</span></span>

<span data-ttu-id="67818-122">Este exemplo copia o conteúdo do `C:\Logfiles` diretório para o diretório existente `C:\Drawings` .</span><span class="sxs-lookup"><span data-stu-id="67818-122">This example copies the contents of the `C:\Logfiles` directory into the existing `C:\Drawings` directory.</span></span> <span data-ttu-id="67818-123">O `Logfiles` diretório não é copiado.</span><span class="sxs-lookup"><span data-stu-id="67818-123">The `Logfiles` directory isn't copied.</span></span>

<span data-ttu-id="67818-124">Se o `Logfiles` diretório contiver arquivos em subdiretórios, esses subdiretórios serão copiados com suas árvores de arquivo intactas.</span><span class="sxs-lookup"><span data-stu-id="67818-124">If the `Logfiles` directory contains files in subdirectories, those subdirectories are copied with their file trees intact.</span></span> <span data-ttu-id="67818-125">Por padrão, o parâmetro de **contêiner** é definido como **true**, o que preserva a estrutura de diretórios.</span><span class="sxs-lookup"><span data-stu-id="67818-125">By default, the **Container** parameter is set to **True**, which preserves the directory structure.</span></span>

```powershell
Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings" -Recurse
```

> [!NOTE]
> <span data-ttu-id="67818-126">Se você precisar incluir o `Logfiles` diretório na cópia, remova o `\*` do **caminho**.</span><span class="sxs-lookup"><span data-stu-id="67818-126">If you need to include the `Logfiles` directory in the copy, remove the `\*` from the **Path**.</span></span>
> <span data-ttu-id="67818-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="67818-127">For example:</span></span>
>
> `Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings" -Recurse`

### <span data-ttu-id="67818-128">Exemplo 3: copiar diretório e conteúdo para um novo diretório</span><span class="sxs-lookup"><span data-stu-id="67818-128">Example 3: Copy directory and contents to a new directory</span></span>

<span data-ttu-id="67818-129">Este exemplo copia o conteúdo do `C:\Logfiles` diretório de origem e cria um novo diretório de destino.</span><span class="sxs-lookup"><span data-stu-id="67818-129">This example copies the contents of the `C:\Logfiles` source directory and creates a new destination directory.</span></span> <span data-ttu-id="67818-130">O novo diretório de destino, `\Logs` é criado no `C:\Drawings` .</span><span class="sxs-lookup"><span data-stu-id="67818-130">The new destination directory, `\Logs` is created in `C:\Drawings`.</span></span>

<span data-ttu-id="67818-131">Para incluir o nome do diretório de origem, copie para um diretório de destino existente, conforme mostrado no **exemplo 2**.</span><span class="sxs-lookup"><span data-stu-id="67818-131">To include the source directory's name, copy to an existing destination directory as shown in **Example 2**.</span></span> <span data-ttu-id="67818-132">Ou, nomeie o novo diretório de destino com o mesmo diretório de origem.</span><span class="sxs-lookup"><span data-stu-id="67818-132">Or, name the new destination directory with the same as the source directory.</span></span>

```powershell
Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings\Logs" -Recurse
```

> [!NOTE]
> <span data-ttu-id="67818-133">Se o **caminho** incluir `\*` , todo o conteúdo do arquivo do diretório, incluindo as árvores de subdiretórios, será copiado para o novo diretório de destino.</span><span class="sxs-lookup"><span data-stu-id="67818-133">If the **Path** includes `\*`, all the directory's file contents, including the subdirectory trees, are copied to the new destination directory.</span></span> <span data-ttu-id="67818-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="67818-134">For example:</span></span>
>
> `Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings\Logs" -Recurse`

### <span data-ttu-id="67818-135">Exemplo 4: copiar um arquivo para o diretório especificado e renomear o arquivo</span><span class="sxs-lookup"><span data-stu-id="67818-135">Example 4: Copy a file to the specified directory and rename the file</span></span>

<span data-ttu-id="67818-136">Este exemplo usa o `Copy-Item` cmdlet para copiar o `Get-Widget.ps1` script do `\\Server01\Share` diretório para o `\\Server12\ScriptArchive` diretório.</span><span class="sxs-lookup"><span data-stu-id="67818-136">This example uses the `Copy-Item` cmdlet to copy the `Get-Widget.ps1` script from the `\\Server01\Share` directory to the `\\Server12\ScriptArchive` directory.</span></span> <span data-ttu-id="67818-137">Como parte da operação de cópia, o comando altera o nome do item de `Get-Widget.ps1` para `Get-Widget.ps1.txt` , para que ele possa ser anexado a mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="67818-137">As part of the copy operation, the command changes the item name from `Get-Widget.ps1` to `Get-Widget.ps1.txt`, so it can be attached to email messages.</span></span>

```powershell
Copy-Item "\\Server01\Share\Get-Widget.ps1" -Destination "\\Server12\ScriptArchive\Get-Widget.ps1.txt"
```

### <span data-ttu-id="67818-138">Exemplo 5: copiar um arquivo para um computador remoto</span><span class="sxs-lookup"><span data-stu-id="67818-138">Example 5: Copy a file to a remote computer</span></span>

<span data-ttu-id="67818-139">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="67818-139">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="67818-140">O `Copy-Item` cmdlet copia `test.log` da `D:\Folder001` pasta para a `C:\Folder001_Copy` pasta no computador remoto usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="67818-140">The `Copy-Item` cmdlet copies `test.log` from the `D:\Folder001` folder to the `C:\Folder001_Copy` folder on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="67818-141">O arquivo original não é excluído.</span><span class="sxs-lookup"><span data-stu-id="67818-141">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "D:\Folder001\test.log" -Destination "C:\Folder001_Copy\" -ToSession $Session
```

### <span data-ttu-id="67818-142">Exemplo 6: copiar uma pasta para um computador remoto</span><span class="sxs-lookup"><span data-stu-id="67818-142">Example 6: Copy a folder to a remote computer</span></span>

<span data-ttu-id="67818-143">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="67818-143">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="67818-144">O `Copy-Item` cmdlet copia a `D:\Folder002` pasta para o `C:\Folder002_Copy` diretório no computador remoto usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="67818-144">The `Copy-Item` cmdlet copies the `D:\Folder002` folder to the `C:\Folder002_Copy` directory on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="67818-145">Todas as subpastas ou arquivos não são copiados sem usar a opção **recurse** .</span><span class="sxs-lookup"><span data-stu-id="67818-145">Any subfolders or files are not copied without using the **Recurse** switch.</span></span>
<span data-ttu-id="67818-146">A operação criará a `Folder002_Copy` pasta se ela ainda não existir.</span><span class="sxs-lookup"><span data-stu-id="67818-146">The operation creates the `Folder002_Copy` folder if it doesn't already exist.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server02" -Credential "Contoso\User01"
Copy-Item "D:\Folder002\" -Destination "C:\Folder002_Copy\" -ToSession $Session
```

### <span data-ttu-id="67818-147">Exemplo 7: copiar recursivamente todo o conteúdo de uma pasta para um computador remoto</span><span class="sxs-lookup"><span data-stu-id="67818-147">Example 7: Recursively copy the entire contents of a folder to a remote computer</span></span>

<span data-ttu-id="67818-148">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="67818-148">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="67818-149">O `Copy-Item` cmdlet copia todo o conteúdo da `D:\Folder003` pasta para o `C:\Folder003_Copy` diretório no computador remoto usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="67818-149">The `Copy-Item` cmdlet copies the entire contents from the `D:\Folder003` folder to the `C:\Folder003_Copy` directory on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="67818-150">As subpastas são copiadas com suas árvores de arquivo intactas.</span><span class="sxs-lookup"><span data-stu-id="67818-150">The subfolders are copied with their file trees intact.</span></span> <span data-ttu-id="67818-151">A operação criará a `Folder003_Copy` pasta se ela ainda não existir.</span><span class="sxs-lookup"><span data-stu-id="67818-151">The operation creates the `Folder003_Copy` folder if it doesn't already exist.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder003\" -Destination "C:\Folder003_Copy\" -ToSession $Session -Recurse
```

### <span data-ttu-id="67818-152">Exemplo 8: copiar um arquivo para um computador remoto e, em seguida, renomear o arquivo</span><span class="sxs-lookup"><span data-stu-id="67818-152">Example 8: Copy a file to a remote computer and then rename the file</span></span>

<span data-ttu-id="67818-153">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="67818-153">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="67818-154">O `Copy-Item` cmdlet copia `scriptingexample.ps1` da `D:\Folder004` pasta para a `C:\Folder004_Copy` pasta no computador remoto usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="67818-154">The `Copy-Item` cmdlet copies `scriptingexample.ps1` from the `D:\Folder004` folder to the `C:\Folder004_Copy` folder on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="67818-155">Como parte da operação de cópia, o comando altera o nome do item de `scriptingexample.ps1` para `scriptingexample_copy.ps1` , para que ele possa ser anexado a mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="67818-155">As part of the copy operation, the command changes the item name from `scriptingexample.ps1` to `scriptingexample_copy.ps1`, so it can be attached to email messages.</span></span> <span data-ttu-id="67818-156">O arquivo original não é excluído.</span><span class="sxs-lookup"><span data-stu-id="67818-156">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder004\scriptingexample.ps1" -Destination "C:\Folder004_Copy\scriptingexample_copy.ps1" -ToSession $Session
```

### <span data-ttu-id="67818-157">Exemplo 9: copiar um arquivo remoto para o computador local</span><span class="sxs-lookup"><span data-stu-id="67818-157">Example 9: Copy a remote file to the local computer</span></span>

<span data-ttu-id="67818-158">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="67818-158">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="67818-159">O `Copy-Item` cmdlet copia `test.log` do controle remoto `C:\MyRemoteData\` para a `D:\MyLocalData` pasta local usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="67818-159">The `Copy-Item` cmdlet copies `test.log` from the remote `C:\MyRemoteData\` to the local `D:\MyLocalData` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="67818-160">O arquivo original não é excluído.</span><span class="sxs-lookup"><span data-stu-id="67818-160">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\test.log" -Destination "D:\MyLocalData\" -FromSession $Session
```

### <span data-ttu-id="67818-161">Exemplo 10: copiar todo o conteúdo de uma pasta remota para o computador local</span><span class="sxs-lookup"><span data-stu-id="67818-161">Example 10: Copy the entire contents of a remote folder to the local computer</span></span>

<span data-ttu-id="67818-162">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="67818-162">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="67818-163">O `Copy-Item` cmdlet copia todo o conteúdo da pasta remota `C:\MyRemoteData\scripts` para a pasta local `D:\MyLocalData` usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="67818-163">The `Copy-Item` cmdlet copies the entire contents from the remote `C:\MyRemoteData\scripts` folder to the local `D:\MyLocalData` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="67818-164">Se a pasta scripts contiver arquivos em subpastas, essas subpastas serão copiadas com suas árvores de arquivo intactas.</span><span class="sxs-lookup"><span data-stu-id="67818-164">If the scripts folder contains files in subfolders, those subfolders are copied with their file trees intact.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\" -FromSession $Session
```

### <span data-ttu-id="67818-165">Exemplo 11: copiar recursivamente todo o conteúdo de uma pasta remota para o computador local</span><span class="sxs-lookup"><span data-stu-id="67818-165">Example 11: Recursively copy the entire contents of a remote folder to the local computer</span></span>

<span data-ttu-id="67818-166">Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .</span><span class="sxs-lookup"><span data-stu-id="67818-166">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="67818-167">O `Copy-Item` cmdlet copia todo o conteúdo da pasta remota `C:\MyRemoteData\scripts` para a pasta local `D:\MyLocalData\scripts` usando as informações de sessão armazenadas na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="67818-167">The `Copy-Item` cmdlet copies the entire contents from the remote `C:\MyRemoteData\scripts` folder to the local `D:\MyLocalData\scripts` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="67818-168">Como o parâmetro **recurse** é usado, a operação cria a pasta scripts, caso ela ainda não exista.</span><span class="sxs-lookup"><span data-stu-id="67818-168">Because the **Recurse** parameter is used, the operation creates the scripts folder if it doesn't already exist.</span></span> <span data-ttu-id="67818-169">Se a pasta scripts contiver arquivos em subpastas, essas subpastas serão copiadas com suas árvores de arquivo intactas.</span><span class="sxs-lookup"><span data-stu-id="67818-169">If the scripts folder contains files in subfolders, those subfolders are copied with their file trees intact.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\scripts" -FromSession $Session -Recurse
```

### <span data-ttu-id="67818-170">Exemplo 12: copiar arquivos recursivamente de uma árvore de pastas para a pasta atual</span><span class="sxs-lookup"><span data-stu-id="67818-170">Example 12: Recursively copy files from a folder tree into the current folder</span></span>

<span data-ttu-id="67818-171">Este exemplo mostra como copiar arquivos de uma estrutura de pasta de vários níveis em uma única pasta simples.</span><span class="sxs-lookup"><span data-stu-id="67818-171">This example shows how to copy files from a multilevel folder structure into a single flat folder.</span></span>
<span data-ttu-id="67818-172">Os três primeiros comandos mostram a estrutura de pastas existente e o conteúdo de dois arquivos, ambos os nomes `file3.txt` .</span><span class="sxs-lookup"><span data-stu-id="67818-172">The first three commands show the existing folder structure and the contents of two files, both names `file3.txt`.</span></span>

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

<span data-ttu-id="67818-173">O `Copy-Item` cmdlet tem o parâmetro de **contêiner** definido como `$false` .</span><span class="sxs-lookup"><span data-stu-id="67818-173">The `Copy-Item` cmdlet has the **Container** parameter set to `$false`.</span></span> <span data-ttu-id="67818-174">Isso faz com que o conteúdo da pasta de origem seja copiado, mas não preserva a estrutura de pastas.</span><span class="sxs-lookup"><span data-stu-id="67818-174">This causes the contents of the source folder to be copied but does not preserve the folder structure.</span></span> <span data-ttu-id="67818-175">Observe que os arquivos com o mesmo nome são substituídos na pasta de destino.</span><span class="sxs-lookup"><span data-stu-id="67818-175">Notice that files with the same name are overwritten in the destination folder.</span></span>

## <span data-ttu-id="67818-176">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="67818-176">PARAMETERS</span></span>

### <span data-ttu-id="67818-177">-Confirm</span><span class="sxs-lookup"><span data-stu-id="67818-177">-Confirm</span></span>

<span data-ttu-id="67818-178">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="67818-178">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="67818-179">-Contêiner</span><span class="sxs-lookup"><span data-stu-id="67818-179">-Container</span></span>

<span data-ttu-id="67818-180">Indica que esse cmdlet preserva objetos de contêiner durante a operação de cópia.</span><span class="sxs-lookup"><span data-stu-id="67818-180">Indicates that this cmdlet preserves container objects during the copy operation.</span></span> <span data-ttu-id="67818-181">Por padrão, o parâmetro de **contêiner** é definido como **true**.</span><span class="sxs-lookup"><span data-stu-id="67818-181">By default, the **Container** parameter is set to **True**.</span></span>

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

### <span data-ttu-id="67818-182">-Credential</span><span class="sxs-lookup"><span data-stu-id="67818-182">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="67818-183">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67818-183">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="67818-184">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="67818-184">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="67818-185">-Destino</span><span class="sxs-lookup"><span data-stu-id="67818-185">-Destination</span></span>

<span data-ttu-id="67818-186">Especifica o caminho para o local de destino.</span><span class="sxs-lookup"><span data-stu-id="67818-186">Specifies the path to the new location.</span></span> <span data-ttu-id="67818-187">O padrão é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="67818-187">The default is the current directory.</span></span>

<span data-ttu-id="67818-188">Para renomear o item que está sendo copiado, especifique um novo nome no valor do parâmetro de **destino** .</span><span class="sxs-lookup"><span data-stu-id="67818-188">To rename the item being copied, specify a new name in the value of the **Destination** parameter.</span></span>

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

### <span data-ttu-id="67818-189">-Excluir</span><span class="sxs-lookup"><span data-stu-id="67818-189">-Exclude</span></span>

<span data-ttu-id="67818-190">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="67818-190">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="67818-191">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="67818-191">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="67818-192">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="67818-192">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="67818-193">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="67818-193">Wildcard characters are permitted.</span></span> <span data-ttu-id="67818-194">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="67818-194">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="67818-195">-Filter</span><span class="sxs-lookup"><span data-stu-id="67818-195">-Filter</span></span>

<span data-ttu-id="67818-196">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="67818-196">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="67818-197">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="67818-197">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="67818-198">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="67818-198">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="67818-199">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="67818-199">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span>

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

### <span data-ttu-id="67818-200">-Force</span><span class="sxs-lookup"><span data-stu-id="67818-200">-Force</span></span>

<span data-ttu-id="67818-201">Indica que esse cmdlet copia itens que não podem ser alterados de outra forma, como copiar por um arquivo somente leitura ou alias.</span><span class="sxs-lookup"><span data-stu-id="67818-201">Indicates that this cmdlet copies items that can't otherwise be changed, such as copying over a read-only file or alias.</span></span>

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

### <span data-ttu-id="67818-202">-FromSession</span><span class="sxs-lookup"><span data-stu-id="67818-202">-FromSession</span></span>

<span data-ttu-id="67818-203">Especifica o objeto **PSSession** do qual um arquivo remoto está sendo copiado.</span><span class="sxs-lookup"><span data-stu-id="67818-203">Specifies the **PSSession** object from which a remote file is being copied.</span></span> <span data-ttu-id="67818-204">Quando você usa esse parâmetro, os parâmetros **Path** e **LiteralPath** referem-se ao caminho local no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="67818-204">When you use this parameter, the **Path** and **LiteralPath** parameters refer to the local path on the remote machine.</span></span>

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

### <span data-ttu-id="67818-205">-Incluir</span><span class="sxs-lookup"><span data-stu-id="67818-205">-Include</span></span>

<span data-ttu-id="67818-206">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="67818-206">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="67818-207">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="67818-207">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="67818-208">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="67818-208">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="67818-209">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="67818-209">Wildcard characters are permitted.</span></span> <span data-ttu-id="67818-210">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="67818-210">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="67818-211">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="67818-211">-LiteralPath</span></span>

<span data-ttu-id="67818-212">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="67818-212">Specifies a path to one or more locations.</span></span> <span data-ttu-id="67818-213">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="67818-213">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="67818-214">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="67818-214">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="67818-215">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="67818-215">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="67818-216">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="67818-216">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="67818-217">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="67818-217">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="67818-218">-PassThru</span><span class="sxs-lookup"><span data-stu-id="67818-218">-PassThru</span></span>

<span data-ttu-id="67818-219">Retorna um objeto que representa o item com o qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="67818-219">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="67818-220">Por padrão, esse cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="67818-220">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="67818-221">-Path</span><span class="sxs-lookup"><span data-stu-id="67818-221">-Path</span></span>

<span data-ttu-id="67818-222">Especifica, como uma matriz de cadeia de caracteres, o caminho para os itens a serem copiados.</span><span class="sxs-lookup"><span data-stu-id="67818-222">Specifies, as a string array, the path to the items to copy.</span></span> <span data-ttu-id="67818-223">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="67818-223">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="67818-224">-Recurse</span><span class="sxs-lookup"><span data-stu-id="67818-224">-Recurse</span></span>

<span data-ttu-id="67818-225">Indica que esse cmdlet faz uma cópia recursiva.</span><span class="sxs-lookup"><span data-stu-id="67818-225">Indicates that this cmdlet does a recursive copy.</span></span>

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

### <span data-ttu-id="67818-226">-Tosession</span><span class="sxs-lookup"><span data-stu-id="67818-226">-ToSession</span></span>

<span data-ttu-id="67818-227">Especifica o objeto **PSSession** ao qual um arquivo remoto está sendo copiado.</span><span class="sxs-lookup"><span data-stu-id="67818-227">Specifies the **PSSession** object to which a remote file is being copied.</span></span> <span data-ttu-id="67818-228">Quando você usa esse parâmetro, o parâmetro de **destino** refere-se ao caminho local no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="67818-228">When you use this parameter, the **Destination** parameter refers to the local path on the remote machine.</span></span>

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

### <span data-ttu-id="67818-229">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="67818-229">-WhatIf</span></span>

<span data-ttu-id="67818-230">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="67818-230">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="67818-231">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="67818-231">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="67818-232">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="67818-232">CommonParameters</span></span>

<span data-ttu-id="67818-233">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="67818-233">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="67818-234">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="67818-234">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="67818-235">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="67818-235">INPUTS</span></span>

### <span data-ttu-id="67818-236">System.String</span><span class="sxs-lookup"><span data-stu-id="67818-236">System.String</span></span>

<span data-ttu-id="67818-237">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="67818-237">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="67818-238">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="67818-238">OUTPUTS</span></span>

### <span data-ttu-id="67818-239">Nenhum ou um objeto que representa o item copiado</span><span class="sxs-lookup"><span data-stu-id="67818-239">None or an object representing the copied item</span></span>

<span data-ttu-id="67818-240">Quando você usa o parâmetro **PassThru** , esse cmdlet retorna um objeto que representa o item copiado.</span><span class="sxs-lookup"><span data-stu-id="67818-240">When you use the **PassThru** parameter, this cmdlet returns an object that represents the copied item.</span></span> <span data-ttu-id="67818-241">Caso contrário, esse cmdlet não gerará nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="67818-241">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="67818-242">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="67818-242">NOTES</span></span>

<span data-ttu-id="67818-243">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="67818-243">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="67818-244">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="67818-244">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="67818-245">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="67818-245">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="67818-246">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="67818-246">RELATED LINKS</span></span>

[<span data-ttu-id="67818-247">about_Providers</span><span class="sxs-lookup"><span data-stu-id="67818-247">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="67818-248">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="67818-248">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="67818-249">Get-Item</span><span class="sxs-lookup"><span data-stu-id="67818-249">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="67818-250">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="67818-250">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="67818-251">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="67818-251">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="67818-252">Move-Item</span><span class="sxs-lookup"><span data-stu-id="67818-252">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="67818-253">New-Item</span><span class="sxs-lookup"><span data-stu-id="67818-253">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="67818-254">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="67818-254">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="67818-255">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="67818-255">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="67818-256">Set-Item</span><span class="sxs-lookup"><span data-stu-id="67818-256">Set-Item</span></span>](Set-Item.md)

