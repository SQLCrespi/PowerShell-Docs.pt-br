---
title: Gravando um aplicativo host do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81aeafad-dbc3-4712-8bb9-e6a417be260f
caps.latest.revision: 15
ms.openlocfilehash: b44708b3bbcb974a6178323dff2302b7da121af6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367275"
---
# <a name="writing-a-windows-powershell-host-application"></a><span data-ttu-id="28b42-102">Escrever um aplicativo host do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28b42-102">Writing a Windows PowerShell Host Application</span></span>

<span data-ttu-id="28b42-103">Você pode hospedar o Windows PowerShell em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="28b42-103">You can host Windows PowerShell in your application.</span></span> <span data-ttu-id="28b42-104">O aplicativo host pode definir o runspace onde os comandos são executados, abrir sessões em um computador local ou remoto e invocar os comandos de forma síncrona ou assíncrona com base nas necessidades do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="28b42-104">The host application can define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

<span data-ttu-id="28b42-105">Os tópicos a seguir explicam como criar um aplicativo que hospeda o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28b42-105">The following topics explain how to create an application that hosts Windows PowerShell.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="28b42-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="28b42-106">In This Section</span></span>

<span data-ttu-id="28b42-107">[Início rápido do host do Windows PowerShell](./windows-powershell-host-quickstart.md) Fornece instruções e exemplos de código para começar a criar aplicativos host.</span><span class="sxs-lookup"><span data-stu-id="28b42-107">[Windows PowerShell Host Quickstart](./windows-powershell-host-quickstart.md) Provides instructions and code samples to get you started creating host applications.</span></span>

<span data-ttu-id="28b42-108">[Criando Runspaces](./creating-runspaces.md) Um conjunto de tópicos que explica como criar espaços de execução para executar o comando do Windows PowerShell em um aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="28b42-108">[Creating Runspaces](./creating-runspaces.md) A set of topics that explain how to create runspaces to run Windows PowerShell command in a host application.</span></span>

<span data-ttu-id="28b42-109">[Adicionando e invocando comandos](./adding-and-invoking-commands.md) Explica como criar e executar um pipeline de comando em seu aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="28b42-109">[Adding and invoking commands](./adding-and-invoking-commands.md) Explains how to create and run a command pipeline in your host application..</span></span>

<span data-ttu-id="28b42-110">[Criando Runspaces remotas](./creating-remote-runspaces.md) Explica como conectar um runspace a um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="28b42-110">[Creating remote runspaces](./creating-remote-runspaces.md) Explains how to connect a runspace to a remote computer.</span></span>

<span data-ttu-id="28b42-111">[Criando uma interface do usuário personalizada](./creating-a-custom-user-interface.md) Apresenta interfaces de usuário personalizadas e fornece links para exemplos.</span><span class="sxs-lookup"><span data-stu-id="28b42-111">[Creating a custom user interface](./creating-a-custom-user-interface.md) Introduces custom user interfaces and provides links to examples.</span></span>

<span data-ttu-id="28b42-112">[Exemplos de aplicativos host](./host-application-samples.md) Esta seção inclui exemplos de aplicativos host completos.</span><span class="sxs-lookup"><span data-stu-id="28b42-112">[Host Application Samples](./host-application-samples.md) This section includes samples of complete host applications.</span></span>

## <a name="see-also"></a><span data-ttu-id="28b42-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="28b42-113">See Also</span></span>

[<span data-ttu-id="28b42-114">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28b42-114">Windows PowerShell</span></span>](https://msdn.microsoft.com/en-us/b41a2af3-aec1-402d-8e18-c2c26be461ff)
