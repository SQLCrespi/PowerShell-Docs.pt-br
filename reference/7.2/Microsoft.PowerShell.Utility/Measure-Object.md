---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object
ms.openlocfilehash: 594837b2f85f4d5d5d4125d3f7c63ad2c8a16153
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598645"
---
# Measure-Object

## SINOPSE
Calcula as propriedades numéricas de objetos e os caracteres, palavras e linhas em objetos de cadeia de caracteres, como arquivos de texto.

## SYNTAX

### GenericMeasure (padrão)

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-StandardDeviation]
 [-Sum] [-AllStats] [-Average] [-Maximum] [-Minimum] [<CommonParameters>]
```

### Textmeasure

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-Line] [-Word]
 [-Character] [-IgnoreWhiteSpace] [<CommonParameters>]
```

## DESCRIPTION

O `Measure-Object` cmdlet calcula os valores de propriedade de determinados tipos de objeto.
`Measure-Object` executa três tipos de medidas, dependendo dos parâmetros no comando.

O `Measure-Object` cmdlet executa cálculos nos valores de propriedade de objetos. Você pode usar `Measure-Object` para contar objetos ou contar objetos com uma **Propriedade** especificada. Você também pode usar `Measure-Object` para calcular o **mínimo**, **máximo**, **soma**, **i** e **média** de valores numéricos. Para objetos de **cadeia de caracteres** , você também pode usar `Measure-Object` para contar o número de linhas, palavras e caracteres.

## EXEMPLOS

### Exemplo 1: contar os arquivos e as pastas em um diretório

Esse comando conta os arquivos e pastas no diretório atual.

```powershell
Get-ChildItem | Measure-Object
```

### Exemplo 2: medir os arquivos em um diretório

Esse comando exibe o **mínimo**, o **máximo** e a **soma** dos tamanhos de todos os arquivos no diretório atual e o tamanho médio de um arquivo no diretório.

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### Exemplo 3: medir o texto em um arquivo de texto

Este comando exibe o número de caracteres, palavras e linhas no arquivo Text.txt.
Sem o parâmetro **RAW** , `Get-Content` o gera o arquivo como uma matriz de linhas.

O primeiro comando usa `Set-Content` para adicionar um texto padrão a um arquivo.

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### Exemplo 4: objetos de medida que contêm uma propriedade especificada

Este exemplo conta o número de objetos que têm uma propriedade **DisplayName** . Os dois primeiros comandos recuperam todos os serviços e processos no computador local. O terceiro comando conta o número combinado de serviços e processos. O último comando combina as duas coleções e canaliza o resultado para `Measure-Object` .

O objeto **System. Diagnostics. Process** não tem uma propriedade **DisplayName** e é deixado da contagem final.

```powershell
$services = Get-Service
$processes = Get-Process
$services + $processes | Measure-Object
$services + $processes | Measure-Object -Property DisplayName
```

```Output
Count    : 682
Average  :
Sum      :
Maximum  :
Minimum  :
Property :

Count    : 290
Average  :
Sum      :
Maximum  :
Minimum  :
Property : DisplayName
```

### Exemplo 5: medir o conteúdo de um arquivo CSV

Este comando calcula os médio anos de serviço dos funcionários de uma empresa.

O `ServiceYrs.csv` arquivo é um arquivo CSV que contém o número do funcionário e os anos de serviço de cada funcionário. A primeira linha da tabela é uma linha de cabeçalho de **empno**, **anos**.

Quando você usa `Import-Csv` o para importar o arquivo, o resultado é um **PSCustomObject** com as propriedades de observação de **empno** e **anos**.
Você pode usar `Measure-Object` para calcular os valores dessas propriedades, assim como qualquer outra propriedade de um objeto.

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### Exemplo 6: medir valores Boolianos

Este exemplo demonstra como o `Measure-Object` pode medir valores Boolianos.
Nesse caso, ele usa a propriedade  **booliana** PsIsContainer para medir a incidência de pastas (vs. Files) no diretório atual.

```powershell
Get-ChildItem | Measure-Object -Property psiscontainer -Maximum -Sum -Minimum -Average
```

```Output
Count             : 126
Average           : 0.0634920634920635
Sum               : 8
Maximum           : 1
Minimum           : 0
StandardDeviation :
Property          : PSIsContainer
```

### Exemplo 7: cadeias de caracteres de medida

O exemplo a seguir mede o número de linhas, primeiro uma única cadeia de caracteres e, em seguida, em várias cadeias. O caractere de nova linha <code>`n</code> separa cadeias de caracteres em várias linhas.

```powershell
# The newline character `n separates the string into separate lines, as shown in the output.
"One`nTwo`nThree"
"One`nTwo`nThree" | Measure-Object -Line
```

```Output
One
Two
Three


Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The first string counts as a single line.
# The second string is separated into two lines by the newline character.
"One", "Two`nThree" | Measure-Object -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The Word switch counts the number of words in each InputObject
# Each InputObject is treated as a single line.
"One, Two", "Three", "Four Five" | Measure-Object -Word -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3     5
```

### Exemplo 8: medir todos os valores

A partir do PowerShell 6, o parâmetro **Perstats** de `Measure-Object` permite que você meça todas as estatísticas juntas.

```powershell
1..5 | Measure-Object -AllStats
```

```output
Count             : 5
Average           : 3
Sum               : 15
Maximum           : 5
Minimum           : 1
StandardDeviation : 1.58113883008419
Property          :
```

### Exemplo 9: medida usando Propriedades scriptblock

A partir do PowerShell 6, `Measure-Object` dá suporte a propriedades **scriptblock** . O exemplo a seguir demonstra como usar uma propriedade **scriptblock** para determinar o tamanho, em megabytes, de todos os arquivos em um diretório.

```powershell
Get-ChildItem | Measure-Object -Sum {$_.Length/1MB}
```

### Exemplo 10: medir as Hashtables

A partir do PowerShell 6, o `Measure-Object` dá suporte à medição de entrada de **Hashtable** . O exemplo a seguir determina o maior valor para a `num` chave de 3 objetos de **tabela de hash** .

```powershell
@{num=3}, @{num=4}, @{num=5} | Measure-Object -Maximum Num
```

```output
Count             : 3
Average           :
Sum               :
Maximum           : 5
Minimum           :
StandardDeviation :
Property          : num
```

### Exemplo 11: medir o desvio padrão

A partir do PowerShell 6, `Measure-Object` o oferece suporte ao `-StandardDeviation` parâmetro. O exemplo a seguir determina o *desvio padrão* para a CPU usada por todos os processos. Um grande desvio indicaria um pequeno número de processos consumindo a maioria da CPU.

```powershell
Get-Process | Measure-Object -Average -StandardDeviation CPU
```

```output
Count             : 303
Average           : 163.032384488449
Sum               :
Maximum           :
Minimum           :
StandardDeviation : 859.444048419069
Property          : CPU
```

### Exemplo 12: medida usando curingas

A partir do PowerShell 6, o `Measure-Object` dá suporte à medição de objetos usando curingas em nomes de propriedade. O exemplo a seguir determina o máximo de qualquer tipo de uso de memória paginado entre um conjunto de processos.

```powershell
Get-Process | Measure-Object -Maximum *paged*memory*size
```

```output
Count             : 303
Average           :
Sum               :
Maximum           : 735784
Minimum           :
StandardDeviation :
Property          : NonpagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 352104448
Minimum           :
StandardDeviation :
Property          : PagedMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 2201968
Minimum           :
StandardDeviation :
Property          : PagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 719032320
Minimum           :
StandardDeviation :
Property          : PeakPagedMemorySize
```

## PARAMETERS

### -Média

Indica que o cmdlet exibe o valor médio das propriedades especificadas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Caractere

Indica que o cmdlet conta o número de caracteres nos objetos de entrada.

> [!NOTE]
> As opções de **palavra**, **Char** e **linha** contam *dentro* de cada objeto de entrada, bem como *entre* objetos de entrada. Consulte o exemplo 7.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreWhiteSpace

Indica que o cmdlet ignora o espaço em branco em contagens de caracteres.
Por padrão, o espaço em branco não é ignorado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica os objetos a serem medidos.
Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

Quando você usa o parâmetro **InputObject** com `Measure-Object` , em vez de direcionar os resultados de comando para `Measure-Object` , o valor **InputObject** é tratado como um único objeto.

É recomendável que você use `Measure-Object` no pipeline se desejar medir uma coleção de objetos com base em se os objetos têm valores específicos nas propriedades definidas.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Linha

Indica que o cmdlet conta o número de linhas nos objetos de entrada.

> [!NOTE]
> As opções de **palavra**, **Char** e **linha** contam *dentro* de cada objeto de entrada, bem como *entre* objetos de entrada. Consulte o exemplo 7.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Máximo

Indica que o cmdlet exibe o valor máximo das propriedades especificadas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mínimo

Indica que o cmdlet exibe o valor mínimo das propriedades especificadas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Propriedade

Especifica uma ou mais propriedades a serem medidas. Se você não especificar nenhuma outra medida, `Measure-Object` o contará os objetos que têm as propriedades especificadas.

O valor do parâmetro **Property** pode ser uma nova propriedade calculada. A propriedade calculada deve ser um bloco de script. Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -I

Indica que o cmdlet exibe o desvio padrão dos valores das propriedades especificadas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sum

Indica que o cmdlet exibe a soma dos valores das propriedades especificadas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Estatísticas

Indica que o cmdlet exibe todas as estatísticas das propriedades especificadas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Palavra

Indica que o cmdlet conta o número de palavras nos objetos de entrada.

> [!NOTE]
> As opções de **palavra**, **Char** e **linha** contam *dentro* de cada objeto de entrada, bem como *entre* objetos de entrada. Consulte o exemplo 7.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

Você pode canalizar objetos para `Measure-Object` .

## SAÍDAS

### Microsoft. PowerShell. Commands. GenericMeasureInfo

### Microsoft. PowerShell. Commands. TextMeasureInfo

Se você usar o parâmetro **Word** , `Measure-Object` retornará um objeto **TextMeasureInfo** .
Caso contrário, ele retorna um objeto **GenericMeasureInfo** .

## OBSERVAÇÕES

## LINKS RELACIONADOS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
