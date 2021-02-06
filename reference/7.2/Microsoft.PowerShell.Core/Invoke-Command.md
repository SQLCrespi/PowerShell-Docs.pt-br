---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Command
ms.openlocfilehash: d8f0a8a56792a39371a307166788f047fec99a9a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598632"
---
# Invoke-Command

## SINOPSE
Executa comandos em computadores locais e remotos.

## SYNTAX

### Inprocessar (padrão)

```
Invoke-Command [-ScriptBlock] <ScriptBlock> [-NoNewScope] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### FilePathRunspace

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### Sessão

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### FilePathComputerName

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-FilePath] <String> [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### ComputerName

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### Uri

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### FilePathUri

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### VMId

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### VMName

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### FilePathVMId

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### FilePathVMName

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### SSHHost

```
Invoke-Command [-Port <Int32>] [-AsJob] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> -HostName <String[]> [-UserName <String>] [-KeyFilePath <String>]
 [-SSHTransport] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-Subsystem <String>] [<CommonParameters>]
```

### ContainerId

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RunAsAdministrator] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### FilePathContainerId

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RunAsAdministrator] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### SSHHostHashParam

```
Invoke-Command [-AsJob] [-HideComputerName] [-JobName <String>] [-ScriptBlock] <ScriptBlock>
 -SSHConnection <Hashtable[]> [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### FilePathSSHHost

```
Invoke-Command [-AsJob] [-HideComputerName] -FilePath <String> -HostName <String[]>
 [-UserName <String>] [-KeyFilePath <String>] [-SSHTransport] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### FilePathSSHHostHash

```
Invoke-Command [-AsJob] [-HideComputerName] -FilePath <String> -SSHConnection <Hashtable[]>
 [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Invoke-Command` cmdlet executa comandos em um computador local ou remoto e retorna toda a saída dos comandos, incluindo erros. Usando um único `Invoke-Command` comando, você pode executar comandos em vários computadores.

Para executar um único comando em um computador remoto, use o parâmetro **ComputerName**. Para executar uma série de comandos relacionados que compartilham dados, use o `New-PSSession` cmdlet para criar uma **PSSession** (uma conexão persistente) no computador remoto e, em seguida, use o parâmetro **Session** de `Invoke-Command` para executar o comando em **PSSession**. Para executar um comando em uma sessão desconectada, use o parâmetro **InDisconnectedSession**. Para executar um comando em um trabalho em segundo plano, use o parâmetro **AsJob**.

Você também pode usar `Invoke-Command` em um computador local para um bloco de script como um comando. O PowerShell executa o bloco de script imediatamente em um escopo filho do escopo atual.

Antes de usar o `Invoke-Command` para executar comandos em um computador remoto, leia [about_Remote](./About/about_Remote.md).

A partir do PowerShell 6,0, você pode usar Secure Shell (SSH) para estabelecer uma conexão com o e invocar comandos em computadores remotos. O SSH deve ser instalado no computador local e o computador remoto deve ser configurado com um ponto de extremidade SSH do PowerShell. O benefício de uma sessão remota do PowerShell baseada em SSH é que ela funciona em várias plataformas (Windows, Linux e macOS). Para sessão baseada em SSH, use os parâmetros **hostname** ou **SSHConnection** para especificar o computador remoto e as informações de conexão relevantes. Para obter mais informações sobre como configurar a comunicação remota do PowerShell SSH, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

Alguns exemplos de código usam nivelamento para reduzir o comprimento da linha. Para obter mais informações, consulte [about_Splatting](./About/about_Splatting.md).

## EXEMPLOS

### Exemplo 1: executar um script em um servidor

Este exemplo executa o `Test.ps1` script no computador Server01.

```powershell
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
```

O parâmetro **FilePath** especifica um script que está localizado no computador local. O script é executado no computador remoto e os resultados são retornados ao computador local.

### Exemplo 2: executar um comando em um servidor remoto

Este exemplo executa um `Get-Culture` comando no computador remoto Server01.

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }
```

O parâmetro **ComputerName** especifica o nome do computador remoto. O parâmetro **Credential** é usado para executar o comando no contexto de segurança de Domínio01 \ Usuário01, um usuário que tem permissão para executar comandos. O parâmetro **scriptblock** especifica o comando a ser executado no computador remoto.

Em resposta, o PowerShell solicita a senha e um método de autenticação para a conta User01.
Em seguida, ele executa o comando no computador Server01 e retorna o resultado.

### Exemplo 3: executar um comando em uma conexão persistente

Este exemplo executa o mesmo `Get-Culture` comando em uma sessão, usando uma conexão persistente, no computador remoto chamado Server02.

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

O `New-PSSession` cmdlet cria uma sessão no computador remoto Server02 e salva-a na `$s` variável. Normalmente, você cria uma sessão somente quando executa uma série de comandos no computador remoto.

O `Invoke-Command` cmdlet executa o `Get-Culture` comando em Server02. O parâmetro **Session** especifica a sessão salva na `$s` variável.

Em resposta, o PowerShell executa o comando na sessão no computador Server02.

### Exemplo 4: usar uma sessão para executar uma série de comandos que compartilham dados

Este exemplo compara os efeitos do uso de **ComputerName** e de parâmetros de **sessão** do `Invoke-Command` . Ele mostra como utilizar uma sessão para executar uma série de comandos que compartilham os mesmos dados.

```powershell
Invoke-Command -ComputerName Server02 -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -ComputerName Server02 -ScriptBlock {$p.VirtualMemorySize}
$s = New-PSSession -ComputerName Server02
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -Session $s -ScriptBlock {$p.VirtualMemorySize}
```

```Output
17930240
```

Os dois primeiros comandos usam o parâmetro **ComputerName** do `Invoke-Command` para executar comandos no computador remoto Server02. O primeiro comando usa o `Get-Process` cmdlet para obter o processo do PowerShell no computador remoto e salvá-lo na `$p` variável. O segundo comando obtém o valor da propriedade **VirtualMemorySize** do processo do PowerShell.

Quando você usa o parâmetro **ComputerName** , o PowerShell cria uma nova sessão para executar o comando.
A sessão é fechada quando o comando é concluído. A `$p` variável foi criada em uma conexão, mas ela não existe na conexão criada para o segundo comando.

O problema é resolvido com a criação de uma sessão persistente no computador remoto e, em seguida, a execução dos dois comandos na mesma sessão.

O `New-PSSession` cmdlet cria uma sessão persistente no computador Server02 e salva a sessão na `$s` variável. As `Invoke-Command` linhas a seguir usam o parâmetro **Session** para executar os dois comandos na mesma sessão. Como ambos os comandos são executados na mesma sessão, o `$p` valor permanece ativo.

### Exemplo 5: inserir um comando armazenado em uma variável local

Este exemplo mostra como criar um comando que é armazenado como um bloco de script em uma variável local.
Quando o bloco de script é salvo em uma variável local, você pode especificar a variável como o valor do parâmetro **scriptblock** .

```powershell
$command = { Get-WinEvent -LogName PowerShellCore/Operational |
  Where-Object {$_.Message -like "*certificate*"} }
Invoke-Command -ComputerName S1, S2 -ScriptBlock $command
```

A `$command` variável armazena o `Get-WinEvent` comando que é formatado como um bloco de script. O `Invoke-Command` executa o comando armazenado em `$command` nos computadores remotos S1 e S2.

### Exemplo 6: executar um único comando em vários computadores

Este exemplo demonstra como usar `Invoke-Command` o para executar um único comando em vários computadores.

```powershell
$parameters = @{
  ComputerName = "Server01", "Server02", "TST-0143", "localhost"
  ConfigurationName = 'MySession.PowerShell'
  ScriptBlock = { Get-WinEvent -LogName PowerShellCore/Operational }
}
Invoke-Command @parameters
```

O parâmetro **ComputerName** especifica uma lista separada por vírgulas de nomes de computador. A lista de computadores inclui o valor de localhost, que representa o computador local. O parâmetro **ConfigurationName** especifica uma configuração de sessão alternativa. O parâmetro **scriptblock** é executado `Get-WinEvent` para obter os logs de eventos PowerShellCore/operacionais de cada computador.

### Exemplo 7: obter a versão do programa host em vários computadores

Este exemplo obtém a versão do programa host do PowerShell em execução em computadores remotos 200.

```powershell
$version = Invoke-Command -ComputerName (Get-Content Machines.txt) -ScriptBlock {(Get-Host).Version}
```

Como apenas um comando é executado, você não precisa criar conexões persistentes para cada um dos computadores. Em vez disso, o comando usa o parâmetro **ComputerName** para indicar os computadores. Para especificar os computadores, ele usa o `Get-Content` cmdlet para obter o conteúdo do arquivo de Machine.txt, um arquivo de nomes de computador.

O `Invoke-Command` cmdlet executa um `Get-Host` comando nos computadores remotos. Ele usa a notação de ponto para obter a propriedade **version** do host do PowerShell.

Esses comandos são executados um de cada vez. Quando os comandos forem concluídos, a saída dos comandos de todos os computadores será salva na `$version` variável. A saída inclui o nome do computador de origem de dados.

### Exemplo 8: executar um trabalho em segundo plano em vários computadores remotos

Este exemplo executa um comando em dois computadores remotos. O `Invoke-Command` comando usa o parâmetro **AsJob** para que o comando seja executado como um trabalho em segundo plano. Os comandos são executados nos computadores remotos, mas o trabalho existe no computador local. Os resultados são transmitidos para o computador local.

```powershell
$s = New-PSSession -ComputerName Server01, Server02
Invoke-Command -Session $s -ScriptBlock {Get-EventLog system} -AsJob
```

```Output
Id   Name    State      HasMoreData   Location           Command
---  ----    -----      -----         -----------        ---------------
1    Job1    Running    True          Server01,Server02  Get-EventLog system
```

```powershell
$j = Get-Job
$j | Format-List -Property *
```

```Output
HasMoreData   : True
StatusMessage :
Location      : Server01,Server02
Command       : Get-EventLog system
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : e124bb59-8cb2-498b-a0d2-2e07d4e030ca
Id            : 1
Name          : Job1
ChildJobs     : {Job2, Job3}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :
```

```powershell
$results = $j | Receive-Job
```

O `New-PSSession` cmdlet cria sessões nos computadores remotos Server01 e Server02. O `Invoke-Command` cmdlet executa um trabalho em segundo plano em cada uma das sessões. O comando usa o parâmetro **AsJob** para executar o comando como um trabalho em segundo plano. Esse comando retorna um objeto de trabalho que contém dois objetos de trabalho filho, um para cada um dos trabalhos executados nos dois computadores remotos.

O `Get-Job` comando salva o objeto de trabalho na `$j` variável. `$j`Em seguida, a variável é canalizada para o `Format-List` cmdlet para exibir todas as propriedades do objeto de trabalho em uma lista. O último comando obtém os resultados dos trabalhos. Ele canaliza o objeto de trabalho `$j` para o `Receive-Job` cmdlet e armazena os resultados na `$results` variável.

### Exemplo 9: incluir variáveis locais em um comando executado em um computador remoto

Este exemplo mostra como incluir os valores das variáveis locais em um comando executado em um computador remoto. O comando usa o `Using` modificador de escopo para identificar uma variável local em um comando remoto. Por padrão, todas as variáveis devem ser definidas na sessão remota. O `Using` modificador de escopo foi introduzido no PowerShell 3,0. Para obter mais informações sobre o `Using` modificador de escopo, consulte [about_Remote_Variables](./About/about_Remote_Variables.md) e [about_Scopes](./about/about_scopes.md).

```powershell
$Log = "PowerShellCore/Operational"
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-WinEvent -LogName $Using:Log -MaxEvents 10}
```

A `$Log` variável armazena o nome do log de eventos, PowerShellCore/Operational. O `Invoke-Command` cmdlet é executado `Get-WinEvent` no Server01 para obter os dez eventos mais recentes do log de eventos. O valor do parâmetro **LogName** é a `$Log` variável que é prefixada pelo `Using` modificador de escopo para indicar que ele foi criado na sessão local, não na sessão remota.

### Exemplo 10: ocultar o nome do computador

Este exemplo mostra o efeito de usar o parâmetro **HideComputerName** de `Invoke-Command` .
**HideComputerName** não altera o objeto retornado por esse cmdlet. Ele altera apenas a exibição. Você ainda pode usar os cmdlets **Format** para exibir a propriedade **PSComputerName** de qualquer um dos objetos afetados.

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell}
```

```Output
PSComputerName    Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
--------------    -------  ------    -----      ----- -----   ------     --   -----------
S1                575      15        45100      40988   200     4.68     1392 PowerShell
S2                777      14        35100      30988   150     3.68     67   PowerShell
```

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell} -HideComputerName
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
575      15        45100      40988   200     4.68     1392 PowerShell
777      14        35100      30988   150     3.68     67   PowerShell
```

Os dois primeiros comandos usam `Invoke-Command` para executar um `Get-Process` comando para o processo do PowerShell. A saída do primeiro comando inclui a propriedade **PsComputerName**, que contém o nome do computador no qual o comando foi executado. A saída do segundo comando, que usa **HideComputerName**, não inclui a coluna **PSComputerName** .

### Exemplo 11: usar a palavra-chave param em um bloco de script

A `Param` palavra-chave e o parâmetro **ArgumentList** são usados para passar valores de variáveis para parâmetros nomeados em um bloco de script. Este exemplo exibe os nomes de nome que começam com a letra `a` e têm a `.pdf` extensão.

Para obter mais informações sobre a `Param` palavra-chave, consulte [about_Language_Keywords](./about/about_language_keywords.md#param).

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Param ($param1,$param2) Get-ChildItem -Name $param1 -Include $param2 }
    ArgumentList = "a*", "*.pdf"
}
Invoke-Command @parameters
```

```Output
aa.pdf
ab.pdf
ac.pdf
az.pdf
```

`Invoke-Command` usa o parâmetro **scriptblock** que define duas variáveis, `$param1` e `$param2` . `Get-ChildItem` usa os parâmetros nomeados, **Name** e **include** com os nomes de variáveis. O **argumentolist** passa os valores para as variáveis.

### Exemplo 12: usar a $args variável automática em um bloco de script

A `$args` variável automática e o parâmetro **ArgumentList** são usados para passar valores de matriz para posições de parâmetro em um bloco de script. Este exemplo exibe o conteúdo do diretório de arquivos de um servidor `.txt` . O `Get-ChildItem` parâmetro de **caminho** é a posição 0 e o parâmetro de **filtro** é posição
1.

Para obter mais informações sobre a `$args` variável, consulte [about_Automatic_Variables](./about/about_automatic_variables.md#args)

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Get-ChildItem $args[0] $args[1] }
    ArgumentList = "C:\Test", "*.txt*"
}
Invoke-Command @parameters
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           6/12/2019    15:15            128 alog.txt
-a---           7/27/2019    15:16            256 blog.txt
-a---           9/28/2019    17:10             64 zlog.txt
```

`Invoke-Command` usa um parâmetro **scriptblock** e `Get-ChildItem` especifica os `$args[0]` valores de `$args[1]` matriz e. O **argumentolist** passa os `$args` valores de matriz para as `Get-ChildItem` posições de parâmetro para **caminho** e **filtro**.

### Exemplo 13: executar um script em todos os computadores listados em um arquivo de texto

Este exemplo usa o `Invoke-Command` cmdlet para executar o `Sample.ps1` script em todos os computadores listados no `Servers.txt` arquivo. O comando usa o parâmetro **FilePath** para especificar o arquivo de script. Esse comando permite que você execute o script nos computadores remotos, mesmo que o arquivo de script não esteja acessível para os computadores remotos.

```powershell
Invoke-Command -ComputerName (Get-Content Servers.txt) -FilePath C:\Scripts\Sample.ps1 -ArgumentList Process, Service
```

Quando você envia o comando, o conteúdo do `Sample.ps1` arquivo é copiado em um bloco de script e o bloco de script é executado em cada um dos computadores remotos. Esse procedimento equivale a utilizar o parâmetro **ScriptBlock** para enviar o conteúdo do script.

### Exemplo 14: executar um comando em um computador remoto usando um URI

Este exemplo mostra como executar um comando em um computador remoto que é identificado por um Uniform Resource Identifier (URI). Este exemplo específico executa um `Set-Mailbox` comando em um servidor Exchange remoto.

```powershell
$LiveCred = Get-Credential
$parameters = @{
  ConfigurationName = 'Microsoft.Exchange'
  ConnectionUri = 'https://ps.exchangelabs.com/PowerShell'
  Credential = $LiveCred
  Authentication = 'Basic'
  ScriptBlock = {Set-Mailbox Dan -DisplayName "Dan Park"}
}
Invoke-Command @parameters
```

A primeira linha usa o `Get-Credential` cmdlet para armazenar as credenciais do Windows Live ID na `$LiveCred` variável. O PowerShell solicita que o usuário insira as credenciais do Windows Live ID.

A `$parameters` variável é uma tabela de hash que contém os parâmetros a serem passados para o `Invoke-Command` cmdlet. O `Invoke-Command` cmdlet executa um `Set-Mailbox` comando usando a configuração de sessão do **Microsoft. Exchange** . O parâmetro **ConnectionURI** especifica a URL do ponto de extremidade do servidor Exchange. O parâmetro **Credential** especifica as credenciais armazenadas na `$LiveCred` variável. O parâmetro **AuthenticationMechanism** especifica o uso da autenticação básica. O parâmetro **ScriptBlock** especifica um bloco de script que contém o comando.

### Exemplo 15: usar uma opção de sessão

Este exemplo mostra como criar e usar um parâmetro **SessionOption** .

```powershell
$so = New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck
Invoke-Command -ComputerName server01 -UseSSL -ScriptBlock { Get-HotFix } -SessionOption $so -Credential server01\user01
```

O `New-PSSessionOption` cmdlet cria um objeto de opção de sessão que faz com que a extremidade remota não verifique a autoridade de certificação, o nome canônico e as listas de revogação ao avaliar a conexão HTTPS de entrada. O objeto **SessionOption** é salvo na `$so` variável.

> [!NOTE]
> A desabilitação dessas verificações é conveniente para a solução de problemas, mas, obviamente, não é segura.

O `Invoke-Command` cmdlet executa um `Get-HotFix` comando remotamente. O parâmetro **SessionOption** recebe a `$so` variável.

### Exemplo 16: gerenciar o redirecionamento de URI em um comando remoto

Este exemplo mostra como usar os parâmetros **AllowRedirection** e **SessionOption** para gerenciar o redirecionamento de URI em um comando remoto.

```powershell
$max = New-PSSessionOption -MaximumRedirection 1
$parameters = @{
  ConnectionUri = "https://ps.exchangelabs.com/PowerShell"
  ScriptBlock = { Get-Mailbox dan }
  AllowRedirection = $true
  SessionOption = $max
}
Invoke-Command @parameters
```

O `New-PSSessionOption` cmdlet cria um objeto **PSSessionOption** que é salvo na `$max` variável. O comando utiliza o parâmetro **MaximumRedirection** para definir a propriedade **MaximumConnectionRedirectionCount** do objeto **PSSessionOption** como 1.

O `Invoke-Command` cmdlet executa um `Get-Mailbox` comando em um servidor remoto do Microsoft Exchange. O parâmetro **AllowRedirection** fornece permissão explícita para redirecionar a conexão para um ponto de extremidade alternativo. O parâmetro **SessionOption** usa o objeto de sessão armazenado na `$max` variável.

Como resultado, se o computador remoto especificado por **conexãouri** retornar uma mensagem de redirecionamento, o PowerShell redireciona a conexão, mas se o novo destino retornar outra mensagem de redirecionamento, o valor de contagem de redirecionamento de 1 será excedido e `Invoke-Command` retornará um erro de não finalização.

### Exemplo 17: acessar um compartilhamento de rede em uma sessão remota

Este exemplo mostra como acessar um compartilhamento de rede de uma sessão remota. Três computadores são usados para demonstrar o exemplo. Server01 é o computador local, Server02 é o computador remoto e Net03 contém o compartilhamento de rede. Server01 conecta-se ao Server02 e, em seguida, o Server02 faz um segundo salto para o Net03 acessar o compartilhamento de rede. Para obter mais informações sobre como a comunicação remota do PowerShell dá suporte a saltos entre computadores, consulte [tornando o segundo salto na comunicação remota do PowerShell](/powershell/scripting/learn/remoting/ps-remoting-second-hop).

A delegação necessária da CredSSP (provedor de suporte à segurança de credencial) está habilitada nas configurações do cliente no computador local e nas configurações do serviço no computador remoto. Para executar os comandos neste exemplo, você deve ser um membro do grupo **Administradores** no computador local e no computador remoto.

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer Server02
$s = New-PSSession Server02
Invoke-Command -Session $s -ScriptBlock {Enable-WSManCredSSP -Role Server -Force}
$parameters = @{
  Session = $s
  ScriptBlock = { Get-Item \\Net03\Scripts\LogFiles.ps1 }
  Authentication = "CredSSP"
  Credential = "Domain01\Admin01"
}
Invoke-Command @parameters
```

O `Enable-WSManCredSSP` cmdlet habilita a delegação de CredSSP do computador local Server01 para o computador remoto Server02. O parâmetro **role** especifica o **cliente** para definir a configuração do cliente CredSSP no computador local.

`New-PSSession` Cria um objeto **PSSession** para Server02 e armazena o objeto na `$s` variável.

O `Invoke-Command` cmdlet usa a `$s` variável para se conectar ao computador remoto, Server02. O parâmetro **scriptblock** é executado `Enable-WSManCredSSP` no computador remoto. O parâmetro de **função** especifica **servidor** para configurar a configuração do servidor CredSSP no computador remoto.

A `$parameters` variável contém os valores de parâmetro para se conectar ao compartilhamento de rede. O `Invoke-Command` cmdlet executa um `Get-Item` comando na sessão no `$s` . Esse comando obtém um script do `\\Net03\Scripts` compartilhamento de rede. O comando usa o parâmetro de **autenticação** com um valor de **CredSSP** e o parâmetro **Credential** com um valor de **domain01\admin01**.

### Exemplo 18: iniciar scripts em vários computadores remotos

Este exemplo executa um script em mais de uma centena de computadores. Para minimizar o impacto no computador local, ele se conecta a cada computador, inicia o script e, em seguida, desconecta de cada computador.
O script continuará a ser executado nas sessões desconectadas.

```powershell
$parameters = @{
  ComputerName = (Get-Content -Path C:\Test\Servers.txt)
  InDisconnectedSession = $true
  FilePath = "\\Scripts\Public\ConfigInventory.ps1"
  SessionOption = @{OutputBufferingMode="Drop";IdleTimeout=43200000}
}
Invoke-Command @parameters
```

O comando usa `Invoke-Command` para executar o script. O valor do parâmetro **ComputerName** é um `Get-Content` comando que obtém os nomes dos computadores remotos a partir de um arquivo de texto. O parâmetro **InDisconnectedSession** desconecta as sessões assim que ele inicia o comando. O valor do parâmetro **FilePath** é o script que `Invoke-Command` é executado em cada computador.

O valor de **SessionOption** é uma tabela de hash. O valor de **OutputBufferingMode** é definido como **drop** e o valor de **IdleTimeout** é definido como **43,2 milhões** milissegundos (12 horas).

Para obter os resultados de comandos e scripts que são executados em sessões desconectadas, use o `Receive-PSSession` cmdlet.

### Exemplo 19: executar um comando em um computador remoto usando SSH

Este exemplo mostra como executar um comando em um computador remoto usando Secure Shell (SSH). Se o SSH estiver configurado no computador remoto para solicitar senhas, você receberá um prompt de senha.
Caso contrário, você precisará usar a autenticação de usuário baseada em chave SSH.

```powershell
Invoke-Command -HostName UserA@LinuxServer01 -ScriptBlock { Get-MailBox * }
```

### Exemplo 20: executar um comando em um computador remoto usando SSH e especificar uma chave de autenticação de usuário

Este exemplo mostra como executar um comando em um computador remoto usando SSH e especificando um arquivo de chave para autenticação de usuário. Não será solicitada uma senha a menos que a autenticação de chave falhe e o computador remoto esteja configurado para permitir a autenticação de senha básica.

```powershell
Invoke-Command -HostName UserA@LinuxServer01 -ScriptBlock { Get-MailBox * } -KeyFilePath /UserA/UserAKey_rsa
```

### Exemplo 21: executar um arquivo de script em vários computadores remotos usando SSH como um trabalho

Este exemplo mostra como executar um arquivo de script em vários computadores remotos usando SSH e o conjunto de parâmetros **SSHConnection** . O parâmetro **SSHConnection** usa uma matriz de tabelas de hash que contêm informações de conexão para cada computador. Este exemplo requer que os computadores remotos de destino tenham o SSH configurado para dar suporte à autenticação de usuário baseada em chave.

```powershell
$sshConnections =
@{ HostName="WinServer1"; UserName="Domain\UserA"; KeyFilePath="C:\Users\UserA\id_rsa" },
@{ HostName="UserB@LinuxServer5"; KeyFilePath="/Users/UserB/id_rsa" }
$results = Invoke-Command -FilePath c:\Scripts\CollectEvents.ps1 -SSHConnection $sshConnections
```

## PARAMETERS

### -AllowRedirection

Permite o redirecionamento da conexão para um URI (Uniform Resource Identifier) alternativo.

Quando você usa o parâmetro **ConnectionURI**, o destino remoto pode retornar uma instrução para redirecionar para um URI diferente. Por padrão, o PowerShell não redireciona conexões, mas você pode usar esse parâmetro para permitir que ele redirecione a conexão.

É possível também limitar o número de vezes que a conexão é redirecionada alterando o valor da opção de sessão **MaximumConnectionRedirectionCount**. Use o parâmetro **MaximumRedirection** do `New-PSSessionOption` cmdlet ou defina a propriedade **MaximumConnectionRedirectionCount** da variável de `$PSSessionOption` preferência. O valor padrão é 5.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Especifica o segmento de nome de aplicativo do URI de conexão. Use esse parâmetro para especificar o nome do aplicativo quando você não estiver usando o parâmetro **conexãouri** no comando.

O valor padrão é o valor da `$PSSessionApplicationName` variável de preferência no computador local. Se essa variável de preferência não for definida, o valor padrão será WSMAN. Esse valor é adequado para a maioria dos usos. Para obter mais informações, consulte [about_Preference_Variables](./About/about_Preference_Variables.md).

O serviço WinRM usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão.
O valor desse parâmetro deve corresponder ao valor da propriedade **URLPrefix** de um ouvinte no computador remoto.

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: $PSSessionApplicationName if set on the local computer, otherwise WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ArgumentList

Fornece os valores de variáveis locais no comando. As variáveis no comando são substituídas por esses valores antes do comando ser executado no computador remoto. Digite os valores em uma lista separada por vírgulas. Os valores são associados a variáveis na ordem em que estão listados. O alias para **ArgumentList** é args.

Os valores no parâmetro **ArgumentList** podem ser valores reais, como 1024, ou podem ser referências a variáveis locais, como `$max` .

Para utilizar variáveis locais em um comando, use o seguinte formato de comando:

`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` - ou - `<local-variable>`

A palavra-chave **param** lista as variáveis locais que são usadas no comando. **ArgumentList** fornece os valores das variáveis, na ordem em que estão listadas. Para obter mais informações sobre o comportamento de **ArgumentList**, consulte [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob

Indica que esse cmdlet executa o comando como um trabalho em segundo plano em um computador remoto. Use esse parâmetro para executar comandos que levam muito tempo para serem concluídos.

Quando você usa o parâmetro **AsJob** , o comando retorna um objeto que representa o trabalho e, em seguida, exibe o prompt de comando. É possível continuar a trabalhar na sessão enquanto o trabalho é concluído. Para gerenciar o trabalho, use os `*-Job` cmdlets. Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.

O parâmetro **AsJob** é semelhante ao uso do `Invoke-Command` cmdlet para executar um `Start-Job` cmdlet remotamente. No entanto, com **AsJob**, o trabalho é criado no computador local, embora o trabalho seja executado em um computador remoto. Os resultados do trabalho remoto são retornados automaticamente para o computador local.

Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](About/about_Jobs.md) e [about_Remote_Jobs](About/about_Remote_Jobs.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Autenticação

Especifica o mecanismo usado para autenticar as credenciais do usuário. A autenticação CredSSP está disponível somente no Windows Vista, no Windows Server 2008 e em versões posteriores do sistema operacional Windows.

Os valores aceitáveis para esse parâmetro são os seguintes:

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
> A autenticação CredSSP (Credencial Security Support Provider), na qual as credenciais do usuário são passadas a um computador remoto para autenticação, foi projetada para comandos que exijam autenticação em mais de um recurso, como acessar um compartilhamento de rede remota. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede. Para obter mais informações, consulte [provedor de suporte à segurança de credenciais](/windows/win32/secauthn/credential-security-support-provider).

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:
Accepted values: Basic, Default, Credssp, Digest, Kerberos, Negotiate, NegotiateWithImplicitCredential

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para se conectar à sessão desconectada. Insira a impressão digital do certificado.

Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles podem ser mapeados apenas para contas de usuário local e não funcionam com contas de domínio.

Para obter uma impressão digital do certificado, use um `Get-Item` `Get-ChildItem` comando ou na unidade certificado do PowerShell:.

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

Especifica os computadores em que o comando é executado. O padrão é o computador local.

Quando você usa o parâmetro **ComputerName** , o PowerShell cria uma conexão temporária que é usada somente para executar o comando especificado e, em seguida, é fechada. Se você precisar de uma conexão persistente, use o parâmetro **Session** .

Digite o nome da NETBIOS, o endereço IP ou o nome de domínio totalmente qualificado de um ou mais computadores em uma lista separada por vírgulas. Para especificar o computador local, digite o nome do computador, localhost ou um ponto ( `.` ).

Para usar um endereço IP no valor de **ComputerName**, o comando deve incluir o parâmetro **Credential** . O computador deve ser configurado para o transporte HTTPS ou o endereço IP do computador remoto deve ser incluído na lista de **TrustedHosts** WinRM do computador local. Para obter instruções para adicionar um nome de computador à lista **TrustedHosts** , consulte [como adicionar um computador à lista de hosts confiáveis](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list).

No Windows Vista e versões posteriores do sistema operacional Windows, para incluir o computador local no valor **ComputerName**, você deve executar o PowerShell usando a opção **Executar como administrador** .

```yaml
Type: System.String[]
Parameter Sets: ComputerName, FilePathComputerName
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName

Especifica a configuração de sessão que é usada para a nova **PSSession**.

Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão. Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/PowerShell` .

Quando usado com SSH, esse parâmetro especifica o subsistema a ser usado no destino, conforme definido em `sshd_config` . O valor padrão para SSH é o `powershell` subsistema.

A configuração da sessão para uma sessão está localizada no computador remoto. Se a configuração de sessão especificada não existir no computador remoto, o comando falhará.

O valor padrão é o valor da `$PSSessionConfigurationName` variável de preferência no computador local. Se essa variável de preferência não for definida, o padrão será **Microsoft. PowerShell**. Para obter mais informações, consulte [about_Preference_Variables](about/about_Preference_Variables.md).

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: $PSSessionConfigurationName if set on the local computer, otherwise Microsoft.PowerShell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Conexãouri

Especifica um URI (Uniform Resource Identifier) que define o ponto de extremidade de conexão da sessão.
O URI deve ser totalmente qualificado.

O formato dessa cadeia de caracteres é o seguinte:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

O valor padrão é o seguinte:

`http://localhost:5985/WSMAN`

Se você não especificar um URI de conexão, poderá usar os parâmetros **UseSSL** e **Port** para especificar os valores de URI de conexão.

Os valores válidos para o segmento **Transport** do URI são HTTP e HTTPS. Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com as portas de padrões: 80 para HTTP e 443 para HTTPS. Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.

Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.

```yaml
Type: System.Uri[]
Parameter Sets: Uri, FilePathUri
Aliases: URI, CU

Required: False
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContainerId

Especifica uma matriz de IDs de contêiner.

```yaml
Type: System.String[]
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName
Aliases:

Required: True (VMId, VMName, FilePathVMId, FilePathVMName), False (ComputerName, FilePathComputerName, Uri, FilePathUri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableNetworkAccess

Indica que esse cmdlet adiciona um token de segurança interativo a sessões de loopback. O token interativo permite executar comandos na sessão de loopback que obtêm dados de outros computadores. Por exemplo, você pode executar um comando na sessão que copia arquivos XML de um computador remoto no computador local.

Uma sessão de loopback é uma **PSSession** originada e termina no mesmo computador. Para criar uma sessão de loopback, omita o parâmetro **ComputerName** ou defina seu valor como ponto ( `.` ), localhost ou o nome do computador local.

Por padrão, as sessões de loopback são criadas usando um token de rede, que pode não fornecer permissão suficiente para autenticar em computadores remotos.

O parâmetro **EnableNetworkAccess** só é eficaz em sessões de loopback. Se você usar **EnableNetworkAccess** ao criar uma sessão em um computador remoto, o comando terá sucesso, mas o parâmetro será ignorado.

Você pode permitir o acesso remoto em uma sessão de loopback usando o valor **CredSSP** do parâmetro de **autenticação** , que delega as credenciais de sessão para outros computadores.

Para proteger o computador contra acesso mal-intencionado, as sessões de loopback desconectadas que têm tokens interativos, que são aquelas criadas usando **EnableNetworkAccess**, podem ser reconectadas somente do computador no qual a sessão foi criada. Sessões desconectadas que usam a autenticação CredSSP podem ser reconectadas por meio de outros computadores. Para obter mais informações, consulte `Disconnect-PSSession`.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Especifica um script local que esse cmdlet executa em um ou mais computadores remotos. Insira o caminho e o nome de arquivo do script ou redirecione um caminho de script para `Invoke-Command` . O script deve existir no computador local ou em um diretório que o computador local possa acessar. Use **ArgumentList** para especificar os valores dos parâmetros no script.

Quando você usa esse parâmetro, o PowerShell converte o conteúdo do arquivo de script especificado em um bloco de script, transmite o bloco de script para o computador remoto e o executa no computador remoto.

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, FilePathComputerName, FilePathUri, FilePathVMId, FilePathVMName, FilePathContainerId, FilePathSSHHost, FilePathSSHHostHash
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HideComputerName

Indica que esse cmdlet omite o nome do computador de cada objeto da exibição de saída. Por padrão, o nome do computador que gerou o objeto aparece na exibição.

Este parâmetro afeta somente a exibição de saída. Ele não altera o objeto.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases: HCN

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName

Especifica uma matriz de nomes de computador para uma conexão baseada em Secure Shell (SSH). Isso é semelhante ao parâmetro **ComputerName** , exceto pelo fato de que a conexão com o computador remoto é feita usando SSH em vez de WinRM do Windows.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.String[]
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InDisconnectedSession

Indica que este cmdlet executa um comando ou script em uma sessão desconectada.

Quando você usa o parâmetro **InDisconnectedSession** , o `Invoke-Command` cria uma sessão persistente em cada computador remoto, inicia o comando especificado pelo parâmetro **scriptblock** ou **FilePath** e, em seguida, desconecta-se da sessão. Os comandos continuam a ser executados nas sessões desconectadas. O **InDisconnectedSession** permite que você execute comandos sem manter uma conexão com as sessões remotas. E, como a sessão é desconectada antes de qualquer resultado ser retornado, o **InDisconnectedSession** garante que todos os resultados de comando sejam retornados para a sessão reconectada, em vez de serem divididos entre as sessões.

Você não pode usar **InDisconnectedSession** com o parâmetro **Session** ou o parâmetro **AsJob** .

Comandos que usam **InDisconnectedSession** retornam um objeto **PSSession** que representa a sessão desconectada. Eles não retornam a saída do comando. Para se conectar à sessão desconectada, use os `Connect-PSSession` `Receive-PSSession` cmdlets ou. Para obter os resultados dos comandos que foram executados na sessão, use o `Receive-PSSession` cmdlet. Para executar comandos que geram saída em uma sessão desconectada, defina o valor da opção de sessão **OutputBufferingMode** como **drop**. Se você pretende se conectar à sessão desconectada, defina o tempo limite ocioso na sessão para que ela forneça tempo suficiente para que você se conecte antes de excluir a sessão.

Você pode definir o modo de buffer de saída e o tempo limite ocioso no parâmetro **SessionOption** ou na `$PSSessionOption` variável de preferência. Para obter mais informações sobre as opções de sessão, consulte `New-PSSessionOption` e [about_Preference_Variables](./about/about_preference_variables.md).

Para obter mais informações sobre o recurso de Sessões desconectadas, consulte [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases: Disconnected

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica a entrada para o comando. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

Ao usar o parâmetro **InputObject** , use a `$Input` variável automática no valor do parâmetro **scriptblock** para representar os objetos de entrada.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobName

Especifica um nome amigável para o trabalho em segundo plano. Por padrão, os trabalhos são nomeados `Job<n>` , em que `<n>` é um número ordinal.

Se você usar o parâmetro **JobName** em um comando, o comando será executado como um trabalho e `Invoke-Command` retornará um objeto de trabalho, mesmo que você não inclua **AsJob** no comando.

Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](./About/about_Jobs.md).

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam
Aliases:

Required: False
Position: Named
Default value: Job<n>
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyFilePath

Especifica um caminho de arquivo de chave usado pelo Secure Shell (SSH) para autenticar um usuário em um computador remoto.

O SSH permite que a autenticação do usuário seja executada por meio de chaves públicas e privadas como uma alternativa à autenticação de senha básica. Se o computador remoto estiver configurado para autenticação de chave, esse parâmetro poderá ser usado para fornecer a chave que identifica o usuário.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: SSHHost, FilePathSSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoNewScope

Indica que esse cmdlet executa o comando especificado no escopo atual. Por padrão, `Invoke-Command` o executa comandos em seu próprio escopo.

Esse parâmetro é válido somente em comandos que são executados na sessão atual, ou seja, comandos que omitem ambos os parâmetros **ComputerName** e **Session**.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InProcess
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Especifica a porta de rede no computador remoto que é usada para este comando. Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão. As portas padrão são 5985 (porta do WinRM para HTTP) e 5986 (porta do WinRM para HTTPS).

Antes de usar uma porta alternativa, configure o ouvinte WinRM no computador remoto para escutar na porta. Para configurar o ouvinte, digite os dois comandos a seguir no prompt do PowerShell:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Não use o parâmetro **Port** , a menos que você precise. A porta que está definida no comando se aplica a todos os computadores ou sessões em que o comando é executado. Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.

```yaml
Type: System.Int32
Parameter Sets: ComputerName, FilePathComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteDebug

Usado para executar o comando chamado no modo de depuração na sessão remota do PowerShell.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsAdministrator

Indica que esse cmdlet invoca um comando como administrador.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Especifica os comandos a serem executados. Coloque os comandos entre chaves `{ }` para criar um bloco de script.
Este parâmetro é necessário.

Por padrão, todas as variáveis no comando são avaliadas no computador remoto. Para incluir variáveis locais no comando, use **ArgumentList**.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: InProcess, Session, ComputerName, Uri, VMId, VMName, SSHHost, ContainerId, SSHHostHashParam
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessão

Especifica uma matriz de sessões em que esse cmdlet executa o comando. Insira uma variável que contenha objetos **PSSession** ou um comando que cria ou obtém os objetos **PSSession** , como um `New-PSSession` `Get-PSSession` comando ou.

Quando você cria uma **PSSession**, o PowerShell estabelece uma conexão persistente com o computador remoto. Use uma **PSSession** para executar uma série de comandos relacionados que compartilham dados. Para executar um único comando ou uma série de comandos não relacionados, use o parâmetro **ComputerName** . Para obter mais informações, consulte [about_PSSessions](./About/about_PSSessions.md).

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: FilePathRunspace, Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SESSIONNAME

Especifica um nome amigável para uma sessão desconectada. Você pode usar o nome para fazer referência à sessão em comandos subsequentes, como um `Get-PSSession` comando. Esse parâmetro é válido somente com o parâmetro **InDisconnectedSession**.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.String[]
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionOption

Especifica as opções avançadas para a sessão. Insira um objeto **SessionOption** , como um que você cria usando o `New-PSSessionOption` cmdlet ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.

Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se ele estiver definido. Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.

Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão. No entanto, eles não têm precedência sobre os valores máximos, cotas ou limites definidos na configuração da sessão.

Para obter uma descrição das opções de sessão que incluem os valores padrão, consulte `New-PSSessionOption` . Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md).
Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SSHConnection

Esse parâmetro usa uma matriz de tabelas de hash em que cada tabela de hash contém um ou mais parâmetros de conexão necessários para estabelecer uma conexão de Secure Shell (SSH). O parâmetro **SSHConnection** é útil para criar várias sessões em que cada sessão requer informações de conexão diferentes.

A tabela de hash tem os seguintes membros:

- **Nome do** **computador** (ou hostname)
- **Porta**
- **UserName**
- **KeyFilePath** (ou **IdentityFilePath**)

**ComputerName** (ou **hostname**) é o único par chave-valor necessário.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SSHHostHashParam, FilePathSSHHostHash
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SSHTransport

Indica que a conexão remota é estabelecida usando Secure Shell (SSH).

Por padrão, o PowerShell usa o Windows WinRM para se conectar a um computador remoto. Essa opção força o PowerShell a usar o parâmetro **hostname** para estabelecer uma conexão remota com base em SSH.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.
Se você omite esse parâmetro ou digita um valor 0, o valor padrão, 32, é usado.

O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.

```yaml
Type: System.Int32
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName

Especifica o nome de usuário para a conta usada para executar um comando no computador remoto. O método de autenticação de usuário depende de como o Secure Shell (SSH) é configurado no computador remoto.

Se o SSH estiver configurado para autenticação de senha básica, a senha do usuário será solicitada.

Se o SSH estiver configurado para autenticação de usuário baseada em chave, um caminho de arquivo de chave poderá ser fornecido por meio do parâmetro **keyFilePath** e nenhum prompt de senha ocorrerá. Se o arquivo de chave de usuário do cliente estiver localizado em um local de SSH conhecido, o parâmetro **keyFilePath** não será necessário para a autenticação baseada em chave e a autenticação do usuário ocorrerá automaticamente com base no nome de usuário. Para obter mais informações, consulte a documentação do SSH da sua plataforma sobre a autenticação de usuário baseada em chave.

Esse não é um parâmetro obrigatório. Se o parâmetro **username** não for especificado, o nome de usuário conectado no momento será usado para a conexão.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para estabelecer uma conexão com o computador remoto. Por padrão, o SSL não é usado.

WS-Management criptografa todo o conteúdo do PowerShell transmitido pela rede. O parâmetro **UseSSL** é uma proteção adicional que envia os dados por um https, em vez de http.

Se você usar esse parâmetro, mas o SSL não estiver disponível na porta usada para o comando, o comando falhará.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMId

Especifica uma matriz de IDs de máquinas virtuais.

```yaml
Type: System.Guid[]
Parameter Sets: VMId, FilePathVMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName

Especifica uma matriz de nomes de máquinas virtuais.

```yaml
Type: System.String[]
Parameter Sets: VMName, FilePathVMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subsistema

Especifica o subsistema SSH usado para a nova **PSSession**.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. ScriptBlock

É possível canalizar um comando em um bloco de script para `Invoke-Command` . Use a `$Input` variável automática para representar os objetos de entrada no comando.

## SAÍDAS

### System. Management. Automation. PSRemotingJob, System. Management. Automation. Runspaces. PSSession ou a saída do comando invocado

Esse cmdlet retorna um objeto de trabalho, se você usar o parâmetro **AsJob** . Se você especificar o parâmetro **InDisconnectedSession** , `Invoke-Command` retornará um objeto **PSSession** . Caso contrário, ele retorna a saída do comando invocado, que é o valor do parâmetro **scriptblock** .

## OBSERVAÇÕES

No Windows Vista e versões posteriores do sistema operacional Windows, para usar o parâmetro **ComputerName** do `Invoke-Command` para executar um comando no computador local, você deve executar o PowerShell usando a opção **Executar como administrador** .

Quando você executa comandos em vários computadores, o PowerShell se conecta aos computadores na ordem em que aparecem na lista. No entanto, a saída do comando é exibida na ordem em que ela é recebida dos computadores remotos, o que pode ser diferente.

Os erros resultantes do comando `Invoke-Command` executado são incluídos nos resultados do comando.
Erros que poderiam ser erros de finalização em um comando local são tratados como erros de não finalização em um comando remoto. Essa estratégia garante que os erros de encerramento em um computador não fechem o comando em todos os computadores nos quais ele é executado. Essa prática é utilizada mesmo quando um comando remoto é executado em um único computador.

Se o computador remoto não estiver em um domínio no qual o computador local confia, talvez o computador não consiga autenticar as credenciais do usuário. Para adicionar o computador remoto à lista de hosts confiáveis no WS-Management, use o seguinte comando no `WSMAN` provedor, em que `<Remote-Computer-Name>` é o nome do computador remoto:

`Set-Item -Path WSMan:\Localhost\Client\TrustedHosts -Value \<Remote-Computer-Name\>`

Quando você desconecta uma **PSSession** usando o parâmetro **InDisconnectedSession** , o estado da sessão é **desconectado** e a disponibilidade é **nenhuma**. O valor da propriedade **State** é relativo a sessão atual. Um valor de **desconectado** significa que a **PSSession** não está conectada à sessão atual. No entanto, isso não significa que a **PSSession** seja desconectada de todas as sessões. Ela pode ser conectada a uma sessão diferente. Para determinar se é possível conectar-se ou reconectar-se à sessão, utilize a propriedade **Availability**.

Um valor **Availability** de **None** indica que é possível conectar-se à sessão. Um valor de **ocupado** indica que você não pode se conectar à **PSSession** porque ela está conectada a outra sessão. Para obter mais informações sobre os valores da propriedade **State** de sessões, consulte [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate). Para obter mais informações sobre os valores da propriedade de sessões de **disponibilidade** , consulte [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).

Os parâmetros **hostname** e **SSHConnection** foram incluídos a partir do PowerShell 6,0. Elas foram adicionadas para fornecer comunicação remota do PowerShell com base em Secure Shell (SSH). O PowerShell e o SSH têm suporte em várias plataformas (Windows, Linux, macOS) e a comunicação remota do PowerShell funciona nessas plataformas em que o PowerShell e o SSH estão instalados e configurados. Isso é separado da somente comunicação remota do Windows anterior que é baseada no WinRM e que muitos dos recursos e limitações específicos do WinRM não se aplicam. Por exemplo, cotas baseadas em WinRM, opções de sessão, configuração de ponto de extremidade personalizado e recursos de desconexão/reconexão não têm suporte no momento. Para obter mais informações sobre como configurar a comunicação remota do PowerShell SSH, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

## LINKS RELACIONADOS

[about_PSSessions](./About/about_PSSessions.md)

[about_Remote](./About/about_Remote.md)

[about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md)

[about_Remote_Troubleshooting](./About/about_remote_troubleshooting.md)

[about_Remote_Variables](./About/about_Remote_Variables.md)

[about_Scopes](./About/about_scopes.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Item](../Microsoft.PowerShell.Management/Invoke-Item.md)

[New-PSSession](New-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)

[Provedor WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

