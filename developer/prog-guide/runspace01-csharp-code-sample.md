---
title: Runspace01 (C#) exemplo de código | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d59f8b7c-e800-4633-aa5b-74d4c57e2706
caps.latest.revision: 6
ms.openlocfilehash: ab067485d70523a16493eb57170615ab300eaa98
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735044"
---
# <a name="runspace01-c-code-sample"></a>Exemplo de código Runspace01 (C#)

Aqui estão exemplos de código para o espaço de execução descrito [criação de um Console do aplicativo que é executado um comando especificado](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program). Para fazer isso, o aplicativo invoca um runspace e, em seguida, invoca um comando. (Observe que este aplicativo não especificar informações de configuração do espaço de execução, nem explicitamente cria um pipeline). O comando é invocado é o `Get-Process` cmdlet.

> [!NOTE]
> Você pode baixar o C# arquivo de origem (runspace01.cs) para esse espaço de execução usando o Microsoft Windows Software Development Kit para Windows Vista e o Microsoft .NET Framework 3.0 Runtime Components. Para obter instruções de download, consulte [como instalar o Windows PowerShell e o Download do SDK do Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Os arquivos de origem baixado estão disponíveis na  **\<amostras do PowerShell >** directory.

## <a name="code-sample"></a>Exemplo de código

[!code-csharp[Runspace01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a>Consulte Também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)