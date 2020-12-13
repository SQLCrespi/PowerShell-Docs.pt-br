---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código RunSpace06
description: Exemplo de código RunSpace06
ms.openlocfilehash: 627fa2be51721dd8bfdd63fabdd2e6f286d593be
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667463"
---
# <a name="runspace06-code-sample"></a>Exemplo de código RunSpace06

Este é o código-fonte do exemplo Runspace06 descrito em [Configurando um runspace usando um snap-in do Windows PowerShell](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).
Esse aplicativo de exemplo cria um runspace com base em um snap-in do Windows PowerShell, que é usado para executar um pipeline com um único comando. Para fazer isso, o aplicativo cria as informações de configuração do runspace, cria um runspace, cria um pipeline com um único comando e, em seguida, executa o pipeline.

> [!NOTE]
> Você pode baixar o arquivo de origem do C# (runspace06.cs) usando o kit de desenvolvimento de software do Windows para componentes de tempo de execução do Windows Vista e do Microsoft .NET Framework 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs" range="11-85":::

## <a name="see-also"></a>Consulte Também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
