---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-string?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-String
ms.openlocfilehash: 339afab9c817b54a79e2f1b33b7021ecb4fe6a6e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597793"
---
# Select-String

## SINOPSE
Localiza texto em arquivos e cadeias de caracteres.

## SYNTAX

### Arquivo (padrão)

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### ObjectRaw

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### Objeto

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### FileRaw

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### LiteralFileRaw

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### Valor literal

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Select-String` cmdlet procura padrões de texto e texto em cadeias de caracteres de entrada e arquivos. Você pode usar `Select-String` semelhante ao **grep** no UNIX ou **findstr.exe** no Windows.

`Select-String` baseia-se em linhas de texto. Por padrão, `Select-String` o localiza a primeira correspondência em cada linha e, para cada correspondência, exibe o nome do arquivo, o número da linha e todo o texto na linha que contém a correspondência. Você pode direcionar `Select-String` para localizar várias correspondências por linha, exibir texto antes e depois da correspondência, ou exibir um valor booliano (true ou false) que indica se uma correspondência é encontrada.

`Select-String` usa correspondência de expressão regular, mas também pode executar uma correspondência que pesquisa a entrada para o texto que você especificar.

`Select-String` pode exibir todas as correspondências de texto ou parar após a primeira correspondência em cada arquivo de entrada.
`Select-String` pode ser usado para exibir todo o texto que não corresponde ao padrão especificado.

Você também pode especificar que `Select-String` deve esperar uma codificação de caractere específica, como quando você está pesquisando arquivos de texto Unicode. `Select-String` usa a BOM (marca de ordem de byte) para detectar o formato de codificação do arquivo. Se o arquivo não tiver uma BOM, ele assumirá que a codificação é UTF8.

## EXEMPLOS

### Exemplo 1: Localizar uma correspondência que diferencia maiúsculas de minúsculas

Este exemplo faz uma correspondência que diferencia maiúsculas de minúsculas do texto que foi enviado pelo pipeline para o `Select-String` cmdlet.

```powershell
'Hello', 'HELLO' | Select-String -Pattern 'HELLO' -CaseSensitive -SimpleMatch
```

As cadeias de texto **Olá** e **Olá** são enviadas ao pipeline para o `Select-String` cmdlet.
`Select-String` usa o parâmetro **Pattern** para especificar **Hello**. O parâmetro **CaseSensitive** especifica que o caso deve corresponder apenas ao padrão em maiúsculas. **SimpleMatch** é um parâmetro opcional e especifica que a cadeia de caracteres no padrão não é interpretada como uma expressão regular.
`Select-String` exibe **Olá** no console do PowerShell.

### Exemplo 2: localizar correspondências em arquivos de texto

Esse comando pesquisa todos os arquivos com a `.txt` extensão de nome de arquivo no diretório atual. A saída exibe as linhas nesses arquivos que incluem a cadeia de caracteres especificada.

```powershell
Get-Alias | Out-File -FilePath .\Alias.txt
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\*.txt -Pattern 'Get-'
```

```Output
Alias.txt:8:Alias            cat -> Get-Content
Alias.txt:28:Alias           dir -> Get-ChildItem
Alias.txt:43:Alias           gal -> Get-Alias
Command.txt:966:Cmdlet       Get-Acl
Command.txt:967:Cmdlet       Get-Alias
```

Neste exemplo, `Get-Alias` e `Get-Command` são usados com o `Out-File` cmdlet para criar dois arquivos de texto no diretório atual, **Alias.txt** e **Command.txt**.

`Select-String` usa o parâmetro **path** com o curinga asterisco ( `*` ) para pesquisar todos os arquivos no diretório atual com a extensão de nome de arquivo `.txt` . O parâmetro **Pattern** especifica o texto para corresponder a **Get-**. `Select-String` exibe a saída no console do PowerShell. O nome do arquivo e o número da linha precedem cada linha de conteúdo que contém uma correspondência para o parâmetro **Pattern** .

### Exemplo 3: Localizar uma correspondência de padrão

Neste exemplo, vários arquivos são pesquisados para localizar correspondências para o padrão especificado. O padrão usa um quantificador de expressão regular. Para obter mais informações, consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).

```powershell
Select-String -Path "$PSHOME\en-US\*.txt" -Pattern '\?'
```

```Output
C:\Program Files\PowerShell\6\en-US\default.help.txt:27:    beginning at https://go.microsoft.com/fwlink/?LinkID=108518.
C:\Program Files\PowerShell\6\en-US\default.help.txt:50:    or go to: https://go.microsoft.com/fwlink/?LinkID=210614
```

O `Select-String` cmdlet usa dois parâmetros, **Path** e **Pattern**. O parâmetro **path** usa a variável `$PSHOME` que especifica o diretório do PowerShell. O restante do caminho inclui o subdiretório **en-US** e especifica cada `*.txt` arquivo no diretório. O parâmetro **Pattern** especifica a correspondência de um ponto de interrogação ( `?` ) em cada arquivo. Uma barra invertida ( `\` ) é usada como um caractere de escape e é necessária porque o ponto de interrogação ( `?` ) é um quantificador de expressão regular. `Select-String` exibe a saída no console do PowerShell. O nome do arquivo e o número da linha precedem cada linha de conteúdo que contém uma correspondência para o parâmetro **Pattern** .

### Exemplo 4: usar Select-String em uma função

Este exemplo cria uma função para procurar por um padrão nos arquivos de ajuda do PowerShell. Para este exemplo, a função existe somente na sessão do PowerShell. Quando a sessão do PowerShell é fechada, a função é excluída. Para obter mais informações, consulte [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).

```
PS> Function Search-Help
>> {
>> $PSHelp = "$PSHOME\en-US\*.txt"
>> Select-String -Path $PSHelp -Pattern 'About_'
>> }
PS>

PS> Search-Help

C:\Program Files\PowerShell\6\en-US\default.help.txt:67:    The titles of conceptual topics begin with "About_".
C:\Program Files\PowerShell\6\en-US\default.help.txt:70:    Get-Help About_<topic-name>
C:\Program Files\PowerShell\6\en-US\default.help.txt:93:    Get-Help About_Modules : Displays help about PowerShell modules.
C:\Program Files\PowerShell\6\en-US\default.help.txt:97:    about_Updatable_Help
```

A função é criada na linha de comando do PowerShell. O `Function` comando usa o nome **Search-Help**. Pressione **Enter** para começar a adicionar instruções à função. No `>>` prompt, adicione cada instrução e pressione **Enter** , conforme mostrado no exemplo. Depois que o colchete de fechamento for adicionado, você será retornado para um prompt do PowerShell.

A função contém dois comandos. A `$PSHelp` variável armazena o caminho para os arquivos de ajuda do PowerShell. `$PSHOME` é o diretório de instalação do PowerShell com o subdiretório **en-US** que especifica cada `*.txt` arquivo no diretório.

O `Select-String` comando na função usa os parâmetros **Path** e **Pattern** . O parâmetro **path** usa a `$PSHelp` variável para obter o caminho. O parâmetro **Pattern** usa a cadeia de caracteres **About_** como os critérios de pesquisa.

Para executar a função, digite `Search-Help` . O comando da função `Select-String` exibe a saída no console do PowerShell.

### Exemplo 5: Pesquisar uma cadeia de caracteres em um log de eventos do Windows

Este exemplo pesquisa uma cadeia de caracteres em um log de eventos do Windows. A variável `$_` representa o objeto atual no pipeline. Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

```powershell
$Events = Get-WinEvent -LogName Application -MaxEvents 50
$Events | Select-String -InputObject {$_.message} -Pattern 'Failed'
```

O `Get-WinEvent` cmdlet usa o parâmetro **LogName** para especificar o log do aplicativo. O parâmetro **MaxEvents** obtém os 50 eventos mais recentes do log. O conteúdo do log é armazenado na variável chamada `$Events` .

A `$Events` variável é enviada ao pipeline para o `Select-String` cmdlet. `Select-String` usa o parâmetro **InputObject** . A `$_` variável representa o objeto atual e `message` é uma propriedade do evento. O parâmetro **Pattern** especifica a cadeia de caracteres que **falhou** e procura por correspondências `$_.message` . `Select-String` exibe a saída no console do PowerShell.

### Exemplo 6: Localizar uma cadeia de caracteres em subdiretórios

Este exemplo pesquisa um diretório e todos os seus subdiretórios para uma cadeia de texto específica.

```powershell
Get-ChildItem -Path C:\Windows\System32\*.txt -Recurse | Select-String -Pattern 'Microsoft' -CaseSensitive
```

`Get-ChildItem` usa o parâmetro **path** para especificar **C:\Windows\System32 \* . txt**. O parâmetro **recurse** inclui os subdiretórios. Os objetos são enviados ao pipeline para `Select-String` .

`Select-String` usa o parâmetro **Pattern** e especifica a cadeia de caracteres **Microsoft**. O parâmetro **CaseSensitive** é usado para corresponder ao caso exato da cadeia de caracteres. `Select-String` exibe a saída no console do PowerShell.

> [!NOTE]
> Dependendo de suas permissões, você poderá ver as mensagens de **acesso negado** na saída.

### Exemplo 7: localizar cadeias de caracteres que não correspondem a um padrão

Este exemplo mostra como excluir linhas de dados que não correspondem a um padrão.

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get', 'Set'  -NotMatch
```

O `Get-Command` cmdlet envia objetos por meio do pipeline para o `Out-File` para criar o arquivo de **Command.txt** no diretório atual. `Select-String` usa o parâmetro **path** para especificar o arquivo de **Command.txt** . O parâmetro **Pattern** especifica **Get** e **set** como o padrão de pesquisa. O parâmetro não **Match** exclui **Get** e **set** dos resultados.
`Select-String` exibe a saída no console do PowerShell que não inclui **Get** ou **set**.

### Exemplo 8: localizar linhas antes e depois de uma correspondência

Este exemplo mostra como obter as linhas antes e depois do padrão correspondente.

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get-Computer' -Context 2, 3
```

```Output
  Command.txt:986:Cmdlet          Get-CmsMessage           6.1.0.0    Microsoft.PowerShell.Security
  Command.txt:987:Cmdlet          Get-Command              6.1.2.0    Microsoft.PowerShell.Core
> Command.txt:988:Cmdlet          Get-ComputerInfo         6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:990:Cmdlet          Get-Content              6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:991:Cmdlet          Get-ControlPanelItem     3.1.0.0    Microsoft.PowerShell.Management
  Command.txt:992:Cmdlet          Get-Credential           6.1.0.0    Microsoft.PowerShell.Security
```

O `Get-Command` cmdlet envia objetos por meio do pipeline para o `Out-File` para criar o arquivo de **Command.txt** no diretório atual. `Select-String` usa o parâmetro **path** para especificar o arquivo de **Command.txt** . O parâmetro **Pattern** especifica **Get-Computer** como o padrão de pesquisa. O parâmetro de **contexto** usa dois valores, antes e depois, e marca as correspondências de padrão na saída com um colchete angular ( `>` ). O parâmetro **Context** gera as duas linhas antes do primeiro padrão corresponder e três linhas após a última correspondência de padrão.

### Exemplo 9: localizar todas as correspondências de padrão

Este exemplo mostra como o parâmetro **Mymatchs** encontra cada correspondência de padrão em uma linha de texto. Por padrão, `Select-String` o localiza apenas a primeira ocorrência de um padrão em uma linha de texto. Este exemplo usa propriedades de objeto que são encontradas com o `Get-Member` cmdlet.

```
PS> $A = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell'

PS> $A

C:\Program Files\PowerShell\6\en-US\default.help.txt:3:    PowerShell Help System
C:\Program Files\PowerShell\6\en-US\default.help.txt:6:    Displays help about PowerShell cmdlets and concepts.
C:\Program Files\PowerShell\6\en-US\default.help.txt:9:    PowerShell Help describes PowerShell cmdlets

PS> $A.Matches

Groups   : {0}
Success  : True
Name     : 0
Captures : {0}
Index    : 4
Length   : 10
Value    : PowerShell

PS> $A.Matches.Length

8

PS> $B = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell' -AllMatches

PS> $B.Matches.Length

9
```

O `Get-ChildItem` cmdlet usa o parâmetro **Path** . O parâmetro **path** usa a variável `$PSHOME` que especifica o diretório do PowerShell. O restante do caminho inclui o subdiretório **en-US** e especifica cada `*.txt` arquivo no diretório. Os `Get-ChildItem` objetos são armazenados na `$A` variável. A `$A` variável é enviada ao pipeline para o `Select-String` cmdlet. `Select-String` usa o parâmetro **Pattern** para pesquisar cada arquivo para a cadeia de caracteres **PowerShell**.

Na linha de comando do PowerShell, o `$A` conteúdo da variável é exibido. Há uma linha que contém duas ocorrências da cadeia de caracteres do **PowerShell**.

A `$A.Matches` propriedade lista a primeira ocorrência do **PowerShell** padrão em cada linha.

A `$A.Matches.Length` Propriedade conta a primeira ocorrência do **PowerShell** padrão em cada linha.

A `$B` variável usa os mesmos `Get-ChildItem` `Select-String` cmdlets e, mas adiciona o parâmetro de todas as **correspondências** . Os **Permatchs** localiza cada ocorrência do **PowerShell** padrão em cada linha. Os objetos armazenados nas `$A` variáveis e `$B` são idênticos.

A `$B.Matches.Length` Propriedade aumenta porque, para cada linha, todas as ocorrências do padrão do **PowerShell** são contadas.

## PARAMETERS

### -Todas as correspondências

Indica que o cmdlet pesquisa mais de uma correspondência em cada linha de texto. Sem esse parâmetro, `Select-String` o localiza apenas a primeira correspondência em cada linha de texto.

Quando `Select-String` o encontra mais de uma correspondência em uma linha de texto, ele ainda emite apenas um objeto **MatchInfo** para a linha, mas a propriedade **corresponde** do objeto contém todas as correspondências.

> [!NOTE]
> Esse parâmetro é ignorado quando usado em combinação com o parâmetro **SimpleMatch** . Se você deseja retornar todas as correspondências e o padrão que você está procurando contém caracteres de expressão regular, você deve escapar esses caracteres em vez de usar **SimpleMatch**. Consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) para obter mais informações sobre a saída de expressões regulares.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CaseSensitive

Indica que as correspondências de cmdlet diferenciam maiúsculas de minúsculas. Por padrão, as correspondências não diferenciam maiúsculas de minúsculas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Context

Captura o número especificado de linhas antes e depois da linha que corresponde ao padrão.

Se você inserir um número como o valor desse parâmetro, esse número determina o número de linhas capturadas antes e após a correspondência. Se você inserir dois números como valor, o primeiro número determina o número de linhas antes da correspondência e o segundo determina o número de linhas após a correspondência. Por exemplo, `-Context 2,3`.

Na exibição padrão, as linhas com uma correspondência são indicadas por um colchete angular direito ( `>` ) (ASCII 62) na primeira coluna da exibição. Linhas desmarcadas são o contexto.

O parâmetro de **contexto** não altera o número de objetos gerados pelo `Select-String` .
`Select-String` gera um objeto [MatchInfo](/dotnet/api/microsoft.powershell.commands.matchinfo) para cada correspondência. O contexto é armazenado como uma matriz de cadeias de caracteres na propriedade **Context** do objeto.

Quando a saída de um `Select-String` comando é enviada para o pipeline para outro `Select-String` comando, o comando de recebimento pesquisa apenas o texto na linha correspondente. A linha correspondente é o valor da propriedade **line** do objeto **MatchInfo** , não o texto nas linhas de contexto. Como resultado, o parâmetro de **contexto** não é válido no comando de recebimento `Select-String` .

Quando o contexto inclui uma correspondência, o objeto **MatchInfo** de cada correspondência inclui todas as linhas de contexto, mas as linhas sobrepostas aparecem apenas uma vez na exibição.

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Culture

Especifica um nome de cultura para corresponder ao padrão especificado. O parâmetro **Culture** deve ser usado com o parâmetro **SimpleMatch** . O comportamento padrão usa a cultura do runspace do PowerShell atual (sessão).

Para obter uma lista de todas as culturas com suporte, use o `Get-Culture -ListAvailable` comando.

Além disso, esse parâmetro aceita os seguintes argumentos:

- CurrentCulture, que é padrão;
- Ordinal, que é uma comparação binária não lingüística;
- Invariável, que é a comparação independente de cultura.

Com o `Select-String -Culture Ordinal -CaseSensitive -SimpleMatch` comando, você obtém uma comparação binária mais rápida.

O parâmetro **Culture** usa a conclusão de Tab para percorrer a lista de argumentos que especificam as culturas disponíveis. Para listar todos os argumentos disponíveis, use o seguinte comando:

`(Get-Command Select-String).Parameters.Culture.Attributes.ValidValues`

Para obter mais informações sobre a propriedade CultureInfo.Name do .NET, consulte [CultureInfo.Name](/dotnet/api//system.globalization.cultureinfo.name).

O parâmetro **Culture** foi introduzido no PowerShell 7.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Culture of the current PowerShell session
Accept pipeline input: False
Accept wildcard characters: False
```

### -Codificação

Especifica o tipo de codificação para o arquivo de destino. O valor padrão é `utf8NoBOM`.

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
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -Excluir

Exclui os itens especificados. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um elemento ou padrão de caminho, como `*.txt` . Caracteres curinga são permitidos.

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

### -Incluir

Inclui os itens especificados. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um elemento ou padrão de caminho, como `*.txt` . Caracteres curinga são permitidos.

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

### -InputObject

Especifica o texto a ser pesquisada. Insira uma variável que contém o texto ou digite um comando ou uma expressão que obtenha o texto.

Usar o parâmetro **InputObject** não é o mesmo que enviar cadeias de caracteres para baixo do pipeline para `Select-String` .

Quando você canaliza mais de uma cadeia de caracteres para o `Select-String` cmdlet, ele pesquisa o texto especificado em cada cadeia de caracteres e retorna cada cadeia de caracteres que contém o texto de pesquisa.

Quando você usa o parâmetro **InputObject** para enviar uma coleção de cadeias de caracteres, `Select-String` o trata a coleção como uma única cadeia de caracteres combinada. `Select-String` Retorna as cadeias de caracteres como uma unidade se encontrar o texto de pesquisa em qualquer cadeia de caracteres.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Object, ObjectRaw
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lista

Somente a primeira instância de texto correspondente é retornada de cada arquivo de entrada. Essa é a maneira mais eficiente de recuperar uma lista de arquivos que têm conteúdo correspondente à expressão regular.

Por padrão, `Select-String` retorna um objeto **MatchInfo** para cada correspondência que ele encontra.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Especifica o caminho para os arquivos a serem pesquisados. O valor do parâmetro **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape. Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralFileRaw, LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Noênfase

Por padrão, `Select-String` o realça a cadeia de caracteres que corresponde ao padrão que você pesquisou com o parâmetro **Pattern** . O parâmetro **noênfase** desabilita o realce.

A ênfase usa cores negativas com base nas cores de texto e de fundo do PowerShell. Por exemplo, se suas cores do PowerShell forem um plano de fundo preto com texto em branco. A ênfase é um plano de fundo branco com texto em preto.

Esse parâmetro foi introduzido no PowerShell 7.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Não correspondente

O parâmetro não **Match** localiza texto que não corresponde ao padrão especificado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica o caminho para os arquivos a serem pesquisados. Caracteres curinga são permitidos. O local padrão é o diretório local.

Especifique os arquivos no diretório, como `log1.txt` , `*.doc` ou `*.*` . Se você especificar apenas um diretório, o comando falha.

```yaml
Type: System.String[]
Parameter Sets: File, FileRaw
Aliases:

Required: True
Position: 1
Default value: Local directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Padrão

Especifica o texto a ser localizado em cada linha. O valor padrão é tratado como uma expressão regular.

Para saber mais sobre expressões regulares, consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Quiet

Indica que o cmdlet retorna um valor booliano (true ou false), em vez de um objeto **MatchInfo** . O valor será true se o padrão for encontrado; caso contrário, o valor será false.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File, Object, LiteralFile
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RAW

Faz com que o cmdlet gere somente as cadeias de caracteres correspondentes, em vez de objetos **MatchInfo** . Esses são os resultados em comportamento que é o mais semelhante aos comandos UNIX **grep** ou Windows **findstr.exe** .

Esse parâmetro foi introduzido no PowerShell 7.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ObjectRaw, FileRaw, LiteralFileRaw
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SimpleMatch

Indica que o cmdlet usa uma correspondência simples em vez de uma correspondência de expressão regular. Em uma correspondência simples, `Select-String` o pesquisa a entrada para o texto no parâmetro **Pattern** . Ele não interpreta o valor do parâmetro **Pattern** como uma instrução de expressão regular.

Além disso, quando **SimpleMatch** é usado, a propriedade **corresponde** do objeto **MatchInfo** retornado está vazia.

> [!NOTE]
> Quando esse parâmetro é usado com o parâmetro **Mymatchs** , os **correspondentes** são ignorados.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

É possível canalizar qualquer objeto que tenha um método **ToString** para `Select-String` .

## SAÍDAS

### Microsoft. PowerShell. Commands. MatchInfo, System. booliano, System. String

Por padrão, a saída é um conjunto de objetos **MatchInfo** com um para cada correspondência encontrada. Se você usar o parâmetro **Quiet** , a saída será um valor **booliano** indicando se o padrão foi encontrado.
Se você usar o parâmetro **RAW** , a saída será um conjunto de objetos **String** que correspondem ao padrão.

## OBSERVAÇÕES

`Select-String` é semelhante ao **grep** no UNIX ou **findstr.exe** no Windows.

O alias de **SLS** para o `Select-String` cmdlet foi introduzido no PowerShell 3,0.

> [!NOTE]
> De acordo com [verbos aprovados para comandos do PowerShell](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands), o prefixo de alias oficial para `Select-*` cmdlets é `sc` , não `sl` . Portanto, o alias apropriado para `Select-String` deveria ser `scs` , não `sls` . Esta é uma exceção a essa regra.

Para usar `Select-String` , digite o texto que você deseja localizar como o valor do parâmetro **Pattern** . Para especificar o texto a ser pesquisado, use os seguintes critérios:

- Digite o texto em uma cadeia de caracteres entre aspas e, em seguida, redirecione-o para `Select-String` .
- Armazene uma cadeia de texto em uma variável e, em seguida, especifique a variável como o valor do parâmetro **InputObject** .
- Se o texto estiver armazenado em arquivos, use o parâmetro **path** para especificar o caminho para os arquivos.

Por padrão, `Select-String` o interpreta o valor do parâmetro **Pattern** como uma expressão regular. Para obter mais informações, consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md). Você pode usar o parâmetro **SimpleMatch** para substituir a correspondência de expressão regular. O parâmetro **SimpleMatch** localiza instâncias do valor do parâmetro **Pattern** na entrada.

A saída padrão de `Select-String` é um objeto **MatchInfo** , que inclui informações detalhadas sobre as correspondências. As informações no objeto são úteis quando você está pesquisando texto em arquivos, porque os objetos **MatchInfo** têm propriedades como **filename** e **line**. Quando a entrada não estiver no arquivo, o valor desses parâmetros será **InputStream**.

Se você não precisar das informações no objeto **MatchInfo** , use o parâmetro **Quiet** . O parâmetro **Quiet** retorna um valor booliano (true ou false) para indicar se ele encontrou uma correspondência, em vez de um objeto **MatchInfo** .

Quando as frases correspondentes, `Select-String` o usa a cultura atual definida para o sistema. Para localizar a cultura atual, use o `Get-Culture` cmdlet.

Para localizar as propriedades de um objeto **MatchInfo** , digite o seguinte comando:

`Select-String -Path test.txt -Pattern 'test' | Get-Member | Format-List -Property *`

## LINKS RELACIONADOS

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md)

[about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md)

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)

[Get-Alias](Get-Alias.md)

[Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[Get-Command](../Microsoft.PowerShell.Core/Get-Command.md)

[Get-Member](Get-Member.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Out-File](Out-File.md)

