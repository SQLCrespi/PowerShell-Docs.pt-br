---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 514a66ebee3827de998622a738c75d4f8e0c7279
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193823"
---
# <span data-ttu-id="b947a-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="b947a-103">Format-Hex</span></span>

## <span data-ttu-id="b947a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b947a-104">SYNOPSIS</span></span>

<span data-ttu-id="b947a-105">Exibe um arquivo ou outra entrada como hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="b947a-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="b947a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b947a-106">SYNTAX</span></span>

### <span data-ttu-id="b947a-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="b947a-107">Path (Default)</span></span>

```
Format-Hex [-Path] <string[]> [<CommonParameters>]
```

### <span data-ttu-id="b947a-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b947a-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <string[]> [<CommonParameters>]
```

### <span data-ttu-id="b947a-109">ByInputObject</span><span class="sxs-lookup"><span data-stu-id="b947a-109">ByInputObject</span></span>

```
Format-Hex -InputObject <Object> [-Encoding <string>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="b947a-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b947a-110">DESCRIPTION</span></span>

<span data-ttu-id="b947a-111">O `Format-Hex` cmdlet exibe um arquivo ou outra entrada como valores hexadecimais.</span><span class="sxs-lookup"><span data-stu-id="b947a-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="b947a-112">Para determinar o deslocamento de um caractere da saída, adicione o número na extrema esquerda da linha ao número na parte superior da coluna para esse caractere.</span><span class="sxs-lookup"><span data-stu-id="b947a-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="b947a-113">O `Format-Hex` cmdlet pode ajudá-lo a determinar o tipo de arquivo de um arquivo corrompido ou um arquivo que pode não ter uma extensão filename.</span><span class="sxs-lookup"><span data-stu-id="b947a-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="b947a-114">Você pode executar esse cmdlet e, em seguida, ler a saída hexadecimal para obter informações do arquivo.</span><span class="sxs-lookup"><span data-stu-id="b947a-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="b947a-115">Ao usar `Format-Hex` em um arquivo, o cmdlet ignora os caracteres de nova linha e retorna todo o conteúdo de um arquivo em uma cadeia de caracteres com a nova linha preservada.</span><span class="sxs-lookup"><span data-stu-id="b947a-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="b947a-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b947a-116">EXAMPLES</span></span>

### <span data-ttu-id="b947a-117">Exemplo 1: obter a representação hexadecimal de uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b947a-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="b947a-118">Esse comando retorna os valores hexadecimais de uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b947a-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

<span data-ttu-id="b947a-119">A cadeia de caracteres **Olá, mundo** é enviada ao pipeline para o `Format-Hex` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b947a-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="b947a-120">A saída hexadecimal de `Format-Hex` mostra os valores de cada caractere na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b947a-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="b947a-121">Exemplo 2: localizar um tipo de arquivo da saída hexadecimal</span><span class="sxs-lookup"><span data-stu-id="b947a-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="b947a-122">Este exemplo usa a saída hexadecimal para determinar o tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b947a-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="b947a-123">O cmdlet exibe o caminho completo do arquivo e os valores hexadecimais.</span><span class="sxs-lookup"><span data-stu-id="b947a-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="b947a-124">Para testar o comando a seguir, faça uma cópia de um arquivo PDF existente no computador local e renomeie o arquivo copiado para **File. t7f** .</span><span class="sxs-lookup"><span data-stu-id="b947a-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to **File.t7f** .</span></span>

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

<span data-ttu-id="b947a-125">O `Format-Hex` cmdlet usa o parâmetro **Path** para especificar um nome de arquivo no diretório atual, `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="b947a-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, `File.t7f`.</span></span> <span data-ttu-id="b947a-126">A extensão do arquivo `.t7f` não é comum, mas a saída hexadecimal `%PDF` mostra que se trata de um arquivo PDF.</span><span class="sxs-lookup"><span data-stu-id="b947a-126">The file extension `.t7f` is uncommon, but the hexadecimal output `%PDF` shows that it is a PDF file.</span></span>

### <span data-ttu-id="b947a-127">Exemplo 3: Exibir saída hexadecimal bruta</span><span class="sxs-lookup"><span data-stu-id="b947a-127">Example 3: Display raw hexadecimal output</span></span>

<span data-ttu-id="b947a-128">Por padrão, o é `Format-Hex` usado para a saída compacta de tipos de dados numéricos: sequências de byte único ou de byte duplo são usadas se o valor for pequeno o suficiente.</span><span class="sxs-lookup"><span data-stu-id="b947a-128">By default `Format-Hex` opts for compact output of numeric data types: single-byte or double-byte sequences are used if the value is small enough.</span></span> <span data-ttu-id="b947a-129">O parâmetro **RAW** desativa esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="b947a-129">The **Raw** parameter deactivates this behavior.</span></span>

```
PS> 1,2,3,1000 | Format-Hex

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 02 03 E8 03                                   ...è.


PS> 1,2,3,1000 | Format-Hex -Raw

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 00 00 00 02 00 00 00 03 00 00 00 E8 03 00 00  ............è...
```

<span data-ttu-id="b947a-130">Observe a diferença na saída.</span><span class="sxs-lookup"><span data-stu-id="b947a-130">Notice the difference in output.</span></span> <span data-ttu-id="b947a-131">O parâmetro **RAW** exibe os números como valores de 4 bytes, verdadeiros para seus tipos **Int32** .</span><span class="sxs-lookup"><span data-stu-id="b947a-131">The **Raw** parameter displays the numbers as 4-byte values, true to their **Int32** types.</span></span>

## <span data-ttu-id="b947a-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b947a-132">PARAMETERS</span></span>

### <span data-ttu-id="b947a-133">-Codificação</span><span class="sxs-lookup"><span data-stu-id="b947a-133">-Encoding</span></span>

<span data-ttu-id="b947a-134">Especifica a codificação da saída.</span><span class="sxs-lookup"><span data-stu-id="b947a-134">Specifies the encoding of the output.</span></span> <span data-ttu-id="b947a-135">Isso se aplica somente à `[string]` entrada.</span><span class="sxs-lookup"><span data-stu-id="b947a-135">This only applies to `[string]` input.</span></span> <span data-ttu-id="b947a-136">O parâmetro não tem nenhum efeito sobre tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="b947a-136">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="b947a-137">O valor padrão é `ASCII`.</span><span class="sxs-lookup"><span data-stu-id="b947a-137">The default value is `ASCII`.</span></span>

<span data-ttu-id="b947a-138">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="b947a-138">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="b947a-139">`Ascii` Usa conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="b947a-139">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="b947a-140">`BigEndianUnicode` Usa UTF-16 com a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="b947a-140">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="b947a-141">`Unicode` Usa UTF-16 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="b947a-141">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="b947a-142">`UTF7` Usa UTF-7.</span><span class="sxs-lookup"><span data-stu-id="b947a-142">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="b947a-143">`UTF8` Usa UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b947a-143">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="b947a-144">`UTF32` Usa UTF-32 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="b947a-144">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="b947a-145">Os caracteres não ASCII na entrada são gerados como caracteres literais, `?` resultando em uma perda de informações.</span><span class="sxs-lookup"><span data-stu-id="b947a-145">Non-ASCII characters in the input are output as literal `?` characters resulting in a loss of information.</span></span>

```yaml
Type: System.String
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b947a-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b947a-146">-InputObject</span></span>

<span data-ttu-id="b947a-147">Usado para entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="b947a-147">Used for pipeline input.</span></span> <span data-ttu-id="b947a-148">A entrada do pipeline dá suporte a apenas determinados tipos e instâncias escalares `[system.io.fileinfo]` para a tubulação `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="b947a-148">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="b947a-149">Os tipos escalares com suporte são:</span><span class="sxs-lookup"><span data-stu-id="b947a-149">The supported scalar types are:</span></span>

- `[string]`
- `[byte]`
- <span data-ttu-id="b947a-150">`[int]`, `[int32]`</span><span class="sxs-lookup"><span data-stu-id="b947a-150">`[int]`, `[int32]`</span></span>
- <span data-ttu-id="b947a-151">`[long]`, `[int64]`</span><span class="sxs-lookup"><span data-stu-id="b947a-151">`[long]`, `[int64]`</span></span>

```yaml
Type: System.Object
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b947a-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b947a-152">-LiteralPath</span></span>

<span data-ttu-id="b947a-153">Especifica o caminho completo para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b947a-153">Specifies the complete path to a file.</span></span> <span data-ttu-id="b947a-154">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="b947a-154">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="b947a-155">Esse parâmetro não aceita caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="b947a-155">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="b947a-156">Para especificar vários caminhos para arquivos, separe os caminhos com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="b947a-156">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="b947a-157">Se o parâmetro **LiteralPath** incluir caracteres de escape, coloque o caminho entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="b947a-157">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="b947a-158">O PowerShell não interpreta nenhum caractere em uma única cadeia de caracteres entre aspas como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="b947a-158">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="b947a-159">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="b947a-159">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b947a-160">-Path</span><span class="sxs-lookup"><span data-stu-id="b947a-160">-Path</span></span>

<span data-ttu-id="b947a-161">Especifica o caminho para os arquivos.</span><span class="sxs-lookup"><span data-stu-id="b947a-161">Specifies the path to files.</span></span> <span data-ttu-id="b947a-162">Use um ponto ( `.` ) para especificar o local atual.</span><span class="sxs-lookup"><span data-stu-id="b947a-162">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="b947a-163">O caractere curinga ( `*` ) é aceito e pode ser usado para especificar todos os itens em um local.</span><span class="sxs-lookup"><span data-stu-id="b947a-163">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="b947a-164">Se o parâmetro **path** incluir caracteres de escape, coloque o caminho entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="b947a-164">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="b947a-165">Para especificar vários caminhos para arquivos, separe os caminhos com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="b947a-165">To specify multiple paths to files, separate the paths with a comma.</span></span>

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

### <span data-ttu-id="b947a-166">-RAW</span><span class="sxs-lookup"><span data-stu-id="b947a-166">-Raw</span></span>

<span data-ttu-id="b947a-167">Por padrão, o é `Format-Hex` usado para a saída compacta de tipos de dados numéricos: sequências de byte único ou de byte duplo são usadas se o valor for pequeno o suficiente.</span><span class="sxs-lookup"><span data-stu-id="b947a-167">By default `Format-Hex` opts for compact output of numeric data types: single-byte or double-byte sequences are used if the value is small enough.</span></span> <span data-ttu-id="b947a-168">O parâmetro **RAW** desativa esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="b947a-168">The **Raw** parameter deactivates this behavior.</span></span>

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

### <span data-ttu-id="b947a-169">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b947a-169">CommonParameters</span></span>

<span data-ttu-id="b947a-170">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b947a-170">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b947a-171">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b947a-171">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b947a-172">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b947a-172">INPUTS</span></span>

### <span data-ttu-id="b947a-173">System.String</span><span class="sxs-lookup"><span data-stu-id="b947a-173">System.String</span></span>

<span data-ttu-id="b947a-174">É possível canalizar uma cadeia de caracteres para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b947a-174">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="b947a-175">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b947a-175">OUTPUTS</span></span>

### <span data-ttu-id="b947a-176">Microsoft. PowerShell. Commands. Bytecollection</span><span class="sxs-lookup"><span data-stu-id="b947a-176">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="b947a-177">Esse cmdlet retorna um **bytecollection** .</span><span class="sxs-lookup"><span data-stu-id="b947a-177">This cmdlet returns a **ByteCollection** .</span></span> <span data-ttu-id="b947a-178">Esse objeto representa uma coleção de bytes.</span><span class="sxs-lookup"><span data-stu-id="b947a-178">This object represents a collection of bytes.</span></span> <span data-ttu-id="b947a-179">Ele inclui métodos que convertem a coleção de bytes em uma cadeia de caracteres formatada como cada linha de saída retornada por `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="b947a-179">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="b947a-180">Se você especificar o **caminho** ou o parâmetro **LiteralPath** , o objeto também conterá o caminho do arquivo que contém cada byte.</span><span class="sxs-lookup"><span data-stu-id="b947a-180">If you specify the **Path** or **LiteralPath** parameter, the object also contains the path of the file that contains each byte.</span></span>

## <span data-ttu-id="b947a-181">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b947a-181">NOTES</span></span>

<span data-ttu-id="b947a-182">A coluna mais à direita da saída tenta renderizar os bytes como caracteres:</span><span class="sxs-lookup"><span data-stu-id="b947a-182">The right-most column of output tries to render the bytes as characters:</span></span>

<span data-ttu-id="b947a-183">Em geral, cada byte é interpretado como um ponto de código Unicode, o que significa que:</span><span class="sxs-lookup"><span data-stu-id="b947a-183">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="b947a-184">Caracteres ASCII imprimíveis sempre são renderizados corretamente</span><span class="sxs-lookup"><span data-stu-id="b947a-184">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="b947a-185">Caracteres UTF-8 de vários bytes nunca são renderizados corretamente</span><span class="sxs-lookup"><span data-stu-id="b947a-185">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="b947a-186">Os caracteres UTF-16 são renderizados corretamente apenas se o byte de ordem superior acontece `NUL` .</span><span class="sxs-lookup"><span data-stu-id="b947a-186">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="b947a-187">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b947a-187">RELATED LINKS</span></span>

[<span data-ttu-id="b947a-188">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="b947a-188">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="b947a-189">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="b947a-189">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="b947a-190">Format-List</span><span class="sxs-lookup"><span data-stu-id="b947a-190">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="b947a-191">Format-Table</span><span class="sxs-lookup"><span data-stu-id="b947a-191">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="b947a-192">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="b947a-192">Format-Wide</span></span>](Format-Wide.md)
