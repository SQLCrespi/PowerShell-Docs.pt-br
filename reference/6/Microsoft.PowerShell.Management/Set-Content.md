---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: 33ed166b4e467d5c1054c936414a6628370f69d8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193389"
---
# <span data-ttu-id="a07dd-103">Set-Content</span><span class="sxs-lookup"><span data-stu-id="a07dd-103">Set-Content</span></span>

## <span data-ttu-id="a07dd-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a07dd-104">SYNOPSIS</span></span>
<span data-ttu-id="a07dd-105">Grava novo conteúdo ou substitui o conteúdo existente em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a07dd-105">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="a07dd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a07dd-106">SYNTAX</span></span>

### <span data-ttu-id="a07dd-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="a07dd-107">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="a07dd-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a07dd-108">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="a07dd-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a07dd-109">DESCRIPTION</span></span>

<span data-ttu-id="a07dd-110">`Set-Content` é um cmdlet de processamento de cadeia de caracteres que grava novo conteúdo ou substitui o conteúdo em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a07dd-110">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="a07dd-111">`Set-Content` Substitui o conteúdo existente e difere do `Add-Content` cmdlet que acrescenta o conteúdo a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a07dd-111">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="a07dd-112">Para enviar conteúdo para `Set-Content` você pode usar o parâmetro **Value** na linha de comando ou enviar conteúdo por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="a07dd-112">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="a07dd-113">Se você precisar criar arquivos ou diretórios para os exemplos a seguir, consulte [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="a07dd-113">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="a07dd-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a07dd-114">EXAMPLES</span></span>

### <span data-ttu-id="a07dd-115">Exemplo 1: substituir o conteúdo de vários arquivos em um diretório</span><span class="sxs-lookup"><span data-stu-id="a07dd-115">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="a07dd-116">Este exemplo substitui o conteúdo de vários arquivos no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="a07dd-116">This example replaces the content for multiple files in the current directory.</span></span>

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

<span data-ttu-id="a07dd-117">O `Get-ChildItem` cmdlet usa o parâmetro **Path** para listar arquivos **. txt** que começam com `Test*` no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="a07dd-117">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="a07dd-118">O `Set-Content` cmdlet usa o parâmetro **Path** para especificar os `Test*.txt` arquivos.</span><span class="sxs-lookup"><span data-stu-id="a07dd-118">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="a07dd-119">O parâmetro **Value** fornece a cadeia de caracteres de texto **Olá, mundo** que substitui o conteúdo existente em cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="a07dd-119">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="a07dd-120">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar os `Test*.txt` arquivos e exibe o conteúdo de cada arquivo no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a07dd-120">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="a07dd-121">Exemplo 2: criar um novo arquivo e gravar o conteúdo</span><span class="sxs-lookup"><span data-stu-id="a07dd-121">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="a07dd-122">Este exemplo cria um novo arquivo e grava a data e hora atuais no arquivo.</span><span class="sxs-lookup"><span data-stu-id="a07dd-122">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="a07dd-123">`Set-Content` usa os parâmetros **Path** e **Value** para criar um novo arquivo chamado **DateTime.txt** no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="a07dd-123">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="a07dd-124">O parâmetro **Value** usa `Get-Date` para obter a data e a hora atuais.</span><span class="sxs-lookup"><span data-stu-id="a07dd-124">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="a07dd-125">`Set-Content` grava o objeto **DateTime** no arquivo como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a07dd-125">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="a07dd-126">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o conteúdo de **DateTime.txt** no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a07dd-126">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="a07dd-127">Exemplo 3: substituir o texto em um arquivo</span><span class="sxs-lookup"><span data-stu-id="a07dd-127">Example 3: Replace text in a file</span></span>

<span data-ttu-id="a07dd-128">Esse comando substitui todas as instâncias do Word em um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="a07dd-128">This command replaces all instances of word within an existing file.</span></span>

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

<span data-ttu-id="a07dd-129">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o arquivo de **Notice.txt** no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="a07dd-129">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="a07dd-130">O `Get-Content` comando é encapsulado com parênteses para que o comando seja concluído antes de ser enviado ao pipeline.</span><span class="sxs-lookup"><span data-stu-id="a07dd-130">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="a07dd-131">O conteúdo do arquivo de **Notice.txt** é enviado ao pipeline para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a07dd-131">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="a07dd-132">`ForEach-Object` usa a variável automática `$_` e substitui cada ocorrência de **Warning** por **cuidado** .</span><span class="sxs-lookup"><span data-stu-id="a07dd-132">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution** .</span></span> <span data-ttu-id="a07dd-133">Os objetos são enviados para o pipeline para o `Set-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a07dd-133">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="a07dd-134">`Set-Content` usa o parâmetro **path** para especificar o arquivo de **Notice.txt** e grava o conteúdo atualizado no arquivo.</span><span class="sxs-lookup"><span data-stu-id="a07dd-134">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="a07dd-135">O último `Get-Content` cmdlet exibe o conteúdo do arquivo atualizado no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a07dd-135">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="a07dd-136">Exemplo 4: usar filtros com Set-Content</span><span class="sxs-lookup"><span data-stu-id="a07dd-136">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="a07dd-137">Você pode especificar um filtro para o `Set-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a07dd-137">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="a07dd-138">Ao usar filtros para qualificar o parâmetro de **caminho** , você precisa incluir um asterisco à direita ( `*` ) para indicar o conteúdo do caminho.</span><span class="sxs-lookup"><span data-stu-id="a07dd-138">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="a07dd-139">O comando a seguir define o conteúdo todos os `*.txt` arquivos no `C:\Temp` diretório para o **valor** vazio.</span><span class="sxs-lookup"><span data-stu-id="a07dd-139">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="a07dd-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a07dd-140">PARAMETERS</span></span>

### <span data-ttu-id="a07dd-141">-AsByteStream</span><span class="sxs-lookup"><span data-stu-id="a07dd-141">-AsByteStream</span></span>

<span data-ttu-id="a07dd-142">Especifica que o conteúdo deve ser lido como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="a07dd-142">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="a07dd-143">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="a07dd-143">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="a07dd-144">Um aviso ocorre quando você usa o parâmetro **AsByteStream** com o parâmetro **Encoding** .</span><span class="sxs-lookup"><span data-stu-id="a07dd-144">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="a07dd-145">O parâmetro **AsByteStream** ignora qualquer codificação e a saída é retornada como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="a07dd-145">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="a07dd-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="a07dd-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="a07dd-147">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a07dd-147">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="a07dd-148">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="a07dd-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="a07dd-149">-Codificação</span><span class="sxs-lookup"><span data-stu-id="a07dd-149">-Encoding</span></span>

<span data-ttu-id="a07dd-150">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="a07dd-150">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="a07dd-151">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="a07dd-151">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="a07dd-152">A codificação é um parâmetro dinâmico que o provedor FileSystem adiciona `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="a07dd-152">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="a07dd-153">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a07dd-153">This parameter works only in file system drives.</span></span>

<span data-ttu-id="a07dd-154">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="a07dd-154">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="a07dd-155">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="a07dd-155">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="a07dd-156">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="a07dd-156">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="a07dd-157">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="a07dd-157">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="a07dd-158">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="a07dd-158">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="a07dd-159">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="a07dd-159">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="a07dd-160">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="a07dd-160">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="a07dd-161">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="a07dd-161">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="a07dd-162">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="a07dd-162">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="a07dd-163">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="a07dd-163">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="a07dd-164">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="a07dd-164">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="a07dd-165">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="a07dd-165">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

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

### <span data-ttu-id="a07dd-166">-Excluir</span><span class="sxs-lookup"><span data-stu-id="a07dd-166">-Exclude</span></span>

<span data-ttu-id="a07dd-167">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="a07dd-167">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="a07dd-168">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="a07dd-168">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a07dd-169">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="a07dd-169">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="a07dd-170">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a07dd-170">Wildcard characters are permitted.</span></span> <span data-ttu-id="a07dd-171">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="a07dd-171">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="a07dd-172">-Filter</span><span class="sxs-lookup"><span data-stu-id="a07dd-172">-Filter</span></span>

<span data-ttu-id="a07dd-173">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="a07dd-173">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="a07dd-174">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="a07dd-174">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="a07dd-175">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="a07dd-175">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="a07dd-176">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="a07dd-176">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="a07dd-177">-Force</span><span class="sxs-lookup"><span data-stu-id="a07dd-177">-Force</span></span>

<span data-ttu-id="a07dd-178">Força o cmdlet a definir o conteúdo de um arquivo, mesmo se o arquivo for somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a07dd-178">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="a07dd-179">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="a07dd-179">Implementation varies from provider to provider.</span></span> <span data-ttu-id="a07dd-180">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a07dd-180">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="a07dd-181">O parâmetro **Force** não substitui as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="a07dd-181">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="a07dd-182">-Incluir</span><span class="sxs-lookup"><span data-stu-id="a07dd-182">-Include</span></span>

<span data-ttu-id="a07dd-183">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="a07dd-183">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="a07dd-184">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="a07dd-184">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a07dd-185">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="a07dd-185">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="a07dd-186">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a07dd-186">Wildcard characters are permitted.</span></span> <span data-ttu-id="a07dd-187">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="a07dd-187">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="a07dd-188">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a07dd-188">-LiteralPath</span></span>

<span data-ttu-id="a07dd-189">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="a07dd-189">Specifies a path to one or more locations.</span></span> <span data-ttu-id="a07dd-190">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="a07dd-190">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="a07dd-191">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="a07dd-191">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="a07dd-192">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="a07dd-192">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a07dd-193">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="a07dd-193">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="a07dd-194">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="a07dd-194">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="a07dd-195">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="a07dd-195">-NoNewline</span></span>

<span data-ttu-id="a07dd-196">As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída.</span><span class="sxs-lookup"><span data-stu-id="a07dd-196">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="a07dd-197">Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="a07dd-197">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="a07dd-198">Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="a07dd-198">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="a07dd-199">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a07dd-199">-PassThru</span></span>

<span data-ttu-id="a07dd-200">Retorna um objeto que representa o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a07dd-200">Returns an object that represents the content.</span></span> <span data-ttu-id="a07dd-201">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="a07dd-201">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a07dd-202">-Path</span><span class="sxs-lookup"><span data-stu-id="a07dd-202">-Path</span></span>

<span data-ttu-id="a07dd-203">Especifica o caminho do item que recebe o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a07dd-203">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="a07dd-204">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a07dd-204">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a07dd-205">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="a07dd-205">-Stream</span></span>

<span data-ttu-id="a07dd-206">Especifica um fluxo de dados alternativo para o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a07dd-206">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="a07dd-207">Se o fluxo não existir, esse cmdlet o criará.</span><span class="sxs-lookup"><span data-stu-id="a07dd-207">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="a07dd-208">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="a07dd-208">Wildcard characters are not supported.</span></span>

<span data-ttu-id="a07dd-209">**Stream** é um parâmetro dinâmico que o provedor **FileSystem** adiciona `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="a07dd-209">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="a07dd-210">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a07dd-210">This parameter works only in file system drives.</span></span>

<span data-ttu-id="a07dd-211">Você pode usar o `Set-Content` cmdlet para alterar o conteúdo do fluxo de dados de **zona. identificador** alternativo.</span><span class="sxs-lookup"><span data-stu-id="a07dd-211">You can use the `Set-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="a07dd-212">No entanto, não recomendamos isso como uma maneira de eliminar verificações de segurança que bloqueiam arquivos baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="a07dd-212">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="a07dd-213">Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a07dd-213">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="a07dd-214">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="a07dd-214">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a07dd-215">-Value</span><span class="sxs-lookup"><span data-stu-id="a07dd-215">-Value</span></span>

<span data-ttu-id="a07dd-216">Especifica o novo conteúdo para o item.</span><span class="sxs-lookup"><span data-stu-id="a07dd-216">Specifies the new content for the item.</span></span>

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

### <span data-ttu-id="a07dd-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a07dd-217">-Confirm</span></span>

<span data-ttu-id="a07dd-218">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a07dd-218">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a07dd-219">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a07dd-219">-WhatIf</span></span>

<span data-ttu-id="a07dd-220">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="a07dd-220">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a07dd-221">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="a07dd-221">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a07dd-222">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a07dd-222">CommonParameters</span></span>

<span data-ttu-id="a07dd-223">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="a07dd-223">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span>
<span data-ttu-id="a07dd-224">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a07dd-224">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a07dd-225">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a07dd-225">INPUTS</span></span>

### <span data-ttu-id="a07dd-226">System.Object</span><span class="sxs-lookup"><span data-stu-id="a07dd-226">System.Object</span></span>

<span data-ttu-id="a07dd-227">É possível canalizar um objeto que contém o novo valor para o item para `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="a07dd-227">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="a07dd-228">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a07dd-228">OUTPUTS</span></span>

### <span data-ttu-id="a07dd-229">Nenhum ou System.String</span><span class="sxs-lookup"><span data-stu-id="a07dd-229">None or System.String</span></span>

<span data-ttu-id="a07dd-230">Quando você usa o parâmetro **PassThru** , o `Set-Content` gera um objeto **System. String** que representa o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a07dd-230">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="a07dd-231">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="a07dd-231">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a07dd-232">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a07dd-232">NOTES</span></span>

- <span data-ttu-id="a07dd-233">Você também pode consultar `Set-Content` por seu alias interno, `sc` .</span><span class="sxs-lookup"><span data-stu-id="a07dd-233">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="a07dd-234">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="a07dd-234">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="a07dd-235">`Set-Content` é projetado para processamento de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a07dd-235">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="a07dd-236">Se você canaliza objetos que não são de cadeia de caracteres para `Set-Content` , ele converte o objeto em uma cadeia de caracteres antes de gravá-lo.</span><span class="sxs-lookup"><span data-stu-id="a07dd-236">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="a07dd-237">Para gravar objetos em arquivos, use `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="a07dd-237">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="a07dd-238">O `Set-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="a07dd-238">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a07dd-239">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="a07dd-239">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="a07dd-240">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a07dd-240">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="a07dd-241">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a07dd-241">RELATED LINKS</span></span>

[<span data-ttu-id="a07dd-242">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="a07dd-242">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="a07dd-243">about_Automatic_Variables. MD</span><span class="sxs-lookup"><span data-stu-id="a07dd-243">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="a07dd-244">about_Providers</span><span class="sxs-lookup"><span data-stu-id="a07dd-244">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="a07dd-245">Add-Content</span><span class="sxs-lookup"><span data-stu-id="a07dd-245">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="a07dd-246">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="a07dd-246">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="a07dd-247">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="a07dd-247">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="a07dd-248">Get-Content</span><span class="sxs-lookup"><span data-stu-id="a07dd-248">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="a07dd-249">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="a07dd-249">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="a07dd-250">New-Item</span><span class="sxs-lookup"><span data-stu-id="a07dd-250">New-Item</span></span>](New-Item.md)
