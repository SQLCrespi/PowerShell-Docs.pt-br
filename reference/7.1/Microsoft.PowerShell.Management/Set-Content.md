---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: bb9345470aa58dac7c14e1443c0fe4c12e7563a6
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "93195260"
---
# <span data-ttu-id="88d39-103">Set-Content</span><span class="sxs-lookup"><span data-stu-id="88d39-103">Set-Content</span></span>

## <span data-ttu-id="88d39-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="88d39-104">SYNOPSIS</span></span>
<span data-ttu-id="88d39-105">Grava novo conteúdo ou substitui o conteúdo existente em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="88d39-105">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="88d39-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="88d39-106">SYNTAX</span></span>

### <span data-ttu-id="88d39-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="88d39-107">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="88d39-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="88d39-108">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="88d39-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="88d39-109">DESCRIPTION</span></span>

<span data-ttu-id="88d39-110">`Set-Content` é um cmdlet de processamento de cadeia de caracteres que grava novo conteúdo ou substitui o conteúdo em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="88d39-110">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="88d39-111">`Set-Content` Substitui o conteúdo existente e difere do `Add-Content` cmdlet que acrescenta o conteúdo a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="88d39-111">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="88d39-112">Para enviar conteúdo para `Set-Content` você pode usar o parâmetro **Value** na linha de comando ou enviar conteúdo por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="88d39-112">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="88d39-113">Se você precisar criar arquivos ou diretórios para os exemplos a seguir, consulte [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="88d39-113">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="88d39-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="88d39-114">EXAMPLES</span></span>

### <span data-ttu-id="88d39-115">Exemplo 1: substituir o conteúdo de vários arquivos em um diretório</span><span class="sxs-lookup"><span data-stu-id="88d39-115">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="88d39-116">Este exemplo substitui o conteúdo de vários arquivos no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="88d39-116">This example replaces the content for multiple files in the current directory.</span></span>

```powershell
Get-ChildItem -Path .\Test*.txt
```

```Output
Test1.txt
Test2.txt
Test3.txt
```

```powershell
Set-Content -Path .\Test*.txt -Value 'Hello, World'
Get-Content -Path .\Test*.txt
```

```Output
Hello, World
Hello, World
Hello, World
```

<span data-ttu-id="88d39-117">O `Get-ChildItem` cmdlet usa o parâmetro **Path** para listar arquivos **. txt** que começam com `Test*` no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="88d39-117">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="88d39-118">O `Set-Content` cmdlet usa o parâmetro **Path** para especificar os `Test*.txt` arquivos.</span><span class="sxs-lookup"><span data-stu-id="88d39-118">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="88d39-119">O parâmetro **Value** fornece a cadeia de caracteres de texto **Olá, mundo** que substitui o conteúdo existente em cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="88d39-119">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="88d39-120">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar os `Test*.txt` arquivos e exibe o conteúdo de cada arquivo no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88d39-120">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="88d39-121">Exemplo 2: criar um novo arquivo e gravar o conteúdo</span><span class="sxs-lookup"><span data-stu-id="88d39-121">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="88d39-122">Este exemplo cria um novo arquivo e grava a data e hora atuais no arquivo.</span><span class="sxs-lookup"><span data-stu-id="88d39-122">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="88d39-123">`Set-Content` usa os parâmetros **Path** e **Value** para criar um novo arquivo chamado **DateTime.txt** no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="88d39-123">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="88d39-124">O parâmetro **Value** usa `Get-Date` para obter a data e a hora atuais.</span><span class="sxs-lookup"><span data-stu-id="88d39-124">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="88d39-125">`Set-Content` grava o objeto **DateTime** no arquivo como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="88d39-125">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="88d39-126">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o conteúdo de **DateTime.txt** no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88d39-126">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="88d39-127">Exemplo 3: substituir o texto em um arquivo</span><span class="sxs-lookup"><span data-stu-id="88d39-127">Example 3: Replace text in a file</span></span>

<span data-ttu-id="88d39-128">Esse comando substitui todas as instâncias do Word em um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="88d39-128">This command replaces all instances of word within an existing file.</span></span>

```powershell
Get-Content -Path .\Notice.txt
```

```Output
Warning
Replace Warning with a new word.
The word Warning was replaced.
```

```powershell
(Get-Content -Path .\Notice.txt) |
    ForEach-Object {$_ -Replace 'Warning', 'Caution'} |
        Set-Content -Path .\Notice.txt
Get-Content -Path .\Notice.txt
```

```Output
Caution
Replace Caution with a new word.
The word Caution was replaced.
```

<span data-ttu-id="88d39-129">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o arquivo de **Notice.txt** no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="88d39-129">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="88d39-130">O `Get-Content` comando é encapsulado com parênteses para que o comando seja concluído antes de ser enviado ao pipeline.</span><span class="sxs-lookup"><span data-stu-id="88d39-130">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="88d39-131">O conteúdo do arquivo de **Notice.txt** é enviado ao pipeline para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="88d39-131">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="88d39-132">`ForEach-Object` usa a variável automática `$_` e substitui cada ocorrência de **Warning** por **cuidado** .</span><span class="sxs-lookup"><span data-stu-id="88d39-132">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution** .</span></span> <span data-ttu-id="88d39-133">Os objetos são enviados para o pipeline para o `Set-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="88d39-133">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="88d39-134">`Set-Content` usa o parâmetro **path** para especificar o arquivo de **Notice.txt** e grava o conteúdo atualizado no arquivo.</span><span class="sxs-lookup"><span data-stu-id="88d39-134">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="88d39-135">O último `Get-Content` cmdlet exibe o conteúdo do arquivo atualizado no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88d39-135">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="88d39-136">Exemplo 4: usar filtros com Set-Content</span><span class="sxs-lookup"><span data-stu-id="88d39-136">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="88d39-137">Você pode especificar um filtro para o `Set-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="88d39-137">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="88d39-138">Ao usar filtros para qualificar o parâmetro de **caminho** , você precisa incluir um asterisco à direita ( `*` ) para indicar o conteúdo do caminho.</span><span class="sxs-lookup"><span data-stu-id="88d39-138">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="88d39-139">O comando a seguir define o conteúdo todos os `*.txt` arquivos no `C:\Temp` diretório para o **valor** vazio.</span><span class="sxs-lookup"><span data-stu-id="88d39-139">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="88d39-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="88d39-140">PARAMETERS</span></span>

### <span data-ttu-id="88d39-141">-AsByteStream</span><span class="sxs-lookup"><span data-stu-id="88d39-141">-AsByteStream</span></span>

<span data-ttu-id="88d39-142">Especifica que o conteúdo deve ser lido como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="88d39-142">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="88d39-143">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="88d39-143">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="88d39-144">Um aviso ocorre quando você usa o parâmetro **AsByteStream** com o parâmetro **Encoding** .</span><span class="sxs-lookup"><span data-stu-id="88d39-144">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="88d39-145">O parâmetro **AsByteStream** ignora qualquer codificação e a saída é retornada como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="88d39-145">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="88d39-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="88d39-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="88d39-147">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88d39-147">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="88d39-148">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="88d39-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="88d39-149">-Codificação</span><span class="sxs-lookup"><span data-stu-id="88d39-149">-Encoding</span></span>

<span data-ttu-id="88d39-150">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="88d39-150">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="88d39-151">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="88d39-151">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="88d39-152">A codificação é um parâmetro dinâmico que o provedor FileSystem adiciona `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="88d39-152">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="88d39-153">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="88d39-153">This parameter works only in file system drives.</span></span>

<span data-ttu-id="88d39-154">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="88d39-154">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="88d39-155">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="88d39-155">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="88d39-156">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="88d39-156">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="88d39-157">`bigendianutf32`: Codifica em formato UTF-32 usando a ordem de byte big-endian.</span><span class="sxs-lookup"><span data-stu-id="88d39-157">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="88d39-158">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="88d39-158">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="88d39-159">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="88d39-159">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="88d39-160">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="88d39-160">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="88d39-161">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="88d39-161">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="88d39-162">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="88d39-162">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="88d39-163">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="88d39-163">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="88d39-164">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="88d39-164">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="88d39-165">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="88d39-165">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="88d39-166">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="88d39-166">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="88d39-167">O **UTF-7** \* não é mais recomendado para uso.</span><span class="sxs-lookup"><span data-stu-id="88d39-167">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="88d39-168">No PowerShell 7,1, um aviso será gravado se você especificar `utf7` para o parâmetro de **codificação** .</span><span class="sxs-lookup"><span data-stu-id="88d39-168">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

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

### <span data-ttu-id="88d39-169">-Excluir</span><span class="sxs-lookup"><span data-stu-id="88d39-169">-Exclude</span></span>

<span data-ttu-id="88d39-170">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="88d39-170">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="88d39-171">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="88d39-171">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="88d39-172">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="88d39-172">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="88d39-173">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="88d39-173">Wildcard characters are permitted.</span></span> <span data-ttu-id="88d39-174">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="88d39-174">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="88d39-175">-Filter</span><span class="sxs-lookup"><span data-stu-id="88d39-175">-Filter</span></span>

<span data-ttu-id="88d39-176">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="88d39-176">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="88d39-177">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="88d39-177">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="88d39-178">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="88d39-178">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="88d39-179">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="88d39-179">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="88d39-180">-Force</span><span class="sxs-lookup"><span data-stu-id="88d39-180">-Force</span></span>

<span data-ttu-id="88d39-181">Força o cmdlet a definir o conteúdo de um arquivo, mesmo se o arquivo for somente leitura.</span><span class="sxs-lookup"><span data-stu-id="88d39-181">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="88d39-182">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="88d39-182">Implementation varies from provider to provider.</span></span> <span data-ttu-id="88d39-183">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="88d39-183">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="88d39-184">O parâmetro **Force** não substitui as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="88d39-184">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="88d39-185">-Incluir</span><span class="sxs-lookup"><span data-stu-id="88d39-185">-Include</span></span>

<span data-ttu-id="88d39-186">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="88d39-186">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="88d39-187">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="88d39-187">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="88d39-188">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="88d39-188">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="88d39-189">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="88d39-189">Wildcard characters are permitted.</span></span> <span data-ttu-id="88d39-190">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="88d39-190">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="88d39-191">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="88d39-191">-LiteralPath</span></span>

<span data-ttu-id="88d39-192">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="88d39-192">Specifies a path to one or more locations.</span></span> <span data-ttu-id="88d39-193">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="88d39-193">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="88d39-194">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="88d39-194">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="88d39-195">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="88d39-195">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="88d39-196">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="88d39-196">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="88d39-197">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="88d39-197">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="88d39-198">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="88d39-198">-NoNewline</span></span>

<span data-ttu-id="88d39-199">As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída.</span><span class="sxs-lookup"><span data-stu-id="88d39-199">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="88d39-200">Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="88d39-200">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="88d39-201">Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="88d39-201">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="88d39-202">-PassThru</span><span class="sxs-lookup"><span data-stu-id="88d39-202">-PassThru</span></span>

<span data-ttu-id="88d39-203">Retorna um objeto que representa o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="88d39-203">Returns an object that represents the content.</span></span> <span data-ttu-id="88d39-204">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="88d39-204">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="88d39-205">-Path</span><span class="sxs-lookup"><span data-stu-id="88d39-205">-Path</span></span>

<span data-ttu-id="88d39-206">Especifica o caminho do item que recebe o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="88d39-206">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="88d39-207">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="88d39-207">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="88d39-208">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="88d39-208">-Stream</span></span>

<span data-ttu-id="88d39-209">Especifica um fluxo de dados alternativo para o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="88d39-209">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="88d39-210">Se o fluxo não existir, esse cmdlet o criará.</span><span class="sxs-lookup"><span data-stu-id="88d39-210">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="88d39-211">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="88d39-211">Wildcard characters are not supported.</span></span>

<span data-ttu-id="88d39-212">**Stream** é um parâmetro dinâmico que o provedor **FileSystem** adiciona `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="88d39-212">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="88d39-213">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="88d39-213">This parameter works only in file system drives.</span></span>

<span data-ttu-id="88d39-214">Você pode usar o `Set-Content` cmdlet para alterar o conteúdo do fluxo de dados de **zona. identificador** alternativo.</span><span class="sxs-lookup"><span data-stu-id="88d39-214">You can use the `Set-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="88d39-215">No entanto, não recomendamos isso como uma maneira de eliminar verificações de segurança que bloqueiam arquivos baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="88d39-215">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="88d39-216">Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="88d39-216">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="88d39-217">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="88d39-217">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="88d39-218">-Value</span><span class="sxs-lookup"><span data-stu-id="88d39-218">-Value</span></span>

<span data-ttu-id="88d39-219">Especifica o novo conteúdo para o item.</span><span class="sxs-lookup"><span data-stu-id="88d39-219">Specifies the new content for the item.</span></span>

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

### <span data-ttu-id="88d39-220">-Confirm</span><span class="sxs-lookup"><span data-stu-id="88d39-220">-Confirm</span></span>

<span data-ttu-id="88d39-221">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="88d39-221">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="88d39-222">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="88d39-222">-WhatIf</span></span>

<span data-ttu-id="88d39-223">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="88d39-223">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="88d39-224">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="88d39-224">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="88d39-225">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="88d39-225">CommonParameters</span></span>

<span data-ttu-id="88d39-226">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="88d39-226">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span>
<span data-ttu-id="88d39-227">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="88d39-227">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="88d39-228">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="88d39-228">INPUTS</span></span>

### <span data-ttu-id="88d39-229">System.Object</span><span class="sxs-lookup"><span data-stu-id="88d39-229">System.Object</span></span>

<span data-ttu-id="88d39-230">É possível canalizar um objeto que contém o novo valor para o item para `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="88d39-230">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="88d39-231">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="88d39-231">OUTPUTS</span></span>

### <span data-ttu-id="88d39-232">Nenhum ou System.String</span><span class="sxs-lookup"><span data-stu-id="88d39-232">None or System.String</span></span>

<span data-ttu-id="88d39-233">Quando você usa o parâmetro **PassThru** , o `Set-Content` gera um objeto **System. String** que representa o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="88d39-233">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="88d39-234">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="88d39-234">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="88d39-235">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="88d39-235">NOTES</span></span>

- <span data-ttu-id="88d39-236">Você também pode consultar `Set-Content` por seu alias interno, `sc` .</span><span class="sxs-lookup"><span data-stu-id="88d39-236">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="88d39-237">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="88d39-237">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="88d39-238">`Set-Content` é projetado para processamento de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="88d39-238">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="88d39-239">Se você canaliza objetos que não são de cadeia de caracteres para `Set-Content` , ele converte o objeto em uma cadeia de caracteres antes de gravá-lo.</span><span class="sxs-lookup"><span data-stu-id="88d39-239">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="88d39-240">Para gravar objetos em arquivos, use `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="88d39-240">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="88d39-241">O `Set-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="88d39-241">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="88d39-242">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="88d39-242">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="88d39-243">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="88d39-243">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="88d39-244">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="88d39-244">RELATED LINKS</span></span>

[<span data-ttu-id="88d39-245">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="88d39-245">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="88d39-246">about_Automatic_Variables. MD</span><span class="sxs-lookup"><span data-stu-id="88d39-246">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="88d39-247">about_Providers</span><span class="sxs-lookup"><span data-stu-id="88d39-247">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="88d39-248">Add-Content</span><span class="sxs-lookup"><span data-stu-id="88d39-248">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="88d39-249">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="88d39-249">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="88d39-250">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="88d39-250">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="88d39-251">Get-Content</span><span class="sxs-lookup"><span data-stu-id="88d39-251">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="88d39-252">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="88d39-252">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="88d39-253">New-Item</span><span class="sxs-lookup"><span data-stu-id="88d39-253">New-Item</span></span>](New-Item.md)

