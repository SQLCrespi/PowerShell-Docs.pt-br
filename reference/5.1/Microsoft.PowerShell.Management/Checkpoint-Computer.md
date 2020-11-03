---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/checkpoint-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Checkpoint-Computer
ms.openlocfilehash: 61f8d626cd45cfe47f0e65a3043696a01c97ca20
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194218"
---
# Checkpoint-Computer

## SINOPSE
Cria um ponto de restauração do sistema no computador local.

## SYNTAX

```
Checkpoint-Computer [-Description] <String> [[-RestorePointType] <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Checkpoint-Computer` cmdlet cria um ponto de restauração do sistema no computador local.

Os pontos de restauração do sistema e o `Checkpoint-Computer` cmdlet têm suporte apenas em sistemas operacionais cliente, como o Windows 8, o Windows 7, o Windows Vista e o Windows XP.

A partir do Windows 8, `Checkpoint-Computer` não é possível criar mais de um ponto de verificação por dia.

## EXEMPLOS

### Exemplo 1: criar um ponto de restauração do sistema

```powershell
Checkpoint-Computer -Description "Install MyApp"
```

Este comando cria um ponto de restauração do sistema chamado Install MyApp.
Ele utiliza o tipo de ponto de restauração de APPLICATION_INSTALL padrão.

### Exemplo 2: criar um ponto de restauração do sistema MODIFY_SETTINGS

```powershell
Checkpoint-Computer -Description "ChangeNetSettings" -RestorePointType MODIFY_SETTINGS
```

Este comando cria um ponto de restauração do sistema MODIFY_SETTINGS chamado "ChangeNetSettings".

## PARAMETERS

### -Description

Especifica um nome descritivo para o ponto de restauração.
Este parâmetro é necessário.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestorePointType

Especifica o tipo de ponto de restauração.
O padrão é APPLICATION_INSTALL.

Os valores aceitáveis para esse parâmetro são:

- APPLICATION_INSTALL
- APPLICATION_UNINSTALL
- DEVICE_DRIVER_INSTALL
- MODIFY_SETTINGS
- CANCELLED_OPERATION

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RPT
Accepted values: APPLICATION_INSTALL, APPLICATION_UNINSTALL, DEVICE_DRIVER_INSTALL, MODIFY_SETTINGS, CANCELLED_OPERATION

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### Nenhum

Não é possível canalizar objetos para `Checkpoint-Computer` .

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

- Esse cmdlet usa o método **CreateRestorePoint** da classe **SystemRestore** com um evento **BEGIN_SYSTEM_CHANGE** .
- A partir do Windows 8, o `Checkpoint-Computer` não pode criar mais de um ponto de restauração do sistema por dia. Se você tentar criar um novo ponto de restauração antes do período de 24 horas, o Windows PowerShell gera o seguinte erro:

  `"A new system restore point cannot be created because one has already been created within the past 24 hours.
  Please try again later."`

## LINKS RELACIONADOS

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restore-Computer](Restore-Computer.md)
