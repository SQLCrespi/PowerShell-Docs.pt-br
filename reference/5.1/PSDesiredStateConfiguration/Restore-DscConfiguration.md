---
external help file: Restore-DSCConfiguration.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/restore-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-DscConfiguration
ms.openlocfilehash: 823032f7665d9ec83faa59c37560510e049efdd2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194140"
---
# Restore-DscConfiguration

## SINOPSE
Reaplica a configuração anterior para o nó.

## SYNTAX

```
Restore-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Restore-DscConfiguration** reaplica a configuração anterior para o nó, se existir uma configuração anterior.
Especifique computadores usando sessões CIM (Common Information Model).
Se você não especificar um computador de destino, o cmdlet restaurará a configuração do computador local.
Se não houver nenhuma configuração anterior para um nó específico, esse cmdlet retornará uma mensagem de erro.

Este cmdlet não oferece suporte ao parâmetro **Confirm** .

## EXEMPLOS

### Exemplo 1: restaurar a configuração do computador local

```
PS C:\> Restore-DscConfiguration
```

Este comando restaura a configuração do computador local.

### Exemplo 2: restaurar a configuração para um computador especificado

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Restore-DscConfiguration -CimSession $Session
```

Este exemplo restaura a configuração em um computador especificado por uma sessão CIM.
O exemplo cria uma sessão CIM para um computador denominado Server01 para uso com o cmdlet.
Como alternativa, crie uma matriz de sessões CIM para aplicar o cmdlet a vários computadores especificados.

O primeiro comando cria uma sessão CIM usando o cmdlet **New-CimSession** e, em seguida, armazena o objeto **CimSession** na variável $Session.
O comando solicita uma senha.
Para obter mais informações, digite `Get-Help New-CimSession`.

O segundo comando restaura a configuração atual dos computadores identificados pelos objetos **CimSession** armazenados na variável $Session, nesse caso, o computador chamado Server01.

## PARAMETERS

### -AsJob
Indica que esse cmdlet executa o comando como um trabalho em segundo plano.

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

### -CimSession
Executa o cmdlet em uma sessão remota ou em um computador remoto.
Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet **New-CimSession** ou **Get-CimSession** .

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

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
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Visão geral da Desired State Configuration do Windows PowerShell](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
