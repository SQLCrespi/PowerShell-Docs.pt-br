---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 644663c8871233bae84288f83492b518405d14ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193575"
---
# Get-Random

## SINOPSE
Obtém um número aleatório ou seleciona objetos aleatoriamente de uma coleção.

## SYNTAX

### RandomNumberParameterSet (padrão)

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [-Count <Int32>] [<CommonParameters>]
```

### RandomListItemParameterSet

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

### ShuffleParameterSet

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Shuffle] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Random` cmdlet obtém um número selecionado aleatoriamente. Se você enviar uma coleção de objetos ao `Get-Random` , ele obterá um ou mais objetos selecionados aleatoriamente da coleção.

Sem parâmetros ou entrada, um `Get-Random` comando retorna um inteiro não assinado de 32 bits selecionado aleatoriamente entre 0 (zero) e **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ).

Você pode usar os parâmetros de `Get-Random` para especificar um número de semente, os valores mínimo e máximo, o número de objetos retornados de uma coleção enviada e a coleção inteira em uma ordem aleatória.

## EXEMPLOS

### Exemplo 1: obter um inteiro aleatório

Esse comando obtém um inteiro aleatório entre 0 (zero) e **Int32. MaxValue** .

```powershell
Get-Random
```

```Output
3951433
```

### Exemplo 2: obter um inteiro aleatório entre 0 e 99

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### Exemplo 3: obter um inteiro aleatório entre-100 e 99

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### Exemplo 4: obter um número de ponto flutuante aleatório

Esse comando obtém um número de ponto flutuante aleatório maior ou igual a 10.7 e menor que 20.92.

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### Exemplo 5: obter um inteiro aleatório de uma matriz

Esse comando obtém um número selecionado aleatoriamente da matriz especificada.

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### Exemplo 6: obter vários inteiros aleatórios de uma matriz

Esse comando obtém três números selecionados aleatoriamente em ordem aleatória de uma matriz.

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### Exemplo 7: tornar aleatório uma coleção inteira

A partir do PowerShell 7,1, você pode usar o parâmetro de **ordem aleatória** para retornar a coleção inteira em uma ordem aleatória.

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Shuffle
```

```Output
2
3
5
1
8
13
```

### Exemplo 8: obter um valor não numérico aleatório

Esse comando retorna um valor aleatório de uma coleção não numérica.

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### Exemplo 9: usar o parâmetro setsemente

Este exemplo mostra o efeito do uso do parâmetro **SetSeed** .

Como **setsemente** produz comportamento não aleatório, ele é normalmente usado apenas para reproduzir resultados, como ao depurar ou analisar um script.

```powershell
# Commands with the default seed are pseudorandom
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

```powershell
# Commands with the same seed are not random
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
```

```Output
74
74
74
```

```powershell
# SetSeed results in a repeatable series
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

### Exemplo 10: obter arquivos aleatórios

Esses comandos obtêm um exemplo selecionado aleatoriamente de 50 arquivos da `C:` unidade do computador local.

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### Exemplo 11: roll Fair

Este exemplo acumula um dado justo 1200 vezes e conta os resultados. O primeiro comando, `For-EachObject` repete a chamada para `Get-Random` do piped em números (1-6). Os resultados são agrupados por seu valor com `Group-Object` e formatados como uma tabela com `Select-Object` .

```powershell
1..1200 | ForEach-Object {
    1..6 | Get-Random
} | Group-Object | Select-Object Name,Count
```

```Output
Name Count
---- -----
1      206
2      199
3      196
4      226
5      185
6      188
```

### Exemplo 12: usar o parâmetro de contagem

Agora você pode usar o parâmetro **Count** sem objetos de tubulação para `Get-Random` .
O exemplo a seguir obtém três números aleatórios menores que 10.

```powershell
Get-Random -Count 3 -Maximum 10
```

```Output
9
0
8
```

### Exemplo 13: usar o parâmetro InputObject com uma cadeia de caracteres vazia ou $null

Neste exemplo, o parâmetro **InputObject** especifica uma matriz que contém uma cadeia de caracteres vazia ( `''` ) e `$null` .

```powershell
Get-Random -InputObject @('a','',$null)
```

`Get-Random` retornará uma `a` cadeia de caracteres vazia ou `$null` . O Stinger vazio é exibido como uma linha em branco e `$null` retorna a um prompt do PowerShell.

## PARAMETERS

### -Contagem

Especifica o número de objetos aleatórios ou números a serem retornados. O padrão é 1.

Quando usado com `InputObject` , se o valor de **Count** excede o número de objetos na coleção, `Get-Random` retorna todos os objetos em ordem aleatória.

```yaml
Type: System.Int32
Parameter Sets: RandomNumberParameterSet, RandomListItemParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica uma coleção de objetos. `Get-Random` Obtém objetos aleatoriamente selecionados em ordem aleatória da coleção até o número especificado por **contagem** . Insira os objetos, uma variável que contenha os objetos ou um comando ou expressão que os obtenha. Também é possível canalizar uma coleção de objetos para o `Get-Random` .

A partir do PowerShell 7, o parâmetro **InputObject** aceita matrizes que podem conter uma cadeia de caracteres vazia ou `$null` . A matriz pode ser enviada ao pipeline ou como um valor de parâmetro **InputObject** .

```yaml
Type: System.Object[]
Parameter Sets: RandomListItemParameterSet, ShuffleParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Máximo

Especifica um valor máximo para o número aleatório. `Get-Random` Retorna um valor menor que o máximo (não igual). Insira um inteiro, um número de ponto flutuante de precisão dupla ou um objeto que possa ser convertido em um número inteiro ou duplo, como uma cadeia de caracteres numérica ("100").

O valor de **Maximum** deve ser maior que (diferente de) o valor de **Minimum** . Se o valor **máximo** ou **mínimo** for um número de ponto flutuante, o `Get-Random` retornará um número de ponto flutuante selecionado aleatoriamente.

Em um computador de 64 bits, se o valor **mínimo** for um inteiro de 32 bits, o valor padrão de **máximo** será **Int32. MaxValue** .

Se o valor **mínimo** for um Double (um número de ponto flutuante), o valor padrão de **Maximum** será **Double. MaxValue** . Caso contrário, o valor padrão é **Int32. MaxValue** .

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mínimo

Especifica um valor mínimo para o número aleatório. Insira um inteiro, um número de ponto flutuante de precisão dupla ou um objeto que possa ser convertido em um número inteiro ou duplo, como uma cadeia de caracteres numérica ("100"). O valor padrão é 0 (zero).

O valor de **Minimum** deve ser menor que (diferente de) o valor de **Maximum** . Se o valor **máximo** ou **mínimo** for um número de ponto flutuante, o `Get-Random` retornará um número de ponto flutuante selecionado aleatoriamente.

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Setsemente

Especifica um valor de semente para o número aleatório. Esse valor de semente é usado para o comando atual e para todos os comandos subsequentes `Get-Random` na sessão atual até que você use **setsemente** novamente ou feche a sessão. Não é possível redefinir a semente para seu valor padrão.

O parâmetro **setsemente** não é necessário. Por padrão, `Get-Random` o usa o método [RandomNumberGenerator ()](/dotnet/api/system.security.cryptography.randomnumbergenerator) para gerar um valor de semente. Como o **setsemente** resulta em comportamento não aleatório, ele é normalmente usado apenas ao tentar reproduzir o comportamento, como ao depurar ou analisar um script que inclui `Get-Random` comandos.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ordem aleatória

Retorna a coleção inteira em uma ordem aleatória.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ShuffleParameterSet
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

### System.Object

É possível canalizar um ou mais objetos. `Get-Random` seleciona valores aleatoriamente dos objetos canalizados.

## SAÍDAS

### System. Int32, System. Int64, sistema. Double

`Get-Random` Retorna um número inteiro ou de ponto flutuante ou um objeto selecionado aleatoriamente de uma coleção enviada.

## OBSERVAÇÕES

`Get-Random` define uma semente padrão para cada sessão com base no relógio de tempo do sistema quando a sessão é iniciada.

`Get-Random` Nem sempre retorna o mesmo tipo de dados que o valor de entrada. A tabela a seguir mostra o tipo de saída para cada um dos tipos de entrada numéricos.

| Tipo de entrada | Tipo de saída |
| :--------: | :---------: |
|   SByte    |   Duplo    |
|    Byte    |   Duplo    |
|   Int16    |   Duplo    |
|   UInt16   |   Duplo    |
|   Int32    |    Int32    |
|   UInt32   |   Double    |
|   Int64    |    Int64    |
|   UInt64   |   Double    |
|   Double   |   Double    |
|   Simples   |   Duplo    |

A partir do Windows PowerShell 3,0, `Get-Random` dá suporte a inteiros de 64 bits. No Windows PowerShell 2,0, todos os valores são convertidos em **System. Int32** .

A partir do PowerShell 7, o parâmetro **InputObject** no conjunto de parâmetros **RandomListItemParameterSet** aceita matrizes que contêm uma cadeia de caracteres vazia ou `$null` . Nas versões anteriores do PowerShell, apenas o parâmetro **máximo** no conjunto de parâmetros **RandomNumberParameterSet** aceitou uma cadeia de caracteres vazia ou `$null` .

## LINKS RELACIONADOS

