---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSSession
ms.openlocfilehash: 9c08e78d840815a396b55eb26bf8e21d73cb81aa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598834"
---
# Enter-PSSession

## SINOPSE
Inicia uma sessão interativa com um computador remoto.

## SYNTAX

### ComputerName (padrão)

```
Enter-PSSession [-ComputerName] <String> [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL] [-ApplicationName <String>]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### SSHHost

```
Enter-PSSession [-HostName] <String> [-Port <Int32>] [-UserName <String>] [-KeyFilePath <String>]
 [-SSHTransport] [<CommonParameters>]
```

### Sessão

```
Enter-PSSession [[-Session] <PSSession>] [<CommonParameters>]
```

### Uri

```
Enter-PSSession [[-ConnectionUri] <Uri>] [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### InstanceId

```
Enter-PSSession [-InstanceId <Guid>] [<CommonParameters>]
```

### ID

```
Enter-PSSession [[-Id] <Int32>] [<CommonParameters>]
```

### Nome

```
Enter-PSSession [-Name <String>] [<CommonParameters>]
```

### VMId

```
Enter-PSSession [-VMId] <Guid> [-Credential] <PSCredential> [-ConfigurationName <String>] [<CommonParameters>]
```

### VMName

```
Enter-PSSession [-VMName] <String> [-Credential] <PSCredential> [-ConfigurationName <String>]
 [<CommonParameters>]
```

### ContainerId

```
Enter-PSSession [-ContainerId] <String> [-ConfigurationName <String>] [-RunAsAdministrator]
 [<CommonParameters>]
```

## DESCRIPTION

O `Enter-PSSession` cmdlet inicia uma sessão interativa com um único computador remoto.
Durante a sessão, os comandos digitados são executados no computador remoto, assim como se você estivesse digitando diretamente no computador remoto. Você pode ter somente uma sessão interativa por vez.

Normalmente, você usa o parâmetro **ComputerName** para especificar o nome do computador remoto.
No entanto, você também pode usar uma sessão que você cria usando o `New-PSSession` cmdlet para a sessão interativa. No entanto, você não pode usar os `Disconnect-PSSession` `Connect-PSSession` `Receive-PSSession` cmdlets, ou para se desconectar ou se conectar novamente a uma sessão interativa.

A partir do PowerShell 6,0, você pode usar Secure Shell (SSH) para estabelecer uma conexão com um computador remoto, se o SSH estiver disponível no computador local e o computador remoto estiver configurado com um ponto de extremidade SSH do PowerShell. O benefício de uma sessão remota do PowerShell baseada em SSH é que ela funciona em várias plataformas (Windows, Linux e macOS). Para a comunicação remota baseada em SSH, use o parâmetro **hostname** definido para especificar o computador remoto e as informações de conexão relevantes. Para obter mais informações sobre como configurar a comunicação remota do PowerShell SSH, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

Para encerrar a sessão interativa e desconectar-se do computador remoto, use o `Exit-PSSession` cmdlet ou digite `exit` .

## EXEMPLOS

### Exemplo 1: iniciar uma sessão interativa

```
PS> Enter-PSSession
[localhost]: PS>
```

Esse comando inicia uma sessão interativa no computador local. O prompt de comando é alterado para indicar que você está executando comandos em uma sessão diferente.

Os comandos que você inseriu são executados na nova sessão e os resultados são retornados à sessão padrão como texto.

### Exemplo 2: trabalhar com uma sessão interativa

O primeiro comando usa o `Enter-PSSession` cmdlet para iniciar uma sessão interativa com Server01, um computador remoto. Quando a sessão é iniciada, o prompt de comando é alterado para incluir o nome do computador.

O segundo comando obtém o processo do PowerShell e redireciona a saída para o arquivo Process.txt. O comando é enviado ao computador remoto e o arquivo é salvo no computador remoto.

O terceiro comando usa a palavra-chave **Exit** para encerrar a sessão interativa e fechar a conexão.
O quarto comando confirma que o arquivo Process.txt está no computador remoto. Um `Get-ChildItem` comando ("dir") no computador local não pode localizar o arquivo.

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS>
[Server01]: PS C:\> Get-Process PowerShell > C:\ps-test\Process.txt
[Server01]: PS C:\> exit
PS C:\>
PS C:\> dir C:\ps-test\process.txt
Get-ChildItem : Cannot find path 'C:\ps-test\process.txt' because it does not exist.
At line:1 char:4
+ dir <<<<  c:\ps-test\process.txt
```

Este comando mostra como trabalhar em uma sessão interativa com um computador remoto.

### Exemplo 3: usar o parâmetro Session

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
[Server01]: PS>
```

Esses comandos usam o parâmetro **Session** do `Enter-PSSession` para executar a sessão interativa em uma sessão existente do PowerShell (**PSSession**).

### Exemplo 4: iniciar uma sessão interativa e especificar os parâmetros de porta e de credencial

```powershell
PS> Enter-PSSession -ComputerName Server01 -Port 90 -Credential Domain01\User01
[Server01]: PS>
```

Esse comando inicia uma sessão interativa com o computador Server01. Ele usa o parâmetro **Port** para especificar a porta e o parâmetro **Credential** para especificar a conta de um usuário que tem permissão para se conectar ao computador remoto.

### Exemplo 5: parar uma sessão interativa

```powershell
PS> Enter-PSSession -ComputerName Server01
[Server01]: PS> Exit-PSSession
PS>
```

Este exemplo mostra como iniciar e interromper uma sessão interativa. O primeiro comando usa o `Enter-PSSession` cmdlet para iniciar uma sessão interativa com o computador Server01.

O segundo comando usa o `Exit-PSSession` cmdlet para encerrar a sessão. Você também pode usar a palavra-chave **Exit** para encerrar a sessão interativa. `Exit-PSSession` e **Exit** têm o mesmo efeito.

### Exemplo 6: iniciar uma sessão interativa usando SSH

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer01
```

Este exemplo mostra como iniciar uma sessão interativa usando o Secure Shell (SSH). Se o SSH estiver configurado no computador remoto para solicitar senhas, você receberá um prompt de senha.
Caso contrário, você precisará usar a autenticação de usuário baseada em chave SSH.

### Exemplo 7: iniciar uma sessão interativa usando SSH e especificar a porta e a chave de autenticação do usuário

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer02:22 -KeyFilePath c:\<path>\userAKey_rsa
```

Este exemplo mostra como iniciar uma sessão interativa usando SSH. Ele usa o parâmetro **Port** para especificar a porta a ser usada e o parâmetro **keyFilePath** para especificar uma chave RSA usada para autenticar o usuário no computador remoto.

## PARAMETERS

### -AllowRedirection

Permite o redirecionamento da conexão para um URI (Uniform Resource Identifier) alternativo. Por padrão, o redirecionamento não é permitido.

Quando você usa o parâmetro **ConnectionURI**, o destino remoto pode retornar uma instrução para redirecionar para um URI diferente. Por padrão, o PowerShell não redireciona conexões, mas você pode usar esse parâmetro para permitir que ele redirecione a conexão.

É possível também limitar o número de vezes que a conexão é redirecionada alterando o valor da opção de sessão **MaximumConnectionRedirectionCount**. Use o parâmetro **MaximumRedirection** do `New-PSSessionOption` cmdlet ou defina a propriedade **MaximumConnectionRedirectionCount** da variável de `$PSSessionOption` preferência. O valor padrão é 5.

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

O serviço **WinRM** usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão. O valor desse parâmetro deve corresponder ao valor da propriedade **URLPrefix** de um ouvinte no computador remoto.

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

Especifica o mecanismo usado para autenticar as credenciais do usuário. Os valores aceitáveis para esse parâmetro são:

- Padrão
- Básico
- CredSSP
- Digest
- Kerberos
- Negotiate
- NegotiateWithImplicitCredential

O valor padrão é Default.

A autenticação CredSSP está disponível somente no Windows Vista, no Windows Server 2008 e em versões posteriores do sistema operacional Windows.

Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationMechanism enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

Cuidado: a autenticação do Credential Security Support Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

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

Especifica um nome de computador. Esse cmdlet inicia uma sessão interativa com o computador remoto especificado. Digite apenas um nome de computador. O padrão é o computador local.

Digite o nome NetBIOS, o endereço IP ou o nome de domínio totalmente qualificado do computador. Você também pode canalizar um nome de computador para `Enter-PSSession` .

Para usar um endereço IP no valor do parâmetro **ComputerName** , o comando deve incluir o parâmetro **Credential** . Além disso, o computador deve ser configurado para o transporte HTTPS ou o endereço IP do computador remoto deve ser incluído na lista WinRM TrustedHosts no computador local. Para obter instruções sobre como adicionar um nome de computador à lista TrustedHosts, consulte "como adicionar um computador à lista de hosts confiáveis" em [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).

Observação: no Windows Vista e versões posteriores do sistema operacional Windows, para incluir o computador local no valor do parâmetro **ComputerName** , você deve iniciar o PowerShell com a opção Executar como administrador.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ConfigurationName

Especifica a configuração de sessão usada para a sessão interativa.

Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão. Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/powershell` .

Quando usado com SSH, isso especifica o subsistema a ser usado no destino, conforme definido em sshd_config. O valor padrão para SSH é o `powershell` subsistema.

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

Se não especificar um **ConnectionURI**, poderá usar os parâmetros **UseSSL**, **ComputerName**, **Port** e **ApplicationName** para especificar os valores do **ConnectionURI**.

Os valores válidos para o segmento Transport do URI são HTTP e HTTPS. Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada usando portas de padrões: 80 para HTTP e 443 para HTTPS. Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.

Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.

```yaml
Type: System.Uri
Parameter Sets: Uri
Aliases: URI, CU

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContainerId

Especifica a ID de um contêiner.

```yaml
Type: System.String
Parameter Sets: ContainerId
Aliases:

Required: True
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
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: 1
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableNetworkAccess

Indica que esse cmdlet adiciona um token de segurança interativo a sessões de loopback. O token interativo permite executar comandos na sessão de loopback que obtêm dados de outros computadores. Por exemplo, você pode executar um comando na sessão que copia arquivos XML de um computador remoto no computador local.

Uma sessão de loopback é uma **PSSession** originada e termina no mesmo computador. Para criar uma sessão de loopback, omita o parâmetro **ComputerName** ou defina seu valor como. (ponto), localhost ou o nome do computador local.

Por padrão, as sessões de loopback são criadas usando um token de rede, que pode não fornecer permissão suficiente para autenticar em computadores remotos.

O parâmetro **EnableNetworkAccess** só é eficaz em sessões de loopback. Se você usar **EnableNetworkAccess** ao criar uma sessão em um computador remoto, o comando terá sucesso, mas o parâmetro será ignorado.

Também é possível permitir o acesso remoto em uma sessão de loopback usando o valor **CredSSP** do parâmetro **Authentication**, que delega as credenciais de sessão a outros computadores.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName

Especifica um nome de computador para uma conexão baseada em Secure Shell (SSH). Isso é semelhante ao parâmetro **ComputerName** , exceto pelo fato de que a conexão com o computador remoto é feita usando SSH em vez de WinRM do Windows. Esse parâmetro dá suporte à especificação do nome de usuário e/ou porta como parte do valor do parâmetro de nome do host usando o formulário `user@hostname:port` . O nome de usuário e/ou a porta especificada como parte do nome do host tem precedência sobre os `-UserName` `-Port` parâmetros e, se especificado. Isso permite passar vários nomes de computador para esse parâmetro, em que alguns têm nomes de usuário e/ou portas específicos, enquanto outros usam o nome de usuário e/ou a porta dos `-UserName` `-Port` parâmetros e.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id

Especifica a ID de uma sessão existente. `Enter-PSSession` usa a sessão especificada para a sessão interativa.

Para localizar a ID de uma sessão, use o `Get-PSSession` cmdlet.

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Especifica a ID de instância de uma sessão existente. `Enter-PSSession` usa a sessão especificada para a sessão interativa.

A ID de instância é um GUID. Para localizar a ID de instância de uma sessão, use o `Get-PSSession` cmdlet. Você também pode usar os parâmetros de **sessão**, **nome** ou **ID** para especificar uma sessão existente. Ou, você pode usar o parâmetro **ComputerName** para iniciar uma sessão temporária.

```yaml
Type: System.Guid
Parameter Sets: InstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Especifica o nome amigável de uma sessão existente. `Enter-PSSession` usa a sessão especificada para a sessão interativa.

Se o nome que você especificou corresponder a mais de uma sessão, o comando falha. Você também pode usar os parâmetros **Session**, **InstanceId** ou **ID** para especificar uma sessão existente. Ou, você pode usar o parâmetro **ComputerName** para iniciar uma sessão temporária.

Para estabelecer um nome amigável para uma sessão, use o parâmetro **Name** do `New-PSSession` cmdlet.

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port

Especifica a porta de rede no computador remoto que é usada para este comando.

No PowerShell 6,0, esse parâmetro foi incluído no conjunto de parâmetros **hostname** que dá suporte a conexões Secure Shell (SSH).

**WinRM (conjunto de parâmetros ComputerName)**

Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão. As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.

Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta. Use os seguintes comandos para configurar o ouvinte:

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

Não use o parâmetro **Port** a menos que seja necessário. A configuração da porta no comando se aplica a todos os computadores ou sessões em que o comando for executado. Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.

**SSH (conjunto de parâmetros do nome do host)**

Para se conectar a um computador remoto, o computador remoto deve ser configurado com o serviço SSH (SSHD) e deve estar escutando na porta usada pela conexão. A porta padrão para SSH é 22.

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

Especifica uma sessão do PowerShell (**PSSession**) a ser usada para a sessão interativa. Esse parâmetro usa um objeto de sessão. Você também pode usar os parâmetros **Name**, **InstanceId** ou **ID** para especificar uma **PSSession**.

Insira uma variável que contenha um objeto de sessão ou um comando que cria ou Obtém um objeto de sessão, como um `New-PSSession` `Get-PSSession` comando ou. Também é possível canalizar um objeto de sessão para `Enter-PSSession` . Você pode enviar apenas uma **PSSession** usando esse parâmetro. Se você inserir uma variável que contenha mais de uma **PSSession**, o comando falhará.

Quando você usa `Exit-PSSession` o ou a palavra-chave **Exit** , a sessão interativa termina, mas a **PSSession** que você criou permanece aberta e disponível para uso.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionOption

Define opções avançadas para a sessão. Insira um objeto **SessionOption** , como um que você cria usando o `New-PSSessionOption` cmdlet ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.

Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se estiver definido. Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.

Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão. No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.

Para obter uma descrição das opções de sessão, incluindo os valores padrão, consulte `New-PSSessionOption` .
Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md). Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).

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

### -Subsistema

Especifica o subsistema SSH usado para a nova **PSSession**.

Isso especifica o subsistema a ser usado no destino, conforme definido em sshd_config. O subsistema inicia uma versão específica do PowerShell com parâmetros predefinidos. Se o subsistema especificado não existir no computador remoto, o comando falhará.

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

### -UserName

Especifica o nome de usuário para a conta usada para criar uma sessão no computador remoto. O método de autenticação de usuário dependerá de como o Secure Shell (SSH) está configurado no computador remoto.

Se o SSH estiver configurado para autenticação de senha básica, você será solicitado a fornecer a senha do usuário.

Se o SSH estiver configurado para a autenticação de usuário baseada em chave, um caminho de arquivo de chave poderá ser fornecido por meio do parâmetro **keyFilePath** e nenhum prompt de senha ocorrerá. Observe que, se o arquivo de chave de usuário do cliente estiver localizado em um local de SSH conhecido, o parâmetro **keyFilePath** não será necessário para a autenticação baseada em chave e a autenticação do usuário ocorrerá automaticamente com base no nome de usuário. Consulte a documentação do SSH sobre autenticação de usuário baseada em chave para obter mais informações.

Esse não é um parâmetro obrigatório. Se nenhum parâmetro **username** for especificado, o nome de usuário do logon atual será usado para a conexão.

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

Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para estabelecer uma conexão com o computador remoto. Por padrão, SSL não é usado.

WS-Management criptografa todo o conteúdo do PowerShell transmitido pela rede. O parâmetro **UseSSL** é uma proteção adicional que envia os dados por uma conexão HTTPS em vez de uma conexão http.

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

Especifica a ID de uma máquina virtual.

```yaml
Type: System.Guid
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VMName

Especifica o nome de uma máquina virtual.

```yaml
Type: System.String
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. String, System. Management. Automation. Runspaces. PSSession

É possível canalizar um nome de computador, como uma cadeia de caracteres ou um objeto de sessão para esse cmdlet.

## SAÍDAS

### Nenhum

O cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

Para se conectar a um computador remoto, você deve ser um membro do grupo Administradores no computador remoto. Para iniciar uma sessão interativa no computador local, você deve iniciar o PowerShell com a opção **Executar como administrador** .

Quando você usa o `Enter-PSSession` , seu perfil de usuário no computador remoto é usado para a sessão interativa. Os comandos no perfil de usuário remoto, incluindo comandos para adicionar módulos do PowerShell e para alterar o prompt de comando, são executados antes que o prompt remoto seja exibido.

`Enter-PSSession` usa a configuração de cultura da interface do usuário no computador local para a sessão interativa. Para localizar a cultura da interface do usuário local, use a `$UICulture` variável automática.

`Enter-PSSession` requer os `Get-Command` `Out-Default` `Exit-PSSession` cmdlets, e. Se esses cmdlets não estiverem incluídos na configuração de sessão no computador remoto, os `Enter-PSSession` comandos falharão.

Ao contrário de `Invoke-Command` , que analisa e interpreta os comandos antes de enviá-los para o computador remoto, `Enter-PSSession` o envia os comandos diretamente para o computador remoto sem interpretação.

Se a sessão que você deseja inserir estiver ocupada processando um comando, pode haver um atraso antes que o PowerShell responda ao `Enter-PSSession` comando. Você está conectado assim que a sessão está disponível. Para cancelar o `Enter-PSSession` comando, pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>.

O parâmetro **hostname** definido foi incluído a partir do PowerShell 6,0. Ele foi adicionado para fornecer comunicação remota do PowerShell com base em Secure Shell (SSH). Tanto o SSH quanto o PowerShell têm suporte em várias plataformas (Windows, Linux, macOS) e a comunicação remota do PowerShell funcionará nessas plataformas nas quais o PowerShell e o SSH estão instalados e configurados. Isso é separado da somente comunicação remota do Windows anterior, que é baseada no WinRM, e que muitos dos recursos e limitações específicos do WinRM não se aplicam. Por exemplo, cotas baseadas em WinRM, opções de sessão, configuração de ponto de extremidade personalizado e recursos de desconexão/reconexão não têm suporte no momento. Para obter mais informações sobre como configurar a comunicação remota do PowerShell SSH, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

Antes do PowerShell 7.1, a comunicação remota por SSH não dava suporte a sessões remotas de segundo salto. Essa funcionalidade estava limitada a sessões que usavam o WinRM. O PowerShell 7.1 permite que `Enter-PSSession` e `Enter-PSHostProcess` funcionem em qualquer sessão remota interativa.

## LINKS RELACIONADOS

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[about_PSSessions](About/about_PSSessions.md)

[about_Remote](About/about_Remote.md)
