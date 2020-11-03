---
external help file: Get-DscConfigurationStatus.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfigurationStatus
ms.openlocfilehash: 0d59ce58a70eab68441ea1fe6097bbdf7792a54f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194157"
---
# Get-DscConfigurationStatus

## SINOPSE
Recupera dados sobre execuções de configuração concluídas.

## SYNTAX

```
Get-DscConfigurationStatus [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Get-DscConfigurationStatus** recupera informações detalhadas sobre as execuções de configuração concluídas no sistema.
Por padrão, ele retorna as informações sobre a última execução de configuração.
Esse cmdlet é útil para encontrar informações históricas sobre as execuções de configuração, como quando as configurações foram executadas, o status das execuções, o número de recursos nas configurações e quais recursos tiveram êxito ou falharam.

## EXEMPLOS

### Exemplo 1: obter informações sobre a última execução de configuração

```
PS C:\> Get-DscConfigurationStatus
```

Este comando obtém informações sobre a última execução de configuração.

### Exemplo 2: obter informações sobre todas as configurações

```
PS C:\> Get-DscConfigurationStatus -All
```

Esse comando obtém informações sobre todas as configurações que foram executadas no sistema, incluindo a verificação de consistência da DSC (configuração de estado desejado) do Windows PowerShell.

### Exemplo 3: obter informações sobre a execução da configuração em um computador remoto

```
PS C:\> Get-DscConfigurationStatus -CimSession "Server01"
```

Esse comando obtém os detalhes de execução da configuração do computador remoto chamado Server01.
Isso usa o transporte WSMan para se conectar ao computador remoto e requer que o usuário que está se conectando seja um administrador no computador remoto.

## PARAMETERS

### -All
Indica que esse cmdlet recupera informações sobre todas as execuções de configuração no computador, incluindo o aplicativo de configuração e a verificação de consistência.

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

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscLocalConfigurationManager](Get-DscLocalConfigurationManager.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
