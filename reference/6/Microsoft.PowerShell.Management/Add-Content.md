---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 291ec8f3a3958aa726fafb8032b996296272a21e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193458"
---
# <span data-ttu-id="18007-103">Add-Content</span><span class="sxs-lookup"><span data-stu-id="18007-103">Add-Content</span></span>

## <span data-ttu-id="18007-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="18007-104">SYNOPSIS</span></span>
<span data-ttu-id="18007-105">Adiciona conteúdo aos itens especificados, como a adição de palavras a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="18007-105">Adds content to the specified items, such as adding words to a file.</span></span>

## <span data-ttu-id="18007-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="18007-106">SYNTAX</span></span>

### <span data-ttu-id="18007-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="18007-107">Path (Default)</span></span>

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="18007-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="18007-108">LiteralPath</span></span>

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="18007-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="18007-109">DESCRIPTION</span></span>

<span data-ttu-id="18007-110">O `Add-Content` cmdlet acrescenta o conteúdo a um item ou arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="18007-110">The `Add-Content` cmdlet appends content to a specified item or file.</span></span> <span data-ttu-id="18007-111">Você pode especificar o conteúdo, digitando-o no comando ou especificando um objeto que contém o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="18007-111">You can specify the content by typing the content in the command or by specifying an object that contains the content.</span></span>

<span data-ttu-id="18007-112">Se você precisar criar arquivos ou diretórios para os exemplos a seguir, consulte [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="18007-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="18007-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="18007-113">EXAMPLES</span></span>

### <span data-ttu-id="18007-114">Exemplo 1: adicionar uma cadeia de caracteres a todos os arquivos de texto com uma exceção</span><span class="sxs-lookup"><span data-stu-id="18007-114">Example 1: Add a string to all text files with an exception</span></span>

<span data-ttu-id="18007-115">Este exemplo acrescenta um valor a arquivos de texto no diretório atual, mas exclui arquivos com base no nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="18007-115">This example appends a value to text files in the current directory but excludes files based on their file name.</span></span>

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

<span data-ttu-id="18007-116">O parâmetro **path** especifica todos os `.txt` arquivos no diretório atual, mas o parâmetro **Exclude** ignora os nomes de arquivo que correspondem ao padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="18007-116">The **Path** parameter specifies all `.txt` files in the current directory, but the **Exclude** parameter ignores file names that match the specified pattern.</span></span> <span data-ttu-id="18007-117">O parâmetro **Value** especifica a cadeia de caracteres de texto que é gravada nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="18007-117">The **Value** parameter specifies the text string that is written to the files.</span></span>

### <span data-ttu-id="18007-118">Exemplo 2: adicionar uma data ao final dos arquivos especificados</span><span class="sxs-lookup"><span data-stu-id="18007-118">Example 2: Add a date to the end of the specified files</span></span>

<span data-ttu-id="18007-119">Este exemplo acrescenta a data a arquivos no diretório atual e exibe a data no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18007-119">This example appends the date to files in the current directory and displays the date in the PowerShell console.</span></span>

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

```Output
Tuesday, May 14, 2019 8:24:27 AM
Tuesday, May 14, 2019 8:24:27 AM
5/14/2019 8:24:27 AM
```

<span data-ttu-id="18007-120">O `Add-Content` cmdlet cria dois novos arquivos no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="18007-120">The `Add-Content` cmdlet creates two new files in the current directory.</span></span> <span data-ttu-id="18007-121">O parâmetro **Value** contém a saída do `Get-Date` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18007-121">The **Value** parameter contains the output of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="18007-122">O parâmetro **PassThru** gera o conteúdo adicionado ao pipeline.</span><span class="sxs-lookup"><span data-stu-id="18007-122">The **PassThru** parameter outputs the added contents to the pipeline.</span></span>
<span data-ttu-id="18007-123">Como não há nenhum outro cmdlet para receber a saída, ele é exibido no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18007-123">Because there is no other cmdlet to receive the output, it is displayed in the PowerShell console.</span></span>
<span data-ttu-id="18007-124">O `Get-Content` cmdlet exibe o arquivo atualizado, `DateTimeFile1.log` .</span><span class="sxs-lookup"><span data-stu-id="18007-124">The `Get-Content` cmdlet displays the updated file, `DateTimeFile1.log`.</span></span>

### <span data-ttu-id="18007-125">Exemplo 3: Adicionar o conteúdo de um arquivo especificado a outro arquivo</span><span class="sxs-lookup"><span data-stu-id="18007-125">Example 3: Add the contents of a specified file to another file</span></span>

<span data-ttu-id="18007-126">Este exemplo obtém o conteúdo de um arquivo e armazena o conteúdo em uma variável.</span><span class="sxs-lookup"><span data-stu-id="18007-126">This example gets the content from a file and stores the content in a variable.</span></span> <span data-ttu-id="18007-127">A variável é usada para acrescentar o conteúdo a outro arquivo.</span><span class="sxs-lookup"><span data-stu-id="18007-127">The variable is used to append the content into another file.</span></span>

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

- <span data-ttu-id="18007-128">O `Get-Content` cmdlet obtém o conteúdo de `CopyFromFile.txt` e armazena o conteúdo na `$From` variável.</span><span class="sxs-lookup"><span data-stu-id="18007-128">The `Get-Content` cmdlet gets the contents of `CopyFromFile.txt` and stores the contents in the `$From` variable.</span></span>
- <span data-ttu-id="18007-129">O `Add-Content` cmdlet atualiza o `CopyToFile.txt` arquivo usando o conteúdo da `$From` variável.</span><span class="sxs-lookup"><span data-stu-id="18007-129">The `Add-Content` cmdlet updates the `CopyToFile.txt` file using the contents of the `$From` variable.</span></span>
- <span data-ttu-id="18007-130">O `Get-Content` cmdlet exibe CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="18007-130">The `Get-Content` cmdlet displays CopyToFile.txt.</span></span>

### <span data-ttu-id="18007-131">Exemplo 4: Adicionar o conteúdo de um arquivo especificado a outro arquivo usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="18007-131">Example 4: Add the contents of a specified file to another file using the pipeline</span></span>

<span data-ttu-id="18007-132">Este exemplo obtém o conteúdo de um arquivo e o canaliza para o `Add-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18007-132">This example gets the content from a file and pipes it to the `Add-Content` cmdlet.</span></span>

```powershell
Get-Content -Path .\CopyFromFile.txt | Add-Content -Path .\CopyToFile.txt
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="18007-133">O `Get-Content` cmdlet obtém o conteúdo de `CopyFromFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="18007-133">The `Get-Content` cmdlet gets the contents of `CopyFromFile.txt`.</span></span> <span data-ttu-id="18007-134">Os resultados são canalizados para o `Add-Content` cmdlet, que atualiza o `CopyToFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="18007-134">The results are piped to the `Add-Content` cmdlet, which updates the `CopyToFile.txt`.</span></span>
<span data-ttu-id="18007-135">O último `Get-Content` cmdlet é exibido `CopyToFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="18007-135">The last `Get-Content` cmdlet displays `CopyToFile.txt`.</span></span>

### <span data-ttu-id="18007-136">Exemplo 5: criar um novo arquivo e copiar o conteúdo</span><span class="sxs-lookup"><span data-stu-id="18007-136">Example 5: Create a new file and copy content</span></span>

<span data-ttu-id="18007-137">Este exemplo cria um novo arquivo e copia o conteúdo de um arquivo existente no novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="18007-137">This example creates a new file and copies an existing file's content into the new file.</span></span>

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

- <span data-ttu-id="18007-138">O `Add-Content` cmdlet usa os parâmetros **Path** e **Value** para criar um novo arquivo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="18007-138">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create a new file in the current directory.</span></span>
- <span data-ttu-id="18007-139">O `Get-Content` cmdlet obtém o conteúdo de um arquivo existente `CopyFromFile.txt` e o passa para o parâmetro **Value** .</span><span class="sxs-lookup"><span data-stu-id="18007-139">The `Get-Content` cmdlet gets the contents of an existing file, `CopyFromFile.txt` and passes it to the **Value** parameter.</span></span> <span data-ttu-id="18007-140">Os parênteses em volta do `Get-Content` cmdlet garantem que o comando seja concluído antes do `Add-Content` início do comando.</span><span class="sxs-lookup"><span data-stu-id="18007-140">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span>
- <span data-ttu-id="18007-141">O `Get-Content` cmdlet exibe o conteúdo do novo arquivo, `NewFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="18007-141">The `Get-Content` cmdlet displays the contents of the new file, `NewFile.txt`.</span></span>

### <span data-ttu-id="18007-142">Exemplo 6: adicionar conteúdo a um arquivo somente leitura</span><span class="sxs-lookup"><span data-stu-id="18007-142">Example 6: Add content to a read-only file</span></span>

<span data-ttu-id="18007-143">Esse comando adiciona um valor ao arquivo, mesmo que o atributo de arquivo **IsReadOnly** esteja definido como **true** .</span><span class="sxs-lookup"><span data-stu-id="18007-143">This command adds a value to the file even if the **IsReadOnly** file attribute is set to **True** .</span></span>
<span data-ttu-id="18007-144">As etapas para criar um arquivo somente leitura são incluídas no exemplo.</span><span class="sxs-lookup"><span data-stu-id="18007-144">The steps to create a read-only file are included in the example.</span></span>

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

- <span data-ttu-id="18007-145">O `New-Item` cmdlet usa os parâmetros **Path** e **ItemType** para criar o arquivo `IsReadOnlyTextFile.txt` no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="18007-145">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the file `IsReadOnlyTextFile.txt` in the current directory.</span></span>
- <span data-ttu-id="18007-146">O `Set-ItemProperty` cmdlet usa os parâmetros **Name** e **Value** para alterar a propriedade **IsReadOnly** do arquivo para true.</span><span class="sxs-lookup"><span data-stu-id="18007-146">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to True.</span></span>
- <span data-ttu-id="18007-147">O `Get-ChildItem` cmdlet mostra que o arquivo está vazio (0) e tem o atributo somente leitura ( `r` ).</span><span class="sxs-lookup"><span data-stu-id="18007-147">The `Get-ChildItem` cmdlet shows the file is empty (0) and has the read-only attribute (`r`).</span></span>
- <span data-ttu-id="18007-148">O `Add-Content` cmdlet usa o parâmetro **Path** para especificar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="18007-148">The `Add-Content` cmdlet uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="18007-149">O parâmetro **Value** inclui a cadeia de caracteres de texto a ser acrescentada ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="18007-149">The **Value** parameter includes the text string to append to the file.</span></span> <span data-ttu-id="18007-150">O parâmetro **Force** grava o texto no arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="18007-150">The **Force** parameter writes the text to the read-only file.</span></span>
- <span data-ttu-id="18007-151">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="18007-151">The `Get-Content` cmdlet uses the **Path** parameter to display the file's contents.</span></span>

<span data-ttu-id="18007-152">Para remover o atributo somente leitura, use o `Set-ItemProperty` comando com o parâmetro de **valor** definido como `False` .</span><span class="sxs-lookup"><span data-stu-id="18007-152">To remove the read-only attribute, use the `Set-ItemProperty` command with the **Value** parameter set to `False`.</span></span>

### <span data-ttu-id="18007-153">Exemplo 7: usar filtros com Add-Content</span><span class="sxs-lookup"><span data-stu-id="18007-153">Example 7: Use Filters with Add-Content</span></span>

<span data-ttu-id="18007-154">Você pode especificar um filtro para o `Add-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18007-154">You can specify a filter to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="18007-155">Ao usar filtros para qualificar o parâmetro de **caminho** , você precisa incluir um asterisco à direita ( `*` ) para indicar o conteúdo do caminho.</span><span class="sxs-lookup"><span data-stu-id="18007-155">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="18007-156">O comando a seguir adiciona a palavra "Done" do conteúdo de todos os `*.txt` arquivos no `C:\Temp` diretório.</span><span class="sxs-lookup"><span data-stu-id="18007-156">The following command adds the word "Done" the content of all `*.txt` files in the `C:\Temp` directory.</span></span>

```powershell
Add-Content -Path C:\Temp\* -Filter *.txt -Value "Done"
```

## <span data-ttu-id="18007-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="18007-157">PARAMETERS</span></span>

### <span data-ttu-id="18007-158">-AsByteStream</span><span class="sxs-lookup"><span data-stu-id="18007-158">-AsByteStream</span></span>

<span data-ttu-id="18007-159">Especifica que o conteúdo deve ser lido como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="18007-159">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="18007-160">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="18007-160">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="18007-161">Um aviso ocorre quando você usa o parâmetro **AsByteStream** com o parâmetro **Encoding** .</span><span class="sxs-lookup"><span data-stu-id="18007-161">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="18007-162">O parâmetro **AsByteStream** ignora qualquer codificação e a saída é retornada como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="18007-162">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="18007-163">-Credential</span><span class="sxs-lookup"><span data-stu-id="18007-163">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="18007-164">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18007-164">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="18007-165">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="18007-165">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="18007-166">-Codificação</span><span class="sxs-lookup"><span data-stu-id="18007-166">-Encoding</span></span>

<span data-ttu-id="18007-167">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="18007-167">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="18007-168">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="18007-168">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="18007-169">A codificação é um parâmetro dinâmico que o provedor FileSystem adiciona ao `Add-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18007-169">Encoding is a dynamic parameter that the FileSystem provider adds to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="18007-170">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="18007-170">This parameter works only in file system drives.</span></span>

<span data-ttu-id="18007-171">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18007-171">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="18007-172">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="18007-172">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="18007-173">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="18007-173">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="18007-174">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="18007-174">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="18007-175">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="18007-175">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="18007-176">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="18007-176">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="18007-177">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="18007-177">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="18007-178">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="18007-178">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="18007-179">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="18007-179">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="18007-180">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="18007-180">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="18007-181">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="18007-181">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="18007-182">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="18007-182">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

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

### <span data-ttu-id="18007-183">-Excluir</span><span class="sxs-lookup"><span data-stu-id="18007-183">-Exclude</span></span>

<span data-ttu-id="18007-184">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="18007-184">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="18007-185">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="18007-185">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="18007-186">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="18007-186">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="18007-187">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="18007-187">Wildcard characters are permitted.</span></span> <span data-ttu-id="18007-188">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="18007-188">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="18007-189">-Filter</span><span class="sxs-lookup"><span data-stu-id="18007-189">-Filter</span></span>

<span data-ttu-id="18007-190">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="18007-190">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="18007-191">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="18007-191">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="18007-192">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="18007-192">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="18007-193">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="18007-193">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="18007-194">-Force</span><span class="sxs-lookup"><span data-stu-id="18007-194">-Force</span></span>

<span data-ttu-id="18007-195">Substitui o atributo somente leitura, permitindo adicionar conteúdo a um arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="18007-195">Overrides the read-only attribute, allowing you to add content to a read-only file.</span></span> <span data-ttu-id="18007-196">Por exemplo, o **Force** substituirá o atributo somente leitura ou criar diretórios para concluir um caminho de arquivo, mas não tentará alterar permissões de arquivo.</span><span class="sxs-lookup"><span data-stu-id="18007-196">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="18007-197">-Incluir</span><span class="sxs-lookup"><span data-stu-id="18007-197">-Include</span></span>

<span data-ttu-id="18007-198">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="18007-198">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="18007-199">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="18007-199">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="18007-200">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="18007-200">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="18007-201">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="18007-201">Wildcard characters are permitted.</span></span> <span data-ttu-id="18007-202">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="18007-202">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="18007-203">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="18007-203">-LiteralPath</span></span>

<span data-ttu-id="18007-204">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="18007-204">Specifies a path to one or more locations.</span></span> <span data-ttu-id="18007-205">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="18007-205">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="18007-206">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="18007-206">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="18007-207">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="18007-207">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="18007-208">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="18007-208">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="18007-209">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="18007-209">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="18007-210">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="18007-210">-NoNewline</span></span>

<span data-ttu-id="18007-211">Indica que esse cmdlet não adiciona uma nova linha ou retorno de carro ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="18007-211">Indicates that this cmdlet does not add a new line or carriage return to the content.</span></span>

<span data-ttu-id="18007-212">As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída.</span><span class="sxs-lookup"><span data-stu-id="18007-212">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="18007-213">Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="18007-213">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="18007-214">Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="18007-214">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="18007-215">-PassThru</span><span class="sxs-lookup"><span data-stu-id="18007-215">-PassThru</span></span>

<span data-ttu-id="18007-216">Retorna um objeto que representa o conteúdo adicionado.</span><span class="sxs-lookup"><span data-stu-id="18007-216">Returns an object representing the added content.</span></span> <span data-ttu-id="18007-217">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="18007-217">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="18007-218">-Path</span><span class="sxs-lookup"><span data-stu-id="18007-218">-Path</span></span>

<span data-ttu-id="18007-219">Especifica o caminho para os itens que recebem conteúdo adicional.</span><span class="sxs-lookup"><span data-stu-id="18007-219">Specifies the path to the items that receive the additional content.</span></span>
<span data-ttu-id="18007-220">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="18007-220">Wildcard characters are permitted.</span></span>
<span data-ttu-id="18007-221">Os caminhos devem ser caminhos para itens, não para contêineres.</span><span class="sxs-lookup"><span data-stu-id="18007-221">The paths must be paths to items, not to containers.</span></span>
<span data-ttu-id="18007-222">Por exemplo, você deve especificar um caminho para um ou mais arquivos, não um caminho para um diretório.</span><span class="sxs-lookup"><span data-stu-id="18007-222">For example, you must specify a path to one or more files, not a path to a directory.</span></span>
<span data-ttu-id="18007-223">Se você especificar vários caminhos, use vírgulas para separá-los.</span><span class="sxs-lookup"><span data-stu-id="18007-223">If you specify multiple paths, use commas to separate the paths.</span></span>

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

### <span data-ttu-id="18007-224">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="18007-224">-Stream</span></span>

<span data-ttu-id="18007-225">Especifica um fluxo de dados alternativo para o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="18007-225">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="18007-226">Se o fluxo não existir, esse cmdlet o criará.</span><span class="sxs-lookup"><span data-stu-id="18007-226">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="18007-227">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="18007-227">Wildcard characters are not supported.</span></span>

<span data-ttu-id="18007-228">**Stream** é um parâmetro dinâmico que o provedor FileSystem adiciona `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="18007-228">**Stream** is a dynamic parameter that the FileSystem provider adds to `Add-Content`.</span></span> <span data-ttu-id="18007-229">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="18007-229">This parameter works only in file system drives.</span></span>

<span data-ttu-id="18007-230">Você pode usar o `Add-Content` cmdlet para alterar o conteúdo do fluxo de dados de **zona. identificador** alternativo.</span><span class="sxs-lookup"><span data-stu-id="18007-230">You can use the `Add-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="18007-231">No entanto, não recomendamos isso como uma maneira de eliminar verificações de segurança que bloqueiam arquivos baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="18007-231">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="18007-232">Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18007-232">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="18007-233">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="18007-233">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="18007-234">-Value</span><span class="sxs-lookup"><span data-stu-id="18007-234">-Value</span></span>

<span data-ttu-id="18007-235">Especifica o conteúdo a ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="18007-235">Specifies the content to be added.</span></span> <span data-ttu-id="18007-236">Digite uma cadeia de caracteres entre aspas, como **esses dados são somente para uso interno** ou especifique um objeto que contenha conteúdo, como o objeto **DateTime** que `Get-Date` gera.</span><span class="sxs-lookup"><span data-stu-id="18007-236">Type a quoted string, such as **This data is for internal use only** , or specify an object that contains content, such as the **DateTime** object that `Get-Date` generates.</span></span>

<span data-ttu-id="18007-237">Você não pode especificar o conteúdo de um arquivo digitando seu caminho, pois o caminho é apenas uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="18007-237">You cannot specify the contents of a file by typing its path, because the path is just a string.</span></span>
<span data-ttu-id="18007-238">Você pode usar um `Get-Content` comando para obter o conteúdo e passá-lo para o parâmetro **Value** .</span><span class="sxs-lookup"><span data-stu-id="18007-238">You can use a `Get-Content` command to get the content and pass it to the **Value** parameter.</span></span>

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

### <span data-ttu-id="18007-239">-Confirm</span><span class="sxs-lookup"><span data-stu-id="18007-239">-Confirm</span></span>

<span data-ttu-id="18007-240">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18007-240">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="18007-241">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="18007-241">-WhatIf</span></span>

<span data-ttu-id="18007-242">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="18007-242">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="18007-243">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="18007-243">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="18007-244">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="18007-244">CommonParameters</span></span>

<span data-ttu-id="18007-245">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="18007-245">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="18007-246">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="18007-246">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="18007-247">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="18007-247">INPUTS</span></span>

### <span data-ttu-id="18007-248">System. Object, System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="18007-248">System.Object, System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="18007-249">Você pode canalizar valores, caminhos ou credenciais para `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="18007-249">You can pipe values, paths, or credentials to `Set-Content`.</span></span>

## <span data-ttu-id="18007-250">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="18007-250">OUTPUTS</span></span>

### <span data-ttu-id="18007-251">Nenhum ou System.String</span><span class="sxs-lookup"><span data-stu-id="18007-251">None or System.String</span></span>

<span data-ttu-id="18007-252">Quando você usa o parâmetro **PassThru** , o `Add-Content` gera um objeto **System. String** que representa o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="18007-252">When you use the **PassThru** parameter, `Add-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="18007-253">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="18007-253">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="18007-254">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="18007-254">NOTES</span></span>

- <span data-ttu-id="18007-255">Quando você canaliza um objeto para `Add-Content` , o objeto é convertido em uma cadeia de caracteres antes de ser adicionado ao item.</span><span class="sxs-lookup"><span data-stu-id="18007-255">When you pipe an object to `Add-Content`, the object is converted to a string before it is added to the item.</span></span> <span data-ttu-id="18007-256">O tipo de objeto determina o formato de cadeia de caracteres, mas o formato pode ser diferente da exibição padrão do objeto.</span><span class="sxs-lookup"><span data-stu-id="18007-256">The object type determines the string format, but the format might be different than the default display of the object.</span></span> <span data-ttu-id="18007-257">Para controlar o formato da cadeia de caracteres, use os parâmetros de formatação do cmdlet de envio.</span><span class="sxs-lookup"><span data-stu-id="18007-257">To control the string format, use the formatting parameters of the sending cmdlet.</span></span>
- <span data-ttu-id="18007-258">Você também pode consultar `Add-Content` por seu alias interno, `ac` .</span><span class="sxs-lookup"><span data-stu-id="18007-258">You can also refer to `Add-Content` by its built-in alias, `ac`.</span></span> <span data-ttu-id="18007-259">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="18007-259">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="18007-260">O `Add-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="18007-260">The `Add-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="18007-261">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="18007-261">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="18007-262">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="18007-262">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="18007-263">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="18007-263">RELATED LINKS</span></span>

[<span data-ttu-id="18007-264">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="18007-264">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="18007-265">about_Providers</span><span class="sxs-lookup"><span data-stu-id="18007-265">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="18007-266">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="18007-266">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="18007-267">Get-Content</span><span class="sxs-lookup"><span data-stu-id="18007-267">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="18007-268">Get-Item</span><span class="sxs-lookup"><span data-stu-id="18007-268">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="18007-269">New-Item</span><span class="sxs-lookup"><span data-stu-id="18007-269">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="18007-270">Set-Content</span><span class="sxs-lookup"><span data-stu-id="18007-270">Set-Content</span></span>](Set-Content.md)
