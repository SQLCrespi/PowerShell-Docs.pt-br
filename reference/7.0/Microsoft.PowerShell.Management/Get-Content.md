---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-content?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Content
ms.openlocfilehash: 48f15f9d7018c2e58584bff80f81132fe08fea1e
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692740"
---
# <span data-ttu-id="314cf-102">Get-Content</span><span class="sxs-lookup"><span data-stu-id="314cf-102">Get-Content</span></span>

## <span data-ttu-id="314cf-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="314cf-103">SYNOPSIS</span></span>
<span data-ttu-id="314cf-104">Obtém o conteúdo do item no local especificado.</span><span class="sxs-lookup"><span data-stu-id="314cf-104">Gets the content of the item at the specified location.</span></span>

## <span data-ttu-id="314cf-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="314cf-105">SYNTAX</span></span>

### <span data-ttu-id="314cf-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="314cf-106">Path (Default)</span></span>

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] [-Path] <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-Delimiter <String>] [-Wait] [-Raw] [-Encoding <Encoding>] [-AsByteStream] [-Stream <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="314cf-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="314cf-107">LiteralPath</span></span>

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] -LiteralPath <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-Delimiter <String>] [-Wait] [-Raw] [-Encoding <Encoding>] [-AsByteStream] [-Stream <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="314cf-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="314cf-108">DESCRIPTION</span></span>

<span data-ttu-id="314cf-109">O `Get-Content` cmdlet obtém o conteúdo do item no local especificado pelo caminho, como o texto em um arquivo ou o conteúdo de uma função.</span><span class="sxs-lookup"><span data-stu-id="314cf-109">The `Get-Content` cmdlet gets the content of the item at the location specified by the path, such as the text in a file or the content of a function.</span></span> <span data-ttu-id="314cf-110">Para arquivos, o conteúdo é lido uma linha por vez e retorna uma coleção de objetos, cada um representando uma linha de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="314cf-110">For files, the content is read one line at a time and returns a collection of objects, each of which represents a line of content.</span></span>

<span data-ttu-id="314cf-111">A partir do PowerShell 3,0, `Get-Content` também pode obter um número especificado de linhas do início ou do fim de um item.</span><span class="sxs-lookup"><span data-stu-id="314cf-111">Beginning in PowerShell 3.0, `Get-Content` can also get a specified number of lines from the beginning or end of an item.</span></span>

## <span data-ttu-id="314cf-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="314cf-112">EXAMPLES</span></span>

### <span data-ttu-id="314cf-113">Exemplo 1: obter o conteúdo de um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="314cf-113">Example 1: Get the content of a text file</span></span>

<span data-ttu-id="314cf-114">Este exemplo obtém o conteúdo de um arquivo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="314cf-114">This example gets the content of a file in the current directory.</span></span> <span data-ttu-id="314cf-115">O `LineNumbers.txt` arquivo contém 100 linhas no formato, **é a linha X** e é usado em vários exemplos.</span><span class="sxs-lookup"><span data-stu-id="314cf-115">The `LineNumbers.txt` file contains 100 lines in the format, **This is Line X** and is used in several examples.</span></span>

```powershell
1..100 | ForEach-Object { Add-Content -Path .\LineNumbers.txt -Value "This is line $_." }
Get-Content -Path .\LineNumbers.txt
```

```Output
This is Line 1
This is Line 2
...
This is line 99.
This is line 100.
```

<span data-ttu-id="314cf-116">Os valores de matriz 1-100 são enviados pelo pipeline para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="314cf-116">The array values 1-100 are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="314cf-117">`ForEach-Object` usa um bloco de script com o `Add-Content` cmdlet para criar o `LineNumbers.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="314cf-117">`ForEach-Object` uses a script block with the `Add-Content` cmdlet to create the `LineNumbers.txt` file.</span></span> <span data-ttu-id="314cf-118">A variável `$_` representa os valores de matriz conforme cada objeto é enviado ao pipeline.</span><span class="sxs-lookup"><span data-stu-id="314cf-118">The variable `$_` represents the array values as each object is sent down the pipeline.</span></span> <span data-ttu-id="314cf-119">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o `LineNumbers.txt` arquivo e exibe o conteúdo no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="314cf-119">The `Get-Content` cmdlet uses the **Path** parameter to specify the `LineNumbers.txt` file and displays the content in the PowerShell console.</span></span>

### <span data-ttu-id="314cf-120">Exemplo 2: limitar o número de linhas Get-Content retorna</span><span class="sxs-lookup"><span data-stu-id="314cf-120">Example 2: Limit the number of lines Get-Content returns</span></span>

<span data-ttu-id="314cf-121">Esse comando obtém as primeiras cinco linhas de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="314cf-121">This command gets the first five lines of a file.</span></span> <span data-ttu-id="314cf-122">O parâmetro **TotalCount** é usado para obter as primeiras cinco linhas de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="314cf-122">The **TotalCount** parameter is used to gets the first five lines of content.</span></span> <span data-ttu-id="314cf-123">Este exemplo usa o `LineNumbers.txt` arquivo que foi criado no exemplo 1.</span><span class="sxs-lookup"><span data-stu-id="314cf-123">This example uses the `LineNumbers.txt` file that was created in Example 1.</span></span>

```powershell
Get-Content -Path .\LineNumbers.txt -TotalCount 5
```

```Output
This is Line 1
This is Line 2
This is Line 3
This is Line 4
This is Line 5
```

### <span data-ttu-id="314cf-124">Exemplo 3: obter uma linha de conteúdo específica de um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="314cf-124">Example 3: Get a specific line of content from a text file</span></span>

<span data-ttu-id="314cf-125">Esse comando obtém um número específico de linhas de um arquivo e, em seguida, exibe apenas a última linha desse conteúdo.</span><span class="sxs-lookup"><span data-stu-id="314cf-125">This command gets a specific number of lines from a file and then displays only the last line of that content.</span></span> <span data-ttu-id="314cf-126">O parâmetro **TotalCount** Obtém as 25 primeiras linhas de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="314cf-126">The **TotalCount** parameter gets the first 25 lines of content.</span></span> <span data-ttu-id="314cf-127">Este exemplo usa o `LineNumbers.txt` arquivo que foi criado no exemplo 1.</span><span class="sxs-lookup"><span data-stu-id="314cf-127">This example uses the `LineNumbers.txt` file that was created in Example 1.</span></span>

```powershell
(Get-Content -Path .\LineNumbers.txt -TotalCount 25)[-1]
```

```Output
This is Line 25
```

<span data-ttu-id="314cf-128">O `Get-Content` comando é encapsulado entre parênteses para que o comando seja concluído antes de ir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="314cf-128">The `Get-Content` command is wrapped in parentheses so that the command completes before going to the next step.</span></span> <span data-ttu-id="314cf-129">`Get-Content`Retorna uma matriz de linhas, isso permite que você adicione a notação de índice após o parêntese para recuperar um número de linha específico.</span><span class="sxs-lookup"><span data-stu-id="314cf-129">`Get-Content`returns an array of lines, this allows you to add the index notation after the parenthesis to retrieve a specific line number.</span></span> <span data-ttu-id="314cf-130">Nesse caso, o `[-1]` índice especifica o último índice na matriz retornada de 25 linhas recuperadas.</span><span class="sxs-lookup"><span data-stu-id="314cf-130">In this case, the `[-1]` index specifies the last index in the returned array of 25 retrieved lines.</span></span>

### <span data-ttu-id="314cf-131">Exemplo 4: obter a última linha de um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="314cf-131">Example 4: Get the last line of a text file</span></span>

<span data-ttu-id="314cf-132">Esse comando obtém a primeira linha e a última linha de conteúdo de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="314cf-132">This command gets the first line and last line of content from a file.</span></span> <span data-ttu-id="314cf-133">Este exemplo usa o `LineNumbers.txt` arquivo que foi criado no exemplo 1.</span><span class="sxs-lookup"><span data-stu-id="314cf-133">This example uses the `LineNumbers.txt` file that was created in Example 1.</span></span>

```powershell
Get-Item -Path .\LineNumbers.txt | Get-Content -Tail 1
```

```Output
This is Line 100
```

<span data-ttu-id="314cf-134">Este exemplo usa o `Get-Item` cmdlet para demonstrar que você pode canalizar arquivos para o `Get-Content` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="314cf-134">This example uses the `Get-Item` cmdlet to demonstrate that you can pipe files into the `Get-Content` parameter.</span></span> <span data-ttu-id="314cf-135">O parâmetro **tail** Obtém a última linha do arquivo.</span><span class="sxs-lookup"><span data-stu-id="314cf-135">The **Tail** parameter gets the last line of the file.</span></span> <span data-ttu-id="314cf-136">Esse método é mais rápido do que recuperar todas as linhas e usar a `[-1]` notação de índice.</span><span class="sxs-lookup"><span data-stu-id="314cf-136">This method is faster than retrieving all of the lines and using the `[-1]` index notation.</span></span>

### <span data-ttu-id="314cf-137">Exemplo 5: obter o conteúdo de um fluxo de dados alternativo</span><span class="sxs-lookup"><span data-stu-id="314cf-137">Example 5: Get the content of an alternate data stream</span></span>

<span data-ttu-id="314cf-138">Este exemplo descreve como usar o parâmetro **Stream** para obter o conteúdo de um fluxo de dados alternativo para arquivos armazenados em um volume NTFS do Windows.</span><span class="sxs-lookup"><span data-stu-id="314cf-138">This example describes how to use the **Stream** parameter to get the content of an alternate data stream for files stored on a Windows NTFS volume.</span></span> <span data-ttu-id="314cf-139">Neste exemplo, o `Set-Content` cmdlet é usado para criar conteúdo de exemplo em um arquivo chamado `Stream.txt` .</span><span class="sxs-lookup"><span data-stu-id="314cf-139">In this example, the `Set-Content` cmdlet is used to create sample content in a file named `Stream.txt`.</span></span>

```powershell
Set-Content -Path .\Stream.txt -Value 'This is the content of the Stream.txt file'
# Specify a wildcard to the Stream parameter to display all streams of the recently created file.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44
```

```powershell
# Retrieve the content of the primary, or $DATA stream.
Get-Content -Path .\Stream.txt -Stream $DATA
```

```Output
This is the content of the Stream.txt file
```

```powershell
# Use the Stream parameter of Add-Content to create a new Stream containing sample content.
Add-Content -Path .\Stream.txt -Stream NewStream -Value 'Added a stream named NewStream to Stream.txt'
# Use Get-Item to verify the stream was created.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44

PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt:NewStream
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt:NewStream
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : NewStream
Length        : 46
```

```powershell
# Retrieve the content of your newly created Stream.
Get-Content -Path .\Stream.txt -Stream NewStream
```

```Output
Added a stream named NewStream to Stream.txt
```

<span data-ttu-id="314cf-140">O parâmetro **Stream** é um parâmetro dinâmico do [provedor FileSystem](../microsoft.powershell.core/about/about_filesystem_provider.md#stream-systemstring).</span><span class="sxs-lookup"><span data-stu-id="314cf-140">The **Stream** parameter is a dynamic parameter of the [FileSystem provider](../microsoft.powershell.core/about/about_filesystem_provider.md#stream-systemstring).</span></span>
<span data-ttu-id="314cf-141">Por padrão `Get-Content` , o só recupera dados do padrão ou do `:$DATA` fluxo.</span><span class="sxs-lookup"><span data-stu-id="314cf-141">By default `Get-Content` only retrieves data from the default, or `:$DATA` stream.</span></span> <span data-ttu-id="314cf-142">Os **fluxos** podem ser usados para armazenar dados ocultos, como atributos, configurações de segurança ou outros dados.</span><span class="sxs-lookup"><span data-stu-id="314cf-142">**Streams** can be used to store hidden data such as attributes, security settings, or other data.</span></span> <span data-ttu-id="314cf-143">Eles também podem ser armazenados em diretórios sem serem itens filho.</span><span class="sxs-lookup"><span data-stu-id="314cf-143">They can also be stored on directories without being child items.</span></span>

### <span data-ttu-id="314cf-144">Exemplo 6: obter conteúdo bruto</span><span class="sxs-lookup"><span data-stu-id="314cf-144">Example 6: Get raw content</span></span>

<span data-ttu-id="314cf-145">Os comandos neste exemplo obtêm o conteúdo de um arquivo como uma cadeia de caracteres, em vez de uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="314cf-145">The commands in this example get the contents of a file as one string, instead of an array of strings.</span></span> <span data-ttu-id="314cf-146">Por padrão, sem o parâmetro dinâmico **bruto** , o conteúdo é retornado como uma matriz de cadeias de caracteres delimitadas por nova linha.</span><span class="sxs-lookup"><span data-stu-id="314cf-146">By default, without the **Raw** dynamic parameter, content is returned as an array of newline-delimited strings.</span></span> <span data-ttu-id="314cf-147">Este exemplo usa o `LineNumbers.txt` arquivo que foi criado no exemplo</span><span class="sxs-lookup"><span data-stu-id="314cf-147">This example uses the `LineNumbers.txt` file that was created in Example</span></span>
1.

```powershell
$raw = Get-Content -Path .\LineNumbers.txt -Raw
$lines = Get-Content -Path .\LineNumbers.txt
Write-Host "Raw contains $($raw.Count) lines."
Write-Host "Lines contains $($lines.Count) lines."
```

```Output
Raw contains 1 lines.
Lines contains 100 lines.
```

### <span data-ttu-id="314cf-148">Exemplo 7: usar filtros com Get-Content</span><span class="sxs-lookup"><span data-stu-id="314cf-148">Example 7: Use Filters with Get-Content</span></span>

<span data-ttu-id="314cf-149">Você pode especificar um filtro para o `Get-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="314cf-149">You can specify a filter to the `Get-Content` cmdlet.</span></span> <span data-ttu-id="314cf-150">Ao usar filtros para qualificar o parâmetro de **caminho** , você precisa incluir um asterisco à direita ( `*` ) para indicar o conteúdo do caminho.</span><span class="sxs-lookup"><span data-stu-id="314cf-150">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="314cf-151">O comando a seguir obtém o conteúdo de todos os `*.log` arquivos no `C:\Temp` diretório.</span><span class="sxs-lookup"><span data-stu-id="314cf-151">The following command gets the content of all `*.log` files in the `C:\Temp` directory.</span></span>

```powershell
Get-Content -Path C:\Temp\* -Filter *.log
```

### <span data-ttu-id="314cf-152">Exemplo 8: obter o conteúdo do arquivo como uma matriz de bytes</span><span class="sxs-lookup"><span data-stu-id="314cf-152">Example 8: Get file contents as a byte array</span></span>

<span data-ttu-id="314cf-153">Este exemplo demonstra como obter o conteúdo de um arquivo como um `[byte[]]` único objeto.</span><span class="sxs-lookup"><span data-stu-id="314cf-153">This example demonstrates how to get the contents of a file as a `[byte[]]` as a single object.</span></span>

```powershell
$byteArray = Get-Content -Path C:\temp\test.txt -AsByteStream -Raw
Get-Member -InputObject $bytearray
```

```Output
   TypeName: System.Byte[]

Name           MemberType            Definition
----           ----------            ----------
Count          AliasProperty         Count = Length
Add            Method                int IList.Add(System.Object value)
```

<span data-ttu-id="314cf-154">O primeiro comando usa o parâmetro **AsByteStream** para obter o fluxo de bytes do arquivo.</span><span class="sxs-lookup"><span data-stu-id="314cf-154">The first command uses the **AsByteStream** parameter to get the stream of bytes from the file.</span></span>
<span data-ttu-id="314cf-155">O parâmetro **RAW** garante que os bytes sejam retornados como um `[System.Byte[]]` .</span><span class="sxs-lookup"><span data-stu-id="314cf-155">The **Raw** parameter ensures that the bytes are returned as a `[System.Byte[]]`.</span></span> <span data-ttu-id="314cf-156">Se o parâmetro **RAW** estiver ausente, o valor de retorno será um fluxo de bytes, que é interpretado pelo PowerShell como `[System.Object[]]` .</span><span class="sxs-lookup"><span data-stu-id="314cf-156">If the **Raw** parameter was absent, the return value is a stream of bytes, which is interpreted by PowerShell as `[System.Object[]]`.</span></span>

## <span data-ttu-id="314cf-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="314cf-157">PARAMETERS</span></span>

### <span data-ttu-id="314cf-158">-Path</span><span class="sxs-lookup"><span data-stu-id="314cf-158">-Path</span></span>

<span data-ttu-id="314cf-159">Especifica o caminho para um item em que `Get-Content` o Obtém o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="314cf-159">Specifies the path to an item where `Get-Content` gets the content.</span></span> <span data-ttu-id="314cf-160">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="314cf-160">Wildcard characters are permitted.</span></span> <span data-ttu-id="314cf-161">Os caminhos devem ser caminhos para itens, não para contêineres.</span><span class="sxs-lookup"><span data-stu-id="314cf-161">The paths must be paths to items, not to containers.</span></span> <span data-ttu-id="314cf-162">Por exemplo, você deve especificar um caminho para um ou mais arquivos, não um caminho para um diretório.</span><span class="sxs-lookup"><span data-stu-id="314cf-162">For example, you must specify a path to one or more files, not a path to a directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="314cf-163">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="314cf-163">-LiteralPath</span></span>

<span data-ttu-id="314cf-164">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="314cf-164">Specifies a path to one or more locations.</span></span> <span data-ttu-id="314cf-165">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="314cf-165">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="314cf-166">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="314cf-166">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="314cf-167">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="314cf-167">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="314cf-168">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="314cf-168">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="314cf-169">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="314cf-169">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="314cf-170">-ReadCount</span><span class="sxs-lookup"><span data-stu-id="314cf-170">-ReadCount</span></span>

<span data-ttu-id="314cf-171">Especifica quantas linhas de conteúdo são enviadas por meio do pipeline por vez.</span><span class="sxs-lookup"><span data-stu-id="314cf-171">Specifies how many lines of content are sent through the pipeline at a time.</span></span> <span data-ttu-id="314cf-172">O valor padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="314cf-172">The default value is 1.</span></span>
<span data-ttu-id="314cf-173">Um valor de 0 (zero) envia todo o conteúdo de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="314cf-173">A value of 0 (zero) sends all of the content at one time.</span></span>

<span data-ttu-id="314cf-174">Esse parâmetro não altera o conteúdo exibido, mas ele afeta o tempo necessário para exibir o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="314cf-174">This parameter does not change the content displayed, but it does affect the time it takes to display the content.</span></span> <span data-ttu-id="314cf-175">Como o valor de **ReadCount** aumenta, o tempo necessário para retornar a primeira linha também aumenta, mas o tempo total para a operação diminui.</span><span class="sxs-lookup"><span data-stu-id="314cf-175">As the value of **ReadCount** increases, the time it takes to return the first line increases, but the total time for the operation decreases.</span></span> <span data-ttu-id="314cf-176">Isso pode fazer uma diferença perceptível em itens grandes.</span><span class="sxs-lookup"><span data-stu-id="314cf-176">This can make a perceptible difference in large items.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="314cf-177">-TotalCount</span><span class="sxs-lookup"><span data-stu-id="314cf-177">-TotalCount</span></span>

<span data-ttu-id="314cf-178">Especifica o número de linhas desde o início de um arquivo ou outro item.</span><span class="sxs-lookup"><span data-stu-id="314cf-178">Specifies the number of lines from the beginning of a file or other item.</span></span> <span data-ttu-id="314cf-179">O padrão é -1 (todas as linhas).</span><span class="sxs-lookup"><span data-stu-id="314cf-179">The default is -1 (all lines).</span></span>

<span data-ttu-id="314cf-180">Você pode usar o nome do parâmetro **TotalCount** ou seus aliases, **primeiro** ou o **cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="314cf-180">You can use the **TotalCount** parameter name or its aliases, **First** or **Head**.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: First, Head

Required: False
Position: Named
Default value: -1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="314cf-181">-Parte final</span><span class="sxs-lookup"><span data-stu-id="314cf-181">-Tail</span></span>

<span data-ttu-id="314cf-182">Especifica o número de linhas do final de um arquivo ou outro item.</span><span class="sxs-lookup"><span data-stu-id="314cf-182">Specifies the number of lines from the end of a file or other item.</span></span> <span data-ttu-id="314cf-183">Você pode usar o nome do parâmetro de **cauda** ou seu alias, **por fim**.</span><span class="sxs-lookup"><span data-stu-id="314cf-183">You can use the **Tail** parameter name or its alias, **Last**.</span></span> <span data-ttu-id="314cf-184">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="314cf-184">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Last

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="314cf-185">-Filter</span><span class="sxs-lookup"><span data-stu-id="314cf-185">-Filter</span></span>

<span data-ttu-id="314cf-186">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="314cf-186">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="314cf-187">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="314cf-187">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="314cf-188">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="314cf-188">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="314cf-189">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="314cf-189">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="314cf-190">-Incluir</span><span class="sxs-lookup"><span data-stu-id="314cf-190">-Include</span></span>

<span data-ttu-id="314cf-191">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="314cf-191">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="314cf-192">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="314cf-192">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="314cf-193">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="314cf-193">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="314cf-194">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="314cf-194">Wildcard characters are permitted.</span></span> <span data-ttu-id="314cf-195">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="314cf-195">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="314cf-196">-Excluir</span><span class="sxs-lookup"><span data-stu-id="314cf-196">-Exclude</span></span>

<span data-ttu-id="314cf-197">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="314cf-197">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span>
<span data-ttu-id="314cf-198">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="314cf-198">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="314cf-199">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="314cf-199">Enter a path element or pattern, such as `*.txt`.</span></span>
<span data-ttu-id="314cf-200">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="314cf-200">Wildcard characters are permitted.</span></span>

<span data-ttu-id="314cf-201">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="314cf-201">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="314cf-202">-Force</span><span class="sxs-lookup"><span data-stu-id="314cf-202">-Force</span></span>

<span data-ttu-id="314cf-203">**Forçar** irá substituir um atributo somente leitura ou criar diretórios para concluir um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="314cf-203">**Force** will override a read-only attribute or create directories to complete a file path.</span></span> <span data-ttu-id="314cf-204">O parâmetro **Force** não tenta alterar as permissões de arquivo ou substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="314cf-204">The **Force** parameter does not attempt to change file permissions or override security restrictions.</span></span>

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

### <span data-ttu-id="314cf-205">-Credential</span><span class="sxs-lookup"><span data-stu-id="314cf-205">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="314cf-206">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="314cf-206">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="314cf-207">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="314cf-207">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="314cf-208">-Delimitador</span><span class="sxs-lookup"><span data-stu-id="314cf-208">-Delimiter</span></span>

<span data-ttu-id="314cf-209">Especifica o delimitador que `Get-Content` o usa para dividir o arquivo em objetos enquanto ele lê.</span><span class="sxs-lookup"><span data-stu-id="314cf-209">Specifies the delimiter that `Get-Content` uses to divide the file into objects while it reads.</span></span> <span data-ttu-id="314cf-210">O padrão é `\n` , o caractere de fim de linha.</span><span class="sxs-lookup"><span data-stu-id="314cf-210">The default is `\n`, the end-of-line character.</span></span> <span data-ttu-id="314cf-211">Ao ler um arquivo de texto, `Get-Content` retorna uma coleção de objetos String, cada um dos quais termina com um caractere de final de linha.</span><span class="sxs-lookup"><span data-stu-id="314cf-211">When reading a text file, `Get-Content` returns a collection of string objects, each of which ends with an end-of-line character.</span></span> <span data-ttu-id="314cf-212">Quando você insere um delimitador que não existe no arquivo, `Get-Content` o retorna o arquivo inteiro como um único objeto não delimitado.</span><span class="sxs-lookup"><span data-stu-id="314cf-212">When you enter a delimiter that does not exist in the file, `Get-Content` returns the entire file as a single, undelimited object.</span></span>

<span data-ttu-id="314cf-213">Você pode usar esse parâmetro para dividir um arquivo grande em arquivos menores, especificando um separador de arquivo como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="314cf-213">You can use this parameter to split a large file into smaller files by specifying a file separator, as the delimiter.</span></span> <span data-ttu-id="314cf-214">O delimitador é preservado (não descartado) e se torna o último item em cada seção do arquivo.</span><span class="sxs-lookup"><span data-stu-id="314cf-214">The delimiter is preserved (not discarded) and becomes the last item in each file section.</span></span>

<span data-ttu-id="314cf-215">O **delimitador** é um parâmetro dinâmico que o provedor **FileSystem** adiciona ao `Get-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="314cf-215">**Delimiter** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet.</span></span> <span data-ttu-id="314cf-216">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="314cf-216">This parameter works only in file system drives.</span></span>

> [!NOTE]
> <span data-ttu-id="314cf-217">Atualmente, quando o valor do parâmetro **delimitador** é uma cadeia de caracteres vazia, o não `Get-Content` retorna nada.</span><span class="sxs-lookup"><span data-stu-id="314cf-217">Currently, when the value of the **Delimiter** parameter is an empty string, `Get-Content` does not return anything.</span></span> <span data-ttu-id="314cf-218">Este é um problema conhecido.</span><span class="sxs-lookup"><span data-stu-id="314cf-218">This is a known issue.</span></span> <span data-ttu-id="314cf-219">Para forçar a `Get-Content` retornar o arquivo inteiro como uma única cadeia de caracteres não delimitado.</span><span class="sxs-lookup"><span data-stu-id="314cf-219">To force `Get-Content` to return the entire file as a single, undelimited string.</span></span> <span data-ttu-id="314cf-220">Insira um valor que não exista no arquivo.</span><span class="sxs-lookup"><span data-stu-id="314cf-220">Enter a value that does not exist in the file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: End-of-line character
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="314cf-221">-Wait</span><span class="sxs-lookup"><span data-stu-id="314cf-221">-Wait</span></span>

<span data-ttu-id="314cf-222">Mantém o arquivo aberto após a saída de todas as linhas existentes.</span><span class="sxs-lookup"><span data-stu-id="314cf-222">Keeps the file open after all existing lines have been output.</span></span> <span data-ttu-id="314cf-223">Enquanto aguarda, `Get-Content` o verifica o arquivo uma vez por segundo e gera novas linhas, se houver.</span><span class="sxs-lookup"><span data-stu-id="314cf-223">While waiting, `Get-Content` checks the file once each second and outputs new lines if present.</span></span> <span data-ttu-id="314cf-224">Você pode interromper a **espera** pressionando **Ctrl + C**.</span><span class="sxs-lookup"><span data-stu-id="314cf-224">You can interrupt **Wait** by pressing **CTRL+C**.</span></span> <span data-ttu-id="314cf-225">A espera também termina se o arquivo é excluído, caso em que um erro de não finalização é relatado.</span><span class="sxs-lookup"><span data-stu-id="314cf-225">Waiting also ends if the file gets deleted, in which case a non-terminating error is reported.</span></span>

<span data-ttu-id="314cf-226">**Wait** é um parâmetro dinâmico que o provedor FileSystem adiciona ao `Get-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="314cf-226">**Wait** is a dynamic parameter that the FileSystem provider adds to the `Get-Content` cmdlet.</span></span> <span data-ttu-id="314cf-227">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="314cf-227">This parameter works only in file system drives.</span></span> <span data-ttu-id="314cf-228">**Wait** não pode ser combinado com **RAW**.</span><span class="sxs-lookup"><span data-stu-id="314cf-228">**Wait** cannot be combined with **Raw**.</span></span>

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

### <span data-ttu-id="314cf-229">-RAW</span><span class="sxs-lookup"><span data-stu-id="314cf-229">-Raw</span></span>

<span data-ttu-id="314cf-230">Ignora os caracteres de nova linha e retorna todo o conteúdo de um arquivo em uma cadeia de caracteres com as novas linhas preservadas.</span><span class="sxs-lookup"><span data-stu-id="314cf-230">Ignores newline characters and returns the entire contents of a file in one string with the newlines preserved.</span></span> <span data-ttu-id="314cf-231">Por padrão, os caracteres de nova linha em um arquivo são usados como delimitadores para separar a entrada em uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="314cf-231">By default, newline characters in a file are used as delimiters to separate the input into an array of strings.</span></span> <span data-ttu-id="314cf-232">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="314cf-232">This parameter was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="314cf-233">**RAW** é um parâmetro dinâmico que o provedor **FileSystem** adiciona ao `Get-Content` cmdlet. esse parâmetro funciona somente em unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="314cf-233">**Raw** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet This parameter works only in file system drives.</span></span>

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

### <span data-ttu-id="314cf-234">-Codificação</span><span class="sxs-lookup"><span data-stu-id="314cf-234">-Encoding</span></span>

<span data-ttu-id="314cf-235">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="314cf-235">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="314cf-236">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="314cf-236">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="314cf-237">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="314cf-237">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="314cf-238">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="314cf-238">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="314cf-239">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="314cf-239">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="314cf-240">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="314cf-240">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="314cf-241">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="314cf-241">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="314cf-242">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="314cf-242">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="314cf-243">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="314cf-243">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="314cf-244">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="314cf-244">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="314cf-245">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="314cf-245">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="314cf-246">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="314cf-246">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="314cf-247">A codificação é um parâmetro dinâmico que o provedor **FileSystem** adiciona ao `Get-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="314cf-247">Encoding is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet.</span></span>
<span data-ttu-id="314cf-248">Esse parâmetro está disponível somente em unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="314cf-248">This parameter is available only in file system drives.</span></span>

<span data-ttu-id="314cf-249">Ao ler e gravar em arquivos binários, use o parâmetro **AsByteStream** e um valor de 0 para o parâmetro **readCount** .</span><span class="sxs-lookup"><span data-stu-id="314cf-249">When reading from and writing to binary files, use the **AsByteStream** parameter and a value of 0 for the **ReadCount** parameter.</span></span> <span data-ttu-id="314cf-250">Um valor de **readCount** de 0 lê o arquivo inteiro em uma única operação de leitura.</span><span class="sxs-lookup"><span data-stu-id="314cf-250">A **ReadCount** value of 0 reads the entire file in a single read operation.</span></span> <span data-ttu-id="314cf-251">O valor padrão de **readCount** , 1, lê um byte em cada operação de leitura e converte cada byte em um objeto separado, o que causa erros quando você usa o `Set-Content` cmdlet para gravar os bytes em um arquivo, a menos que use o parâmetro **AsByteStream** .</span><span class="sxs-lookup"><span data-stu-id="314cf-251">The default **ReadCount** value, 1, reads one byte in each read operation and converts each byte into a separate object, which causes errors when you use the `Set-Content` cmdlet to write the bytes to a file unless you use **AsByteStream** parameter.</span></span>

<span data-ttu-id="314cf-252">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="314cf-252">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="314cf-253">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="314cf-253">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="314cf-254">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="314cf-254">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="314cf-255">Esse parâmetro só está disponível no Windows.</span><span class="sxs-lookup"><span data-stu-id="314cf-255">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="314cf-256">Obtém o fluxo de arquivos NTFS alternativo especificado do conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="314cf-256">Gets the contents of the specified alternate NTFS file stream from the file.</span></span> <span data-ttu-id="314cf-257">Insira o nome do fluxo.</span><span class="sxs-lookup"><span data-stu-id="314cf-257">Enter the stream name.</span></span>
<span data-ttu-id="314cf-258">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="314cf-258">Wildcards are not supported.</span></span>

<span data-ttu-id="314cf-259">**Stream** é um parâmetro dinâmico que o provedor **FileSystem** adiciona ao `Get-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="314cf-259">**Stream** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet.</span></span>
<span data-ttu-id="314cf-260">Esse parâmetro funciona apenas em unidades do sistema de arquivos em sistemas Windows.</span><span class="sxs-lookup"><span data-stu-id="314cf-260">This parameter works only in file system drives on Windows systems.</span></span> <span data-ttu-id="314cf-261">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="314cf-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="314cf-262">-AsByteStream</span><span class="sxs-lookup"><span data-stu-id="314cf-262">-AsByteStream</span></span>

<span data-ttu-id="314cf-263">Especifica que o conteúdo deve ser lido como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="314cf-263">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="314cf-264">O parâmetro **AsByteStream** foi introduzido no Windows PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="314cf-264">The **AsByteStream** parameter was introduced in Windows PowerShell 6.0.</span></span>

<span data-ttu-id="314cf-265">Um aviso ocorre quando você usa o parâmetro **AsByteStream** com o parâmetro **Encoding** .</span><span class="sxs-lookup"><span data-stu-id="314cf-265">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="314cf-266">O parâmetro **AsByteStream** ignora qualquer codificação e a saída é retornada como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="314cf-266">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="314cf-267">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="314cf-267">CommonParameters</span></span>

<span data-ttu-id="314cf-268">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="314cf-268">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="314cf-269">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="314cf-269">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="314cf-270">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="314cf-270">INPUTS</span></span>

### <span data-ttu-id="314cf-271">System.Int64, System.String[], System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="314cf-271">System.Int64, System.String[], System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="314cf-272">Você pode canalizar a contagem de leitura, a contagem total, os caminhos ou as credenciais para `Get-Content` .</span><span class="sxs-lookup"><span data-stu-id="314cf-272">You can pipe the read count, total count, paths, or credentials to `Get-Content`.</span></span>

## <span data-ttu-id="314cf-273">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="314cf-273">OUTPUTS</span></span>

### <span data-ttu-id="314cf-274">System. byte, System. String</span><span class="sxs-lookup"><span data-stu-id="314cf-274">System.Byte, System.String</span></span>

<span data-ttu-id="314cf-275">`Get-Content` Retorna cadeias de caracteres ou bytes.</span><span class="sxs-lookup"><span data-stu-id="314cf-275">`Get-Content` returns strings or bytes.</span></span> <span data-ttu-id="314cf-276">O tipo de saída depende do tipo de conteúdo que você especificar como entrada.</span><span class="sxs-lookup"><span data-stu-id="314cf-276">The output type depends upon the type of content that you specify as input.</span></span>

## <span data-ttu-id="314cf-277">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="314cf-277">NOTES</span></span>

<span data-ttu-id="314cf-278">O `Get-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="314cf-278">The `Get-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="314cf-279">Para obter os provedores em sua sessão, use o `Get-PSProvider` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="314cf-279">To get the providers in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="314cf-280">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="314cf-280">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="314cf-281">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="314cf-281">RELATED LINKS</span></span>

[<span data-ttu-id="314cf-282">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="314cf-282">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="314cf-283">about_Providers</span><span class="sxs-lookup"><span data-stu-id="314cf-283">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="314cf-284">Add-Content</span><span class="sxs-lookup"><span data-stu-id="314cf-284">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="314cf-285">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="314cf-285">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="314cf-286">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="314cf-286">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="314cf-287">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="314cf-287">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="314cf-288">Set-Content</span><span class="sxs-lookup"><span data-stu-id="314cf-288">Set-Content</span></span>](Set-Content.md)
