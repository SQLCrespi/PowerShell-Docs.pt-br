---
title: Exemplo de código RunSpace05 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9688cd69-07ea-4ea0-8822-0a4850bcf86c
caps.latest.revision: 7
ms.openlocfilehash: 8802e308712be93992ead5ef77b97d8c21b137f7
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870635"
---
# <a name="runspace05-code-sample"></a>Exemplo de código RunSpace05

Este é o código-fonte do exemplo Runspace05 descrito em [Configurando um runspace usando RunspaceConfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).
Este exemplo mostra como criar as informações de configuração do runspace, criar um runspace, criar um pipeline com um único comando e, em seguida, executar o pipeline. O comando executado é o cmdlet `Get-Process`.

> [!NOTE]
> Você pode baixar o C# arquivo de origem (runspace05.cs) usando o Microsoft Windows Software Development Kit para Windows Vista e Microsoft .NET Framework 3,0 Runtime Components. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório.

## <a name="code-sample"></a>Exemplo de código

[!code-csharp[Runspace05.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs#L11-L86 "Runspace05.cs")]

## <a name="see-also"></a>Veja também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
