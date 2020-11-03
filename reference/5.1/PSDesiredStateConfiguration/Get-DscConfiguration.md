---
external help file: Get-DSCConfiguration.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfiguration
ms.openlocfilehash: 42b24e72de4c4bcc9326d52861c08a05853b18e0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194155"
---
# Get-DscConfiguration

## SINOPSE
Obtém a configuração atual dos nós.

## SYNTAX

```
Get-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Get-DscConfiguration** Obtém a configuração atual dos nós, se a configuração existir.
Especifique computadores usando sessões CIM (Common Information Model).
Se você não especificar um computador de destino, o cmdlet obtém a configuração do computador local.

## EXEMPLOS

### Exemplo 1: obter a configuração para o computador local

```
PS C:\> Get-DscConfiguration
```

Esse comando obtém o estado atual do computador local.

### Exemplo 2: obter a configuração para um computador especificado

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Get-DscConfiguration -CimSession $Session
```

Este exemplo obtém o estado atual de um computador especificado por uma sessão CIM.
O exemplo cria uma sessão CIM para um computador denominado Server01 para uso com o cmdlet.
Como alternativa, crie uma matriz de sessões CIM para aplicar o cmdlet a vários computadores especificados.

O primeiro comando cria uma sessão CIM usando o cmdlet **New-CimSession** e, em seguida, armazena o objeto **CimSession** na variável **$Session** .
O comando solicita uma senha.
Para obter mais informações, digite `Get-Help New-CimSession`.

O segundo comando obtém a configuração atual dos computadores identificados pelos objetos **CimSession** armazenados na variável **$Session** , nesse caso, o computador chamado Server01.

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
Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) ou [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .
O padrão é a sessão atual do computador local.

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
Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador.
O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.

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

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Visão geral da Desired State Configuration do Windows PowerShell](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
