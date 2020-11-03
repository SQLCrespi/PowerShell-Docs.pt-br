---
description: Contém perguntas e respostas sobre a execução de comandos remotos no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_faq?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_FAQ
ms.openlocfilehash: de56c3391dd43106252439e71a1d4bbe1e0082f9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195653"
---
# <a name="about-remote-faq"></a>Perguntas frequentes sobre comunicação remota

## <a name="short-description"></a>Descrição breve
Contém perguntas e respostas sobre a execução de comandos remotos no PowerShell.

## <a name="long-description"></a>Descrição longa

Quando você trabalha remotamente, digita comandos no PowerShell em um computador (conhecido como "computador local"), mas os comandos são executados em outro computador (conhecido como "computador remoto"). A experiência de trabalhar remotamente deve ser muito parecida com o trabalho diretamente no computador remoto.

Observação: para usar a comunicação remota do PowerShell, o computador remoto deve ser configurado para comunicação remota. Para obter mais informações, consulte [about_Remote_Requirements](about_Remote_Requirements.md).

### <a name="must-both-computers-have-powershell-installed"></a>Os dois computadores devem ter o PowerShell instalado?

Sim. Para trabalhar remotamente, os computadores locais e remotos devem ter o PowerShell, o Microsoft .NET Framework e o protocolo WS-Management (Web Services for Management). Todos os arquivos e outros recursos necessários para executar um comando específico devem estar no computador remoto.

Computadores que executam o Windows PowerShell 3,0 e computadores que executam o Windows PowerShell 2,0 podem se conectar entre si remotamente e executar comandos remotos.
No entanto, alguns recursos, como a capacidade de se desconectar de uma sessão e se reconectar a ela, funcionam somente quando ambos os computadores executam o Windows PowerShell 3,0.

Você deve ter permissão para se conectar ao computador remoto, permissão para executar o PowerShell e permissão para acessar armazenamentos de dados (como arquivos e pastas) e o registro no computador remoto.

Para obter mais informações, consulte [about_Remote_Requirements](about_Remote_Requirements.md).

### <a name="how-does-remoting-work"></a>Como funciona a comunicação remota?

Quando você envia um comando remoto, o comando é transmitido pela rede para o mecanismo do PowerShell no computador remoto e é executado no cliente do PowerShell no computador remoto. Os resultados do comando são enviados de volta ao computador local e aparecem na sessão do PowerShell no computador local.

Para transmitir os comandos e receber a saída, o PowerShell usa o protocolo WS-Management. Para obter informações sobre o protocolo WS-Management, consulte [protocolo WS-Management](/windows/win32/winrm/ws-management-protocol) na documentação do Windows.

A partir do Windows PowerShell 3,0, as sessões remotas são armazenadas no computador remoto. Isso permite que você se desconecte da sessão e reconecte-se de uma sessão diferente ou de um computador diferente sem interromper os comandos ou perder o estado.

### <a name="is-powershell-remoting-secure"></a>A comunicação remota do PowerShell é segura?

Quando você se conecta a um computador remoto, o sistema usa as credenciais de nome de usuário e senha no computador local ou as credenciais que você fornece no comando para fazer logon no computador remoto. As credenciais e o restante da transmissão são criptografados.

Para adicionar proteção adicional, você pode configurar o computador remoto para usar protocolo SSL (SSL) em vez de HTTP para escutar solicitações de Gerenciamento Remoto do Windows (WinRM). Em seguida, os usuários podem usar o parâmetro **UseSSL** dos `Invoke-Command` `New-PSSession` `Enter-PSSession` cmdlets, e ao estabelecer uma conexão. Essa opção usa o canal HTTPS mais seguro em vez de HTTP.

### <a name="do-all-remote-commands-require-powershell-remoting"></a>Todos os comandos remotos exigem comunicação remota do PowerShell?

Não. Vários cmdlets têm um parâmetro **ComputerName** que permite que você obtenha objetos do computador remoto.

Esses cmdlets não usam a comunicação remota do PowerShell. Portanto, você pode usá-los em qualquer computador que esteja executando o PowerShell, mesmo se o computador não estiver configurado para comunicação remota do PowerShell ou se o computador não atender aos requisitos de comunicação remota do PowerShell.

Esses cmdlets incluem o seguinte:

- `Get-Process`
- `Get-Service`
- `Get-WinEvent`
- `Get-EventLog`
- `Test-Connection`

Para localizar todos os cmdlets com um parâmetro **ComputerName** , digite:

```powershell
Get-Help * -Parameter ComputerName
# or
Get-Command -ParameterName ComputerName
```

Para determinar se o parâmetro **ComputerName** de um determinado cmdlet requer comunicação remota do PowerShell, consulte a descrição do parâmetro. Para exibir a descrição do parâmetro, digite:

```powershell
Get-Help <cmdlet-name> -Parameter ComputerName
```

Por exemplo:

```powershell
Get-Help Get-Process -Parameter ComputerName
```

Para todos os outros comandos, use o `Invoke-Command` cmdlet.

### <a name="how-do-i-run-a-command-on-a-remote-computer"></a>Como fazer executar um comando em um computador remoto?

Para executar um comando em um computador remoto, use o `Invoke-Command` cmdlet.

Coloque o comando entre chaves ( `{}` ) para torná-lo um bloco de script. Use o parâmetro **scriptblock** do `Invoke-Command` para especificar o comando.

Você pode usar o parâmetro **ComputerName** de `Invoke-Command` para especificar um computador remoto. Ou, você pode criar uma conexão persistente com um computador remoto (uma sessão) e, em seguida, usar o parâmetro de **sessão** do `Invoke-Command` para executar o comando na sessão.

Por exemplo, os comandos a seguir executam um `Get-Process` comando remotamente.

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-Process}

#  - OR -

Invoke-Command -Session $s -ScriptBlock {Get-Process}
```

Para interromper um comando remoto, digite <kbd>Ctrl</kbd> + <kbd>C</kbd>. A solicitação de interrupção é passada para o computador remoto, onde ele encerra o comando remoto.

Para obter mais informações sobre comandos remotos, consulte about_Remote e os tópicos de ajuda para os cmdlets que oferecem suporte a comunicação remota.

### <a name="can-i-just-telnet-into-a-remote-computer"></a>Posso apenas fazer o Telnet em um computador remoto?

Você pode usar o `Enter-PSSession` cmdlet para iniciar uma sessão interativa com um computador remoto.

No prompt do PowerShell, digite:

```powershell
Enter-PSSession <ComputerName>
```

O prompt de comando é alterado para mostrar que você está conectado ao computador remoto.

```
<ComputerName>\C:>
```

Agora, os comandos digitados são executados no computador remoto, como se você os tivesse digitado diretamente no computador remoto.

Para encerrar a sessão interativa, digite:

```powershell
Exit-PSSession
```

Uma sessão interativa é uma sessão persistente que usa o protocolo WS-Management. Não é o mesmo que usar o Telnet, mas fornece uma experiência semelhante.

Para obter mais informações, consulte `Enter-PSSession`.

### <a name="can-i-create-a-persistent-connection"></a>Posso criar uma conexão persistente?

Sim. Você pode executar comandos remotos especificando o nome do computador remoto, seu nome NetBIOS ou seu endereço IP. Ou, você pode executar comandos remotos especificando uma sessão do PowerShell (PSSession) que está conectada ao computador remoto.

Quando você usa o parâmetro **ComputerName** do `Invoke-Command` ou, o `Enter-PSSession` PowerShell estabelece uma conexão temporária. O PowerShell usa a conexão para executar apenas o comando atual e fecha a conexão. Esse é um método muito eficiente para executar um único comando ou vários comandos não relacionados, mesmo em vários computadores remotos.

Quando você usa o `New-PSSession` cmdlet para criar uma PSSession, o PowerShell estabelece uma conexão persistente para a PSSession. Em seguida, você pode executar vários comandos na PSSession, incluindo comandos que compartilham dados.

Normalmente, você cria uma PSSession para executar uma série de comandos relacionados que compartilham dados. Caso contrário, a conexão temporária criada pelo parâmetro **ComputerName** é suficiente para a maioria dos comandos.

Para obter mais informações sobre sessões, consulte about_PSSessions.

### <a name="can-i-run-commands-on-more-than-one-computer-at-a-time"></a>Posso executar comandos em mais de um computador por vez?

Sim. O parâmetro **ComputerName** do `Invoke-Command` cmdlet aceita vários nomes de computador e o parâmetro **Session** aceita várias PSSessions.

Quando você executa um `Invoke-Command` comando, o PowerShell executa os comandos em todos os computadores especificados ou em todas as PSSessions especificadas.

O PowerShell pode gerenciar centenas de conexões remotas simultâneas. No entanto, o número de comandos remotos que você pode enviar pode ser limitado pelos recursos do seu computador e sua capacidade de estabelecer e manter várias conexões de rede.

Para obter mais informações, consulte o exemplo no `Invoke-Command` tópico da ajuda.

### <a name="where-are-my-profiles"></a>Onde estão meus perfis?

Os perfis do PowerShell não são executados automaticamente em sessões remotas, portanto, os comandos que o perfil adiciona não estão presentes na sessão. Além disso, a `$profile` variável automática não é populada em sessões remotas.

Para executar um perfil em uma sessão, use o `Invoke-Command` cmdlet.

Por exemplo, o comando a seguir executa o perfil CurrentUserCurrentHost do computador local na sessão no `$s` .

```
Invoke-Command -Session $s -FilePath $profile
```

O comando a seguir executa o perfil CurrentUserCurrentHost do computador remoto na sessão no `$s` . Como a `$profile` variável não é populada, o comando usa o caminho explícito para o perfil.

```powershell
Invoke-Command -Session $s {
  . "$home\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

Depois de executar esse comando, os comandos que o perfil adiciona à sessão estão disponíveis no `$s` .

Você também pode usar um script de inicialização em uma configuração de sessão para executar um perfil em cada sessão remota que usa a configuração de sessão.

Para obter mais informações sobre perfis do PowerShell, consulte about_Profiles.
Para obter mais informações sobre configurações de sessão, consulte `Register-PSSessionConfiguration` .

### <a name="how-does-throttling-work-on-remote-commands"></a>Como a limitação funciona em comandos remotos?

Para ajudá-lo a gerenciar os recursos em seu computador local, o PowerShell inclui um recurso de limitação por comando que permite limitar o número de conexões remotas simultâneas estabelecidas para cada comando.

O padrão é 32 conexões simultâneas, mas você pode usar o parâmetro **ThrottleLimit** dos cmdlets para definir um limite de limitação personalizado para comandos específicos.

Ao usar o recurso de limitação, lembre-se de que ele é aplicado a cada comando, e não a toda a sessão ou ao computador. Se você estiver executando comandos simultaneamente em várias sessões ou PSSessions, o número de conexões simultâneas será a soma das conexões simultâneas em todas as sessões.

Para localizar cmdlets com um parâmetro **ThrottleLimit** , digite:

```
Get-Help * -Parameter ThrottleLimit
-or-
Get-Command -ParameterName ThrottleLimit
```

### <a name="is-the-output-of-remote-commands-different-from-local-output"></a>A saída de comandos remotos é diferente da saída local?

Quando você usa o PowerShell localmente, você envia e recebe objetos de .NET Framework "ao vivo"; objetos "dinâmicos" são objetos associados a programas reais ou componentes do sistema. Quando você invoca os métodos ou altera as propriedades de objetos dinâmicos, as alterações afetam o programa ou componente real. E, quando as propriedades de um programa ou componente são alteradas, as propriedades do objeto que as representa também são alteradas.

No entanto, como a maioria dos objetos dinâmicos não pode ser transmitida pela rede, o PowerShell "serializa" a maioria dos objetos enviados em comandos remotos, ou seja, converte cada objeto em uma série de elementos de dados XML (linguagem de restrição em XML [CLiXML]) para transmissão.

Quando o PowerShell recebe um objeto serializado, ele converte o XML em um tipo de objeto desserializado. O objeto desserializado é um registro preciso das propriedades do programa ou componente em um momento anterior, mas não é mais "dinâmico", ou seja, não está mais diretamente associado ao componente. E os métodos são removidos porque não são mais eficazes.

Normalmente, você pode usar objetos desserializados da mesma forma que usaria objetos dinâmicos, mas deve estar ciente de suas limitações. Além disso, os objetos retornados pelo `Invoke-Command` cmdlet têm propriedades adicionais que ajudam a determinar a origem do comando.

Alguns tipos de objeto, como objetos DirectoryInfo e GUIDs, são convertidos de volta em objetos dinâmicos quando eles são recebidos. Esses objetos não precisam de tratamento ou formatação especial.

Para obter informações sobre como interpretar e formatar a saída remota, consulte [about_Remote_Output](about_Remote_Output.md).

### <a name="can-i-run-background-jobs-remotely"></a>Posso executar trabalhos em segundo plano remotamente?

Sim. Um trabalho em segundo plano do PowerShell é um comando do PowerShell que é executado de forma assíncrona sem interagir com a sessão. Quando você inicia um trabalho em segundo plano, o prompt de comando retorna imediatamente, e você pode continuar a trabalhar na sessão enquanto o trabalho é executado, mesmo que ele seja executado por um longo período de tempo.

Você pode iniciar um trabalho em segundo plano mesmo que outros comandos estejam em execução porque os trabalhos em segundo plano sempre são executados de forma assíncrona em uma sessão temporária.

Você pode executar trabalhos em segundo plano em um computador local ou remoto. Por padrão, um trabalho em segundo plano é executado no computador local. No entanto, você pode usar o parâmetro **AsJob** do `Invoke-Command` cmdlet para executar qualquer comando remoto como um trabalho em segundo plano. E, você pode usar `Invoke-Command` o para executar um `Start-Job` comando remotamente.

Para obter mais informações sobre trabalhos em segundo plano no PowerShell, consulte [about_Jobs (about_Jobs. MD)] e [about_Remote_Jobs (about_Remote_Jobs. MD)].

### <a name="can-i-run-windows-programs-on-a-remote-computer"></a>Posso executar programas do Windows em um computador remoto?

Você pode usar os comandos remotos do PowerShell para executar programas baseados no Windows em computadores remotos. Por exemplo, você pode executar `Shutdown.exe` ou `Ipconfig.exe` em um computador remoto.

No entanto, você não pode usar comandos do PowerShell para abrir a interface do usuário para qualquer programa em um computador remoto.

Quando você inicia um programa do Windows em um computador remoto, o comando não é concluído e o prompt de comando do PowerShell não retorna, até que o programa seja concluído ou até que você pressione <kbd>Ctrl</kbd> + <kbd>C</kbd> para interromper o comando. Por exemplo, se você executar o `Ipconfig.exe` programa em um computador remoto, o prompt de comando não retornará até que o `Ipconfig.exe` seja concluído.

Se você usar comandos remotos para iniciar um programa que tenha uma interface do usuário, o processo do programa será iniciado, mas a interface do usuário não será exibida. O comando do PowerShell não é concluído e o prompt de comando não retorna até que o processo do programa seja interrompido ou até que você pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>, o que interrompe o comando e interrompe o processo.

Por exemplo, se você usar um comando do PowerShell para executar `Notepad` em um computador remoto, o processo do bloco de notas será iniciado no computador remoto, mas a interface do usuário do bloco de notas não será exibida. Para interromper o comando e restaurar o prompt de comando, pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>.

### <a name="can-i-limit-the-commands-that-users-can-run-remotely-on-my-computer"></a>Posso limitar os comandos que os usuários podem executar remotamente no meu computador?

Sim. Cada sessão remota deve usar uma das configurações de sessão no computador remoto. Você pode gerenciar as configurações de sessão no seu computador (e as permissões para essas configurações de sessão) para determinar quem pode executar comandos remotamente em seu computador e quais comandos eles podem executar.

Uma configuração de sessão configura o ambiente para a sessão. Você pode definir a configuração usando um assembly que implementa uma nova classe de configuração ou usando um script que é executado na sessão. A configuração pode determinar os comandos que estão disponíveis na sessão.
Além disso, a configuração pode incluir configurações que protegem o computador, como configurações que limitam a quantidade de dados que a sessão pode receber remotamente em um único objeto ou comando. Você também pode especificar um descritor de segurança que determina as permissões necessárias para usar a configuração.

O `Enable-PSRemoting` cmdlet cria as configurações de sessão padrão em seu computador: Microsoft. PowerShell, Microsoft. PowerShell. Workflow e Microsoft. powershell32 (somente sistemas operacionais de 64 bits). `Enable-PSRemoting` define o descritor de segurança para a configuração para permitir que somente membros do grupo Administradores no seu computador os utilizem.

Você pode usar os cmdlets de configuração de sessão para editar as configurações de sessão padrão, para criar novas configurações de sessão e para alterar os descritores de segurança de todas as configurações de sessão.

A partir do Windows PowerShell 3,0, o `New-PSSessionConfigurationFile` cmdlet permite que você crie configurações de sessão personalizadas usando um arquivo de texto. O arquivo inclui opções para definir o modo de linguagem e para especificar os cmdlets e módulos que estão disponíveis em sessões que usam a configuração de sessão.

Quando os usuários usam `Invoke-Command` os `New-PSSession` cmdlets,, ou `Enter-PSSession` , eles podem usar o parâmetro **ConfigurationName** para indicar a configuração de sessão usada para a sessão. Além disso, eles podem alterar a configuração padrão usada por suas sessões alterando o valor da `$PSSessionConfigurationName` variável de preferência na sessão.

Para obter mais informações sobre configurações de sessão, consulte a ajuda para os cmdlets de configuração de sessão. Para localizar os cmdlets de configuração de sessão, digite:

```powershell
Get-Command *PSSessionConfiguration
```

### <a name="what-are-fan-in-and-fan-out-configurations"></a>O que são configurações de Fan-in e Fan out?

O cenário de comunicação remota do PowerShell mais comum que envolve vários computadores é a configuração de um para muitos, na qual um computador local (o computador do administrador) executa comandos do PowerShell em vários computadores remotos. Isso é conhecido como o cenário de "Fan-out".

No entanto, em algumas empresas, a configuração é muitos para um, em que muitos computadores cliente se conectam a um único computador remoto que está executando o PowerShell, como um servidor de arquivos ou um quiosque. Isso é conhecido como a configuração "Fan-in".

A comunicação remota do PowerShell dá suporte a configurações de Fan-out e de Fan-in.

Para a configuração de Fan-out, o PowerShell usa o protocolo WS-Management (Web Services for Management) e o serviço WinRM que dá suporte à implementação da Microsoft do WS-Management. Quando um computador local se conecta a um computador remoto, WS-Management estabelece uma conexão e usa um plug-in para o PowerShell para iniciar o processo de host do PowerShell (Wsmprovhost.exe) no computador remoto. O usuário pode especificar uma porta alternativa, uma configuração de sessão alternativa e outros recursos para personalizar a conexão remota.

Para dar suporte à configuração "Fan-in", o PowerShell usa o IIS (serviços de informações da Internet) para hospedar o WS-Management, carregar o plug-in do PowerShell e iniciar o PowerShell. Nesse cenário, em vez de iniciar cada sessão do PowerShell em um processo separado, todas as sessões do PowerShell são executadas no mesmo processo de host.

O gerenciamento remoto de hospedagem e de Fan-in do IIS não tem suporte no Windows XP ou no Windows Server 2003.

Em uma configuração de Fan-in, o usuário pode especificar um URI de conexão e um ponto de extremidade HTTP, incluindo o transporte, o nome do computador, a porta e o nome do aplicativo.
O IIS encaminha todas as solicitações com um nome de aplicativo especificado para o aplicativo. O padrão é WS-Management, que pode hospedar o PowerShell.

Você também pode especificar um mecanismo de autenticação e proibir ou permitir o redirecionamento de pontos de extremidade HTTP e HTTPS.

### <a name="can-i-test-remoting-on-a-single-computer-not-in-a-domain"></a>Posso testar a comunicação remota em um único computador que não está em um domínio?

Sim. A comunicação remota do PowerShell está disponível mesmo quando o computador local não está em um domínio. Você pode usar os recursos de comunicação remota para se conectar a sessões e criar sessões no mesmo computador. Os recursos funcionam da mesma forma que quando você se conecta a um computador remoto.

Para executar comandos remotos em um computador em um grupo de trabalho, altere as seguintes configurações do Windows no computador.

Cuidado: essas configurações afetam todos os usuários no sistema e podem tornar o sistema mais vulnerável a um ataque mal-intencionado. Tome cuidado ao fazer essas alterações.

- Windows Vista, Windows 7, Windows 8:

  Crie a seguinte entrada de registro e, em seguida, defina seu valor como 1: LocalAccountTokenFilterPolicy em ` HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`

  Você pode usar o seguinte comando do PowerShell para adicionar essa entrada:

    ```powershell
    $parameters = @{
      Path='HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System'
      Name='LocalAccountTokenFilterPolicy'
      propertyType='DWord'
      Value=1
    }
    New-ItemProperty @parameters
    ```

- Windows Server 2003, Windows Server 2008, Windows Server 2012, Windows Server 2012 R2:

  Nenhuma alteração é necessária porque a configuração padrão da política "acesso à rede: modelo de compartilhamento e segurança para contas locais" é "clássica". Verifique a configuração caso ela tenha sido alterada.

### <a name="can-i-run-remote-commands-on-a-computer-in-another-domain"></a>Posso executar comandos remotos em um computador em outro domínio?

Sim. Normalmente, os comandos são executados sem erros, embora talvez seja necessário usar o parâmetro **Credential** dos `Invoke-Command` `New-PSSession` cmdlets, ou `Enter-PSSession` para fornecer as credenciais de um membro do grupo Administradores no computador remoto. Isso às vezes é necessário mesmo quando o usuário atual é membro do grupo Administradores nos computadores locais e remotos.

No entanto, se o computador remoto não estiver em um domínio no qual o computador local confia, talvez o computador remoto não consiga autenticar as credenciais do usuário.

Para habilitar a autenticação, use o comando a seguir para adicionar o computador remoto à lista de hosts confiáveis para o computador local no WinRM. Digite o comando no prompt do PowerShell.

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value <Remote-computer-name>
```

Por exemplo, para adicionar o computador Server01 à lista de hosts confiáveis no computador local, digite o seguinte comando no prompt do PowerShell:

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value Server01
```

### <a name="does-powershell-support-remoting-over-ssh"></a>O PowerShell dá suporte a comunicação remota por SSH?

Sim. Para obter mais informações, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

## <a name="see-also"></a>Confira também

[about_Remote](about_Remote.md)

[about_Profiles](about_Profiles.md)

[about_PSSessions](about_PSSessions.md)

[about_Remote_Jobs](about_Remote_Jobs.md)

[about_Remote_Variables](about_Remote_Variables.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)
