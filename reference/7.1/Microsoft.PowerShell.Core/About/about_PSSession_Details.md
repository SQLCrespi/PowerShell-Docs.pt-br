---
description: Fornece informações detalhadas sobre as sessões do PowerShell e a função que elas desempenham em comandos remotos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssession_details?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSession_Details
ms.openlocfilehash: 3d6ac25d7f8cac3d0b38cf921382e9a7aaeaf3d6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196335"
---
# <a name="about-pssession-details"></a>Sobre os detalhes da PSSession

## <a name="short-description"></a>Descrição breve
Fornece informações detalhadas sobre as sessões do PowerShell e a função que elas desempenham em comandos remotos.

## <a name="long-description"></a>Descrição longa

Uma sessão é um ambiente no qual o PowerShell é executado. Uma sessão é criada para você sempre que você iniciar o PowerShell. Você pode criar sessões adicionais, chamadas "sessões do PowerShell" ou "PSSessions" no seu computador ou em outro computador.

Ao contrário das sessões que o PowerShell cria para você, você controla e gerencia as PSSessions criadas por você.

As PSSessions desempenham um papel importante na computação remota. Quando você cria uma PSSession que está conectada a um computador remoto, o PowerShell estabelece uma conexão persistente com o computador remoto para dar suporte a PSSession. Você pode usar a PSSession para executar uma série de comandos, funções e scripts que compartilham dados.

Este tópico fornece informações detalhadas sobre sessões e PSSessions no PowerShell. Para obter informações básicas sobre as tarefas que você pode executar com sessões, consulte [about_PSSessions](about_PSSessions.md).

## <a name="about-sessions"></a>Sobre sessões

Tecnicamente, uma sessão é um ambiente de execução no qual o PowerShell é executado. Cada sessão inclui uma instância do mecanismo System. Management. Automation e um programa host no qual o PowerShell é executado. O host pode ser o conhecido console do PowerShell ou outro programa que executa comandos, como Cmd.exe, ou um programa criado para hospedar o PowerShell, como o Ambiente de Script Integrado do Windows PowerShell (ISE). Do ponto de vista do Windows, uma sessão é um processo do Windows no computador de destino.

Cada sessão é configurada de forma independente. Ele inclui suas próprias propriedades, sua própria política de execução e seus próprios perfis. O ambiente que existe quando a sessão é criada persiste durante seu tempo de vida, mesmo se você alterar o ambiente no computador. Todas as sessões são criadas em um escopo global, até mesmo as sessões que você cria em um script.

Você pode executar apenas um comando (ou pipeline de comando) em uma sessão ao mesmo tempo. Um segundo comando executado de forma síncrona (um de cada vez) aguarda até quatro minutos para que o primeiro comando seja concluído. Um segundo comando executado de forma assíncrona (simultânea) falha.

## <a name="about-pssessions"></a>Sobre PSSessions

Uma sessão é criada toda vez que você inicia o PowerShell. E o PowerShell cria sessões temporárias para executar comandos individuais.
No entanto, você também pode criar sessões (chamadas de "sessões do PowerShell" ou "PSSessions") que você controla e gerencia.

As PSSessions são essenciais para os comandos remotos. Se você usar o parâmetro **ComputerName** dos `Invoke-Command` `Enter-PSSession` cmdlets ou, o PowerShell estabelecerá uma sessão temporária para executar o comando e, em seguida, fechará a sessão assim que o comando ou a sessão interativa for concluída.

No entanto, se você usar o `New-PSSession` cmdlet para criar uma PSSession, o PowerShell estabelecerá uma sessão persistente no computador remoto no qual você pode executar vários comandos ou sessões interativas. As PSSessions que você cria permanecem abertas e disponíveis para uso até você excluí-las ou até que você feche a sessão na qual elas foram criadas.

Quando você cria uma PSSession em um computador remoto, o sistema cria um processo do PowerShell no computador remoto e estabelece uma conexão do computador local com o processo no computador remoto. Quando você cria uma PSSession no computador local, o novo processo e as conexões são criados no computador local.

## <a name="when-do-i-need-a-pssession"></a>Quando preciso de uma PSSession?

Os `Invoke-Command` `Enter-PSSession` cmdlets e têm os parâmetros **ComputerName** e **Session** . Você pode usar qualquer um deles para executar um comando remoto.

Use o parâmetro **ComputerName** para executar um único comando ou uma série de comandos não relacionados em um ou vários computadores.

Para executar comandos que compartilham dados, você precisa de uma conexão persistente com o computador remoto. Nesse caso, crie uma PSSession e, em seguida, use o parâmetro **Session** para executar comandos na PSSession.

Muitos outros cmdlets que obtêm dados de computadores remotos, como `Get-Process` ,, `Get-Service` `Get-EventLog` e `Get-WmiObject` têm apenas um parâmetro **ComputerName** . Eles usam tecnologias diferentes da comunicação remota do PowerShell para coletar dados remotamente. Esses cmdlets não têm um parâmetro de **sessão** , mas você pode usar o `Invoke-Command` cmdlet para executar esses comandos em uma PSSession.

## <a name="how-do-i-create-a-pssession"></a>Como faço para criar uma PSSession?

Para criar uma PSSession, use o `New-PSSession` cmdlet. Você pode usar `New-PSSession` o para criar uma PSSession em um computador local ou remoto.

## <a name="can-i-create-a-pssession-on-any-computer"></a>Posso criar uma PSSession em qualquer computador?

Para criar uma PSSession que esteja conectada a um computador remoto, o computador deve ser configurado para comunicação remota no PowerShell. O usuário atual deve ser um membro do grupo Administradores no computador remoto ou o usuário atual deve ser capaz de fornecer as credenciais de um membro do grupo Administradores. Para obter mais informações, consulte [about_Remote_Requirements](about_Remote_Requirements.md).

## <a name="can-i-see-my-pssessions-in-other-sessions"></a>Posso ver minhas PSSessions em outras sessões?

A partir do Windows PowerShell 3,0, o parâmetro **ComputerName** do `Get-PSSession` cmdlet obtém PSSessions que você criou nos computadores remotos especificados.

As PSSessions ativas são mantidas no computador remoto (o "lado do servidor" de uma conexão) e você pode obtê-las de qualquer sessão em qualquer computador.

Por exemplo, se você criar uma PSSession do computador Server01 para o computador Server02 e, em seguida, alternar para o computador Server03, poderá usar um comando como o seguinte para obter a sessão.

```powershell
Get-PSSession -ComputerName Server02
```

Mesmo se você se desconectar da sessão, a sessão será mantida no computador remoto até você excluí-la ou expirar.

No Windows PowerShell 2,0, você pode obter apenas as PSSessions que você criou na sessão atual. Não é possível obter PSSessions que você criou em outras sessões.

Para obter mais informações, consulte [Get-PSSession](xref:Microsoft.PowerShell.Core.Get-PSSession).

## <a name="can-i-see-the-pssessions-that-others-have-created-on-my-computer"></a>Posso ver as PSSessions que outras pessoas criaram no Meu Computador?

Você pode obter e gerenciar apenas as PSSessions que outras pessoas criaram apenas se você puder fornecer as credenciais do usuário que criou a PSSession ou a configuração de sessão que a PSSession usa inclui credenciais RunAs. Caso contrário, você pode obter, conectar-se, usar e gerenciar apenas as PSSessions que você criou.

## <a name="can-i-connect-to-a-pssession-from-a-different-computer"></a>Posso me conectar a uma PSSession de um computador diferente?

A partir do Windows PowerShell 3,0, as PSSessions são independentes das sessões em que foram criadas. As PSSessions ativas são mantidas no computador no remoto ou no "servidor" de uma conexão.

Você pode usar o `Disconnect-PSSession` cmdlet para se desconectar de uma PSSession. A PSSession é desconectada da sessão local, mas é mantida no computador remoto.
Os comandos continuam a ser executados na PSSession desconectada. Você pode fechar o PowerShell e desligar o computador de origem sem interromper a PSSession.

Então, mesmo as horas mais tarde, você pode usar o `Get-PSSession` cmdlet para obter a PSSession e o `Connect-PSSession` cmdlet para se conectar à PSSession a partir de uma nova sessão em um computador diferente.

Para obter mais informações, consulte [about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md).

## <a name="what-happens-to-my-pssession-if-my-computer-stops"></a>O que acontece com minha PSSession se Meu Computador parar?

As PSSessions desconectadas são independentes das sessões em que foram criadas. Se você desconectar uma PSSession e fechar o computador de origem, a PSSession será mantida no computador remoto.

Além disso, o PowerShell tenta recuperar as PSSessions ativas que são desconectadas involuntariamente, por exemplo, por uma reinicialização do computador, uma interrupção de energia temporária ou interrupções de rede. O PowerShell tenta manter ou recuperar o PSSession para um estado aberto, se a sessão de origem ainda estiver disponível ou para um estado desconectado, se não for.

Uma PSSession "ativa" é aquela que está executando comandos. Se uma PSSession estiver conectada (não desconectada) e os comandos estiverem em execução na PSSession quando a sessão conectada for fechada, o PowerShell tentará manter a PSSession no computador remoto. No entanto, se nenhum comando estiver em execução na PSSession, o PowerShell fechará a PSSession quando a sessão conectada fechar.

Para obter mais informações, consulte [about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md).

## <a name="can-i-run-a-background-job-in-a-pssession"></a>Posso executar um trabalho em segundo plano em uma PSSession?

Sim. Um trabalho em segundo plano é um comando que é executado de forma assíncrona em segundo plano sem interagir com a sessão atual. Quando você envia um comando para iniciar um trabalho, o comando retorna um objeto de trabalho, mas o trabalho continua a ser executado em segundo plano até que seja concluído.

Para iniciar um trabalho em segundo plano em um computador local, use o `Start-Job` comando.
Você pode executar o trabalho em segundo plano em uma conexão temporária (usando o parâmetro **ComputerName** ) ou em uma PSSession (usando o parâmetro **Session** ).

Para iniciar um trabalho em segundo plano em um computador remoto, use o `Invoke-Command` cmdlet com seu parâmetro **AsJob** ou use o `Invoke-Command` cmdlet para executar um `Start-Job` comando em um computador remoto. Ao usar o parâmetro **AsJob** , você pode usar os parâmetros **ComputerName** ou **Session** .

Ao usar `Invoke-Command` o para executar um `Start-Job` comando, você deve executar o comando em uma PSSession. Se você usar o parâmetro **ComputerName** , o PowerShell encerrará a conexão quando o objeto de trabalho retornar e o trabalho será interrompido.

Para obter mais informações, consulte [about_Jobs](about_Jobs.md).

## <a name="can-i-run-an-interactive-session"></a>Posso executar uma sessão interativa?

Sim. Para iniciar uma sessão interativa com um computador remoto, use o `Enter-PSSession` cmdlet. Em uma sessão interativa, os comandos que você digita são executados no computador remoto, assim como se você os digitou diretamente no computador remoto.

Você pode executar uma sessão interativa em uma sessão temporária (usando o parâmetro **ComputerName** ) ou em uma PSSession (usando o parâmetro **Session** ).
Se você usar uma PSSession, a PSSession manterá os dados de comandos anteriores e a PSSession manterá todos os dados gerados durante a sessão interativa para uso em comandos posteriores.

Quando você finaliza a sessão interativa, a PSSession permanece aberta e disponível para uso.

Para obter mais informações, consulte [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) e [Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession).

## <a name="must-i-delete-the-pssessions"></a>É necessário excluir as PSSessions?

Sim. Uma PSSession é um processo, que é um ambiente independente que usa memória e outros recursos, mesmo quando você não o está usando. Quando você terminar com uma PSSession, exclua-a. Se você criar várias PSSessions, feche aquelas que você não está usando e mantenha somente aquelas em uso no momento.

Para excluir PSSessions, use o `Remove-PSSession` cmdlet. Ele exclui as PSSessions e libera todos os recursos que estavam usando.

Você também pode usar o parâmetro **IdleTimeOut** de `New-PSSessionOption` para fechar uma PSSession ociosa após um intervalo especificado. Para obter mais informações, consulte [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

Se você salvar um objeto PSSession em uma variável e, em seguida, excluir a PSSession ou deixá-la atingir o tempo limite, a variável ainda conterá o objeto PSSession, mas a PSSession não estará ativa e não poderá ser usada ou reparada.

## <a name="are-all-sessions-and-pssessions-alike"></a>Todas as sessões e PSSessions são semelhantes?

Não. Os desenvolvedores podem criar sessões personalizadas que incluam apenas os cmdlets e provedores selecionados. Se um comando funciona em uma sessão, mas não em outro, pode ser porque a sessão é restrita.

## <a name="see-also"></a>Consulte Também

[about_Jobs](about_Jobs.md)

[about_PSSessions](about_PSSessions.md)

[about_Remote](about_Remote.md)

[about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md)

[about_Remote_Requirements](about_Remote_Requirements.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession)

[Get-PSSession](xref:Microsoft.PowerShell.Core.Get-PSSession)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Remove-PSSession](xref:Microsoft.PowerShell.Core.Remove-PSSession)

