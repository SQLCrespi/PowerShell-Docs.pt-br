---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSession
ms.openlocfilehash: e5dedf3d161f2687bddfbd09740812d8c5cbaa77
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93195027"
---
# New-PSSession

## SINOPSE
Cria uma conexão persistente para um computador local ou remoto.

## SYNTAX

### ComputerName (padrão)

```
New-PSSession [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Name <String[]>]
 [-EnableNetworkAccess] [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### Uri

```
New-PSSession [-Credential <PSCredential>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### VMId

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 [-VMId] <Guid[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### VMName

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 -VMName <String[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### Session

```
New-PSSession [[-Session] <PSSession[]>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### ContainerId

```
New-PSSession [-Name <String[]>] [-ConfigurationName <String>] -ContainerId <String[]>
 [-RunAsAdministrator] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### UseWindowsPowerShellParameterSet

```
New-PSSession [-Name <String[]>] [-UseWindowsPowerShell] [<CommonParameters>]
```

### SSHHost

```
New-PSSession [-Name <String[]>] [-Port <Int32>] [-HostName] <String[]> [-UserName <String>]
 [-KeyFilePath <String>] [-SSHTransport] [-Subsystem <String>] [<CommonParameters>]
```

### SSHHostHashParam

```
New-PSSession [-Name <String[]>] -SSHConnection <Hashtable[]> [<CommonParameters>]
```

## DESCRIPTION

O `New-PSSession` cmdlet cria uma sessão do PowerShell ( **PSSession** ) em um computador local ou remoto. Quando você cria uma **PSSession** , o PowerShell estabelece uma conexão persistente com o computador remoto.

Use uma **PSSession** para executar vários comandos que compartilham dados, como uma função ou o valor de uma variável. Para executar comandos em uma **PSSession** , use o `Invoke-Command` cmdlet. Para usar a **PSSession** para interagir diretamente com um computador remoto, use o `Enter-PSSession` cmdlet. Para obter mais informações, consulte [about_PSSessions](about/about_PSSessions.md).

Você pode executar comandos em um computador remoto sem criar uma **PSSession** usando os parâmetros **ComputerName** de `Enter-PSSession` ou `Invoke-Command` . Quando você usa o parâmetro **ComputerName** , o PowerShell cria uma conexão temporária que é usada para o comando e, em seguida, é fechada.

A partir do PowerShell 6,0, você pode usar Secure Shell (SSH) para estabelecer uma conexão com o e criar uma sessão em um computador remoto, se o SSH estiver disponível no computador local e o computador remoto estiver configurado com um ponto de extremidade SSH do PowerShell. O benefício de uma sessão remota do PowerShell baseada em SSH é que ela pode funcionar em várias plataformas (Windows, Linux e macOS). Para sessões baseadas em SSH, use o parâmetro **hostname** ou **SSHConnection** definido para especificar o computador remoto e as informações de conexão relevantes. Para obter mais informações sobre como configurar a comunicação remota do PowerShell SSH, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

> [!NOTE]
> Ao usar a comunicação remota do WSMan em um cliente Linux ou macOS com um ponto de extremidade HTTPS em que o certificado do servidor não é confiável (por exemplo, um certificado autoassinado). Você deve fornecer um `PSSessionOption` que inclui `-SkipCACheck` e `-SkipCNCheck` para estabelecer a conexão com êxito. Faça isso apenas se você estiver em um ambiente em que você pode ter certeza do certificado do servidor e da conexão de rede com o sistema de destino.

## EXEMPLOS

### Exemplo 1: criar uma sessão no computador local

```powershell
$s = New-PSSession
```

Esse comando cria uma nova **PSSession** no computador local e salva a **PSSession** na `$s` variável.

Agora você pode usar esta **PSSession** para executar comandos no computador local.

### Exemplo 2: criar uma sessão em um computador remoto

```powershell
$Server01 = New-PSSession -ComputerName Server01
```

Esse comando cria uma nova **PSSession** no computador Server01 e salva-a na `$Server01` variável.

Ao criar vários objetos **PSSession** , atribua-os a variáveis com nomes úteis. Isso ajudará você a gerenciar os objetos **PSSession** em comandos subsequentes.

### Exemplo 3: criar sessões em vários computadores

```powershell
$s1, $s2, $s3 = New-PSSession -ComputerName Server01,Server02,Server03
```

Esse comando cria três objetos **PSSession** , um em cada um dos computadores especificados pelo parâmetro **ComputerName** .

O comando usa o operador de atribuição (=) para atribuir os novos objetos **PSSession** às variáveis: `$s1` , `$s2` , `$s3` . Ele atribui a **PSSession** Server01 a `$s1` , a **PSSession** Server02 `$s2` e a Server03 **PSSession** para `$s3` .

Quando você atribui vários objetos a uma série de variáveis, o PowerShell atribui cada objeto a uma variável na série, respectivamente. Se houver mais objetos que variáveis, todos os objetos restantes serão atribuídos à última variável. Se houver mais variáveis que objetos, as variáveis restantes ficarão vazias (nulas).

### Exemplo 4: criar uma sessão com uma porta especificada

```powershell
New-PSSession -ComputerName Server01 -Port 8081 -UseSSL -ConfigurationName E12
```

Este comando cria uma nova **PSSession** no computador Server01 que se conecta à porta do servidor 8081 e usa o protocolo SSL. A nova **PSSession** usa uma configuração de sessão alternativa chamada E12.

Antes de configurar a porta, você deve configurar o ouvinte WinRM no computador remoto para escutar na porta 8081. Para obter mais informações, consulte a descrição do parâmetro **Port** .

### Exemplo 5: criar uma sessão com base em uma sessão existente

```powershell
New-PSSession -Session $s -Credential Domain01\User01
```

Este comando cria uma **PSSession** com as mesmas propriedades de uma **PSSession** existente. Você pode usar esse formato de comando quando os recursos de uma **PSSession** existente são esgotados e uma nova **PSSession** é necessária para descarregar parte da demanda.

O comando usa o parâmetro **Session** de `New-PSSession` para especificar a **PSSession** salva na `$s` variável. Ele usa as credenciais do usuário Domain1\Admin01 para concluir o comando.

### Exemplo 6: criar uma sessão com um escopo global em um domínio diferente

```powershell
$global:s = New-PSSession -ComputerName Server1.Domain44.Corpnet.Fabrikam.com -Credential Domain01\Admin01
```

Este exemplo mostra como criar uma **PSSession** com um escopo global em um computador em um domínio diferente.

Por padrão, os objetos **PSSession** criados na linha de comando são criados com o escopo local e os objetos **PSSession** criados em um script têm escopo de script.

Para criar uma **PSSession** com escopo global, crie uma nova **PSSession** e, em seguida, armazene a **PSSession** em uma variável que é convertida em um escopo global. Nesse caso, a `$s` variável é convertida em um escopo global.

O comando usa o parâmetro **ComputerName** para especificar o computador remoto. Como o computador está em um domínio diferente da conta de usuário, o nome completo do computador é especificado junto com as credenciais do usuário.

### Exemplo 7: criar sessões para muitos computadores

```powershell
$rs = Get-Content C:\Test\Servers.txt | New-PSSession -ThrottleLimit 50
```

Esse comando cria uma **PSSession** em cada um dos computadores 200 listados no arquivo Servers.txt e armazena a **PSSession** resultante na `$rs` variável. Os objetos **PSSession** têm um limite de limitação de 50.

Você pode usar esse formato de comando quando os nomes dos computadores são armazenados em um banco de dados, arquivo de texto, planilha ou outro formato convertível em texto.

### Exemplo 8: criar uma sessão usando um URI

```powershell
$s = New-PSSession -URI http://Server01:91/NewSession -Credential Domain01\User01
```

Esse comando cria uma **PSSession** no computador Server01 e a armazena na `$s` variável. Ele usa o parâmetro **URI** para especificar o protocolo de transporte, o computador remoto, a porta e uma configuração de sessão alternativa. Ele também usa o parâmetro **Credential** para especificar uma conta de usuário que tenha permissão para criar uma sessão no computador remoto.

### Exemplo 9: executar um trabalho em segundo plano em um conjunto de sessões

```powershell
$s = New-PSSession -ComputerName (Get-Content Servers.txt) -Credential Domain01\Admin01 -ThrottleLimit 16
Invoke-Command -Session $s -ScriptBlock {Get-Process PowerShell} -AsJob
```

Esses comandos criam um conjunto de objetos **PSSession** e, em seguida, executam um trabalho em segundo plano em cada um dos objetos **PSSession** .

O primeiro comando cria uma nova **PSSession** em cada um dos computadores listados no arquivo Servers.txt. Ele usa o `New-PSSession` cmdlet para criar a **PSSession** . O valor do parâmetro **ComputerName** é um comando que usa o `Get-Content` cmdlet para obter a lista de nomes de computador que o arquivo Servers.txt.

O comando usa o parâmetro **Credential** para criar os objetos **PSSession** que têm a permissão de um administrador de domínio e ele usa o parâmetro **ThrottleLimit** para limitar o comando a 16 conexões simultâneas. O comando salva os objetos **PSSession** na `$s` variável.

O segundo comando usa o parâmetro **AsJob** do `Invoke-Command` cmdlet para iniciar um trabalho em segundo plano que executa um `Get-Process PowerShell` comando em cada um dos objetos **PSSession** no `$s` .

Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](About/about_Jobs.md) e [about_Remote_Jobs](About/about_Remote_Jobs.md).

### Exemplo 10: criar uma sessão para um computador usando seu URI

```powershell
New-PSSession -ConnectionURI https://management.exchangelabs.com/Management
```

Este comando cria objetos **PSSession** que se conectam a um computador especificado por um URI em vez de um nome de computador.

### Exemplo 11: criar uma opção de sessão

```powershell
$so = New-PSSessionOption -SkipCACheck
New-PSSession -ConnectionUri https://management.exchangelabs.com/Management -SessionOption $so -Credential Server01\Admin01
```

Este exemplo mostra como criar um objeto de opção de sessão e usar o parâmetro **SessionOption** .

O primeiro comando usa o `New-PSSessionOption` cmdlet para criar uma opção de sessão. Ele salva o objeto **SessionOption** resultante na `$so` variável.

O segundo comando usa a opção em uma nova sessão. O comando usa o `New-PSSession` cmdlet para criar uma nova sessão. O valor do parâmetro SessionOption é o objeto **SessionOption** na `$so` variável.

### Exemplo 12: criar uma sessão usando SSH

```powershell
New-PSSession -HostName UserA@LinuxServer01
```

Este exemplo mostra como criar uma nova **PSSession** usando Secure Shell (SSH). Se o SSH estiver configurado no computador remoto para solicitar senhas, você receberá um prompt de senha. Caso contrário, você precisará usar a autenticação de usuário baseada em chave SSH.

### Exemplo 13: criar uma sessão usando SSH e especificar a porta e a chave de autenticação do usuário

```powershell
New-PSSession -HostName UserA@LinuxServer01:22 -KeyFilePath c:\<path>\userAKey_rsa
```

Este exemplo mostra como criar uma **PSSession** usando Secure Shell (SSH). Ele usa o parâmetro **Port** para especificar a porta a ser usada e o parâmetro **keyFilePath** para especificar uma chave RSA usada para identificar e autenticar o usuário no computador remoto.

### Exemplo 14: criar várias sessões usando SSH

```powershell
$sshConnections = @{ HostName="WinServer1"; UserName="domain\userA"; KeyFilePath="c:\users\UserA\id_rsa" }, @{ HostName="UserB@LinuxServer5"; KeyFilePath="c:\UserB\<path>\id_rsa" }
New-PSSession -SSHConnection $sshConnections
```

Este exemplo mostra como criar várias sessões usando Secure Shell (SSH) e o conjunto de parâmetros **SSHConnection** . O parâmetro **SSHConnection** usa uma matriz de tabelas de hash que contêm informações de conexão para cada sessão. Observe que este exemplo requer que os computadores remotos de destino tenham o SSH configurado para dar suporte à autenticação de usuário baseada em chave.

## PARAMETERS

### -AllowRedirection

Indica que esse cmdlet permite o redirecionamento dessa conexão para um Uniform Resource Identifier alternativo (URI).

Quando você usa o parâmetro **ConnectionURI** , o destino remoto pode retornar uma instrução para redirecionar para um URI diferente. Por padrão, o PowerShell não redireciona conexões, mas você pode usar esse parâmetro para habilitá-la a redirecionar a conexão.

É possível também limitar o número de vezes que a conexão é redirecionada alterando o valor da opção de sessão **MaximumConnectionRedirectionCount** . Use o parâmetro **MaximumRedirection** do `New-PSSessionOption` cmdlet ou defina a propriedade **MaximumConnectionRedirectionCount** da variável de preferência **$PSSessionOption** . O valor padrão é 5.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Especifica o segmento de nome de aplicativo do URI de conexão. Use esse parâmetro para especificar o nome do aplicativo quando não estiver usando o parâmetro **ConnectionURI** no comando.

O valor padrão é o valor da `$PSSessionApplicationName` variável de preferência no computador local. Se esta variável de preferência não estiver definida, o valor padrão é WSMAN. Esse valor é adequado para a maioria dos usos. Para obter mais informações, consulte [about_Preference_Variables](About/about_Preference_Variables.md).

O serviço WinRM usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão.
O valor desse parâmetro deve corresponder ao valor da propriedade **URLPrefix** de um ouvinte no computador remoto.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Autenticação

Especifica o mecanismo usado para autenticar as credenciais do usuário.
Os valores aceitáveis para esse parâmetro são:

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
Parameter Sets: ComputerName, Uri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação. Insira a impressão digital do certificado.

Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.

Para obter um certificado, use o `Get-Item` `Get-ChildItem` comando ou na unidade de certificado do PowerShell:.

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Especifica uma matriz de nomes de computadores. Esse cmdlet cria uma conexão persistente ( **PSSession** ) para o computador especificado. Se você inserir vários nomes de computador, o `New-PSSession` criará vários objetos **PSSession** , um para cada computador. O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores remotos. Para especificar o computador local, digite o nome do computador, localhost ou um ponto (.). Quando o computador está em um domínio diferente do usuário, é necessário o nome de domínio totalmente qualificado. Também é possível canalizar um nome de computador, entre aspas, para `New-PSSession` .

Para usar um endereço IP no valor do parâmetro **ComputerName** , o comando deve incluir o parâmetro **Credential** . Além disso, o computador deve ser configurado para o transporte HTTPS ou o endereço IP do computador remoto deve ser incluído na lista WinRM TrustedHosts no computador local. Para obter instruções sobre como adicionar um nome de computador à lista TrustedHosts, consulte "como adicionar um computador à lista de hosts confiáveis" em [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).

Para incluir o computador local no valor do parâmetro **ComputerName** , inicie o Windows PowerShell usando a opção Executar como administrador.

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ConfigurationName

Especifica a configuração de sessão que é usada para a nova **PSSession** .

Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão. Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/PowerShell` .

A configuração da sessão para uma sessão está localizada no computador remoto. Se a configuração de sessão especificada não existir no computador remoto, o comando falhará.

O valor padrão é o valor da `$PSSessionConfigurationName` variável de preferência no computador local. Se esta variável de preferência não for definida, o padrão é Microsoft. Para obter mais informações, consulte [about_Preference_Variables](About/about_Preference_Variables.md).

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri, VMId, VMName, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Conexãouri

Especifica um URI que define o ponto de extremidade de conexão para a sessão. O URI deve ser totalmente qualificado. O formato dessa cadeia de caracteres é o seguinte:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

O valor padrão é o seguinte:

`http://localhost:5985/WSMAN`

Se não especificar um **ConnectionURI** , poderá usar os parâmetros **UseSSL** , **ComputerName** , **Port** e **ApplicationName** para especificar os valores do **ConnectionURI** .

Os valores válidos para o segmento Transport do URI são HTTP e HTTPS. Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas de padrões: 80 para HTTP e 443 para HTTPS. Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.

Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.

```yaml
Type: System.Uri[]
Parameter Sets: Uri
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContainerId

Especifica uma matriz de IDs de contêineres. Esse cmdlet inicia uma sessão interativa com cada um dos contêineres especificados. Use o `docker ps` comando para obter uma lista de IDs de contêiner. Para obter mais informações, consulte a ajuda para o comando [Docker PS](https://docs.docker.com/engine/reference/commandline/ps/) .

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableNetworkAccess

Indica que esse cmdlet adiciona um token de segurança interativo a sessões de loopback. O token interativo permite executar comandos na sessão de loopback que obtêm dados de outros computadores. Por exemplo, você pode executar um comando na sessão que copia arquivos XML de um computador remoto no computador local.

Uma sessão de loopback é uma **PSSession** originada e termina no mesmo computador. Para criar uma sessão de loopback, omita o parâmetro **ComputerName** ou defina seu valor como ponto (.), localhost ou o nome do computador local.

Por padrão, esse cmdlet cria sessões de loopback usando um token de rede, que pode não fornecer permissão suficiente para autenticar em computadores remotos.

O parâmetro **EnableNetworkAccess** só é eficaz em sessões de loopback. Se você usar **EnableNetworkAccess** ao criar uma sessão em um computador remoto, o comando terá sucesso, mas o parâmetro será ignorado.

Você também pode habilitar o acesso remoto em uma sessão de loopback usando o valor CredSSP do parâmetro de **autenticação** , que delega as credenciais de sessão para outros computadores.

Para proteger o computador contra acesso mal-intencionado, as sessões de loopback desconectadas que têm tokens interativos, que são aquelas criadas usando o parâmetro **EnableNetworkAccess** , podem ser reconectadas somente do computador no qual a sessão foi criada. Sessões desconectadas que usam a autenticação CredSSP podem ser reconectadas por meio de outros computadores. Para obter mais informações, consulte `Disconnect-PSSession`.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri, Session
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName

Especifica uma matriz de nomes de computador para uma conexão baseada em Secure Shell (SSH). Isso é semelhante ao parâmetro ComputerName, exceto pelo fato de que a conexão com o computador remoto é feita usando SSH em vez de WinRM do Windows.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.String[]
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyFilePath

Especifica um caminho de arquivo de chave usado pelo Secure Shell (SSH) para autenticar um usuário em um computador remoto.

O SSH permite que a autenticação do usuário seja executada por meio de chaves privadas/públicas como uma alternativa à autenticação básica de senha. Se o computador remoto estiver configurado para autenticação de chave, esse parâmetro poderá ser usado para fornecer a chave que identifica o usuário.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica um nome amigável para a **PSSession** .

Você pode usar o nome para se referir à **PSSession** quando usar outros cmdlets, como `Get-PSSession` e `Enter-PSSession` . Não é necessário que o nome do computador ou da sessão atual seja exclusivo.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Especifica a porta de rede no computador remoto que é usada para esta conexão. Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão. As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.

Antes de usar outra porta, você deve configurar o ouvinte do WinRM no computador remoto para escutar nessa porta. Use os seguintes comandos para configurar o ouvinte:

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

Não use o parâmetro **Port** a menos que seja necessário. A configuração da porta no comando se aplica a todos os computadores ou sessões em que o comando for executado. Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.

```yaml
Type: System.Int32
Parameter Sets: ComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsAdministrator

Indica que a **PSSession** é executada como administrador.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessão

Especifica uma matriz de objetos **PSSession** que esse cmdlet usa como um modelo para a nova **PSSession** . Esse parâmetro cria novos objetos **PSSession** que têm as mesmas propriedades que os objetos **PSSession** especificados.

Insira uma variável que contém os objetos **PSSession** ou um comando que cria ou obtém os objetos **PSSession** , como um `New-PSSession` comando ou `Get-PSSession` .

Os objetos **PSSession** resultantes têm o mesmo nome do computador, nome do aplicativo, URI de conexão, porta, nome de configuração, limite de limitação e valor de protocolo SSL (SSL) como os originais, mas têm um nome de exibição diferente, ID e ID de instância (GUID).

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionOption

Especifica as opções avançadas para a sessão. Insira um objeto **SessionOption** , como um que você cria usando o `New-PSSessionOption` cmdlet ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.

Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se estiver definido. Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.

Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão. No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.

Para obter uma descrição das opções de sessão que incluem os valores padrão, consulte `New-PSSessionOption` . Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md). Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SSHConnection

Esse parâmetro usa uma matriz de Hashtables em que cada Hashtable contém um ou mais parâmetros de conexão necessários para estabelecer uma conexão de Secure Shell (SSH) (nome do host, porta, nome de usuário, keyFilePath).

Os parâmetros de conexão da tabela de hash são os mesmos definidos para o conjunto de parâmetros **hostname** .

O parâmetro **SSHConnection** é útil para criar várias sessões em que cada sessão requer informações de conexão diferentes.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SSHHostHashParam
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SSHTransport

Indica que a conexão remota é estabelecida usando Secure Shell (SSH).

Por padrão, o PowerShell usa o Windows WinRM para se conectar a um computador remoto. Essa opção força o PowerShell a usar o parâmetro HostName definido para estabelecer uma conexão remota com base em SSH.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.
Se você omitir esse parâmetro ou digitar o valor 0 (zero), o valor padrão, 32, será usado.

O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.

```yaml
Type: System.Int32
Parameter Sets: ComputerName, Uri, VMId, VMName, Session, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName

Especifica o nome de usuário para a conta usada para criar uma sessão no computador remoto. O método de autenticação de usuário dependerá de como o Secure Shell (SSH) está configurado no computador remoto.

Se o SSH estiver configurado para autenticação de senha básica, você será solicitado a fornecer a senha do usuário.

Se o SSH estiver configurado para a autenticação de usuário baseada em chave, um caminho de arquivo de chave poderá ser fornecido por meio do parâmetro keyFilePath e nenhum prompt de senha ocorrerá. Observe que, se o arquivo de chave de usuário do cliente estiver localizado em um local de SSH conhecido, o parâmetro keyFilePath não será necessário para a autenticação baseada em chave e a autenticação do usuário ocorrerá automaticamente com base no nome de usuário. Consulte a documentação do SSH sobre autenticação de usuário baseada em chave para obter mais informações.

Esse não é um parâmetro obrigatório. Se nenhum parâmetro UserName for especificado, o nome de usuário do logon atual será usado para a conexão.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

Indica que esse cmdlet usa o protocolo SSL para estabelecer uma conexão com o computador remoto.
Por padrão, SSL não é usado.

WS-Management criptografa todo o conteúdo do PowerShell transmitido pela rede. O parâmetro **UseSSL** oferece uma proteção adicional que envia os dados por uma conexão HTTPS em vez de uma conexão http.

Se você usar esse parâmetro, mas o SSL não estiver disponível na porta usada para o comando, o comando falhará.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMId

Especifica uma matriz de ID de máquinas virtuais. Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas. Para ver as máquinas virtuais que estão disponíveis para você, use o seguinte comando:

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName

Especifica uma matriz de nomes de máquinas virtuais. Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas. Para ver as máquinas virtuais que estão disponíveis para você, use o `Get-VM` cmdlet.

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subsistema

Especifica o subsistema SSH usado para a nova **PSSession** .

Isso especifica o subsistema a ser usado no destino, conforme definido em sshd_config.
O subsistema inicia uma versão específica do PowerShell com parâmetros predefinidos.
Se o subsistema especificado não existir no computador remoto, o comando falhará.

Se esse parâmetro não for usado, o padrão será o subsistema ' PowerShell '.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseWindowsPowerShell

{{Descrição de UseWindowsPowerShell de preenchimento}}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseWindowsPowerShellParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. String, System. URI, System. Management. Automation. Runspaces. PSSession

É possível canalizar uma cadeia de caracteres, um URI ou um objeto de sessão para esse cmdlet.

## SAÍDAS

### System. Management. Automation. Runspaces. PSSession

## OBSERVAÇÕES

- Esse cmdlet usa a infraestrutura de comunicação remota do PowerShell. Para usar esse cmdlet, o computador local e os computadores remotos devem ser configurados para a comunicação remota do PowerShell. Para obter mais informações, consulte [about_Remote_Requirements](About/about_Remote_Requirements.md).
- Para criar uma **PSSession** no computador local, inicie o PowerShell com a opção Executar como administrador.
- Quando você terminar com a **PSSession** , use o `Remove-PSSession` cmdlet para excluir a **PSSession** e liberar seus recursos.
- Os conjuntos de parâmetros **hostname** e **SSHConnection** foram incluídos a partir do PowerShell 6,0.
  Elas foram adicionadas para fornecer comunicação remota do PowerShell com base em Secure Shell (SSH). Tanto o SSH quanto o PowerShell têm suporte em várias plataformas (Windows, Linux, macOS) e a comunicação remota do PowerShell funcionará nessas plataformas nas quais o PowerShell e o SSH estão instalados e configurados. Isso é separado da somente comunicação remota do Windows anterior, que é baseada no WinRM, e que muitos dos recursos e limitações específicos do WinRM não se aplicam. Por exemplo, cotas baseadas em WinRM, opções de sessão, configuração de ponto de extremidade personalizado e recursos de desconexão/reconexão não têm suporte no momento. Para obter mais informações sobre como configurar a comunicação remota do PowerShell SSH, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

## LINKS RELACIONADOS

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[Receive-PSSession](Receive-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)

