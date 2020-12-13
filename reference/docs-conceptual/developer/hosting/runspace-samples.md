---
ms.date: 09/13/2016
ms.topic: reference
title: Amostras de runspace
description: Amostras de runspace
ms.openlocfilehash: 0171622f3ade3b341bc226f14398d6d293262f0c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657949"
---
# <a name="runspace-samples"></a>Amostras de runspace

Esta seção inclui um código de exemplo que mostra como usar diferentes tipos de Runspaces para executar comandos de forma síncrona e assíncrona. Você pode usar Microsoft Visual Studio para criar um aplicativo de console e, em seguida, copiar o código dos tópicos nesta seção para seu aplicativo host.

## <a name="in-this-section"></a>Nesta seção

> [!NOTE]
> Para obter exemplos de aplicativos host que criam interfaces de host personalizadas, consulte [amostras de host personalizado](./custom-host-samples.md).

 [Exemplo de Runspace01](./runspace01-sample.md) Este exemplo mostra como usar a classe [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) para executar o cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) de forma síncrona e exibir sua saída em uma janela do console.

 [Exemplo de Runspace02](./runspace02-sample.md) Este exemplo mostra como usar a classe [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) para executar os cmdlets [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) e [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) de forma síncrona. Os resultados desses comandos são exibidos usando um controle [System. Windows. Forms. DataGridView](/dotnet/api/System.Windows.Forms.DataGridView) .

 [Exemplo de Runspace03](./runspace03-sample.md) Este exemplo mostra como usar a classe [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) para executar um script de forma síncrona e como lidar com erros de não finalização. O script recebe uma lista de nomes de processo e, em seguida, recupera tais processos. Os resultados do script, incluindo quaisquer erros de não encerramento gerados durante a execução do script, são exibidos em uma janela do console.

 [Exemplo de Runspace04](./runspace04-sample.md) Este exemplo mostra como usar a classe [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) para executar comandos e como detectar erros de encerramento que são lançados durante a execução dos comandos. Dois comandos são executados e o último comando é passado um argumento de parâmetro que não é válido. Como resultado, nenhum objeto é retornado e um erro de encerramento é gerado.

 [Exemplo de Runspace05](./runspace05-sample.md) Este exemplo mostra como adicionar um snap-in a um objeto [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) para que o cmdlet do snap-in esteja disponível quando o runspace é aberto. O snap-in fornece um cmdlet Get-Proc (definido pelo [exemplo GetProcessSample01](../cmdlet/getprocesssample01-sample.md)) que é executado de forma síncrona usando um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

 [Exemplo de Runspace06](./runspace06-sample.md) Este exemplo mostra como adicionar um módulo a um objeto [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) para que o módulo seja carregado quando o runspace for aberto. O módulo fornece um cmdlet Get-Proc (definido pelo [exemplo GetProcessSample02](../cmdlet/getprocesssample02-sample.md)) que é executado de forma síncrona usando um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

 [Exemplo de Runspace07](./runspace07-sample.md) Este exemplo mostra como criar um runspace e, em seguida, usar esse runspace para executar dois cmdlets de forma síncrona usando um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

 [Exemplo de Runspace08](./runspace08-sample.md) Este exemplo mostra como adicionar comandos e argumentos ao pipeline de um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) e como executar os comandos de forma síncrona.

 [Exemplo de Runspace09](./runspace09-sample.md) Este exemplo mostra como adicionar um script ao pipeline de um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) e como executar o script de forma assíncrona. Eventos são usados para tratar a saída do script.

 [Exemplo de Runspace10](./runspace10-sample.md) Este exemplo mostra como criar um estado de sessão inicial padrão, como adicionar um cmdlet ao [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState), como criar um runspace que usa o estado de sessão inicial e como executar o comando usando um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

 [Exemplo de Runspace11](./runspace11-sample.md) Isso mostra como usar a classe [System. Management. Automation. ProxyCommand](/dotnet/api/System.Management.Automation.ProxyCommand) para criar um comando de proxy que chama um cmdlet existente, mas restringe o conjunto de parâmetros disponíveis. O comando de proxy é adicionado a um estado de sessão inicial que é usado para criar um espaço de execução restrito. Isso significa que o usuário pode acessar a funcionalidade do cmdlet apenas por meio do comando proxy.

## <a name="see-also"></a>Consulte Também
