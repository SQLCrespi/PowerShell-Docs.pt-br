---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4d06fdd1d5a616c24a4dd7bec10ea4dadea4062
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595579"
---
# Start-Sleep

## SINOPSE
Suspende a atividade em um script ou sessão pelo período de tempo especificado.

## SYNTAX

### Segundos (padrão)

```
Start-Sleep [-Seconds] <Double> [<CommonParameters>]
```

### Milissegundos

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## DESCRIPTION

O `Start-Sleep` cmdlet suspende a atividade em um script ou sessão pelo período de tempo especificado. É possível utilizá-lo para várias tarefas, como aguardar a conclusão de uma operação ou pausar antes de repetir uma operação.

## EXEMPLOS

### Exemplo 1: suspender todos os comandos por 15 segundos

```powershell
Start-Sleep -s 15
```

### Exemplo 2: suspender todos os comandos por 1,5 segundos

Este exemplo faz com que todos os comandos na sessão sejam suspensos por um e um semestre de segundos.

```powershell
Start-Sleep -Seconds 1.5
```

## PARAMETERS

### -Milissegundos

Especifica por quanto tempo o recurso entra em suspensão, em milissegundos. O parâmetro pode ser abreviado como **m**.

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases: ms

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Segundos

Especifica por quanto tempo o recurso entra em suspensão, em segundos. Você pode omitir o nome do parâmetro ou pode abreviar como **s**. A partir do PowerShell 6.2.0, esse parâmetro agora aceita valores fracionários.

```yaml
Type: System.Double
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.Int32

Você pode canalizar o número de segundos para `Start-Sleep` .

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

- Você também pode consultar `Start-Sleep` por seu alias interno, `sleep` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- `Ctrl+C` é dividido de `Start-Sleep` .
  - `Ctrl+C` Não é interrompido de `[Threading.Thread]::Sleep` . Para obter mais informações, consulte [método Thread. Sleep](/dotnet/api/system.threading.thread.sleep).

## LINKS RELACIONADOS

