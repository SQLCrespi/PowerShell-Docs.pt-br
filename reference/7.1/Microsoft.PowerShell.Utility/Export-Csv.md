---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: f920130ec8354b61b0bb3617e061520271df0eed
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913229"
---
# Export-Csv

## SINOPSE
Converte objetos em uma série de cadeias de caracteres de valores separados por vírgulas (CSV) e salva as cadeias de caracteres em um arquivo.

## SYNTAX

### Delimitador (padrão)

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### parâmetro

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## DESCRIPTION

O `Export-CSV` cmdlet cria um arquivo CSV dos objetos que você envia. Cada objeto é uma linha que inclui uma lista separada por vírgulas dos valores de Propriedade do objeto. Você pode usar o `Export-CSV` cmdlet para criar planilhas e compartilhar dados com programas que aceitam arquivos CSV como entrada.

Não formate objetos antes de enviá-los para o `Export-CSV` cmdlet. Se `Export-CSV` o receber objetos formatados, o arquivo CSV conterá as propriedades de formato em vez das propriedades do objeto. Para exportar apenas as propriedades selecionadas de um objeto, use o `Select-Object` cmdlet.

## EXEMPLOS

### Exemplo 1: exportar Propriedades do processo para um arquivo CSV

Este exemplo seleciona objetos de **processo** com propriedades específicas, exporta os objetos para um arquivo CSV.

```powershell
Get-Process -Name WmiPrvSE | Select-Object -Property BasePriority,Id,SessionId,WorkingSet |
  Export-Csv -Path .\WmiData.csv -NoTypeInformation
Import-Csv -Path .\WmiData.csv
```

```Output
BasePriority Id    SessionId WorkingSet
------------ --    --------- ----------
8            976   0         20267008
8            2292  0         36786176
8            3816  0         30351360
8            8604  0         15011840
8            10008 0         8830976
8            11764 0         14237696
8            54632 0         9502720
```

O `Get-Process` cmdlet obtém os objetos de **processo** . O parâmetro **Name** filtra a saída para incluir apenas os objetos de processo do WmiPrvSE. Os objetos de processo são enviados por meio do pipeline para o `Select-Object` cmdlet. `Select-Object` usa o parâmetro **Property** para selecionar um subconjunto das propriedades do objeto de processo. Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet. `Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV. O parâmetro **path** especifica que o arquivo de WmiData.csv é salvo no diretório atual. O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6. O `Import-Csv` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.

### Exemplo 2: exportar processos para um arquivo delimitado por vírgula

Este exemplo obtém objetos de **processo** e exporta os objetos para um arquivo CSV.

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

O `Get-Process` cmdlet obtém objetos de **processo** . Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet. `Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.
O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual. O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6. O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.

### Exemplo 3: exportar processos para um arquivo delimitado por ponto e vírgula

Este exemplo obtém objetos de **processo** e exporta os objetos para um arquivo com um delimitador de ponto-e-vírgula.

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

O `Get-Process` cmdlet obtém objetos de **processo** . Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet. `Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.
O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual. O parâmetro **delimitador** especifica um ponto e vírgula para separar os valores da cadeia de caracteres. O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6. O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.

### Exemplo 4: exportar processos usando o separador de lista da cultura atual

Este exemplo obtém objetos de **processo** e exporta os objetos para um arquivo. O delimitador é o separador de lista da cultura atual.

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

O `Get-Culture` cmdlet usa as propriedades aninhadas **TextInfo** e **ListSeparator** e exibe o separador de lista padrão da cultura atual. O `Get-Process` cmdlet obtém objetos de **processo** .
Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet. `Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV. O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual. O parâmetro **UseCulture** usa o separador de lista padrão da cultura atual como o delimitador. O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6. O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.

### Exemplo 5: exportar processos com informações de tipo

Este exemplo explica como incluir as informações de cabeçalho de **#TYPE** em um arquivo CSV. O cabeçalho de **#TYPE** é o padrão nas versões anteriores ao PowerShell 6,0.

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -IncludeTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

O `Get-Process` cmdlet obtém objetos de **processo** . Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet. `Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.
O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual. O **IncludeTypeInformation** inclui o cabeçalho de informações **#TYPE** na saída CSV. O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.

### Exemplo 6: exportar e acrescentar objetos a um arquivo CSV

Este exemplo descreve como exportar objetos para um arquivo CSV e usar o parâmetro **Append** para adicionar objetos a um arquivo existente.

```powershell
$AppService = (Get-Service -DisplayName *Application* | Select-Object -Property DisplayName, Status)
$AppService | Export-Csv -Path .\Services.Csv -NoTypeInformation
Get-Content -Path .\Services.Csv
$WinService = (Get-Service -DisplayName *Windows* | Select-Object -Property DisplayName, Status)
$WinService | Export-Csv -Path ./Services.csv -NoTypeInformation -Append
Get-Content -Path .\Services.Csv
```

```Output
"DisplayName","Status"
"Application Layer Gateway Service","Stopped"
"Application Identity","Running"
"Windows Audio Endpoint Builder","Running"
"Windows Audio","Running"
"Windows Event Log","Running"
```

O `Get-Service` cmdlet obtém os objetos de serviço. O parâmetro **DisplayName** retorna serviços que contêm o aplicativo Word. Os objetos de serviço são enviados pelo pipeline para o `Select-Object` cmdlet. `Select-Object` usa o parâmetro **Property** para especificar as propriedades **DisplayName** e **status** . A `$AppService` variável armazena os objetos.

Os `$AppService` objetos são enviados para o pipeline para o `Export-Csv` cmdlet. `Export-Csv` Converte os objetos de serviço em uma série de cadeias de caracteres CSV. O parâmetro **path** especifica que o arquivo de Services.csv é salvo no diretório atual. O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6. O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.

Os `Get-Service` `Select-Object` cmdlets e são repetidos para serviços que contêm a palavra Windows. A `$WinService` variável armazena os objetos de serviço. O `Export-Csv` cmdlet usa o parâmetro **Append** para especificar que os `$WinService` objetos sejam adicionados ao arquivo de Services.csv existente. O `Get-Content` cmdlet é repetido para exibir o arquivo atualizado que inclui os dados acrescentados.

### Exemplo 7: o cmdlet Format dentro de um pipeline cria resultados inesperados

Este exemplo mostra por que é importante não usar um cmdlet de formato em um pipeline. Quando a saída inesperada for recebida, solucione o problema da sintaxe do pipeline.

```powershell
Get-Date | Select-Object -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\DateTime.csv -NoTypeInformation
Get-Content -Path .\DateTime.csv
```

```Output
"DateTime","Day","DayOfWeek","DayOfYear"
"Wednesday, January 2, 2019 14:59:34","2","Wednesday","2"
```

```powershell
Get-Date | Format-Table -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\FTDateTime.csv -NoTypeInformation
Get-Content -Path .\FTDateTime.csv
```

```Output
"ClassId2e4f51ef21dd47e99d3c952918aff9cd","pageHeaderEntry","pageFooterEntry","autosizeInfo", ...
"033ecb2bc07a4d43b5ef94ed5a35d280",,,,"Microsoft.PowerShell.Commands.Internal.Format. ...
"9e210fe47d09416682b841769c78b8a3",,,,,
"27c87ef9bbda4f709f6b4002fa4af63c",,,,,
"4ec4f0187cb04f4cb6973460dfe252df",,,,,
"cf522b78d86c486691226b40aa69e95c",,,,,
```

O `Get-Date` cmdlet obtém o objeto **DateTime** . O objeto é enviado ao pipeline para o `Select-Object` cmdlet. `Select-Object` usa o parâmetro **Property** para selecionar um subconjunto das propriedades do objeto. O objeto é enviado ao pipeline para o `Export-Csv` cmdlet. `Export-Csv` Converte o objeto em um formato CSV. O parâmetro **path** especifica que o arquivo de DateTime.csv é salvo no diretório atual. O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6. O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo CSV localizado no diretório atual.

Quando o `Format-Table` cmdlet é usado no pipeline para selecionar propriedades, resultados inesperados são recebidos. `Format-Table` envia objetos de formato de tabela por meio do pipeline para o `Export-Csv` cmdlet, em vez do objeto **DateTime** . `Export-Csv` Converte os objetos de formato de tabela em uma série de cadeias de caracteres CSV. O `Get-Content` cmdlet exibe o arquivo CSV que contém os objetos de formato de tabela.

### Exemplo 8: usando o parâmetro Force para substituir arquivos somente leitura

Este exemplo cria um arquivo somente leitura vazio e usa o parâmetro **Force** para atualizar o arquivo.

```powershell
New-Item -Path .\ReadOnly.csv -ItemType File
Set-ItemProperty -Path .\ReadOnly.csv -Name IsReadOnly -Value $true
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
```

```Output
Export-Csv : Access to the path 'C:\ReadOnly.csv' is denied.
At line:1 char:15
+ Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
+               ~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (:) [Export-Csv], UnauthorizedAccessException
+ FullyQualifiedErrorId : FileOpenFailure,Microsoft.PowerShell.Commands.ExportCsvCommand
```

```powershell
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation -Force
Get-Content -Path .\ReadOnly.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

O `New-Item` cmdlet usa os parâmetros **Path** e **ItemType** para criar o arquivo de ReadOnly.csv no diretório atual. O `Set-ItemProperty` cmdlet usa os parâmetros **Name** e **Value** para alterar a propriedade **IsReadOnly** do arquivo para true. O `Get-Process` cmdlet obtém objetos de **processo** . Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet. `Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV. O parâmetro **path** especifica que o arquivo de ReadOnly.csv é salvo no diretório atual. O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6. A saída mostra que o arquivo não foi gravado porque o acesso foi negado.

O parâmetro **Force** é adicionado ao `Export-Csv` cmdlet para forçar a exportação a gravar no arquivo. O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.

### Exemplo 9: usando o parâmetro Force com Append

Este exemplo mostra como usar os parâmetros **Force** e **Append** . Quando esses parâmetros são combinados, as propriedades de objeto incompatíveis podem ser gravadas em um arquivo CSV.

```powershell
$Content = [PSCustomObject]@{Name = 'PowerShell Core'; Version = '6.0'}
$Content | Export-Csv -Path .\ParmFile.csv -NoTypeInformation
$AdditionalContent = [PSCustomObject]@{Name = 'Windows PowerShell'; Edition = 'Desktop'}
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
```

```Output
Export-Csv : Cannot append CSV content to the following file: ParmFile.csv.
The appended object does not have a property that corresponds to the following column:
Version. To continue with mismatched properties, add the -Force parameter, and then retry
 the command.
At line:1 char:22
+ $AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (Version:String) [Export-Csv], InvalidOperationException
+ FullyQualifiedErrorId : CannotAppendCsvWithMismatchedPropertyNames,Microsoft.PowerShell. ...
```

```powershell
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append -Force
Import-Csv -Path .\ParmFile.csv
```

```Output
Name               Version
----               -------
PowerShell Core    6.0
Windows PowerShell
```

Uma expressão cria o **PSCustomObject** com propriedades **Name** e **version** . Os valores são armazenados na `$Content` variável. A `$Content` variável é enviada ao pipeline para o `Export-Csv` cmdlet. `Export-Csv` usa o parâmetro **path** e salva o arquivo ParmFile.csv no diretório atual. O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.

Outra expressão cria um **PSCustomObject** com as propriedades **Name** e **Edition** . Os valores são armazenados na `$AdditionalContent` variável. A `$AdditionalContent` variável é enviada ao pipeline para o `Export-Csv` cmdlet. O parâmetro **Append** é usado para adicionar os dados ao arquivo. O acréscimo falha porque há uma incompatibilidade de nome de propriedade entre a **versão** e a **edição**.

O `Export-Csv` parâmetro **Force** do cmdlet é usado para forçar a exportação a gravar no arquivo. A propriedade de **edição** é descartada. O `Import-Csv` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.

### Exemplo 10: exportar para CSV com aspas em cerca de duas colunas

Este exemplo converte um objeto **DateTime** em uma cadeia de caracteres CSV.

```powershell
Get-Date | Export-Csv  -QuoteFields "DateTime","Date" -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### Exemplo 11: exportar para CSV com aspas somente quando necessário

Este exemplo converte um objeto **DateTime** em uma cadeia de caracteres CSV.

```powershell
Get-Date | Export-Csv  -UseQuotes AsNeeded -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## PARAMETERS

### -Acrescentar

Use esse parâmetro para que `Export-CSV` o adicione a saída de CSV ao final do arquivo especificado. Sem esse parâmetro, `Export-CSV` o substitui o conteúdo do arquivo sem aviso.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

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

### -Delimitador

Especifica um delimitador para separar os valores da propriedade. O padrão é uma vírgula ( `,` ). Insira um caractere, como dois-pontos ( `:` ). Para especificar um ponto e vírgula ( `;` ), coloque-o entre aspas.

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

### -Codificação

Especifica a codificação do arquivo CSV exportado. O valor padrão é `utf8NoBOM`.

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

### -Force

Esse parâmetro permite `Export-Csv` substituir arquivos pelo atributo **somente leitura** .

Quando os parâmetros **Force** e **Append** são combinados, os objetos que contêm propriedades incompatíveis podem ser gravados em um arquivo CSV. Somente as propriedades que correspondem são gravadas no arquivo. As propriedades incompatíveis são descartadas.

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

### -IncludeTypeInformation

Quando esse parâmetro é usado, a primeira linha da saída CSV contém **#TYPE** seguido pelo nome totalmente qualificado do tipo de objeto. Por exemplo, **#TYPE System. Diagnostics. Process**.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ITI

Required: False
Position: Named
Default value: #TYPE <Object>
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica os objetos a exportar como cadeias CSV. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos. Você também pode canalizar objetos para `Export-CSV` .

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Especifica o caminho para o arquivo de saída CSV. Ao contrário de **Path**, o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, use aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber

Use esse parâmetro para que `Export-CSV` o não substitua um arquivo existente. Por padrão, se o arquivo existir no caminho especificado, `Export-CSV` o substituirá o arquivo sem aviso.

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

### -NoTypeInformation

Remove o cabeçalho de informações **#TYPE** da saída. Esse parâmetro se tornou o padrão no PowerShell 6,0 e está incluído para compatibilidade com versões anteriores.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Um parâmetro necessário que especifica o local para salvar o arquivo de saída CSV.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseCulture

Usa o separador de lista para a cultura atual como o delimitador de item. Para localizar o separador de lista para uma cultura, use o seguinte comando: `(Get-Culture).TextInfo.ListSeparator` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

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

### -WhatIf

Impede que o cmdlet seja processado ou faça alterações. A saída mostra o que aconteceria se o cmdlet fosse executado.

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

### -QuoteFields

Especifica os nomes das colunas que devem ser entre aspas. Quando esse parâmetro é usado, somente as colunas especificadas são citadas. Esse parâmetro foi adicionado no PowerShell 7,0.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: QF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseQuotes

Especifica quando as aspas são usadas nos arquivos CSV. Os valores possíveis são:

- Nunca-não citar nada
- Sempre-cotação de tudo (comportamento padrão)
- Apenas campos de cotação necessários que contêm um caractere delimitador

Esse parâmetro foi adicionado no PowerShell 7,0.

```yaml
Type: Microsoft.PowerShell.Commands.BaseCsvWritingCommand+QuoteKind
Parameter Sets: (All)
Aliases: UQ

Required: False
Position: Named
Default value: Always
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

É possível canalizar qualquer objeto com um adaptador de sistema de tipo estendido (ETS) para o `Export-CSV` .

## SAÍDAS

### System.String

A lista CSV é enviada para o arquivo designado no parâmetro Path.

## OBSERVAÇÕES

O `Export-CSV` cmdlet converte os objetos que você envia em uma série de cadeias de caracteres CSV e salva-os no arquivo de texto especificado. Você pode usar `Export-CSV -IncludeTypeInformation` o para salvar objetos em um arquivo CSV e, em seguida, usar o `Import-Csv` cmdlet para criar objetos a partir do texto no arquivo CSV.

No arquivo CSV, cada objeto é representado por uma lista separada por vírgulas dos valores de propriedade do objeto. Os valores de propriedade são convertidos em cadeias de caracteres usando o método **ToString ()** . As cadeias de caracteres são representadas pelo nome do valor da propriedade. `Export-CSV -IncludeTypeInformation` não exporta os métodos do objeto.

As cadeias de caracteres CSV são saídas da seguinte maneira:

- Se **IncludeTypeInformation** for usado, a primeira cadeia de caracteres conterá o cabeçalho de informações **#TYPE** seguido pelo nome totalmente qualificado do tipo de objeto.
  Por exemplo, **#TYPE System. Diagnostics. Process**.
- Se **IncludeTypeInformation** não for usado, a primeira cadeia de caracteres incluirá os cabeçalhos de coluna. Os cabeçalhos contêm os nomes de Propriedade do primeiro objeto como uma lista separada por vírgulas.
- As cadeias de caracteres restantes contêm listas separadas por vírgulas dos valores de propriedade de cada objeto.

A partir do PowerShell 6,0, o comportamento padrão de `Export-CSV` é não incluir as informações de **#TYPE** no CSV e **NoTypeInformation** é implícito. **IncludeTypeInformation** pode ser usado para incluir as informações de **#TYPE** e emular o comportamento padrão de `Export-CSV` antes do PowerShell 6,0.

Quando você envia vários objetos ao `Export-CSV` , `Export-CSV` o organiza o arquivo com base nas propriedades do primeiro objeto que você envia. Se os objetos restantes não tiverem uma das propriedades especificadas, o valor da propriedade desse primeiro objeto será nulo, condição esta representada por duas vírgulas consecutivas. Se os objetos restantes têm propriedades adicionais, os valores de propriedade não são incluídos no arquivo.

Você pode usar o `Import-Csv` cmdlet para recriar objetos a partir de cadeias de caracteres CSV nos arquivos. Os objetos resultantes são versões em CSV dos objetos originais, que consistem em representações dos valores das propriedades em cadeia, sem métodos.

Os `ConvertTo-Csv` `ConvertFrom-Csv` cmdlets e convertem objetos em cadeias de caracteres CSV e de cadeias de caracteres CSV. `Export-CSV` é o mesmo `ConvertTo-CSV` que, exceto pelo fato de salvar as cadeias de caracteres CSV em um arquivo.

## LINKS RELACIONADOS

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[Format-Table](Format-Table.md)

[Import-Csv](Import-Csv.md)

[Select-Object](Select-Object.md)
