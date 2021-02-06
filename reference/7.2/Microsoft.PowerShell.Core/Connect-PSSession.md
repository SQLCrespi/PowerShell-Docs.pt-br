---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: fda672ba4f6dafc9f955ef8025c386f7732d81bc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603759"
---
# Connect-PSSession

## SINOPSE
Reconecta-se a sessões desconectadas.

## SYNTAX

### Nome (padrão)

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Sessão

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ComputerNameGuid

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ComputerName

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ConnectionUriGuid

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ConnectionUri

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ID

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Connect-PSSession` cmdlet se reconecta a sessões do PowerShell gerenciadas pelo usuário (**PSSessions**) que foram desconectadas. Ele funciona em sessões desconectadas intencionalmente, como usando o `Disconnect-PSSession` cmdlet ou o parâmetro **InDisconnectedSession** do `Invoke-Command` cmdlet, e aqueles que foram desconectados de forma não intencional, como por uma interrupção de rede temporária.

`Connect-PSSession` pode se conectar a qualquer sessão desconectada que foi iniciada pelo mesmo usuário. Elas incluem aquelas que foram iniciadas pelo ou desconectadas de outras sessões em outros computadores.

No entanto, o `Connect-PSSession` não pode se conectar a sessões interrompidas ou fechadas, ou sessões interativas iniciadas usando o `Enter-PSSession` cmdlet. Além disso, não é possível conectar sessões a sessões iniciadas por outros usuários, a menos que você possa fornecer as credenciais do usuário que criou a sessão.

Para obter mais informações sobre o recurso de Sessões desconectadas, consulte [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: reconectar-se a uma sessão

```
PS C:\> Connect-PSSession -ComputerName Server01 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Opened        ITTasks                  Available
```

Esse comando se reconecta à sessão ITTask no computador Server01.

A saída mostra que o comando teve êxito. O **estado** da sessão é aberto e a **disponibilidade** está disponível, o que indica que você pode executar comandos na sessão.

### Exemplo 2: efeito de desconectar e reconectar

```
PS C:\> Get-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available


PS C:\> Get-PSSession | Disconnect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Disconnected  Microsoft.PowerShell          None


PS C:\> Get-PSSession | Connect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available
```

Este exemplo mostra o efeito de se desconectar e, em seguida, reconectar a uma sessão.

O primeiro comando usa o `Get-PSSession` cmdlet. Sem o parâmetro **ComputerName**, o comando obtém apenas as sessões que foram criadas na sessão atual.

A saída mostra que o comando obtém a sessão de Backups no computador local. O **estado** da sessão é aberto e a **disponibilidade** está disponível.

O segundo comando usa o `Get-PSSession` cmdlet para obter os objetos **PSSession** que foram criados na sessão atual e o `Disconnect-PSSession` cmdlet para desconectar as sessões. A saída mostra que a sessão de Backups foi desconectada. O **estado** da sessão está desconectado e a **disponibilidade** é nenhuma.

O terceiro comando usa o `Get-PSSession` cmdlet para obter os objetos **PSSession** que foram criados na sessão atual e o `Connect-PSSession` cmdlet para reconectar as sessões. A saída mostra que a sessão de Backups foi reconectada. O **estado** da sessão é aberto e a **disponibilidade** está disponível.

Se você usar o `Connect-PSSession` cmdlet em uma sessão que não está desconectada, o comando não afetará a sessão e não gerará nenhum erro.

### Exemplo 3: série de comandos em um cenário empresarial

Esta série de comandos mostra como o `Connect-PSSession` cmdlet pode ser usado em um cenário empresarial. Nesse caso, uma administradora do sistema inicia um trabalho de longa execução em uma sessão em um computador remoto. Após iniciar o trabalho, a administradora se desconecta da sessão e vai para casa.
Mais tarde, a noite, o administrador faz logon em seu computador doméstico e verifica se o trabalho foi executado até ser concluído.

O administrador começa criando sessões em um computador remoto e executando um script na sessão. O primeiro comando usa o `New-PSSession` cmdlet para criar a sessão ITTask no computador remoto Server01. O comando usa o parâmetro **ConfigurationName** para especificar a configuração da sessão ITTasks. O comando salva as sessões na `$s` variável.

O segundo cmdlet de comando `Invoke-Command` para iniciar um trabalho em segundo plano na sessão na `$s` variável. Ele usa o parâmetro **FilePath** para executar o script no trabalho em segundo plano.

O terceiro comando usa o `Disconnect-PSSession` cmdlet para se desconectar da sessão na `$s` variável. O comando usa o parâmetro **OutputBufferingMode** com um valor de Drop para impedir que o script seja bloqueado por precisar fornecer saída à sessão. Ele usa o parâmetro **IdleTimeoutSec** para estender o tempo limite da sessão para 15 horas. Quando o comando é concluído, o administrador bloqueia seu computador e entra em casa pela noite.

Mais tarde, a noite, o administrador inicia seu computador doméstico, faz logon na rede corporativa e inicia o PowerShell. O quarto comando usa o `Get-PSSession` cmdlet para obter as sessões no computador Server01. O comando localiza a sessão ITTask. O quinto comando usa o `Connect-PSSession` cmdlet para se conectar à sessão ITTask. O comando salva a sessão na variável `$s`.

O sexto comando usa o `Invoke-Command` cmdlet para executar um `Get-Job` comando na sessão na `$s` variável. A saída mostra que o trabalho foi concluído com êxito. O sétimo comando usa o `Invoke-Command` cmdlet para executar um `Receive-Job` comando na sessão na `$s` variável na sessão. O comando salva os resultados na `$BackupSpecs` variável. O oitavo comando usa o `Invoke-Command` cmdlet para executar outro script na sessão. O comando usa o valor da `$BackupSpecs` variável na sessão como entrada para o script.

```
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

O nono comando desconecta da sessão na `$s` variável. O administrador fecha o PowerShell e fecha o computador. Ela pode se reconectar à sessão no dia seguinte e verificar o status do script do seu computador de trabalho.

## PARAMETERS

### -AllowRedirection

Indica que esse cmdlet permite o redirecionamento dessa conexão para um URI alternativo.

Quando você usa o parâmetro **ConnectionURI**, o destino remoto pode retornar uma instrução para redirecionar para um URI diferente. Por padrão, o PowerShell não redireciona conexões, mas você pode usar esse parâmetro para permitir que ele redirecione a conexão.

É possível também limitar o número de vezes que a conexão é redirecionada alterando o valor da opção de sessão **MaximumConnectionRedirectionCount**. Use o parâmetro **MaximumRedirection** do `New-PSSessionOption` cmdlet ou defina a propriedade **MaximumConnectionRedirectionCount** da variável de preferência **$PSSessionOption** . O valor padrão é 5.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Especifica o nome de um aplicativo. Esse cmdlet se conecta somente a sessões que usam o aplicativo especificado.

Insira o segmento de nome de aplicativo do URI de conexão. Por exemplo, no seguinte URI de conexão, o nome do aplicativo é WSMan: `http://localhost:5985/WSMAN` . O nome de aplicativo de uma sessão é armazenado na propriedade **Runspace.ConnectionInfo.AppName** da sessão.

O valor desse parâmetro é usado para selecionar e filtrar sessões. Ele não altera o aplicativo utilizado pela sessão.

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Autenticação

Especifica o mecanismo usado para autenticar credenciais de usuário no comando para reconectar-se à sessão desconectada. Os valores aceitáveis para esse parâmetro são:

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
> A autenticação CredSSP (Credencial Security Support Provider), na qual as credenciais do usuário são passadas a um computador remoto para autenticação, foi projetada para comandos que exijam autenticação em mais de um recurso, como acessar um compartilhamento de rede remota. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para se conectar à sessão desconectada. Insira a impressão digital do certificado.

Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles podem ser mapeados somente para contas de usuário local. Eles não funcionam com contas de domínio.

Para obter uma impressão digital do certificado, use um `Get-Item` `Get-ChildItem` comando ou na unidade certificado do PowerShell:.

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Especifica os computadores nos quais as sessões desconectadas estão armazenadas. As sessões são armazenadas no computador que está no lado do servidor ou no fim do recebimento de uma conexão. O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador. Caracteres curinga não são permitidos. Para especificar o computador local, digite o nome do computador, localhost ou um ponto (.)

```yaml
Type: System.String[]
Parameter Sets: ComputerNameGuid, ComputerName
Aliases: Cn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName

Conecta-se somente a sessões que usam a configuração de sessão especificada.

Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão. Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/powershell` . O nome de configuração de uma sessão é armazenado na propriedade **ConfigurationName** da sessão.

O valor desse parâmetro é usado para selecionar e filtrar sessões. Ele não altera a configuração de sessão utilizada pela sessão.

Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Conexãouri

Especifica os URIs dos pontos de extremidade de conexão para as sessões desconectadas.

O URI deve ser totalmente qualificado. O formato dessa cadeia de caracteres é o seguinte:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

O valor padrão é o seguinte:

`http://localhost:5985/WSMAN`

Se você não especificar um URI de conexão, poderá usar os parâmetros **UseSSL** e **Port** para especificar os valores de URI de conexão.

Os valores válidos para o segmento **Transport** do URI são HTTP e HTTPS. Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas de padrões: 80 para HTTP e 443 para HTTPS. Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.

Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUriGuid, ConnectionUri
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para se conectar à sessão desconectada. O padrão é o usuário atual.

Digite um nome de usuário, como `User01` ou `Domain01\User01` , ou insira um `PSCredential` objeto gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, você será solicitado a inserir a senha.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Especifica as IDs das sessões desconectadas. O parâmetro **ID** só funcionará quando a sessão desconectada tiver sido conectada anteriormente à sessão atual.

Este parâmetro é válido, mas não é eficaz, quando a sessão está armazenada no computador local, mas não estava conectada à sessão atual.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Especifica as IDs de instância das sessões desconectadas.

A ID da instância é um GUID que identifica exclusivamente uma **PSSession** em um computador local ou remoto.

A ID da instância é armazenada na propriedade **InstanceId** da **PSSession**.

```yaml
Type: System.Guid[]
Parameter Sets: ComputerNameGuid, ConnectionUriGuid, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica os nomes amigáveis das sessões desconectadas.

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri
Aliases:

Required: True (Name), False (ComputerName, ConnectionUri)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Especifica a porta de rede no computador remoto que é usada para se reconectar à sessão. Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão. As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.

Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta. Para configurar o ouvinte, digite os dois comandos a seguir no prompt do PowerShell:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Não use o parâmetro **Port** a menos que seja necessário. A porta que está definida no comando se aplica a todos os computadores ou sessões em que o comando é executado. Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.

```yaml
Type: System.Int32
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessão

Especifica as sessões desconectadas. Insira uma variável que contém os objetos **PSSession** ou um comando que cria ou obtém os objetos **PSSession** , como um `Get-PSSession` comando.

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
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

Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se estiver definido. Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.

Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão. No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.

Para obter uma descrição das opções de sessão que incluem os valores padrão, consulte `New-PSSessionOption` . Para obter informações sobre a variável de preferência de **$PSSessionOption** , consulte [about_Preference_Variables](About/about_Preference_Variables.md). Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
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

### -UseSSL

Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para se conectar à sessão desconectada. Por padrão, SSL não é usado.

WS-Management criptografa todo o conteúdo do PowerShell transmitido pela rede. O parâmetro **UseSSL** é uma proteção adicional que envia os dados por uma conexão HTTPS em vez de uma conexão http.

Se você usar esse parâmetro, mas o SSL não estiver disponível na porta usada para o comando, o comando falhará.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameGuid, ComputerName
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

### System. Management. Automation. Runspaces. PSSession

Você pode canalizar uma sessão (**PSSession**) para este cmdlet.

## SAÍDAS

### System. Management. Automation. Runspaces. PSSession

Esse cmdlet retorna um objeto que representa a sessão à qual ele se reconecta.

## OBSERVAÇÕES

- Esse cmdlet só está disponível em plataformas Windows.

- `Connect-PSSession` reconecta-se somente a sessões desconectadas, ou seja, sessões que têm um valor de desconectado para a propriedade de **estado** . Somente as sessões que estão conectadas ou terminam em computadores que executam o Windows PowerShell 3,0 ou versões posteriores podem ser desconectadas e reconectadas.

- Se você usar `Connect-PSSession` o em uma sessão que não está desconectada, o comando não afetará a sessão e não gerará erros.

- Sessões de loopback desconectadas com tokens interativos, que são criadas usando o parâmetro **EnableNetworkAccess** , podem ser reconectadas somente do computador no qual a sessão foi criada. Essa restrição protege o computador contra acessos mal-intencionados.

- O valor da propriedade **State** de uma **PSSession** é relativo à sessão atual.
  Portanto, um valor de **desconectado** significa que a **PSSession** não está conectada à sessão atual. No entanto, isso não significa que a **PSSession** seja desconectada de todas as sessões. Ela pode ser conectada a uma sessão diferente. Para determinar se é possível conectar-se ou reconectar-se à sessão, utilize a propriedade **Availability**.

  Um valor **Availability** de None indica que é possível conectar-se à sessão. Um valor de ocupado indica que você não pode se conectar à **PSSession** porque ela está conectada a outra sessão.

  Para obter mais informações sobre os valores da propriedade **State** de sessões, consulte [Enumeração RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).

  Para obter mais informações sobre os valores da propriedade de sessões de **disponibilidade** , consulte [Enumeração RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).

- Não é possível alterar o valor de tempo limite ocioso de uma **PSSession** quando você se conecta à **PSSession**. O parâmetro **SessionOption** de `Connect-PSSession` usa um objeto **SessionOption** que tem um valor **IdleTimeout** . No entanto, o valor **IdleTimeout** do objeto **SessionOption** e o valor **IdleTimeout** da `$PSSessionOption` variável são ignorados ao se conectar a uma **PSSession**.

  Você pode definir e alterar o tempo limite de ociosidade de uma **PSSession** quando você cria a **PSSession**, usando os `New-PSSession` `Invoke-Command` cmdlets ou, e quando você se desconecta da **PSSession**.

  A propriedade **IdleTimeout** de uma **PSSession** é crítica para sessões desconectadas, pois determina por quanto tempo uma sessão desconectada é mantida no computador remoto. Sessões desconectadas são consideradas ociosas desde o momento em que são desconectadas, ainda que comandos estejam em execução na sessão desconectada.

## LINKS RELACIONADOS

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[Receive-PSSession](Receive-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Remove-PSSession](Remove-PSSession.md)
