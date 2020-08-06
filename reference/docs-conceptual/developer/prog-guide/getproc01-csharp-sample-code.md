---
title: Código de exemplo de GetProc01 (C#) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 883beb9dd1328a1897b9b61656a98cf515a21be7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778893"
---
# <a name="getproc01-c-sample-code"></a>Código de exemplo GetProc01 (C#)

O código a seguir mostra a implementação do cmdlet de exemplo GetProc01. Observe que o cmdlet é simplificado deixando o trabalho real de recuperação do processo com o método [System. Diagnostics. Process. GetProcesses *](/dotnet/api/System.Diagnostics.Process.GetProcesses) .

> [!NOTE]
> Você pode baixar o arquivo de origem do C# (getproc01.cs) para este cmdlet Get-proc usando o Microsoft Windows Software Development Kit para Windows Vista e .NET Framework os componentes de tempo de execução do 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="11-126":::

## <a name="see-also"></a>Consulte Também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
