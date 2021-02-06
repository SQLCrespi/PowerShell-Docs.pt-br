---
external help file: Microsoft.PowerShell.Archive-help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 02/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/compress-archive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compress-Archive
ms.openlocfilehash: 58807ba0745a6b09e7956547425c489b427d4f4b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596776"
---
# <span data-ttu-id="08e50-102">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="08e50-102">Compress-Archive</span></span>

## <span data-ttu-id="08e50-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="08e50-103">SYNOPSIS</span></span>
<span data-ttu-id="08e50-104">Cria um arquivo morto compactado, ou compactado, de arquivos e diretórios especificados.</span><span class="sxs-lookup"><span data-stu-id="08e50-104">Creates a compressed archive, or zipped file, from specified files and directories.</span></span>

## <span data-ttu-id="08e50-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="08e50-105">SYNTAX</span></span>

### <span data-ttu-id="08e50-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="08e50-106">Path (Default)</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="08e50-107">PathWithUpdate</span><span class="sxs-lookup"><span data-stu-id="08e50-107">PathWithUpdate</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Update
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="08e50-108">PathWithForce</span><span class="sxs-lookup"><span data-stu-id="08e50-108">PathWithForce</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Force
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="08e50-109">LiteralPathWithUpdate</span><span class="sxs-lookup"><span data-stu-id="08e50-109">LiteralPathWithUpdate</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Update [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="08e50-110">LiteralPathWithForce</span><span class="sxs-lookup"><span data-stu-id="08e50-110">LiteralPathWithForce</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Force [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="08e50-111">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="08e50-111">LiteralPath</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="08e50-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e50-112">DESCRIPTION</span></span>

<span data-ttu-id="08e50-113">O `Compress-Archive` cmdlet cria um arquivo morto compactado, ou zipado, de um ou mais arquivos ou diretórios especificados.</span><span class="sxs-lookup"><span data-stu-id="08e50-113">The `Compress-Archive` cmdlet creates a compressed, or zipped, archive file from one or more specified files or directories.</span></span> <span data-ttu-id="08e50-114">Um arquivo compacta vários arquivos, com compactação opcional, em um único arquivos zipados para distribuição e armazenamento mais fáceis.</span><span class="sxs-lookup"><span data-stu-id="08e50-114">An archive packages multiple files, with optional compression, into a single zipped file for easier distribution and storage.</span></span> <span data-ttu-id="08e50-115">Um arquivo morto pode ser compactado usando o algoritmo de compactação especificado pelo parâmetro **CompressionLevel** .</span><span class="sxs-lookup"><span data-stu-id="08e50-115">An archive file can be compressed by using the compression algorithm specified by the **CompressionLevel** parameter.</span></span>

<span data-ttu-id="08e50-116">O `Compress-Archive` cmdlet usa o arquivo de API Microsoft .NET [System.IO.Compression.Zip](/dotnet/api/system.io.compression.ziparchive) para compactar arquivos.</span><span class="sxs-lookup"><span data-stu-id="08e50-116">The `Compress-Archive` cmdlet uses the Microsoft .NET API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) to compress files.</span></span>
<span data-ttu-id="08e50-117">O tamanho máximo do arquivo é 2 GB, pois há uma limitação da API subjacente.</span><span class="sxs-lookup"><span data-stu-id="08e50-117">The maximum file size is 2 GB because there's a limitation of the underlying API.</span></span>

<span data-ttu-id="08e50-118">Alguns exemplos usam nivelamento para reduzir o tamanho da linha dos exemplos de código.</span><span class="sxs-lookup"><span data-stu-id="08e50-118">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="08e50-119">Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="08e50-119">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="08e50-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="08e50-120">EXAMPLES</span></span>

### <span data-ttu-id="08e50-121">Exemplo 1: compactar arquivos para criar um arquivo morto</span><span class="sxs-lookup"><span data-stu-id="08e50-121">Example 1: Compress files to create an archive file</span></span>

<span data-ttu-id="08e50-122">Este exemplo compacta arquivos de diretórios diferentes e cria um arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-122">This example compresses files from different directories and creates an archive file.</span></span> <span data-ttu-id="08e50-123">Um caractere curinga é usado para obter todos os arquivos com uma extensão de arquivo específica.</span><span class="sxs-lookup"><span data-stu-id="08e50-123">A wildcard is used to get all files with a particular file extension.</span></span> <span data-ttu-id="08e50-124">Não há nenhuma estrutura de diretório no arquivo morto porque o **caminho** especifica apenas nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="08e50-124">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
  Path = "C:\Reference\Draftdoc.docx", "C:\Reference\Images\*.vsd"
  CompressionLevel = "Fastest"
  DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="08e50-125">O parâmetro **path** aceita nomes de arquivo e nomes de arquivo específicos com curingas, `*.vsd` .</span><span class="sxs-lookup"><span data-stu-id="08e50-125">The **Path** parameter accepts specific file names and file names with wildcards, `*.vsd`.</span></span> <span data-ttu-id="08e50-126">O **caminho** usa uma lista separada por vírgulas para obter arquivos de diretórios diferentes.</span><span class="sxs-lookup"><span data-stu-id="08e50-126">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="08e50-127">O nível de compactação é **mais rápido** para reduzir o tempo de processamento.</span><span class="sxs-lookup"><span data-stu-id="08e50-127">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="08e50-128">O parâmetro **DestinationPath** especifica o local para o `Draft.zip` arquivo.</span><span class="sxs-lookup"><span data-stu-id="08e50-128">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="08e50-129">O `Draft.zip` arquivo contém `Draftdoc.docx` e todos os arquivos com uma `.vsd` extensão.</span><span class="sxs-lookup"><span data-stu-id="08e50-129">The `Draft.zip` file contains `Draftdoc.docx` and all the files with a `.vsd` extension.</span></span>

### <span data-ttu-id="08e50-130">Exemplo 2: compactar arquivos usando um LiteralPath</span><span class="sxs-lookup"><span data-stu-id="08e50-130">Example 2: Compress files using a LiteralPath</span></span>

<span data-ttu-id="08e50-131">Este exemplo compacta arquivos nomeados específicos e cria um novo arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-131">This example compresses specific named files and creates a new archive file.</span></span> <span data-ttu-id="08e50-132">Não há nenhuma estrutura de diretório no arquivo morto porque o **caminho** especifica apenas nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="08e50-132">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
LiteralPath= "C:\Reference\Draft Doc.docx", "C:\Reference\Images\diagram2.vsd"
CompressionLevel = "Fastest"
DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="08e50-133">O caminho absoluto e os nomes de arquivo são usados porque o parâmetro **LiteralPath** não aceita curingas.</span><span class="sxs-lookup"><span data-stu-id="08e50-133">Absolute path and file names are used because the **LiteralPath** parameter doesn't accept wildcards.</span></span> <span data-ttu-id="08e50-134">O **caminho** usa uma lista separada por vírgulas para obter arquivos de diretórios diferentes.</span><span class="sxs-lookup"><span data-stu-id="08e50-134">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="08e50-135">O nível de compactação é **mais rápido** para reduzir o tempo de processamento.</span><span class="sxs-lookup"><span data-stu-id="08e50-135">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="08e50-136">O parâmetro **DestinationPath** especifica o local para o `Draft.zip` arquivo.</span><span class="sxs-lookup"><span data-stu-id="08e50-136">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="08e50-137">O `Draft.zip` arquivo contém apenas `Draftdoc.docx` e `diagram2.vsd` .</span><span class="sxs-lookup"><span data-stu-id="08e50-137">The `Draft.zip` file only contains `Draftdoc.docx` and `diagram2.vsd`.</span></span>

### <span data-ttu-id="08e50-138">Exemplo 3: compactar um diretório que inclui o diretório raiz</span><span class="sxs-lookup"><span data-stu-id="08e50-138">Example 3: Compress a directory that includes the root directory</span></span>

<span data-ttu-id="08e50-139">Este exemplo compacta um diretório e cria um arquivo morto que **inclui** o diretório raiz e todos os seus arquivos e subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="08e50-139">This example compresses a directory and creates an archive file that **includes** the root directory, and all its files and subdirectories.</span></span> <span data-ttu-id="08e50-140">O arquivo morto tem uma estrutura de diretório porque o **caminho** especifica um diretório raiz.</span><span class="sxs-lookup"><span data-stu-id="08e50-140">The archive file has a directory structure because the **Path** specifies a root directory.</span></span>

```powershell
Compress-Archive -Path C:\Reference -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="08e50-141">`Compress-Archive` usa o parâmetro **path** para especificar o diretório raiz, `C:\Reference` .</span><span class="sxs-lookup"><span data-stu-id="08e50-141">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference`.</span></span> <span data-ttu-id="08e50-142">O parâmetro **DestinationPath** especifica o local para o arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-142">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="08e50-143">O `Draft.zip` arquivo morto inclui o `Reference` diretório raiz e todos os seus arquivos e subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="08e50-143">The `Draft.zip` archive includes the `Reference` root directory, and all its files and subdirectories.</span></span>

### <span data-ttu-id="08e50-144">Exemplo 4: compactar um diretório que exclui o diretório raiz</span><span class="sxs-lookup"><span data-stu-id="08e50-144">Example 4: Compress a directory that excludes the root directory</span></span>

<span data-ttu-id="08e50-145">Este exemplo compacta um diretório e cria um arquivo morto que **exclui** o diretório raiz porque o **caminho** usa um curinga asterisco ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="08e50-145">This example compresses a directory and creates an archive file that **excludes** the root directory because the **Path** uses an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="08e50-146">O arquivo contém uma estrutura de diretório que contém os arquivos e subdiretórios do diretório raiz.</span><span class="sxs-lookup"><span data-stu-id="08e50-146">The archive contains a directory structure that contains the root directory's files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference\* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="08e50-147">`Compress-Archive` usa o parâmetro **path** para especificar o diretório raiz, `C:\Reference` com um curinga asterisco ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="08e50-147">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="08e50-148">O parâmetro **DestinationPath** especifica o local para o arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-148">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="08e50-149">O `Draft.zip` arquivo contém os arquivos e subdiretórios do diretório raiz.</span><span class="sxs-lookup"><span data-stu-id="08e50-149">The `Draft.zip` archive contains the root directory's files and subdirectories.</span></span> <span data-ttu-id="08e50-150">O `Reference` diretório raiz é excluído do arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-150">The `Reference` root directory is excluded from the archive.</span></span>

### <span data-ttu-id="08e50-151">Exemplo 5: compactar apenas os arquivos em um diretório raiz</span><span class="sxs-lookup"><span data-stu-id="08e50-151">Example 5: Compress only the files in a root directory</span></span>

<span data-ttu-id="08e50-152">Este exemplo compacta apenas os arquivos em um diretório raiz e cria um arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-152">This example compresses only the files in a root directory and creates an archive file.</span></span> <span data-ttu-id="08e50-153">Não há nenhuma estrutura de diretório no arquivo porque apenas os arquivos são compactados.</span><span class="sxs-lookup"><span data-stu-id="08e50-153">There's no directory structure in the archive because only files are compressed.</span></span>

```powershell
Compress-Archive -Path C:\Reference\*.* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="08e50-154">`Compress-Archive` usa o parâmetro **path** para especificar o diretório raiz, `C:\Reference` com um curinga **asterisco-ponto-asterisco** ( `*.*` ).</span><span class="sxs-lookup"><span data-stu-id="08e50-154">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with a **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="08e50-155">O parâmetro **DestinationPath** especifica o local para o arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-155">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="08e50-156">O `Draft.zip` arquivo morto contém apenas os `Reference` arquivos do diretório raiz e o diretório raiz é excluído.</span><span class="sxs-lookup"><span data-stu-id="08e50-156">The `Draft.zip` archive only contains the `Reference` root directory's files and the root directory is excluded.</span></span>

### <span data-ttu-id="08e50-157">Exemplo 6: usar o pipeline para arquivar arquivos</span><span class="sxs-lookup"><span data-stu-id="08e50-157">Example 6: Use the pipeline to archive files</span></span>

<span data-ttu-id="08e50-158">Este exemplo envia arquivos para baixo do pipeline para criar um arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-158">This example sends files down the pipeline to create an archive.</span></span> <span data-ttu-id="08e50-159">Não há nenhuma estrutura de diretório no arquivo morto porque o **caminho** especifica apenas nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="08e50-159">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
Get-ChildItem -Path C:\Reference\Afile.txt, C:\Reference\Images\Bfile.txt |
  Compress-Archive -DestinationPath C:\Archives\PipelineFiles.zip
```

<span data-ttu-id="08e50-160">`Get-ChildItem` usa o parâmetro **path** para especificar dois arquivos de diretórios diferentes.</span><span class="sxs-lookup"><span data-stu-id="08e50-160">`Get-ChildItem` uses the **Path** parameter to specify two files from different directories.</span></span> <span data-ttu-id="08e50-161">Cada arquivo é representado por um objeto **FileInfo** e é enviado ao pipeline para `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="08e50-161">Each file is represented by a **FileInfo** object and is sent down the pipeline to `Compress-Archive`.</span></span>
<span data-ttu-id="08e50-162">Os dois arquivos especificados são arquivados no `PipelineFiles.zip` .</span><span class="sxs-lookup"><span data-stu-id="08e50-162">The two specified files are archived in `PipelineFiles.zip`.</span></span>

### <span data-ttu-id="08e50-163">Exemplo 7: usar o pipeline para arquivar um diretório</span><span class="sxs-lookup"><span data-stu-id="08e50-163">Example 7: Use the pipeline to archive a directory</span></span>

<span data-ttu-id="08e50-164">Este exemplo envia um diretório para baixo do pipeline para criar um arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-164">This example sends a directory down the pipeline to create an archive.</span></span> <span data-ttu-id="08e50-165">Os arquivos são enviados como objetos **FileInfo** e diretórios como objetos **DirectoryInfo** .</span><span class="sxs-lookup"><span data-stu-id="08e50-165">Files are sent as **FileInfo** objects and directories as **DirectoryInfo** objects.</span></span> <span data-ttu-id="08e50-166">A estrutura de diretório do arquivo morto não inclui o diretório raiz, mas seus arquivos e subdiretórios estão incluídos no arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-166">The archive's directory structure doesn't include the root directory, but its files and subdirectories are included in the archive.</span></span>

```powershell
Get-ChildItem -Path C:\LogFiles | Compress-Archive -DestinationPath C:\Archives\PipelineDir.zip
```

<span data-ttu-id="08e50-167">`Get-ChildItem` usa o parâmetro **path** para especificar o `C:\LogFiles` diretório raiz.</span><span class="sxs-lookup"><span data-stu-id="08e50-167">`Get-ChildItem` uses the **Path** parameter to specify the `C:\LogFiles` root directory.</span></span> <span data-ttu-id="08e50-168">Cada objeto **FileInfo** e **DirectoryInfo** é enviado pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="08e50-168">Each **FileInfo** and **DirectoryInfo** object is sent down the pipeline.</span></span>

<span data-ttu-id="08e50-169">`Compress-Archive` Adiciona cada objeto ao `PipelineDir.zip` arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-169">`Compress-Archive` adds each object to the `PipelineDir.zip` archive.</span></span> <span data-ttu-id="08e50-170">O parâmetro **path** não foi especificado porque os objetos de pipeline são recebidos na posição de parâmetro 0.</span><span class="sxs-lookup"><span data-stu-id="08e50-170">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

### <span data-ttu-id="08e50-171">Exemplo 8: como a recursão pode afetar os arquivos mortos</span><span class="sxs-lookup"><span data-stu-id="08e50-171">Example 8: How recursion can affect archives</span></span>

<span data-ttu-id="08e50-172">Este exemplo mostra como a recursão pode duplicar arquivos em seu arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-172">This example shows how recursion can duplicate files in your archive.</span></span> <span data-ttu-id="08e50-173">Por exemplo, se você usar `Get-ChildItem` com o parâmetro **recurse** .</span><span class="sxs-lookup"><span data-stu-id="08e50-173">For example, if you use `Get-ChildItem` with the **Recurse** parameter.</span></span> <span data-ttu-id="08e50-174">Como processos de recursão, cada objeto **FileInfo** e **DirectoryInfo** é enviado pelo pipeline e adicionado ao arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-174">As recursion processes, each **FileInfo** and **DirectoryInfo** object is sent down the pipeline and added to the archive.</span></span>

```powershell
Get-ChildItem -Path C:\TestLog -Recurse |
  Compress-Archive -DestinationPath C:\Archives\PipelineRecurse.zip
```

<span data-ttu-id="08e50-175">O `C:\TestLog` diretório não contém nenhum arquivo.</span><span class="sxs-lookup"><span data-stu-id="08e50-175">The `C:\TestLog` directory doesn't contain any files.</span></span> <span data-ttu-id="08e50-176">Ele contém um subdiretório chamado `testsub` que contém o `testlog.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="08e50-176">It does contain a subdirectory named `testsub` that contains the `testlog.txt` file.</span></span>

<span data-ttu-id="08e50-177">`Get-ChildItem` usa o parâmetro **path** para especificar o diretório raiz, `C:\TestLog` .</span><span class="sxs-lookup"><span data-stu-id="08e50-177">`Get-ChildItem` uses the **Path** parameter to specify the root directory, `C:\TestLog`.</span></span> <span data-ttu-id="08e50-178">O parâmetro **recurse** processa os arquivos e diretórios.</span><span class="sxs-lookup"><span data-stu-id="08e50-178">The **Recurse** parameter processes the files and directories.</span></span> <span data-ttu-id="08e50-179">Um objeto **DirectoryInfo** é criado para `testsub` e um objeto **FileInfo** `testlog.txt` .</span><span class="sxs-lookup"><span data-stu-id="08e50-179">A **DirectoryInfo** object is created for `testsub` and a **FileInfo** object `testlog.txt`.</span></span>

<span data-ttu-id="08e50-180">Cada objeto é enviado ao pipeline para `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="08e50-180">Each object is sent down the pipeline to `Compress-Archive`.</span></span> <span data-ttu-id="08e50-181">O **DestinationPath** especifica o local para o arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-181">The **DestinationPath** specifies the location for the archive file.</span></span> <span data-ttu-id="08e50-182">O parâmetro **path** não foi especificado porque os objetos de pipeline são recebidos na posição de parâmetro 0.</span><span class="sxs-lookup"><span data-stu-id="08e50-182">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

<span data-ttu-id="08e50-183">O resumo a seguir descreve o `PipelineRecurse.zip` conteúdo do arquivo morto que contém um arquivo duplicado:</span><span class="sxs-lookup"><span data-stu-id="08e50-183">The following summary describes the `PipelineRecurse.zip` archive's contents that contains a duplicate file:</span></span>

- <span data-ttu-id="08e50-184">O objeto **DirectoryInfo** cria o `testsub` diretório e contém o `testlog.txt` arquivo, que reflete a estrutura do diretório original.</span><span class="sxs-lookup"><span data-stu-id="08e50-184">The **DirectoryInfo** object creates the `testsub` directory and contains the `testlog.txt` file, which reflects the original directory structure.</span></span>
- <span data-ttu-id="08e50-185">O objeto **FileInfo** cria uma duplicata `testlog.txt` na raiz do arquivo.</span><span class="sxs-lookup"><span data-stu-id="08e50-185">The **FileInfo** object creates a duplicate `testlog.txt` in the archive's root.</span></span> <span data-ttu-id="08e50-186">O arquivo duplicado é criado porque a recursão enviou um objeto de arquivo para `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="08e50-186">The duplicate file is created because recursion sent a file object to `Compress-Archive`.</span></span> <span data-ttu-id="08e50-187">Esse comportamento é esperado porque cada objeto enviado pelo pipeline é adicionado ao arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-187">This behavior is expected because each object sent down the pipeline is added to the archive.</span></span>

### <span data-ttu-id="08e50-188">Exemplo 9: atualizar um arquivo morto existente</span><span class="sxs-lookup"><span data-stu-id="08e50-188">Example 9: Update an existing archive file</span></span>

<span data-ttu-id="08e50-189">Este exemplo atualiza um arquivo morto existente, `Draft.Zip` , no `C:\Archives` diretório.</span><span class="sxs-lookup"><span data-stu-id="08e50-189">This example updates an existing archive file, `Draft.Zip`, in the `C:\Archives` directory.</span></span> <span data-ttu-id="08e50-190">Neste exemplo, o arquivo morto existente contém o diretório raiz e seus arquivos e subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="08e50-190">In this example, the existing archive file contains the root directory, and its files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference -Update -DestinationPath C:\Archives\Draft.Zip
```

<span data-ttu-id="08e50-191">O comando é atualizado `Draft.Zip` com versões mais recentes de arquivos existentes no `C:\Reference` diretório e em seus subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="08e50-191">The command updates `Draft.Zip` with newer versions of existing files in the `C:\Reference` directory and its subdirectories.</span></span> <span data-ttu-id="08e50-192">E novos arquivos que foram adicionados ao `C:\Reference` ou seus subdiretórios estão incluídos no `Draft.Zip` arquivo atualizado.</span><span class="sxs-lookup"><span data-stu-id="08e50-192">And, new files that were added to `C:\Reference` or its subdirectories are included in the updated `Draft.Zip` archive.</span></span>

## <span data-ttu-id="08e50-193">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="08e50-193">PARAMETERS</span></span>

### <span data-ttu-id="08e50-194">-CompressionLevel</span><span class="sxs-lookup"><span data-stu-id="08e50-194">-CompressionLevel</span></span>

<span data-ttu-id="08e50-195">Especifica a quantidade de compactação a ser aplicada quando você estiver criando o arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-195">Specifies how much compression to apply when you're creating the archive file.</span></span> <span data-ttu-id="08e50-196">A compactação mais rápida requer menos tempo para criar o arquivo, mas pode resultar em tamanhos de arquivo maiores.</span><span class="sxs-lookup"><span data-stu-id="08e50-196">Faster compression requires less time to create the file, but can result in larger file sizes.</span></span>

<span data-ttu-id="08e50-197">Se esse parâmetro não for especificado, o comando usará o valor padrão, **ideal**.</span><span class="sxs-lookup"><span data-stu-id="08e50-197">If this parameter isn't specified, the command uses the default value, **Optimal**.</span></span>

<span data-ttu-id="08e50-198">Estes são os valores aceitáveis para esse parâmetro:</span><span class="sxs-lookup"><span data-stu-id="08e50-198">The following are the acceptable values for this parameter:</span></span>

- <span data-ttu-id="08e50-199">**Mais rápido**.</span><span class="sxs-lookup"><span data-stu-id="08e50-199">**Fastest**.</span></span> <span data-ttu-id="08e50-200">Use o método de compactação mais rápido disponível para reduzir o tempo de processamento.</span><span class="sxs-lookup"><span data-stu-id="08e50-200">Use the fastest compression method available to reduce processing time.</span></span> <span data-ttu-id="08e50-201">A compactação mais rápida pode resultar em tamanhos de arquivo maiores.</span><span class="sxs-lookup"><span data-stu-id="08e50-201">Faster compression can result in larger file sizes.</span></span>
- <span data-ttu-id="08e50-202">**NoCompression**.</span><span class="sxs-lookup"><span data-stu-id="08e50-202">**NoCompression**.</span></span> <span data-ttu-id="08e50-203">Não compacta os arquivos de origem.</span><span class="sxs-lookup"><span data-stu-id="08e50-203">Doesn't compress the source files.</span></span>
- <span data-ttu-id="08e50-204">**Ideal**.</span><span class="sxs-lookup"><span data-stu-id="08e50-204">**Optimal**.</span></span> <span data-ttu-id="08e50-205">O tempo de processamento depende do tamanho do arquivo.</span><span class="sxs-lookup"><span data-stu-id="08e50-205">Processing time is dependent on file size.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Optimal, NoCompression, Fastest

Required: False
Position: Named
Default value: Optimal
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08e50-206">-Confirm</span><span class="sxs-lookup"><span data-stu-id="08e50-206">-Confirm</span></span>

<span data-ttu-id="08e50-207">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="08e50-207">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="08e50-208">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="08e50-208">-DestinationPath</span></span>

<span data-ttu-id="08e50-209">Esse parâmetro é necessário e especifica o caminho para o arquivo de saída de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="08e50-209">This parameter is required and specifies the path to the archive output file.</span></span> <span data-ttu-id="08e50-210">O **DestinationPath** deve incluir o nome do arquivo compactado e o caminho absoluto ou relativo para o arquivo compactado.</span><span class="sxs-lookup"><span data-stu-id="08e50-210">The **DestinationPath** should include the name of the zipped file, and either the absolute or relative path to the zipped file.</span></span>

<span data-ttu-id="08e50-211">Se o nome do arquivo em **DestinationPath** não tiver uma `.zip` extensão de nome de arquivo, o cmdlet adicionará a `.zip` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="08e50-211">If the file name in **DestinationPath** doesn't have a `.zip` file name extension, the cmdlet adds the `.zip` file name extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08e50-212">-Force</span><span class="sxs-lookup"><span data-stu-id="08e50-212">-Force</span></span>

<span data-ttu-id="08e50-213">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="08e50-213">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithForce, LiteralPathWithForce
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08e50-214">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="08e50-214">-LiteralPath</span></span>

<span data-ttu-id="08e50-215">Especifica o caminho ou caminhos para os arquivos que você deseja adicionar ao arquivo compactado de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="08e50-215">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="08e50-216">Ao contrário do parâmetro **path** , o valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="08e50-216">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="08e50-217">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="08e50-217">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="08e50-218">Se o caminho incluir caracteres de escape, coloque cada caractere de escape entre aspas simples, para instruir o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="08e50-218">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>
<span data-ttu-id="08e50-219">Para especificar vários caminhos e incluir arquivos em vários locais em seu arquivo compactado de saída, use vírgulas para separar os caminhos.</span><span class="sxs-lookup"><span data-stu-id="08e50-219">To specify multiple paths, and include files in multiple locations in your output zipped file, use commas to separate the paths.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPathWithUpdate, LiteralPathWithForce, LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="08e50-220">-PassThru</span><span class="sxs-lookup"><span data-stu-id="08e50-220">-PassThru</span></span>

<span data-ttu-id="08e50-221">Faz com que o cmdlet gere um objeto de arquivo que representa o arquivo morto criado.</span><span class="sxs-lookup"><span data-stu-id="08e50-221">Causes the cmdlet to output a file object representing the archive file created.</span></span>

<span data-ttu-id="08e50-222">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="08e50-222">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="08e50-223">-Path</span><span class="sxs-lookup"><span data-stu-id="08e50-223">-Path</span></span>

<span data-ttu-id="08e50-224">Especifica o caminho ou caminhos para os arquivos que você deseja adicionar ao arquivo compactado de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="08e50-224">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="08e50-225">Para especificar vários caminhos e incluir arquivos em vários locais, use vírgulas para separar os caminhos.</span><span class="sxs-lookup"><span data-stu-id="08e50-225">To specify multiple paths, and include files in multiple locations, use commas to separate the paths.</span></span>

<span data-ttu-id="08e50-226">Esse parâmetro aceita caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="08e50-226">This parameter accepts wildcard characters.</span></span> <span data-ttu-id="08e50-227">Os caracteres curinga permitem que você adicione todos os arquivos em um diretório ao arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-227">Wildcard characters allow you to add all files in a directory to your archive file.</span></span>

<span data-ttu-id="08e50-228">O uso de caracteres curinga com um diretório raiz afeta o conteúdo do arquivo:</span><span class="sxs-lookup"><span data-stu-id="08e50-228">Using wildcards with a root directory affects the archive's contents:</span></span>

- <span data-ttu-id="08e50-229">Para criar um arquivo que **inclui** o diretório raiz e todos os seus arquivos e subdiretórios, especifique o diretório raiz no **caminho** sem curingas.</span><span class="sxs-lookup"><span data-stu-id="08e50-229">To create an archive that **includes** the root directory, and all its files and subdirectories, specify the root directory in the **Path** without wildcards.</span></span> <span data-ttu-id="08e50-230">Por exemplo: `-Path C:\Reference`</span><span class="sxs-lookup"><span data-stu-id="08e50-230">For example: `-Path C:\Reference`</span></span>
- <span data-ttu-id="08e50-231">Para criar um arquivo que **exclua** o diretório raiz, mas zips todos os seus arquivos e subdiretórios, use o curinga asterisco ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="08e50-231">To create an archive that **excludes** the root directory, but zips all its files and subdirectories, use the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="08e50-232">Por exemplo: `-Path C:\Reference\*`</span><span class="sxs-lookup"><span data-stu-id="08e50-232">For example: `-Path C:\Reference\*`</span></span>
- <span data-ttu-id="08e50-233">Para criar um arquivo morto que só zips os arquivos no diretório raiz, use o curinga **Star-dot-Star** ( `*.*` ).</span><span class="sxs-lookup"><span data-stu-id="08e50-233">To create an archive that only zips the files in the root directory, use the **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="08e50-234">Os subdiretórios da raiz não estão incluídos no arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-234">Subdirectories of the root aren't included in the archive.</span></span> <span data-ttu-id="08e50-235">Por exemplo: `-Path C:\Reference\*.*`</span><span class="sxs-lookup"><span data-stu-id="08e50-235">For example: `-Path C:\Reference\*.*`</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path, PathWithUpdate, PathWithForce
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="08e50-236">-Atualização</span><span class="sxs-lookup"><span data-stu-id="08e50-236">-Update</span></span>

<span data-ttu-id="08e50-237">Atualiza o arquivo especificado substituindo versões de arquivo mais antigas no arquivo morto por versões de arquivo mais recentes que têm os mesmos nomes.</span><span class="sxs-lookup"><span data-stu-id="08e50-237">Updates the specified archive by replacing older file versions in the archive with newer file versions that have the same names.</span></span> <span data-ttu-id="08e50-238">Você também pode adicionar esse parâmetro para adicionar arquivos a um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="08e50-238">You can also add this parameter to add files to an existing archive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithUpdate, LiteralPathWithUpdate
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08e50-239">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="08e50-239">-WhatIf</span></span>

<span data-ttu-id="08e50-240">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="08e50-240">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="08e50-241">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="08e50-241">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="08e50-242">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="08e50-242">CommonParameters</span></span>

<span data-ttu-id="08e50-243">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="08e50-243">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="08e50-244">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="08e50-244">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="08e50-245">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="08e50-245">INPUTS</span></span>

### <span data-ttu-id="08e50-246">System.String</span><span class="sxs-lookup"><span data-stu-id="08e50-246">System.String</span></span>

<span data-ttu-id="08e50-247">É possível canalizar uma cadeia de caracteres que contém um caminho para um ou mais arquivos.</span><span class="sxs-lookup"><span data-stu-id="08e50-247">You can pipe a string that contains a path to one or more files.</span></span>

## <span data-ttu-id="08e50-248">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="08e50-248">OUTPUTS</span></span>

### <span data-ttu-id="08e50-249">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="08e50-249">System.IO.FileInfo</span></span>

<span data-ttu-id="08e50-250">O cmdlet retorna apenas um objeto **FileInfo** quando você usa o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="08e50-250">The cmdlet only returns a **FileInfo** object when you use the **PassThru** parameter.</span></span>

## <span data-ttu-id="08e50-251">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="08e50-251">NOTES</span></span>

<span data-ttu-id="08e50-252">Usar recursão e enviar objetos por meio do pipeline pode duplicar arquivos em seu arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-252">Using recursion and sending objects down the pipeline can duplicate files in your archive.</span></span> <span data-ttu-id="08e50-253">Por exemplo, se você usar `Get-ChildItem` com o parâmetro **recurse** , cada objeto **FileInfo** e **DirectoryInfo** enviado pelo pipeline será adicionado ao arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-253">For example, if you use `Get-ChildItem` with the **Recurse** parameter, each **FileInfo** and **DirectoryInfo** object that's sent down the pipeline is added to the archive.</span></span>

<span data-ttu-id="08e50-254">A [especificação do arquivo zip](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) não especifica uma maneira padrão de codificar nomes de arquivos que contenham caracteres não ASCII.</span><span class="sxs-lookup"><span data-stu-id="08e50-254">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="08e50-255">O `Compress-Archive` cmdlet usa a codificação UTF-8.</span><span class="sxs-lookup"><span data-stu-id="08e50-255">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="08e50-256">Outras ferramentas de arquivo ZIP podem usar um esquema de codificação diferente.</span><span class="sxs-lookup"><span data-stu-id="08e50-256">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="08e50-257">Ao extrair arquivos com nomes de arquivo não armazenados usando a codificação UTF-8, `Expand-Archive` o usa o valor bruto encontrado no arquivamento.</span><span class="sxs-lookup"><span data-stu-id="08e50-257">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="08e50-258">Isso pode resultar em um nome de arquivo diferente do nome de arquivo de origem armazenado no arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="08e50-258">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="08e50-259">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="08e50-259">RELATED LINKS</span></span>

[<span data-ttu-id="08e50-260">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="08e50-260">Expand-Archive</span></span>](Expand-Archive.md)

[<span data-ttu-id="08e50-261">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="08e50-261">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

