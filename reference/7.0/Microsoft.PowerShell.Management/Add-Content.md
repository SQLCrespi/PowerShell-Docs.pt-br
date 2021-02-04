---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: e31e792a60cd09d35ecc67263f107584857efe7d
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97693038"
---
# <span data-ttu-id="8292f-102">Add-Content</span><span class="sxs-lookup"><span data-stu-id="8292f-102">Add-Content</span></span>

## <span data-ttu-id="8292f-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8292f-103">SYNOPSIS</span></span>
<span data-ttu-id="8292f-104">Adiciona conteúdo aos itens especificados, como a adição de palavras a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="8292f-104">Adds content to the specified items, such as adding words to a file.</span></span>

## <span data-ttu-id="8292f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8292f-105">SYNTAX</span></span>

### <span data-ttu-id="8292f-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="8292f-106">Path (Default)</span></span>

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="8292f-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8292f-107">LiteralPath</span></span>

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="8292f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8292f-108">DESCRIPTION</span></span>

<span data-ttu-id="8292f-109">O `Add-Content` cmdlet acrescenta o conteúdo a um item ou arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="8292f-109">The `Add-Content` cmdlet appends content to a specified item or file.</span></span> <span data-ttu-id="8292f-110">Você pode especificar o conteúdo, digitando-o no comando ou especificando um objeto que contém o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8292f-110">You can specify the content by typing the content in the command or by specifying an object that contains the content.</span></span>

<span data-ttu-id="8292f-111">Se você precisar criar arquivos ou diretórios para os exemplos a seguir, consulte [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="8292f-111">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="8292f-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8292f-112">EXAMPLES</span></span>

### <span data-ttu-id="8292f-113">Exemplo 1: adicionar uma cadeia de caracteres a todos os arquivos de texto com uma exceção</span><span class="sxs-lookup"><span data-stu-id="8292f-113">Example 1: Add a string to all text files with an exception</span></span>

<span data-ttu-id="8292f-114">Este exemplo acrescenta um valor a arquivos de texto no diretório atual, mas exclui arquivos com base no nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="8292f-114">This example appends a value to text files in the current directory but excludes files based on their file name.</span></span>

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

<span data-ttu-id="8292f-115">O parâmetro **path** especifica todos os `.txt` arquivos no diretório atual, mas o parâmetro **Exclude** ignora os nomes de arquivo que correspondem ao padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="8292f-115">The **Path** parameter specifies all `.txt` files in the current directory, but the **Exclude** parameter ignores file names that match the specified pattern.</span></span> <span data-ttu-id="8292f-116">O parâmetro **Value** especifica a cadeia de caracteres de texto que é gravada nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="8292f-116">The **Value** parameter specifies the text string that is written to the files.</span></span>

### <span data-ttu-id="8292f-117">Exemplo 2: adicionar uma data ao final dos arquivos especificados</span><span class="sxs-lookup"><span data-stu-id="8292f-117">Example 2: Add a date to the end of the specified files</span></span>

<span data-ttu-id="8292f-118">Este exemplo acrescenta a data a arquivos no diretório atual e exibe a data no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8292f-118">This example appends the date to files in the current directory and displays the date in the PowerShell console.</span></span>

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

```Output
Tuesday, May 14, 2019 8:24:27 AM
Tuesday, May 14, 2019 8:24:27 AM
5/14/2019 8:24:27 AM
```

<span data-ttu-id="8292f-119">O `Add-Content` cmdlet cria dois novos arquivos no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="8292f-119">The `Add-Content` cmdlet creates two new files in the current directory.</span></span> <span data-ttu-id="8292f-120">O parâmetro **Value** contém a saída do `Get-Date` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8292f-120">The **Value** parameter contains the output of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="8292f-121">O parâmetro **PassThru** gera o conteúdo adicionado ao pipeline.</span><span class="sxs-lookup"><span data-stu-id="8292f-121">The **PassThru** parameter outputs the added contents to the pipeline.</span></span>
<span data-ttu-id="8292f-122">Como não há nenhum outro cmdlet para receber a saída, ele é exibido no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8292f-122">Because there is no other cmdlet to receive the output, it is displayed in the PowerShell console.</span></span>
<span data-ttu-id="8292f-123">O `Get-Content` cmdlet exibe o arquivo atualizado, `DateTimeFile1.log` .</span><span class="sxs-lookup"><span data-stu-id="8292f-123">The `Get-Content` cmdlet displays the updated file, `DateTimeFile1.log`.</span></span>

### <span data-ttu-id="8292f-124">Exemplo 3: Adicionar o conteúdo de um arquivo especificado a outro arquivo</span><span class="sxs-lookup"><span data-stu-id="8292f-124">Example 3: Add the contents of a specified file to another file</span></span>

<span data-ttu-id="8292f-125">Este exemplo obtém o conteúdo de um arquivo e armazena o conteúdo em uma variável.</span><span class="sxs-lookup"><span data-stu-id="8292f-125">This example gets the content from a file and stores the content in a variable.</span></span> <span data-ttu-id="8292f-126">A variável é usada para acrescentar o conteúdo a outro arquivo.</span><span class="sxs-lookup"><span data-stu-id="8292f-126">The variable is used to append the content into another file.</span></span>

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

- <span data-ttu-id="8292f-127">O `Get-Content` cmdlet obtém o conteúdo de `CopyFromFile.txt` e armazena o conteúdo na `$From` variável.</span><span class="sxs-lookup"><span data-stu-id="8292f-127">The `Get-Content` cmdlet gets the contents of `CopyFromFile.txt` and stores the contents in the `$From` variable.</span></span>
- <span data-ttu-id="8292f-128">O `Add-Content` cmdlet atualiza o `CopyToFile.txt` arquivo usando o conteúdo da `$From` variável.</span><span class="sxs-lookup"><span data-stu-id="8292f-128">The `Add-Content` cmdlet updates the `CopyToFile.txt` file using the contents of the `$From` variable.</span></span>
- <span data-ttu-id="8292f-129">O `Get-Content` cmdlet exibe CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="8292f-129">The `Get-Content` cmdlet displays CopyToFile.txt.</span></span>

### <span data-ttu-id="8292f-130">Exemplo 4: Adicionar o conteúdo de um arquivo especificado a outro arquivo usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="8292f-130">Example 4: Add the contents of a specified file to another file using the pipeline</span></span>

<span data-ttu-id="8292f-131">Este exemplo obtém o conteúdo de um arquivo e o canaliza para o `Add-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8292f-131">This example gets the content from a file and pipes it to the `Add-Content` cmdlet.</span></span>

```powershell
Get-Content -Path .\CopyFromFile.txt | Add-Content -Path .\CopyToFile.txt
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="8292f-132">O `Get-Content` cmdlet obtém o conteúdo de `CopyFromFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="8292f-132">The `Get-Content` cmdlet gets the contents of `CopyFromFile.txt`.</span></span> <span data-ttu-id="8292f-133">Os resultados são canalizados para o `Add-Content` cmdlet, que atualiza o `CopyToFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="8292f-133">The results are piped to the `Add-Content` cmdlet, which updates the `CopyToFile.txt`.</span></span>
<span data-ttu-id="8292f-134">O último `Get-Content` cmdlet é exibido `CopyToFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="8292f-134">The last `Get-Content` cmdlet displays `CopyToFile.txt`.</span></span>

### <span data-ttu-id="8292f-135">Exemplo 5: criar um novo arquivo e copiar o conteúdo</span><span class="sxs-lookup"><span data-stu-id="8292f-135">Example 5: Create a new file and copy content</span></span>

<span data-ttu-id="8292f-136">Este exemplo cria um novo arquivo e copia o conteúdo de um arquivo existente no novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="8292f-136">This example creates a new file and copies an existing file's content into the new file.</span></span>

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

- <span data-ttu-id="8292f-137">O `Add-Content` cmdlet usa os parâmetros **Path** e **Value** para criar um novo arquivo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="8292f-137">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create a new file in the current directory.</span></span>
- <span data-ttu-id="8292f-138">O `Get-Content` cmdlet obtém o conteúdo de um arquivo existente `CopyFromFile.txt` e o passa para o parâmetro **Value** .</span><span class="sxs-lookup"><span data-stu-id="8292f-138">The `Get-Content` cmdlet gets the contents of an existing file, `CopyFromFile.txt` and passes it to the **Value** parameter.</span></span> <span data-ttu-id="8292f-139">Os parênteses em volta do `Get-Content` cmdlet garantem que o comando seja concluído antes do `Add-Content` início do comando.</span><span class="sxs-lookup"><span data-stu-id="8292f-139">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span>
- <span data-ttu-id="8292f-140">O `Get-Content` cmdlet exibe o conteúdo do novo arquivo, `NewFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="8292f-140">The `Get-Content` cmdlet displays the contents of the new file, `NewFile.txt`.</span></span>

### <span data-ttu-id="8292f-141">Exemplo 6: adicionar conteúdo a um arquivo somente leitura</span><span class="sxs-lookup"><span data-stu-id="8292f-141">Example 6: Add content to a read-only file</span></span>

<span data-ttu-id="8292f-142">Esse comando adiciona um valor ao arquivo, mesmo que o atributo de arquivo **IsReadOnly** esteja definido como **true**.</span><span class="sxs-lookup"><span data-stu-id="8292f-142">This command adds a value to the file even if the **IsReadOnly** file attribute is set to **True**.</span></span>
<span data-ttu-id="8292f-143">As etapas para criar um arquivo somente leitura são incluídas no exemplo.</span><span class="sxs-lookup"><span data-stu-id="8292f-143">The steps to create a read-only file are included in the example.</span></span>

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

- <span data-ttu-id="8292f-144">O `New-Item` cmdlet usa os parâmetros **Path** e **ItemType** para criar o arquivo `IsReadOnlyTextFile.txt` no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="8292f-144">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the file `IsReadOnlyTextFile.txt` in the current directory.</span></span>
- <span data-ttu-id="8292f-145">O `Set-ItemProperty` cmdlet usa os parâmetros **Name** e **Value** para alterar a propriedade **IsReadOnly** do arquivo para true.</span><span class="sxs-lookup"><span data-stu-id="8292f-145">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to True.</span></span>
- <span data-ttu-id="8292f-146">O `Get-ChildItem` cmdlet mostra que o arquivo está vazio (0) e tem o atributo somente leitura ( `r` ).</span><span class="sxs-lookup"><span data-stu-id="8292f-146">The `Get-ChildItem` cmdlet shows the file is empty (0) and has the read-only attribute (`r`).</span></span>
- <span data-ttu-id="8292f-147">O `Add-Content` cmdlet usa o parâmetro **Path** para especificar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="8292f-147">The `Add-Content` cmdlet uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="8292f-148">O parâmetro **Value** inclui a cadeia de caracteres de texto a ser acrescentada ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="8292f-148">The **Value** parameter includes the text string to append to the file.</span></span> <span data-ttu-id="8292f-149">O parâmetro **Force** grava o texto no arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="8292f-149">The **Force** parameter writes the text to the read-only file.</span></span>
- <span data-ttu-id="8292f-150">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="8292f-150">The `Get-Content` cmdlet uses the **Path** parameter to display the file's contents.</span></span>

<span data-ttu-id="8292f-151">Para remover o atributo somente leitura, use o `Set-ItemProperty` comando com o parâmetro de **valor** definido como `False` .</span><span class="sxs-lookup"><span data-stu-id="8292f-151">To remove the read-only attribute, use the `Set-ItemProperty` command with the **Value** parameter set to `False`.</span></span>

### <span data-ttu-id="8292f-152">Exemplo 7: usar filtros com Add-Content</span><span class="sxs-lookup"><span data-stu-id="8292f-152">Example 7: Use Filters with Add-Content</span></span>

<span data-ttu-id="8292f-153">Você pode especificar um filtro para o `Add-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8292f-153">You can specify a filter to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="8292f-154">Ao usar filtros para qualificar o parâmetro de **caminho** , você precisa incluir um asterisco à direita ( `*` ) para indicar o conteúdo do caminho.</span><span class="sxs-lookup"><span data-stu-id="8292f-154">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="8292f-155">O comando a seguir adiciona a palavra "Done" do conteúdo de todos os `*.txt` arquivos no `C:\Temp` diretório.</span><span class="sxs-lookup"><span data-stu-id="8292f-155">The following command adds the word "Done" the content of all `*.txt` files in the `C:\Temp` directory.</span></span>

```powershell
Add-Content -Path C:\Temp\* -Filter *.txt -Value "Done"
```

## <span data-ttu-id="8292f-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8292f-156">PARAMETERS</span></span>

### <span data-ttu-id="8292f-157">-AsByteStream</span><span class="sxs-lookup"><span data-stu-id="8292f-157">-AsByteStream</span></span>

<span data-ttu-id="8292f-158">Especifica que o conteúdo deve ser lido como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="8292f-158">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="8292f-159">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="8292f-159">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="8292f-160">Um aviso ocorre quando você usa o parâmetro **AsByteStream** com o parâmetro **Encoding** .</span><span class="sxs-lookup"><span data-stu-id="8292f-160">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="8292f-161">O parâmetro **AsByteStream** ignora qualquer codificação e a saída é retornada como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="8292f-161">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="8292f-162">-Credential</span><span class="sxs-lookup"><span data-stu-id="8292f-162">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="8292f-163">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8292f-163">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="8292f-164">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="8292f-164">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="8292f-165">-Codificação</span><span class="sxs-lookup"><span data-stu-id="8292f-165">-Encoding</span></span>

<span data-ttu-id="8292f-166">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="8292f-166">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="8292f-167">O valor padrão é `utf8BOM`.</span><span class="sxs-lookup"><span data-stu-id="8292f-167">The default value is `utf8BOM`.</span></span>

<span data-ttu-id="8292f-168">A codificação é um parâmetro dinâmico que o provedor FileSystem adiciona ao `Add-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8292f-168">Encoding is a dynamic parameter that the FileSystem provider adds to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="8292f-169">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8292f-169">This parameter works only in file system drives.</span></span>

<span data-ttu-id="8292f-170">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="8292f-170">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="8292f-171">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="8292f-171">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="8292f-172">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="8292f-172">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="8292f-173">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="8292f-173">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="8292f-174">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="8292f-174">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="8292f-175">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="8292f-175">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="8292f-176">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="8292f-176">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="8292f-177">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="8292f-177">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="8292f-178">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="8292f-178">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="8292f-179">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="8292f-179">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="8292f-180">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="8292f-180">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="8292f-181">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="8292f-181">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

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

### <span data-ttu-id="8292f-182">-Excluir</span><span class="sxs-lookup"><span data-stu-id="8292f-182">-Exclude</span></span>

<span data-ttu-id="8292f-183">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="8292f-183">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="8292f-184">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="8292f-184">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="8292f-185">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="8292f-185">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="8292f-186">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="8292f-186">Wildcard characters are permitted.</span></span> <span data-ttu-id="8292f-187">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="8292f-187">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="8292f-188">-Filter</span><span class="sxs-lookup"><span data-stu-id="8292f-188">-Filter</span></span>

<span data-ttu-id="8292f-189">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="8292f-189">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="8292f-190">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="8292f-190">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="8292f-191">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="8292f-191">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="8292f-192">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="8292f-192">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="8292f-193">-Force</span><span class="sxs-lookup"><span data-stu-id="8292f-193">-Force</span></span>

<span data-ttu-id="8292f-194">Substitui o atributo somente leitura, permitindo adicionar conteúdo a um arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="8292f-194">Overrides the read-only attribute, allowing you to add content to a read-only file.</span></span> <span data-ttu-id="8292f-195">Por exemplo, o **Force** substituirá o atributo somente leitura ou criar diretórios para concluir um caminho de arquivo, mas não tentará alterar permissões de arquivo.</span><span class="sxs-lookup"><span data-stu-id="8292f-195">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="8292f-196">-Incluir</span><span class="sxs-lookup"><span data-stu-id="8292f-196">-Include</span></span>

<span data-ttu-id="8292f-197">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="8292f-197">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="8292f-198">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="8292f-198">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="8292f-199">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="8292f-199">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="8292f-200">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="8292f-200">Wildcard characters are permitted.</span></span> <span data-ttu-id="8292f-201">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="8292f-201">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="8292f-202">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8292f-202">-LiteralPath</span></span>

<span data-ttu-id="8292f-203">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="8292f-203">Specifies a path to one or more locations.</span></span> <span data-ttu-id="8292f-204">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="8292f-204">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="8292f-205">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="8292f-205">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="8292f-206">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="8292f-206">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="8292f-207">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="8292f-207">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="8292f-208">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="8292f-208">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="8292f-209">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="8292f-209">-NoNewline</span></span>

<span data-ttu-id="8292f-210">Indica que esse cmdlet não adiciona uma nova linha ou retorno de carro ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8292f-210">Indicates that this cmdlet does not add a new line or carriage return to the content.</span></span>

<span data-ttu-id="8292f-211">As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída.</span><span class="sxs-lookup"><span data-stu-id="8292f-211">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="8292f-212">Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="8292f-212">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="8292f-213">Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="8292f-213">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="8292f-214">-PassThru</span><span class="sxs-lookup"><span data-stu-id="8292f-214">-PassThru</span></span>

<span data-ttu-id="8292f-215">Retorna um objeto que representa o conteúdo adicionado.</span><span class="sxs-lookup"><span data-stu-id="8292f-215">Returns an object representing the added content.</span></span> <span data-ttu-id="8292f-216">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="8292f-216">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="8292f-217">-Path</span><span class="sxs-lookup"><span data-stu-id="8292f-217">-Path</span></span>

<span data-ttu-id="8292f-218">Especifica o caminho para os itens que recebem conteúdo adicional.</span><span class="sxs-lookup"><span data-stu-id="8292f-218">Specifies the path to the items that receive the additional content.</span></span>
<span data-ttu-id="8292f-219">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="8292f-219">Wildcard characters are permitted.</span></span>
<span data-ttu-id="8292f-220">Os caminhos devem ser caminhos para itens, não para contêineres.</span><span class="sxs-lookup"><span data-stu-id="8292f-220">The paths must be paths to items, not to containers.</span></span>
<span data-ttu-id="8292f-221">Por exemplo, você deve especificar um caminho para um ou mais arquivos, não um caminho para um diretório.</span><span class="sxs-lookup"><span data-stu-id="8292f-221">For example, you must specify a path to one or more files, not a path to a directory.</span></span>
<span data-ttu-id="8292f-222">Se você especificar vários caminhos, use vírgulas para separá-los.</span><span class="sxs-lookup"><span data-stu-id="8292f-222">If you specify multiple paths, use commas to separate the paths.</span></span>

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

### <span data-ttu-id="8292f-223">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="8292f-223">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="8292f-224">Esse parâmetro só está disponível no Windows.</span><span class="sxs-lookup"><span data-stu-id="8292f-224">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="8292f-225">Especifica um fluxo de dados alternativo para o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8292f-225">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="8292f-226">Se o fluxo não existir, esse cmdlet o criará.</span><span class="sxs-lookup"><span data-stu-id="8292f-226">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="8292f-227">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="8292f-227">Wildcard characters are not supported.</span></span>

<span data-ttu-id="8292f-228">**Stream** é um parâmetro dinâmico que o provedor FileSystem adiciona `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="8292f-228">**Stream** is a dynamic parameter that the FileSystem provider adds to `Add-Content`.</span></span> <span data-ttu-id="8292f-229">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8292f-229">This parameter works only in file system drives.</span></span>

<span data-ttu-id="8292f-230">Você pode usar o `Add-Content` cmdlet para alterar o conteúdo de qualquer fluxo de dados alternativo, como `Zone.Identifier` .</span><span class="sxs-lookup"><span data-stu-id="8292f-230">You can use the `Add-Content` cmdlet to change the content of any alternate data stream, such as `Zone.Identifier`.</span></span> <span data-ttu-id="8292f-231">No entanto, não recomendamos isso como uma maneira de eliminar verificações de segurança que bloqueiam arquivos baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="8292f-231">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="8292f-232">Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8292f-232">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="8292f-233">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="8292f-233">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8292f-234">-Value</span><span class="sxs-lookup"><span data-stu-id="8292f-234">-Value</span></span>

<span data-ttu-id="8292f-235">Especifica o conteúdo a ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="8292f-235">Specifies the content to be added.</span></span> <span data-ttu-id="8292f-236">Digite uma cadeia de caracteres entre aspas, como **esses dados são somente para uso interno** ou especifique um objeto que contenha conteúdo, como o objeto **DateTime** que `Get-Date` gera.</span><span class="sxs-lookup"><span data-stu-id="8292f-236">Type a quoted string, such as **This data is for internal use only**, or specify an object that contains content, such as the **DateTime** object that `Get-Date` generates.</span></span>

<span data-ttu-id="8292f-237">Você não pode especificar o conteúdo de um arquivo digitando seu caminho, pois o caminho é apenas uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8292f-237">You cannot specify the contents of a file by typing its path, because the path is just a string.</span></span>
<span data-ttu-id="8292f-238">Você pode usar um `Get-Content` comando para obter o conteúdo e passá-lo para o parâmetro **Value** .</span><span class="sxs-lookup"><span data-stu-id="8292f-238">You can use a `Get-Content` command to get the content and pass it to the **Value** parameter.</span></span>

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

### <span data-ttu-id="8292f-239">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8292f-239">-Confirm</span></span>

<span data-ttu-id="8292f-240">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8292f-240">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8292f-241">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8292f-241">-WhatIf</span></span>

<span data-ttu-id="8292f-242">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="8292f-242">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="8292f-243">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="8292f-243">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8292f-244">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8292f-244">CommonParameters</span></span>

<span data-ttu-id="8292f-245">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8292f-245">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8292f-246">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8292f-246">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8292f-247">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8292f-247">INPUTS</span></span>

### <span data-ttu-id="8292f-248">System. Object, System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="8292f-248">System.Object, System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="8292f-249">Você pode canalizar valores, caminhos ou credenciais para `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="8292f-249">You can pipe values, paths, or credentials to `Set-Content`.</span></span>

## <span data-ttu-id="8292f-250">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8292f-250">OUTPUTS</span></span>

### <span data-ttu-id="8292f-251">Nenhum ou System.String</span><span class="sxs-lookup"><span data-stu-id="8292f-251">None or System.String</span></span>

<span data-ttu-id="8292f-252">Quando você usa o parâmetro **PassThru** , o `Add-Content` gera um objeto **System. String** que representa o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8292f-252">When you use the **PassThru** parameter, `Add-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="8292f-253">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="8292f-253">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="8292f-254">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8292f-254">NOTES</span></span>

- <span data-ttu-id="8292f-255">Quando você canaliza um objeto para `Add-Content` , o objeto é convertido em uma cadeia de caracteres antes de ser adicionado ao item.</span><span class="sxs-lookup"><span data-stu-id="8292f-255">When you pipe an object to `Add-Content`, the object is converted to a string before it is added to the item.</span></span> <span data-ttu-id="8292f-256">O tipo de objeto determina o formato de cadeia de caracteres, mas o formato pode ser diferente da exibição padrão do objeto.</span><span class="sxs-lookup"><span data-stu-id="8292f-256">The object type determines the string format, but the format might be different than the default display of the object.</span></span> <span data-ttu-id="8292f-257">Para controlar o formato da cadeia de caracteres, use os parâmetros de formatação do cmdlet de envio.</span><span class="sxs-lookup"><span data-stu-id="8292f-257">To control the string format, use the formatting parameters of the sending cmdlet.</span></span>
- <span data-ttu-id="8292f-258">Você também pode consultar `Add-Content` por seu alias interno, `ac` .</span><span class="sxs-lookup"><span data-stu-id="8292f-258">You can also refer to `Add-Content` by its built-in alias, `ac`.</span></span> <span data-ttu-id="8292f-259">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="8292f-259">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="8292f-260">O `Add-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="8292f-260">The `Add-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="8292f-261">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="8292f-261">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="8292f-262">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="8292f-262">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="8292f-263">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8292f-263">RELATED LINKS</span></span>

[<span data-ttu-id="8292f-264">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="8292f-264">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="8292f-265">about_Providers</span><span class="sxs-lookup"><span data-stu-id="8292f-265">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="8292f-266">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="8292f-266">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="8292f-267">Get-Content</span><span class="sxs-lookup"><span data-stu-id="8292f-267">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="8292f-268">Get-Item</span><span class="sxs-lookup"><span data-stu-id="8292f-268">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="8292f-269">New-Item</span><span class="sxs-lookup"><span data-stu-id="8292f-269">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="8292f-270">Set-Content</span><span class="sxs-lookup"><span data-stu-id="8292f-270">Set-Content</span></span>](Set-Content.md)
