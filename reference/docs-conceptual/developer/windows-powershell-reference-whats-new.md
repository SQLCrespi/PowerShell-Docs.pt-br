---
title: Referência do Windows PowerShell-novidades
ms.date: 09/13/2016
ms.topic: article
ms.openlocfilehash: 364d081ddf2f87ceeaa47732266a35f4a126246f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366085"
---
# <a name="whats-new"></a>Novidades

O Windows PowerShell 2,0 fornece os novos recursos a seguir para uso na criação de cmdlets, provedores e aplicativos de host.

## <a name="modules"></a>Módulos

Agora você pode empacotar e distribuir soluções do Windows PowerShell usando módulos. Os módulos permitem particionar, organizar e abstrair o código do Windows PowerShell em unidades independentes e reutilizáveis. Para obter mais informações sobre módulos, consulte escrevendo um módulo do Windows PowerShell.

## <a name="the-powershell-class"></a>A classe do PowerShell

A classe PowerShell fornece uma solução mais simples para a criação de aplicativos, conhecidos como aplicativos host, que executam comandos programaticamente. Essa classe permite que você crie um pipeline de comandos, especifique o runspace que é usado para executar os comandos e especifique a invocação de comandos de forma síncrona ou assíncrona.

## <a name="the-runspacepool-class"></a>A classe RunspacePool

Pools de runspace permitem que você crie vários Runspaces usando uma única chamada. O método CreateRunspacePool fornece várias sobrecargas que podem ser usadas para criar Runspaces que têm os mesmos recursos, como o mesmo host, estado de sessão inicial e informações de conexão.

## <a name="the-initialsessionstate-class"></a>A classe InitialSessionState

A classe InitialSessionState permite que você crie uma configuração de estado de sessão que é usada quando um runspace é aberto. Você pode criar uma configuração personalizada, uma configuração padrão que inclui os comandos fornecidos pelo mshshort e uma configuração cujos comandos são restritos com base nos recursos da sessão.

## <a name="remote-runspaces"></a>Runspaces remotos

Agora você pode criar espaços de execução que podem ser abertos em computadores remotos, permitindo que você execute comandos no computador remoto e colete os resultados localmente. Para criar um runspace remoto, você deve especificar informações sobre a conexão remota ao criar o runspace. Consulte os métodos CreateRunspace e CreateRunspacePool para obter exemplos. As informações de conexão são definidas pela classe RunspaceConnectionInfo.

## <a name="private-runspace-elements"></a>Elementos de runspace privado

Agora você pode criar Runspaces cujos elementos são públicos ou privados. Isso permite que você crie Runspaces cujos elementos estão disponíveis para o runspace, mas que não estão disponíveis para o usuário. Consulte a classe ConstrainedSessionStateEntry para descobrir quais elementos do runspace podem se tornar particulares.

## <a name="runspace-threading-modes-and-apartment-state"></a>Modos de threading de runspace e estado de apartamento

Agora você pode especificar como os threads são criados e usados ao executar comandos em um runspace. Consulte as propriedades System. Management. Automation. Runspaces. runspace. ThreadOptions e System. Management. Automation. Runspaces. RunspacePool. ThreadOptions.

Agora você pode obter o estado de apartamento dos threads que são usados para executar comandos em um runspace. Consulte as propriedades System. Management. Automation. Runspaces. runspace. seja ApartmentState e System. Management. Automation. Runspaces. RunspacePool. seja ApartmentState.

## <a name="transaction-cmdlets"></a>Cmdlets de transação

Agora você pode criar cmdlets que podem ser usados em uma transação. Quando um cmdlet é usado em uma transação, suas ações são temporárias e podem ser aceitas ou rejeitadas pelos cmdlets de transação fornecidos pelo Windows PowerShell.

Para obter mais informações sobre transações, consulte como dar suporte a transações.

## <a name="transaction-provider"></a>Provedor de transações

Agora você pode criar provedores que podem ser usados em uma transação. Semelhante aos cmdlets, quando um provedor é usado em uma transação, suas ações são temporárias e podem ser aceitas ou rejeitadas pelos cmdlets de transação fornecidos pelo Windows PowerShell.

Para obter mais informações sobre como especificar o suporte para a transação em uma classe de provedor, consulte a propriedade System. Management. Automation. Provider. CmdletProviderAttribute. ProviderCapabilities.

## <a name="job-cmdlets"></a>Cmdlets de trabalho

Agora você pode escrever cmdlets que podem executar sua ação como um trabalho. Esses trabalhos são executados em segundo plano sem interagir com a sessão atual. Para obter mais informações sobre como o Windows PowerShell dá suporte a trabalhos, consulte trabalhos em segundo plano.

## <a name="cmdlet-output-types"></a>Tipos de saída de cmdlet

Agora você pode especificar os tipos de .NET Framework que são retornados pelos cmdlets declarando o atributo OutputType ao escrever seus cmdlets. Isso permitirá que outras pessoas determinem quais tipos de objetos são retornados por um cmdlet examinando a Propriedade OutputType do cmdlet.

## <a name="event-support"></a>Suporte a eventos

Agora você pode escrever cmdlets que adicionam e consomem eventos. Consulte a classe PSEvent.

## <a name="proxy-commands"></a>Comandos de proxy

Agora você pode escrever comandos de proxy que podem ser usados para executar outro comando. Um comando proxy permite que você controle qual funcionalidade do cmdlet de origem está disponível para o usuário. Por exemplo, você pode criar um comando de proxy que remove um parâmetro fornecido pelo comando de origem. Consulte a classe ProxyCommand.

## <a name="multiple-choice-prompts"></a>Prompts com várias opções

Agora você pode escrever aplicativos que podem fornecer prompts que permitem ao usuário selecionar várias opções. Consulte a interface IHostUISupportsMultipleChoiceSelection

## <a name="interactive-sessions"></a>Sessões interativas

Agora você pode escrever aplicativos que podem iniciar e parar uma sessão interativa em um computador remoto.
Consulte a interface IHostSupportsInteractiveSession.

## <a name="custom-cmdlet-help-for-providers"></a>Ajuda de cmdlet personalizado para provedores

Agora você pode criar tópicos de ajuda personalizados para os cmdlets do provedor. Tópicos de ajuda de cmdlets personalizados podem explicar como o cmdlet funciona no caminho do provedor e recursos especiais de documento, incluindo os parâmetros dinâmicos que o provedor adiciona ao cmdlet.
