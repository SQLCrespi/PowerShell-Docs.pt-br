---
ms.date: 09/13/2016
ms.topic: reference
title: Código de exemplo GetProc01 (C#)
description: Código de exemplo GetProc01 (C#)
ms.openlocfilehash: 79509ff12afb32c907058f4ddb0c707f3823857a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654488"
---
# <a name="getproc01-c-sample-code"></a>Código de exemplo GetProc01 (C#)

O código a seguir mostra a implementação do cmdlet de exemplo GetProc01. Observe que o cmdlet é simplificado deixando o trabalho real de recuperação do processo com o método [System. Diagnostics. Process. GetProcesses *](/dotnet/api/System.Diagnostics.Process.GetProcesses) .

> [!NOTE]
> Você pode baixar o arquivo de origem C# (getproc01.cs) para este cmdlet Get-Proc usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e os componentes de tempo de execução do .NET Framework 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="11-126":::

## <a name="see-also"></a>Consulte Também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
