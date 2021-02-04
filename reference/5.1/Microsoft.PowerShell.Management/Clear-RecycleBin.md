---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/29/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: f59cc9ff4e6d1b6579292c84f440bbbdd156b65c
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99098556"
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

Especifica que o usuário não é solicitado a confirmar para limpar uma lixeira. O parâmetro **Force** também substitui os parâmetros **WhatIf** e **Confirm** .

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

## LINKS RELACIONADOS
