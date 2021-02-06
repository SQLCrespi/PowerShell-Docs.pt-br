---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-PSSession
ms.openlocfilehash: 4bc7ba3a8129dd332b13bee30e386dd459d92226
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603773"
---
# Receive-PSSession

## SINOPSE

Obtém resultados de comandos em sessões desconectadas

## SYNTAX

### Sessão (padrão)

```
Receive-PSSession [-Session] <PSSession> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ID

```
Receive-PSSession [-Id] <Int32> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ComputerSessionName

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ComputerInstanceId

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ConnectionUriSessionName

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ConnectionUriInstanceId

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Receive-PSSession -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SessionName

```
Receive-PSSession -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `Receive-PSSession` cmdlet obtém os resultados de comandos em execução em sessões do PowerShell (**PSSession**) que foram desconectadas. Se a sessão estiver conectada no momento, `Receive-PSSession` o obterá os resultados dos comandos que estavam em execução quando a sessão foi desconectada. Se a sessão ainda estiver desconectada, conecta-se `Receive-PSSession` à sessão, retoma todos os comandos que foram suspensos e obtém os resultados dos comandos em execução na sessão.

Esse cmdlet foi introduzido no PowerShell 3,0.

Você pode usar um `Receive-PSSession` , além de ou em vez de um `Connect-PSSession` comando.
`Receive-PSSession` pode se conectar a qualquer sessão desconectada ou reconectada que foi iniciada em outras sessões ou em outros computadores.

`Receive-PSSession` funciona em **PSSessions** que foram desconectadas intencionalmente usando o `Disconnect-PSSession` cmdlet ou o `Invoke-Command` parâmetro **InDisconnectedSession** . Ou desconectado de forma não intencional por uma interrupção de rede.

Se você usar o `Receive-PSSession` cmdlet para se conectar a uma sessão na qual nenhum comando está em execução ou suspenso, `Receive-PSSession` o se conectará à sessão, mas não retornará nenhuma saída ou erro.

Para obter mais informações sobre o recurso de Sessões desconectadas, consulte [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).

Alguns exemplos usam nivelamento para reduzir o tamanho da linha e melhorar a legibilidade. Para obter mais informações, consulte [about_Splatting](./About/about_Splatting.md).

## EXEMPLOS

### Exemplo 1: conectar-se a uma PSSession

Este exemplo se conecta a uma sessão em um computador remoto e obtém os resultados de comandos que estão sendo executados em uma sessão.

```powershell
Receive-PSSession -ComputerName Server01 -Name ITTask
```

O `Receive-PSSession` especifica o computador remoto com o parâmetro **ComputerName** . O parâmetro **Name** identifica a sessão ITTask no computador Server01. O exemplo obtém os resultados de comandos que estavam em execução na sessão ITTask.

Como o comando não usa o parâmetro **outtarget** , os resultados aparecem na linha de comando.

### Exemplo 2: obter resultados de todos os comandos em sessões desconectadas

Este exemplo obtém os resultados de todos os comandos em execução em todas as sessões desconectadas em dois computadores remotos.

Se alguma sessão não tiver sido desconectada ou não estiver executando comandos, `Receive-PSSession` o não se conectará à sessão e não retornará nenhuma saída ou erro.

```powershell
Get-PSSession -ComputerName Server01, Server02 | Receive-PSSession
```

`Get-PSSession` usa o parâmetro **ComputerName** para especificar os computadores remotos. Os objetos são enviados ao pipeline para `Receive-PSSession` .

### Exemplo 3: obter os resultados de um script em execução em uma sessão

Este exemplo usa o `Receive-PSSession` cmdlet para obter os resultados de um script que estava sendo executado na sessão de um computador remoto.

```powershell
$parms = @{
  ComputerName = "Server01"
  Name = "ITTask"
  OutTarget = "Job"
  JobName = "ITTaskJob01"
  Credential = "Domain01\Admin01"
}
Receive-PSSession @parms
```

```Output
Id     Name            State         HasMoreData     Location
--     ----            -----         -----------     --------
16     ITTaskJob01     Running       True            Server01
```

O comando usa os parâmetros **ComputerName** e **Name** para identificar a sessão desconectada.
Ele usa o parâmetro de **destino** com um valor de trabalho para direcionar `Receive-PSSession` para retornar os resultados como um trabalho. O parâmetro **JobName** especifica um nome para o trabalho na sessão reconectada.
O parâmetro **Credential** executa o `Receive-PSSession` comando usando as permissões de um administrador de domínio.

A saída mostra que `Receive-PSSession` retornou os resultados como um trabalho na sessão atual. Para obter os resultados do trabalho, use um `Receive-Job` comando

### Exemplo 4: obter resultados após uma interrupção de rede

Este exemplo usa o `Receive-PSSession` cmdlet para obter os resultados de um trabalho depois que uma interrupção de rede interrompe uma conexão de sessão. O PowerShell tenta automaticamente reconectar a sessão uma vez por segundo nos próximos quatro minutos e abandonar o esforço somente se todas as tentativas no intervalo de quatro minutos falharem.

```
PS> $s = New-PSSession -ComputerName Server01 -Name AD -ConfigurationName ADEndpoint
PS> $s

Id  Name   ComputerName    State        ConfigurationName     Availability
--  ----   ------------    -----        -----------------     ------------
8   AD      Server01       Opened       ADEndpoint               Available


PS> Invoke-Command -Session $s -FilePath \\Server12\Scripts\SharedScripts\New-ADResolve.ps1

Running "New-ADResolve.ps1"

# Network outage
# Restart local computer
# Network access is not re-established within 4 minutes


PS> Get-PSSession -ComputerName Server01

Id  Name   ComputerName    State          ConfigurationName      Availability
--  ----   ------------    -----          -----------------      ------------
1  Backup  Server01        Disconnected   Microsoft.PowerShell           None
8  AD      Server01        Disconnected   ADEndpoint                     None


PS> Receive-PSSession -ComputerName Server01 -Name AD -OutTarget Job -JobName AD

Job Id   Name      State         HasMoreData     Location
--       ----      -----         -----------     --------
16       ADJob     Running       True            Server01


PS> Get-PSSession -ComputerName Server01

Id  Name    ComputerName    State         ConfigurationName     Availability
--  ----    ------------    -----         -----------------     ------------
1  Backup   Server01        Disconnected  Microsoft.PowerShell          Busy
8  AD       Server01        Opened        ADEndpoint               Available
```

O `New-PSSession` cmdlet cria uma sessão no computador Server01 e salva a sessão na `$s` variável. A `$s` variável exibe que o **estado** é aberto e a **disponibilidade** está disponível. Esses valores indicam que você está conectado à sessão e pode executar comandos na sessão.

O `Invoke-Command` cmdlet executa um script na sessão na `$s` variável. O script começa a ser executado e a retornar dados, mas ocorre uma queda de rede que interrompe a sessão. O usuário precisa sair da sessão e reiniciar o computador local.

Quando o computador é reiniciado, o usuário inicia o PowerShell e executa um `Get-PSSession` comando para obter sessões no computador Server01. A saída mostra que a sessão do **ad** ainda existe no computador Server01. O **estado** indica que a sessão do **ad** está desconectada. O valor de **disponibilidade** de nenhum, indica que a sessão não está conectada a todas as sessões de cliente.

O `Receive-PSSession` cmdlet se reconecta à sessão do **ad** e obtém os resultados do script que foi executado na sessão. O comando usa o parâmetro **outtarget** para solicitar os resultados em um trabalho chamado **ADJob**. O comando retorna um objeto de trabalho e a saída indica que o script ainda está em execução.

O `Get-PSSession` cmdlet é usado para verificar o estado do trabalho. A saída confirma que o `Receive-PSSession` cmdlet foi reconectado à sessão do **ad** , que agora está aberta e disponível para comandos. E o script retomou a execução e está obtendo os resultados do script.

### Exemplo 5: reconectar a sessões desconectadas

Este exemplo usa o `Receive-PSSession` cmdlet para se reconectar a sessões que foram intencionalmente desconectadas e obter os resultados de trabalhos que estavam em execução nas sessões.

```
PS> $parms = @{
      InDisconnectedSession = $True
      ComputerName = "Server01", "Server02", "Server30"
      FilePath = "\\Server12\Scripts\SharedScripts\Get-BugStatus.ps1"
      Name = "BugStatus"
      SessionOption = @{IdleTimeout = 86400000}
      ConfigurationName = "ITTasks"
    }
PS> Invoke-Command @parms
PS> Exit


PS> $s = Get-PSSession -ComputerName Server01, Server02, Server30 -Name BugStatus
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Disconnected  ITTasks                       None
8  ITTask  Server02        Disconnected  ITTasks                       None
2  ITTask  Server30        Disconnected  ITTasks                       None


PS> $Results = Receive-PSSession -Session $s
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Opened        ITTasks                  Available
8  ITTask  Server02        Opened        ITTasks                  Available
2  ITTask  Server30        Opened        ITTasks                  Available


PS> $Results

Bug Report - Domain 01
----------------------
ComputerName          BugCount          LastUpdated
--------------        ---------         ------------
Server01              121               Friday, December 30, 2011 5:03:34 PM
```

O `Invoke-Command` cmdlet executa um script em três computadores remotos. Como o script coleta e resume dados de vários bancos de dado, ele geralmente leva o script um tempo estendido para ser concluído. O comando usa o parâmetro **InDisconnectedSession** que inicia os scripts e, em seguida, desconecta imediatamente as sessões. O parâmetro **SessionOption** estende o valor de **IdleTimeout** da sessão desconectada. As sessões desconectadas são consideradas ociosas desde o momento em que são desconectadas. É importante definir o tempo limite ocioso por tempo suficiente para que os comandos possam ser concluídos e você possa se reconectar à sessão. Você pode definir o **IdleTimeout** somente quando criar a **PSSession** e alterá-la somente quando desconectar dela. Não é possível alterar o valor de **IdleTimeout** quando você se conecta a uma **PSSession** ou recebe seus resultados. Depois de executar o comando, o usuário sai do PowerShell e fecha o computador.

No dia seguinte, o usuário retoma o Windows, inicia o PowerShell e usa `Get-PSSession` para obter as sessões em que os scripts estavam em execução. O comando identifica as sessões pelo nome do computador, nome da sessão e o nome da configuração da sessão e salva as sessões na `$s` variável. O valor da `$s` variável é exibido e mostra que as sessões estão desconectadas, mas não estão ocupadas.

O `Receive-PSSession` cmdlet se conecta às sessões na `$s` variável e obtém seus resultados.
O comando salva os resultados na `$Results` variável. A `$s` variável é exibida e mostra que as sessões estão conectadas e disponíveis para comandos.

Os resultados do script na `$Results` variável são exibidos no console do PowerShell. Se qualquer um dos resultados for inesperado, o usuário poderá executar comandos nas sessões para investigar a causa raiz.

### Exemplo 6: executando um trabalho em uma sessão desconectada

Este exemplo mostra o que acontece com um trabalho que está sendo executado em uma sessão desconectada.

```
PS> $s = New-PSSession -ComputerName Server01 -Name Test
PS> $j = Invoke-Command -Session $s { 1..1500 | Foreach-Object {"Return $_"; sleep 30}} -AsJob
PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Running       True            Server01


PS> $s | Disconnect-PSSession

Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server01        Disconnected  Microsoft.PowerShell          None


PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Disconnected  True            Server01


PS> Receive-Job $j -Keep

Return 1
Return 2


PS> $s2 = Connect-PSSession -ComputerName Server01 -Name Test
PS> $j2 = Receive-PSSession -ComputerName Server01 -Name Test
PS> Receive-Job $j

Return 3
Return 4
```

O `New-PSSession` cmdlet cria a sessão de teste no computador Server01. O comando salva a sessão na variável `$s`.

O `Invoke-Command` cmdlet executa um comando na sessão na `$s` variável. O comando usa o parâmetro **AsJob** para executar o comando como um trabalho e cria o objeto de trabalho na sessão atual.
O comando retorna um objeto de trabalho que é salvo na `$j` variável. A `$j` variável exibe o objeto de trabalho.

O objeto de sessão na `$s` variável é enviado ao pipeline para `Disconnect-PSSession` e a sessão é desconectada.

A `$j` variável é exibida e mostra o efeito de desconectar o objeto de trabalho na `$j` variável. O estado do trabalho agora é Desconectado.

O `Receive-Job` é executado no trabalho na `$j` variável. A saída mostra que o trabalho começou a retornar a saída antes de a sessão e o trabalho serem desconectados.

O `Connect-PSSession` cmdlet é executado na mesma sessão de cliente. O comando reconecta-se à sessão de teste no computador Server01 e salva a sessão na `$s2` variável.

O `Receive-PSSession` cmdlet obtém os resultados do trabalho que estava sendo executado na sessão. Como o comando é executado na mesma sessão, `Receive-PSSession` o retorna os resultados como um trabalho por padrão e reutiliza o mesmo objeto de trabalho. O comando salva o trabalho na `$j2` variável. O `Receive-Job` cmdlet obtém os resultados do trabalho na `$j` variável.

## PARAMETERS

### -AllowRedirection

Indica que esse cmdlet permite o redirecionamento dessa conexão para um Uniform Resource Identifier alternativo (URI).

Quando você usa o parâmetro **ConnectionURI**, o destino remoto pode retornar uma instrução para redirecionar para um URI diferente. Por padrão, o PowerShell não redireciona as conexões, mas você pode usar esse parâmetro para habilitá-la a redirecionar a conexão.

É possível também limitar o número de vezes que a conexão é redirecionada alterando o valor da opção de sessão **MaximumConnectionRedirectionCount**. Use o parâmetro **MaximumRedirection** do `New-PSSessionOption` cmdlet ou defina a propriedade **MaximumConnectionRedirectionCount** da variável de `$PSSessionOption` preferência. O valor padrão é 5.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Especifica um aplicativo. Esse cmdlet se conecta somente a sessões que usam o aplicativo especificado.

Insira o segmento de nome de aplicativo do URI de conexão. Por exemplo, no seguinte URI de conexão, WSMan é o nome do aplicativo: `http://localhost:5985/WSMAN` .

O nome de aplicativo de uma sessão é armazenado na propriedade **Runspace.ConnectionInfo.AppName** da sessão.

O valor do parâmetro é usado para selecionar e filtrar sessões. Ele não altera o aplicativo usado pela sessão.

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Autenticação

Especifica o mecanismo usado para autenticar as credenciais do usuário no comando para se reconectar a uma sessão desconectada. Os valores aceitáveis para esse parâmetro são:

- Padrão
- Básico
- CredSSP
- Digest
- Kerberos
- Negotiate
- NegotiateWithImplicitCredential

O valor padrão é Default.

Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> A autenticação do Credential Security Support Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para se conectar à sessão desconectada. Insira a impressão digital do certificado.

Os certificados são utilizados na autenticação baseada em certificado do cliente. Os certificados podem ser mapeados somente para contas de usuário locais e não funcionam com contas de domínio.

Para obter uma impressão digital do certificado, use um `Get-Item` `Get-ChildItem` comando ou na `Cert:` unidade do PowerShell.

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Especifica o computador no qual a sessão desconectada está armazenada. As sessões são armazenadas no computador que está no lado do servidor ou no fim do recebimento de uma conexão. O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP ou um FQDN (nome de domínio totalmente qualificado) de um computador.
Caracteres curinga não são permitidos. Para especificar o computador local, digite o nome do computador, um ponto ( `.` ), `$env:COMPUTERNAME` ou localhost.

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationName

Especifica o nome de uma configuração de sessão. Esse cmdlet se conecta somente a sessões que usam a configuração de sessão especificada.

Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão. Se você especificar somente o nome da configuração, o URI de esquema a seguir será anexado:

`http://schemas.microsoft.com/powershell`.

O nome de configuração de uma sessão é armazenado na propriedade **ConfigurationName** da sessão.

O valor do parâmetro é usado para selecionar e filtrar sessões. Ele não altera a configuração de sessão usada pela sessão.

Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](./About/about_Session_Configurations.md).

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Conexãouri

Especifica um URI que define o ponto de extremidade de conexão que é usado para reconectar-se à sessão desconectada.

O URI deve ser totalmente qualificado. O formato da cadeia de caracteres é o seguinte:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

O valor padrão é o seguinte:

`http://localhost:5985/WSMAN`

Se você não especificar um URI de conexão, poderá usar os parâmetros **UseSSL**, **ComputerName**, **Port** e **ApplicationName** para especificar os valores de URI de conexão.

Os valores válidos para o segmento **Transport** do URI são HTTP e HTTPS. Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas padrão: 80 para HTTP e 443 para HTTPS. Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.

Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.

```yaml
Type: System.Uri
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases: URI, CU

Required: True
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para se conectar à sessão desconectada. O padrão é o usuário atual.

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, você será solicitado a inserir a senha.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Especifica a ID de uma sessão desconectada. O parâmetro **ID** só funcionará quando a sessão desconectada tiver sido conectada anteriormente à sessão atual.

Esse parâmetro é válido, mas não efetivo, quando a sessão é armazenada no computador local, mas não estava conectada à sessão atual.

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InstanceId

Especifica a ID da instância da sessão desconectada. A ID da instância é um GUID que identifica exclusivamente uma **PSSession** em um computador local ou remoto. A ID da instância é armazenada na propriedade **InstanceId** da **PSSession**.

```yaml
Type: System.Guid
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName

Especifica um nome amigável para o trabalho que `Receive-PSSession` retorna.

`Receive-PSSession` Retorna um trabalho quando o valor do parâmetro **outtarget** é trabalho ou o trabalho que está sendo executado na sessão desconectada foi iniciado na sessão atual.

Se o trabalho que está em execução na sessão desconectada foi iniciado na sessão atual, o PowerShell reutiliza o objeto de trabalho original na sessão e ignora o valor do parâmetro **JobName** .

Se o trabalho que está em execução na sessão desconectada tiver sido iniciado em uma sessão diferente, o PowerShell criará um novo objeto de trabalho. Ele usa um nome padrão, mas você pode usar este parâmetro para alterar o nome.

Se o valor padrão ou o valor explícito do parâmetro **outtarget** não for Job, o comando terá sucesso, mas o parâmetro **JobName** não terá nenhum efeito.

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

### -Name

Especifica o nome amigável da sessão desconectada.

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ConnectionUriSessionName, SessionName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Destino

Determina como os resultados da sessão são retornados. Os valores aceitáveis para esse parâmetro são:

- **Trabalho**. Retorna os resultados de forma assíncrona em um objeto de trabalho. Você pode usar o parâmetro **JobName** para especificar um nome ou novo nome para o trabalho.
- **Host**. Retorna os resultados para a linha de comando (de forma síncrona). Se o comando estiver sendo retomado ou os resultados consistirem de um grande número de objetos, a resposta poderá demorar.

O valor padrão do parâmetro **outtarget** é host. Se o comando que está sendo recebido em uma sessão desconectada foi iniciado na sessão atual, o valor padrão do parâmetro **outtarget** é o formulário no qual o comando foi iniciado. Se o comando foi iniciado como um trabalho, por padrão, ele é retornado como um trabalho. Caso contrário, ele será retornado ao programa host por padrão.

Normalmente, o programa do host exibe objetos retornados na linha de comando sem atraso, mas esse comportamento pode variar.

```yaml
Type: Microsoft.PowerShell.Commands.OutTarget
Parameter Sets: (All)
Aliases:
Accepted values: Default, Host, Job

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Especifica a porta de rede do computador remoto que é usada para se reconectar à sessão. Para se conectar a um computador remoto, ele deve estar escutando na porta usada pela conexão. As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.

Antes de usar uma porta alternativa, você deve configurar o ouvinte do WinRM no computador remoto para escutar nessa porta. Para configurar o ouvinte, digite os dois comandos a seguir no prompt do PowerShell:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Não use o parâmetro **Port** , a menos que seja necessário. A porta que é definida no comando aplica-se a todos os computadores ou sessões em que o comando é executado. Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessão

Especifica a sessão desconectada. Insira uma variável que contém a **PSSession** ou um comando que cria ou obtém a **PSSession**, como um `Get-PSSession` comando.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionOption

Especifica as opções avançadas para a sessão. Insira um objeto **SessionOption** , como um que você cria usando o `New-PSSessionOption` cmdlet ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.

Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se ele estiver definido. Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.

Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão. No entanto, eles não têm precedência sobre os valores máximos, cotas ou limites definidos na configuração da sessão.

Para obter uma descrição das opções de sessão que incluem os valores padrão, consulte `New-PSSessionOption` . Para obter informações sobre a variável de preferência de **$PSSessionOption** , consulte [about_Preference_Variables](./About/about_Preference_Variables.md). Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](./About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para se conectar à sessão desconectada. Por padrão, o SSL não é usado.

WS-Management criptografa todo o conteúdo do PowerShell transmitido pela rede. **UseSSL** é uma proteção adicional que envia os dados em uma conexão HTTPS em vez de usar uma conexão HTTP.

Se você usar esse parâmetro e o SSL não estiver disponível na porta usada para o comando, o comando falhará.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases:

Required: False
Position: Named
Default value: False
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

### System. Management. Automation. Runspaces. PSSession

Você pode canalizar objetos de sessão para esse cmdlet, como objetos retornados pelo `Get-PSSession` cmdlet.

### System.Int32

É possível canalizar IDs de sessão para este cmdlet.

### System.Guid

Você pode canalizar as IDs de instância de sessões deste cmdlet.

### System.String

É possível canalizar nomes de sessão para este cmdlet.

## SAÍDAS

### System. Management. Automation. Job ou PSObject

Esse cmdlet retorna os resultados dos comandos que foram executados na sessão desconectada, se houver. Se o valor ou o valor padrão do parâmetro **outtarget** for Job, o `Receive-PSSession` retornará um objeto de trabalho. Caso contrário, ele retorna objetos que representam os resultados do comando.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

`Receive-PSSession` Obtém resultados somente de sessões que foram desconectadas. Somente as sessões que estão conectadas ou terminam em, computadores que executam o PowerShell 3,0 ou versões posteriores podem ser desconectados e reconectados.

Se os comandos que estavam em execução na sessão desconectada não geraram resultados ou se os resultados já tiverem sido retornados para outra sessão, o `Receive-PSSession` não gerará nenhuma saída.

O modo de buffer de saída de uma sessão determina como os comandos na sessão gerenciam a saída quando a sessão é desconectada. Quando o valor da opção **OutputBufferingMode** da sessão é drop e o buffer de saída está cheio, o comando começa a excluir a saída. `Receive-PSSession` Não é possível recuperar esta saída. Para obter mais informações sobre a opção de modo de buffer de saída, consulte os artigos de ajuda para os cmdlets [New-PSSessionOption](New-PSSessionOption.md) e [New-PSTransportOption](New-PSTransportOption.md) .

Não é possível alterar o valor de tempo limite ocioso de uma **PSSession** quando você se conecta à **PSSession** ou recebe resultados. O parâmetro **SessionOption** de `Receive-PSSession` usa um objeto **SessionOption** que tem um valor **IdleTimeout** . No entanto, o valor de **IdleTimeout** do objeto **SessionOption** e o valor de **IdleTimeout** da `$PSSessionOption` variável são ignorados quando se conecta a uma **PSSession** ou recebe resultados.

- Você pode definir e alterar o tempo limite de ociosidade de uma **PSSession** quando você cria a **PSSession**, usando os `New-PSSession` `Invoke-Command` cmdlets ou, e quando você se desconecta da **PSSession**.
- A propriedade **IdleTimeout** de uma **PSSession** é crítica para sessões desconectadas porque determina por quanto tempo uma sessão desconectada é mantida no computador remoto. Sessões desconectadas são consideradas ociosas desde o momento em que são desconectadas, ainda que comandos estejam em execução na sessão desconectada.

Se você iniciar uma tarefa iniciar um trabalho em uma sessão remota usando o parâmetro **AsJob** do `Invoke-Command` cmdlet, o objeto de trabalho será criado na sessão atual, mesmo que o trabalho seja executado na sessão remota. Se você desconectar a sessão remota, o objeto de trabalho na sessão atual será desconectado do trabalho. O objeto de trabalho contém todos os resultados que foram retornados a ele, mas não recebe novos resultados do trabalho na sessão desconectada.

Se um cliente diferente se conectar à sessão que contém o trabalho em execução, os resultados que foram entregues ao objeto de trabalho original na sessão original não estarão disponíveis na sessão conectada recentemente. Somente resultados que não foram fornecidos ao objeto de trabalho original ficam disponíveis na sessão reconectada.

Da mesma forma, se você iniciar um script em uma sessão e desconectar-se da sessão, todos os resultados que o script entrega para a sessão antes de desconectar não estarão disponíveis para outro cliente que se conecte à sessão.

Para evitar a perda de dados em sessões que você pretende desconectar, use o parâmetro **InDisconnectedSession** do `Invoke-Command` cmdlet. Como esse parâmetro impede que resultados sejam retornados à sessão atual, todos os resultados ficam disponíveis quando a sessão é reconectada.

Você também pode evitar a perda de dados usando o `Invoke-Command` cmdlet para executar um `Start-Job` comando na sessão remota. Nesse caso, o objeto de trabalho é criado na sessão remota. Você não pode usar o `Receive-PSSession` cmdlet para obter os resultados do trabalho. Em vez disso, use o `Connect-PSSession` cmdlet para se conectar à sessão e, em seguida, use o `Invoke-Command` cmdlet para executar um `Receive-Job` comando na sessão.

Quando uma sessão que contém um trabalho em execução é desconectada e, em seguida, reconectada, o objeto de trabalho original é reutilizado somente se o trabalho é desconectado e reconectado à mesma sessão, e o comando para reconectar não especifica um novo nome de trabalho. Se a sessão for reconectada a uma sessão de cliente diferente ou se um novo nome de trabalho for especificado, o PowerShell criará um novo objeto de trabalho para a nova sessão.

Quando você desconecta uma **PSSession**, o estado da sessão é desconectado e a disponibilidade é nenhuma.

- O valor da propriedade **State** é relativo a sessão atual. Um valor de desconectado significa que a **PSSession** não está conectada à sessão atual. No entanto, isso não significa que a **PSSession** seja desconectada de todas as sessões. Ela pode ser conectada a uma sessão diferente.
  Para determinar se é possível conectar-se ou reconectar-se à sessão, utilize a propriedade **Availability**.
- Um valor **Availability** de None indica que é possível conectar-se à sessão. Um valor de ocupado indica que você não pode se conectar à **PSSession** porque ela está conectada a outra sessão.
- Para obter mais informações sobre os valores da propriedade **State** de sessões, consulte [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).
- Para obter mais informações sobre os valores da propriedade de sessões de **disponibilidade** , consulte [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).

## LINKS RELACIONADOS

[about_PSSessions](./About/about_PSSessions.md)

[about_Remote](./About/about_Remote.md)

[about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md)

[about_Session_Configurations](./About/about_Session_Configurations.md)

[Connect-PSSession](Connect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[Remove-PSSession](Remove-PSSession.md)
