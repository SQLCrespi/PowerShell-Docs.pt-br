---
title: Criando espaços de Runspaces | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17f323c3-e873-449e-8a28-477f1c6b5e12
caps.latest.revision: 6
ms.openlocfilehash: b4e61600f68521e4e7ab56ceae3349381e88a70a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367575"
---
# <a name="creating-runspaces"></a>Criar runspaces

Um runspace é o ambiente operacional para os comandos que são invocados por um aplicativo host. Esse ambiente inclui os comandos e dados atualmente presentes e as restrições de idioma que se aplicam atualmente.

 Os aplicativos host podem usar o runspace padrão fornecido pelo Windows PowerShell, que inclui todos os comandos de núcleo disponíveis, ou criar um runspace personalizado que inclui apenas um subconjunto dos comandos disponíveis. Para criar um runspace personalizado, você cria um objeto [System. Management. Automation. Runspaces. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) e o atribui ao runspace.

## <a name="runspace-tasks"></a>Tarefas do runspace

1. [Criando um InitialSessionState](./creating-an-initialsessionstate.md)

2. [Criando um runspace restrito](./creating-a-constrained-runspace.md)

3. [Criando vários Runspaces](./creating-multiple-runspaces.md)

## <a name="see-also"></a>Consulte Também
