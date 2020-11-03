---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Computer
ms.openlocfilehash: 860a5ec4f75136bd53fa5c9621504b1613e9c511
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193948"
---
# Rename-Computer

## SINOPSE
Renomeia um computador.

## SYNTAX

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Rename-Computer` cmdlet renomeia o computador local ou um computador remoto.
Ele renomeia um computador em cada comando.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: renomear o computador local

Esse comando renomeia o computador local para `Server044` e, em seguida, o reinicia para que a alteração seja efetiva.

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### Exemplo 2: renomear um computador remoto

Esse comando renomeia o `Srv01` computador para `Server001` . O computador não foi reiniciado.

O parâmetro **DomainCredential** especifica as credenciais de um usuário que tem permissão para renomear computadores no domínio.

O parâmetro **Force** suprime o prompt de confirmação.

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## PARAMETERS

### -ComputerName

Renomeia o computador remoto especificado.
O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador remoto.
Para especificar o computador local, digite o nome do computador, um ponto ( `.` ) ou `localhost` .

Esse parâmetro não depende da comunicação remota do PowerShell.
Você pode usar o parâmetro **ComputerName** de `Rename-Computer` mesmo que o computador não esteja configurado para executar comandos remotos.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local Computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DomainCredential

Especifica uma conta de usuário que tem permissão para se conectar ao domínio.
São necessárias credenciais explícitas para renomear um computador que ingressou em um domínio.

Digite um nome de usuário, como `User01` ou `Domain01\User01` , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.

Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.

Para especificar uma conta de usuário com permissão para se conectar ao computador especificado pelo parâmetro **ComputerName** , use o parâmetro **LocalCredential** .

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalCredential

Especifica uma conta de usuário que tenha permissão para conectar-se ao computador especificado pelo parâmetro **ComputerName** . O padrão é o usuário atual.

Digite um nome de usuário, como `User01` ou `Domain01\User01` , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.

Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.

Para especificar uma conta de usuário que tenha permissão para se conectar ao domínio, use o parâmetro **DomainCredential** .

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current User
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName

Especifica um novo nome para o computador.
Este parâmetro é necessário.

Os nomes padrão podem conter letras ( `a-z` ), ( `A-Z` ), números ( `0-9` ) e hifens ( `-` ), mas sem espaços ou pontos ( `.` ). O nome não pode consistir inteiramente de dígitos e não pode ter mais de 63 caracteres

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Retorna os resultados do comando.
Caso contrário, este cmdlet não gera nenhuma saída.

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

### -Protocol

Especifica qual protocolo usar para renomear o computador.
Os valores aceitáveis para esse parâmetro são: WSMan e DCOM.
O valor padrão é DCOM.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Restart

Indica que esse cmdlet reinicia o computador que foi renomeado.
Uma reinicialização é geralmente necessária para que as alterações entrem em vigor.

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

### -WsmanAuthentication

Especifica o mecanismo usado para autenticar as credenciais do usuário quando este cmdlet usa o protocolo WSMan. Os valores aceitáveis para esse parâmetro são:

- **Basic**
- **CredSSP**
- **Default**
- **Resumo da mensagem**
- **Kerberos**
- **Inicia**

O valor padrão é **Default** .

Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!WARNING]
> A autenticação do Credential Security Service Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.
> Esse mecanismo aumenta o risco de segurança da operação remota.
> Se o computador remoto estiver comprometido, as credenciais passadas para ele poderão ser usadas para controlar > sessão de rede.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### Nenhum

Esse cmdlet não tem parâmetros que obtêm entradas por valor.
No entanto, é possível redirecionar os valores das propriedades de objetos **ComputerName** e **NewName** para esse cmdlet.

## SAÍDAS

### Microsoft. PowerShell. Commands. ComputerChangeInfo

Esse cmdlet retorna um objeto **ComputerChangeInfo** , se você especificar o parâmetro **PassThru** .
Caso contrário, ele não retorna nenhuma saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Add-Computer](Add-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Reset-ComputerMachinePassword](Reset-ComputerMachinePassword.md)

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
