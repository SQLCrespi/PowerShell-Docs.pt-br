---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: 71602cb0621c835257f556a0a9db15bd754a3aee
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "93195354"
---
# <span data-ttu-id="18419-103">Out-File</span><span class="sxs-lookup"><span data-stu-id="18419-103">Out-File</span></span>

## <span data-ttu-id="18419-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="18419-104">SYNOPSIS</span></span>
<span data-ttu-id="18419-105">Envia a saída para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="18419-105">Sends output to a file.</span></span>

## <span data-ttu-id="18419-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="18419-106">SYNTAX</span></span>

### <span data-ttu-id="18419-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="18419-107">ByPath (Default)</span></span>

```
Out-File [-FilePath] <string> [[-Encoding] <string>] [-Append] [-Force] [-NoClobber] [-Width <int>]
 [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="18419-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="18419-108">ByLiteralPath</span></span>

```
Out-File [[-Encoding] <string>] -LiteralPath <string> [-Append] [-Force] [-NoClobber] [-Width <int>]
 [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="18419-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="18419-109">DESCRIPTION</span></span>

<span data-ttu-id="18419-110">O `Out-File` cmdlet envia a saída para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="18419-110">The `Out-File` cmdlet sends output to a file.</span></span> <span data-ttu-id="18419-111">Ele usa implicitamente o sistema de formatação do PowerShell para gravar no arquivo.</span><span class="sxs-lookup"><span data-stu-id="18419-111">It implicitly uses PowerShell's formatting system to write to the file.</span></span> <span data-ttu-id="18419-112">O arquivo recebe a mesma representação de exibição que o terminal.</span><span class="sxs-lookup"><span data-stu-id="18419-112">The file receives the same display representation as the terminal.</span></span> <span data-ttu-id="18419-113">Isso significa que a saída pode não ser ideal para processamento programático, a menos que todos os objetos de entrada sejam cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="18419-113">This means that the output may not be ideal for programmatic processing unless all input objects are strings.</span></span>
<span data-ttu-id="18419-114">Quando você precisar especificar parâmetros para a saída, use `Out-File` em vez do operador de redirecionamento ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="18419-114">When you need to specify parameters for the output, use `Out-File` rather than the redirection operator (`>`).</span></span> <span data-ttu-id="18419-115">Para obter mais informações sobre o redirecionamento, consulte [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span><span class="sxs-lookup"><span data-stu-id="18419-115">For more information about redirection, see [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span></span>

## <span data-ttu-id="18419-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="18419-116">EXAMPLES</span></span>

### <span data-ttu-id="18419-117">Exemplo 1: enviar a saída e criar um arquivo</span><span class="sxs-lookup"><span data-stu-id="18419-117">Example 1: Send output and create a file</span></span>

<span data-ttu-id="18419-118">Este exemplo mostra como enviar uma lista de processos do computador local para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="18419-118">This example shows how to send a list of the local computer's processes to a file.</span></span> <span data-ttu-id="18419-119">Se o arquivo não existir, o `Out-File` criará o arquivo no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="18419-119">If the file does not exist, `Out-File` creates the file in the specified path.</span></span>

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

<span data-ttu-id="18419-120">O `Get-Process` cmdlet obtém a lista de processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="18419-120">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="18419-121">Os objetos de **processo** são enviados por meio do pipeline para o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18419-121">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="18419-122">`Out-File` usa o parâmetro **FilePath** e cria um arquivo no diretório atual chamado **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="18419-122">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="18419-123">O `Get-Content` comando obtém o conteúdo do arquivo e o exibe no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18419-123">The `Get-Content` command gets content from the file and displays it in the PowerShell console.</span></span>

### <span data-ttu-id="18419-124">Exemplo 2: impedir que um arquivo existente seja substituído</span><span class="sxs-lookup"><span data-stu-id="18419-124">Example 2: Prevent an existing file from being overwritten</span></span>

<span data-ttu-id="18419-125">Este exemplo impede que um arquivo existente seja substituído.</span><span class="sxs-lookup"><span data-stu-id="18419-125">This example prevents an existing file from being overwritten.</span></span> <span data-ttu-id="18419-126">Por padrão, o `Out-File` substitui os arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="18419-126">By default, `Out-File` overwrites existing files.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

<span data-ttu-id="18419-127">O `Get-Process` cmdlet obtém a lista de processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="18419-127">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="18419-128">Os objetos de **processo** são enviados por meio do pipeline para o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18419-128">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="18419-129">`Out-File` usa o parâmetro **FilePath** e tenta gravar em um arquivo no diretório atual chamado **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="18419-129">`Out-File` uses the **FilePath** parameter and attempts to write to a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="18419-130">O parâmetro **NoClobber** impede que o arquivo seja substituído e exibe uma mensagem informando que o arquivo já existe.</span><span class="sxs-lookup"><span data-stu-id="18419-130">The **NoClobber** parameter prevents the file from being overwritten and displays a message that the file already exists.</span></span>

### <span data-ttu-id="18419-131">Exemplo 3: enviar a saída para um arquivo no formato ASCII</span><span class="sxs-lookup"><span data-stu-id="18419-131">Example 3: Send output to a file in ASCII format</span></span>

<span data-ttu-id="18419-132">Este exemplo mostra como codificar a saída com um tipo de codificação específico.</span><span class="sxs-lookup"><span data-stu-id="18419-132">This example shows how to encode output with a specific encoding type.</span></span>

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

<span data-ttu-id="18419-133">O `Get-Process` cmdlet obtém a lista de processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="18419-133">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="18419-134">Os objetos de **processo** são armazenados na variável, `$Procs` .</span><span class="sxs-lookup"><span data-stu-id="18419-134">The **Process** objects are stored in the variable, `$Procs`.</span></span> <span data-ttu-id="18419-135">`Out-File` usa o parâmetro **FilePath** e cria um arquivo no diretório atual chamado **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="18419-135">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="18419-136">O parâmetro **InputObject** passa os objetos de processo `$Procs` para o arquivo **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="18419-136">The **InputObject** parameter passes the process objects in `$Procs` to the file **Process.txt** .</span></span> <span data-ttu-id="18419-137">O parâmetro **Encoding** converte a saída para o formato **ASCII** .</span><span class="sxs-lookup"><span data-stu-id="18419-137">The **Encoding** parameter converts the output to **ASCII** format.</span></span> <span data-ttu-id="18419-138">O parâmetro **Width** limita cada linha no arquivo a 50 caracteres, de modo que alguns dados possam ser truncados.</span><span class="sxs-lookup"><span data-stu-id="18419-138">The **Width** parameter limits each line in the file to 50 characters so some data might be truncated.</span></span>

### <span data-ttu-id="18419-139">Exemplo 4: usar um provedor e enviar a saída para um arquivo</span><span class="sxs-lookup"><span data-stu-id="18419-139">Example 4: Use a provider and send output to a file</span></span>

<span data-ttu-id="18419-140">Este exemplo mostra como usar o `Out-File` cmdlet quando você não está em uma unidade do provedor **FileSystem** .</span><span class="sxs-lookup"><span data-stu-id="18419-140">This example shows how to use the `Out-File` cmdlet when you are not in a **FileSystem** provider drive.</span></span> <span data-ttu-id="18419-141">Use o `Get-PSProvider` cmdlet para exibir os provedores em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="18419-141">Use the `Get-PSProvider` cmdlet to view the providers on your local computer.</span></span> <span data-ttu-id="18419-142">Para obter mais informações, consulte [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="18419-142">For more information, see [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span></span>

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

<span data-ttu-id="18419-143">O `Set-Location` comando usa o parâmetro **Path** para definir o local atual como o provedor de registro `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="18419-143">The `Set-Location` command uses the **Path** parameter to set the current location to the registry provider `Alias:`.</span></span> <span data-ttu-id="18419-144">O `Get-Location` cmdlet exibe o caminho completo para `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="18419-144">The `Get-Location` cmdlet displays the complete path for `Alias:`.</span></span>
<span data-ttu-id="18419-145">`Get-ChildItem` envia objetos pelo pipeline para o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18419-145">`Get-ChildItem` sends objects down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="18419-146">`Out-File` usa o parâmetro **FilePath** para especificar o caminho e o nome de arquivo completos para a saída, **C:\TestDir\AliasNames.txt** .</span><span class="sxs-lookup"><span data-stu-id="18419-146">`Out-File` uses the **FilePath** parameter to specify the complete path and filename for the output, **C:\TestDir\AliasNames.txt** .</span></span> <span data-ttu-id="18419-147">O `Get-Content` cmdlet usa o parâmetro **Path** e exibe o conteúdo do arquivo no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18419-147">The `Get-Content` cmdlet uses the **Path** parameter and displays the file's content in the PowerShell console.</span></span>

## <span data-ttu-id="18419-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="18419-148">PARAMETERS</span></span>

### <span data-ttu-id="18419-149">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="18419-149">-Append</span></span>

<span data-ttu-id="18419-150">Adiciona a saída ao final de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="18419-150">Adds the output to the end of an existing file.</span></span> <span data-ttu-id="18419-151">Se nenhuma **codificação** for especificada, o cmdlet usará a codificação padrão.</span><span class="sxs-lookup"><span data-stu-id="18419-151">If no **Encoding** is specified, the cmdlet uses the default encoding.</span></span> <span data-ttu-id="18419-152">Essa codificação pode não corresponder à codificação do arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="18419-152">That encoding may not match the encoding of the target file.</span></span> <span data-ttu-id="18419-153">Esse é o mesmo comportamento que o operador de redirecionamento ( `>>` ).</span><span class="sxs-lookup"><span data-stu-id="18419-153">This is the same behavior as the redirection operator (`>>`).</span></span>

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

### <span data-ttu-id="18419-154">-Codificação</span><span class="sxs-lookup"><span data-stu-id="18419-154">-Encoding</span></span>

<span data-ttu-id="18419-155">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="18419-155">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="18419-156">O valor padrão é `unicode`.</span><span class="sxs-lookup"><span data-stu-id="18419-156">The default value is `unicode`.</span></span>

<span data-ttu-id="18419-157">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18419-157">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="18419-158">`ascii` Usa conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="18419-158">`ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="18419-159">`bigendianunicode` Usa UTF-16 com a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="18419-159">`bigendianunicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="18419-160">`default` Usa a codificação que corresponde à página de código ativa do sistema (geralmente ANSI).</span><span class="sxs-lookup"><span data-stu-id="18419-160">`default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="18419-161">`oem` Usa a codificação que corresponde à página de código OEM atual do sistema.</span><span class="sxs-lookup"><span data-stu-id="18419-161">`oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="18419-162">`string` Igual a `unicode`.</span><span class="sxs-lookup"><span data-stu-id="18419-162">`string` Same as `unicode`.</span></span>
- <span data-ttu-id="18419-163">`unicode` Usa UTF-16 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="18419-163">`unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="18419-164">`unknown` Igual a `unicode`.</span><span class="sxs-lookup"><span data-stu-id="18419-164">`unknown` Same as `unicode`.</span></span>
- <span data-ttu-id="18419-165">`utf7` Usa UTF-7.</span><span class="sxs-lookup"><span data-stu-id="18419-165">`utf7` Uses UTF-7.</span></span>
- <span data-ttu-id="18419-166">`utf8` Usa UTF-8.</span><span class="sxs-lookup"><span data-stu-id="18419-166">`utf8` Uses UTF-8.</span></span>
- <span data-ttu-id="18419-167">`utf32` Usa UTF-32 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="18419-167">`utf32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: 1
Default value: Unicode
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18419-168">-FilePath</span><span class="sxs-lookup"><span data-stu-id="18419-168">-FilePath</span></span>

<span data-ttu-id="18419-169">Especifica o caminho para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="18419-169">Specifies the path to the output file.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18419-170">-Force</span><span class="sxs-lookup"><span data-stu-id="18419-170">-Force</span></span>

<span data-ttu-id="18419-171">Substitui o atributo somente leitura e sobrescreve um arquivo somente leitura existente.</span><span class="sxs-lookup"><span data-stu-id="18419-171">Overrides the read-only attribute and overwrites an existing read-only file.</span></span> <span data-ttu-id="18419-172">O parâmetro **Force** não substitui as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="18419-172">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="18419-173">-InputObject</span><span class="sxs-lookup"><span data-stu-id="18419-173">-InputObject</span></span>

<span data-ttu-id="18419-174">Especifica os objetos a serem gravados no arquivo.</span><span class="sxs-lookup"><span data-stu-id="18419-174">Specifies the objects to be written to the file.</span></span> <span data-ttu-id="18419-175">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="18419-175">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="18419-176">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="18419-176">-LiteralPath</span></span>

<span data-ttu-id="18419-177">Especifica o caminho para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="18419-177">Specifies the path to the output file.</span></span> <span data-ttu-id="18419-178">O parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="18419-178">The **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="18419-179">Caracteres curinga não são aceitos.</span><span class="sxs-lookup"><span data-stu-id="18419-179">Wildcard characters are not accepted.</span></span> <span data-ttu-id="18419-180">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="18419-180">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="18419-181">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="18419-181">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="18419-182">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="18419-182">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="18419-183">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="18419-183">-NoClobber</span></span>

<span data-ttu-id="18419-184">**NoClobber** impede que um arquivo existente seja substituído e exibe uma mensagem informando que o arquivo já existe.</span><span class="sxs-lookup"><span data-stu-id="18419-184">**NoClobber** prevents an existing file from being overwritten and displays a message that the file already exists.</span></span> <span data-ttu-id="18419-185">Por padrão, se um arquivo existir no caminho especificado, `Out-File` o substituirá o arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="18419-185">By default, if a file exists in the specified path, `Out-File` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="18419-186">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="18419-186">-NoNewline</span></span>

<span data-ttu-id="18419-187">Especifica que o conteúdo gravado no arquivo não termina com um caractere de nova linha.</span><span class="sxs-lookup"><span data-stu-id="18419-187">Specifies that the content written to the file does not end with a newline character.</span></span> <span data-ttu-id="18419-188">As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída.</span><span class="sxs-lookup"><span data-stu-id="18419-188">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="18419-189">Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="18419-189">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="18419-190">Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="18419-190">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="18419-191">-Largura</span><span class="sxs-lookup"><span data-stu-id="18419-191">-Width</span></span>

<span data-ttu-id="18419-192">Especifica o número de caracteres em cada linha de saída.</span><span class="sxs-lookup"><span data-stu-id="18419-192">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="18419-193">Quaisquer eventuais caracteres adicionais ficam truncados, não encapsulados.</span><span class="sxs-lookup"><span data-stu-id="18419-193">Any additional characters are truncated, not wrapped.</span></span> <span data-ttu-id="18419-194">Se esse parâmetro não for usado, a largura será determinada pelas características do host.</span><span class="sxs-lookup"><span data-stu-id="18419-194">If this parameter is not used, the width is determined by the characteristics of the host.</span></span> <span data-ttu-id="18419-195">O padrão para o console do PowerShell é de 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="18419-195">The default for the PowerShell console is 80 characters.</span></span>

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

### <span data-ttu-id="18419-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="18419-196">-Confirm</span></span>

<span data-ttu-id="18419-197">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18419-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="18419-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="18419-198">-WhatIf</span></span>

<span data-ttu-id="18419-199">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="18419-199">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="18419-200">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="18419-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="18419-201">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="18419-201">CommonParameters</span></span>

<span data-ttu-id="18419-202">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="18419-202">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="18419-203">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="18419-203">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="18419-204">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="18419-204">INPUTS</span></span>

### <span data-ttu-id="18419-205">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="18419-205">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="18419-206">Você pode canalizar qualquer objeto para `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="18419-206">You can pipe any object to `Out-File`.</span></span>

## <span data-ttu-id="18419-207">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="18419-207">OUTPUTS</span></span>

### <span data-ttu-id="18419-208">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18419-208">None</span></span>

<span data-ttu-id="18419-209">`Out-File` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="18419-209">`Out-File` does not generate any output.</span></span>

## <span data-ttu-id="18419-210">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="18419-210">NOTES</span></span>

<span data-ttu-id="18419-211">Os objetos de entrada são formatados automaticamente como seriam no terminal, mas você pode usar um `Format-*` cmdlet para controlar explicitamente a formatação da saída para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="18419-211">Input objects are automatically formatted as they would be in the terminal, but you can use a `Format-*` cmdlet to explicitly control the formatting of the output to the file.</span></span> <span data-ttu-id="18419-212">Por exemplo, `Get-Date | Format-List | Out-File out.txt`</span><span class="sxs-lookup"><span data-stu-id="18419-212">For example, `Get-Date | Format-List | Out-File out.txt`</span></span>

<span data-ttu-id="18419-213">Para enviar a saída de um comando do PowerShell para o `Out-File` cmdlet, use o pipeline.</span><span class="sxs-lookup"><span data-stu-id="18419-213">To send a PowerShell command's output to the `Out-File` cmdlet, use the pipeline.</span></span> <span data-ttu-id="18419-214">Como alternativa, você pode armazenar dados em uma variável e usar o parâmetro **InputObject** para passar dados para o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18419-214">Alternatively, you can store data in a variable and use the **InputObject** parameter to pass data to the `Out-File` cmdlet.</span></span>

<span data-ttu-id="18419-215">`Out-File` salva dados em um arquivo, mas não produz nenhum objeto de saída para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="18419-215">`Out-File` saves data to a file but it does not produce any output objects to the pipeline.</span></span>

## <span data-ttu-id="18419-216">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="18419-216">RELATED LINKS</span></span>

[<span data-ttu-id="18419-217">about_Providers</span><span class="sxs-lookup"><span data-stu-id="18419-217">about_Providers</span></span>](../Microsoft.Powershell.Core/About/about_Providers.md)

[<span data-ttu-id="18419-218">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="18419-218">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="18419-219">Out-Default</span><span class="sxs-lookup"><span data-stu-id="18419-219">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="18419-220">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="18419-220">Out-GridView</span></span>](Out-GridView.md)

[<span data-ttu-id="18419-221">Out-Host</span><span class="sxs-lookup"><span data-stu-id="18419-221">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="18419-222">Out-Null</span><span class="sxs-lookup"><span data-stu-id="18419-222">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="18419-223">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="18419-223">Out-Printer</span></span>](Out-Printer.md)

[<span data-ttu-id="18419-224">Out-String</span><span class="sxs-lookup"><span data-stu-id="18419-224">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="18419-225">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="18419-225">Tee-Object</span></span>](Tee-Object.md)
