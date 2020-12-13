---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código RunSpace05
description: Exemplo de código RunSpace05
ms.openlocfilehash: f128e09522bdb05cba2c160bce4944c829a5c108
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654212"
---
# <a name="runspace05-code-sample"></a>Exemplo de código RunSpace05

Este é o código-fonte do exemplo Runspace05 descrito em [Configurando um runspace usando RunspaceConfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).
Este exemplo mostra como criar as informações de configuração do runspace, criar um runspace, criar um pipeline com um único comando e, em seguida, executar o pipeline. O comando executado é o `Get-Process` cmdlet.

> [!NOTE]
> Você pode baixar o arquivo de origem do C# (runspace05.cs) usando o Microsoft Windows Software Development Kit para Windows Vista e os componentes de tempo de execução do Microsoft .NET Framework 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs" range="11-86":::

## <a name="see-also"></a>Consulte Também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
