---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código Runspace01 (C#)
description: Exemplo de código Runspace01 (C#)
ms.openlocfilehash: e6121c144e1a4c1a1d9460d01119f44ee5835821
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657151"
---
# <a name="runspace01-c-code-sample"></a>Exemplo de código Runspace01 (C#)

Aqui estão os exemplos de código para o runspace descrito em [criando um aplicativo de console que executa um comando especificado](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).
Para fazer isso, o aplicativo invoca um runspace e, em seguida, invoca um comando. (Observe que esse aplicativo não especifica informações de configuração de runspace, nem cria explicitamente um pipeline). O comando que é invocado é o `Get-Process` cmdlet.

> [!NOTE]
> Você pode baixar o arquivo de origem do C# (runspace01.cs) para este runspace usando o Microsoft Windows Software Development Kit para Windows Vista e os componentes de tempo de execução do Microsoft .NET Framework 3,0.
> Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a>Consulte Também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
