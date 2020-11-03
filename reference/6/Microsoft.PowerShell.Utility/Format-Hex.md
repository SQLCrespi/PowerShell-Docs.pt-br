---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 64275e72f8c21942179431b3aed4a17d328aa2e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194497"
---
# <span data-ttu-id="847dd-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="847dd-103">Format-Hex</span></span>

## <span data-ttu-id="847dd-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="847dd-104">SYNOPSIS</span></span>

<span data-ttu-id="847dd-105">Exibe um arquivo ou outra entrada como hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="847dd-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="847dd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="847dd-106">SYNTAX</span></span>

### <span data-ttu-id="847dd-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="847dd-107">Path (Default)</span></span>

```
Format-Hex [-Path] <string[]> [-Count <long>] [-Offset <long>] [<CommonParameters>]
```

### <span data-ttu-id="847dd-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="847dd-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <string[]> [-Count <long>] [-Offset <long>] [<CommonParameters>]
```

### <span data-ttu-id="847dd-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="847dd-109">InputObject</span></span>

```
Format-Hex -InputObject <psobject> [-Encoding <Encoding>] [-Count <long>] [-Offset <long>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="847dd-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="847dd-110">DESCRIPTION</span></span>

<span data-ttu-id="847dd-111">O `Format-Hex` cmdlet exibe um arquivo ou outra entrada como valores hexadecimais.</span><span class="sxs-lookup"><span data-stu-id="847dd-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="847dd-112">Para determinar o deslocamento de um caractere da saída, adicione o número na extrema esquerda da linha ao número na parte superior da coluna para esse caractere.</span><span class="sxs-lookup"><span data-stu-id="847dd-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="847dd-113">O `Format-Hex` cmdlet pode ajudá-lo a determinar o tipo de arquivo de um arquivo corrompido ou um arquivo que pode não ter uma extensão filename.</span><span class="sxs-lookup"><span data-stu-id="847dd-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="847dd-114">Você pode executar esse cmdlet e, em seguida, ler a saída hexadecimal para obter informações do arquivo.</span><span class="sxs-lookup"><span data-stu-id="847dd-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="847dd-115">Ao usar `Format-Hex` em um arquivo, o cmdlet ignora os caracteres de nova linha e retorna todo o conteúdo de um arquivo em uma cadeia de caracteres com a nova linha preservada.</span><span class="sxs-lookup"><span data-stu-id="847dd-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="847dd-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="847dd-116">EXAMPLES</span></span>

### <span data-ttu-id="847dd-117">Exemplo 1: obter a representação hexadecimal de uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="847dd-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="847dd-118">Esse comando retorna os valores hexadecimais de uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="847dd-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

<span data-ttu-id="847dd-119">A cadeia de caracteres **Olá, mundo** é enviada ao pipeline para o `Format-Hex` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="847dd-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="847dd-120">A saída hexadecimal de `Format-Hex` mostra os valores de cada caractere na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="847dd-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="847dd-121">Exemplo 2: localizar um tipo de arquivo da saída hexadecimal</span><span class="sxs-lookup"><span data-stu-id="847dd-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="847dd-122">Este exemplo usa a saída hexadecimal para determinar o tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="847dd-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="847dd-123">O cmdlet exibe o caminho completo do arquivo e os valores hexadecimais.</span><span class="sxs-lookup"><span data-stu-id="847dd-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="847dd-124">Para testar o comando a seguir, faça uma cópia de um arquivo PDF existente no computador local e renomeie o arquivo copiado para `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="847dd-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to `File.t7f`.</span></span>

```powershell
Format-Hex -Path .\File.t7f
```

```Output
           Path: C:\Test\File.t7f

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D  %PDF-1.5..%????.
00000010   0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70  .1 0 obj..<</Typ
00000020   65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20  e/Catalog/Pages
```

<span data-ttu-id="847dd-125">O `Format-Hex` cmdlet usa o parâmetro **Path** para especificar um nome de arquivo no diretório atual, **File. t7f** .</span><span class="sxs-lookup"><span data-stu-id="847dd-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, **File.t7f** .</span></span> <span data-ttu-id="847dd-126">A extensão de arquivo **. t7f** é incomum, mas a saída hexadecimal **% PDF** mostra que se trata de um arquivo PDF.</span><span class="sxs-lookup"><span data-stu-id="847dd-126">The file extension **.t7f** is uncommon, but the hexadecimal output **%PDF** shows that it is a PDF file.</span></span>

## <span data-ttu-id="847dd-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="847dd-127">PARAMETERS</span></span>

### <span data-ttu-id="847dd-128">-Codificação</span><span class="sxs-lookup"><span data-stu-id="847dd-128">-Encoding</span></span>

<span data-ttu-id="847dd-129">Especifica a codificação da saída.</span><span class="sxs-lookup"><span data-stu-id="847dd-129">Specifies the encoding of the output.</span></span> <span data-ttu-id="847dd-130">Isso se aplica somente à `[string]` entrada.</span><span class="sxs-lookup"><span data-stu-id="847dd-130">This only applies to `[string]` input.</span></span> <span data-ttu-id="847dd-131">O parâmetro não tem nenhum efeito sobre tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="847dd-131">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="847dd-132">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="847dd-132">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="847dd-133">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="847dd-133">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="847dd-134">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="847dd-134">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="847dd-135">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="847dd-135">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="847dd-136">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="847dd-136">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="847dd-137">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="847dd-137">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="847dd-138">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="847dd-138">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="847dd-139">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="847dd-139">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="847dd-140">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="847dd-140">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="847dd-141">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="847dd-141">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="847dd-142">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="847dd-142">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="847dd-143">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="847dd-143">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="847dd-144">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="847dd-144">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="847dd-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="847dd-145">-InputObject</span></span>

<span data-ttu-id="847dd-146">Usado para entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="847dd-146">Used for pipeline input.</span></span> <span data-ttu-id="847dd-147">A entrada do pipeline dá suporte a apenas determinados tipos e instâncias escalares `[system.io.fileinfo]` para a tubulação `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="847dd-147">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="847dd-148">Os tipos escalares com suporte são:</span><span class="sxs-lookup"><span data-stu-id="847dd-148">The supported scalar types are:</span></span>

- <span data-ttu-id="847dd-149">`[string]`, `[char]`</span><span class="sxs-lookup"><span data-stu-id="847dd-149">`[string]`, `[char]`</span></span>
- <span data-ttu-id="847dd-150">`[byte]`, `[sbyte]`</span><span class="sxs-lookup"><span data-stu-id="847dd-150">`[byte]`, `[sbyte]`</span></span>
- <span data-ttu-id="847dd-151">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span><span class="sxs-lookup"><span data-stu-id="847dd-151">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span></span>
- <span data-ttu-id="847dd-152">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span><span class="sxs-lookup"><span data-stu-id="847dd-152">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span></span>
- <span data-ttu-id="847dd-153">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="847dd-153">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span></span>
- <span data-ttu-id="847dd-154">`[single]`, `[float]`, `[double]`</span><span class="sxs-lookup"><span data-stu-id="847dd-154">`[single]`, `[float]`, `[double]`</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="847dd-155">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="847dd-155">-LiteralPath</span></span>

<span data-ttu-id="847dd-156">Especifica o caminho completo para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="847dd-156">Specifies the complete path to a file.</span></span> <span data-ttu-id="847dd-157">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="847dd-157">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="847dd-158">Esse parâmetro não aceita caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="847dd-158">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="847dd-159">Para especificar vários caminhos para arquivos, separe os caminhos com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="847dd-159">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="847dd-160">Se o parâmetro **LiteralPath** incluir caracteres de escape, coloque o caminho entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="847dd-160">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="847dd-161">O PowerShell não interpreta nenhum caractere em uma única cadeia de caracteres entre aspas como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="847dd-161">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="847dd-162">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="847dd-162">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="847dd-163">-Path</span><span class="sxs-lookup"><span data-stu-id="847dd-163">-Path</span></span>

<span data-ttu-id="847dd-164">Especifica o caminho para os arquivos.</span><span class="sxs-lookup"><span data-stu-id="847dd-164">Specifies the path to files.</span></span> <span data-ttu-id="847dd-165">Use um ponto ( `.` ) para especificar o local atual.</span><span class="sxs-lookup"><span data-stu-id="847dd-165">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="847dd-166">O caractere curinga ( `*` ) é aceito e pode ser usado para especificar todos os itens em um local.</span><span class="sxs-lookup"><span data-stu-id="847dd-166">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="847dd-167">Se o parâmetro **path** incluir caracteres de escape, coloque o caminho entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="847dd-167">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="847dd-168">Para especificar vários caminhos para arquivos, separe os caminhos com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="847dd-168">To specify multiple paths to files, separate the paths with a comma.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="847dd-169">-RAW</span><span class="sxs-lookup"><span data-stu-id="847dd-169">-Raw</span></span>

<span data-ttu-id="847dd-170">Esse parâmetro não faz mais nada.</span><span class="sxs-lookup"><span data-stu-id="847dd-170">This parameter no longer does anything.</span></span> <span data-ttu-id="847dd-171">Ele é retido para compatibilidade de script.</span><span class="sxs-lookup"><span data-stu-id="847dd-171">It is retained for script compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="847dd-172">-Deslocamento</span><span class="sxs-lookup"><span data-stu-id="847dd-172">-Offset</span></span>

<span data-ttu-id="847dd-173">Isso representa o número de bytes a serem ignorados, sendo parte da saída de hex.</span><span class="sxs-lookup"><span data-stu-id="847dd-173">This represents the number of bytes to skip from being part of the hex output.</span></span>

<span data-ttu-id="847dd-174">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="847dd-174">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="847dd-175">-Contagem</span><span class="sxs-lookup"><span data-stu-id="847dd-175">-Count</span></span>

<span data-ttu-id="847dd-176">Isso representa o número de bytes a serem incluídos na saída hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="847dd-176">This represents the number of bytes to include in the hex output.</span></span>

<span data-ttu-id="847dd-177">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="847dd-177">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Int64.MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="847dd-178">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="847dd-178">CommonParameters</span></span>

<span data-ttu-id="847dd-179">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="847dd-179">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="847dd-180">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="847dd-180">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="847dd-181">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="847dd-181">INPUTS</span></span>

### <span data-ttu-id="847dd-182">System.String</span><span class="sxs-lookup"><span data-stu-id="847dd-182">System.String</span></span>

<span data-ttu-id="847dd-183">É possível canalizar uma cadeia de caracteres para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="847dd-183">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="847dd-184">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="847dd-184">OUTPUTS</span></span>

### <span data-ttu-id="847dd-185">Microsoft. PowerShell. Commands. Bytecollection</span><span class="sxs-lookup"><span data-stu-id="847dd-185">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="847dd-186">Esse cmdlet retorna um **bytecollection** .</span><span class="sxs-lookup"><span data-stu-id="847dd-186">This cmdlet returns a **ByteCollection** .</span></span> <span data-ttu-id="847dd-187">Esse objeto representa uma coleção de bytes.</span><span class="sxs-lookup"><span data-stu-id="847dd-187">This object represents a collection of bytes.</span></span> <span data-ttu-id="847dd-188">Ele inclui métodos que convertem a coleção de bytes em uma cadeia de caracteres formatada como cada linha de saída retornada por `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="847dd-188">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="847dd-189">Se você especificar o **caminho** ou o parâmetro **LiteralPath** , o objeto também conterá o caminho do arquivo que contém cada byte.</span><span class="sxs-lookup"><span data-stu-id="847dd-189">If you specify the **Path** or **LiteralPath** parameter, the object also contains the path of the file that contains each byte.</span></span>

## <span data-ttu-id="847dd-190">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="847dd-190">NOTES</span></span>

<span data-ttu-id="847dd-191">A coluna mais à direita da saída tenta renderizar os bytes como caracteres ASCII:</span><span class="sxs-lookup"><span data-stu-id="847dd-191">The right-most column of output tries to render the bytes as ASCII characters:</span></span>

<span data-ttu-id="847dd-192">Em geral, cada byte é interpretado como um ponto de código Unicode, o que significa que:</span><span class="sxs-lookup"><span data-stu-id="847dd-192">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="847dd-193">Caracteres ASCII imprimíveis sempre são renderizados corretamente</span><span class="sxs-lookup"><span data-stu-id="847dd-193">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="847dd-194">Caracteres UTF-8 de vários bytes nunca são renderizados corretamente</span><span class="sxs-lookup"><span data-stu-id="847dd-194">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="847dd-195">Os caracteres UTF-16 são renderizados corretamente apenas se o byte de ordem superior acontece `NUL` .</span><span class="sxs-lookup"><span data-stu-id="847dd-195">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="847dd-196">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="847dd-196">RELATED LINKS</span></span>

[<span data-ttu-id="847dd-197">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="847dd-197">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="847dd-198">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="847dd-198">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="847dd-199">Format-List</span><span class="sxs-lookup"><span data-stu-id="847dd-199">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="847dd-200">Format-Table</span><span class="sxs-lookup"><span data-stu-id="847dd-200">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="847dd-201">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="847dd-201">Format-Wide</span></span>](Format-Wide.md)
