---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 553b61c9669afab325e9feec101d701c2b9a7c83
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194900"
---
# Restart-Computer

## SINOPSE
Reinicia o sistema operacional em computadores locais e remotos.

## SYNTAX

### Padrãoset (padrão)

```
Restart-Computer [-DcomAuthentication <AuthenticationLevel>] [-Impersonation <ImpersonationLevel>]
 [-WsmanAuthentication <String>] [-Protocol <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AsJobset

```
Restart-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>]
 [-Impersonation <ImpersonationLevel>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Force] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Restart-Computer` cmdlet reinicia o sistema operacional nos computadores locais e remotos.

Você pode usar os parâmetros de `Restart-Computer` para executar as operações de reinicialização como um trabalho em segundo plano, para especificar os níveis de autenticação e as credenciais alternativas, para limitar as operações executadas ao mesmo tempo e forçar uma reinicialização imediata.

A partir do Windows PowerShell 3,0, você pode aguardar a conclusão da reinicialização antes de executar o próximo comando. Especifique um tempo limite de espera e um intervalo de consulta e aguarde a disponibilidade de serviços específicos no computador reiniciado. Esse recurso torna o uso prático `Restart-Computer` em scripts e funções.

Você pode usar o protocolo WSMan (WS-Management) para reiniciar o computador, caso as chamadas DCOM (Component Object Model distribuídas) sejam bloqueadas, como por um firewall corporativo. Para obter mais informações, consulte [protocolo WS-Management](/windows/desktop/WinRM/ws-management-protocol).

Esse cmdlet requer a comunicação remota do Windows PowerShell somente quando você usa o parâmetro **AsJob** em um comando.

## EXEMPLOS

### Exemplo 1: reiniciar o computador local

`Restart-Computer` reinicia o computador local.

```powershell
Restart-Computer
```

### Exemplo 2: reiniciar vários computadores

`Restart-Computer` pode reiniciar computadores remotos e locais. O parâmetro **ComputerName** aceita uma matriz de nomes de computador.

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### Exemplo 3: reiniciar computadores como um trabalho em segundo plano

Esses comandos executam um `Restart-Computer` comando como um trabalho em segundo plano em dois computadores remotos e, em seguida, obtêm os resultados.

Como **AsJob** cria o trabalho no computador local e retorna automaticamente os resultados para o computador local, você pode executar `Receive-Job` como um comando local.

```powershell
$Job = Restart-Computer -ComputerName "Server01", "Server02" -AsJob
$Job | Receive-Job
```

`Restart-Computer` usa o parâmetro **ComputerName** para especificar **Server01** e **Server02** . O parâmetro **AsJob** executa o comando como um trabalho em segundo plano. O objeto de trabalho é armazenado na `$Job` variável. `$Job` é enviado ao pipeline para o `Receive-Job` cmdlet que obtém os resultados.

### Exemplo 4: reiniciar um computador remoto

`Restart-Computer` reinicia um computador remoto com configurações personalizadas de representação e autenticação.

```powershell
Restart-Computer -ComputerName Server01 -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

`Restart-Computer` usa o parâmetro **ComputerName** para especificar **Server01** . O parâmetro **Impersonation** especifica Anonymous para ocultar a identidade do solicitante. O parâmetro **DcomAuthentication** especifica PacketIntegrity como o nível de autenticação da conexão.

### Exemplo 5: forçar a reinicialização de computadores listados em um arquivo de texto

Este exemplo força uma reinicialização imediata dos computadores listados no `Domain01.txt` arquivo. Os nomes de computador do arquivo de texto são armazenados em uma variável. O parâmetro **Force** força uma reinicialização imediata e o parâmetro **ThrottleLimit** limita o número de conexões simultâneas.

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force -ThrottleLimit 10
```

`Get-Content` usa o parâmetro **path** para obter uma lista de nomes de computador de um arquivo de texto, **Domain01.txt** . Os nomes dos computadores são armazenados na variável `$Names` . `Get-Credential` solicita um nome de usuário e uma senha e armazena os valores na variável `$Creds` . `Restart-Computer` usa os parâmetros **ComputerName** e **Credential** com suas variáveis. O parâmetro **Force** causa uma reinicialização imediata de cada computador. O parâmetro **ThrottleLimit** limita o comando a 10 conexões simultâneas.

### Exemplo 6: reiniciar um computador remoto e aguardar o PowerShell

`Restart-Computer` reinicia o computador remoto e aguarda até 5 minutos (300 segundos) para que o PowerShell fique disponível no computador reiniciado antes de continuar.

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

`Restart-Computer` usa o parâmetro **ComputerName** para especificar **Server01** . O parâmetro **Wait** aguarda a conclusão da reinicialização. O **para** especifica que o PowerShell pode executar comandos no computador remoto. O parâmetro **Timeout** especifica uma espera de cinco minutos. O parâmetro **Delay** consulta o computador remoto a cada dois segundos para determinar se ele foi reiniciado.

### Exemplo 7: reiniciar um computador usando o protocolo WSMan

`Restart-Computer` reinicia o computador remoto usando o protocolo WSMan em vez do padrão, DCOM. A autenticação Kerberos determina se o usuário atual tem permissão para reiniciar o computador remoto.

Essas configurações foram projetadas para empresas nas quais as reinicializações baseadas em DCOM falham porque o DCOM está bloqueado. Por exemplo, por um firewall.

```powershell
Restart-Computer -ComputerName Server01 -Protocol WSMan -WsmanAuthentication Kerberos
```

`Restart-Computer` usa o parâmetro **ComputerName** para especificar o computador remoto, **Server01** .
O parâmetro **Protocol** especifica o uso do protocolo WSMan. O parâmetro **WsmanAuthentication** especifica o método de autenticação como **Kerberos** .

## PARAMETERS

### -AsJob

Indica que `Restart-Computer` o é executado como um trabalho em segundo plano.

Para usar esse parâmetro, os computadores locais e remotos devem ser configurados para comunicação remota. No Windows Vista e versões posteriores do sistema operacional Windows, você deve abrir o PowerShell usando a opção **Executar como administrador** . Para obter mais informações, consulte [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

Quando você especifica o parâmetro **AsJob** , o comando retorna imediatamente um objeto que representa o trabalho em segundo plano. É possível continuar a trabalhar na sessão enquanto o trabalho é concluído. O trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local. Para gerenciar o trabalho, use os cmdlets **Job** . Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.

Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) e [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Especifica um nome de computador ou uma matriz separada por vírgulas de nomes de computador. `Restart-Computer` aceita objetos **ComputerName** do pipeline ou das variáveis.

Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador remoto. Para especificar o computador local, digite o nome do computador, um ponto `.` ou localhost.

Esse parâmetro não depende da comunicação remota do PowerShell. Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.

Se o parâmetro **ComputerName** não for especificado, `Restart-Computer` o reiniciará o computador local.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

Especifica o nível de autenticação que é usado para a conexão WMI. `Restart-Computer` usa o WMI.

Os valores válidos são:

- **Chamada** : autenticação com em nível de chamada
- **Conectar** : autenticação com no nível de conexão
- **Padrão** : autenticação do Windows
- **Nenhum** : nenhuma autenticação com
- **Pacote** : autenticação com em nível de pacote.
- **PacketIntegrity** : autenticação com de nível de integridade de pacote
- **PacketPrivacy** de privacidade: pacote de autenticação com.
- **Inalterado** : o nível de autenticação é o mesmo que o comando anterior.

Para obter mais informações, consulte [Enumeração AuthenticationLevel](/dotnet/api/system.management.authenticationlevel).

Este parâmetro é introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Atraso

Especifica a frequência de consultas, em segundos. O PowerShell consulta o serviço especificado pelo parâmetro **for** para determinar se o serviço está disponível depois que o computador é reiniciado.

Esse parâmetro é válido somente junto com os parâmetros **Wait** e **for** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

Se o parâmetro **Delay** não for especificado, o `Restart-Computer` usará um atraso de cinco segundos.

```yaml
Type: System.Int16
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Para

Especifica o comportamento do PowerShell, pois ele aguarda que o serviço ou o recurso especificado se torne disponível após a reinicialização do computador. Esse parâmetro só é válido com o parâmetro **Wait** .

Os valores aceitáveis para esse parâmetro são:

- **Padrão** : aguarda a reinicialização do PowerShell.
- **PowerShell** : pode executar comandos em uma sessão remota do PowerShell no computador.
- **WMI** : recebe uma resposta a uma consulta Win32_ComputerSystem para o computador.
- **WinRM** : pode estabelecer uma sessão remota para o computador usando o WS-Management.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: DefaultSet
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Força uma reinicialização imediata do computador.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Representação

Especifica o nível de representação que esse cmdlet usa para chamar o WMI. `Restart-Computer` usa o WMI.
Os valores aceitáveis para esse parâmetro são:

- **Padrão** : representação padrão. Apesar do nome, esse não é o valor padrão.
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

Especifica o protocolo a ser usado para reiniciar os computadores. Os valores válidos são **WSMan** e **DCOM** .

Este parâmetro é introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.
O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.

Se o parâmetro **ThrottleLimit** não for especificado ou um valor de 0 for usado, `Restart-Computer` o usará um máximo de 32 conexões simultâneas.

```yaml
Type: System.Int32
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tempo limite

Especifica a duração da espera, em segundos. Quando o tempo limite expira, o `Restart-Computer` retorna ao prompt de comando, mesmo que os computadores não sejam reiniciados.

O parâmetro **Timeout** só é válido com o parâmetro **Wait** . O **tempo limite** substitui o período de espera indefinido do parâmetro de **espera** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Int32
Parameter Sets: DefaultSet
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

`Restart-Computer` suprime o prompt do PowerShell e bloqueia o pipeline até que os computadores sejam reiniciados. Você pode usar esse parâmetro em um script para reiniciar os computadores e continuar a processar quando a reinicialização for concluída.

O parâmetro **Wait** aguarda indefinidamente para que os computadores sejam reiniciados. Você pode usar o **tempo limite** para ajustar o tempo e os parâmetros **de e de** **atraso** para aguardar que serviços específicos se tornem disponíveis nos computadores reiniciados.

O parâmetro **Wait** não é válido quando você está reiniciando o computador local. Se o valor do parâmetro **ComputerName** contiver os nomes de computadores remotos e o computador local, o `Restart-Computer` gerará um erro de não finalização para **aguardar** no computador local, mas aguardará a reinicialização dos computadores remotos.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WsmanAuthentication

Especifica o mecanismo usado para autenticar as credenciais do usuário. Este parâmetro foi introduzido no Windows PowerShell 3.0.

Os valores aceitáveis para esse parâmetro são: **Basic** , **CredSSP** , **Default** , **Digest** , **Kerberos** e **Negotiate** .

Para obter mais informações, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!WARNING]
> A autenticação do Credential Security Service Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Solicita a confirmação antes de executar `Restart-Computer` .

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

Mostra o que aconteceria se o `Restart-Computer` for executado. O `Restart-Computer` cmdlet não é executado.

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

`Restart-Computer` aceita nomes de computador do pipeline ou de variáveis.

No Windows PowerShell 2.0, o parâmetro **ComputerName** aceita entradas do pipeline somente pelo nome da propriedade. No Windows PowerShell 3,0 e posterior, o parâmetro **ComputerName** usa a entrada do pipeline por valor.

## SAÍDAS

### Nenhum, System. Management. Automation. RemotingJob

Se você especificar o parâmetro **AsJob** , o `Restart-Computer` retornará um objeto de trabalho. Do contrário, nenhuma saída é gerada.

## OBSERVAÇÕES

- `Restart-Computer` Só funciona em computadores que executam o Windows e exige que o WinRM e o WMI desliguem um sistema, incluindo o sistema local.
- `Restart-Computer` usa o [método Win32Shutdown](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) da classe Instrumentação de gerenciamento do Windows (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) .  Esse método requer que o privilégio **SeShutdownPrivilege** seja habilitado para a conta de usuário usada para reiniciar o computador.

No Windows PowerShell 2,0, o parâmetro **AsJob** não funciona de maneira confiável quando você está reiniciando ou parando computadores remotos. No Windows PowerShell 3.0, a implementação é alterada para resolver esse problema.

## LINKS RELACIONADOS

[Sobre Gerenciamento Remoto do Windows](/windows/desktop/WinRM/about-windows-remote-management)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Protocolo WS-Management](/windows/desktop/WinRM/ws-management-protocol)
