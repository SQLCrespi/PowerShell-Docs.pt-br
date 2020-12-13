---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código RunSpace07
description: Exemplo de código RunSpace07
ms.openlocfilehash: 6e8c9f48a6e9c5a642ecf93bca8a85003b3cfbf8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647393"
---
# <a name="runspace07-code-sample"></a>Exemplo de código RunSpace07

Aqui está o código-fonte para o exemplo de Runspace07 descrito em [criando um aplicativo de console que adiciona comandos a um pipeline](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).
Esse aplicativo de exemplo cria um runspace, cria um pipeline, adiciona dois comandos ao pipeline e, em seguida, executa o pipeline. Os comandos adicionados ao pipeline são os `Get-Process` `Measure-Object` cmdlets e.

> [!NOTE]
> Você pode baixar o arquivo de origem do C# (runspace07.cs) usando o Microsoft Windows Software Development Kit para Windows Vista e Microsoft .NET Framework 3,0 Runtime Components. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs" range="11-108":::

## <a name="see-also"></a>Consulte Também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
