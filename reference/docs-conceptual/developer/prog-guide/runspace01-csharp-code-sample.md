---
title: Exemplo deC#código Runspace01 () | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d59f8b7c-e800-4633-aa5b-74d4c57e2706
caps.latest.revision: 6
ms.openlocfilehash: 607113ed566fc1e08e5b1d7092c83da2a22366ca
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74418009"
---
# <a name="runspace01-c-code-sample"></a>Exemplo de código Runspace01 (C#)

Aqui estão os exemplos de código para o runspace descrito em [criando um aplicativo de console que executa um comando especificado](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program). Para fazer isso, o aplicativo invoca um runspace e, em seguida, invoca um comando. (Observe que esse aplicativo não especifica informações de configuração de runspace, nem cria explicitamente um pipeline). O comando que é invocado é o cmdlet `Get-Process`.

> [!NOTE]
> Você pode baixar o C# arquivo de origem (runspace01.cs) para este runspace usando o Microsoft Windows Software Development Kit para Windows Vista e os componentes de tempo de execução do Microsoft .NET Framework 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
>
> Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório.

## <a name="code-sample"></a>Exemplo de código

[!code-csharp[Runspace01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a>Consulte também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
