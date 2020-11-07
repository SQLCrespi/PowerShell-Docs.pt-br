---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: 4131232e7afb2e0a213bbe11f5da7ee3a0071a59
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344296"
---
# Clear-RecycleBin

## SINOPSE
Limpa o conteúdo de uma lixeira.

## SYNTAX

### Tudo

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Clear-RecycleBin` cmdlet exclui o conteúdo da lixeira de um computador. Essa ação é como usar a **Lixeira vazia** do Windows.

Esse cmdlet foi adicionado novamente no PowerShell 7.

## EXEMPLOS

### 1: limpar todas as lixeiras

Neste exemplo, todas as lixeiras do computador local são limpas.

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

`Clear-RecycleBin` solicita ao usuário a confirmação para limpar todas as lixeiras no computador local.

### 2: limpar uma lixeira especificada

Este exemplo limpa a lixeira para uma letra de unidade especificada.

```powershell
Clear-RecycleBin -DriveLetter C
```

`Clear-RecycleBin` usa o parâmetro **DriveLetter** para especificar a lixeira no volume **C** . O usuário receberá uma solicitação de confirmação para executar o comando.

### 3: limpar todas as lixeiras sem confirmação

Este exemplo não solicita confirmação para limpar os compartimentos da lixeira do computador local.

```powershell
Clear-RecycleBin -Force
```

`Clear-RecycleBin` usa o parâmetro **Force** e não solicita ao usuário a confirmação para limpar todas as lixeiras no computador local.

Uma alternativa é substituir `-Force` por `-Confirm:$false` .

## PARAMETERS

### -DriveLetter

Especifica a lixeira a ser desmarcada para uma única letra de unidade ou uma matriz de letras de unidade.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Especifica que o usuário não é solicitado a confirmar para limpar uma lixeira.

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

### -Confirm

Solicita a confirmação do usuário antes de executar o cmdlet. O usuário será solicitado a confirmar, mesmo que o parâmetro **Confirm** não seja especificado.

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

Mostra o que aconteceria se `Clear-RecycleBin` for executado. O cmdlet não é executado.

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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

### Nenhum

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

## LINKS RELACIONADOS
