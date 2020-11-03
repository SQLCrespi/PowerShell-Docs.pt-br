---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-psdebug?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSDebug
ms.openlocfilehash: a0b5d7e86f9d63b487bc093feb18ecc7a4496999
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194567"
---
# Set-PSDebug

## SINOPSE
Ativa/desativa os recursos de depuração de script, define o nível de rastreamento e ativa/desativa o modo estrito.

## SYNTAX

### em

```
Set-PSDebug [-Trace <Int32>] [-Step] [-Strict] [<CommonParameters>]
```

### Desligar

```
Set-PSDebug [-Off] [<CommonParameters>]
```

## DESCRIPTION

O `Set-PSDebug` cmdlet ativa e desativa os recursos de depuração de script, define o nível de rastreamento e alterna o modo estrito. Por padrão, os recursos de depuração do PowerShell estão desativados.

Quando o parâmetro **trace** tem um valor de `1` , cada linha de script é rastreada à medida que é executada. Quando o parâmetro tem um valor de `2` , atribuições de variáveis, chamadas de função e chamadas de script também são rastreadas. Se o parâmetro **Step** for especificado, você será solicitado antes que cada linha do script seja executada.

## EXEMPLOS

### Exemplo 1: definir o nível de rastreamento

Este exemplo define o nível de rastreamento como `2` e, em seguida, executa um script que exibe os números 1, 2 e
3.

```powershell
Set-PSDebug -Trace 2; foreach ($i in 1..3) {$i}
```

```Output
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in  >>>> 1..3) {$i}
DEBUG:     ! SET $foreach = 'IEnumerator'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '1'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
1
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '2'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
2
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '3'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
3
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $foreach = ''.
```

### Exemplo 2: ativar a depuração

Este exemplo ativa a depuração e, em seguida, executa um script que exibe os números 1, 2 e 3.

```powershell
Set-PSDebug -Step; foreach ($i in 1..3) {$i}
```

```Output
Continue with this operation?
   1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): A
DEBUG:    1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
1
2
3
```

### Exemplo 3: usar o modo estrito

Este exemplo coloca o PowerShell no modo estrito e tenta acessar uma variável que não tem um valor atribuído.

```powershell
Set-PSDebug -Strict; $NewVar
```

```Output
The variable '$NewVar' cannot be retrieved because it has not been set.
At line:1 char:22
+ Set-PSDebug -Strict; $NewVar
```

### Exemplo 4: desativar os recursos de depuração

Este exemplo desativa todos os recursos de depuração e, em seguida, executa um script que exibe os números 1, 2 e 3.

```powershell
Set-PSDebug -Off; foreach ($i in 1..3) {$i}
```

```Output
1
2
3
```

## PARAMETERS

### -Desativado

Desativa todos os recursos de depuração de scripts.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: off
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Etapa

Ativa a execução de script passo a passo. Antes de cada linha ser executada, o PowerShell solicita que você pare, continue ou insira um novo nível de interpretador para inspecionar o estado do script.

A especificação do parâmetro **Step** define automaticamente um nível de rastreamento de `1` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Estrito

Especifica que as variáveis devem ser atribuídas a um valor antes de serem referenciadas em um script. Se uma variável for referenciada antes de um valor ser atribuído, o PowerShell retornará um erro de exceção. Isso é equivalente a `Set-StrictMode -Version 1`. Para obter mais informações, consulte [Set-StrictMode](Set-StrictMode.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rastreamento

Especifica o nível de rastreamento para cada linha em um script. Cada linha é rastreada à medida que é executada.

Os valores aceitáveis para esse parâmetro são os seguintes:

- 0: desativar o rastreamento de script.
- 1: rastrear linhas de script conforme elas são executadas.
- 2: rastrear linhas de script, atribuições de variáveis, chamadas de função e scripts.

```yaml
Type: System.Int32
Parameter Sets: on
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

Não é possível pipeline de entrada para este cmdlet.

## SAÍDAS

### Nenhum

Esse cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[about_Debuggers](./About/about_Debuggers.md)

[Debug-Process](../Microsoft.PowerShell.Management/Debug-Process.md)

[Set-PSBreakpoint](../Microsoft.PowerShell.Utility/Set-PSBreakpoint.md)

[Set-StrictMode](Set-StrictMode.md)

[Write-Debug](../Microsoft.PowerShell.Utility/Write-Debug.md)

