---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: 50a7dba8c4e9cb1cfabd42f39e9fdfb43f22f9b1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193217"
---
# <span data-ttu-id="ac739-103">New-Item</span><span class="sxs-lookup"><span data-stu-id="ac739-103">New-Item</span></span>

## <span data-ttu-id="ac739-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ac739-104">SYNOPSIS</span></span>
<span data-ttu-id="ac739-105">Cria um novo item.</span><span class="sxs-lookup"><span data-stu-id="ac739-105">Creates a new item.</span></span>

## <span data-ttu-id="ac739-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ac739-106">SYNTAX</span></span>

### <span data-ttu-id="ac739-107">caminhoset (padrão)</span><span class="sxs-lookup"><span data-stu-id="ac739-107">pathSet (Default)</span></span>

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ac739-108">nome do</span><span class="sxs-lookup"><span data-stu-id="ac739-108">nameSet</span></span>

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ac739-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ac739-109">DESCRIPTION</span></span>

<span data-ttu-id="ac739-110">O `New-Item` cmdlet cria um novo item e define seu valor.</span><span class="sxs-lookup"><span data-stu-id="ac739-110">The `New-Item` cmdlet creates a new item and sets its value.</span></span> <span data-ttu-id="ac739-111">Os tipos de itens que podem ser criados dependem do local do item.</span><span class="sxs-lookup"><span data-stu-id="ac739-111">The types of items that can be created depend on the location of the item.</span></span> <span data-ttu-id="ac739-112">Por exemplo, no sistema de arquivos, o `New-Item` cria arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="ac739-112">For example, in the file system, `New-Item` creates files and folders.</span></span> <span data-ttu-id="ac739-113">No registro, o `New-Item` cria chaves e entradas do registro.</span><span class="sxs-lookup"><span data-stu-id="ac739-113">In the registry, `New-Item` creates registry keys and entries.</span></span>

<span data-ttu-id="ac739-114">`New-Item` também pode definir o valor dos itens que ele cria.</span><span class="sxs-lookup"><span data-stu-id="ac739-114">`New-Item` can also set the value of the items that it creates.</span></span> <span data-ttu-id="ac739-115">Por exemplo, quando ele cria um novo arquivo, o `New-Item` pode adicionar conteúdo inicial ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="ac739-115">For example, when it creates a new file, `New-Item` can add initial content to the file.</span></span>

## <span data-ttu-id="ac739-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ac739-116">EXAMPLES</span></span>

### <span data-ttu-id="ac739-117">Exemplo 1: criar um arquivo no diretório atual</span><span class="sxs-lookup"><span data-stu-id="ac739-117">Example 1: Create a file in the current directory</span></span>

<span data-ttu-id="ac739-118">Esse comando cria um arquivo de texto chamado "testfile1.txt" no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="ac739-118">This command creates a text file that is named "testfile1.txt" in the current directory.</span></span> <span data-ttu-id="ac739-119">O ponto ('. ') no valor do parâmetro **path** indica o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="ac739-119">The dot ('.') in the value of the **Path** parameter indicates the current directory.</span></span> <span data-ttu-id="ac739-120">O texto entre aspas que segue o parâmetro de **valor** é adicionado ao arquivo como conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ac739-120">The quoted text that follows the **Value** parameter is added to the file as content.</span></span>

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### <span data-ttu-id="ac739-121">Exemplo 2: criar um diretório</span><span class="sxs-lookup"><span data-stu-id="ac739-121">Example 2: Create a directory</span></span>

<span data-ttu-id="ac739-122">Esse comando cria um diretório chamado "LogFiles" na `C:` unidade.</span><span class="sxs-lookup"><span data-stu-id="ac739-122">This command creates a directory named "Logfiles" in the `C:` drive.</span></span> <span data-ttu-id="ac739-123">O parâmetro **ItemType** especifica que o novo item é um diretório, não um arquivo ou outro objeto do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ac739-123">The **ItemType** parameter specifies that the new item is a directory, not a file or other file system object.</span></span>

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### <span data-ttu-id="ac739-124">Exemplo 3: criar um perfil</span><span class="sxs-lookup"><span data-stu-id="ac739-124">Example 3: Create a profile</span></span>

<span data-ttu-id="ac739-125">Esse comando cria um perfil do PowerShell no caminho especificado pela `$profile` variável.</span><span class="sxs-lookup"><span data-stu-id="ac739-125">This command creates a PowerShell profile in the path that is specified by the `$profile` variable.</span></span>

<span data-ttu-id="ac739-126">Você pode usar perfis para personalizar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac739-126">You can use profiles to customize PowerShell.</span></span> <span data-ttu-id="ac739-127">`$profile` é uma variável automática (interna) que armazena o caminho e o nome de arquivo do perfil "CurrentUser/CurrentHost".</span><span class="sxs-lookup"><span data-stu-id="ac739-127">`$profile` is an automatic (built-in) variable that stores the path and file name of the "CurrentUser/CurrentHost" profile.</span></span> <span data-ttu-id="ac739-128">Por padrão, o perfil não existe, mesmo que o PowerShell armazene um caminho e um nome de arquivo para ele.</span><span class="sxs-lookup"><span data-stu-id="ac739-128">By default, the profile does not exist, even though PowerShell stores a path and file name for it.</span></span>

<span data-ttu-id="ac739-129">Nesse comando, a `$profile` variável representa o caminho do arquivo.</span><span class="sxs-lookup"><span data-stu-id="ac739-129">In this command, the `$profile` variable represents the path of the file.</span></span> <span data-ttu-id="ac739-130">O parâmetro **ItemType** especifica que o comando cria um arquivo.</span><span class="sxs-lookup"><span data-stu-id="ac739-130">**ItemType** parameter specifies that the command creates a file.</span></span> <span data-ttu-id="ac739-131">O parâmetro **Force** permite criar um arquivo no caminho do perfil, mesmo quando os diretórios no caminho não existem.</span><span class="sxs-lookup"><span data-stu-id="ac739-131">The **Force** parameter lets you create a file in the profile path, even when the directories in the path do not exist.</span></span>

<span data-ttu-id="ac739-132">Depois de criar um perfil, você pode inserir aliases, funções e scripts no perfil para personalizar o Shell.</span><span class="sxs-lookup"><span data-stu-id="ac739-132">After you create a profile, you can enter aliases, functions, and scripts in the profile to customize your shell.</span></span>

<span data-ttu-id="ac739-133">Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) e [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ac739-133">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

### <span data-ttu-id="ac739-134">Exemplo 4: criar um diretório em um diretório diferente</span><span class="sxs-lookup"><span data-stu-id="ac739-134">Example 4: Create a directory in a different directory</span></span>

<span data-ttu-id="ac739-135">Este exemplo cria um novo diretório de scripts no diretório "C:\PS-Test".</span><span class="sxs-lookup"><span data-stu-id="ac739-135">This example creates a new Scripts directory in the "C:\PS-Test" directory.</span></span>

<span data-ttu-id="ac739-136">O nome do novo item de diretório, "scripts", é incluído no valor do parâmetro **path** , em vez de ser especificado no valor de **Name** .</span><span class="sxs-lookup"><span data-stu-id="ac739-136">The name of the new directory item, "Scripts", is included in the value of **Path** parameter, instead of being specified in the value of **Name** .</span></span> <span data-ttu-id="ac739-137">Conforme indicado pela sintaxe, ambos os formatos de comando são válidos.</span><span class="sxs-lookup"><span data-stu-id="ac739-137">As indicated by the syntax, either command form is valid.</span></span>

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### <span data-ttu-id="ac739-138">Exemplo 5: criar vários arquivos</span><span class="sxs-lookup"><span data-stu-id="ac739-138">Example 5: Create multiple files</span></span>

<span data-ttu-id="ac739-139">Este exemplo cria arquivos em dois diretórios diferentes.</span><span class="sxs-lookup"><span data-stu-id="ac739-139">This example creates files in two different directories.</span></span> <span data-ttu-id="ac739-140">Como o **caminho** usa várias cadeias de caracteres, você pode usá-lo para criar vários itens.</span><span class="sxs-lookup"><span data-stu-id="ac739-140">Because **Path** takes multiple strings, you can use it to create multiple items.</span></span>

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### <span data-ttu-id="ac739-141">Exemplo 6: usar curingas para criar arquivos em vários diretórios</span><span class="sxs-lookup"><span data-stu-id="ac739-141">Example 6: Use wildcards to create files in multiple directories</span></span>

<span data-ttu-id="ac739-142">O `New-Item` cmdlet dá suporte a curingas no parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="ac739-142">The `New-Item` cmdlet supports wildcards in the **Path** parameter.</span></span> <span data-ttu-id="ac739-143">O comando a seguir cria um `temp.txt` arquivo em todos os diretórios especificados pelos curingas no parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="ac739-143">The following command creates a `temp.txt` file in all of the directories specified by the wildcards in the **Path** parameter.</span></span>

```powershell
Get-ChildItem -Path C:\Temp\
```

```Output
    Directory:  C:\Temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d-----        5/15/2019   6:45 AM        1   One
d-----        5/15/2019   6:45 AM        1   Two
d-----        5/15/2019   6:45 AM        1   Three
```

```powershell
New-Item -Path * -Name temp.txt -ItemType File | Select-Object FullName
```

```Output
FullName
--------
C:\Temp\One\temp.txt
C:\Temp\Three\temp.txt
C:\Temp\Two\temp.txt
```

<span data-ttu-id="ac739-144">O `Get-ChildItem` cmdlet mostra três diretórios sob o `C:\Temp` diretório.</span><span class="sxs-lookup"><span data-stu-id="ac739-144">The `Get-ChildItem` cmdlet shows three directories under the `C:\Temp` directory.</span></span> <span data-ttu-id="ac739-145">Usando curingas o `New-Item` cmdlet cria um `temp.txt` arquivo em todos os diretórios no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="ac739-145">Using wildcards the `New-Item` cmdlet creates a `temp.txt` file in all of the directories under the current directory.</span></span> <span data-ttu-id="ac739-146">O `New-Item` cmdlet gera os itens que você criou, que é canalizado para `Select-Object` para verificar os caminhos dos arquivos recém-criados.</span><span class="sxs-lookup"><span data-stu-id="ac739-146">The `New-Item` cmdlet outputs the items you created, which is piped to `Select-Object` to verify the paths of the newly created files.</span></span>

### <span data-ttu-id="ac739-147">Exemplo 7: criar um link simbólico para um arquivo ou pasta</span><span class="sxs-lookup"><span data-stu-id="ac739-147">Example 7: Create a symbolic link to a file or folder</span></span>

<span data-ttu-id="ac739-148">Este exemplo cria um link simbólico para o arquivo de Notice.txt na pasta atual.</span><span class="sxs-lookup"><span data-stu-id="ac739-148">This example creates a symbolic link to the Notice.txt file in the current folder.</span></span>

```powershell
$link = New-Item -ItemType SymbolicLink -Path .\link -Target .\Notice.txt
$link | Select-Object LinkType, Target
```

```Output
LinkType     Target
--------     ------
SymbolicLink {.\Notice.txt}
```

<span data-ttu-id="ac739-149">Neste exemplo, **target** é um alias para o parâmetro **Value** .</span><span class="sxs-lookup"><span data-stu-id="ac739-149">In this example, **Target** is an alias for the **Value** parameter.</span></span> <span data-ttu-id="ac739-150">O destino do link simbólico pode ser um caminho relativo.</span><span class="sxs-lookup"><span data-stu-id="ac739-150">The target of the symbolic link can be a relative path.</span></span> <span data-ttu-id="ac739-151">Antes do PowerShell v 6.2, o destino deve ser um caminho totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="ac739-151">Prior to PowerShell v6.2, the target must be a fully-qualified path.</span></span>

<span data-ttu-id="ac739-152">A partir do PowerShell 7,1, agora você pode criar um **SymbolicLink** para uma pasta no Windows usando um caminho relativo.</span><span class="sxs-lookup"><span data-stu-id="ac739-152">Beginning in PowerShell 7.1, you can now create to a **SymbolicLink** to a folder on Windows using a relative path.</span></span>

### <span data-ttu-id="ac739-153">Exemplo 8: usar o parâmetro-Force para tentar recriar pastas</span><span class="sxs-lookup"><span data-stu-id="ac739-153">Example 8: Use the -Force parameter to attempt to recreate folders</span></span>

<span data-ttu-id="ac739-154">Este exemplo cria uma pasta com um arquivo dentro de.</span><span class="sxs-lookup"><span data-stu-id="ac739-154">This example creates a folder with a file inside.</span></span> <span data-ttu-id="ac739-155">Em seguida, o tenta criar a mesma pasta usando `-Force` .</span><span class="sxs-lookup"><span data-stu-id="ac739-155">Then, attempts to create the same folder using `-Force`.</span></span> <span data-ttu-id="ac739-156">Ele não substituirá a pasta, mas simplesmente retornará o objeto de pasta existente com o arquivo criado intacto.</span><span class="sxs-lookup"><span data-stu-id="ac739-156">It will not overwrite the folder but simply return the existing folder object with the file created intact.</span></span>

```powershell
PS> New-Item -Path .\TestFolder -ItemType Directory
PS> New-Item -Path .\TestFolder\TestFile.txt -ItemType File

PS> New-Item -Path .\TestFolder -ItemType Directory -Force

    Directory: C:\
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         5/1/2020   8:03 AM                TestFolder

PS> Get-ChildItem .\TestFolder\

    Directory: C:\TestFolder
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:03 AM              0 TestFile.txt
```

### <span data-ttu-id="ac739-157">Exemplo 9: usar o parâmetro-Force para substituir os arquivos existentes</span><span class="sxs-lookup"><span data-stu-id="ac739-157">Example 9: Use the -Force parameter to overwrite existing files</span></span>

<span data-ttu-id="ac739-158">Este exemplo cria um arquivo com um valor e, em seguida, recria o arquivo usando `-Force` .</span><span class="sxs-lookup"><span data-stu-id="ac739-158">This example creates a file with a value and then recreates the file using `-Force`.</span></span> <span data-ttu-id="ac739-159">Isso substitui o arquivo existente e perderá seu conteúdo como você pode ver pela propriedade Length</span><span class="sxs-lookup"><span data-stu-id="ac739-159">This overwrites The existing file and it will lose it's content as you can see by the length property</span></span>

```powershell
PS> New-Item ./TestFile.txt -ItemType File -Value 'This is just a test file'

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM             24 TestFile.txt

New-Item ./TestFile.txt -ItemType File -Force

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM              0 TestFile.txt
```

> [!NOTE]
> <span data-ttu-id="ac739-160">Ao usar `New-Item` com a `-Force` opção para criar chaves do registro, o comando se comportará da mesma forma que ao substituir um arquivo.</span><span class="sxs-lookup"><span data-stu-id="ac739-160">When using `New-Item` with the `-Force` switch to create registry keys, the command will behave the same as when overwriting a file.</span></span> <span data-ttu-id="ac739-161">Se a chave do registro já existir, a chave e todos os valores e propriedades serão substituídos por uma chave do registro vazia.</span><span class="sxs-lookup"><span data-stu-id="ac739-161">If the registry key already exists, the key and all properties and values will be overwritten with an empty registry key.</span></span>

## <span data-ttu-id="ac739-162">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ac739-162">PARAMETERS</span></span>

### <span data-ttu-id="ac739-163">-Credential</span><span class="sxs-lookup"><span data-stu-id="ac739-163">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="ac739-164">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac739-164">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="ac739-165">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="ac739-165">To impersonate another user or elevate your credentials when running this cmdlet, use `Invoke-Command`.</span></span>

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

### <span data-ttu-id="ac739-166">-Force</span><span class="sxs-lookup"><span data-stu-id="ac739-166">-Force</span></span>

<span data-ttu-id="ac739-167">Força este cmdlet a criar um item que grava em um item somente leitura existente.</span><span class="sxs-lookup"><span data-stu-id="ac739-167">Forces this cmdlet to create an item that writes over an existing read-only item.</span></span> <span data-ttu-id="ac739-168">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="ac739-168">Implementation varies from provider to provider.</span></span> <span data-ttu-id="ac739-169">Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="ac739-169">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ac739-170">-ItemType</span><span class="sxs-lookup"><span data-stu-id="ac739-170">-ItemType</span></span>

<span data-ttu-id="ac739-171">Especifica o tipo de provedor especificado do novo item.</span><span class="sxs-lookup"><span data-stu-id="ac739-171">Specifies the provider-specified type of the new item.</span></span> <span data-ttu-id="ac739-172">Os valores disponíveis desse parâmetro dependem do provedor atual que você está usando.</span><span class="sxs-lookup"><span data-stu-id="ac739-172">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="ac739-173">Se o local estiver em uma `FileSystem` unidade, os seguintes valores serão permitidos:</span><span class="sxs-lookup"><span data-stu-id="ac739-173">If your location is in a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="ac739-174">Arquivo</span><span class="sxs-lookup"><span data-stu-id="ac739-174">File</span></span>
- <span data-ttu-id="ac739-175">Diretório</span><span class="sxs-lookup"><span data-stu-id="ac739-175">Directory</span></span>
- <span data-ttu-id="ac739-176">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="ac739-176">SymbolicLink</span></span>
- <span data-ttu-id="ac739-177">Junção</span><span class="sxs-lookup"><span data-stu-id="ac739-177">Junction</span></span>
- <span data-ttu-id="ac739-178">Real</span><span class="sxs-lookup"><span data-stu-id="ac739-178">HardLink</span></span>

> [!NOTE]
> <span data-ttu-id="ac739-179">A criação de um `SymbolicLink` tipo no Windows requer elevação como administrador.</span><span class="sxs-lookup"><span data-stu-id="ac739-179">Creating a `SymbolicLink` type on Windows requires elevation as administrator.</span></span> <span data-ttu-id="ac739-180">No entanto, o Windows 10 (Build 14972 ou mais recente) com o modo de desenvolvedor habilitado não requer mais a elevação da criação de links simbólicos.</span><span class="sxs-lookup"><span data-stu-id="ac739-180">However, Windows 10 (build 14972 or newer) with Developer Mode enabled no longer requires elevation creating symbolic links.</span></span>

<span data-ttu-id="ac739-181">Em uma `Certificate` unidade, esses são os valores que você pode especificar:</span><span class="sxs-lookup"><span data-stu-id="ac739-181">In a `Certificate` drive, these are the values you can specify:</span></span>

- <span data-ttu-id="ac739-182">Provedor Certificate</span><span class="sxs-lookup"><span data-stu-id="ac739-182">Certificate Provider</span></span>
- <span data-ttu-id="ac739-183">Certificado</span><span class="sxs-lookup"><span data-stu-id="ac739-183">Certificate</span></span>
- <span data-ttu-id="ac739-184">Repositório</span><span class="sxs-lookup"><span data-stu-id="ac739-184">Store</span></span>
- <span data-ttu-id="ac739-185">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="ac739-185">StoreLocation</span></span>

<span data-ttu-id="ac739-186">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="ac739-186">For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ac739-187">-Name</span><span class="sxs-lookup"><span data-stu-id="ac739-187">-Name</span></span>

<span data-ttu-id="ac739-188">Especifica o nome do novo item.</span><span class="sxs-lookup"><span data-stu-id="ac739-188">Specifies the name of the new item.</span></span> <span data-ttu-id="ac739-189">Você pode especificar o nome do novo item no valor do parâmetro **Name** ou **Path** e pode especificar o caminho do novo item no **nome** ou no valor do **caminho** .</span><span class="sxs-lookup"><span data-stu-id="ac739-189">You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.</span></span> <span data-ttu-id="ac739-190">Os nomes de itens passados usando o parâmetro **Name** são criados em relação ao valor do parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="ac739-190">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: nameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ac739-191">-Path</span><span class="sxs-lookup"><span data-stu-id="ac739-191">-Path</span></span>

<span data-ttu-id="ac739-192">Especifica o caminho do local do novo item.</span><span class="sxs-lookup"><span data-stu-id="ac739-192">Specifies the path of the location of the new item.</span></span> <span data-ttu-id="ac739-193">O padrão é o local atual quando o **caminho** é omitido.</span><span class="sxs-lookup"><span data-stu-id="ac739-193">The default is the current location when **Path** is omitted.</span></span> <span data-ttu-id="ac739-194">Você pode especificar o nome do novo item no **nome** ou incluí-lo no **caminho** .</span><span class="sxs-lookup"><span data-stu-id="ac739-194">You can specify the name of the new item in **Name** , or include it in **Path** .</span></span> <span data-ttu-id="ac739-195">Os nomes de itens passados usando o parâmetro **Name** são criados em relação ao valor do parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="ac739-195">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

<span data-ttu-id="ac739-196">Para esse cmdlet, o parâmetro **path** funciona como o parâmetro **LiteralPath** de outros cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ac739-196">For this cmdlet, the **Path** parameter works like the **LiteralPath** parameter of other cmdlets.</span></span>
<span data-ttu-id="ac739-197">Os caracteres curinga não são interpretados.</span><span class="sxs-lookup"><span data-stu-id="ac739-197">Wildcard characters are not interpreted.</span></span> <span data-ttu-id="ac739-198">Todos os caracteres são passados para o provedor do local.</span><span class="sxs-lookup"><span data-stu-id="ac739-198">All characters are passed to the location's provider.</span></span> <span data-ttu-id="ac739-199">O provedor pode não dar suporte a todos os caracteres.</span><span class="sxs-lookup"><span data-stu-id="ac739-199">The provider may not support all characters.</span></span> <span data-ttu-id="ac739-200">Por exemplo, você não pode criar um nome de arquivo que contenha um caractere de asterisco ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="ac739-200">For example, you cannot create a filename that contains an asterisk (`*`) character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: pathSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ac739-201">-Value</span><span class="sxs-lookup"><span data-stu-id="ac739-201">-Value</span></span>

<span data-ttu-id="ac739-202">Especifica o valor do novo item.</span><span class="sxs-lookup"><span data-stu-id="ac739-202">Specifies the value of the new item.</span></span> <span data-ttu-id="ac739-203">Você também pode canalizar um valor para `New-Item` .</span><span class="sxs-lookup"><span data-stu-id="ac739-203">You can also pipe a value to `New-Item`.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Target

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ac739-204">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ac739-204">-Confirm</span></span>

<span data-ttu-id="ac739-205">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ac739-205">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ac739-206">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ac739-206">-WhatIf</span></span>

<span data-ttu-id="ac739-207">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="ac739-207">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ac739-208">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="ac739-208">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ac739-209">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ac739-209">CommonParameters</span></span>

<span data-ttu-id="ac739-210">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="ac739-210">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="ac739-211">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="ac739-211">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="ac739-212">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ac739-212">INPUTS</span></span>

### <span data-ttu-id="ac739-213">System.Object</span><span class="sxs-lookup"><span data-stu-id="ac739-213">System.Object</span></span>

<span data-ttu-id="ac739-214">É possível canalizar um valor para o novo item para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ac739-214">You can pipe a value for the new item to this cmdlet.</span></span>

## <span data-ttu-id="ac739-215">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ac739-215">OUTPUTS</span></span>

### <span data-ttu-id="ac739-216">System.Object</span><span class="sxs-lookup"><span data-stu-id="ac739-216">System.Object</span></span>

<span data-ttu-id="ac739-217">Esse cmdlet retorna o item que ele cria.</span><span class="sxs-lookup"><span data-stu-id="ac739-217">This cmdlet returns the item that it creates.</span></span>

## <span data-ttu-id="ac739-218">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ac739-218">NOTES</span></span>

<span data-ttu-id="ac739-219">`New-Item` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="ac739-219">`New-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="ac739-220">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="ac739-220">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="ac739-221">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="ac739-221">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="ac739-222">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ac739-222">RELATED LINKS</span></span>

[<span data-ttu-id="ac739-223">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="ac739-223">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="ac739-224">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="ac739-224">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="ac739-225">Get-Item</span><span class="sxs-lookup"><span data-stu-id="ac739-225">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="ac739-226">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="ac739-226">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="ac739-227">Move-Item</span><span class="sxs-lookup"><span data-stu-id="ac739-227">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="ac739-228">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="ac739-228">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="ac739-229">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="ac739-229">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="ac739-230">Set-Item</span><span class="sxs-lookup"><span data-stu-id="ac739-230">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="ac739-231">about_Providers</span><span class="sxs-lookup"><span data-stu-id="ac739-231">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

