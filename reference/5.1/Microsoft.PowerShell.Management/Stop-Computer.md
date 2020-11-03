---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: 8062210aa94cb46d5e5557ede1bac672cae39622
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194898"
---
# Stop-Computer

## SINOPSE
Encerra (desliga) computadores locais e remotos.

## SYNTAX

### Tudo

```
Stop-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `Stop-Computer` cmdlet desliga o computador local e os computadores remotos.

Você pode usar os parâmetros de `Stop-Computer` para executar as operações de desligamento como um trabalho em segundo plano, para especificar os níveis de autenticação e credenciais alternativas, para limitar as conexões simultâneas criadas para executar o comando e forçar um desligamento imediato.

Esse cmdlet não requer comunicação remota do PowerShell, a menos que você use o parâmetro **AsJob** .

## EXEMPLOS

### Exemplo 1: desligar o computador local

Este exemplo desliga o computador local.

```powershell
Stop-Computer -ComputerName localhost
```

### Exemplo 2: desligar dois computadores remotos e o computador local

Este exemplo interrompe dois computadores remotos e o computador local.

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

`Stop-Computer` usa o parâmetro **ComputerName** para especificar dois computadores remotos e o computador local. Cada computador é desligado.

### Exemplo 3: desligar computadores remotos como um trabalho em segundo plano

Neste exemplo, `Stop-Computer` é executado como um trabalho em segundo plano em dois computadores remotos.

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" -AsJob
$results = $j | Receive-Job
$results
```

`Stop-Computer` usa o parâmetro **ComputerName** para especificar dois computadores remotos. O parâmetro **AsJob** executa o comando como um trabalho em segundo plano. Os objetos de trabalho são armazenados na `$j` variável.

Os objetos de trabalho na `$j` variável são enviados ao pipeline para `Receive-Job` , que obtém os resultados do trabalho. Os objetos são armazenados na `$results` variável. A `$results` variável exibe as informações do trabalho no console do PowerShell.

Como **AsJob** cria o trabalho no computador local e retorna automaticamente os resultados para o computador local, você pode executar `Receive-Job` como um comando local.

### Exemplo 4: desligar um computador remoto

Este exemplo desliga um computador remoto usando a autenticação especificada.

```powershell
Stop-Computer -ComputerName "Server01" -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

`Stop-Computer` usa o parâmetro **ComputerName** para especificar o computador remoto. O parâmetro **Impersonation** especifica uma representação personalizada e o parâmetro **DcomAuthentication** especifica as configurações de nível de autenticação.

### Exemplo 5: desligar os computadores em um domínio

Neste exemplo, os comandos forçam um desligamento imediato de todos os computadores em um domínio especificado.

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -ThrottleLimit 10 -Credential $c
```

`Get-Content` usa o parâmetro **path** para obter um arquivo no diretório atual com a lista de computadores de domínio. Os objetos são armazenados na `$s` variável.

`Get-Credential` usa o parâmetro **Credential** para especificar as credenciais de um administrador de domínio. As credenciais são armazenadas na `$c` variável.

`Stop-Computer` Desliga os computadores especificados com a lista de computadores do parâmetro **ComputerName** na `$s` variável. O parâmetro **Force** força um desligamento imediato. O parâmetro **ThrottleLimit** limita o comando a 10 conexões simultâneas. O parâmetro **Credential** envia as credenciais salvas na `$c` variável.

## PARAMETERS

### -AsJob

Indica que esse cmdlet é executado como um trabalho em segundo plano.

Para usar esse parâmetro, os computadores locais e remotos devem ser configurados para comunicação remota e, no Windows Vista e em versões posteriores do sistema operacional Windows, você deve abrir o PowerShell usando a opção **Executar como administrador** . Para obter mais informações, consulte [about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md).

Quando você especifica o parâmetro **AsJob** , o comando retorna imediatamente um objeto que representa o trabalho em segundo plano. É possível continuar a trabalhar na sessão enquanto o trabalho é concluído. O trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local. Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.

Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) e [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md).

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

### -ComputerName

Especifica os computadores a serem interrompidos. O padrão é o computador local.

Digite o nome da NETBIOS, o endereço IP ou o nome de domínio totalmente qualificado de um ou mais computadores em uma lista separada por vírgulas. Para especificar o computador local, digite o nome do computador ou localhost.

Esse parâmetro não depende da comunicação remota do PowerShell. Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. O padrão é o usuário atual.

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, você será solicitado a inserir a senha.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -DcomAuthentication

Especifica o nível de autenticação que esse cmdlet usa com o WMI. `Stop-Computer` usa o WMI. O valor padrão é **pacote** .

Os valores aceitáveis para esse parâmetro são:

- **Padrão** : autenticação do Windows.
- **Nenhum** : nenhuma autenticação com.
- **Connect** : autenticação com de nível de conexão.
- **Chamada** : autenticação com em nível de chamada.
- **Pacote** : autenticação com em nível de pacote.
- **PacketIntegrity** : autenticação com de nível de integridade de pacote.
- **PacketPrivacy** de privacidade: pacote de autenticação com.
- **Inalterado** : o mesmo que o comando anterior.

Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel).

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Força um desligamento imediato do computador.

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

### -Representação

Especifica o nível de representação a ser usado quando este cmdlet chama WMI. O valor padrão é **Impersonate** .

`Stop-Computer` usa o WMI. Os valores aceitáveis para esse parâmetro são:

- **Padrão** : representação padrão.
- **Anônimo** : oculta a identidade do chamador.
- **Identificar** : permite que os objetos consultem as credenciais do chamador.
- **Impersonate** : permite que os objetos usem as credenciais do chamador.

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

Especifica o protocolo a ser usado para reiniciar os computadores. Os valores aceitáveis para esse parâmetro são: **WSMan** e **DCOM** . O valor padrão é **DCOM** .

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: DCOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.
Se você omite esse parâmetro ou digita um valor 0, o valor padrão, 32, é usado.

O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.

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

### -WsmanAuthentication

Especifica o mecanismo usado para autenticar as credenciais do usuário quando este cmdlet usa o protocolo WSMan. O valor padrão é **Default** .

Os valores aceitáveis para esse parâmetro são:

- Básico
- CredSSP
- Padrão
- Digest
- Kerberos
- Negotiate.

Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> A autenticação do Credential Security Service Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
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

Não é possível canalizar a entrada para este cmdlet.

## SAÍDAS

### Nenhum ou System. Management. Automation. RemotingJob

O cmdlet retorna um objeto **System. Management. Automation. RemotingJob** , se você especificar o parâmetro **AsJob** . Caso contrário, ele não gerará nenhuma saída.

## OBSERVAÇÕES

Esse cmdlet usa o método **Win32Shutdown** da classe WMI **Win32_OperatingSystem** . Esse método requer que o privilégio **SeShutdownPrivilege** seja habilitado para a conta de usuário usada para reiniciar o computador.

## LINKS RELACIONADOS

[Add-Computer](Add-Computer.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Test-Connection](Test-Connection.md)
