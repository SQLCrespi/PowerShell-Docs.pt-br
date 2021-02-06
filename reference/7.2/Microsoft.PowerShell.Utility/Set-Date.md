---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-date?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Date
ms.openlocfilehash: 0f35eea0dfca76b535aad3bdb663d55c224a11d2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597594"
---
# Set-Date

## SINOPSE
Altera a hora do sistema no computador para uma hora que você especificar.

## SYNTAX

### Data (padrão)

```
Set-Date [-Date] <DateTime> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Ajustar

```
Set-Date [-Adjust] <TimeSpan> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Set-Date` cmdlet altera a data e a hora do sistema no computador para uma data e hora que você especificar.
Você pode especificar uma nova data e/ou hora digitando uma cadeia de caracteres ou passando um objeto **DateTime** ou **TimeSpan** para `Set-Date` . Para especificar uma nova data ou hora, use o parâmetro **Date** .
Para especificar um intervalo de alteração, use o parâmetro **ADJUST** .

## EXEMPLOS

### Exemplo 1: adicionar três dias à data do sistema

Este comando adiciona três dias à data do sistema atual.
Ele não afeta a hora.
O comando usa o parâmetro **Date** para especificar a data.

O `Get-Date` cmdlet retorna a data atual como um objeto **DateTime** . O método **AddDays** do objeto **DateTime** adiciona um número especificado de dias (3) ao objeto **DateTime** atual.

```powershell
Set-Date -Date (Get-Date).AddDays(3)
```

### Exemplo 2: definir o relógio do sistema de volta 10 minutos

Este exemplo define a hora atual do sistema de volta por 10 minutos.

O parâmetro **ADJUST** permite que você especifique um intervalo de alteração (menos dez minutos) no formato de hora padrão para a localidade.

O parâmetro **DisplayHint** informa ao PowerShell para exibir apenas a hora, mas não afeta o objeto **DateTime** que `Set-Date` retorna.

```powershell
Set-Date -Adjust -0:10:0 -DisplayHint Time
```

### Exemplo 3: definir a data e a hora como um valor de variável

Esses comandos alteram a data e a hora do sistema no computador local para a data e hora salvas na variável `$T` . O primeiro comando obtém a data e a armazena em `$T` .

O segundo comando usa o parâmetro **Date** para passar o objeto **DateTime** para `$T` o `Set-Date` cmdlet.

```powershell
$T = Get-Date
Set-Date -Date $T
```

### Exemplo 4: adicionar 90 minutos ao relógio do sistema

Estes comandos adiantam a hora do sistema no computador local por 90 minutos.

O primeiro comando usa o `New-TimeSpan` cmdlet para criar um objeto **TimeSpan** com um intervalo de 90 minutos e o salva na `$90mins` variável.

O segundo comando usa o parâmetro **ADJUST** de `Set-Date` para ajustar a data pelo valor do objeto **TimeSpan** na `$90mins` variável.

```powershell
$90mins = New-TimeSpan -Minutes 90
Set-Date -Adjust $90mins
```

## PARAMETERS

### -Ajustar

Especifica o valor para o qual este cmdlet adiciona ou subtrai da data e hora atuais.
pode digitar um ajuste no formato de data e hora padrão para sua localidade ou usar o parâmetro **ADJUST** para passar um objeto **TimeSpan** de `New-TimeSpan` para `Set-Date` .

```yaml
Type: System.TimeSpan
Parameter Sets: Adjust
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Data

Altera a data e hora com os valores especificados.
Você pode digitar uma nova data no formato de data abreviada e uma hora no formato de hora padrão para sua localidade. Ou, você pode passar um objeto **DateTime** de `Get-Date` .

Se você especificar uma data, mas não uma hora, `Set-Date` o alterará o tempo de meia-noite na data especificada. Se você especificar somente a hora, ele não altera a data.

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DisplayHint

Especifica quais elementos da data e hora são exibidos. Os valores aceitáveis para esse parâmetro são:

- **Data** – exibe apenas a data.
- **Hora** -exibe apenas a hora.
- **DateTime** – exibe a data e a hora.

Este parâmetro afeta somente a exibição.
Ele não afeta o objeto **DateTime** que o `Get-Date` recupera.

```yaml
Type: Microsoft.PowerShell.Commands.DisplayHintType
Parameter Sets: (All)
Aliases:
Accepted values: Date, Time, DateTime

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

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.DateTime

Você pode canalizar uma data para `Set-Date` .

## SAÍDAS

### System.DateTime

`Set-Date` Retorna um objeto que representa a data que ele definiu.

## OBSERVAÇÕES

- Use esse cmdlet com cuidado ao alterar a data e a hora do computador. A alteração pode impedir que o computador receba eventos de todo o sistema e atualizações que são disparadas por uma data ou hora. Use os parâmetros **WhatIf** e **Confirm** para evitar erros.
- Você pode usar métodos padrão do .NET com os objetos **DateTime** e **TimeSpan** usados com o `Set-Date` , como **subdias**, **AddMonths** e **FromFileTime**. Para obter mais informações, consulte [métodos DateTime](/dotnet/api/system.datetime) e

  [Métodos TimeSpan](/dotnet/api/system.timespan) no SDK do .net.

## LINKS RELACIONADOS

[Obter Data](Get-Date.md)

[New-TimeSpan](New-TimeSpan.md)
