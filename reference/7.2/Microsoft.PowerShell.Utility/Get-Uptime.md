---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uptime?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Uptime
ms.openlocfilehash: 99f9372ddd1a58b0c374e915eec436cda817bb67
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103196042"
---
# Get-Uptime

## SINOPSE
Obter o **período** desde a última inicialização.

## SYNTAX

### TimeSpan (padrão)

```
Get-Uptime [<CommonParameters>]
```

### Depois

```
Get-Uptime [-Since] [<CommonParameters>]
```

## DESCRIPTION

Esse cmdlet retorna o tempo decorrido desde a última inicialização do sistema operacional.

O `Get-Uptime` cmdlet foi introduzido no PowerShell 6,0.

## EXEMPLOS

### Exemplo 1-mostrar o tempo desde a última inicialização

```powershell
Get-Uptime
```

```Output
Days              : 9
Hours             : 0
Minutes           : 9
Seconds           : 45
Milliseconds      : 0
Ticks             : 7781850000000
TotalDays         : 9.00677083333333
TotalHours        : 216.1625
TotalMinutes      : 12969.75
TotalSeconds      : 778185
TotalMilliseconds : 778185000
```

### Exemplo 2 – mostrar a hora da última inicialização

```powershell
Get-Uptime -Since
```

```Output
Tuesday, June 18, 2019 2:34:56 PM
```

## PARAMETERS

### -Desde

Faz com que o cmdlet retorne um objeto **DateTime** que representa a última vez em que o sistema operacional foi inicializado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Since
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

### Nenhum

## SAÍDAS

### System.TimeSpan

Esse é o tipo de retorno padrão quando nenhum parâmetro é usado.

### System.DateTime

Esse tipo é retornado ao usar o parâmetro **Since** .

> [!NOTE]
> Se a inicialização rápida do Windows estiver habilitada, o Windows não atualizará o valor armazenado em **LastBootUpTime**. Para desabilitar a inicialização rápida, execute o seguinte comando: `Powercfg -h off` .
>
> Para obter mais informações sobre a inicialização rápida do Windows, consulte como [diferenciar a inicialização rápida de Wake-from-Hibernation](/windows-hardware/drivers/kernel/distinguishing-fast-startup-from-wake-from-hibernation).

## OBSERVAÇÕES

No Windows, o valor retornado é o mesmo que a propriedade **LastBootUpTime** da classe **Win32_OperatingSystem** no WMI.

## LINKS RELACIONADOS

[Win32_OperatingSystem](/windows/win32/cimwin32prov/win32-operatingsystem#properties)

