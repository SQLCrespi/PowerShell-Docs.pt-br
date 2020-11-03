---
description: Descreve sessões do PowerShell (PSSessions) e explica como estabelecer uma conexão persistente com um computador remoto.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssessions?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSessions
ms.openlocfilehash: c3221254b3688bb974214c0b6b45f10fcd848bec
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196288"
---
# <a name="about-pssessions"></a>Sobre PSSessions

## <a name="short-description"></a>Descrição breve
Descreve sessões do PowerShell (PSSessions) e explica como estabelecer uma conexão persistente com um computador remoto.

## <a name="long-description"></a>Descrição longa

Para executar comandos do PowerShell em um computador remoto, você pode usar o parâmetro **ComputerName** de um cmdlet ou pode criar uma sessão do PowerShell (PSSession) e executar comandos na PSSession.

Quando você cria uma PSSession, o PowerShell estabelece uma conexão persistente com o computador remoto. Use uma PSSession para executar uma série de comandos relacionados em um computador remoto. Os comandos que são executados na mesma PSSession podem compartilhar dados, como os valores de variáveis, aliases e funções.

Você também pode criar uma PSSession no computador local e executar comandos nela.
Uma PSSession local usa a infraestrutura de comunicação remota do PowerShell para criar e manter a PSSession.

A partir do Windows PowerShell 3,0, as PSSessions são independentes das sessões nas quais elas são criadas. As PSSessions ativas são mantidas no computador remoto (ou no computador na extremidade remota ou no "lado do servidor" da conexão). Como resultado, você pode se desconectar da PSSession e se reconectar a ela mais tarde, a partir do mesmo computador ou de um computador diferente.

Este tópico explica como criar, usar, obter e excluir PSSessions. Para obter informações mais avançadas, consulte [about_PSSession_Details](about_PSSession_Details.md).

Observação: as PSSessions usam a infraestrutura de comunicação remota do PowerShell. Para usar PSSessions, os computadores locais e remotos devem ser configurados para comunicação remota.
Para obter mais informações, consulte [about_Remote_Requirements](about_Remote_Requirements.md).

No Windows Vista e versões posteriores do Windows, para criar uma PSSession em um computador local, você deve iniciar o PowerShell com a opção "executar como administrador".

## <a name="what-is-a-session"></a>O que é uma sessão?

Uma sessão é um ambiente no qual o PowerShell é executado.

Cada vez que você inicia o PowerShell, uma sessão é criada para você e você pode executar comandos na sessão. Você também pode adicionar itens à sua sessão, como módulos e snap-ins, e pode criar itens, como variáveis, funções e aliases. Esses itens existem somente na sessão e são excluídos quando a sessão termina.

Você também pode criar sessões gerenciadas pelo usuário, conhecidas como "sessões do PowerShell" ou "PSSessions", no computador local ou em um computador remoto. Assim como a sessão padrão, você pode executar comandos em uma PSSession e adicionar e criar itens. No entanto, diferentemente da sessão que é iniciada automaticamente, você pode controlar as PSSessions criadas por você. Você pode obter, criar, configurar e removê-los, desconectar-se e reconectá-los e executar vários comandos na mesma PSSession. A PSSession permanece disponível até você excluí-la ou expirar.

Normalmente, você cria uma PSSession para executar uma série de comandos relacionados em um computador remoto. Quando você cria uma PSSession em um computador remoto, o PowerShell estabelece uma conexão persistente com o computador remoto para dar suporte à sessão.

Se você usar o parâmetro **ComputerName** do `Invoke-Command` `Enter-PSSession` cmdlet ou para executar um comando remoto ou para iniciar uma sessão interativa, o PowerShell criará uma sessão temporária no computador remoto e fechará a sessão assim que o comando for concluído ou assim que a sessão interativa terminar. Você não pode controlar essas sessões temporárias e não pode usá-las para mais de um único comando ou uma única sessão interativa.

No PowerShell, a "sessão atual" é a sessão na qual você está trabalhando. A "sessão atual" pode se referir a qualquer sessão, incluindo uma sessão temporária ou uma PSSession.

## <a name="why-use-a-pssession"></a>Por que usar uma PSSession?

Use uma PSSession quando precisar de uma conexão persistente com um computador remoto.
Com uma PSSession, você pode executar uma série de comandos que compartilham dados, como o valor de variáveis, o conteúdo de uma função ou a definição de um alias.

Você pode executar comandos remotos sem criar uma PSSession. Use o parâmetro **ComputerName** de cmdlets habilitados para remoto para executar um único comando ou uma série de comandos não relacionados em um ou vários computadores.

Quando você usa o parâmetro **ComputerName** do `Invoke-Command` ou, o `Enter-PSSession` PowerShell estabelece uma conexão temporária com o computador remoto e fecha a conexão assim que o comando é concluído. Todos os elementos de dados que você criar serão perdidos quando a conexão for fechada.

Outros cmdlets que têm um parâmetro **ComputerName** , como `Get-Eventlog` e `Get-WmiObject` , usam tecnologias de comunicação remota diferentes para coletar dados. Nenhum crie uma conexão persistente como uma PSSession.

## <a name="how-to-create-a-pssession"></a>Como criar uma PSSession

Para criar uma PSSession, use o `New-PSSession` cmdlet. Para criar a PSSession em um computador remoto, use o parâmetro **ComputerName** do `New-PSSession` cmdlet.

Por exemplo, o comando a seguir cria uma nova PSSession no computador Server01.

```powershell
New-PSSession -ComputerName Server01
```

Quando você envia o comando, `New-PSSession` o cria a PSSession e retorna um objeto que representa a PSSession. Você pode salvar o objeto em uma variável ao criar a PSSession ou pode usar um `Get-PSSession` comando para obter a PSSession posteriormente.

Por exemplo, o comando a seguir cria uma nova PSSession no computador Server01 e salva o objeto resultante na variável $ps.

```powershell
$ps = New-PSSession -ComputerName Server01
```

## <a name="how-to-create-pssessions-on-multiple-computers"></a>Como criar PSSessions em vários computadores

Para criar PSSessions em vários computadores, use o parâmetro **ComputerName** do `New-PSSession` cmdlet. Digite os nomes dos computadores remotos em uma lista separada por vírgulas.

Por exemplo, para criar PSSessions nos computadores Server01, Server02 e Server03, digite:

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
```

`New-PSSession` Cria uma PSSession em cada um dos computadores remotos.

## <a name="how-to-get-pssessions"></a>Como obter PSSessions

Para obter as PSSessions que foram criadas na sessão atual, use o `Get-PSSession` cmdlet sem o parâmetro **ComputerName** . `Get-PSSession` Retorna o mesmo tipo de objeto que `New-PSSession` retorna.

O comando a seguir obtém todas as PSSessions que foram criadas na sessão atual.

```powershell
Get-PSSession
```

A exibição padrão de PSSessions mostra sua ID e um nome de exibição padrão. Você pode atribuir um nome de exibição alternativo ao criar a sessão.

```output
Id   Name       ComputerName    State    ConfigurationName
---  ----       ------------    -----    ---------------------
1    Session1   Server01        Opened   Microsoft.PowerShell
2    Session2   Server02        Opened   Microsoft.PowerShell
3    Session3   Server03        Opened   Microsoft.PowerShell
```

Você também pode salvar as PSSessions em uma variável. O comando a seguir obtém as PSSessions e as salva na \$ variável ps123.

```powershell
$ps123 = Get-PSSession
```

Ao usar os cmdlets de PSSession, você pode se referir a uma PSSession por sua ID, por seu nome ou por sua ID de instância (um GUID). O comando a seguir obtém uma PSSession por sua ID e a salva na \$ variável PS01.

```powershell
$ps01 = Get-PSSession -Id 1
```

A partir do Windows PowerShell 3,0, as PSSessions são mantidas no computador remoto. Para obter as PSSessions que você criou em computadores remotos específicos, use o parâmetro **ComputerName** do `Get-PSSession` cmdlet. O comando a seguir obtém as PSSessions que você criou no computador remoto Server01. Isso inclui PSSessions criadas na sessão atual e em outras sessões no computador local ou em outros computadores.

```powershell
Get-PSSession -ComputerName Server01
```

No Windows PowerShell 2,0, `Get-PSSession` obtém somente as PSSessions que foram criadas na sessão atual. Ele não obtém PSSessions que foram criadas em outras sessões ou em outros computadores, mesmo que as sessões estejam conectadas ao e estejam executando comandos no computador local.

## <a name="how-to-run-commands-in-a-pssession"></a>Como executar comandos em uma PSSession

Para executar um comando em uma ou mais PSSessions, use o `Invoke-Command` cmdlet.
Use o parâmetro Session para especificar as PSSessions e o parâmetro **scriptblock** para especificar o comando.

Por exemplo, para executar um `Get-ChildItem` comando ("dir") em cada uma das três PSSessions salvas na variável $ps 123, digite:

```powershell
Invoke-Command -Session $ps123 -ScriptBlock { Get-ChildItem }
```

## <a name="how-to-delete-pssessions"></a>Como excluir PSSessions

Quando você terminar com a PSSession, use o `Remove-PSSession` cmdlet para excluir a PSSession e liberar os recursos que ele estava usando.

```powershell
Remove-PSSession -Session $ps
```

ou

```powershell
Remove-PSSession -Id 1
```

Para remover uma PSSession de um computador remoto, use o parâmetro **ComputerName** do `Remove-PSSession` cmdlet.

```powershell
Remove-PSSession -ComputerName Server01 -Id 1
```

Se você não excluir a PSSession, a PSSession permanecerá disponível para uso até atingir o tempo limite.

Você também pode usar o parâmetro **IdleTimeout** do `New-PSSessionOption` cmdlet para definir um tempo de expiração para uma PSSession ociosa. Para obter mais informações, consulte [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

## <a name="the-pssession-cmdlets"></a>Os cmdlets de PSSession

Para obter uma lista de cmdlets PSSession, digite:

```powershell
Get-Help *-PSSession
```

- Connect-PSSession: conecta uma PSSession à sessão atual
- Disconnect-PSSession: desconecta uma PSSession da sessão atual
- Enter-PSSession: inicia uma sessão interativa
- Exit-PSSession: encerra uma sessão interativa
- Get-PSSession: Obtém as PSSessions na sessão atual
- New-PSSession: cria uma nova PSSession em um computador local ou remoto
- Receive-PSSession: Obtém os resultados dos comandos que foram executados em uma sessão desconectada
- Remove-PSSession: exclui as PSSessions na sessão atual

## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre PSSessions, consulte [about_PSSession_Details](about_PSSession_Details.md).

## <a name="see-also"></a>Consulte Também

[about_Remote](about_Remote.md)

[about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md)

[about_Remote_Requirements](about_Remote_Requirements.md)

[Connect-PSSession](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[Disconnect-PSSession](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession)

[Get-PSSession](xref:Microsoft.PowerShell.Core.Get-PSSession)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Remove-PSSession](xref:Microsoft.PowerShell.Core.Remove-PSSession)
