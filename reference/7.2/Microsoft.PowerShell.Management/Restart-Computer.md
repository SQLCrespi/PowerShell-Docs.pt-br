---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 0e6df859a19f2281cc835b725fbc52c232042e56
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597405"
---
# Restart-Computer

## SINOPSE
Reinicia o sistema operacional em computadores locais e remotos.

## SYNTAX

### Padrãoset (padrão)

```
Restart-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential]<PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Restart-Computer` cmdlet reinicia o sistema operacional nos computadores locais e remotos.

Você pode usar os parâmetros de `Restart-Computer` para executar as operações de reinicialização, para especificar os níveis de autenticação e as credenciais alternativas, para limitar as operações executadas ao mesmo tempo e forçar uma reinicialização imediata.

A partir do Windows PowerShell 3,0, você pode aguardar a conclusão da reinicialização antes de executar o próximo comando. Especifique um tempo limite de espera e um intervalo de consulta e aguarde a disponibilidade de serviços específicos no computador reiniciado. Esse recurso torna o uso prático `Restart-Computer` em scripts e funções.

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

### Exemplo 3: obter nomes de computador de um arquivo de texto

`Restart-Computer` Obtém uma lista de nomes de computador de um arquivo de texto e reinicia os computadores. O parâmetro **ComputerName** não foi especificado. Mas, como é o primeiro parâmetro de posição, ele aceita os nomes de computador do arquivo de texto que são enviados pelo pipeline.

```powershell
Get-Content -Path C:\Domain01.txt | Restart-Computer
```

`Get-Content` usa o parâmetro **path** para obter uma lista de nomes de computador de um arquivo de texto, **Domain01.txt**. Os nomes dos computadores são enviados pelo pipeline. `Restart-Computer` reinicia cada computador.

### Exemplo 4: forçar a reinicialização de computadores listados em um arquivo de texto

Este exemplo força uma reinicialização imediata dos computadores listados no `Domain01.txt` arquivo. Os nomes de computador do arquivo de texto são armazenados em uma variável. O parâmetro **Force** força uma reinicialização imediata.

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force
```

`Get-Content` usa o parâmetro **path** para obter uma lista de nomes de computador de um arquivo de texto, **Domain01.txt**. Os nomes dos computadores são armazenados na variável `$Names` . `Get-Credential` solicita um nome de usuário e uma senha e armazena os valores na variável `$Creds` . `Restart-Computer` usa os parâmetros **ComputerName** e **Credential** com suas variáveis. O parâmetro **Force** causa uma reinicialização imediata de cada computador.

### Exemplo 6: reiniciar um computador remoto e aguardar o PowerShell

`Restart-Computer` reinicia o computador remoto e aguarda até 5 minutos (300 segundos) para que o PowerShell fique disponível no computador reiniciado antes de continuar.

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

`Restart-Computer` usa o parâmetro **ComputerName** para especificar **Server01**. O parâmetro **Wait** aguarda a conclusão da reinicialização. O **para** especifica que o PowerShell pode executar comandos no computador remoto. O parâmetro **Timeout** especifica uma espera de cinco minutos. O parâmetro **Delay** consulta o computador remoto a cada dois segundos para determinar se ele foi reiniciado.

### Exemplo 7: reiniciar um computador usando o WsmanAuthentication

`Restart-Computer` reinicia o computador remoto usando o mecanismo **WsmanAuthentication** .
A autenticação Kerberos determina se o usuário atual tem permissão para reiniciar o computador remoto. Para obter mais informações, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

```powershell
Restart-Computer -ComputerName Server01 -WsmanAuthentication Kerberos
```

`Restart-Computer` usa o parâmetro **ComputerName** para especificar o computador remoto, **Server01**.
O parâmetro **WsmanAuthentication** especifica o método de autenticação como **Kerberos**.

## PARAMETERS

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

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, você será solicitado a inserir a senha.

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

### -Atraso

Especifica a frequência de consultas, em segundos. O PowerShell consulta o serviço especificado pelo parâmetro **for** para determinar se o serviço está disponível depois que o computador é reiniciado.

Esse parâmetro é válido somente junto com os parâmetros **Wait** e **for** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

Se o parâmetro **Delay** não for especificado, o `Restart-Computer` usará um atraso de cinco segundos.

```yaml
Type: System.Int16
Parameter Sets: (All)
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

- **Padrão**: aguarda a reinicialização do PowerShell.
- **PowerShell**: pode executar comandos em uma sessão remota do PowerShell no computador.
- **WMI**: recebe uma resposta a uma consulta Win32_ComputerSystem para o computador.
- **WinRM**: pode estabelecer uma sessão remota para o computador usando o WS-Management.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: (All)
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

### -Tempo limite

Especifica a duração da espera, em segundos. Quando o tempo limite expira, o `Restart-Computer` retorna ao prompt de comando, mesmo que os computadores não sejam reiniciados.

O parâmetro **Timeout** só é válido com o parâmetro **Wait** . O **tempo limite** substitui o período de espera indefinido do parâmetro de **espera** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Int32
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WsmanAuthentication

Especifica o mecanismo usado para autenticar as credenciais do usuário. Este parâmetro foi introduzido no Windows PowerShell 3.0.

Os valores aceitáveis para esse parâmetro são: **Basic**, **CredSSP**, **Default**, **Digest**, **Kerberos** e **Negotiate**.

Para obter mais informações, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!WARNING]
> A autenticação do Credential Security Service Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

```yaml
Type: System.String
Parameter Sets: (All)
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

## SAÍDAS

### Nenhum

`Restart-Computer` não gera nenhuma saída.

## OBSERVAÇÕES

- No Windows, `Restart-Computer` o usa o [método Win32Shutdown](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) da classe Instrumentação de gerenciamento do Windows (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) . Esse método requer que o privilégio **SeShutdownPrivilege** seja habilitado para a conta de usuário usada para reiniciar o computador.
- No Linux e Mac OS, `Restart-Computer` o usa a `/sbin/shutdown` ferramenta bash.

## LINKS RELACIONADOS

[Sobre Gerenciamento Remoto do Windows](/windows/desktop/WinRM/about-windows-remote-management)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Protocolo WS-Management](/windows/desktop/WinRM/ws-management-protocol)
