---
title: Criando espaços de Runspaces | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0c27e2bf54e16a3bdc93c4b91629893bb1cc1e3e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779566"
---
# <a name="creating-runspaces"></a><span data-ttu-id="c4a8d-102">Criar runspaces</span><span class="sxs-lookup"><span data-stu-id="c4a8d-102">Creating Runspaces</span></span>

<span data-ttu-id="c4a8d-103">Um runspace é o ambiente operacional para os comandos que são invocados por um aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="c4a8d-103">A runspace is the operating environment for the commands that are invoked by a host application.</span></span> <span data-ttu-id="c4a8d-104">Esse ambiente inclui os comandos e dados atualmente presentes e as restrições de idioma que se aplicam atualmente.</span><span class="sxs-lookup"><span data-stu-id="c4a8d-104">This environment includes the commands and data that are currently present, and any language restrictions that currently apply.</span></span>

 <span data-ttu-id="c4a8d-105">Os aplicativos host podem usar o runspace padrão fornecido pelo Windows PowerShell, que inclui todos os comandos de núcleo disponíveis, ou criar um runspace personalizado que inclui apenas um subconjunto dos comandos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c4a8d-105">Host applications can use the default runspace that is provided by Windows PowerShell, which includes all available core commands, or create a custom runspace that includes only a subset of the available commands.</span></span> <span data-ttu-id="c4a8d-106">Para criar um runspace personalizado, você cria um objeto [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) e o atribui ao runspace.</span><span class="sxs-lookup"><span data-stu-id="c4a8d-106">To create a customized runspace, you create an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object and assign it to your runspace.</span></span>

## <a name="runspace-tasks"></a><span data-ttu-id="c4a8d-107">Tarefas do runspace</span><span class="sxs-lookup"><span data-stu-id="c4a8d-107">Runspace tasks</span></span>

1. [<span data-ttu-id="c4a8d-108">Criar um InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="c4a8d-108">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

2. [<span data-ttu-id="c4a8d-109">Criar um runspace com restrição</span><span class="sxs-lookup"><span data-stu-id="c4a8d-109">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

3. [<span data-ttu-id="c4a8d-110">Criar vários runspaces</span><span class="sxs-lookup"><span data-stu-id="c4a8d-110">Creating multiple runspaces</span></span>](./creating-multiple-runspaces.md)

## <a name="see-also"></a><span data-ttu-id="c4a8d-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c4a8d-111">See Also</span></span>
