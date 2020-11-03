---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: a222044b9dc62a7b0834f7350fd32bed2e95d9a9
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196503"
---
# ConvertFrom-Json

## SINOPSE
Converte uma cadeia de caracteres formatada em JSON em um objeto personalizado ou uma tabela de hash.

## SYNTAX

```
ConvertFrom-Json [-InputObject] <String> [-AsHashtable] [-Depth <Int32>] [-NoEnumerate] [<CommonParameters>]
```

## DESCRIPTION

O `ConvertFrom-Json` cmdlet converte uma cadeia de caracteres formatada JavaScript Object Notation (JSON) em um objeto **PSCustomObject** personalizado que tem uma propriedade para cada campo na cadeia de caracteres JSON. JSON utilizado comumente por sites da web para fornecer uma representação textual de objetos. O padrão JSON não proíbe o uso que seja proibido com um **PSCustomObject** . Por exemplo, se a cadeia de caracteres JSON contiver chaves duplicadas, somente a última chave será usada por esse cmdlet. Consulte outros exemplos abaixo.

Para gerar uma cadeia de caracteres JSON de qualquer objeto, use o `ConvertTo-Json` cmdlet.

Esse cmdlet foi introduzido no PowerShell 3,0.

> [!NOTE]
> A partir do PowerShell 6, esse cmdlet dá suporte a JSON com comentários. Os comentários aceitos são iniciados com duas barras "/" ( `//` ). O comentário não será representado nos dados e poderá ser gravado no arquivo sem corromper os dados ou gerar um erro como fazia no PowerShell 5,1.

## EXEMPLOS

### Exemplo 1: converter um objeto DateTime em um objeto JSON

Esse comando usa os `ConvertTo-Json` `ConvertFrom-Json` cmdlets e para converter um objeto **DateTime** do `Get-Date` cmdlet em um objeto JSON, em seguida, em um **PSCustomObject** .

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : Friday, January 13, 2012 8:06:31 PM
Date        : 1/13/2012 8:00:00 AM
Day         : 13
DayOfWeek   : 5
DayOfYear   : 13
Hour        : 20
Kind        : 2
Millisecond : 400
Minute      : 6
Month       : 1
Second      : 31
Ticks       : 634620819914009002
TimeOfDay   : @{Ticks=723914009002; Days=0; Hours=20; Milliseconds=400; Minutes=6; Seconds=31; TotalDays=0.83786343634490734; TotalHours=20.108722472277776; TotalMilliseconds=72391400.900200009; TotalMinutes=1206.5233483366667;TotalSeconds=72391.4009002}
Year        : 2012
```

O exemplo usa o `Select-Object` cmdlet para obter todas as propriedades do objeto **DateTime** . Ele usa o `ConvertTo-Json` cmdlet para converter o objeto **DateTime** em uma cadeia de caracteres formatada como um objeto JSON e o `ConvertFrom-Json` cmdlet para converter a cadeia de caracteres formatada em JSON em um objeto **PSCustomObject** .

### Exemplo 2: obter cadeias de caracteres JSON de um serviço Web e convertê-las em objetos do PowerShell

Esse comando usa o `Invoke-WebRequest` cmdlet para obter cadeias de caracteres JSON de um serviço Web e, em seguida, usa o `ConvertFrom-Json` cmdlet para converter o conteúdo JSON em objetos que podem ser gerenciados no PowerShell.

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

Você também pode usar o `Invoke-RestMethod` cmdlet, que converte automaticamente o conteúdo JSON em objetos.

### Exemplo 3: converter uma cadeia de caracteres JSON em um objeto personalizado

Este exemplo mostra como usar o `ConvertFrom-Json` cmdlet para converter um arquivo JSON em um objeto personalizado do PowerShell.

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

O comando usa Get-Content cmdlet para obter as cadeias de caracteres em um arquivo JSON. Em seguida, ele usa o operador de pipeline para enviar a cadeia de caracteres delimitada ao `ConvertFrom-Json` cmdlet, que converte-o em um objeto personalizado.

### Exemplo 4: converter uma cadeia de caracteres JSON em uma tabela de hash

Esse comando mostra um exemplo em que a `-AsHashtable` opção pode superar as limitações do comando.

```powershell
'{ "key":"value1", "Key":"value2" }' | ConvertFrom-Json -AsHashtable
```

A cadeia de caracteres JSON contém dois pares chave-valor com chaves que diferem apenas em maiúsculas e minúsculas. Sem a opção, o comando teria gerado um erro.

### Exemplo 5: viagem de ida e volta de uma única matriz de elemento

Esse comando mostra um exemplo em que a `-NoEnumerate` opção é usada para fazer ida e volta de uma matriz JSON de um único elemento.

```powershell
Write-Output "With -NoEnumerate: $('[1]' | ConvertFrom-Json -NoEnumerate | ConvertTo-Json -Compress)"
Write-Output "Without -NoEnumerate: $('[1]' | ConvertFrom-Json | ConvertTo-Json -Compress)"
```

```Output
With -NoEnumerate: [1]
Without -NoEnumerate: 1
```

A cadeia de caracteres JSON contém uma matriz com um único elemento. Sem a opção, converter o JSON em um PSObject e, em seguida, convertê-lo novamente com os `ConvertTo-Json` resultados do comando em um único inteiro.

## PARAMETERS

### -AsHashTable

Converte o JSON em um objeto de tabela de hash. Essa opção foi introduzida no PowerShell 6,0. Há vários cenários em que ele pode superar algumas limitações do `ConvertFrom-Json` cmdlet.

- Se o JSON contiver uma lista com chaves que diferem apenas em maiúsculas e minúsculas. Sem a opção, essas chaves seriam vistas como chaves idênticas e, portanto, apenas a última seria usada.
- Se o JSON contiver uma chave que seja uma cadeia de caracteres vazia. Sem a opção, o cmdlet geraria um erro, pois um não `PSCustomObject` permite isso, mas uma tabela de hash faz. Um exemplo de caso de uso onde isso pode ocorrer são `project.lock.json` os arquivos.
- As tabelas de hash podem ser processadas mais rapidamente para determinadas estruturas de dados.

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

### -Profundidade

Obtém ou define a profundidade máxima que a entrada JSON pode ter. Por padrão, é 1024.

Esse parâmetro foi introduzido no PowerShell 6,2.

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

### -InputObject

Especifica as cadeias de caracteres JSON a converter em objetos JSON. Insira uma variável que contenha a cadeia de caracteres ou digite um comando ou expressão que obtenha essa cadeia. Você também pode canalizar uma cadeia de caracteres para `ConvertFrom-Json` .

O parâmetro **InputObject** é obrigatório, mas seu valor pode ser uma cadeia de caracteres vazia. Quando o objeto de entrada é uma cadeia de caracteres vazia, o não `ConvertFrom-Json` gera nenhuma saída. O valor **InputObject** não pode ser `$null` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Noenumerate

Especifica que a saída não é enumerada.

Definir esse parâmetro faz com que as matrizes sejam enviadas como um único objeto em vez de enviar cada elemento separadamente. Isso garante que o JSON possa ser arredondado via `ConvertTo-Json` .

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

### System.String

É possível canalizar uma cadeia de caracteres JSON para `ConvertFrom-Json` .

## SAÍDAS

### PSCustomObject

### System.Collections.Hashtable

## OBSERVAÇÕES

Esse cmdlet é implementado usando [Newtonsoft JSON.net](https://www.newtonsoft.com/json).

A partir do PowerShell 6, o `ConvertTo-Json` tenta converter cadeias de caracteres formatadas como carimbos de **Data/** hora em valores DateTime. O valor convertido é uma `[datetime]` instância com um `Kind` conjunto de propriedades da seguinte maneira:

- `Unspecified`, se não houver informações de fuso horário na cadeia de caracteres de entrada.
- `Utc`, se as informações de fuso horário forem à direita `Z` .
- `Local`, se as informações de fuso horário forem dadas como um _deslocamento_ UTC à direita como `+02:00` . O deslocamento é convertido corretamente no fuso horário configurado do chamador. A formatação de saída padrão não indica o deslocamento de fuso horário original.

## LINKS RELACIONADOS

[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[ConvertTo-Json](ConvertTo-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)

