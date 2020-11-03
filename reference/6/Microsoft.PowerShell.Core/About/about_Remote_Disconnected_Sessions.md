---
description: Explica como desconectar e reconectar-se a uma sessão do PowerShell (PSSession).
keywords: powershell, cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_disconnected_sessions?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Disconnected_Sessions
ms.openlocfilehash: 2f352ab123618f1ab9617e9d300f10f7a5e5928a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195654"
---
# <a name="about-remote-disconnected-sessions"></a>Sobre sessões desconectadas remotas

## <a name="short-description"></a>Descrição breve

Explica como desconectar e reconectar-se a uma sessão do PowerShell (PSSession).

## <a name="long-description"></a>Descrição longa

A partir do PowerShell 3,0, você pode se desconectar de uma PSSession e reconectar-se à PSSession no mesmo computador ou em um computador diferente. O estado da sessão é mantido e os comandos na PSSession continuam a ser executados enquanto a sessão está desconectada.

O recurso de sessões desconectadas só estará disponível quando o computador remoto estiver executando o PowerShell 3,0 ou uma versão posterior.

O recurso de sessões desconectadas permite fechar a sessão na qual uma PSSession foi criada e até mesmo fechar o PowerShell e desligar o computador, sem interromper os comandos em execução na PSSession. As sessões desconectadas são úteis para executar comandos que levam um longo tempo para serem concluídas e fornece a flexibilidade de tempo e dispositivo que os profissionais de ti exigem.

Não é possível desconectar-se de uma sessão interativa que é iniciada usando o `Enter-PSSession` cmdlet.

Você pode usar sessões desconectadas para gerenciar PSSessions que foram desconectadas involuntariamente como resultado de uma interrupção de computador ou rede.

No uso do mundo real, o recurso de sessões desconectadas permite que você comece a resolver um problema, volte a sua atenção para um problema de prioridade mais alta e, em seguida, retome o trabalho na solução, mesmo em um computador diferente em um local diferente.

## <a name="disconnected-session-cmdlets"></a>Cmdlets de sessão desconectada

Os cmdlets a seguir dão suporte ao recurso de sessões desconectadas:

- `Connect-PSSession`: Conecta-se a uma PSSession desconectada.
- `Disconnect-PSSession`: Desconecta uma PSSession.
- `Get-PSSession`: Obtém PSSessions no computador local ou em computadores remotos.
- `Receive-PSSession`: Obtém os resultados dos comandos que foram executados em sessões desconectadas.
- `Invoke-Command`: O parâmetro **InDisconnectedSession** cria uma PSSession e desconecta-se imediatamente.

## <a name="how-the-disconnected-sessions-feature-works"></a>Como funciona o recurso de sessões desconectadas

A partir do PowerShell 3,0, as PSSessions são independentes das sessões nas quais elas são criadas. As PSSessions ativas são mantidas no computador remoto ou no **lado do servidor** da conexão, mesmo que a sessão na qual a PSSession foi criada seja fechada e o computador de origem seja desligado ou desconectado da rede.

No PowerShell 2,0, a PSSession é excluída do computador remoto quando é desconectada da sessão de origem ou a sessão na qual ela foi criada termina.

Quando você desconecta uma PSSession, a PSSession permanece ativa e é mantida no computador remoto. O estado da sessão muda de **sendo executado** para **desconectado** . Você pode se reconectar a uma PSSession desconectada da sessão atual ou de uma sessão diferente no mesmo computador ou em um computador diferente. O computador remoto que mantém a sessão deve estar em execução e estar conectado à rede.

Os comandos em uma PSSession desconectada continuam a ser executados sem interrupções no computador remoto até que o comando seja concluído ou o buffer de saída seja preenchido. Para impedir que um buffer de saída completo suspenda um comando, use o parâmetro **OutputBufferingMode** dos `Disconnect-PSSession` `New-PSSessionOption` `New-PSTransportOption` cmdlets, ou.

As sessões desconectadas são mantidas no estado desconectado no computador remoto. Eles estão disponíveis para você se reconectar, até que você exclua a PSSession, como usando o `Remove-PSSession` cmdlet ou até que o tempo limite de ociosidade da PSSession expire. Você pode ajustar o tempo limite de ociosidade de uma PSSession usando os parâmetros **IdleTimeoutSec** ou **IdleTimeout** dos `Disconnect-PSSession` `New-PSSessionOption` `New-PSTransportOption` cmdlets, ou.

Outro usuário pode se conectar a PSSessions que você criou, mas somente se eles puderem fornecer as credenciais que foram usadas para criar a sessão ou usar as `RunAs` credenciais da configuração de sessão.

## <a name="how-to-get-pssessions"></a>Como obter PSSessions

A partir do PowerShell 3,0, o `Get-PSSession` cmdlet obtém PSSessions no computador local e nos computadores remotos. Ele também pode obter PSSessions que foram criadas na sessão atual.

Para obter as PSSessions no computador local ou nos computadores remotos, use os parâmetros **ComputerName** ou **conexãouri** . Sem parâmetros, `Get-PSSession` Obtém PSSession que foram criadas na sessão local, independentemente de onde elas forem encerradas.

Ao obter as PSSessions, lembre-se de procurar por elas no computador no qual elas são mantidas, ou seja, o computador remoto ou **do lado do servidor** .

Por exemplo, se você criar uma PSSession para o computador Server01, obtenha a sessão do computador Server01. Se você criar uma PSSession de outro computador para o computador local, obtenha a sessão do computador local.

A seqüência de comandos a seguir mostra como o `Get-PSSession` funciona.

O primeiro comando cria uma sessão para o computador Server01. A sessão reside no computador Server01.

```powershell
New-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

Para obter a sessão, use o parâmetro **ComputerName** de `Get-PSSession` com um valor de Server01.

```powershell
Get-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

Se o valor do parâmetro **ComputerName** de `Get-PSSession` for localhost, o `Get-PSSession` obterá PSSessions que terminam em e são mantidos no computador local. Ele não obtém PSSessions no computador Server01, mesmo que eles tenham sido iniciados no computador local.

```powershell
Get-PSSession -ComputerName localhost
```

Para obter as sessões que foram criadas na sessão atual, use o `Get-PSSession` cmdlet sem parâmetros. Neste exemplo, `Get-PSSession` Obtém a PSSession que foi criada na sessão atual e conecta-se ao computador Server01.

```powershell
Get-PSSession
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-disconnect-sessions"></a>Como desconectar sessões

Para desconectar uma PSSession, use o `Disconnect-PSSession` cmdlet. Para identificar a PSSession, use o parâmetro **Session** ou o pipeline a PSSession dos `New-PSSession` `Get-PSSession` cmdlets ou para `Disconnect-PSSession` .

O comando a seguir desconecta a PSSession para o computador Server01.
Observe que o valor da propriedade **State** está **desconectado** e a **disponibilidade** é **None** .

```powershell
Get-PSSession -ComputerName Server01 | Disconnect-PSSession
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 2 Session2  Server01      Disconnected  Microsoft.PowerShell          None
```

Para criar uma sessão desconectada, use o parâmetro **InDisconnectedSession** do `Invoke-Command` cmdlet. Ele cria uma sessão, inicia o comando e se desconecta imediatamente, antes que o comando possa retornar qualquer saída.

O comando a seguir executa um `Get-WinEvent` comando em uma sessão desconectada no computador remoto Server02.

```powershell
Invoke-Command -ComputerName Server02 -InDisconnectedSession -ScriptBlock {
   Get-WinEvent -LogName "*PowerShell*" }
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 4 Session3  Server02      Disconnected  Microsoft.PowerShell          None
```

## <a name="how-to-connect-to-disconnected-sessions"></a>Como se conectar a sessões desconectadas

Você pode se conectar a qualquer PSSession desconectada disponível da sessão na qual você criou a PSSession ou de outras sessões no computador local ou em outros computadores.

Você pode criar uma PSSession, executar comandos na PSSession, desconectar-se da PSSession, fechar o PowerShell e desligar o computador. Horas depois, você pode abrir um computador diferente, obter a PSSession, conectar-se a ele e obter os resultados dos comandos que foram executados na PSSession enquanto ele estava desconectado. Em seguida, você pode executar mais comandos na sessão.

Para conectar uma PSSession desconectada, use o `Connect-PSSession` cmdlet. Use os parâmetros **ComputerName** ou **conexãouri** para identificar a PSSession ou o pipeline a PSSession de `Get-PSSession` para `Connect-PSSession` .

O comando a seguir obtém as sessões no computador Server02. A saída inclui duas sessões desconectadas, ambas disponíveis.

```powershell
Get-PSSession -ComputerName Server02
```

```Output
Id Name      ComputerName   State         ConfigurationName     Availability
-- ----      ------------   -----         -----------------     ------------
 2 Session2  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
 4 Session3  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
```

O comando a seguir se conecta ao Session2. A PSSession agora está aberta e disponível.

```powershell
Connect-PSSession -ComputerName Server02 -Name Session2
```

```Output
Id Name      ComputerName    State    ConfigurationName     Availability
-- ----      ------------    -----    -----------------     ------------
 2 Session2  juneb-srv8320   Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-get-the-results"></a>Como obter os resultados

Para obter os resultados dos comandos que foram executados em uma PSSession desconectada, use o `Receive-PSSession` cmdlet.

Você pode usar `Receive-PSSession` em vez de usar o `Connect-PSSession` cmdlet. Se a sessão já estiver reconectada, `Receive-PSSession` o obterá os resultados dos comandos que foram executados quando a sessão foi desconectada. Se a PSSession ainda estiver desconectada, `Receive-PSSession` conecta-se a ela e obtém os resultados dos comandos que foram executados enquanto ele estava desconectado.

`Receive-PSSession` pode retornar os resultados em um trabalho (de modo assíncrono) ou para o programa de host (de forma síncrona). Use o parâmetro **outtarget** para selecionar o **trabalho** ou o **host** . O valor padrão é **host** . No entanto, se o comando que está sendo recebido tiver sido iniciado na sessão atual como um **trabalho** , ele será retornado como um **trabalho** por padrão.

O comando a seguir usa o `Receive-PSSession` cmdlet para se conectar à PSSession no computador Server02 e obter os resultados do `Get-WinEvent` comando que foi executado na sessão Session3. O comando usa o parâmetro **outtarget** para obter os resultados em um **trabalho** .

```powershell
Receive-PSSession -ComputerName Server02 -Name Session3 -OutTarget Job
```

```Output
Id   Name   PSJobTypeName   State         HasMoreData     Location
--   ----   -------------   -----         -----------     --------
 3   Job3   RemoteJob       Running       True            Server02
```

Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.

```powershell
Get-Job | Receive-Job -Keep
```

```Output
ProviderName: PowerShell

TimeCreated             Id LevelDisplayName Message     PSComputerName
-----------             -- ---------------- -------     --------------
5/14/2012 7:26:04 PM   400 Information      Engine stat Server02
5/14/2012 7:26:03 PM   600 Information      Provider "W Server02
5/14/2012 7:26:03 PM   600 Information      Provider "C Server02
5/14/2012 7:26:03 PM   600 Information      Provider "V Server02
```

## <a name="state-and-availability-properties"></a>Propriedades de estado e disponibilidade

As propriedades de **estado** e **disponibilidade** de uma PSSession desconectada informam se a sessão está disponível para que você se reconecte a ela.

Quando uma PSSession é conectada à sessão atual, seu estado é **aberto** e sua disponibilidade está **disponível** . Quando você se desconecta da PSSession, o estado de PSSession é **desconectado** e sua disponibilidade é **nenhuma** .

O valor da propriedade **State** é relativo a sessão atual. Um valor de **desconectado** significa que a PSSession não está conectada à sessão atual. Mas, não significa que PSSession está desconectado de todas as sessões. Ela pode ser conectada a uma sessão diferente.

Para determinar se você pode se conectar ou reconectar-se à PSSession, use a propriedade de **disponibilidade** . Um valor de **None** indica que você pode se conectar à sessão. Um valor de **ocupado** indica que você não pode se conectar à PSSession porque ela está conectada a outra sessão.

O exemplo a seguir é executado em duas sessões do PowerShell no mesmo computador.
Observe que os valores de alteração das propriedades **State** e **Availability** em cada sessão como PSSession são desconectados e reconectados.

```powershell
# Session 1
New-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30 -Name Test | Disconnect-PSSession
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Connect-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
3 Test    Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```Output
# Idle Timeout
```

As sessões desconectadas são mantidas no computador remoto até que você as exclua, como usando o `Remove-PSSession` cmdlet, ou elas atingem o tempo limite. A propriedade **IdleTimeout** de uma PSSession determina por quanto tempo uma sessão desconectada é mantida antes de ser excluída.

As PSSessions ficam ociosas quando o **thread de pulsação** não recebe nenhuma resposta.
Desconectar uma sessão a torna ociosa e inicia o relógio de **IdleTimeout** , mesmo que os comandos ainda estejam em execução na sessão desconectada. O PowerShell considera as sessões desconectadas como ativas, mas ociosas.

Ao criar e desconectar sessões, verifique se o tempo limite de ociosidade na PSSession é longo o suficiente para manter a sessão para suas necessidades, mas não tanto tempo que consome recursos desnecessários no computador remoto.

A propriedade **IdleTimeoutMs** da configuração de sessão determina o tempo limite de ociosidade padrão de sessões que usam a configuração de sessão. Você pode substituir o valor padrão, mas o valor que você usa não pode exceder a propriedade **MaxIdleTimeoutMs** da configuração de sessão.

Para localizar o valor dos valores **IdleTimeoutMs** e **MaxIdleTimeoutMs** de uma configuração de sessão, use o seguinte formato de comando.

```powershell
Get-PSSessionConfiguration |
  Format-Table Name, IdleTimeoutMs, MaxIdleTimeoutMs
```

Você pode substituir o valor padrão na configuração da sessão e definir o tempo limite de ociosidade de uma PSSession ao criar uma PSSession e quando você se desconecta.

Se você for um membro do grupo Administradores no computador remoto, poderá criar e alterar as propriedades **IdleTimeoutMs** e **MaxIdleTimeoutMs** de configurações de sessão.

## <a name="idle-timeout-values"></a>Valores de tempo limite de ociosidade

O valor de tempo limite de ociosidade de configurações de sessão e opções de sessão é em milissegundos. O valor de tempo limite de ociosidade de sessões e opções de configuração de sessão é em segundos.

Você pode definir o tempo limite de ociosidade de uma PSSession ao criar a PSSession ( `New-PSSession` , `Invoke-Command` ) e quando você se desconecta dela ( `Disconnect-PSSession` ). No entanto, não é possível alterar o valor de **IdleTimeout** quando você se conecta a PSSession ( `Connect-PSSession` ) ou Get Results ( `Receive-PSSession` ).

Os `Connect-PSSession` `Receive-PSSession` cmdlets e têm um parâmetro **SessionOption** que usa um objeto **SessionOption** , como um retornado pelo `New-PSSessionOption` cmdlet. O valor de **IdleTimeout** no objeto **SessionOption** e o valor **IdleTimeout** na `$PSSessionOption` variável de preferência não alteram o valor de **IdleTimeout** de PSSession em um `Connect-PSSession` `Receive-PSSession` comando ou.

Para criar uma PSSession com um valor de tempo limite ocioso específico, crie uma `$PSSessionOption` variável de preferência. Defina o valor da propriedade **IdleTimeout** para o valor desejado (em milissegundos).

Quando você cria PSSessions, os valores na `$PSSessionOption` variável têm precedência sobre os valores na configuração da sessão.

Por exemplo, o comando a seguir define um tempo limite de ociosidade de 48 horas:

```powershell
$PSSessionOption = New-PSSessionOption -IdleTimeoutMSec 172800000
```

Para criar uma PSSession com um valor de tempo limite ocioso específico, use o parâmetro **IdleTimeoutMSec** do `New-PSSessionOption` cmdlet. Em seguida, use a opção de sessão no valor do parâmetro **SessionOption** dos `New-PSSession` `Invoke-Command` cmdlets ou.

Os valores definidos ao criar a sessão têm precedência sobre os valores definidos na `$PSSessionOption` variável de preferência e a configuração da sessão.

Por exemplo:

```powershell
$o = New-PSSessionOption -IdleTimeoutMSec 172800000
New-PSSession -SessionOption $o
```

Para alterar o tempo limite de ociosidade de uma PSSession ao desconectar, use o parâmetro **IdleTimeoutSec** do `Disconnect-PSSession` cmdlet.

Por exemplo:

```powershell
Disconnect-PSSession -IdleTimeoutSec 172800
```

Para criar uma configuração de sessão com um tempo limite de ociosidade específico e o tempo limite de ociosidade máximo, use os parâmetros **IdleTimeoutSec** e **MaxIdleTimeoutSec** do `New-PSTransportOption` cmdlet. Em seguida, use a opção Transport no valor do parâmetro **TransportOption** de `Register-PSSessionConfiguration` .

Por exemplo:

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

Para alterar o tempo limite de ociosidade padrão e o tempo limite máximo de ociosidade de uma configuração de sessão, use os parâmetros **IdleTimeoutSec** e **MaxIdleTimeoutSec** do `New-PSTransportOption` cmdlet. Em seguida, use a opção Transport no valor do parâmetro **TransportOption** de `Set-PSSessionConfiguration` .

Por exemplo:

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="output-buffering-mode"></a>Modo de buffer de saída

O modo de buffer de saída de uma PSSession determina como a saída do comando é gerenciada quando o buffer de saída da PSSession está cheio.

Em uma sessão desconectada, o modo de buffer de saída determina efetivamente se o comando continua a ser executado enquanto a sessão está desconectada.

Os valores válidos são os seguintes:

- **Bloquear** . Quando o buffer de saída está cheio, a execução é suspensa até que o buffer esteja limpo. O valor padrão.
- **Drop** . Quando o buffer de saída está cheio, a execução continua. À medida que a nova saída é gerada, a saída mais antiga é descartada.

O **bloqueio** preserva os dados, mas pode interromper o comando. Um valor de **Drop** permite que o comando ser concluído, embora os dados possam ser perdidos. Ao usar o valor **Drop** , redirecione a saída do comando para um arquivo no disco. Esse valor é recomendado para sessões desconectadas.

A propriedade **OutputBufferingMode** da configuração de sessão determina o modo de buffer de saída padrão de sessões que usam a configuração de sessão.

Para localizar o valor de uma configuração de sessão do **OutputBufferingMode** , você pode usar qualquer um dos seguintes formatos de comando:

```powershell
(Get-PSSessionConfiguration <ConfigurationName>).OutputBufferingMode
```

```powershell
Get-PSSessionConfiguration | Format-Table Name, OutputBufferingMode
```

Você pode substituir o valor padrão na configuração da sessão e definir o modo de buffer de saída de uma PSSession quando você cria uma PSSession, quando você se desconecta e quando você se reconecta.

Se você for um membro do grupo Administradores no computador remoto, poderá criar e alterar o modo de buffer de saída de configurações de sessão.

Para criar uma PSSession com um modo de buffer de saída de **drop** , crie uma `$PSSessionOption` variável de preferência na qual o valor da propriedade **OutputBufferingMode** seja **drop** .

Quando você cria PSSessions, os valores na `$PSSessionOption` variável têm precedência sobre os valores na configuração da sessão.

Por exemplo:

```powershell
$PSSessionOption = New-PSSessionOption -OutputBufferingMode Drop
```

Para criar uma PSSession com um modo de buffer de saída de **drop** , use o parâmetro **OutputBufferingMode** do `New-PSSessionOption` cmdlet para criar uma opção de sessão com um valor de **drop** . Em seguida, use a opção de sessão no valor do parâmetro **SessionOption** dos `New-PSSession` `Invoke-Command` cmdlets ou.

Os valores definidos ao criar a sessão têm precedência sobre os valores definidos na `$PSSessionOption` variável de preferência e a configuração da sessão.

Por exemplo:

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
New-PSSession -SessionOption $o
```

Para alterar o modo de buffer de saída de uma PSSession ao desconectar, use o parâmetro **OutputBufferingMode** do `Disconnect-PSSession` cmdlet.

Por exemplo:

```powershell
Disconnect-PSSession -OutputBufferingMode Drop
```

Para alterar o modo de buffer de saída de uma PSSession ao reconectar, use o parâmetro **OutputBufferingMode** do `New-PSSessionOption` cmdlet para criar uma opção de sessão com um valor de **drop** . Em seguida, use a opção de sessão no valor do parâmetro **SessionOption** de `Connect-PSSession` ou `Receive-PSSession` .

Por exemplo:

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
Connect-PSSession -ComputerName Server01 -Name Test -SessionOption $o
```

Para criar uma configuração de sessão com um modo de **descarte** de buffer de saída padrão, use o parâmetro **OutputBufferingMode** do `New-PSTransportOption` cmdlet para criar um objeto de opção de transporte com um valor de **drop** . Em seguida, use a opção Transport no valor do parâmetro **TransportOption** de `Register-PSSessionConfiguration` .

Por exemplo:

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

Para alterar o modo de buffer de saída padrão de uma configuração de sessão, use o parâmetro **OutputBufferingMode** do `New-PSTransportOption` cmdlet para criar uma opção de transporte com um valor de **drop** . Em seguida, use a opção Transport no valor do parâmetro **SessionOption** de `Set-PSSessionConfiguration` .

Por exemplo:

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="disconnecting-loopback-sessions"></a>Desconectando sessões de loopback

Sessões de loopback, ou sessões locais, são PSSessions que se originam e terminam no mesmo computador. Assim como outras PSSessions, as sessões de loopback ativas são mantidas no computador na extremidade remota da conexão (o computador local), para que você possa se desconectar e reconectar-se a sessões de loopback.

Por padrão, as sessões de loopback são criadas com um token de segurança de rede que não permite que os comandos sejam executados na sessão para acessar outros computadores. Você pode se reconectar a sessões de loopback que têm um token de segurança de rede de qualquer sessão no computador local ou em um computador remoto.

No entanto, se você **EnableNetworkAccess** usar o parâmetro EnableNetworkAccess `New-PSSession` do `Enter-PSSession` cmdlet,, ou `Invoke-Command` , a sessão de loopback será criada com um token de segurança interativo. O token interativo permite que os comandos executados na sessão de loopback obtenham dados de outros computadores.

Você pode desconectar sessões de loopback com tokens interativos e, em seguida, reconectá-las da mesma sessão ou de uma sessão diferente no mesmo computador.
No entanto, para impedir o acesso mal-intencionado, você pode se reconectar a sessões de loopback com tokens interativos somente do computador no qual elas foram criadas.

## <a name="waiting-for-jobs-in-disconnected-sessions"></a>Aguardando trabalhos em sessões desconectadas

O `Wait-Job` cmdlet aguarda até que um trabalho seja concluído e, em seguida, retorna ao prompt de comando ou ao próximo comando. Por padrão, `Wait-Job` retorna se a sessão na qual um trabalho está sendo executado está desconectada. Para instruir o `Wait-Job` cmdlet a aguardar até que a sessão seja reconectada, no estado **aberto** , use o parâmetro **Force** . Para obter mais informações, consulte [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job).

## <a name="robust-sessions-and-unintentional-disconnection"></a>Sessões robustas e desconexão não intencional

Uma PSSession pode ser desconectada de forma não intencional devido a uma falha no computador ou à interrupção da rede. O PowerShell tenta recuperar a PSSession, mas seu sucesso depende da gravidade e da duração da causa.

O estado de uma PSSession desconectada involuntariamente pode ser **rompido** ou **fechado** , mas também pode ser **desconectado** . Se o valor do **estado** for **desconectado** , você poderá usar as mesmas técnicas para gerenciar a PSSession como faria se a sessão fosse desconectada intencionalmente. Por exemplo, você pode usar o `Connect-PSSession` cmdlet para se reconectar à sessão e ao `Receive-PSSession` cmdlet para obter resultados de comandos que foram executados enquanto a sessão foi desconectada.

Se você fechar (sair) a sessão na qual uma PSSession foi criada enquanto os comandos estão em execução na PSSession, o PowerShell manterá a PSSession no estado **desconectado** no computador remoto. Se você fechar (sair) a sessão na qual uma PSSession foi criada, mas nenhum comando estiver sendo executado na PSSession, o PowerShell não tentará manter a PSSession.

## <a name="see-also"></a>Confira também

[about_Jobs](about_Jobs.md)

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[about_PSSessions](about_PSSessions.md)

[about_Session_Configurations](about_Session_Configurations.md)

[Connect-PSSession](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[Disconnect-PSSession](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[Get-PSSession](xref:Microsoft.PowerShell.Core.Get-PSSession)

[Receive-PSSession](xref:Microsoft.PowerShell.Core.Receive-PSSession)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
