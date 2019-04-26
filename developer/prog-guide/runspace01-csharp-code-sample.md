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
ms.openlocfilehash: 59320365c4a35c3d71af10273eb21b1ce01e5c0c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081454"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="c1334-102">Exemplo de código Runspace01 (C#)</span><span class="sxs-lookup"><span data-stu-id="c1334-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="c1334-103">Aqui estão exemplos de código para o espaço de execução descrito [criação de um Console do aplicativo que é executado um comando especificado](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e).</span><span class="sxs-lookup"><span data-stu-id="c1334-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e).</span></span> <span data-ttu-id="c1334-104">Para fazer isso, o aplicativo invoca um runspace e, em seguida, invoca um comando.</span><span class="sxs-lookup"><span data-stu-id="c1334-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="c1334-105">(Observe que este aplicativo não especificar informações de configuração do espaço de execução, nem explicitamente cria um pipeline).</span><span class="sxs-lookup"><span data-stu-id="c1334-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="c1334-106">O comando é invocado é o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c1334-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="c1334-107">Você pode baixar o C# arquivo de origem (runspace01.cs) para esse espaço de execução usando o Microsoft Windows Software Development Kit para Windows Vista e o Microsoft .NET Framework 3.0 Runtime Components.</span><span class="sxs-lookup"><span data-stu-id="c1334-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="c1334-108">Para obter instruções de download, consulte [como instalar o Windows PowerShell e o Download do SDK do Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="c1334-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="c1334-109">Os arquivos de origem baixado estão disponíveis na  **\<amostras do PowerShell >** directory.</span><span class="sxs-lookup"><span data-stu-id="c1334-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="c1334-110">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="c1334-110">Code Sample</span></span>

[!code-csharp[Runspace01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a><span data-ttu-id="c1334-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c1334-111">See Also</span></span>

[<span data-ttu-id="c1334-112">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1334-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="c1334-113">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1334-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)