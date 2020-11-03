---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: 897029cab790487f6834d021bfc447060fd39812
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193934"
---
# <span data-ttu-id="9d2ba-103">Set-Content</span><span class="sxs-lookup"><span data-stu-id="9d2ba-103">Set-Content</span></span>

## <span data-ttu-id="9d2ba-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9d2ba-104">SYNOPSIS</span></span>
<span data-ttu-id="9d2ba-105">Grava novo conteúdo ou substitui o conteúdo existente em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-105">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="9d2ba-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9d2ba-106">SYNTAX</span></span>

### <span data-ttu-id="9d2ba-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="9d2ba-107">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### <span data-ttu-id="9d2ba-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9d2ba-108">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

## <span data-ttu-id="9d2ba-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d2ba-109">DESCRIPTION</span></span>

<span data-ttu-id="9d2ba-110">`Set-Content` é um cmdlet de processamento de cadeia de caracteres que grava novo conteúdo ou substitui o conteúdo em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-110">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="9d2ba-111">`Set-Content` Substitui o conteúdo existente e difere do `Add-Content` cmdlet que acrescenta o conteúdo a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-111">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="9d2ba-112">Para enviar conteúdo para `Set-Content` você pode usar o parâmetro **Value** na linha de comando ou enviar conteúdo por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-112">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="9d2ba-113">Se você precisar criar arquivos ou diretórios para os exemplos a seguir, consulte [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ba-113">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="9d2ba-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9d2ba-114">EXAMPLES</span></span>

### <span data-ttu-id="9d2ba-115">Exemplo 1: substituir o conteúdo de vários arquivos em um diretório</span><span class="sxs-lookup"><span data-stu-id="9d2ba-115">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="9d2ba-116">Este exemplo substitui o conteúdo de vários arquivos no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-116">This example replaces the content for multiple files in the current directory.</span></span>

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

<span data-ttu-id="9d2ba-117">O `Get-ChildItem` cmdlet usa o parâmetro **Path** para listar arquivos **. txt** que começam com `Test*` no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-117">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="9d2ba-118">O `Set-Content` cmdlet usa o parâmetro **Path** para especificar os `Test*.txt` arquivos.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-118">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="9d2ba-119">O parâmetro **Value** fornece a cadeia de caracteres de texto **Olá, mundo** que substitui o conteúdo existente em cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-119">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="9d2ba-120">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar os `Test*.txt` arquivos e exibe o conteúdo de cada arquivo no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-120">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="9d2ba-121">Exemplo 2: criar um novo arquivo e gravar o conteúdo</span><span class="sxs-lookup"><span data-stu-id="9d2ba-121">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="9d2ba-122">Este exemplo cria um novo arquivo e grava a data e hora atuais no arquivo.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-122">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="9d2ba-123">`Set-Content` usa os parâmetros **Path** e **Value** para criar um novo arquivo chamado **DateTime.txt** no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-123">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="9d2ba-124">O parâmetro **Value** usa `Get-Date` para obter a data e a hora atuais.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-124">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="9d2ba-125">`Set-Content` grava o objeto **DateTime** no arquivo como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-125">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="9d2ba-126">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o conteúdo de **DateTime.txt** no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-126">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="9d2ba-127">Exemplo 3: substituir o texto em um arquivo</span><span class="sxs-lookup"><span data-stu-id="9d2ba-127">Example 3: Replace text in a file</span></span>

<span data-ttu-id="9d2ba-128">Esse comando substitui todas as instâncias do Word em um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-128">This command replaces all instances of word within an existing file.</span></span>

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

<span data-ttu-id="9d2ba-129">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o arquivo de **Notice.txt** no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-129">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="9d2ba-130">O `Get-Content` comando é encapsulado com parênteses para que o comando seja concluído antes de ser enviado ao pipeline.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-130">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="9d2ba-131">O conteúdo do arquivo de **Notice.txt** é enviado ao pipeline para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-131">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="9d2ba-132">`ForEach-Object` usa a variável automática `$_` e substitui cada ocorrência de **Warning** por **cuidado** .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-132">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution** .</span></span> <span data-ttu-id="9d2ba-133">Os objetos são enviados para o pipeline para o `Set-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-133">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="9d2ba-134">`Set-Content` usa o parâmetro **path** para especificar o arquivo de **Notice.txt** e grava o conteúdo atualizado no arquivo.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-134">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="9d2ba-135">O último `Get-Content` cmdlet exibe o conteúdo do arquivo atualizado no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-135">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="9d2ba-136">Exemplo 4: usar filtros com Set-Content</span><span class="sxs-lookup"><span data-stu-id="9d2ba-136">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="9d2ba-137">Você pode especificar um filtro para o `Set-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-137">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="9d2ba-138">Ao usar filtros para qualificar o parâmetro de **caminho** , você precisa incluir um asterisco à direita ( `*` ) para indicar o conteúdo do caminho.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-138">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="9d2ba-139">O comando a seguir define o conteúdo todos os `*.txt` arquivos no `C:\Temp` diretório para o **valor** vazio.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-139">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="9d2ba-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9d2ba-140">PARAMETERS</span></span>

### <span data-ttu-id="9d2ba-141">-Credential</span><span class="sxs-lookup"><span data-stu-id="9d2ba-141">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="9d2ba-142">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-142">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="9d2ba-143">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ba-143">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="9d2ba-144">-Codificação</span><span class="sxs-lookup"><span data-stu-id="9d2ba-144">-Encoding</span></span>

<span data-ttu-id="9d2ba-145">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-145">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="9d2ba-146">O valor padrão é `Default`.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-146">The default value is `Default`.</span></span>

<span data-ttu-id="9d2ba-147">A codificação é um parâmetro dinâmico que o provedor FileSystem adiciona `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-147">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="9d2ba-148">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-148">This parameter works only in file system drives.</span></span>

<span data-ttu-id="9d2ba-149">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="9d2ba-149">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="9d2ba-150">`Ascii` Usa conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="9d2ba-150">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="9d2ba-151">`BigEndianUnicode` Usa UTF-16 com a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-151">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="9d2ba-152">`BigEndianUTF32` Usa UTF-32 com a ordem de byte big-endian.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-152">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="9d2ba-153">`Byte` Codifica um conjunto de caracteres em uma sequência de bytes.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-153">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="9d2ba-154">`Default` Usa a codificação que corresponde à página de código ativa do sistema (geralmente ANSI).</span><span class="sxs-lookup"><span data-stu-id="9d2ba-154">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="9d2ba-155">`Oem` Usa a codificação que corresponde à página de código OEM atual do sistema.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-155">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="9d2ba-156">`String` Igual a `Unicode`.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-156">`String` Same as `Unicode`.</span></span>
- <span data-ttu-id="9d2ba-157">`Unicode` Usa UTF-16 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-157">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="9d2ba-158">`Unknown` Igual a `Unicode`.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-158">`Unknown` Same as `Unicode`.</span></span>
- <span data-ttu-id="9d2ba-159">`UTF7` Usa UTF-7.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-159">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="9d2ba-160">`UTF8` Usa UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-160">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="9d2ba-161">`UTF32` Usa UTF-32 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-161">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="9d2ba-162">A codificação é um parâmetro dinâmico que o provedor FileSystem adiciona `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-162">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="9d2ba-163">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-163">This parameter works only in file system drives.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d2ba-164">-Excluir</span><span class="sxs-lookup"><span data-stu-id="9d2ba-164">-Exclude</span></span>

<span data-ttu-id="9d2ba-165">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-165">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="9d2ba-166">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-166">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9d2ba-167">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-167">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="9d2ba-168">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-168">Wildcard characters are permitted.</span></span> <span data-ttu-id="9d2ba-169">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-169">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="9d2ba-170">-Filter</span><span class="sxs-lookup"><span data-stu-id="9d2ba-170">-Filter</span></span>

<span data-ttu-id="9d2ba-171">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-171">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="9d2ba-172">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-172">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="9d2ba-173">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ba-173">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="9d2ba-174">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-174">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="9d2ba-175">-Force</span><span class="sxs-lookup"><span data-stu-id="9d2ba-175">-Force</span></span>

<span data-ttu-id="9d2ba-176">Força o cmdlet a definir o conteúdo de um arquivo, mesmo se o arquivo for somente leitura.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-176">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="9d2ba-177">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-177">Implementation varies from provider to provider.</span></span> <span data-ttu-id="9d2ba-178">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ba-178">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="9d2ba-179">O parâmetro **Force** não substitui as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-179">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="9d2ba-180">-Incluir</span><span class="sxs-lookup"><span data-stu-id="9d2ba-180">-Include</span></span>

<span data-ttu-id="9d2ba-181">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-181">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="9d2ba-182">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-182">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9d2ba-183">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-183">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="9d2ba-184">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-184">Wildcard characters are permitted.</span></span> <span data-ttu-id="9d2ba-185">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-185">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="9d2ba-186">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9d2ba-186">-LiteralPath</span></span>

<span data-ttu-id="9d2ba-187">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-187">Specifies a path to one or more locations.</span></span> <span data-ttu-id="9d2ba-188">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-188">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="9d2ba-189">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-189">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9d2ba-190">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-190">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9d2ba-191">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-191">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="9d2ba-192">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ba-192">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9d2ba-193">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="9d2ba-193">-NoNewline</span></span>

<span data-ttu-id="9d2ba-194">As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-194">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="9d2ba-195">Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-195">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="9d2ba-196">Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-196">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="9d2ba-197">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9d2ba-197">-PassThru</span></span>

<span data-ttu-id="9d2ba-198">Retorna um objeto que representa o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-198">Returns an object that represents the content.</span></span> <span data-ttu-id="9d2ba-199">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-199">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="9d2ba-200">-Path</span><span class="sxs-lookup"><span data-stu-id="9d2ba-200">-Path</span></span>

<span data-ttu-id="9d2ba-201">Especifica o caminho do item que recebe o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-201">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="9d2ba-202">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-202">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="9d2ba-203">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="9d2ba-203">-Stream</span></span>

<span data-ttu-id="9d2ba-204">Especifica um fluxo de dados alternativo para o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-204">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="9d2ba-205">Se o fluxo não existir, esse cmdlet o criará.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-205">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="9d2ba-206">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-206">Wildcard characters are not supported.</span></span>

<span data-ttu-id="9d2ba-207">**Stream** é um parâmetro dinâmico que o provedor **FileSystem** adiciona `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-207">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="9d2ba-208">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-208">This parameter works only in file system drives.</span></span>

<span data-ttu-id="9d2ba-209">Você pode usar o `Set-Content` cmdlet para alterar o conteúdo do fluxo de dados de **zona. identificador** alternativo.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-209">You can use the `Set-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="9d2ba-210">No entanto, não recomendamos isso como uma maneira de eliminar verificações de segurança que bloqueiam arquivos baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-210">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="9d2ba-211">Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-211">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="9d2ba-212">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-212">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="9d2ba-213">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="9d2ba-213">-UseTransaction</span></span>

<span data-ttu-id="9d2ba-214">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-214">Includes the command in the active transaction.</span></span> <span data-ttu-id="9d2ba-215">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-215">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="9d2ba-216">Para obter mais informações, consulte [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ba-216">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="9d2ba-217">-Value</span><span class="sxs-lookup"><span data-stu-id="9d2ba-217">-Value</span></span>

<span data-ttu-id="9d2ba-218">Especifica o novo conteúdo para o item.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-218">Specifies the new content for the item.</span></span>

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

### <span data-ttu-id="9d2ba-219">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9d2ba-219">-Confirm</span></span>

<span data-ttu-id="9d2ba-220">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-220">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9d2ba-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9d2ba-221">-WhatIf</span></span>

<span data-ttu-id="9d2ba-222">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-222">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9d2ba-223">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-223">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9d2ba-224">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9d2ba-224">CommonParameters</span></span>

<span data-ttu-id="9d2ba-225">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-225">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span>
<span data-ttu-id="9d2ba-226">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ba-226">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9d2ba-227">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9d2ba-227">INPUTS</span></span>

### <span data-ttu-id="9d2ba-228">System.Object</span><span class="sxs-lookup"><span data-stu-id="9d2ba-228">System.Object</span></span>

<span data-ttu-id="9d2ba-229">É possível canalizar um objeto que contém o novo valor para o item para `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-229">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="9d2ba-230">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9d2ba-230">OUTPUTS</span></span>

### <span data-ttu-id="9d2ba-231">Nenhum ou System.String</span><span class="sxs-lookup"><span data-stu-id="9d2ba-231">None or System.String</span></span>

<span data-ttu-id="9d2ba-232">Quando você usa o parâmetro **PassThru** , o `Set-Content` gera um objeto **System. String** que representa o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-232">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="9d2ba-233">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-233">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9d2ba-234">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9d2ba-234">NOTES</span></span>

- <span data-ttu-id="9d2ba-235">Você também pode consultar `Set-Content` por seu alias interno, `sc` .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-235">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="9d2ba-236">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ba-236">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="9d2ba-237">`Set-Content` é projetado para processamento de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-237">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="9d2ba-238">Se você canaliza objetos que não são de cadeia de caracteres para `Set-Content` , ele converte o objeto em uma cadeia de caracteres antes de gravá-lo.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-238">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="9d2ba-239">Para gravar objetos em arquivos, use `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-239">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="9d2ba-240">O `Set-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-240">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="9d2ba-241">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="9d2ba-241">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="9d2ba-242">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ba-242">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="9d2ba-243">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9d2ba-243">RELATED LINKS</span></span>

[<span data-ttu-id="9d2ba-244">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="9d2ba-244">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="9d2ba-245">about_Automatic_Variables. MD</span><span class="sxs-lookup"><span data-stu-id="9d2ba-245">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="9d2ba-246">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9d2ba-246">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="9d2ba-247">about_Transactions</span><span class="sxs-lookup"><span data-stu-id="9d2ba-247">about_Transactions</span></span>](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[<span data-ttu-id="9d2ba-248">Add-Content</span><span class="sxs-lookup"><span data-stu-id="9d2ba-248">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="9d2ba-249">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="9d2ba-249">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="9d2ba-250">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="9d2ba-250">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="9d2ba-251">Get-Content</span><span class="sxs-lookup"><span data-stu-id="9d2ba-251">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="9d2ba-252">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="9d2ba-252">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="9d2ba-253">New-Item</span><span class="sxs-lookup"><span data-stu-id="9d2ba-253">New-Item</span></span>](New-Item.md)
