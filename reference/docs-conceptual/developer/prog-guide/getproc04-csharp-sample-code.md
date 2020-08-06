---
title: Código de exemplo de GetProc04 (C#) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: dd3965ee504641b1b629ba203090ee14c670da43
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771882"
---
# <a name="getproc04-c-sample-code"></a>Código de exemplo GetProc04 (C#)

O código a seguir mostra a implementação de um `Get-Process` cmdlet que relata erros de não encerramento. Essa implementação chama o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) para relatar erros de não encerramento.

> [!NOTE]
> Você pode baixar o arquivo de origem do C# (getprov04.cs) para este cmdlet Get-proc usando o Microsoft Windows Software Development Kit para Windows Vista e .NET Framework os componentes de tempo de execução do 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs" range="11-98":::

## <a name="see-also"></a>Consulte Também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
