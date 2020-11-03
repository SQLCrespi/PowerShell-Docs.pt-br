---
external help file: Stop-DscConfiguration.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/19/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/stop-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-DscConfiguration
ms.openlocfilehash: 93c8585ae948dfa360a2ae8e2563670de8fd6e93
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193716"
---
# Stop-DscConfiguration

## SINOPSE
Interrompe um trabalho de configuração que está em execução.

## SYNTAX

### Tudo

```
Stop-DscConfiguration [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Stop-DscConfiguration` cmdlet interrompe um trabalho de configuração que está em execução. Especifique a quais computadores este cmdlet se aplica usando sessões de modelo CIM (CIM). Se não houver nenhum trabalho de configuração em execução, esse cmdlet retornará uma mensagem de aviso.

`Stop-DscConfiguration` Só está disponível como parte do [pacote cumulativo de atualizações de novembro de 2014 para Windows RT 8,1, Windows 8.1 e Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) da biblioteca suporte da Microsoft. Antes de usar este cmdlet, examine as informações em [novidades do Windows PowerShell 5,0](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)

## EXEMPLOS

### Exemplo 1: parar um trabalho de configuração

Neste exemplo, uma sessão CIM é criada usando o `New-CimSession` cmdlet. O objeto **CimSession** é usado para interromper um trabalho de configuração em execução.

```powershell
$Session = New-CimSession -ComputerName Server01 -Credential ACCOUNTS\User01
Stop-DscConfiguration -CimSession $Session
```

`New-CimSession` usa o parâmetro **ComputerName** para especificar o computador Server01. O parâmetro **Credential** especifica a conta de usuário. O objeto **CimSession** é armazenado na `$Session` variável. Quando o comando for executado, você será solicitado a fornecer a senha da conta do usuário.

`Stop-DscConfiguration` usa o parâmetro **CimSession** e o objeto armazenado em `$Session` para interromper o trabalho de configuração.

## PARAMETERS

### -AsJob

Indica que esse cmdlet executa o comando como um trabalho em segundo plano. Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) e [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).

Para usar o parâmetro **AsJob** , os computadores locais e remotos devem ser configurados para comunicação remota. No Windows Vista e versões posteriores do sistema operacional Windows, você deve abrir o PowerShell com a opção **Executar como administrador** . Para obter mais informações, consulte [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Executa o cmdlet em uma sessão remota ou em um computador remoto. Insira um nome de computador ou um objeto de sessão, como a saída de `New-CimSession` ou `Get-CimSession` .

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

### -Confirm

`Stop-DscConfiguration` Não dá suporte ao parâmetro **Confirm** . Se o parâmetro **Confirm** for usado, será exibido um erro.

Para os cmdlets do PowerShell que dão suporte à **confirmação** , usar o parâmetro solicita a verificação antes de executar um comando.

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

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.

Se esse parâmetro for omitido ou um valor de `0` for inserido, o PowerShell calculará um limite de aceleração ideal com base no número de cmdlets CIM em execução no computador. O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.

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

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

## SAÍDAS

### Nenhum

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-CimSession](../CimCmdlets/Get-CimSession.md)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[New-CimSession](../CimCmdlets/New-CimSession.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)

[Update-DscConfiguration](Update-DscConfiguration.md)

[Visão geral da Desired State Configuration do Windows PowerShell](/powershell/scripting/dsc/overview/overview)
