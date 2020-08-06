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
# <a name="creating-runspaces"></a>Criar runspaces

Um runspace é o ambiente operacional para os comandos que são invocados por um aplicativo host. Esse ambiente inclui os comandos e dados atualmente presentes e as restrições de idioma que se aplicam atualmente.

 Os aplicativos host podem usar o runspace padrão fornecido pelo Windows PowerShell, que inclui todos os comandos de núcleo disponíveis, ou criar um runspace personalizado que inclui apenas um subconjunto dos comandos disponíveis. Para criar um runspace personalizado, você cria um objeto [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) e o atribui ao runspace.

## <a name="runspace-tasks"></a>Tarefas do runspace

1. [Criar um InitialSessionState](./creating-an-initialsessionstate.md)

2. [Criar um runspace com restrição](./creating-a-constrained-runspace.md)

3. [Criar vários runspaces](./creating-multiple-runspaces.md)

## <a name="see-also"></a>Consulte Também
