---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-csv?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Csv
ms.openlocfilehash: e33da9b461086e85e1fa074b0bed60ac275894b4
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "93195242"
---
# Import-Csv

## SINOPSE
Cria objetos personalizados do tipo tabela a partir dos itens em um arquivo CSV (valores separados por vírgula).

## SYNTAX

### DelimiterPath (padrão)

```
Import-Csv [[-Delimiter] <Char>] [-Path] <String[]> [-Header <String[]>] [-Encoding <Encoding>]
 [<CommonParameters>]
```

### DelimiterLiteralPath

```
Import-Csv [[-Delimiter] <Char>] -LiteralPath <String[]> [-Header <String[]>] [-Encoding <Encoding>]
 [<CommonParameters>]
```

### CulturePath

```
Import-Csv [-Path] <String[]> -UseCulture [-Header <String[]>] [-Encoding <Encoding>]
 [<CommonParameters>]
```

### CultureLiteralPath

```
Import-Csv -LiteralPath <String[]> -UseCulture [-Header <String[]>] [-Encoding <Encoding>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Import-Csv` cmdlet cria objetos personalizados do tipo tabela a partir dos itens em arquivos CSV. Cada coluna no arquivo CSV torna-se uma propriedade do objeto personalizado e os itens nas linhas tornam-se os valores de propriedade. `Import-Csv` funciona em qualquer arquivo CSV, incluindo arquivos gerados pelo `Export-Csv` cmdlet.

Você pode usar os parâmetros do `Import-Csv` cmdlet para especificar a linha de cabeçalho de coluna e o delimitador de item, ou direto `Import-Csv` para usar o separador de lista para a cultura atual como o delimitador de item.

Você também pode usar os `ConvertTo-Csv` `ConvertFrom-Csv` cmdlets e para converter objetos em cadeias de caracteres CSV (e vice-versa). Esses cmdlets são os mesmos que os `Export-CSV` `Import-Csv` cmdlets e, exceto que eles não lidam com arquivos.

Se uma entrada de linha de cabeçalho em um arquivo CSV contiver um valor vazio ou nulo, o PowerShell inserirá um nome de linha de cabeçalho padrão e exibirá uma mensagem de aviso.

A partir do PowerShell 6,0, `Import-Csv` o agora dá suporte ao formato de arquivo de log estendido W3C.

## EXEMPLOS

### Exemplo 1: importar objetos de processo

Este exemplo mostra como exportar e importar um arquivo CSV de objetos de processo.

```powershell
Get-Process | Export-Csv -Path .\Processes.csv
$P = Import-Csv -Path .\Processes.csv
$P | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name                       MemberType   Definition
----                       ----------   ----------
Equals                     Method       bool Equals(System.Object obj)
GetHashCode                Method       int GetHashCode()
GetType                    Method       type GetType()
ToString                   Method       string ToString()
BasePriority               NoteProperty string BasePriority=8
Company                    NoteProperty string Company=Microsoft Corporation
...
```

```powershell
$P | Format-Table
```

```Output
Name                   SI Handles VM            WS        PM        NPM    Path
----                   -- ------- --            --        --        ---    ----
ApplicationFrameHost   4  407     2199293489152 15884288  15151104  23792  C:\WINDOWS\system32\ApplicationFrameHost.exe
...
wininit                0  157     2199112204288 4591616   1630208   10376
winlogon               4  233     2199125549056 7659520   2826240   10992  C:\WINDOWS\System32\WinLogon.exe
WinStore.App           4  846     873435136     33652736  26607616  55432  C:\Program Files\WindowsApps\Microsoft.WindowsStore_11712.1001.13.0_x64__8weky...
WmiPrvSE               0  201     2199100219392 8830976   3297280   10632  C:\WINDOWS\system32\wbem\wmiprvse.exe
WmiPrvSE               0  407     2199157727232 18509824  12922880  16624  C:\WINDOWS\system32\wbem\wmiprvse.exe
WUDFHost               0  834     2199310204928 51945472  87441408  24984  C:\Windows\System32\WUDFHost.exe
```

O `Get-Process` cmdlet envia objetos de processo para baixo do pipeline para o `Export-Csv` . O `Export-Csv` cmdlet converte os objetos de processo em cadeias de caracteres CSV e salva as cadeias de caracteres no arquivo de Processes.csv. O `Import-Csv` cmdlet importa as cadeias de caracteres CSV do arquivo Processes.csv.
As cadeias de caracteres são salvas na `$P` variável. A `$P` variável é enviada ao pipeline para o `Get-Member` cmdlet que exibe as propriedades das cadeias de caracteres CSV importadas. A `$P` variável é enviada ao pipeline para o `Format-Table` cmdlet e exibe os objetos.

### Exemplo 2: especificar o delimitador

Este exemplo mostra como usar o parâmetro **delimitador** do `Import-Csv` cmdlet.

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter :
$P = Import-Csv -Path .\Processes.csv -Delimiter :
$P | Format-Table
```

O `Get-Process` cmdlet envia objetos de processo para baixo do pipeline para o `Export-Csv` . O `Export-Csv` cmdlet converte os objetos de processo em cadeias de caracteres CSV e salva as cadeias de caracteres no arquivo de Processes.csv.
O parâmetro **delimitador** é usado para especificar um delimitador de dois-pontos. O `Import-Csv` cmdlet importa as cadeias de caracteres CSV do arquivo Processes.csv. As cadeias de caracteres são salvas na `$P` variável. Para `$P` variável é enviado o pipeline para o `Format-Table` cmdlet.

### Exemplo 3: especificar a cultura atual para o delimitador

Este exemplo mostra como usar o `Import-Csv` cmdlet com o parâmetro **UseCulture** .

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture
Import-Csv -Path .\Processes.csv -UseCulture
```

O `Get-Culture` cmdlet usa as propriedades aninhadas **TextInfo** e **ListSeparator** para obter o separador de lista padrão da cultura atual. O `Get-Process` cmdlet envia objetos de processo para baixo do pipeline para o `Export-Csv` . O `Export-Csv` cmdlet converte os objetos de processo em cadeias de caracteres CSV e salva as cadeias de caracteres no arquivo de Processes.csv. O parâmetro **UseCulture** usa o separador de lista padrão da cultura atual. O `Import-Csv` cmdlet importa as cadeias de caracteres CSV do arquivo Processes.csv.

### Exemplo 4: alterar nomes de propriedade em um objeto importado

Este exemplo mostra como usar o parâmetro **header** de `Import-Csv` para alterar os nomes das propriedades no objeto importado resultante.

```powershell
Start-Job -ScriptBlock { Get-Process } | Export-Csv -Path .\Jobs.csv -NoTypeInformation
$Header = 'State', 'MoreData', 'StatusMessage', 'Location', 'Command', 'StateInfo', 'Finished', 'InstanceId', 'Id', 'Name', 'ChildJobs', 'BeginTime', 'EndTime', 'JobType', 'Output', 'Error', 'Progress', 'Verbose', 'Debug', 'Warning', 'Information'
# Delete the default header from file
$A = Get-Content -Path .\Jobs.csv
$A = $A[1..($A.Count - 1)]
$A | Out-File -FilePath .\Jobs.csv
$J = Import-Csv -Path .\Jobs.csv -Header $Header
$J
```

```Output
State         : Running
MoreData      : True
StatusMessage :
Location      : localhost
Command       : Get-Process
StateInfo     : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : a259eb63-6824-4b97-a033-305108ae1c2e
Id            : 1
Name          : Job1
ChildJobs     : System.Collections.Generic.List`1[System.Management.Automation.Job]
BeginTime     : 12/20/2018 18:59:57
EndTime       :
JobType       : BackgroundJob
Output        : System.Management.Automation.PSDataCollection`1[System.Management.Automation.PSObject]
Error         : System.Management.Automation.PSDataCollection`1[System.Management.Automation.ErrorRecord]
Progress      : System.Management.Automation.PSDataCollection`1[System.Management.Automation.ProgressRecord]
Verbose       : System.Management.Automation.PSDataCollection`1[System.Management.Automation.VerboseRecord]
Debug         : System.Management.Automation.PSDataCollection`1[System.Management.Automation.DebugRecord]
Warning       : System.Management.Automation.PSDataCollection`1[System.Management.Automation.WarningRecord]
Information   : System.Management.Automation.PSDataCollection`1[System.Management.Automation.InformationRecord]
```

O `Start-Job` cmdlet inicia um trabalho em segundo plano que é executado `Get-Process` . Um objeto de trabalho é enviado ao pipeline para o `Export-Csv` cmdlet e convertido em uma cadeia de caracteres CSV. O parâmetro **NoTypeInformation** remove o cabeçalho de informações de tipo da saída CSV e é opcional no PowerShell Core.
A `$Header` variável contém um cabeçalho personalizado que substitui os seguintes valores padrão: **HasMoreData** , **JobStateInfo** , **PSBeginTime** , **PSEndTime** e **PSJobTypeName** . A `$A` variável usa o `Get-Content` cmdlet para obter a cadeia de caracteres CSV do arquivo de Jobs.csv. A `$A` variável é usada para remover o cabeçalho padrão do arquivo. O `Out-File` cmdlet salva a nova versão do arquivo de Jobs.csv na `$A` variável. O `Import-Csv` cmdlet importa o arquivo de Jobs.csv e usa o parâmetro **header** para aplicar a `$Header` variável. A `$J` variável contém o **PSCustomObject** importado e exibe o objeto no console do PowerShell.

### Exemplo 5: criar um objeto personalizado usando um arquivo CSV

Este exemplo mostra como criar um objeto personalizado no PowerShell usando um arquivo CSV.

```powershell
Get-Content -Path .\Links.csv
```

```Output
113207,about_Aliases
113208,about_Arithmetic_Operators
113209,about_Arrays
113210,about_Assignment_Operators
113212,about_Automatic_Variables
113213,about_Break
113214,about_Command_Precedence
113215,about_Command_Syntax
144309,about_Comment_Based_Help
113216,about_CommonParameters
113217,about_Comparison_Operators
113218,about_Continue
113219,about_Core_Commands
113220,about_Data_Section
```

```powershell
$A = Import-Csv -Path .\Links.csv -Header 'LinkID', 'TopicTitle'
$A | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
LinkID      NoteProperty string LinkID=113207
TopicTitle  NoteProperty string TopicTitle=about_Aliases
```

```powershell
$A | Where-Object -Property TopicTitle -Like '*alias*'
```

```Output
LinkID TopicTitle
------ ----------
113207 about_Aliases
```

Para criar seu arquivo de Links.csv, use os valores mostrados na `Get-Content` saída.

O `Get-Content` cmdlet exibe o arquivo Links.csv. O `Import-Csv` cmdlet importa o arquivo de Links.csv. O parâmetro **header** especifica os nomes de propriedade **LinkId** e **TopicTitle** . Os objetos são armazenados na `$A` variável. O `Get-Member` cmdlet mostra os nomes de Propriedade do parâmetro **header** . O `Where-Object` cmdlet seleciona objetos com a propriedade **TopicTitle** que inclui o **alias** .

### Exemplo 6: importar um CSV que não tem um valor

Este exemplo mostra como o `Import-Csv` cmdlet no PowerShell responde quando a linha de cabeçalho em um arquivo CSV inclui um valor nulo ou vazio. `Import-Csv` Substitui um nome padrão para a linha de cabeçalho ausente que se torna o nome da Propriedade do objeto que `Import-Csv` retorna.

```powershell
Get-Content -Path .\Projects.csv
```

```Output
ProjectID,ProjectName,,Completed
13,Inventory,Redmond,True
440,,FarEast,True
469,Marketing,Europe,False
```

```powershell
Import-Csv -Path .\Projects.csv
```

```Output
WARNING: One or more headers were not specified. Default names starting with "H" have been used in place of any missing headers.

ProjectID ProjectName H1      Completed
--------- ----------- --      ---------
13        Inventory   Redmond True
440                   FarEast True
469       Marketing   Europe  False
```

```powershell
(Import-Csv -Path .\Projects.csv).H1
```

```Output
WARNING: One or more headers were not specified. Default names starting with "H" have been used in place of any missing headers.
Redmond
FarEast
Europe
```

Para criar seu arquivo de Projects.csv, use os valores mostrados na saída do exemplo `Get-Content` .

O `Get-Content` cmdlet exibe o arquivo Projects.csv. A linha de cabeçalho não tem um valor entre **ProjectName** e **concluída** . O `Import-Csv` cmdlet importa o arquivo de Projects.csv e exibe uma mensagem de aviso porque **H1** é um nome de cabeçalho padrão. O `(Import-Csv -Path
.\Projects.csv).H1` comando obtém os valores de propriedade **H1** e exibe um aviso.

## PARAMETERS

### -Delimitador

Especifica o delimitador que separa os valores de propriedade no arquivo CSV.
O padrão é uma vírgula (,).

Insira um caractere, como dois pontos (:).
Para especificar um ponto e vírgula (;) Coloque-o entre aspas simples.

Se você especificar um caractere que não seja o delimitador de cadeia de caracteres real no arquivo, o `Import-Csv` não poderá criar os objetos a partir das cadeias CSV e retornará as seqüências de caracteres CSV.

```yaml
Type: System.Char
Parameter Sets: DelimiterPath, DelimiterLiteralPath
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Codificação

Especifica a codificação para o arquivo CSV importado. O valor padrão é `utf8NoBOM`.

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
> O **UTF-7** * não é mais recomendado para uso. No PowerShell 7,1, um aviso será gravado se você especificar `utf7` para o parâmetro de **codificação** .

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

### -Cabeçalho

Especifica uma linha de cabeçalho de coluna alternativo para o arquivo importado. O cabeçalho de coluna determina os nomes de propriedade dos objetos criados pelo `Import-Csv` .

Insira cabeçalhos de coluna como uma lista separada por vírgulas. Não coloque a cadeia de caracteres do cabeçalho entre aspas. Coloque cada cabeçalho de coluna entre aspas simples.

Se você inserir menos cabeçalhos de coluna do que as colunas de dados, as colunas de dados restantes serão descartadas. Se você inserir mais cabeçalhos de coluna do que as colunas de dados, os cabeçalhos de coluna adicionais serão criados com colunas de dados vazias.

Ao usar o parâmetro **header** , exclua a linha de cabeçalho original do arquivo CSV. Caso contrário, `Import-Csv` cria um objeto extra dos itens na linha de cabeçalho.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Especifica o caminho para o arquivo CSV a importar. Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: DelimiterLiteralPath, CultureLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica o caminho para o arquivo CSV a importar.
Também é possível canalizar um caminho para `Import-Csv` .

```yaml
Type: System.String[]
Parameter Sets: DelimiterPath, CulturePath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UseCulture

Usa o separador de lista para a cultura atual como o delimitador de item. Para localizar o separador de lista para uma cultura, use o seguinte comando: `(Get-Culture).TextInfo.ListSeparator` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CulturePath, CultureLiteralPath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho para `Import-Csv` .

## SAÍDAS

### Objeto

Esse cmdlet retorna os objetos descritos pelo conteúdo no arquivo CSV.

## OBSERVAÇÕES

Como os objetos importados são versões CSV do tipo de objeto, eles não são reconhecidos e formatados pelas entradas de formatação de tipo do PowerShell que formatam as versões não-CSV do tipo de objeto.

O resultado de um `Import-Csv` comando é uma coleção de cadeias de caracteres que formam um objeto personalizado como tabela. Cada linha é uma cadeia de caracteres separada, portanto, você pode usar a propriedade **Count** do objeto para contar as linhas da tabela. As colunas são as propriedades do objeto e os itens nas linhas são os valores das propriedades.

A linha de cabeçalho de coluna determina o número de colunas e os nomes dessas colunas. Os nomes das colunas também são os nomes das propriedades dos objetos. A primeira linha é interpretada como os cabeçalhos de coluna, a menos que você use o parâmetro **header** para especificar cabeçalhos de coluna. Se uma linha qualquer tiver mais valores que a linha de cabeçalhos, os valores excedentes serão ignorados.

Se a linha de cabeçalho da coluna não tiver um valor ou contiver um valor nulo ou vazio, o `Import-Csv` usará **H** seguido por um número para o cabeçalho da coluna e o nome da propriedade ausentes.

No arquivo CSV, cada objeto é representado por uma lista separada por vírgulas dos valores de propriedade do objeto. Os valores de propriedade são convertidos em cadeias de caracteres usando o método **ToString ()** do objeto, para que sejam representados pelo nome do valor da propriedade. `Export-Csv` não exporta os métodos do objeto.

`Import-Csv` também dá suporte ao formato de log estendido W3C. As linhas que começam com `#` são tratadas como comentários e ignoradas, a menos que o comentário comece com `#Fields:` e contenha uma lista delimitada de nomes de coluna. Nesse caso, o cmdlet usa esses nomes de coluna. Esse é o formato padrão para o IIS do Windows e outros logs do servidor Web. Para obter mais informações, consulte [formato de arquivo de log estendido](https://www.w3.org/TR/WD-logfile.html).

## LINKS RELACIONADOS

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[Export-Csv](Export-Csv.md)

[Get-Culture](Get-Culture.md)

