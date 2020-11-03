---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSession
ms.openlocfilehash: c9c927ccdbc70d07ad8fa2cf13f3e2fe4a83f8c5
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194888"
---
# Get-PSSession

## SINOPSE
Obtém as sessões do PowerShell em computadores locais e remotos.

## SYNTAX

### Nome (padrão)

```
Get-PSSession [-Name <String[]>] [<CommonParameters>]
```

### ComputerName

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### ComputerInstanceId

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### ConnectionUriInstanceId

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] -InstanceId <Guid[]>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### ConnectionUri

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### ContainerId

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### ContainerIdInstanceId

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### VMId

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### VMIdInstanceId

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### VMName

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMName <String[]>
 [<CommonParameters>]
```

### VMNameInstanceId

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -VMName <String[]> [<CommonParameters>]
```

### InstanceId

```
Get-PSSession [-InstanceId <Guid[]>] [<CommonParameters>]
```

### ID

```
Get-PSSession [-Id] <Int32[]> [<CommonParameters>]
```

## DESCRIPTION

O `Get-PSSession` cmdlet obtém as sessões do PowerShell gerenciadas pelo usuário ( **PSSessions** ) em computadores locais e remotos.

A partir do Windows PowerShell 3,0, as sessões são armazenadas nos computadores na extremidade remota de cada conexão. Você pode usar os parâmetros **ComputerName** ou **conexãouri** do `Get-PSSession` para obter as sessões que se conectam ao computador local ou a computadores remotos, mesmo que eles não tenham sido criados na sessão atual.

Sem parâmetros, `Get-PSSession` obtém todas as sessões que foram criadas na sessão atual.

Use os parâmetros de filtragem, incluindo **Name** , **ID** , **InstanceId** , **State** , **ApplicationName** e **ConfigurationName** para selecionar entre as sessões que `Get-PSSession` retorna.

Use os parâmetros restantes para configurar a conexão temporária na qual o `Get-PSSession` comando é executado quando você usa os parâmetros **ComputerName** ou **conexãouri** .

Observação: no Windows PowerShell 2,0, sem parâmetros, `Get-PSSession` obtém todas as sessões que foram criadas na sessão atual. O parâmetro **ComputerName** Obtém as sessões que foram criadas na sessão atual e se conecta ao computador especificado.

Para obter mais informações sobre sessões do PowerShell, consulte [about_PSSessions](about/about_PSSessions.md).

## EXEMPLOS

### Exemplo 1: obter sessões criadas na sessão atual

```powershell
Get-PSSession
```

Esse comando obtém todas as **PSSessions** que foram criadas na sessão atual. Ele não obtém **PSSessions** que foram criadas em outras sessões ou em outros computadores, mesmo que se conectem a este computador.

### Exemplo 2: obter sessões conectadas ao computador local

```powershell
Get-PSSession -ComputerName "localhost"
```

Esse comando obtém as **PSSessions** que estão conectadas ao computador local. Para indicar o computador local, digite o nome do computador, localhost ou um ponto (.)

O comando retorna todas as sessões no computador local, mesmo que elas tenham sido criadas em sessões ou em computadores diferentes.

### Exemplo 3: obter sessões conectadas a um computador

```powershell
Get-PSSession -ComputerName "Server02"
```

```Output
 Id Name            ComputerName    State         ConfigurationName     Availability
 -- ----            ------------    -----         -----------------     ------------
  2 Session3        Server02       Disconnected  ITTasks                       Busy
  1 ScheduledJobs   Server02       Opened        Microsoft.PowerShell     Available
  3 Test            Server02       Disconnected  Microsoft.PowerShell          Busy
```

Esse comando obtém as **PSSessions** que estão conectadas ao computador Server02.

O comando retorna todas as sessões em Server02, mesmo que elas tenham sido criadas em sessões ou em computadores diferentes.

A saída mostra que duas das sessões têm o estado de Desconectado e a disponibilidade de Ocupado. Elas foram criadas em sessões diferentes e estão em uso atualmente. A sessão ScheduledJobs, que está aberta e disponível, foi criada na sessão atual.

### Exemplo 4: salvar os resultados deste comando

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
$s1, $s2, $s3 = Get-PSSession
```

Este exemplo mostra como salvar os resultados de um `Get-PSSession` comando em várias variáveis.

O primeiro comando usa o `New-PSSession` cmdlet para criar **PSSessions** em três computadores remotos.

O segundo comando usa um `Get-PSSession` cmdlet para obter as três **PSSessions** . Em seguida, ele salva cada uma das **PSSessions** em uma variável separada.

Quando o PowerShell atribui uma matriz de objetos a uma matriz de variáveis, ele atribui o primeiro objeto à primeira variável, o segundo objeto à segunda variável e assim por diante. Se houver mais objetos que variáveis, ele atribui todos os objetos restantes à última variável da matriz. Se houver mais variáveis que objetos, as variáveis extra não são usadas.

### Exemplo 5: excluir uma sessão usando uma ID de instância

```powershell
Get-PSSession | Format-Table -Property ComputerName, InstanceID
$s = Get-PSSession -InstanceID a786be29-a6bb-40da-80fb-782c67f7db0f
Remove-PSSession -Session $s
```

Este exemplo mostra como obter uma **PSSession** usando sua ID de instância e, em seguida, excluir a **PSSession** .

O primeiro comando obtém todas as **PSSessions** que foram criadas na sessão atual. Ele envia as **PSSessions** para o cmdlet Format-Table, que exibe as propriedades **ComputerName** e **InstanceId** de cada **PSSession** .

O segundo comando usa o `Get-PSSession` cmdlet para obter uma **PSSession** específica e salvá-la na `$s` variável. O comando usa o parâmetro **InstanceId** para identificar a **PSSession** .

O terceiro comando usa o cmdlet Remove-PSSession para excluir a **PSSession** na `$s` variável.

### Exemplo 6: obter uma sessão que tem um nome específico

Os comandos neste exemplo encontram uma sessão que tem um formato de nome específico e usa uma configuração de sessão específica e, em seguida, se conecta à sessão. Você pode usar um comando como este para encontrar uma sessão na qual um colega iniciou uma tarefa e se conectar para concluir a tarefa.

```powershell
Get-PSSession -ComputerName Server02, Server12 -Name BackupJob* -ConfigurationName ITTasks -SessionOption @{OperationTimeout=240000}
```

```Output
 Id Name            ComputerName    State         ConfigurationName     Availability
 -- ----            ------------    -----         -----------------     ------------
  3 BackupJob04     Server02        Disconnected        ITTasks                  None
```

```powershell
$s = Get-PSSession -ComputerName Server02 -Name BackupJob04 -ConfigurationName ITTasks | Connect-PSSession
$s
```

```Output
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 5 BackupJob04     Server02        Opened        ITTasks                  Available
```

O primeiro comando obtém sessões nos computadores remotos Server02 e Server12 que têm nomes que começam com BackupJob e usam a configuração de sessão ITTasks. O comando usa o parâmetro **Name** para especificar o padrão de nome e o parâmetro **ConfigurationName** para especificar a configuração da sessão. O valor do parâmetro **SessionOption** é uma tabela de hash que define o valor de **OperationTimeout** como 240.000 milissegundos (4 minutos). Essa configuração fornece ao comando mais tempo para ser concluído. Os parâmetros **ConfigurationName** e **SessionOption** são usados para configurar as sessões temporárias nas quais o `Get-PSSession` cmdlet é executado em cada computador. A saída mostra que o comando retorna a sessão BackupJob04. A sessão está desconectada e a **disponibilidade** é nenhuma, o que indica que ela não está em uso.

O segundo comando usa o `Get-PSSession` cmdlet para obter a sessão BackupJob04 e o cmdlet Connect-PSSession para se conectar à sessão. O comando salva a sessão na variável $s.

O terceiro comando obtém a sessão na variável $s. A saída mostra que o `Connect-PSSession` comando foi bem-sucedido. A sessão está no estado **Opened** e está disponível para uso.

### Exemplo 7: obter uma sessão usando sua ID

```powershell
Get-PSSession -Id 2
```

Este comando obtém a **PSSession** com ID 2. Como o valor da propriedade **ID** é exclusivo somente na sessão atual, o parâmetro **ID** é válido somente para comandos locais.

## PARAMETERS

### -AllowRedirection

Indica que esse cmdlet permite o redirecionamento dessa conexão para um Uniform Resource Identifier alternativo (URI). Por padrão, o PowerShell não redireciona conexões.

Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **conexãouri** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUri, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Especifica o nome de um aplicativo. Esse cmdlet se conecta somente a sessões que usam o aplicativo especificado.

Insira o segmento de nome de aplicativo do URI de conexão. Por exemplo, no seguinte URI de conexão, o nome do aplicativo é WSMan: `http://localhost:5985/WSMAN` . O nome de aplicativo de uma sessão é armazenado na propriedade **Runspace.ConnectionInfo.AppName** da sessão.

O valor desse parâmetro é usado para selecionar e filtrar sessões. Ele não altera o aplicativo utilizado pela sessão.

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Autenticação

Especifica o mecanismo usado para autenticar credenciais para a sessão na qual o `Get-PSSession` comando é executado.

Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** ou **conexãouri** .

Os valores aceitáveis para esse parâmetro são:

- Padrão
- Básico
- CredSSP
- Digest
- Kerberos
- Negotiate
- NegotiateWithImplicitCredential.

O valor padrão é Default.

Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) na biblioteca MSDN.

Cuidado: a autenticação do Credential Security Support Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Especifica o certificado de chave pública digital (X509) de uma conta de usuário que tem permissão para criar a sessão na qual o `Get-PSSession` comando é executado. Insira a impressão digital do certificado.

Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** ou **conexãouri** .

Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.

Para obter uma impressão digital do certificado, use um comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Especifica uma matriz de nomes de computadores. Obtém as sessões que conectam a computadores especificados.
Caracteres curinga não são permitidos. Nenhum valor padrão.

A partir do Windows PowerShell 3,0, os objetos **PSSession** são armazenados nos computadores na extremidade remota de cada conexão. Para obter as sessões nos computadores especificados, o PowerShell cria uma conexão temporária com cada computador e executa um `Get-PSSession` comando.

Digite o nome de NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores. Para especificar o computador local, digite o nome do computador, localhost ou um ponto (.).

Observação: esse parâmetro Obtém sessões somente de computadores que executam o Windows PowerShell 3,0 ou versões posteriores do PowerShell. Versões anteriores não armazenam sessões.

```yaml
Type: System.String[]
Parameter Sets: ComputerInstanceId, ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationName

Especifica o nome de uma configuração. Esse cmdlet obtém somente as sessões que usam a configuração de sessão especificada.

Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão. Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/powershell` . O nome de configuração de uma sessão é armazenado na propriedade **ConfigurationName** da sessão.

O valor desse parâmetro é usado para selecionar e filtrar sessões. Ele não altera a configuração de sessão utilizada pela sessão.

Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName, VMNameInstanceId
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Conexãouri

Especifica um URI que define o ponto de extremidade de conexão para a sessão temporária na qual o `Get-PSSession` comando é executado. O URI deve ser totalmente qualificado.

Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **conexãouri** .

O formato dessa cadeia de caracteres é:

`<Transport>://<ComputerName>:<Port\>/<ApplicationName>`

O valor padrão é: `http://localhost:5985/WSMAN` .

Se você não especificar um **conexãouri** , poderá usar os parâmetros **UseSSL** , **ComputerName** , **Port** e **ApplicationName** para especificar os valores de **conexãouri** . Os valores válidos para o segmento Transport do URI são HTTP e HTTPS. Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas de padrões: 80 para HTTP e 443 para HTTPS. Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.

Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

Esse parâmetro Obtém sessões somente de computadores que executam o Windows PowerShell 3,0 ou versões posteriores do Windows PowerShell. Versões anteriores não armazenam sessões.

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUri, ConnectionUriInstanceId
Aliases: URI, CU

Required: True
Position: 0
Default value: Http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContainerId

Especifica uma matriz de IDs de contêineres. Esse cmdlet inicia uma sessão interativa com cada um dos contêineres especificados. Use o `docker ps` comando para obter uma lista de IDs de contêiner. Para obter mais informações, consulte a ajuda para o comando [Docker PS](https://docs.docker.com/engine/reference/commandline/ps/) .

```yaml
Type: System.String[]
Parameter Sets: ContainerId, ContainerIdInstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Especifica uma credencial de usuário. Esse cmdlet executa o comando com as permissões do usuário especificado. Especifique uma conta de usuário que tenha permissão para se conectar ao computador remoto e executar um `Get-PSSession` comando. O padrão é o usuário atual.

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, você será solicitado a inserir a senha.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** ou **conexãouri** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Especifica uma matriz de IDs de sessão. Esse cmdlet obtém apenas as sessões com as IDs especificadas. Digite uma ou mais IDs, separadas por vírgulas, ou use o operador de intervalo (..) para especificar um intervalo de IDs. Você não pode usar o parâmetro ID junto com o parâmetro **ComputerName** .

Uma ID é um inteiro que identifica exclusivamente as sessões gerenciadas pelo usuário na sessão atual. É mais fácil lembrar e digitar do que a **InstanceId** , mas só é exclusiva na sessão atual. A ID de uma sessão é armazenada na propriedade ID da sessão.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Especifica uma matriz de IDs de instância de sessões. Esse cmdlet obtém apenas as sessões com as IDs de instância especificadas.

A ID de instância é um GUID que identifica exclusivamente uma sessão em um computador local ou remoto. A **InstanceId** é exclusiva, mesmo quando você tem várias sessões em execução no PowerShell.

A ID de instância de uma sessão é armazenada na propriedade **InstanceID** da sessão.

```yaml
Type: System.Guid[]
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, ContainerIdInstanceId, VMIdInstanceId, VMNameInstanceId, InstanceId
Aliases:

Required: True (ComputerInstanceId, ConnectionUriInstanceId, ContainerIdInstanceId, VMIdInstanceId, VMNameInstanceId), False (InstanceId)
Position: Named
Default value: All sessions
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica uma matriz de nomes de sessão. Esse cmdlet obtém apenas as sessões que têm os nomes amigáveis especificados. Caracteres curinga são permitidos.

O nome amigável de uma sessão é armazenado na propriedade **Name** da sessão.

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri, ContainerId, VMId, VMName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Port

Especifica a porta de rede especificada que é usada para a conexão temporária na qual o `Get-PSSession` comando é executado. Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão. As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.

Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta. Para configurar o ouvinte, digite os dois comandos a seguir no prompt do PowerShell:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** ou **conexãouri** .

Não use o parâmetro **Port** a menos que seja necessário. A **porta** definida no comando aplica-se a todos os computadores ou sessões em que o comando é executado. Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: 5985, 5986
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionOption

Especifica as opções avançadas para a sessão. Insira um objeto **SessionOption** , como um que você cria usando o cmdlet New-PSSessionOption ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.

Os valores padrão das opções são determinados pelo valor da variável de preferência $PSSessionOption, se definida. Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.

Os valores de opção da sessão têm precedência sobre os valores padrão de sessões definidos na variável de preferência $PSSessionOption e na configuração da sessão. No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.

Para obter uma descrição das opções de sessão, incluindo os valores padrão, consulte `New-PSSessionOption` .
Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md). Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Estado

Especifica um estado de sessão. Este cmdlet obtém apenas sessões no estado especificado. Os valores aceitáveis para esse parâmetro são: todos, abertos, desconectados, fechados e desfeitos. O valor padrão é All.

O valor de estado de sessão é relativo à sessão atual. Sessões que não tiverem sido criadas nas sessões atuais e não estiverem conectadas à sessão atual terão um estado de Disconnected, mesmo quando estiverem conectadas a uma sessão diferente.

O estado de uma sessão é armazenado na propriedade **State** da sessão.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: Microsoft.PowerShell.Commands.SessionFilterState
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName, VMNameInstanceId
Aliases:
Accepted values: All, Opened, Disconnected, Closed, Broken

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o `Get-PSSession` comando. Se você omitir esse parâmetro ou digitar o valor 0 (zero), o valor padrão, 32, será usado. O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para estabelecer a conexão na qual o `Get-PSSession` comando é executado. Por padrão, SSL não é usado. Se você usar esse parâmetro e o SSL não estiver disponível na porta usada para o comando, o comando falhará.

Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMId

Especifica uma matriz de ID de máquinas virtuais. Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas. Para ver as máquinas virtuais que estão disponíveis para você, use o seguinte comando:

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId, VMIdInstanceId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName

Especifica uma matriz de nomes de máquinas virtuais. Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas. Para ver as máquinas virtuais que estão disponíveis para você, use o `Get-VM` cmdlet.

```yaml
Type: System.String[]
Parameter Sets: VMName, VMNameInstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Management. Automation. Runspaces. PSSession

## OBSERVAÇÕES

- Esse cmdlet obtém objetos **PSSession** de sessões gerenciadas pelo usuário "como aquelas criadas usando os cmdlets New-PSSession, `Enter-PSSession` e Invoke-Command. Ele não obtém a sessão gerenciada pelo sistema que é criada quando você inicia o PowerShell.
- A partir do Windows PowerShell 3,0, os objetos **PSSession** são armazenados no computador que está no lado do servidor ou no fim do recebimento de uma conexão. Para obter as sessões armazenadas no computador local ou em um computador remoto, o PowerShell estabelece uma sessão temporária para o computador especificado e executa comandos de consulta na sessão.
- Para obter sessões que se conectam a um computador remoto, use os parâmetros **ComputerName** ou **ConnectionUri** para especificar o computador remoto. Para filtrar as sessões que `Get-PSSession` Obtém, use os parâmetros **Name** , **ID** , **InstanceId** e **State** . Use os parâmetros restantes para configurar a sessão temporária que o `Get-PSSession` usa.
- Quando você usa os parâmetros **ComputerName** ou **conexãouri** , o `Get-PSSession` obtém apenas sessões de computadores que executam o Windows PowerShell 3,0 e versões posteriores do PowerShell.
- O valor da propriedade **State** de uma **PSSession** é relativo à sessão atual.
  Portanto, um valor de **desconectado** significa que a **PSSession** não está conectada à sessão atual. No entanto, isso não significa que a **PSSession** seja desconectada de todas as sessões. Ela pode ser conectada a uma sessão diferente. Para determinar se você pode se conectar ou reconectar-se à **PSSession** da sessão atual, use a propriedade de **disponibilidade** .

Um valor **Availability** de **None** indica que é possível conectar-se à sessão. Um valor de **ocupado** indica que você não pode se conectar à **PSSession** porque ela está conectada a outra sessão.

Para obter mais informações sobre os valores da propriedade **State** de sessões, consulte [Enumeração RunspaceState](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate).

Para obter mais informações sobre os valores da propriedade de sessões de **disponibilidade** , consulte [Enumeração RunspaceAvailability](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability).

## LINKS RELACIONADOS

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)

[about_PSSessions](About/about_PSSessions.md)

[about_Remote](About/about_Remote.md)
