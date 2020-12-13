---
ms.date: 09/13/2016
ms.topic: reference
title: Criar runspaces
description: Criar runspaces
ms.openlocfilehash: c6b2c577e435ec88364b189a0c3d065f54f02525
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649349"
---
# <a name="creating-runspaces"></a><span data-ttu-id="2d8dc-103">Criar runspaces</span><span class="sxs-lookup"><span data-stu-id="2d8dc-103">Creating Runspaces</span></span>

<span data-ttu-id="2d8dc-104">Um runspace é o ambiente operacional para os comandos que são invocados por um aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="2d8dc-104">A runspace is the operating environment for the commands that are invoked by a host application.</span></span> <span data-ttu-id="2d8dc-105">Esse ambiente inclui os comandos e dados atualmente presentes e as restrições de idioma que se aplicam atualmente.</span><span class="sxs-lookup"><span data-stu-id="2d8dc-105">This environment includes the commands and data that are currently present, and any language restrictions that currently apply.</span></span>

 <span data-ttu-id="2d8dc-106">Os aplicativos host podem usar o runspace padrão fornecido pelo Windows PowerShell, que inclui todos os comandos de núcleo disponíveis, ou criar um runspace personalizado que inclui apenas um subconjunto dos comandos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2d8dc-106">Host applications can use the default runspace that is provided by Windows PowerShell, which includes all available core commands, or create a custom runspace that includes only a subset of the available commands.</span></span> <span data-ttu-id="2d8dc-107">Para criar um runspace personalizado, você cria um objeto [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) e o atribui ao runspace.</span><span class="sxs-lookup"><span data-stu-id="2d8dc-107">To create a customized runspace, you create an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object and assign it to your runspace.</span></span>

## <a name="runspace-tasks"></a><span data-ttu-id="2d8dc-108">Tarefas do runspace</span><span class="sxs-lookup"><span data-stu-id="2d8dc-108">Runspace tasks</span></span>

1. [<span data-ttu-id="2d8dc-109">Criar um InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="2d8dc-109">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

2. [<span data-ttu-id="2d8dc-110">Criar um runspace com restrição</span><span class="sxs-lookup"><span data-stu-id="2d8dc-110">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

3. [<span data-ttu-id="2d8dc-111">Criar vários runspaces</span><span class="sxs-lookup"><span data-stu-id="2d8dc-111">Creating multiple runspaces</span></span>](./creating-multiple-runspaces.md)

## <a name="see-also"></a><span data-ttu-id="2d8dc-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d8dc-112">See Also</span></span>
