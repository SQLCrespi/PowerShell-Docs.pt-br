---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convert-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-String
ms.openlocfilehash: 29ec9e21277bae02ab94ce5e862787c86a87b439
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193853"
---
# Convert-String

## SINOPSE
Formata uma cadeia de caracteres para fazer a correspondência de exemplos.

## SYNTAX

```
Convert-String [-Example <System.Collections.Generic.List`1[System.Management.Automation.PSObject]>]
 -InputObject <String> [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Convert-String** formata uma cadeia de caracteres para corresponder ao formato dos exemplos.

## EXEMPLOS

### Exemplo 1: converter o formato de uma cadeia de caracteres

```powershell
"Mu Han", "Jim Hance", "David Ahs", "Kim Akers" | Convert-String -Example "Ed Wilson=Wilson, E."
```

```output
Han, M.
Hance, J.
Ahs, D.
Akers, K.
```

O primeiro comando cria uma matriz que contém o nome e o sobrenome.

O segundo comando formata os nomes de acordo com o exemplo.
Ele coloca o sobrenome primeiro na saída, seguido por um inicial.

### Exemplo 2: simplificar o formato de uma cadeia de caracteres

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=last, first"
```

```output
Bach, Johann
Mozart, Wolfgang
Chopin, Frederic
Brahms, Johannes
```

O primeiro comando cria uma matriz que contém nome, meio e sobrenome.
Observe que a última entrada não tem um segundo nome.

O segundo comando formata os nomes de acordo com o exemplo.
Ele coloca o sobrenome primeiro na saída, seguido pelo primeiro nome.
Todos os nomes de meio removidos; a entrada sem o nome do meio é manipulada corretamente.

### Exemplo 3: gerenciamento de saída quando cadeias de caracteres não correspondem ao exemplo

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=middle, first"
```

```output
Sebastian, Johann
Amadeus, Wolfgang
Francois, Frederic
```

O primeiro comando cria uma matriz que contém nome, meio e sobrenome.
Observe que a última entrada não tem um segundo nome.

O segundo comando formata os nomes de acordo com o exemplo.
Ele coloca o **nome do meio** primeiro na saída, seguido pelo primeiro nome.
A última entrada em **$Composers** é ignorada porque não corresponde ao padrão de exemplo: ela não tem um nome de meio.

### Exemplo 4: cuidado com espaços de beleza

```powershell
$composers = @("Antonio Vivaldi", "Richard Wagner ", "Franz Schubert", "Johannes Brahms ")
$composers | Convert-String -Example "Patti Fuller = Fuller, P."
```

```output
 Wagner, R.
 Brahms, J.
```

O primeiro comando cria uma matriz de nome e sobrenome.
Observe que o segundo e o quarto itens têm um espaço à direita extra, após o último nome.

O segundo comando converte todas as cadeias de caracteres que correspondem ao padrão de exemplo: _Word, espaço, palavra e espaço final à direita_ , tudo isso antes do sinal de igual.
Além disso, observe o espaço à esquerda na saída.

### Exemplo 5: Formatar informações de processo com vários padrões

```powershell
$ExamplePatterns = @(
    @{before='"Hello","World"'; after='World: Hello'},
    @{before='"Hello","1"'; after='1: Hello'},
    @{before='"Hello-World","22"'; after='22: Hello-World'},
    @{before='"hello world","333"'; after='333: hello world'}
)
$Processes = Get-Process   | Select-Object -Property ProcessName, Id | ConvertTo-Csv -NoTypeInformation
$Processes | Convert-String -Example $ExamplePatterns
```

```output
Id: ProcessName
4368: AGSService
8896: Amazon Music Helper
4420: AppleMobileDeviceService
...
11140: git-bash
0: Idle
...
56: Secure System
...
13028: WmiPrvSE
2724: WUDFHost
2980: WUDFHost
3348: WUDFHost
```

**$ExamplePatterns** define diferentes padrões esperados nos dados, por meio de exemplos.

O primeiro padrão, `@{before='"Hello","World"'; after='World: Hello'}` , lido da seguinte maneira: _espera-se cadeias de caracteres em que uma palavra é colocada entre aspas duplas, depois uma vírgula_ 
 _e, em seguida, a segunda e última, palavra entre aspas;_ 
 _sem espaços na cadeia de caracteres. Na saída: Coloque a segunda palavra primeiro,_ 
 _sem aspas, um único espaço e, em seguida, a primeira palavra, sem aspas._

O segundo padrão, `@{before='"Hello","1"'; after='1: Hello'}` , lê da seguinte maneira: _espera-se cadeias de caracteres em que uma palavra é colocada entre aspas duplas, depois uma vírgula_ 
 _e um número entre aspas;_ 
 _sem espaços na cadeia de caracteres. Na saída: Coloque o número primeiro,_ 
 _sem aspas, um único espaço e, em seguida, a palavra, sem aspas._

O terceiro padrão, `@{before='"Hello-World","22"'; after='22: Hello-World'}` , lido da seguinte maneira: espera-se _cadeias de caracteres em que duas palavras com um hífen entre elas ficam entre_ 
 _aspas duplas, depois uma vírgula e um número entre aspas;_ 
 _sem espaços entre a vírgula e a terceira aspa dupla._ 
 _Na saída: Coloque o número primeiro, sem aspas, um único espaço,_ 
 _e, em seguida, as palavras hifenizadas, sem aspas._

O quarto e último padrão, `@{before='"hello world","333"'; after='333: hello world'}` , leituras da seguinte maneira: espera-se _cadeias de caracteres em que duas palavras com um espaço entre elas são colocadas entre_ 
 _aspas duplas, depois uma vírgula e um número entre aspas;_ 
 _sem espaços entre a vírgula e a terceira aspa dupla._ 
 _Na saída: Coloque o número primeiro, sem aspas, um único espaço,_ 
 _e, em seguida, as palavras com o espaço entre entre aspas._

O primeiro comando obtém todos os processos usando o cmdlet Get-Process.
O comando os passa para o cmdlet Select-Object, que seleciona o nome do processo e a ID do processo. No final do pipeline, o comando converte a saída em valores separados por vírgula, sem informações de tipo, usando o cmdlet ConvertTo-Csv.
O comando armazena os resultados na variável **$Processes** .
Agora **$Processes** contém nomes de processo e PID.

O segundo comando especifica uma variável de exemplo que altera a ordem dos itens de entrada.
O comando reverte cada cadeia de caracteres em **$Processes** .

>**Observação** O quarto padrão indica implicitamente que duas ou mais palavras separadas por espaços são correspondidas.
>
>Sem o quarto padrão, somente a primeira palavra da cadeia de caracteres entre aspas duplas é correspondida.

## PARAMETERS

### -Exemplo

Especifica uma lista de exemplos do formato de destino.
Especifique os pares separados pelo sinal de igual (=), com o padrão de origem à esquerda e o padrão de destino à direita, como nos exemplos a seguir:

* `-Example "Hello World=World, Hello"`
* `-Example "Hello World=World: Hello",'"Hello","1"=1: Hello'`

>**Observação** O segundo exemplo usa uma lista de padrões

Como alternativa, especifique uma lista de tabelas de hash que contenham as propriedades **before** e **After** .

* `-Example @{before='"Hello","World"'; after='World: Hello'}, @{before='"Hello","1"'; after='1: Hello'}`

>**Cuidado** Evite usar espaços em volta do sinal de igual, pois eles são tratados como parte do padrão.

```yaml
Type: System.Collections.Generic.List`1[System.Management.Automation.PSObject]
Parameter Sets: (All)
Aliases: E

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica uma cadeia de caracteres a ser formatada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### String

Você pode canalizar cadeias de caracteres para este cmdlet.

## SAÍDAS

### String

Esse cmdlet retorna uma cadeia de caracteres.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[ConvertFrom-String](ConvertFrom-String.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)

[Out-String](Out-String.md)

[Select-Object](Select-Object.md)
