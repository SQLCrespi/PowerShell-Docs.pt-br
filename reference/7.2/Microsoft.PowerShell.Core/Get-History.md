---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-History
ms.openlocfilehash: be47925211c57760ddbd0bd4c8e985e161d24593
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597391"
---
# Get-History

## SINOPSE
Obtém uma lista dos comandos inseridos durante a sessão atual.

## SYNTAX

```
Get-History [[-Id] <Int64[]>] [[-Count] <Int32>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-History` cmdlet obtém o histórico de sessão, ou seja, a lista de comandos inseridos durante a sessão atual.

O PowerShell mantém automaticamente um histórico de cada sessão. O número de entradas no histórico de sessão é determinado pelo valor da variável de `$MaximumHistoryCount` preferência. A partir do Windows PowerShell 3,0, o valor padrão é `4096` . Por padrão, os arquivos de histórico são salvos na pasta raiz, mas você pode salvá-lo em qualquer local. Para obter mais informações sobre os recursos de histórico no PowerShell, consulte [about_History](About/about_History.md).

O histórico de sessão é gerenciado separadamente do histórico mantido pelo módulo **PSReadLine** .
Ambos os históricos estão disponíveis em sessões em que **PSReadLine** é carregado. Esse cmdlet funciona apenas com o histórico de sessão. Para obter mais informações, consulte [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

## EXEMPLOS

### Exemplo 1: obter o histórico de sessão

Este exemplo obtém as entradas no histórico de sessão. A exibição padrão mostra cada comando e sua ID, que indica a ordem em que eles foram executados.

```powershell
Get-History
```

### Exemplo 2: obter entradas que incluem uma cadeia de caracteres

Este exemplo obtém entradas no histórico de comandos que incluem o serviço de cadeia de caracteres. O primeiro comando obtém todas as entradas no histórico da sessão. O operador de pipeline ( `|` ) passa os resultados para o `Where-Object` cmdlet, que seleciona apenas os comandos que incluem o serviço.

```powershell
Get-History | Where-Object {$_.CommandLine -like "*Service*"}
```

### Exemplo 3: exportar entradas de histórico até uma ID específica

Este exemplo obtém as cinco entradas de histórico mais recentes que terminam com a entrada 7. O operador de pipeline passa o resultado para o `Export-Csv` cmdlet, que formata o histórico como texto separado por vírgula e o salva no arquivo de History.csv. O arquivo inclui os dados que são exibidos quando você formata o histórico como uma lista. Isso inclui as horas de status e de início e de término do comando.

```powershell
Get-History -ID 7 -Count 5 | Export-Csv History.csv
```

### Exemplo 4: exibir o comando mais recente

Este exemplo obtém o último comando no histórico de comandos. O último comando é o comando inserido mais recentemente. Esse comando usa o parâmetro **Count** para exibir apenas um comando. Por padrão, `Get-History` o Obtém os comandos mais recentes. Este comando pode ser abreviado como "h - c 1" e é equivalente a pressionar a tecla de seta para cima.

```powershell
Get-History -Count 1
```

### Exemplo 5: exibir todas as propriedades das entradas no histórico

Este exemplo exibe todas as propriedades de entradas no histórico de sessão. O operador de pipeline passa os resultados de um `Get-History` comando para o `Format-List` cmdlet, que exibe todas as propriedades de cada entrada de histórico. Isso inclui a ID, o status e os horários de início e término do comando.

```powershell
Get-History | Format-List -Property *
```

## PARAMETERS

### -Contagem

Especifica o número das entradas de histórico mais recentes que esse cmdlet obtém. Por padrão, o `Get-History` obtém todas as entradas no histórico da sessão. Se você usar ambos os parâmetros **Count** e **Id** em um comando, a exibição é encerrada com o comando especificado pelo parâmetro **Id**.

No Windows PowerShell 2,0, por padrão, `Get-History` o Obtém as 32 entradas mais recentes.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Especifica uma matriz de IDs de entradas no histórico de sessão. `Get-History` Obtém apenas as entradas especificadas. Se você usar os parâmetros **ID** e **Count** em um comando, `Get-History` o obterá as entradas mais recentes terminando com a entrada especificada pelo parâmetro **ID** .

```yaml
Type: System.Int64[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.Int64

É possível canalizar uma ID de histórico para esse cmdlet.

## SAÍDAS

### Microsoft. PowerShell. Commands. HistoryInfo

Esse cmdlet retorna um objeto de histórico para cada item de histórico que ele obtém.

## OBSERVAÇÕES

O histórico da sessão é uma lista dos comandos inseridos durante a sessão. O histórico da sessão representa a ordem de execução, o status e os horários de início e término do comando. À medida que você insere cada comando, o PowerShell o adiciona ao histórico para que você possa reutilizá-lo. Para obter mais informações sobre o histórico de comandos, consulte [about_History](About/about_History.md).

A partir do Windows PowerShell 3,0, o valor padrão da `$MaximumHistoryCount` variável de preferência é `4096` . No Windows PowerShell 2,0, o valor padrão é `64` . Para obter mais informações sobre a `$MaximumHistoryCount` variável, consulte [about_Preference_Variables](About/about_Preference_Variables.md).

## LINKS RELACIONADOS

[Add-History](Add-History.md)

[Clear-History](Clear-History.md)

[Invoke-History](Invoke-History.md)

[about_History](About/about_History.md)
