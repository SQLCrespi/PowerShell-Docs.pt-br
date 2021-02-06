---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: e3a066957ab1e6935049003f8ccf55aee8bb7c94
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595767"
---
# <span data-ttu-id="0530b-102">Out-File</span><span class="sxs-lookup"><span data-stu-id="0530b-102">Out-File</span></span>

## <span data-ttu-id="0530b-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0530b-103">SYNOPSIS</span></span>
<span data-ttu-id="0530b-104">Envia a saída para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0530b-104">Sends output to a file.</span></span>

## <span data-ttu-id="0530b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0530b-105">SYNTAX</span></span>

### <span data-ttu-id="0530b-106">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="0530b-106">ByPath (Default)</span></span>

```
Out-File [-FilePath] <string> [[-Encoding] <Encoding>] [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0530b-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="0530b-107">ByLiteralPath</span></span>

```
Out-File [[-Encoding] <Encoding>] -LiteralPath <string> [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0530b-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0530b-108">DESCRIPTION</span></span>

<span data-ttu-id="0530b-109">O `Out-File` cmdlet envia a saída para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0530b-109">The `Out-File` cmdlet sends output to a file.</span></span> <span data-ttu-id="0530b-110">Ele usa implicitamente o sistema de formatação do PowerShell para gravar no arquivo.</span><span class="sxs-lookup"><span data-stu-id="0530b-110">It implicitly uses PowerShell's formatting system to write to the file.</span></span> <span data-ttu-id="0530b-111">O arquivo recebe a mesma representação de exibição que o terminal.</span><span class="sxs-lookup"><span data-stu-id="0530b-111">The file receives the same display representation as the terminal.</span></span> <span data-ttu-id="0530b-112">Isso significa que a saída pode não ser ideal para processamento programático, a menos que todos os objetos de entrada sejam cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0530b-112">This means that the output may not be ideal for programmatic processing unless all input objects are strings.</span></span>
<span data-ttu-id="0530b-113">Quando você precisar especificar parâmetros para a saída, use `Out-File` em vez do operador de redirecionamento ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="0530b-113">When you need to specify parameters for the output, use `Out-File` rather than the redirection operator (`>`).</span></span> <span data-ttu-id="0530b-114">Para obter mais informações sobre o redirecionamento, consulte [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span><span class="sxs-lookup"><span data-stu-id="0530b-114">For more information about redirection, see [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span></span>

## <span data-ttu-id="0530b-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0530b-115">EXAMPLES</span></span>

### <span data-ttu-id="0530b-116">Exemplo 1: enviar a saída e criar um arquivo</span><span class="sxs-lookup"><span data-stu-id="0530b-116">Example 1: Send output and create a file</span></span>

<span data-ttu-id="0530b-117">Este exemplo mostra como enviar uma lista de processos do computador local para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0530b-117">This example shows how to send a list of the local computer's processes to a file.</span></span> <span data-ttu-id="0530b-118">Se o arquivo não existir, o `Out-File` criará o arquivo no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="0530b-118">If the file does not exist, `Out-File` creates the file in the specified path.</span></span>

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

<span data-ttu-id="0530b-119">O `Get-Process` cmdlet obtém a lista de processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="0530b-119">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="0530b-120">Os objetos de **processo** são enviados por meio do pipeline para o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0530b-120">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="0530b-121">`Out-File` usa o parâmetro **FilePath** e cria um arquivo no diretório atual chamado **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="0530b-121">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="0530b-122">O `Get-Content` comando obtém o conteúdo do arquivo e o exibe no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0530b-122">The `Get-Content` command gets content from the file and displays it in the PowerShell console.</span></span>

### <span data-ttu-id="0530b-123">Exemplo 2: impedir que um arquivo existente seja substituído</span><span class="sxs-lookup"><span data-stu-id="0530b-123">Example 2: Prevent an existing file from being overwritten</span></span>

<span data-ttu-id="0530b-124">Este exemplo impede que um arquivo existente seja substituído.</span><span class="sxs-lookup"><span data-stu-id="0530b-124">This example prevents an existing file from being overwritten.</span></span> <span data-ttu-id="0530b-125">Por padrão, o `Out-File` substitui os arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="0530b-125">By default, `Out-File` overwrites existing files.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

<span data-ttu-id="0530b-126">O `Get-Process` cmdlet obtém a lista de processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="0530b-126">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="0530b-127">Os objetos de **processo** são enviados por meio do pipeline para o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0530b-127">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="0530b-128">`Out-File` usa o parâmetro **FilePath** e tenta gravar em um arquivo no diretório atual chamado **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="0530b-128">`Out-File` uses the **FilePath** parameter and attempts to write to a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="0530b-129">O parâmetro **NoClobber** impede que o arquivo seja substituído e exibe uma mensagem informando que o arquivo já existe.</span><span class="sxs-lookup"><span data-stu-id="0530b-129">The **NoClobber** parameter prevents the file from being overwritten and displays a message that the file already exists.</span></span>

### <span data-ttu-id="0530b-130">Exemplo 3: enviar a saída para um arquivo no formato ASCII</span><span class="sxs-lookup"><span data-stu-id="0530b-130">Example 3: Send output to a file in ASCII format</span></span>

<span data-ttu-id="0530b-131">Este exemplo mostra como codificar a saída com um tipo de codificação específico.</span><span class="sxs-lookup"><span data-stu-id="0530b-131">This example shows how to encode output with a specific encoding type.</span></span>

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

<span data-ttu-id="0530b-132">O `Get-Process` cmdlet obtém a lista de processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="0530b-132">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="0530b-133">Os objetos de **processo** são armazenados na variável, `$Procs` .</span><span class="sxs-lookup"><span data-stu-id="0530b-133">The **Process** objects are stored in the variable, `$Procs`.</span></span> <span data-ttu-id="0530b-134">`Out-File` usa o parâmetro **FilePath** e cria um arquivo no diretório atual chamado **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="0530b-134">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="0530b-135">O parâmetro **InputObject** passa os objetos de processo `$Procs` para o arquivo **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="0530b-135">The **InputObject** parameter passes the process objects in `$Procs` to the file **Process.txt**.</span></span> <span data-ttu-id="0530b-136">O parâmetro **Encoding** converte a saída para o formato **ASCII** .</span><span class="sxs-lookup"><span data-stu-id="0530b-136">The **Encoding** parameter converts the output to **ASCII** format.</span></span> <span data-ttu-id="0530b-137">O parâmetro **Width** limita cada linha no arquivo a 50 caracteres, de modo que alguns dados possam ser truncados.</span><span class="sxs-lookup"><span data-stu-id="0530b-137">The **Width** parameter limits each line in the file to 50 characters so some data might be truncated.</span></span>

### <span data-ttu-id="0530b-138">Exemplo 4: usar um provedor e enviar a saída para um arquivo</span><span class="sxs-lookup"><span data-stu-id="0530b-138">Example 4: Use a provider and send output to a file</span></span>

<span data-ttu-id="0530b-139">Este exemplo mostra como usar o `Out-File` cmdlet quando você não está em uma unidade do provedor **FileSystem** .</span><span class="sxs-lookup"><span data-stu-id="0530b-139">This example shows how to use the `Out-File` cmdlet when you are not in a **FileSystem** provider drive.</span></span> <span data-ttu-id="0530b-140">Use o `Get-PSProvider` cmdlet para exibir os provedores em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="0530b-140">Use the `Get-PSProvider` cmdlet to view the providers on your local computer.</span></span> <span data-ttu-id="0530b-141">Para obter mais informações, consulte [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0530b-141">For more information, see [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span></span>

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

<span data-ttu-id="0530b-142">O `Set-Location` comando usa o parâmetro **Path** para definir o local atual como o provedor de registro `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="0530b-142">The `Set-Location` command uses the **Path** parameter to set the current location to the registry provider `Alias:`.</span></span> <span data-ttu-id="0530b-143">O `Get-Location` cmdlet exibe o caminho completo para `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="0530b-143">The `Get-Location` cmdlet displays the complete path for `Alias:`.</span></span>
<span data-ttu-id="0530b-144">`Get-ChildItem` envia objetos pelo pipeline para o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0530b-144">`Get-ChildItem` sends objects down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="0530b-145">`Out-File` usa o parâmetro **FilePath** para especificar o caminho e o nome de arquivo completos para a saída, **C:\TestDir\AliasNames.txt**.</span><span class="sxs-lookup"><span data-stu-id="0530b-145">`Out-File` uses the **FilePath** parameter to specify the complete path and filename for the output, **C:\TestDir\AliasNames.txt**.</span></span> <span data-ttu-id="0530b-146">O `Get-Content` cmdlet usa o parâmetro **Path** e exibe o conteúdo do arquivo no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0530b-146">The `Get-Content` cmdlet uses the **Path** parameter and displays the file's content in the PowerShell console.</span></span>

## <span data-ttu-id="0530b-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0530b-147">PARAMETERS</span></span>

### <span data-ttu-id="0530b-148">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="0530b-148">-Append</span></span>

<span data-ttu-id="0530b-149">Adiciona a saída ao final de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="0530b-149">Adds the output to the end of an existing file.</span></span>

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

### <span data-ttu-id="0530b-150">-Codificação</span><span class="sxs-lookup"><span data-stu-id="0530b-150">-Encoding</span></span>

<span data-ttu-id="0530b-151">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="0530b-151">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="0530b-152">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="0530b-152">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="0530b-153">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="0530b-153">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="0530b-154">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="0530b-154">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="0530b-155">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="0530b-155">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="0530b-156">`bigendianutf32`: Codifica em formato UTF-32 usando a ordem de byte big-endian.</span><span class="sxs-lookup"><span data-stu-id="0530b-156">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="0530b-157">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="0530b-157">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="0530b-158">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="0530b-158">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="0530b-159">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="0530b-159">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="0530b-160">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0530b-160">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="0530b-161">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="0530b-161">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="0530b-162">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="0530b-162">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="0530b-163">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="0530b-163">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="0530b-164">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="0530b-164">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="0530b-165">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="0530b-165">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="0530b-166">O **UTF-7** _ não é mais recomendado para uso.</span><span class="sxs-lookup"><span data-stu-id="0530b-166">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="0530b-167">No PowerShell 7,1, um aviso será gravado se você especificar `utf7` para o parâmetro _ \*Encoding\*\*.</span><span class="sxs-lookup"><span data-stu-id="0530b-167">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: 1
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0530b-168">-FilePath</span><span class="sxs-lookup"><span data-stu-id="0530b-168">-FilePath</span></span>

<span data-ttu-id="0530b-169">Especifica o caminho para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="0530b-169">Specifies the path to the output file.</span></span>

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

### <span data-ttu-id="0530b-170">-Force</span><span class="sxs-lookup"><span data-stu-id="0530b-170">-Force</span></span>

<span data-ttu-id="0530b-171">Substitui o atributo somente leitura e sobrescreve um arquivo somente leitura existente.</span><span class="sxs-lookup"><span data-stu-id="0530b-171">Overrides the read-only attribute and overwrites an existing read-only file.</span></span> <span data-ttu-id="0530b-172">O parâmetro **Force** não substitui as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="0530b-172">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="0530b-173">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0530b-173">-InputObject</span></span>

<span data-ttu-id="0530b-174">Especifica os objetos a serem gravados no arquivo.</span><span class="sxs-lookup"><span data-stu-id="0530b-174">Specifies the objects to be written to the file.</span></span> <span data-ttu-id="0530b-175">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="0530b-175">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="0530b-176">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0530b-176">-LiteralPath</span></span>

<span data-ttu-id="0530b-177">Especifica o caminho para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="0530b-177">Specifies the path to the output file.</span></span> <span data-ttu-id="0530b-178">O parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="0530b-178">The **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="0530b-179">Caracteres curinga não são aceitos.</span><span class="sxs-lookup"><span data-stu-id="0530b-179">Wildcard characters are not accepted.</span></span> <span data-ttu-id="0530b-180">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="0530b-180">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0530b-181">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="0530b-181">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="0530b-182">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="0530b-182">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="0530b-183">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="0530b-183">-NoClobber</span></span>

<span data-ttu-id="0530b-184">**NoClobber** impede que um arquivo existente seja substituído e exibe uma mensagem informando que o arquivo já existe.</span><span class="sxs-lookup"><span data-stu-id="0530b-184">**NoClobber** prevents an existing file from being overwritten and displays a message that the file already exists.</span></span> <span data-ttu-id="0530b-185">Por padrão, se um arquivo existir no caminho especificado, `Out-File` o substituirá o arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="0530b-185">By default, if a file exists in the specified path, `Out-File` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="0530b-186">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="0530b-186">-NoNewline</span></span>

<span data-ttu-id="0530b-187">Especifica que o conteúdo gravado no arquivo não termina com um caractere de nova linha.</span><span class="sxs-lookup"><span data-stu-id="0530b-187">Specifies that the content written to the file does not end with a newline character.</span></span> <span data-ttu-id="0530b-188">As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída.</span><span class="sxs-lookup"><span data-stu-id="0530b-188">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="0530b-189">Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="0530b-189">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="0530b-190">Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="0530b-190">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="0530b-191">-Largura</span><span class="sxs-lookup"><span data-stu-id="0530b-191">-Width</span></span>

<span data-ttu-id="0530b-192">Especifica o número de caracteres em cada linha de saída.</span><span class="sxs-lookup"><span data-stu-id="0530b-192">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="0530b-193">Quaisquer eventuais caracteres adicionais ficam truncados, não encapsulados.</span><span class="sxs-lookup"><span data-stu-id="0530b-193">Any additional characters are truncated, not wrapped.</span></span> <span data-ttu-id="0530b-194">Se esse parâmetro não for usado, a largura será determinada pelas características do host.</span><span class="sxs-lookup"><span data-stu-id="0530b-194">If this parameter is not used, the width is determined by the characteristics of the host.</span></span> <span data-ttu-id="0530b-195">O padrão para o console do PowerShell é de 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="0530b-195">The default for the PowerShell console is 80 characters.</span></span>

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

### <span data-ttu-id="0530b-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0530b-196">-Confirm</span></span>

<span data-ttu-id="0530b-197">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0530b-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0530b-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0530b-198">-WhatIf</span></span>

<span data-ttu-id="0530b-199">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0530b-199">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0530b-200">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0530b-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0530b-201">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0530b-201">CommonParameters</span></span>

<span data-ttu-id="0530b-202">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0530b-202">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0530b-203">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0530b-203">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0530b-204">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0530b-204">INPUTS</span></span>

### <span data-ttu-id="0530b-205">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="0530b-205">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0530b-206">Você pode canalizar qualquer objeto para `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="0530b-206">You can pipe any object to `Out-File`.</span></span>

## <span data-ttu-id="0530b-207">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0530b-207">OUTPUTS</span></span>

### <span data-ttu-id="0530b-208">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0530b-208">None</span></span>

<span data-ttu-id="0530b-209">`Out-File` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="0530b-209">`Out-File` does not generate any output.</span></span>

## <span data-ttu-id="0530b-210">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0530b-210">NOTES</span></span>

<span data-ttu-id="0530b-211">Os objetos de entrada são formatados automaticamente como seriam no terminal, mas você pode usar um `Format-*` cmdlet para controlar explicitamente a formatação da saída para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="0530b-211">Input objects are automatically formatted as they would be in the terminal, but you can use a `Format-*` cmdlet to explicitly control the formatting of the output to the file.</span></span> <span data-ttu-id="0530b-212">Por exemplo, `Get-Date | Format-List | Out-File out.txt`</span><span class="sxs-lookup"><span data-stu-id="0530b-212">For example, `Get-Date | Format-List | Out-File out.txt`</span></span>

<span data-ttu-id="0530b-213">Para enviar a saída de um comando do PowerShell para o `Out-File` cmdlet, use o pipeline.</span><span class="sxs-lookup"><span data-stu-id="0530b-213">To send a PowerShell command's output to the `Out-File` cmdlet, use the pipeline.</span></span> <span data-ttu-id="0530b-214">Como alternativa, você pode armazenar dados em uma variável e usar o parâmetro **InputObject** para passar dados para o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0530b-214">Alternatively, you can store data in a variable and use the **InputObject** parameter to pass data to the `Out-File` cmdlet.</span></span>

<span data-ttu-id="0530b-215">`Out-File` salva dados em um arquivo, mas não produz nenhum objeto de saída para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="0530b-215">`Out-File` saves data to a file but it does not produce any output objects to the pipeline.</span></span>

## <span data-ttu-id="0530b-216">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0530b-216">RELATED LINKS</span></span>

[<span data-ttu-id="0530b-217">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0530b-217">about_Providers</span></span>](../Microsoft.Powershell.Core/About/about_Providers.md)

[<span data-ttu-id="0530b-218">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="0530b-218">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="0530b-219">Out-Default</span><span class="sxs-lookup"><span data-stu-id="0530b-219">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="0530b-220">Out-Host</span><span class="sxs-lookup"><span data-stu-id="0530b-220">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="0530b-221">Out-Null</span><span class="sxs-lookup"><span data-stu-id="0530b-221">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="0530b-222">Out-String</span><span class="sxs-lookup"><span data-stu-id="0530b-222">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="0530b-223">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="0530b-223">Tee-Object</span></span>](Tee-Object.md)

