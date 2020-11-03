---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Computer
ms.openlocfilehash: 89e43220a8d5ac675ea232db09cf3edec2ca2b97
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193956"
---
# Remove-Computer

## SINOPSE
Remove o computador local do seu domínio.

## SYNTAX

### Local (padrão)

```
Remove-Computer [[-UnjoinDomainCredential] <PSCredential>] [-Restart] [-Force] [-PassThru]
 [-WorkgroupName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Remoto

```
Remove-Computer -UnjoinDomainCredential <PSCredential> [-LocalCredential <PSCredential>] [-Restart]
 [-ComputerName <String[]>] [-Force] [-PassThru] [-WorkgroupName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `Remove-Computer` cmdlet Remove o computador local e os computadores remotos de seus domínios atuais.

Quando você remove um computador de um domínio, `Remove-Computer` o também desabilita a conta de domínio do computador. Você deve fornecer credenciais explícitas para desassociar o computador de seu domínio, mesmo quando eles são as credenciais do usuário atual. Você deve reiniciar o computador para que a alteração entre em vigor. Além disso, quando um computador é removido de um domínio, você deverá movê-lo para um grupo de trabalho. Utilize o parâmetro **WorkgroupName** para especificar o grupo de trabalho.

Para mover um computador de um grupo de trabalho para um domínio, de um grupo de trabalho para outro, ou de um domínio para outro, use o `Add-Computer` cmdlet.

Para obter os resultados do comando, utilize os parâmetros **Verbose** e **PassThru** . Para suprimir o prompt do usuário, utilize o parâmetro **Force** .

`Remove-Computer` Remove o computador local e os computadores remotos dos domínios. Ele inclui parâmetros de credenciais que especificam credenciais alternativas para se conectar a computadores remotos e ao sair de um domínio, um parâmetro **Restart** para reiniciar os computadores afetados e um parâmetro **WorkgroupName** para especificar o nome do grupo de trabalho ao qual os computadores são adicionados.

## EXEMPLOS

### Exemplo 1: remover o computador local de seu domínio

Este exemplo remove o computador local do domínio ao qual ele está associado.

```powershell
Remove-Computer -UnjoinDomaincredential Domain01\Admin01 -PassThru -Verbose -Restart
```

O parâmetro **UnjoinDomainCredential** fornece as credenciais de um administrador de domínio. O **PassThru** e os parâmetros comuns **detalhados** exibem informações sobre o êxito ou a falha do comando. O parâmetro de **reinicialização** reinicia o computador para concluir a operação de remoção.

Quando nenhum nome de grupo de trabalho é especificado, o computador é movido para o grupo de trabalho nomeado depois de ser removido de seu domínio.

### Exemplo 2: mover vários computadores para um grupo de trabalho herdado

Este exemplo remove todos os computadores listados no `OldServers.txt` arquivo de seus domínios e os move para o grupo de trabalho **herdado** .

```powershell
Remove-Computer -ComputerName (Get-Content OldServers.txt) -LocalCredential Domain01\Admin01 -UnJoinDomainCredential Domain01\Admin01 -WorkgroupName "Legacy" -Force -Restart
```

O parâmetro **LocalCredential** fornece as credenciais de um usuário que tem permissão para se conectar a computadores remotos. O parâmetro **UnjoinDomainCredential** fornece as credenciais de um usuário que tem permissão para remover os computadores de seus domínios. O parâmetro **Force** suprime os prompts de confirmação para cada computador. O parâmetro de **reinicialização** reinicia cada um dos computadores depois que ele é removido de seu domínio.

### Exemplo 3: remover computadores de um grupo de trabalho sem confirmação

Este exemplo remove o computador remoto, o Server01 e o computador local de seus domínios e os adiciona ao grupo de trabalho **local** .

```powershell
Remove-Computer -ComputerName "Server01", "localhost" -UnjoinDomainCredential Domain01\Admin01 -WorkgroupName "Local" -Restart -Force
```

O parâmetro **Force** suprime o prompt de confirmação para cada computador. O parâmetro de **reinicialização** reinicia os computadores para que a alteração entre em vigor.

## PARAMETERS

### -ComputerName

Especifica os computadores a serem removidos de seus domínios. O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP ou um FQDN (nome de domínio totalmente qualificado) dos computadores remotos. Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.

Esse parâmetro não depende da comunicação remota do PowerShell. Você pode usar o parâmetro **ComputerName** de `Remove-Computer` mesmo que o computador não esteja configurado para executar comandos remotos.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.String[]
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force

Suprime o aviso ao usuário. Por padrão, o `Remove-Computer` solicita a confirmação antes de remover cada computador.

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

### -LocalCredential

Especifica uma conta de usuário que tem permissão para se conectar aos computadores que o parâmetro **ComputerName** especifica. O padrão é o usuário atual.

Digite um nome de usuário, como `User01` ou `Domain01\User01` , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, o cmdlet solicitará uma senha. Para especificar uma conta de usuário que tenha permissão para remover o computador do seu domínio atual, utilize o parâmetro **UnjoinDomainCredential** .

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Retorna os resultados do comando. Caso contrário, este cmdlet não gera nenhuma saída.

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

### -Restart

Indica que esse cmdlet reinicia os computadores que estão sendo removidos. Uma reinicialização é geralmente necessária para que as alterações entrem em vigor.

Esse parâmetro foi introduzido no PowerShell 3,0.

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

### -UnjoinDomainCredential

Especifica uma conta de usuário que tenha permissão para remover os computadores de seus domínios atuais.
Credenciais explícitas, conforme fornecido por esse parâmetro, são necessárias para remover computadores remotos de um domínio, mesmo quando o valor é as credenciais do usuário atual.

Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um gerado por `Get-Credential` . Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.

Para especificar uma conta de usuário que tenha permissão para se conectar a computadores remotos, use o parâmetro **LocalCredential** .

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Local, Remote
Aliases: Credential

Required: False (Local), True (Remote)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkgroupName

Especifica o nome de um grupo de trabalho ao qual os computadores são adicionados ao serem removidos de seus domínios. O valor padrão é **grupo de trabalho** . Quando um computador é removido de um domínio, é necessário adicioná-lo a um grupo de trabalho.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.String
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

### System.String

Você pode canalizar nomes de computador para thiscmdlet.

## SAÍDAS

### Microsoft. PowerShell. Commands. ComputerChangeInfo

Quando você usa o parâmetro **PassThru** , `Remove-Computer` retorna um objeto **ComputerChangeInfo** .
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

Esse cmdlet não remove computadores de grupos de trabalho.

## LINKS RELACIONADOS

[Add-Computer](Add-Computer.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Stop-Computer](Stop-Computer.md)

[Test-Connection](Test-Connection.md)
