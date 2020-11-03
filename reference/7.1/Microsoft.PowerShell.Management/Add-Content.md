---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 3ae91d03e6882eeaf6743d11cfeed5d0ed1aae0c
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "93195251"
---
# <span data-ttu-id="310b6-103">Add-Content</span><span class="sxs-lookup"><span data-stu-id="310b6-103">Add-Content</span></span>

## <span data-ttu-id="310b6-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="310b6-104">SYNOPSIS</span></span>
<span data-ttu-id="310b6-105">Adiciona conteúdo aos itens especificados, como a adição de palavras a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="310b6-105">Adds content to the specified items, such as adding words to a file.</span></span>

## <span data-ttu-id="310b6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="310b6-106">SYNTAX</span></span>

### <span data-ttu-id="310b6-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="310b6-107">Path (Default)</span></span>

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="310b6-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="310b6-108">LiteralPath</span></span>

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="310b6-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="310b6-109">DESCRIPTION</span></span>

<span data-ttu-id="310b6-110">O `Add-Content` cmdlet acrescenta o conteúdo a um item ou arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="310b6-110">The `Add-Content` cmdlet appends content to a specified item or file.</span></span> <span data-ttu-id="310b6-111">Você pode especificar o conteúdo, digitando-o no comando ou especificando um objeto que contém o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="310b6-111">You can specify the content by typing the content in the command or by specifying an object that contains the content.</span></span>

<span data-ttu-id="310b6-112">Se você precisar criar arquivos ou diretórios para os exemplos a seguir, consulte [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="310b6-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="310b6-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="310b6-113">EXAMPLES</span></span>

### <span data-ttu-id="310b6-114">Exemplo 1: adicionar uma cadeia de caracteres a todos os arquivos de texto com uma exceção</span><span class="sxs-lookup"><span data-stu-id="310b6-114">Example 1: Add a string to all text files with an exception</span></span>

<span data-ttu-id="310b6-115">Este exemplo acrescenta um valor a arquivos de texto no diretório atual, mas exclui arquivos com base no nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="310b6-115">This example appends a value to text files in the current directory but excludes files based on their file name.</span></span>

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

<span data-ttu-id="310b6-116">O parâmetro **path** especifica todos os `.txt` arquivos no diretório atual, mas o parâmetro **Exclude** ignora os nomes de arquivo que correspondem ao padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="310b6-116">The **Path** parameter specifies all `.txt` files in the current directory, but the **Exclude** parameter ignores file names that match the specified pattern.</span></span> <span data-ttu-id="310b6-117">O parâmetro **Value** especifica a cadeia de caracteres de texto que é gravada nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="310b6-117">The **Value** parameter specifies the text string that is written to the files.</span></span>

### <span data-ttu-id="310b6-118">Exemplo 2: adicionar uma data ao final dos arquivos especificados</span><span class="sxs-lookup"><span data-stu-id="310b6-118">Example 2: Add a date to the end of the specified files</span></span>

<span data-ttu-id="310b6-119">Este exemplo acrescenta a data a arquivos no diretório atual e exibe a data no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="310b6-119">This example appends the date to files in the current directory and displays the date in the PowerShell console.</span></span>

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

```Output
Tuesday, May 14, 2019 8:24:27 AM
Tuesday, May 14, 2019 8:24:27 AM
5/14/2019 8:24:27 AM
```

<span data-ttu-id="310b6-120">O `Add-Content` cmdlet cria dois novos arquivos no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="310b6-120">The `Add-Content` cmdlet creates two new files in the current directory.</span></span> <span data-ttu-id="310b6-121">O parâmetro **Value** contém a saída do `Get-Date` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="310b6-121">The **Value** parameter contains the output of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="310b6-122">O parâmetro **PassThru** gera o conteúdo adicionado ao pipeline.</span><span class="sxs-lookup"><span data-stu-id="310b6-122">The **PassThru** parameter outputs the added contents to the pipeline.</span></span>
<span data-ttu-id="310b6-123">Como não há nenhum outro cmdlet para receber a saída, ele é exibido no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="310b6-123">Because there is no other cmdlet to receive the output, it is displayed in the PowerShell console.</span></span>
<span data-ttu-id="310b6-124">O `Get-Content` cmdlet exibe o arquivo atualizado, `DateTimeFile1.log` .</span><span class="sxs-lookup"><span data-stu-id="310b6-124">The `Get-Content` cmdlet displays the updated file, `DateTimeFile1.log`.</span></span>

### <span data-ttu-id="310b6-125">Exemplo 3: Adicionar o conteúdo de um arquivo especificado a outro arquivo</span><span class="sxs-lookup"><span data-stu-id="310b6-125">Example 3: Add the contents of a specified file to another file</span></span>

<span data-ttu-id="310b6-126">Este exemplo obtém o conteúdo de um arquivo e armazena o conteúdo em uma variável.</span><span class="sxs-lookup"><span data-stu-id="310b6-126">This example gets the content from a file and stores the content in a variable.</span></span> <span data-ttu-id="310b6-127">A variável é usada para acrescentar o conteúdo a outro arquivo.</span><span class="sxs-lookup"><span data-stu-id="310b6-127">The variable is used to append the content into another file.</span></span>

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

- <span data-ttu-id="310b6-128">O `Get-Content` cmdlet obtém o conteúdo de `CopyFromFile.txt` e armazena o conteúdo na `$From` variável.</span><span class="sxs-lookup"><span data-stu-id="310b6-128">The `Get-Content` cmdlet gets the contents of `CopyFromFile.txt` and stores the contents in the `$From` variable.</span></span>
- <span data-ttu-id="310b6-129">O `Add-Content` cmdlet atualiza o `CopyToFile.txt` arquivo usando o conteúdo da `$From` variável.</span><span class="sxs-lookup"><span data-stu-id="310b6-129">The `Add-Content` cmdlet updates the `CopyToFile.txt` file using the contents of the `$From` variable.</span></span>
- <span data-ttu-id="310b6-130">O `Get-Content` cmdlet exibe CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="310b6-130">The `Get-Content` cmdlet displays CopyToFile.txt.</span></span>

### <span data-ttu-id="310b6-131">Exemplo 4: Adicionar o conteúdo de um arquivo especificado a outro arquivo usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="310b6-131">Example 4: Add the contents of a specified file to another file using the pipeline</span></span>

<span data-ttu-id="310b6-132">Este exemplo obtém o conteúdo de um arquivo e o canaliza para o `Add-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="310b6-132">This example gets the content from a file and pipes it to the `Add-Content` cmdlet.</span></span>

```powershell
Get-Content -Path .\CopyFromFile.txt | Add-Content -Path .\CopyToFile.txt
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="310b6-133">O `Get-Content` cmdlet obtém o conteúdo de `CopyFromFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="310b6-133">The `Get-Content` cmdlet gets the contents of `CopyFromFile.txt`.</span></span> <span data-ttu-id="310b6-134">Os resultados são canalizados para o `Add-Content` cmdlet, que atualiza o `CopyToFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="310b6-134">The results are piped to the `Add-Content` cmdlet, which updates the `CopyToFile.txt`.</span></span>
<span data-ttu-id="310b6-135">O último `Get-Content` cmdlet é exibido `CopyToFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="310b6-135">The last `Get-Content` cmdlet displays `CopyToFile.txt`.</span></span>

### <span data-ttu-id="310b6-136">Exemplo 5: criar um novo arquivo e copiar o conteúdo</span><span class="sxs-lookup"><span data-stu-id="310b6-136">Example 5: Create a new file and copy content</span></span>

<span data-ttu-id="310b6-137">Este exemplo cria um novo arquivo e copia o conteúdo de um arquivo existente no novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="310b6-137">This example creates a new file and copies an existing file's content into the new file.</span></span>

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

- <span data-ttu-id="310b6-138">O `Add-Content` cmdlet usa os parâmetros **Path** e **Value** para criar um novo arquivo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="310b6-138">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create a new file in the current directory.</span></span>
- <span data-ttu-id="310b6-139">O `Get-Content` cmdlet obtém o conteúdo de um arquivo existente `CopyFromFile.txt` e o passa para o parâmetro **Value** .</span><span class="sxs-lookup"><span data-stu-id="310b6-139">The `Get-Content` cmdlet gets the contents of an existing file, `CopyFromFile.txt` and passes it to the **Value** parameter.</span></span> <span data-ttu-id="310b6-140">Os parênteses em volta do `Get-Content` cmdlet garantem que o comando seja concluído antes do `Add-Content` início do comando.</span><span class="sxs-lookup"><span data-stu-id="310b6-140">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span>
- <span data-ttu-id="310b6-141">O `Get-Content` cmdlet exibe o conteúdo do novo arquivo, `NewFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="310b6-141">The `Get-Content` cmdlet displays the contents of the new file, `NewFile.txt`.</span></span>

### <span data-ttu-id="310b6-142">Exemplo 6: adicionar conteúdo a um arquivo somente leitura</span><span class="sxs-lookup"><span data-stu-id="310b6-142">Example 6: Add content to a read-only file</span></span>

<span data-ttu-id="310b6-143">Esse comando adiciona um valor ao arquivo, mesmo que o atributo de arquivo **IsReadOnly** esteja definido como **true** .</span><span class="sxs-lookup"><span data-stu-id="310b6-143">This command adds a value to the file even if the **IsReadOnly** file attribute is set to **True** .</span></span>
<span data-ttu-id="310b6-144">As etapas para criar um arquivo somente leitura são incluídas no exemplo.</span><span class="sxs-lookup"><span data-stu-id="310b6-144">The steps to create a read-only file are included in the example.</span></span>

```powershell
New-Item -Path .\IsReadOnlyTextFile.txt -ItemType File
Set-ItemProperty -Path .\IsReadOnlyTextFile.txt -Name IsReadOnly -Value $True
Get-ChildItem -Path .\IsReadOnlyTextFile.txt
Add-Content -Path .\IsReadOnlyTextFile.txt -Value 'Add value to read-only text file' -Force
Get-Content -Path .\IsReadOnlyTextFile.txt
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-ar--         1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

- <span data-ttu-id="310b6-145">O `New-Item` cmdlet usa os parâmetros **Path** e **ItemType** para criar o arquivo `IsReadOnlyTextFile.txt` no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="310b6-145">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the file `IsReadOnlyTextFile.txt` in the current directory.</span></span>
- <span data-ttu-id="310b6-146">O `Set-ItemProperty` cmdlet usa os parâmetros **Name** e **Value** para alterar a propriedade **IsReadOnly** do arquivo para true.</span><span class="sxs-lookup"><span data-stu-id="310b6-146">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to True.</span></span>
- <span data-ttu-id="310b6-147">O `Get-ChildItem` cmdlet mostra que o arquivo está vazio (0) e tem o atributo somente leitura ( `r` ).</span><span class="sxs-lookup"><span data-stu-id="310b6-147">The `Get-ChildItem` cmdlet shows the file is empty (0) and has the read-only attribute (`r`).</span></span>
- <span data-ttu-id="310b6-148">O `Add-Content` cmdlet usa o parâmetro **Path** para especificar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="310b6-148">The `Add-Content` cmdlet uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="310b6-149">O parâmetro **Value** inclui a cadeia de caracteres de texto a ser acrescentada ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="310b6-149">The **Value** parameter includes the text string to append to the file.</span></span> <span data-ttu-id="310b6-150">O parâmetro **Force** grava o texto no arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="310b6-150">The **Force** parameter writes the text to the read-only file.</span></span>
- <span data-ttu-id="310b6-151">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="310b6-151">The `Get-Content` cmdlet uses the **Path** parameter to display the file's contents.</span></span>

<span data-ttu-id="310b6-152">Para remover o atributo somente leitura, use o `Set-ItemProperty` comando com o parâmetro de **valor** definido como `False` .</span><span class="sxs-lookup"><span data-stu-id="310b6-152">To remove the read-only attribute, use the `Set-ItemProperty` command with the **Value** parameter set to `False`.</span></span>

### <span data-ttu-id="310b6-153">Exemplo 7: usar filtros com Add-Content</span><span class="sxs-lookup"><span data-stu-id="310b6-153">Example 7: Use Filters with Add-Content</span></span>

<span data-ttu-id="310b6-154">Você pode especificar um filtro para o `Add-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="310b6-154">You can specify a filter to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="310b6-155">Ao usar filtros para qualificar o parâmetro de **caminho** , você precisa incluir um asterisco à direita ( `*` ) para indicar o conteúdo do caminho.</span><span class="sxs-lookup"><span data-stu-id="310b6-155">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="310b6-156">O comando a seguir adiciona a palavra "Done" do conteúdo de todos os `*.txt` arquivos no `C:\Temp` diretório.</span><span class="sxs-lookup"><span data-stu-id="310b6-156">The following command adds the word "Done" the content of all `*.txt` files in the `C:\Temp` directory.</span></span>

```powershell
Add-Content -Path C:\Temp\* -Filter *.txt -Value "Done"
```

## <span data-ttu-id="310b6-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="310b6-157">PARAMETERS</span></span>

### <span data-ttu-id="310b6-158">-AsByteStream</span><span class="sxs-lookup"><span data-stu-id="310b6-158">-AsByteStream</span></span>

<span data-ttu-id="310b6-159">Especifica que o conteúdo deve ser lido como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="310b6-159">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="310b6-160">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="310b6-160">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="310b6-161">Um aviso ocorre quando você usa o parâmetro **AsByteStream** com o parâmetro **Encoding** .</span><span class="sxs-lookup"><span data-stu-id="310b6-161">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="310b6-162">O parâmetro **AsByteStream** ignora qualquer codificação e a saída é retornada como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="310b6-162">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="310b6-163">-Credential</span><span class="sxs-lookup"><span data-stu-id="310b6-163">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="310b6-164">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="310b6-164">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="310b6-165">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="310b6-165">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="310b6-166">-Codificação</span><span class="sxs-lookup"><span data-stu-id="310b6-166">-Encoding</span></span>

<span data-ttu-id="310b6-167">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="310b6-167">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="310b6-168">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="310b6-168">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="310b6-169">A codificação é um parâmetro dinâmico que o provedor FileSystem adiciona ao `Add-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="310b6-169">Encoding is a dynamic parameter that the FileSystem provider adds to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="310b6-170">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="310b6-170">This parameter works only in file system drives.</span></span>

<span data-ttu-id="310b6-171">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="310b6-171">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="310b6-172">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="310b6-172">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="310b6-173">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="310b6-173">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="310b6-174">`bigendianutf32`: Codifica em formato UTF-32 usando a ordem de byte big-endian.</span><span class="sxs-lookup"><span data-stu-id="310b6-174">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="310b6-175">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="310b6-175">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="310b6-176">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="310b6-176">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="310b6-177">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="310b6-177">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="310b6-178">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="310b6-178">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="310b6-179">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="310b6-179">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="310b6-180">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="310b6-180">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="310b6-181">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="310b6-181">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="310b6-182">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="310b6-182">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="310b6-183">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="310b6-183">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="310b6-184">O **UTF-7** \* não é mais recomendado para uso.</span><span class="sxs-lookup"><span data-stu-id="310b6-184">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="310b6-185">No PowerShell 7,1, um aviso será gravado se você especificar `utf7` para o parâmetro de **codificação** .</span><span class="sxs-lookup"><span data-stu-id="310b6-185">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="310b6-186">-Excluir</span><span class="sxs-lookup"><span data-stu-id="310b6-186">-Exclude</span></span>

<span data-ttu-id="310b6-187">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="310b6-187">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="310b6-188">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="310b6-188">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="310b6-189">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="310b6-189">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="310b6-190">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="310b6-190">Wildcard characters are permitted.</span></span> <span data-ttu-id="310b6-191">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="310b6-191">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="310b6-192">-Filter</span><span class="sxs-lookup"><span data-stu-id="310b6-192">-Filter</span></span>

<span data-ttu-id="310b6-193">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="310b6-193">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="310b6-194">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="310b6-194">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="310b6-195">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="310b6-195">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="310b6-196">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="310b6-196">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="310b6-197">-Force</span><span class="sxs-lookup"><span data-stu-id="310b6-197">-Force</span></span>

<span data-ttu-id="310b6-198">Substitui o atributo somente leitura, permitindo adicionar conteúdo a um arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="310b6-198">Overrides the read-only attribute, allowing you to add content to a read-only file.</span></span> <span data-ttu-id="310b6-199">Por exemplo, o **Force** substituirá o atributo somente leitura ou criar diretórios para concluir um caminho de arquivo, mas não tentará alterar permissões de arquivo.</span><span class="sxs-lookup"><span data-stu-id="310b6-199">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="310b6-200">-Incluir</span><span class="sxs-lookup"><span data-stu-id="310b6-200">-Include</span></span>

<span data-ttu-id="310b6-201">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="310b6-201">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="310b6-202">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="310b6-202">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="310b6-203">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="310b6-203">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="310b6-204">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="310b6-204">Wildcard characters are permitted.</span></span> <span data-ttu-id="310b6-205">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="310b6-205">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="310b6-206">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="310b6-206">-LiteralPath</span></span>

<span data-ttu-id="310b6-207">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="310b6-207">Specifies a path to one or more locations.</span></span> <span data-ttu-id="310b6-208">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="310b6-208">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="310b6-209">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="310b6-209">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="310b6-210">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="310b6-210">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="310b6-211">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="310b6-211">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="310b6-212">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="310b6-212">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="310b6-213">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="310b6-213">-NoNewline</span></span>

<span data-ttu-id="310b6-214">Indica que esse cmdlet não adiciona uma nova linha ou retorno de carro ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="310b6-214">Indicates that this cmdlet does not add a new line or carriage return to the content.</span></span>

<span data-ttu-id="310b6-215">As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída.</span><span class="sxs-lookup"><span data-stu-id="310b6-215">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="310b6-216">Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="310b6-216">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="310b6-217">Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="310b6-217">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="310b6-218">-PassThru</span><span class="sxs-lookup"><span data-stu-id="310b6-218">-PassThru</span></span>

<span data-ttu-id="310b6-219">Retorna um objeto que representa o conteúdo adicionado.</span><span class="sxs-lookup"><span data-stu-id="310b6-219">Returns an object representing the added content.</span></span> <span data-ttu-id="310b6-220">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="310b6-220">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="310b6-221">-Path</span><span class="sxs-lookup"><span data-stu-id="310b6-221">-Path</span></span>

<span data-ttu-id="310b6-222">Especifica o caminho para os itens que recebem conteúdo adicional.</span><span class="sxs-lookup"><span data-stu-id="310b6-222">Specifies the path to the items that receive the additional content.</span></span>
<span data-ttu-id="310b6-223">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="310b6-223">Wildcard characters are permitted.</span></span>
<span data-ttu-id="310b6-224">Os caminhos devem ser caminhos para itens, não para contêineres.</span><span class="sxs-lookup"><span data-stu-id="310b6-224">The paths must be paths to items, not to containers.</span></span>
<span data-ttu-id="310b6-225">Por exemplo, você deve especificar um caminho para um ou mais arquivos, não um caminho para um diretório.</span><span class="sxs-lookup"><span data-stu-id="310b6-225">For example, you must specify a path to one or more files, not a path to a directory.</span></span>
<span data-ttu-id="310b6-226">Se você especificar vários caminhos, use vírgulas para separá-los.</span><span class="sxs-lookup"><span data-stu-id="310b6-226">If you specify multiple paths, use commas to separate the paths.</span></span>

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

### <span data-ttu-id="310b6-227">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="310b6-227">-Stream</span></span>

<span data-ttu-id="310b6-228">Especifica um fluxo de dados alternativo para o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="310b6-228">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="310b6-229">Se o fluxo não existir, esse cmdlet o criará.</span><span class="sxs-lookup"><span data-stu-id="310b6-229">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="310b6-230">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="310b6-230">Wildcard characters are not supported.</span></span>

<span data-ttu-id="310b6-231">**Stream** é um parâmetro dinâmico que o provedor FileSystem adiciona `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="310b6-231">**Stream** is a dynamic parameter that the FileSystem provider adds to `Add-Content`.</span></span> <span data-ttu-id="310b6-232">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="310b6-232">This parameter works only in file system drives.</span></span>

<span data-ttu-id="310b6-233">Você pode usar o `Add-Content` cmdlet para alterar o conteúdo do fluxo de dados de **zona. identificador** alternativo.</span><span class="sxs-lookup"><span data-stu-id="310b6-233">You can use the `Add-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="310b6-234">No entanto, não recomendamos isso como uma maneira de eliminar verificações de segurança que bloqueiam arquivos baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="310b6-234">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="310b6-235">Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="310b6-235">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="310b6-236">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="310b6-236">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="310b6-237">-Value</span><span class="sxs-lookup"><span data-stu-id="310b6-237">-Value</span></span>

<span data-ttu-id="310b6-238">Especifica o conteúdo a ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="310b6-238">Specifies the content to be added.</span></span> <span data-ttu-id="310b6-239">Digite uma cadeia de caracteres entre aspas, como **esses dados são somente para uso interno** ou especifique um objeto que contenha conteúdo, como o objeto **DateTime** que `Get-Date` gera.</span><span class="sxs-lookup"><span data-stu-id="310b6-239">Type a quoted string, such as **This data is for internal use only** , or specify an object that contains content, such as the **DateTime** object that `Get-Date` generates.</span></span>

<span data-ttu-id="310b6-240">Você não pode especificar o conteúdo de um arquivo digitando seu caminho, pois o caminho é apenas uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="310b6-240">You cannot specify the contents of a file by typing its path, because the path is just a string.</span></span>
<span data-ttu-id="310b6-241">Você pode usar um `Get-Content` comando para obter o conteúdo e passá-lo para o parâmetro **Value** .</span><span class="sxs-lookup"><span data-stu-id="310b6-241">You can use a `Get-Content` command to get the content and pass it to the **Value** parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="310b6-242">-Confirm</span><span class="sxs-lookup"><span data-stu-id="310b6-242">-Confirm</span></span>

<span data-ttu-id="310b6-243">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="310b6-243">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="310b6-244">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="310b6-244">-WhatIf</span></span>

<span data-ttu-id="310b6-245">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="310b6-245">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="310b6-246">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="310b6-246">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="310b6-247">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="310b6-247">CommonParameters</span></span>
<span data-ttu-id="310b6-248">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="310b6-248">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="310b6-249">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="310b6-249">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="310b6-250">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="310b6-250">INPUTS</span></span>

### <span data-ttu-id="310b6-251">System. Object, System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="310b6-251">System.Object, System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="310b6-252">Você pode canalizar valores, caminhos ou credenciais para `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="310b6-252">You can pipe values, paths, or credentials to `Set-Content`.</span></span>

## <span data-ttu-id="310b6-253">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="310b6-253">OUTPUTS</span></span>

### <span data-ttu-id="310b6-254">Nenhum ou System.String</span><span class="sxs-lookup"><span data-stu-id="310b6-254">None or System.String</span></span>

<span data-ttu-id="310b6-255">Quando você usa o parâmetro **PassThru** , o `Add-Content` gera um objeto **System. String** que representa o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="310b6-255">When you use the **PassThru** parameter, `Add-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="310b6-256">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="310b6-256">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="310b6-257">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="310b6-257">NOTES</span></span>

- <span data-ttu-id="310b6-258">Quando você canaliza um objeto para `Add-Content` , o objeto é convertido em uma cadeia de caracteres antes de ser adicionado ao item.</span><span class="sxs-lookup"><span data-stu-id="310b6-258">When you pipe an object to `Add-Content`, the object is converted to a string before it is added to the item.</span></span> <span data-ttu-id="310b6-259">O tipo de objeto determina o formato de cadeia de caracteres, mas o formato pode ser diferente da exibição padrão do objeto.</span><span class="sxs-lookup"><span data-stu-id="310b6-259">The object type determines the string format, but the format might be different than the default display of the object.</span></span> <span data-ttu-id="310b6-260">Para controlar o formato da cadeia de caracteres, use os parâmetros de formatação do cmdlet de envio.</span><span class="sxs-lookup"><span data-stu-id="310b6-260">To control the string format, use the formatting parameters of the sending cmdlet.</span></span>
- <span data-ttu-id="310b6-261">Você também pode consultar `Add-Content` por seu alias interno, `ac` .</span><span class="sxs-lookup"><span data-stu-id="310b6-261">You can also refer to `Add-Content` by its built-in alias, `ac`.</span></span> <span data-ttu-id="310b6-262">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="310b6-262">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="310b6-263">O `Add-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="310b6-263">The `Add-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="310b6-264">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="310b6-264">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="310b6-265">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="310b6-265">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="310b6-266">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="310b6-266">RELATED LINKS</span></span>

[<span data-ttu-id="310b6-267">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="310b6-267">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="310b6-268">about_Providers</span><span class="sxs-lookup"><span data-stu-id="310b6-268">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="310b6-269">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="310b6-269">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="310b6-270">Get-Content</span><span class="sxs-lookup"><span data-stu-id="310b6-270">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="310b6-271">Get-Item</span><span class="sxs-lookup"><span data-stu-id="310b6-271">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="310b6-272">New-Item</span><span class="sxs-lookup"><span data-stu-id="310b6-272">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="310b6-273">Set-Content</span><span class="sxs-lookup"><span data-stu-id="310b6-273">Set-Content</span></span>](Set-Content.md)

