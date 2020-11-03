---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: b1657d369d44d575ee7bed8b76d36224ea2748f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193970"
---
# <span data-ttu-id="23f73-103">New-Item</span><span class="sxs-lookup"><span data-stu-id="23f73-103">New-Item</span></span>

## <span data-ttu-id="23f73-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="23f73-104">SYNOPSIS</span></span>
<span data-ttu-id="23f73-105">Cria um novo item.</span><span class="sxs-lookup"><span data-stu-id="23f73-105">Creates a new item.</span></span>

## <span data-ttu-id="23f73-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23f73-106">SYNTAX</span></span>

### <span data-ttu-id="23f73-107">caminhoset (padrão)</span><span class="sxs-lookup"><span data-stu-id="23f73-107">pathSet (Default)</span></span>

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="23f73-108">nome do</span><span class="sxs-lookup"><span data-stu-id="23f73-108">nameSet</span></span>

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="23f73-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23f73-109">DESCRIPTION</span></span>

<span data-ttu-id="23f73-110">O `New-Item` cmdlet cria um novo item e define seu valor.</span><span class="sxs-lookup"><span data-stu-id="23f73-110">The `New-Item` cmdlet creates a new item and sets its value.</span></span> <span data-ttu-id="23f73-111">Os tipos de itens que podem ser criados dependem do local do item.</span><span class="sxs-lookup"><span data-stu-id="23f73-111">The types of items that can be created depend on the location of the item.</span></span> <span data-ttu-id="23f73-112">Por exemplo, no sistema de arquivos, o `New-Item` cria arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="23f73-112">For example, in the file system, `New-Item` creates files and folders.</span></span> <span data-ttu-id="23f73-113">No registro, o `New-Item` cria chaves e entradas do registro.</span><span class="sxs-lookup"><span data-stu-id="23f73-113">In the registry, `New-Item` creates registry keys and entries.</span></span>

<span data-ttu-id="23f73-114">`New-Item` também pode definir o valor dos itens que ele cria.</span><span class="sxs-lookup"><span data-stu-id="23f73-114">`New-Item` can also set the value of the items that it creates.</span></span> <span data-ttu-id="23f73-115">Por exemplo, quando ele cria um novo arquivo, o `New-Item` pode adicionar conteúdo inicial ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="23f73-115">For example, when it creates a new file, `New-Item` can add initial content to the file.</span></span>

## <span data-ttu-id="23f73-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="23f73-116">EXAMPLES</span></span>

### <span data-ttu-id="23f73-117">Exemplo 1: criar um arquivo no diretório atual</span><span class="sxs-lookup"><span data-stu-id="23f73-117">Example 1: Create a file in the current directory</span></span>

<span data-ttu-id="23f73-118">Esse comando cria um arquivo de texto chamado "testfile1.txt" no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="23f73-118">This command creates a text file that is named "testfile1.txt" in the current directory.</span></span> <span data-ttu-id="23f73-119">O ponto ('. ') no valor do parâmetro **path** indica o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="23f73-119">The dot ('.') in the value of the **Path** parameter indicates the current directory.</span></span> <span data-ttu-id="23f73-120">O texto entre aspas que segue o parâmetro de **valor** é adicionado ao arquivo como conteúdo.</span><span class="sxs-lookup"><span data-stu-id="23f73-120">The quoted text that follows the **Value** parameter is added to the file as content.</span></span>

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### <span data-ttu-id="23f73-121">Exemplo 2: criar um diretório</span><span class="sxs-lookup"><span data-stu-id="23f73-121">Example 2: Create a directory</span></span>

<span data-ttu-id="23f73-122">Esse comando cria um diretório chamado "LogFiles" na `C:` unidade.</span><span class="sxs-lookup"><span data-stu-id="23f73-122">This command creates a directory named "Logfiles" in the `C:` drive.</span></span> <span data-ttu-id="23f73-123">O parâmetro **ItemType** especifica que o novo item é um diretório, não um arquivo ou outro objeto do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="23f73-123">The **ItemType** parameter specifies that the new item is a directory, not a file or other file system object.</span></span>

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### <span data-ttu-id="23f73-124">Exemplo 3: criar um perfil</span><span class="sxs-lookup"><span data-stu-id="23f73-124">Example 3: Create a profile</span></span>

<span data-ttu-id="23f73-125">Esse comando cria um perfil do PowerShell no caminho especificado pela `$profile` variável.</span><span class="sxs-lookup"><span data-stu-id="23f73-125">This command creates a PowerShell profile in the path that is specified by the `$profile` variable.</span></span>

<span data-ttu-id="23f73-126">Você pode usar perfis para personalizar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23f73-126">You can use profiles to customize PowerShell.</span></span> <span data-ttu-id="23f73-127">`$profile` é uma variável automática (interna) que armazena o caminho e o nome de arquivo do perfil "CurrentUser/CurrentHost".</span><span class="sxs-lookup"><span data-stu-id="23f73-127">`$profile` is an automatic (built-in) variable that stores the path and file name of the "CurrentUser/CurrentHost" profile.</span></span> <span data-ttu-id="23f73-128">Por padrão, o perfil não existe, mesmo que o PowerShell armazene um caminho e um nome de arquivo para ele.</span><span class="sxs-lookup"><span data-stu-id="23f73-128">By default, the profile does not exist, even though PowerShell stores a path and file name for it.</span></span>

<span data-ttu-id="23f73-129">Nesse comando, a `$profile` variável representa o caminho do arquivo.</span><span class="sxs-lookup"><span data-stu-id="23f73-129">In this command, the `$profile` variable represents the path of the file.</span></span> <span data-ttu-id="23f73-130">O parâmetro **ItemType** especifica que o comando cria um arquivo.</span><span class="sxs-lookup"><span data-stu-id="23f73-130">**ItemType** parameter specifies that the command creates a file.</span></span> <span data-ttu-id="23f73-131">O parâmetro **Force** permite criar um arquivo no caminho do perfil, mesmo quando os diretórios no caminho não existem.</span><span class="sxs-lookup"><span data-stu-id="23f73-131">The **Force** parameter lets you create a file in the profile path, even when the directories in the path do not exist.</span></span>

<span data-ttu-id="23f73-132">Depois de criar um perfil, você pode inserir aliases, funções e scripts no perfil para personalizar o Shell.</span><span class="sxs-lookup"><span data-stu-id="23f73-132">After you create a profile, you can enter aliases, functions, and scripts in the profile to customize your shell.</span></span>

<span data-ttu-id="23f73-133">Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) e [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="23f73-133">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

> [!NOTE]
> <span data-ttu-id="23f73-134">Quando você cria um arquivo usando esse método, o arquivo resultante é codificado como UTF-8 sem uma BOM (marca de ordem de byte).</span><span class="sxs-lookup"><span data-stu-id="23f73-134">When you create a file using this method, the resulting file is encoded as UTF-8 without a byte-order-mark (BOM).</span></span>

### <span data-ttu-id="23f73-135">Exemplo 4: criar um diretório em um diretório diferente</span><span class="sxs-lookup"><span data-stu-id="23f73-135">Example 4: Create a directory in a different directory</span></span>

<span data-ttu-id="23f73-136">Este exemplo cria um novo diretório de scripts no diretório "C:\PS-Test".</span><span class="sxs-lookup"><span data-stu-id="23f73-136">This example creates a new Scripts directory in the "C:\PS-Test" directory.</span></span>

<span data-ttu-id="23f73-137">O nome do novo item de diretório, "scripts", é incluído no valor do parâmetro **path** , em vez de ser especificado no valor de **Name** .</span><span class="sxs-lookup"><span data-stu-id="23f73-137">The name of the new directory item, "Scripts", is included in the value of **Path** parameter, instead of being specified in the value of **Name** .</span></span> <span data-ttu-id="23f73-138">Conforme indicado pela sintaxe, ambos os formatos de comando são válidos.</span><span class="sxs-lookup"><span data-stu-id="23f73-138">As indicated by the syntax, either command form is valid.</span></span>

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### <span data-ttu-id="23f73-139">Exemplo 5: criar vários arquivos</span><span class="sxs-lookup"><span data-stu-id="23f73-139">Example 5: Create multiple files</span></span>

<span data-ttu-id="23f73-140">Este exemplo cria arquivos em dois diretórios diferentes.</span><span class="sxs-lookup"><span data-stu-id="23f73-140">This example creates files in two different directories.</span></span> <span data-ttu-id="23f73-141">Como o **caminho** usa várias cadeias de caracteres, você pode usá-lo para criar vários itens.</span><span class="sxs-lookup"><span data-stu-id="23f73-141">Because **Path** takes multiple strings, you can use it to create multiple items.</span></span>

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### <span data-ttu-id="23f73-142">Exemplo 6: usar o parâmetro-Force para tentar recriar pastas</span><span class="sxs-lookup"><span data-stu-id="23f73-142">Example 6: Use the -Force parameter to attempt to recreate folders</span></span>

<span data-ttu-id="23f73-143">Este exemplo cria uma pasta com um arquivo dentro de.</span><span class="sxs-lookup"><span data-stu-id="23f73-143">This example creates a folder with a file inside.</span></span> <span data-ttu-id="23f73-144">Em seguida, o tenta criar a mesma pasta usando `-Force` .</span><span class="sxs-lookup"><span data-stu-id="23f73-144">Then, attempts to create the same folder using `-Force`.</span></span> <span data-ttu-id="23f73-145">Ele não substituirá a pasta, mas simplesmente retornará o objeto de pasta existente com o arquivo criado intacto.</span><span class="sxs-lookup"><span data-stu-id="23f73-145">It will not overwrite the folder but simply return the existing folder object with the file created intact.</span></span>

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

### <span data-ttu-id="23f73-146">Exemplo 7: usar o parâmetro-Force para substituir os arquivos existentes</span><span class="sxs-lookup"><span data-stu-id="23f73-146">Example 7: Use the -Force parameter to overwrite existing files</span></span>

<span data-ttu-id="23f73-147">Este exemplo cria um arquivo com um valor e, em seguida, recria o arquivo usando `-Force` .</span><span class="sxs-lookup"><span data-stu-id="23f73-147">This example creates a file with a value and then recreates the file using `-Force`.</span></span> <span data-ttu-id="23f73-148">Isso substitui o arquivo existente e perderá seu conteúdo como você pode ver pela propriedade Length</span><span class="sxs-lookup"><span data-stu-id="23f73-148">This overwrites The existing file and it will lose it's content as you can see by the length property</span></span>

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
> <span data-ttu-id="23f73-149">Ao usar `New-Item` com a `-Force` opção para criar chaves do registro, o comando se comportará da mesma forma que ao substituir um arquivo.</span><span class="sxs-lookup"><span data-stu-id="23f73-149">When using `New-Item` with the `-Force` switch to create registry keys, the command will behave the same as when overwriting a file.</span></span> <span data-ttu-id="23f73-150">Se a chave do registro já existir, a chave e todos os valores e propriedades serão substituídos por uma chave do registro vazia.</span><span class="sxs-lookup"><span data-stu-id="23f73-150">If the registry key already exists, the key and all properties and values will be overwritten with an empty registry key.</span></span>

## <span data-ttu-id="23f73-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23f73-151">PARAMETERS</span></span>

### <span data-ttu-id="23f73-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="23f73-152">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="23f73-153">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23f73-153">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="23f73-154">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="23f73-154">To impersonate another user or elevate your credentials when running this cmdlet, use `Invoke-Command`.</span></span>

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

### <span data-ttu-id="23f73-155">-Force</span><span class="sxs-lookup"><span data-stu-id="23f73-155">-Force</span></span>

<span data-ttu-id="23f73-156">Força este cmdlet a criar um item que grava em um item somente leitura existente.</span><span class="sxs-lookup"><span data-stu-id="23f73-156">Forces this cmdlet to create an item that writes over an existing read-only item.</span></span> <span data-ttu-id="23f73-157">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="23f73-157">Implementation varies from provider to provider.</span></span> <span data-ttu-id="23f73-158">Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="23f73-158">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="23f73-159">-ItemType</span><span class="sxs-lookup"><span data-stu-id="23f73-159">-ItemType</span></span>

<span data-ttu-id="23f73-160">Especifica o tipo de provedor especificado do novo item.</span><span class="sxs-lookup"><span data-stu-id="23f73-160">Specifies the provider-specified type of the new item.</span></span> <span data-ttu-id="23f73-161">Os valores disponíveis desse parâmetro dependem do provedor atual que você está usando.</span><span class="sxs-lookup"><span data-stu-id="23f73-161">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="23f73-162">Se o local estiver em uma `FileSystem` unidade, os seguintes valores serão permitidos:</span><span class="sxs-lookup"><span data-stu-id="23f73-162">If your location is in a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="23f73-163">Arquivo</span><span class="sxs-lookup"><span data-stu-id="23f73-163">File</span></span>
- <span data-ttu-id="23f73-164">Diretório</span><span class="sxs-lookup"><span data-stu-id="23f73-164">Directory</span></span>
- <span data-ttu-id="23f73-165">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="23f73-165">SymbolicLink</span></span>
- <span data-ttu-id="23f73-166">Junção</span><span class="sxs-lookup"><span data-stu-id="23f73-166">Junction</span></span>
- <span data-ttu-id="23f73-167">Real</span><span class="sxs-lookup"><span data-stu-id="23f73-167">HardLink</span></span>

<span data-ttu-id="23f73-168">Quando você cria um arquivo usando esse método, o arquivo resultante é codificado como UTF-8 sem uma BOM (marca de ordem de byte).</span><span class="sxs-lookup"><span data-stu-id="23f73-168">When you create a file using this method, the resulting file is encoded as UTF-8 without a byte-order-mark (BOM).</span></span>

<span data-ttu-id="23f73-169">Em uma `Certificate` unidade, esses são os valores que você pode especificar:</span><span class="sxs-lookup"><span data-stu-id="23f73-169">In a `Certificate` drive, these are the values you can specify:</span></span>

- <span data-ttu-id="23f73-170">Provedor Certificate</span><span class="sxs-lookup"><span data-stu-id="23f73-170">Certificate Provider</span></span>
- <span data-ttu-id="23f73-171">Certificado</span><span class="sxs-lookup"><span data-stu-id="23f73-171">Certificate</span></span>
- <span data-ttu-id="23f73-172">Repositório</span><span class="sxs-lookup"><span data-stu-id="23f73-172">Store</span></span>
- <span data-ttu-id="23f73-173">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="23f73-173">StoreLocation</span></span>

<span data-ttu-id="23f73-174">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="23f73-174">For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="23f73-175">-Name</span><span class="sxs-lookup"><span data-stu-id="23f73-175">-Name</span></span>

<span data-ttu-id="23f73-176">Especifica o nome do novo item.</span><span class="sxs-lookup"><span data-stu-id="23f73-176">Specifies the name of the new item.</span></span> <span data-ttu-id="23f73-177">Você pode especificar o nome do novo item no valor do parâmetro **Name** ou **Path** e pode especificar o caminho do novo item no **nome** ou no valor do **caminho** .</span><span class="sxs-lookup"><span data-stu-id="23f73-177">You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.</span></span> <span data-ttu-id="23f73-178">Os nomes de itens passados usando o parâmetro **Name** são criados em relação ao valor do parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="23f73-178">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

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

### <span data-ttu-id="23f73-179">-Path</span><span class="sxs-lookup"><span data-stu-id="23f73-179">-Path</span></span>

<span data-ttu-id="23f73-180">Especifica o caminho do local do novo item.</span><span class="sxs-lookup"><span data-stu-id="23f73-180">Specifies the path of the location of the new item.</span></span> <span data-ttu-id="23f73-181">O padrão é o local atual quando o **caminho** é omitido.</span><span class="sxs-lookup"><span data-stu-id="23f73-181">The default is the current location when **Path** is omitted.</span></span> <span data-ttu-id="23f73-182">Você pode especificar o nome do novo item no **nome** ou incluí-lo no **caminho** .</span><span class="sxs-lookup"><span data-stu-id="23f73-182">You can specify the name of the new item in **Name** , or include it in **Path** .</span></span> <span data-ttu-id="23f73-183">Os nomes de itens passados usando o parâmetro **Name** são criados em relação ao valor do parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="23f73-183">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

<span data-ttu-id="23f73-184">Para esse cmdlet, o parâmetro **path** funciona como o parâmetro **LiteralPath** de outros cmdlets.</span><span class="sxs-lookup"><span data-stu-id="23f73-184">For this cmdlet, the **Path** parameter works like the **LiteralPath** parameter of other cmdlets.</span></span>
<span data-ttu-id="23f73-185">Os caracteres curinga não são interpretados.</span><span class="sxs-lookup"><span data-stu-id="23f73-185">Wildcard characters are not interpreted.</span></span> <span data-ttu-id="23f73-186">Todos os caracteres são passados para o provedor do local.</span><span class="sxs-lookup"><span data-stu-id="23f73-186">All characters are passed to the location's provider.</span></span> <span data-ttu-id="23f73-187">O provedor pode não dar suporte a todos os caracteres.</span><span class="sxs-lookup"><span data-stu-id="23f73-187">The provider may not support all characters.</span></span> <span data-ttu-id="23f73-188">Por exemplo, você não pode criar um nome de arquivo que contenha um caractere de asterisco ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="23f73-188">For example, you cannot create a filename that contains an asterisk (`*`) character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: pathSet, nameSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="23f73-189">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="23f73-189">-UseTransaction</span></span>

<span data-ttu-id="23f73-190">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="23f73-190">Includes the command in the active transaction.</span></span> <span data-ttu-id="23f73-191">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="23f73-191">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="23f73-192">Para obter mais informações, consulte [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="23f73-192">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="23f73-193">-Value</span><span class="sxs-lookup"><span data-stu-id="23f73-193">-Value</span></span>

<span data-ttu-id="23f73-194">Especifica o valor do novo item.</span><span class="sxs-lookup"><span data-stu-id="23f73-194">Specifies the value of the new item.</span></span> <span data-ttu-id="23f73-195">Você também pode canalizar um valor para `New-Item` .</span><span class="sxs-lookup"><span data-stu-id="23f73-195">You can also pipe a value to `New-Item`.</span></span>

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

### <span data-ttu-id="23f73-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="23f73-196">-Confirm</span></span>

<span data-ttu-id="23f73-197">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23f73-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="23f73-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="23f73-198">-WhatIf</span></span>

<span data-ttu-id="23f73-199">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="23f73-199">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="23f73-200">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="23f73-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="23f73-201">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="23f73-201">CommonParameters</span></span>

<span data-ttu-id="23f73-202">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="23f73-202">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="23f73-203">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="23f73-203">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="23f73-204">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="23f73-204">INPUTS</span></span>

### <span data-ttu-id="23f73-205">System.Object</span><span class="sxs-lookup"><span data-stu-id="23f73-205">System.Object</span></span>

<span data-ttu-id="23f73-206">É possível canalizar um valor para o novo item para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23f73-206">You can pipe a value for the new item to this cmdlet.</span></span>

## <span data-ttu-id="23f73-207">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="23f73-207">OUTPUTS</span></span>

### <span data-ttu-id="23f73-208">System.Object</span><span class="sxs-lookup"><span data-stu-id="23f73-208">System.Object</span></span>

<span data-ttu-id="23f73-209">Esse cmdlet retorna o item que ele cria.</span><span class="sxs-lookup"><span data-stu-id="23f73-209">This cmdlet returns the item that it creates.</span></span>

## <span data-ttu-id="23f73-210">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="23f73-210">NOTES</span></span>

<span data-ttu-id="23f73-211">`New-Item` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="23f73-211">`New-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="23f73-212">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="23f73-212">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="23f73-213">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="23f73-213">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="23f73-214">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="23f73-214">RELATED LINKS</span></span>

[<span data-ttu-id="23f73-215">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="23f73-215">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="23f73-216">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="23f73-216">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="23f73-217">Get-Item</span><span class="sxs-lookup"><span data-stu-id="23f73-217">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="23f73-218">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="23f73-218">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="23f73-219">Move-Item</span><span class="sxs-lookup"><span data-stu-id="23f73-219">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="23f73-220">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="23f73-220">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="23f73-221">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="23f73-221">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="23f73-222">Set-Item</span><span class="sxs-lookup"><span data-stu-id="23f73-222">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="23f73-223">about_Providers</span><span class="sxs-lookup"><span data-stu-id="23f73-223">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
