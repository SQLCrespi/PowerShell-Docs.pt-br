---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restore-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-Computer
ms.openlocfilehash: 824e9a24693c7a7de01358a048a0df55be333263
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193935"
---
# Restore-Computer

## SINOPSE
Inicia uma restauração do sistema no computador local.

## SYNTAX

```
Restore-Computer [-RestorePoint] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Restore-Computer** restaura o computador local para o ponto de restauração do sistema especificado.

**Restaurar – o computador** reinicia o computador.
A restauração é concluída durante a operação de reinício.

Pontos de restauração do sistema e **Restore-Computer** têm suporte apenas em sistemas operacionais cliente, como o Windows 7, o Windows Vista e o Windows XP.

## EXEMPLOS

### Exemplo 1: restaurar o computador local

```
PS C:\> Restore-Computer -RestorePoint 253
```

Este comando restaura o computador local para o ponto de restauração que tem o número de sequência 253.

### Exemplo 2: restaurar o computador local com confirmação

```
PS C:\> Restore-Computer -RestorePoint 255 -Confirm
Confirm
Are you sure you want to perform this action?
Performing operation "Restore-Computer" .
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Este comando restaura o computador local para o ponto de restauração que tem o número de sequência 255.
Ele usa o parâmetro *Confirm* para avisar o usuário antes de realmente executar a operação.

### Exemplo 3: restaurar um computador e verificar o status

```
PS C:\> Get-ComputerRestorePoint
PS C:\> Restore-Computer -RestorePoint 255
PS C:\> Get-ComputerRestorePoint -LastStatus
```

Estes comandos executam uma restauração do sistema e verificam seu status.

O primeiro comando usa **Get-ComputerRestorePoint** para obter os pontos de restauração no computador local.

O segundo comando restaura o computador para o ponto de restauração com o número de sequência 255.

O terceiro comando usa o parâmetro *LastStatus* do cmdlet *Get-ComputerRestorePoint* para verificar o status da operação de restauração.
Como **Restore-Computer** força uma reinicialização, esse comando seria inserido após a reinicialização do computador.

## PARAMETERS

### -RestorePoint
Especifica o número de sequência do ponto de restauração.
Para localizar o número de sequência, use o cmdlet Get-ComputerRestorePoint.
Este parâmetro é necessário.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: SequenceNumber, SN, RP

Required: True
Position: 0
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
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Nenhum
Este cmdlet não gera saída.

## OBSERVAÇÕES

* Para executar um comando Restore-Computer no Windows Vista e em versões posteriores do sistema operacional Windows, abra o Windows PowerShell usando a opção Executar como administrador.
* Esse cmdlet usa Instrumentação de Gerenciamento do Windows a classe **SystemRestore** (WMI).

## LINKS RELACIONADOS

[Checkpoint-Computer](Checkpoint-Computer.md)

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)
