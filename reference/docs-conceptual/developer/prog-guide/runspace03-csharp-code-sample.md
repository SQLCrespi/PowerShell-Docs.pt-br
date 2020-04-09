---
title: Exemplo deC#código RunSpace03 () | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ac8ab99-1856-4d6f-b30d-c0a18b8dd1fc
caps.latest.revision: 6
ms.openlocfilehash: 28cef037f56f2a101f631d3a234974a8868b4ef9
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978314"
---
# <a name="runspace03-c-code-sample"></a>Exemplo de código RunSpace03 (C#)

Este é o C# código-fonte do aplicativo de console descrito em "criando um aplicativo de console que executa um script especificado". Este exemplo usa a classe [System. Management. Automation. Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) para executar um script que recupera informações de processo usando a lista de nomes de processo passados para o script. Ele mostra como passar objetos de entrada para um script e como recuperar objetos de erro, bem como os objetos de saída.

> [!NOTE]
> Você pode baixar o C# arquivo de origem (runspace03.cs) para este exemplo usando os componentes de tempo de execução do Microsoft Windows Software Development Kit para Windows Vista e Microsoft .NET Framework 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a>Consulte Também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
