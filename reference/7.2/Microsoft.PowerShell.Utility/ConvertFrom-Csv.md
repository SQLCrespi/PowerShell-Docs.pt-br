---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/21/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-csv?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Csv
ms.openlocfilehash: 951a1e4ecc46b401ae066bc3b138f264a4313e65
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597395"
---
# ConvertFrom-Csv

## SINOPSE
Converte as propriedades de objeto, do formato de valores separados por vírgulas (CSV), em versões CSV dos objetos originais.

## SYNTAX

### Delimitador (padrão)

```
ConvertFrom-Csv [[-Delimiter] <Char>] [-InputObject] <PSObject[]> [-Header <String[]>]
 [<CommonParameters>]
```

### parâmetro

```
ConvertFrom-Csv -UseCulture [-InputObject] <PSObject[]> [-Header <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `ConvertFrom-Csv` cmdlet cria objetos de cadeias de caracteres de comprimento variável csv que são gerados pelo `ConvertTo-Csv` cmdlet.

Você pode usar os parâmetros deste cmdlet para especificar a linha de cabeçalho de coluna, que determina os nomes de propriedade dos objetos resultantes, para especificar o delimitador de item ou para direcionar esse cmdlet para usar o separador de lista para a cultura atual como o delimitador.

Os objetos que o `ConvertFrom-Csv` cria são versões CSV dos objetos originais. Os valores de propriedade dos objetos CSV são versões em formato de cadeia de caracteres dos valores de propriedade dos objetos originais. As versões CSV dos objetos não têm nenhum método.

Você também pode usar os `Export-Csv` `Import-Csv` cmdlets e para converter objetos em cadeias de caracteres CSV em um arquivo (e voltar). Esses cmdlets são os mesmos que os `ConvertTo-Csv` `ConvertFrom-Csv` cmdlets e, exceto pelo fato de salvarem as cadeias de caracteres CSV em um arquivo.

## EXEMPLOS

### Exemplo 1: converter processos no computador local para o formato CSV

Este exemplo mostra como converter os processos no computador local no formato CSV e, em seguida, restaurá-los para o formulário de objeto.

```powershell
$P = Get-Process | ConvertTo-Csv
$P | ConvertFrom-Csv
```

O `Get-Process` cmdlet envia os processos pelo pipeline para o `ConvertTo-Csv` . O `ConvertTo-Csv` cmdlet converte os objetos de processo em uma série de cadeias de caracteres CSV. O `ConvertFrom-Csv` cmdlet converte as cadeias de caracteres CSV em versões CSV dos objetos de processo originais. As cadeias de caracteres CSV são salvas na `$P` variável.

### Exemplo 2: converter um objeto de dados em formato CSV e, em seguida, para o formato de objeto CSV

Este exemplo mostra como converter um objeto de dados para o formato CSV e, em seguida, para o formato de objeto CSV.

```powershell
$Date = Get-Date | ConvertTo-Csv -Delimiter ';'
ConvertFrom-Csv -InputObject $Date -Delimiter ';'
```

O primeiro comando usa `Get-Date` para enviar a data e a hora atuais para o pipeline `ConvertTo-Csv` . O `ConvertTo-Csv` cmdlet converte o objeto Date em uma série de cadeias de caracteres CSV.
O parâmetro **Delimiter** é usado para especificar um delimitador de ponto-e-vírgula. As cadeias de caracteres são salvas na `$Date` variável.

### Exemplo 3: usar o parâmetro Header para alterar os nomes das propriedades

Este exemplo mostra como usar o parâmetro **header** de `ConvertFrom-Csv` para alterar os nomes das propriedades no objeto importado resultante.

```powershell
$J = Start-Job -ScriptBlock { Get-Process } | ConvertTo-Csv  -NoTypeInformation
$Header = 'State', 'MoreData', 'StatusMessage', 'Location', 'Command', 'StateInfo', 'Finished', 'InstanceId', 'Id', 'Name', 'ChildJobs', 'BeginTime', 'EndTime', 'JobType', 'Output', 'Error', 'Progress', 'Verbose', 'Debug', 'Warning', 'Information'
# Delete the default header from $J
$J = $J[1..($J.count - 1)]
$J | ConvertFrom-Csv -Header $Header
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

O `Start-Job` cmdlet inicia um trabalho em segundo plano que é executado `Get-Process` . Um objeto de trabalho é enviado pelo pipeline para `ConvertTo-Csv` e convertido em uma cadeia de caracteres CSV. O parâmetro **NoTypeInformation** remove o cabeçalho de informações de tipo da saída CSV e é opcional no PowerShell Core. A `$Header` variável contém um cabeçalho personalizado que substitui os seguintes valores padrão: **HasMoreData**, **JobStateInfo**, **PSBeginTime**, **PSEndTime** e **PSJobTypeName**. A `$J` variável contém a cadeia de caracteres CSV e é usada para remover o cabeçalho padrão. O `ConvertFrom-Csv` cmdlet converte a cadeia de caracteres CSV em um **PSCustomObject** e usa o parâmetro **header** para aplicar a `$Header` variável.

### Exemplo 4: converter cadeias de caracteres CSV de objetos de serviço

Este exemplo mostra como usar o `ConvertFrom-Csv` cmdlet com o parâmetro **UseCulture** .

```powershell
(Get-Culture).TextInfo.ListSeparator
$Services = (Get-Service | ConvertTo-Csv)
ConvertFrom-Csv -InputObject $Services -UseCulture
```

O `Get-Culture` cmdlet usa as propriedades aninhadas **TextInfo** e **ListSeparator** para obter o separador de lista padrão da cultura atual. O `Get-Service` cmdlet envia objetos de serviço do pipeline para o `ConvertTo-Csv` . O `ConvertTo-Csv` converte os objetos de serviço em uma série de cadeias de caracteres CSV. As cadeias de caracteres CSV são armazenadas na `$Services` variável. O `ConvertFrom-Csv` cmdlet usa o parâmetro **InputObject** e converte as cadeias de caracteres CSV da `$Services` variável. O parâmetro **UseCulture** usa o separador de lista padrão da cultura atual.

Quando o parâmetro **UseCulture** for usado, certifique-se de que o separador de lista padrão da cultura atual corresponda ao delimitador usado nas cadeias de caracteres CSV. Caso contrário, `ConvertFrom-Csv` o não pode gerar objetos a partir de cadeias de caracteres CSV.

## PARAMETERS

### -Delimitador

Especifica o delimitador que separa os valores de propriedade nas cadeias CSV.
O padrão é uma vírgula (,).

Insira um caractere, como dois pontos (:).
Para especificar um ponto e vírgula (;) Coloque-o entre aspas simples.

Se você especificar um caractere que não seja o delimitador de cadeia de caracteres real no arquivo, o `ConvertFrom-Csv` não poderá criar os objetos a partir das cadeias CSV e retornará as seqüências de caracteres CSV.

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cabeçalho

Especifica uma linha de cabeçalho de coluna alternativo para a cadeia de caracteres importada. O cabeçalho de coluna determina os nomes de propriedade dos objetos criados pelo `ConvertFrom-Csv` .

Insira cabeçalhos de coluna como uma lista separada por vírgulas. Não coloque a cadeia de caracteres do cabeçalho entre aspas. Coloque cada cabeçalho de coluna entre aspas simples.

Se você inserir menos cabeçalhos de coluna do que as colunas de dados, as colunas de dados restantes serão descartadas. Se você inserir mais cabeçalhos de coluna do que as colunas de dados, os cabeçalhos de coluna adicionais serão criados com colunas de dados vazias.

Ao usar o parâmetro **header** , omita a cadeia de caracteres do cabeçalho de coluna das cadeias de caracteres CSV. Caso contrário, esse cmdlet cria um objeto extra dos itens na linha de cabeçalho.

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

### -InputObject

Especifica as cadeias de caracteres CSV a serem convertidas em objetos. Insira uma variável que contém as cadeias de caracteres CSV ou digite um comando ou expressão que obtém as cadeias CSV. Também é possível canalizar as cadeias de caracteres CSV para `ConvertFrom-Csv` .

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
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
Parameter Sets: UseCulture
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

Você pode canalizar cadeias de caracteres CSV para este cmdlet.

## SAÍDAS

### System. Management. Automation. PSObject

Esse cmdlet retorna os objetos descritos pelas propriedades nas cadeias de caracteres CSV.

## OBSERVAÇÕES

Como os objetos importados são versões CSV do tipo de objeto, eles não são reconhecidos e formatados pelas entradas de formatação de tipo do PowerShell que formatam as versões não-CSV do tipo de objeto.

No formato CSV, cada objeto é representado por uma lista dos valores de propriedade do objeto separados por vírgulas. Os valores de propriedade são convertidos em cadeias de caracteres (usando o método **ToString ()** do objeto), portanto, eles são representados pelo nome do valor da propriedade. Esse cmdlet não exporta os métodos do objeto.

## LINKS RELACIONADOS

[ConvertTo-Csv](ConvertTo-Csv.md)

[Export-CSV](Export-Csv.md)

[Import-Csv](Import-Csv.md)

