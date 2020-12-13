---
ms.date: 09/13/2016
ms.topic: reference
title: Código de exemplo GetProc04 (C#)
description: Código de exemplo GetProc04 (C#)
ms.openlocfilehash: 80020b60a7ab34caec0c856b9b7d12021f4276b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654375"
---
# <a name="getproc04-c-sample-code"></a>Código de exemplo GetProc04 (C#)

O código a seguir mostra a implementação de um `Get-Process` cmdlet que relata erros de não encerramento. Essa implementação chama o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) para relatar erros de não encerramento.

> [!NOTE]
> Você pode baixar o arquivo de origem C# (getprov04.cs) para este cmdlet Get-Proc usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e os componentes de tempo de execução do .NET Framework 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs" range="11-98":::

## <a name="see-also"></a>Consulte Também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
