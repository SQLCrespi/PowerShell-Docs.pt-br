---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: f3cd58bffde8bcb6dab488a9e40e69d7435133e4
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "93195350"
---
# <span data-ttu-id="0137c-103">Out-File</span><span class="sxs-lookup"><span data-stu-id="0137c-103">Out-File</span></span>

## <span data-ttu-id="0137c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0137c-104">SYNOPSIS</span></span>
<span data-ttu-id="0137c-105">Envia a saída para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0137c-105">Sends output to a file.</span></span>

## <span data-ttu-id="0137c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0137c-106">SYNTAX</span></span>

### <span data-ttu-id="0137c-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="0137c-107">ByPath (Default)</span></span>

```
Out-File [-FilePath] <string> [[-Encoding] <Encoding>] [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0137c-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="0137c-108">ByLiteralPath</span></span>

```
Out-File [[-Encoding] <Encoding>] -LiteralPath <string> [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0137c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0137c-109">DESCRIPTION</span></span>

<span data-ttu-id="0137c-110">O `Out-File` cmdlet envia a saída para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0137c-110">The `Out-File` cmdlet sends output to a file.</span></span> <span data-ttu-id="0137c-111">Ele usa implicitamente o sistema de formatação do PowerShell para gravar no arquivo.</span><span class="sxs-lookup"><span data-stu-id="0137c-111">It implicitly uses PowerShell's formatting system to write to the file.</span></span> <span data-ttu-id="0137c-112">O arquivo recebe a mesma representação de exibição que o terminal.</span><span class="sxs-lookup"><span data-stu-id="0137c-112">The file receives the same display representation as the terminal.</span></span> <span data-ttu-id="0137c-113">Isso significa que a saída pode não ser ideal para processamento programático, a menos que todos os objetos de entrada sejam cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0137c-113">This means that the output may not be ideal for programmatic processing unless all input objects are strings.</span></span>
<span data-ttu-id="0137c-114">Quando você precisar especificar parâmetros para a saída, use `Out-File` em vez do operador de redirecionamento ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="0137c-114">When you need to specify parameters for the output, use `Out-File` rather than the redirection operator (`>`).</span></span> <span data-ttu-id="0137c-115">Para obter mais informações sobre o redirecionamento, consulte [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span><span class="sxs-lookup"><span data-stu-id="0137c-115">For more information about redirection, see [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span></span>

## <span data-ttu-id="0137c-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0137c-116">EXAMPLES</span></span>

### <span data-ttu-id="0137c-117">Exemplo 1: enviar a saída e criar um arquivo</span><span class="sxs-lookup"><span data-stu-id="0137c-117">Example 1: Send output and create a file</span></span>

<span data-ttu-id="0137c-118">Este exemplo mostra como enviar uma lista de processos do computador local para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0137c-118">This example shows how to send a list of the local computer's processes to a file.</span></span> <span data-ttu-id="0137c-119">Se o arquivo não existir, o `Out-File` criará o arquivo no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="0137c-119">If the file does not exist, `Out-File` creates the file in the specified path.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt
Get-Content -Path .\Process.txt
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     29    22.39      35.40      10.98   42764   9 Application
     53    99.04     113.96       0.00   32664   0 CcmExec
     27    96.62     112.43     113.00   17720   9 Code
```

<span data-ttu-id="0137c-120">O `Get-Process` cmdlet obtém a lista de processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="0137c-120">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="0137c-121">Os objetos de **processo** são enviados por meio do pipeline para o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0137c-121">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="0137c-122">`Out-File` usa o parâmetro **FilePath** e cria um arquivo no diretório atual chamado **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="0137c-122">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="0137c-123">O `Get-Content` comando obtém o conteúdo do arquivo e o exibe no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0137c-123">The `Get-Content` command gets content from the file and displays it in the PowerShell console.</span></span>

### <span data-ttu-id="0137c-124">Exemplo 2: impedir que um arquivo existente seja substituído</span><span class="sxs-lookup"><span data-stu-id="0137c-124">Example 2: Prevent an existing file from being overwritten</span></span>

<span data-ttu-id="0137c-125">Este exemplo impede que um arquivo existente seja substituído.</span><span class="sxs-lookup"><span data-stu-id="0137c-125">This example prevents an existing file from being overwritten.</span></span> <span data-ttu-id="0137c-126">Por padrão, o `Out-File` substitui os arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="0137c-126">By default, `Out-File` overwrites existing files.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

<span data-ttu-id="0137c-127">O `Get-Process` cmdlet obtém a lista de processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="0137c-127">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="0137c-128">Os objetos de **processo** são enviados por meio do pipeline para o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0137c-128">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="0137c-129">`Out-File` usa o parâmetro **FilePath** e tenta gravar em um arquivo no diretório atual chamado **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="0137c-129">`Out-File` uses the **FilePath** parameter and attempts to write to a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="0137c-130">O parâmetro **NoClobber** impede que o arquivo seja substituído e exibe uma mensagem informando que o arquivo já existe.</span><span class="sxs-lookup"><span data-stu-id="0137c-130">The **NoClobber** parameter prevents the file from being overwritten and displays a message that the file already exists.</span></span>

### <span data-ttu-id="0137c-131">Exemplo 3: enviar a saída para um arquivo no formato ASCII</span><span class="sxs-lookup"><span data-stu-id="0137c-131">Example 3: Send output to a file in ASCII format</span></span>

<span data-ttu-id="0137c-132">Este exemplo mostra como codificar a saída com um tipo de codificação específico.</span><span class="sxs-lookup"><span data-stu-id="0137c-132">This example shows how to encode output with a specific encoding type.</span></span>

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

<span data-ttu-id="0137c-133">O `Get-Process` cmdlet obtém a lista de processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="0137c-133">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="0137c-134">Os objetos de **processo** são armazenados na variável, `$Procs` .</span><span class="sxs-lookup"><span data-stu-id="0137c-134">The **Process** objects are stored in the variable, `$Procs`.</span></span> <span data-ttu-id="0137c-135">`Out-File` usa o parâmetro **FilePath** e cria um arquivo no diretório atual chamado **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="0137c-135">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="0137c-136">O parâmetro **InputObject** passa os objetos de processo `$Procs` para o arquivo **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="0137c-136">The **InputObject** parameter passes the process objects in `$Procs` to the file **Process.txt** .</span></span> <span data-ttu-id="0137c-137">O parâmetro **Encoding** converte a saída para o formato **ASCII** .</span><span class="sxs-lookup"><span data-stu-id="0137c-137">The **Encoding** parameter converts the output to **ASCII** format.</span></span> <span data-ttu-id="0137c-138">O parâmetro **Width** limita cada linha no arquivo a 50 caracteres, de modo que alguns dados possam ser truncados.</span><span class="sxs-lookup"><span data-stu-id="0137c-138">The **Width** parameter limits each line in the file to 50 characters so some data might be truncated.</span></span>

### <span data-ttu-id="0137c-139">Exemplo 4: usar um provedor e enviar a saída para um arquivo</span><span class="sxs-lookup"><span data-stu-id="0137c-139">Example 4: Use a provider and send output to a file</span></span>

<span data-ttu-id="0137c-140">Este exemplo mostra como usar o `Out-File` cmdlet quando você não está em uma unidade do provedor **FileSystem** .</span><span class="sxs-lookup"><span data-stu-id="0137c-140">This example shows how to use the `Out-File` cmdlet when you are not in a **FileSystem** provider drive.</span></span> <span data-ttu-id="0137c-141">Use o `Get-PSProvider` cmdlet para exibir os provedores em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="0137c-141">Use the `Get-PSProvider` cmdlet to view the providers on your local computer.</span></span> <span data-ttu-id="0137c-142">Para obter mais informações, consulte [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0137c-142">For more information, see [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span></span>

```
PS> Set-Location -Path Alias:

PS> Get-Location

Path
----
Alias:\

PS> Get-ChildItem | Out-File -FilePath C:\TestDir\AliasNames.txt

PS> Get-Content -Path C:\TestDir\AliasNames.txt

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           cat -> Get-Content
```

<span data-ttu-id="0137c-143">O `Set-Location` comando usa o parâmetro **Path** para definir o local atual como o provedor de registro `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="0137c-143">The `Set-Location` command uses the **Path** parameter to set the current location to the registry provider `Alias:`.</span></span> <span data-ttu-id="0137c-144">O `Get-Location` cmdlet exibe o caminho completo para `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="0137c-144">The `Get-Location` cmdlet displays the complete path for `Alias:`.</span></span>
<span data-ttu-id="0137c-145">`Get-ChildItem` envia objetos pelo pipeline para o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0137c-145">`Get-ChildItem` sends objects down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="0137c-146">`Out-File` usa o parâmetro **FilePath** para especificar o caminho e o nome de arquivo completos para a saída, **C:\TestDir\AliasNames.txt** .</span><span class="sxs-lookup"><span data-stu-id="0137c-146">`Out-File` uses the **FilePath** parameter to specify the complete path and filename for the output, **C:\TestDir\AliasNames.txt** .</span></span> <span data-ttu-id="0137c-147">O `Get-Content` cmdlet usa o parâmetro **Path** e exibe o conteúdo do arquivo no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0137c-147">The `Get-Content` cmdlet uses the **Path** parameter and displays the file's content in the PowerShell console.</span></span>

## <span data-ttu-id="0137c-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0137c-148">PARAMETERS</span></span>

### <span data-ttu-id="0137c-149">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="0137c-149">-Append</span></span>

<span data-ttu-id="0137c-150">Adiciona a saída ao final de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="0137c-150">Adds the output to the end of an existing file.</span></span>

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

### <span data-ttu-id="0137c-151">-Codificação</span><span class="sxs-lookup"><span data-stu-id="0137c-151">-Encoding</span></span>

<span data-ttu-id="0137c-152">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="0137c-152">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="0137c-153">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="0137c-153">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="0137c-154">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="0137c-154">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="0137c-155">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="0137c-155">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="0137c-156">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="0137c-156">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="0137c-157">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="0137c-157">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="0137c-158">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="0137c-158">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="0137c-159">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="0137c-159">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="0137c-160">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0137c-160">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="0137c-161">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="0137c-161">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="0137c-162">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="0137c-162">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="0137c-163">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="0137c-163">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="0137c-164">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="0137c-164">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="0137c-165">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="0137c-165">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: 1
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0137c-166">-FilePath</span><span class="sxs-lookup"><span data-stu-id="0137c-166">-FilePath</span></span>

<span data-ttu-id="0137c-167">Especifica o caminho para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="0137c-167">Specifies the path to the output file.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0137c-168">-Force</span><span class="sxs-lookup"><span data-stu-id="0137c-168">-Force</span></span>

<span data-ttu-id="0137c-169">Substitui o atributo somente leitura e sobrescreve um arquivo somente leitura existente.</span><span class="sxs-lookup"><span data-stu-id="0137c-169">Overrides the read-only attribute and overwrites an existing read-only file.</span></span> <span data-ttu-id="0137c-170">O parâmetro **Force** não substitui as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="0137c-170">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="0137c-171">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0137c-171">-InputObject</span></span>

<span data-ttu-id="0137c-172">Especifica os objetos a serem gravados no arquivo.</span><span class="sxs-lookup"><span data-stu-id="0137c-172">Specifies the objects to be written to the file.</span></span> <span data-ttu-id="0137c-173">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="0137c-173">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0137c-174">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0137c-174">-LiteralPath</span></span>

<span data-ttu-id="0137c-175">Especifica o caminho para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="0137c-175">Specifies the path to the output file.</span></span> <span data-ttu-id="0137c-176">O parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="0137c-176">The **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="0137c-177">Caracteres curinga não são aceitos.</span><span class="sxs-lookup"><span data-stu-id="0137c-177">Wildcard characters are not accepted.</span></span> <span data-ttu-id="0137c-178">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="0137c-178">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0137c-179">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="0137c-179">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="0137c-180">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="0137c-180">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0137c-181">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="0137c-181">-NoClobber</span></span>

<span data-ttu-id="0137c-182">**NoClobber** impede que um arquivo existente seja substituído e exibe uma mensagem informando que o arquivo já existe.</span><span class="sxs-lookup"><span data-stu-id="0137c-182">**NoClobber** prevents an existing file from being overwritten and displays a message that the file already exists.</span></span> <span data-ttu-id="0137c-183">Por padrão, se um arquivo existir no caminho especificado, `Out-File` o substituirá o arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="0137c-183">By default, if a file exists in the specified path, `Out-File` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0137c-184">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="0137c-184">-NoNewline</span></span>

<span data-ttu-id="0137c-185">Especifica que o conteúdo gravado no arquivo não termina com um caractere de nova linha.</span><span class="sxs-lookup"><span data-stu-id="0137c-185">Specifies that the content written to the file does not end with a newline character.</span></span> <span data-ttu-id="0137c-186">As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída.</span><span class="sxs-lookup"><span data-stu-id="0137c-186">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="0137c-187">Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="0137c-187">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="0137c-188">Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="0137c-188">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="0137c-189">-Largura</span><span class="sxs-lookup"><span data-stu-id="0137c-189">-Width</span></span>

<span data-ttu-id="0137c-190">Especifica o número de caracteres em cada linha de saída.</span><span class="sxs-lookup"><span data-stu-id="0137c-190">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="0137c-191">Quaisquer eventuais caracteres adicionais ficam truncados, não encapsulados.</span><span class="sxs-lookup"><span data-stu-id="0137c-191">Any additional characters are truncated, not wrapped.</span></span> <span data-ttu-id="0137c-192">Se esse parâmetro não for usado, a largura será determinada pelas características do host.</span><span class="sxs-lookup"><span data-stu-id="0137c-192">If this parameter is not used, the width is determined by the characteristics of the host.</span></span> <span data-ttu-id="0137c-193">O padrão para o console do PowerShell é de 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="0137c-193">The default for the PowerShell console is 80 characters.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0137c-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0137c-194">-Confirm</span></span>

<span data-ttu-id="0137c-195">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0137c-195">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0137c-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0137c-196">-WhatIf</span></span>

<span data-ttu-id="0137c-197">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0137c-197">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0137c-198">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0137c-198">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0137c-199">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0137c-199">CommonParameters</span></span>

<span data-ttu-id="0137c-200">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0137c-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0137c-201">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0137c-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0137c-202">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0137c-202">INPUTS</span></span>

### <span data-ttu-id="0137c-203">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="0137c-203">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0137c-204">Você pode canalizar qualquer objeto para `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="0137c-204">You can pipe any object to `Out-File`.</span></span>

## <span data-ttu-id="0137c-205">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0137c-205">OUTPUTS</span></span>

### <span data-ttu-id="0137c-206">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0137c-206">None</span></span>

<span data-ttu-id="0137c-207">`Out-File` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="0137c-207">`Out-File` does not generate any output.</span></span>

## <span data-ttu-id="0137c-208">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0137c-208">NOTES</span></span>

<span data-ttu-id="0137c-209">Os objetos de entrada são formatados automaticamente como seriam no terminal, mas você pode usar um `Format-*` cmdlet para controlar explicitamente a formatação da saída para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="0137c-209">Input objects are automatically formatted as they would be in the terminal, but you can use a `Format-*` cmdlet to explicitly control the formatting of the output to the file.</span></span> <span data-ttu-id="0137c-210">Por exemplo, `Get-Date | Format-List | Out-File out.txt`</span><span class="sxs-lookup"><span data-stu-id="0137c-210">For example, `Get-Date | Format-List | Out-File out.txt`</span></span>

<span data-ttu-id="0137c-211">Para enviar a saída de um comando do PowerShell para o `Out-File` cmdlet, use o pipeline.</span><span class="sxs-lookup"><span data-stu-id="0137c-211">To send a PowerShell command's output to the `Out-File` cmdlet, use the pipeline.</span></span> <span data-ttu-id="0137c-212">Como alternativa, você pode armazenar dados em uma variável e usar o parâmetro **InputObject** para passar dados para o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0137c-212">Alternatively, you can store data in a variable and use the **InputObject** parameter to pass data to the `Out-File` cmdlet.</span></span>

<span data-ttu-id="0137c-213">`Out-File` salva dados em um arquivo, mas não produz nenhum objeto de saída para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="0137c-213">`Out-File` saves data to a file but it does not produce any output objects to the pipeline.</span></span>

## <span data-ttu-id="0137c-214">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0137c-214">RELATED LINKS</span></span>

[<span data-ttu-id="0137c-215">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0137c-215">about_Providers</span></span>](../Microsoft.Powershell.Core/About/about_Providers.md)

[<span data-ttu-id="0137c-216">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="0137c-216">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="0137c-217">Out-Default</span><span class="sxs-lookup"><span data-stu-id="0137c-217">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="0137c-218">Out-Host</span><span class="sxs-lookup"><span data-stu-id="0137c-218">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="0137c-219">Out-Null</span><span class="sxs-lookup"><span data-stu-id="0137c-219">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="0137c-220">Out-String</span><span class="sxs-lookup"><span data-stu-id="0137c-220">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="0137c-221">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="0137c-221">Tee-Object</span></span>](Tee-Object.md)
