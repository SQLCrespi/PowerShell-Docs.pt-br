---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: a45e7919b5a24189ca7f50661795ff035c38a037
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596982"
---
# Format-Hex

## SINOPSE

Exibe um arquivo ou outra entrada como hexadecimal.

## SYNTAX

### Caminho

```
Format-Hex [-Path] <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### LiteralPath

```
Format-Hex -LiteralPath <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### ByInputObject

```
Format-Hex -InputObject <PSObject> [-Encoding <Encoding>] [-Count <Int64>] [-Offset <Int64>] [-Raw]
 [<CommonParameters>]
```

## DESCRIPTION

O `Format-Hex` cmdlet exibe um arquivo ou outra entrada como valores hexadecimais. Para determinar o deslocamento de um caractere da saída, adicione o número na extrema esquerda da linha ao número na parte superior da coluna para esse caractere.

O `Format-Hex` cmdlet pode ajudá-lo a determinar o tipo de arquivo de um arquivo corrompido ou um arquivo que pode não ter uma extensão filename. Você pode executar esse cmdlet e, em seguida, ler a saída hexadecimal para obter informações do arquivo.

Ao usar `Format-Hex` em um arquivo, o cmdlet ignora os caracteres de nova linha e retorna todo o conteúdo de um arquivo em uma cadeia de caracteres com a nova linha preservada.

## EXEMPLOS

### Exemplo 1: obter a representação hexadecimal de uma cadeia de caracteres

Esse comando retorna os valores hexadecimais de uma cadeia de caracteres.

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

A cadeia de caracteres **Olá, mundo** é enviada ao pipeline para o `Format-Hex` cmdlet. A saída hexadecimal de `Format-Hex` mostra os valores de cada caractere na cadeia de caracteres.

### Exemplo 2: localizar um tipo de arquivo da saída hexadecimal

Este exemplo usa a saída hexadecimal para determinar o tipo de arquivo. O cmdlet exibe o caminho completo do arquivo e os valores hexadecimais.

Para testar o comando a seguir, faça uma cópia de um arquivo PDF existente no computador local e renomeie o arquivo copiado para `File.t7f` .

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

O `Format-Hex` cmdlet usa o parâmetro **Path** para especificar um nome de arquivo no diretório atual, `File.t7f` . A extensão do arquivo `.t7f` não é comum, mas a saída hexadecimal `%PDF` mostra que se trata de um arquivo PDF. Neste exemplo, o parâmetro **Count** é usado para limitar a saída para os primeiros 48 bytes do arquivo.

### Exemplo 3: Formatar uma matriz de tipos de dados diferentes

Este exemplo usa uma matriz de tipos de dados diferentes para destacar como `Format-Hex` lida com eles no pipeline.

Ele passará cada objeto por meio do pipeline e processará individualmente. No entanto, se forem dados numéricos e o objeto adjacente também for numérico, ele os agrupará em um único bloco de saída.

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
0000000000000000 EF BE AD DE 00 00 00 40 5C 03 00 00             ï¾-Þ   @\�

   Label: Boolean (System.Boolean) <7D8C4C1D>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 00 00 00 00                         �
```

## PARAMETERS

### -Codificação

Especifica a codificação das cadeias de caracteres de entrada. Isso se aplica somente à `[string]` entrada. O parâmetro não tem nenhum efeito sobre tipos numéricos. O valor de saída é sempre `utf8NoBOM` .

Os valores aceitáveis para esse parâmetro são os seguintes:

- `ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).
- `bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.
- `bigendianutf32`: Codifica em formato UTF-32 usando a ordem de byte big-endian.
- `oem`: Usa a codificação padrão para MS-DOS e programas de console.
- `unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.
- `utf7`: Codifica em formato UTF-7.
- `utf8`: Codifica em formato UTF-8.
- `utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)
- `utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)
- `utf32`: Codifica no formato UTF-32.

A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ). Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

> [!NOTE]
> O **UTF-7** _ não é mais recomendado para uso. No PowerShell 7,1, um aviso será gravado se você especificar `utf7` para o parâmetro _ *Encoding**.

```yaml
Type: System.Text.Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Usado para entrada de pipeline. A entrada do pipeline dá suporte a apenas determinados tipos e instâncias escalares `[system.io.fileinfo]` para a tubulação `Get-ChildItem` .

Os tipos escalares com suporte são:

- `[string]`, `[char]`
- `[byte]`, `[sbyte]`
- `[int16]`, `[uint16]`, `[short]`, `[ushort]`
- `[int]`, `[uint]`, `[int32]`, `[uint32]`,
- `[long]`, `[ulong]`, `[int64]`, `[uint64]`
- `[single]`, `[float]`, `[double]`
- `[boolean]`

Antes do PowerShell 6,2, `Format-Hex` trataria uma entrada de pipeline com vários tipos de entrada agrupando todos os objetos como juntos. Agora, ele manipula cada objeto individual à medida que passa pelo pipeline e não agrupa objetos, a menos que como objetos estejam adjacentes.

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

### -LiteralPath

Especifica o caminho completo para um arquivo. O valor de **LiteralPath** é usado exatamente como é digitado.
Esse parâmetro não aceita caracteres curinga. Para especificar vários caminhos para arquivos, separe os caminhos com uma vírgula. Se o parâmetro **LiteralPath** incluir caracteres de escape, coloque o caminho entre aspas simples. O PowerShell não interpreta nenhum caractere em uma única cadeia de caracteres entre aspas como sequências de escape. Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

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

### -Path

Especifica o caminho para os arquivos. Use um ponto ( `.` ) para especificar o local atual. O caractere curinga ( `*` ) é aceito e pode ser usado para especificar todos os itens em um local. Se o parâmetro **path** incluir caracteres de escape, coloque o caminho entre aspas simples. Para especificar vários caminhos para arquivos, separe os caminhos com uma vírgula.

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

### -RAW

Esse parâmetro não faz mais nada. Ele é retido para compatibilidade de script.

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

### -Deslocamento

Isso representa o número de bytes a serem ignorados, sendo parte da saída de hex.

Esse parâmetro foi introduzido no PowerShell 6,2.

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

### -Contagem

Isso representa o número de bytes a serem incluídos na saída hexadecimal.

Esse parâmetro foi introduzido no PowerShell 6,2.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres para este cmdlet.

## SAÍDAS

### Microsoft. PowerShell. Commands. Bytecollection

Esse cmdlet retorna um **bytecollection**. Esse objeto representa uma coleção de bytes. Ele inclui métodos que convertem a coleção de bytes em uma cadeia de caracteres formatada como cada linha de saída retornada por `Format-Hex` . A saída também indica o tipo de bytes que estão sendo processados. Se você especificar o **caminho** ou o parâmetro **LiteralPath** , o objeto conterá o caminho do arquivo que contém cada byte. Se você passar uma cadeia de caracteres, booliano, inteiro etc., ele será rotulado adequadamente.

## OBSERVAÇÕES

A coluna mais à direita da saída tenta renderizar os bytes como caracteres ASCII:

Em geral, cada byte é interpretado como um ponto de código Unicode, o que significa que:

- Caracteres ASCII imprimíveis sempre são renderizados corretamente
- Caracteres UTF-8 de vários bytes nunca são renderizados corretamente
- Os caracteres UTF-16 são renderizados corretamente apenas se o byte de ordem superior acontece `NUL` .

## LINKS RELACIONADOS

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[Format-Custom](Format-Custom.md)

[Format-List](Format-List.md)

[Format-Table](Format-Table.md)

[Format-Wide](Format-Wide.md)

