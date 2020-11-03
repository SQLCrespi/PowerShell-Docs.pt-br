---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 10/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/export-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Counter
ms.openlocfilehash: 54498eb504a1d13a5b96a2583b5e5d6e4c08735e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195528"
---
# Export-Counter

## SINOPSE
Exporta dados do contador de desempenho para arquivos de log.

## SYNTAX

```
Export-Counter [-Path] <String> [-FileFormat <String>] [-MaxSize <UInt32>]
 -InputObject <PerformanceCounterSampleSet[]> [-Force] [-Circular] [<CommonParameters>]
```

## DESCRIPTION

O `Export-Counter` cmdlet exporta dados do contador de desempenho (objetos PerformanceCounterSampleSet) para arquivos de log em log de desempenho binário (. blg), valores separados por vírgulas (. csv) ou formato de valor separado por tabulação (. tsv). Você usa este cmdlet para registrar dados do contador de desempenho.

O `Export-Counter` cmdlet é projetado para exportar dados que são retornados pelos `Get-Counter` `Import-Counter` cmdlets e.

Esse cmdlet é executado somente no Windows 7, no Windows Server 2008 R2 e em versões posteriores do Windows.

## EXEMPLOS

### EXEMPLO 1: exportar dados do contador para um arquivo

Este exemplo exporta os dados do contador para um arquivo BLG.

```powershell
Get-Counter "\Processor(*)\% Processor Time" | Export-Counter -Path $home\Counters.blg
```

O comando usa o `Get-Counter` cmdlet para coletar dados de tempo do processador. Ele usa um operador de pipeline (|) para enviar os dados para o `Export-Counter` cmdlet. O `Export-Counter` comando usa a variável **Path** para especificar o arquivo de saída.

Como o conjunto de dados pode ser muito grande, este exemplo envia os dados para `Export-Counter` por meio do pipeline. Se os dados foram salvos em uma variável, você pode usar uma quantidade desproporcional de memória.

### Exemplo 2: exportar um arquivo para um formato de arquivo de contador

Este exemplo converte um arquivo CSV em um formato de BLG de dados de contador.

O `Import-Counter` cmdlet importa dados do contador de desempenho do `Threads.csv` arquivo. O exemplo supõe que esse arquivo foi exportado anteriormente usando o `Export-Counter` cmdlet. Um operador de pipeline ( `|` ) envia os dados importados para o `Export-Counter` cmdlet. O comando usa o parâmetro **Path** para especificar o local do arquivo de saída. Ele usa os parâmetros **circular** e **MaxSize** para direcionar o `Export-Counter` cmdlet para criar um log circular que encapsula em 1 GB. O parâmetro **MaxSize** é expresso em megabytes.

```powershell
$1GBInMB = 1024 # 1GB = 1024MB
Import-Counter Threads.csv | Export-Counter -Path ThreadTest.blg -Circular -MaxSize $1GBInMB
```

### Exemplo 3: obter dados do contador de um computador remoto e salvar os dados em um arquivo

Este exemplo mostra como obter dados do contador de desempenho de um computador remoto e salva os dados em um arquivo no computador remoto.

O primeiro comando usa o `Get-Counter` cmdlet para coletar dados do contador de conjunto de trabalho do Server01, um computador remoto. O comando salva os dados na `$C` variável.

O segundo comando usa um operador de pipeline ( `|` ) para enviar os dados `$C` para o `Export-Counter` cmdlet, que o salva no `Workingset.blg` arquivo no compartilhamento de desempenho do computador Server01.

```powershell
$C = Get-Counter -ComputerName Server01 -Counter "\Process(*)\Working Set - Private" -MaxSamples $C | Export-Counter -Path \\Server01\Perf\WorkingSet.blg
```

```Output
20
```

### Exemplo 4: registrar novamente os dados existentes

Este exemplo mostra como usar os `Import-Counter` `Export-Counter` cmdlets e para registrar novamente os dados existentes.

O primeiro comando usa o `Import-Counter` cmdlet para importar dados do contador de desempenho do log espaço em disco. blg. Ele salva os dados na `$All` variável. Esse arquivo contém exemplos do \% contador "espaço livre do LogicalDisk" em mais de 200 computadores remotos na empresa.

O segundo comando usa o `Where-Object` cmdlet para selecionar objetos com **CookedValue** de menos de 15 (porcentagem). O comando salva os resultados na `$LowSpace` variável.

O terceiro comando usa um operador de pipeline ( `|` ) para enviar os dados na `$LowSpace` variável para o `Export-Counter` cmdlet. O comando usa o parâmetro **Path** para indicar que os dados selecionados devem ser registrados em log no arquivo LowDiskSpace.blg.

```powershell
$All = Import-Counter DiskSpace.blg
$LowSpace = $All | Where-Object {$_.CounterSamples.CookedValue -lt 15}
$LowSpace | Export-Counter -Path LowDiskSpace.blg
```

## PARAMETERS

### -Circular

Indica que o arquivo de saída é um log circular com o formato PEPS (primeiro a entrar, primeiro a sair).
Ao incluir esse parâmetro, o parâmetro **MaxSize** é necessário.

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

### -FileFormat

Especifica o formato de saída do arquivo de log de saída.

Os valores aceitáveis para esse parâmetro são:

- CSV
- TSV
- BLG

O valor padrão é BLG.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Sobrescreve e substitui um arquivo existente se existir um no local especificado pelo parâmetro **path** .

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

### -InputObject

Especifica, como uma matriz, os dados do contador a serem exportados. Insira uma variável que contém os dados ou um comando que obtém os dados, como o `Get-Counter` cmdlet ou `Import-Counter` .

```yaml
Type: Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MaxSize

Especifica o tamanho máximo do arquivo de saída em megabytes (MB).

Se o parâmetro **circular** for especificado, quando o arquivo de log atingir o tamanho máximo especificado, as entradas mais antigas serão excluídas à medida que mais novas forem adicionadas. Se o parâmetro **circular** não for especificado, quando o arquivo de log atingir o tamanho máximo especificado, nenhum dado novo será adicionado e o cmdlet gerará um erro de não finalização.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica o caminho e o nome do arquivo de saída. Insira um caminho relativo ou absoluto no computador local ou um caminho UNC (Convenção de nomenclatura uniforme) para um computador remoto, como `\\Computer\Share\file.blg` . Este parâmetro é necessário.

O formato de arquivo é determinado pelo valor do parâmetro **FileFormat** , não pela extensão de nome de arquivo no caminho.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Microsoft. PowerShell. Commands. getcounterer. PerformanceCounterSampleSet

Você pode canalizar dados do contador de desempenho do `Get-Counter` ou `Import-Counter` para este cmdlet.

## SAÍDAS

### Nenhum

## OBSERVAÇÕES

O gerador de arquivo de log espera que todos os objetos de entrada tenham o mesmo caminho de contador e que os objetos sejam organizados em ordem temporal crescente.

O caminho e o tipo de contador do primeiro objeto de entrada determina as propriedades registradas no arquivo de log. Se outros objetos de entrada não tiverem um valor para uma propriedade gravada, o campo de propriedade fica vazio. Se os objetos têm valores de propriedade não registrados, os valores de propriedade extra são ignorados.

O monitor de desempenho pode não ser capaz de ler todos os logs `Export-Counter` gerados. Por exemplo, o monitor de desempenho requer que todos os objetos tenham o mesmo caminho e que todos os objetos sejam separados pelo mesmo intervalo de tempo.

O `Import-Counter` cmdlet não tem um parâmetro **ComputerName** . No entanto, se o computador estiver configurado para o Windows PowerShell remoto, você poderá usar o `Invoke-Command` cmdlet para executar um `Import-Counter` comando em um computador remoto.

## LINKS RELACIONADOS

[Get-Counter](Get-Counter.md)

[Import-Counter](Import-Counter.md)
