---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 6cb02f1c6f2583ce4146356fac3553e99a54c7c2
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193074"
---
# <span data-ttu-id="3b4b4-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="3b4b4-103">Format-Hex</span></span>

## <span data-ttu-id="3b4b4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3b4b4-104">SYNOPSIS</span></span>

<span data-ttu-id="3b4b4-105">Exibe um arquivo ou outra entrada como hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="3b4b4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3b4b4-106">SYNTAX</span></span>

### <span data-ttu-id="3b4b4-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="3b4b4-107">Path (Default)</span></span>

```
Format-Hex [-Path] <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="3b4b4-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3b4b4-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="3b4b4-109">ByInputObject</span><span class="sxs-lookup"><span data-stu-id="3b4b4-109">ByInputObject</span></span>
```
Format-Hex -InputObject <PSObject> [-Encoding <Encoding>] [-Count <Int64>] [-Offset <Int64>] [-Raw]
 [<CommonParameters>]
```

## <span data-ttu-id="3b4b4-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3b4b4-110">DESCRIPTION</span></span>

<span data-ttu-id="3b4b4-111">O `Format-Hex` cmdlet exibe um arquivo ou outra entrada como valores hexadecimais.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="3b4b4-112">Para determinar o deslocamento de um caractere da saída, adicione o número na extrema esquerda da linha ao número na parte superior da coluna para esse caractere.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="3b4b4-113">O `Format-Hex` cmdlet pode ajudá-lo a determinar o tipo de arquivo de um arquivo corrompido ou um arquivo que pode não ter uma extensão filename.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="3b4b4-114">Você pode executar esse cmdlet e, em seguida, ler a saída hexadecimal para obter informações do arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="3b4b4-115">Ao usar `Format-Hex` em um arquivo, o cmdlet ignora os caracteres de nova linha e retorna todo o conteúdo de um arquivo em uma cadeia de caracteres com a nova linha preservada.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="3b4b4-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3b4b4-116">EXAMPLES</span></span>

### <span data-ttu-id="3b4b4-117">Exemplo 1: obter a representação hexadecimal de uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3b4b4-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="3b4b4-118">Esse comando retorna os valores hexadecimais de uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
   Label: String (System.String) <2944BEC3>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 48 65 6C 6C 6F 20 57 6F 72 6C 64                Hello World
```

<span data-ttu-id="3b4b4-119">A cadeia de caracteres **Olá, mundo** é enviada ao pipeline para o `Format-Hex` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="3b4b4-120">A saída hexadecimal de `Format-Hex` mostra os valores de cada caractere na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="3b4b4-121">Exemplo 2: localizar um tipo de arquivo da saída hexadecimal</span><span class="sxs-lookup"><span data-stu-id="3b4b4-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="3b4b4-122">Este exemplo usa a saída hexadecimal para determinar o tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="3b4b4-123">O cmdlet exibe o caminho completo do arquivo e os valores hexadecimais.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="3b4b4-124">Para testar o comando a seguir, faça uma cópia de um arquivo PDF existente no computador local e renomeie o arquivo copiado para `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="3b4b4-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to `File.t7f`.</span></span>

```powershell
Format-Hex -Path .\File.t7f -Count 48
```

```Output
   Label: C:\Test\File.t7f

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D %PDF-1.5..%????.
0000000000000010 0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70 .1 0 obj..<</Typ
0000000000000020 65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20 e/Catalog/Pages
```

<span data-ttu-id="3b4b4-125">O `Format-Hex` cmdlet usa o parâmetro **Path** para especificar um nome de arquivo no diretório atual, `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="3b4b4-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, `File.t7f`.</span></span> <span data-ttu-id="3b4b4-126">A extensão do arquivo `.t7f` não é comum, mas a saída hexadecimal `%PDF` mostra que se trata de um arquivo PDF.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-126">The file extension `.t7f` is uncommon, but the hexadecimal output `%PDF` shows that it is a PDF file.</span></span> <span data-ttu-id="3b4b4-127">Neste exemplo, o parâmetro **Count** é usado para limitar a saída para os primeiros 48 bytes do arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-127">In this example, the **Count** parameter is used to limit the output to the first 48 bytes of the file.</span></span>

### <span data-ttu-id="3b4b4-128">Exemplo 3: Formatar uma matriz de tipos de dados diferentes</span><span class="sxs-lookup"><span data-stu-id="3b4b4-128">Example 3: Format an array of different data types</span></span>

<span data-ttu-id="3b4b4-129">Este exemplo usa uma matriz de tipos de dados diferentes para destacar como `Format-Hex` lida com eles no pipeline.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-129">This example uses an array of different data types to highlight how `Format-Hex` handles them in the Pipeline.</span></span>

<span data-ttu-id="3b4b4-130">Ele passará cada objeto por meio do pipeline e processará individualmente.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-130">It will pass each object through the Pipeline and process individually.</span></span> <span data-ttu-id="3b4b4-131">No entanto, se forem dados numéricos e o objeto adjacente também for numérico, ele os agrupará em um único bloco de saída.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-131">However, if it's numeric data, and the adjacent object is also numeric, it will group them into a single output block.</span></span>

```powershell
'Hello world!', 1, 1138, 'foo', 'bar', 0xdeadbeef, 1gb, 0b1101011100 , $true, $false | Format-Hex
```

```Output
   Label: String (System.String) <24F1F0A3>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 48 65 6C 6C 6F 20 77 6F 72 6C 64 21             Hello world!

   Label: Int32 (System.Int32) <2EB933C5>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 72 04 00 00                         �   r�

   Label: String (System.String) <4078B66C>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 66 6F 6F                                        foo

   Label: String (System.String) <51E4A317>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 62 61 72                                        bar

   Label: Int32 (System.Int32) <5ADF167B>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 EF BE AD DE 00 00 00 40 5C 03 00 00             ï¾­Þ   @\�

   Label: Boolean (System.Boolean) <7D8C4C1D>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 00 00 00 00                         �
```

## <span data-ttu-id="3b4b4-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3b4b4-132">PARAMETERS</span></span>

### <span data-ttu-id="3b4b4-133">-Codificação</span><span class="sxs-lookup"><span data-stu-id="3b4b4-133">-Encoding</span></span>

<span data-ttu-id="3b4b4-134">Especifica a codificação das cadeias de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-134">Specifies the encoding of the input strings.</span></span> <span data-ttu-id="3b4b4-135">Isso se aplica somente à `[string]` entrada.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-135">This only applies to `[string]` input.</span></span> <span data-ttu-id="3b4b4-136">O parâmetro não tem nenhum efeito sobre tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-136">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="3b4b4-137">O valor de saída é sempre `utf8NoBOM` .</span><span class="sxs-lookup"><span data-stu-id="3b4b4-137">The output value is always `utf8NoBOM`.</span></span>

<span data-ttu-id="3b4b4-138">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="3b4b4-138">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="3b4b4-139">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="3b4b4-139">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="3b4b4-140">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-140">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="3b4b4-141">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-141">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="3b4b4-142">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-142">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="3b4b4-143">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-143">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="3b4b4-144">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-144">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="3b4b4-145">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="3b4b4-145">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="3b4b4-146">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="3b4b4-146">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="3b4b4-147">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-147">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="3b4b4-148">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="3b4b4-148">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="3b4b4-149">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="3b4b4-149">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3b4b4-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3b4b4-150">-InputObject</span></span>

<span data-ttu-id="3b4b4-151">Usado para entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-151">Used for pipeline input.</span></span> <span data-ttu-id="3b4b4-152">A entrada do pipeline dá suporte a apenas determinados tipos e instâncias escalares `[system.io.fileinfo]` para a tubulação `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="3b4b4-152">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="3b4b4-153">Os tipos escalares com suporte são:</span><span class="sxs-lookup"><span data-stu-id="3b4b4-153">The supported scalar types are:</span></span>

- <span data-ttu-id="3b4b4-154">`[string]`, `[char]`</span><span class="sxs-lookup"><span data-stu-id="3b4b4-154">`[string]`, `[char]`</span></span>
- <span data-ttu-id="3b4b4-155">`[byte]`, `[sbyte]`</span><span class="sxs-lookup"><span data-stu-id="3b4b4-155">`[byte]`, `[sbyte]`</span></span>
- <span data-ttu-id="3b4b4-156">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span><span class="sxs-lookup"><span data-stu-id="3b4b4-156">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span></span>
- <span data-ttu-id="3b4b4-157">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span><span class="sxs-lookup"><span data-stu-id="3b4b4-157">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span></span>
- <span data-ttu-id="3b4b4-158">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="3b4b4-158">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span></span>
- <span data-ttu-id="3b4b4-159">`[single]`, `[float]`, `[double]`</span><span class="sxs-lookup"><span data-stu-id="3b4b4-159">`[single]`, `[float]`, `[double]`</span></span>
- `[boolean]`

<span data-ttu-id="3b4b4-160">Antes do PowerShell 6,2, `Format-Hex` trataria uma entrada de pipeline com vários tipos de entrada agrupando todos os objetos como juntos.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-160">Prior to PowerShell 6.2, `Format-Hex` would handle a Pipeline input with multiple input types by grouping all like objects together.</span></span> <span data-ttu-id="3b4b4-161">Agora, ele manipula cada objeto individual à medida que passa pelo pipeline e não agrupa objetos, a menos que como objetos estejam adjacentes.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-161">Now, it handles each individual object as it passes through the Pipeline and won't group objects together unless like objects are adjacent.</span></span>

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

### <span data-ttu-id="3b4b4-162">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3b4b4-162">-LiteralPath</span></span>

<span data-ttu-id="3b4b4-163">Especifica o caminho completo para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-163">Specifies the complete path to a file.</span></span> <span data-ttu-id="3b4b4-164">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-164">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="3b4b4-165">Esse parâmetro não aceita caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-165">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="3b4b4-166">Para especificar vários caminhos para arquivos, separe os caminhos com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-166">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="3b4b4-167">Se o parâmetro **LiteralPath** incluir caracteres de escape, coloque o caminho entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-167">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="3b4b4-168">O PowerShell não interpreta nenhum caractere em uma única cadeia de caracteres entre aspas como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-168">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="3b4b4-169">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="3b4b4-169">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="3b4b4-170">-Path</span><span class="sxs-lookup"><span data-stu-id="3b4b4-170">-Path</span></span>

<span data-ttu-id="3b4b4-171">Especifica o caminho para os arquivos.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-171">Specifies the path to files.</span></span> <span data-ttu-id="3b4b4-172">Use um ponto ( `.` ) para especificar o local atual.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-172">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="3b4b4-173">O caractere curinga ( `*` ) é aceito e pode ser usado para especificar todos os itens em um local.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-173">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="3b4b4-174">Se o parâmetro **path** incluir caracteres de escape, coloque o caminho entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-174">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="3b4b4-175">Para especificar vários caminhos para arquivos, separe os caminhos com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-175">To specify multiple paths to files, separate the paths with a comma.</span></span>

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

### <span data-ttu-id="3b4b4-176">-RAW</span><span class="sxs-lookup"><span data-stu-id="3b4b4-176">-Raw</span></span>

<span data-ttu-id="3b4b4-177">Esse parâmetro não faz mais nada.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-177">This parameter no longer does anything.</span></span> <span data-ttu-id="3b4b4-178">Ele é retido para compatibilidade de script.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-178">It is retained for script compatibility.</span></span>

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

### <span data-ttu-id="3b4b4-179">-Deslocamento</span><span class="sxs-lookup"><span data-stu-id="3b4b4-179">-Offset</span></span>

<span data-ttu-id="3b4b4-180">Isso representa o número de bytes a serem ignorados, sendo parte da saída de hex.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-180">This represents the number of bytes to skip from being part of the hex output.</span></span>

<span data-ttu-id="3b4b4-181">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-181">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="3b4b4-182">-Contagem</span><span class="sxs-lookup"><span data-stu-id="3b4b4-182">-Count</span></span>

<span data-ttu-id="3b4b4-183">Isso representa o número de bytes a serem incluídos na saída hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-183">This represents the number of bytes to include in the hex output.</span></span>

<span data-ttu-id="3b4b4-184">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-184">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="3b4b4-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3b4b4-185">CommonParameters</span></span>

<span data-ttu-id="3b4b4-186">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3b4b4-187">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3b4b4-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3b4b4-188">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3b4b4-188">INPUTS</span></span>

### <span data-ttu-id="3b4b4-189">System.String</span><span class="sxs-lookup"><span data-stu-id="3b4b4-189">System.String</span></span>

<span data-ttu-id="3b4b4-190">É possível canalizar uma cadeia de caracteres para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-190">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="3b4b4-191">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3b4b4-191">OUTPUTS</span></span>

### <span data-ttu-id="3b4b4-192">Microsoft. PowerShell. Commands. Bytecollection</span><span class="sxs-lookup"><span data-stu-id="3b4b4-192">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="3b4b4-193">Esse cmdlet retorna um **bytecollection** .</span><span class="sxs-lookup"><span data-stu-id="3b4b4-193">This cmdlet returns a **ByteCollection** .</span></span> <span data-ttu-id="3b4b4-194">Esse objeto representa uma coleção de bytes.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-194">This object represents a collection of bytes.</span></span> <span data-ttu-id="3b4b4-195">Ele inclui métodos que convertem a coleção de bytes em uma cadeia de caracteres formatada como cada linha de saída retornada por `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="3b4b4-195">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="3b4b4-196">A saída também indica o tipo de bytes que estão sendo processados.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-196">The output also states they type of bytes being processed.</span></span> <span data-ttu-id="3b4b4-197">Se você especificar o **caminho** ou o parâmetro **LiteralPath** , o objeto conterá o caminho do arquivo que contém cada byte.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-197">If you specify the **Path** or **LiteralPath** parameter, the object contains the path of the file that contains each byte.</span></span> <span data-ttu-id="3b4b4-198">Se você passar uma cadeia de caracteres, booliano, inteiro etc., ele será rotulado adequadamente.</span><span class="sxs-lookup"><span data-stu-id="3b4b4-198">If you pass a string, boolean, integer, etc, it will be labeled appropriately.</span></span>

## <span data-ttu-id="3b4b4-199">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3b4b4-199">NOTES</span></span>

<span data-ttu-id="3b4b4-200">A coluna mais à direita da saída tenta renderizar os bytes como caracteres ASCII:</span><span class="sxs-lookup"><span data-stu-id="3b4b4-200">The right-most column of output tries to render the bytes as ASCII characters:</span></span>

<span data-ttu-id="3b4b4-201">Em geral, cada byte é interpretado como um ponto de código Unicode, o que significa que:</span><span class="sxs-lookup"><span data-stu-id="3b4b4-201">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="3b4b4-202">Caracteres ASCII imprimíveis sempre são renderizados corretamente</span><span class="sxs-lookup"><span data-stu-id="3b4b4-202">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="3b4b4-203">Caracteres UTF-8 de vários bytes nunca são renderizados corretamente</span><span class="sxs-lookup"><span data-stu-id="3b4b4-203">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="3b4b4-204">Os caracteres UTF-16 são renderizados corretamente apenas se o byte de ordem superior acontece `NUL` .</span><span class="sxs-lookup"><span data-stu-id="3b4b4-204">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="3b4b4-205">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3b4b4-205">RELATED LINKS</span></span>

[<span data-ttu-id="3b4b4-206">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="3b4b4-206">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="3b4b4-207">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="3b4b4-207">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="3b4b4-208">Format-List</span><span class="sxs-lookup"><span data-stu-id="3b4b4-208">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="3b4b4-209">Format-Table</span><span class="sxs-lookup"><span data-stu-id="3b4b4-209">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="3b4b4-210">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="3b4b4-210">Format-Wide</span></span>](Format-Wide.md)
