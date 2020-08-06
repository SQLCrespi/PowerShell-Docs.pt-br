---
title: Estado de sessão do Windows PowerShell | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- Cmdlets [PowerShell], session state
- session state [PowerShell]
ms.openlocfilehash: 7436e3ebd0e099ead81f9fea01a0a2994b982213
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783935"
---
# <a name="windows-powershell-session-state"></a>Estado de sessão do Windows PowerShell

Estado da sessão refere-se à configuração atual de uma sessão ou módulo do Windows PowerShell. Uma sessão do Windows PowerShell é o ambiente operacional usado interativamente pelo usuário de linha de comando ou por meio de programação por um aplicativo host. O estado de sessão de uma sessão é conhecido como o estado de sessão global.

Da perspectiva do desenvolvedor, uma sessão do Windows PowerShell refere-se ao tempo entre quando um aplicativo host abre um runspace do Windows PowerShell e quando fecha o runspace. Examinamos de outra forma, a sessão é o tempo de vida de uma instância do mecanismo do Windows PowerShell que é invocado enquanto o runspace existe.

## <a name="module-session-state"></a>Estado de sessão do módulo

Os Estados de sessão de módulo são criados sempre que o módulo ou um de seus módulos aninhados é importado para a sessão. Quando um módulo exporta um elemento, como um cmdlet, uma função ou um script, uma referência a esse elemento é adicionada ao estado de sessão global da sessão. No entanto, quando o elemento é executado, ele é executado dentro do estado de sessão do módulo.

## <a name="session-state-data"></a>Dados de estado da sessão

Os dados de estado da sessão podem ser públicos ou privados. Os dados públicos estão disponíveis para chamadas de fora do estado da sessão enquanto dados privados estão disponíveis somente para chamadas de dentro do estado da sessão. Por exemplo, um módulo pode ter uma função particular que pode ser chamada somente pelo módulo ou apenas internamente por um elemento público que tenha sido exportado. Isso é semelhante aos membros públicos e privados de um tipo de .NET Framework.

Os dados de estado da sessão são armazenados pela instância atual do mecanismo de execução no contexto da sessão atual do Windows PowerShell. Os dados de estado da sessão consistem nos seguintes itens:

- Informações de caminho

- Informações da unidade

- Informações do provedor do Windows PowerShell

- Informações sobre os módulos importados e referências aos elementos do módulo (como, por exemplo, cmdlets, funções e scripts) que são exportados pelo módulo. Essas informações e essas referências são apenas para o estado de sessão global.

- Informações da variável de estado da sessão

## <a name="accessing-session-state-data-within-cmdlets"></a>Acessando dados de estado da sessão em cmdlets

Os cmdlets podem acessar dados de estado de sessão indiretamente por meio da propriedade [System. Management. Automation. PSCmdlet. SessionState *](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) da classe cmdlet ou diretamente por meio da classe [System. Management. Automation. SessionState](/dotnet/api/System.Management.Automation.SessionState) . A classe [System. Management. Automation. SessionState](/dotnet/api/System.Management.Automation.SessionState) fornece propriedades que podem ser usadas para investigar diferentes tipos de dados de estado de sessão.

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. PSCmdlet. SessionState](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)

[System. Management. Automation. SessionState? Displayproperty = FullName](/dotnet/api/System.Management.Automation.SessionState)

[Cmdlets do Windows PowerShell](./cmdlet-overview.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[SDK do shell do Windows PowerShell](../windows-powershell-reference.md)
