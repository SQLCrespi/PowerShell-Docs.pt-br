---
title: Criando uma interface do usuário personalizada | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ebbaba4231b54d42cdcdef07a3ff665bd207d696
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779770"
---
# <a name="creating-a-custom-user-interface"></a>Criar uma interface do usuário personalizada

O Windows PowerShell fornece classes e interfaces abstratas que permitem criar uma interface do usuário interativa personalizada que hospeda o mecanismo do Windows PowerShell. Para criar uma interface do usuário personalizada, você deve implementar a classe [System. Management. Automation. host. PSHost](/dotnet/api/System.Management.Automation.Host.PSHost) . Opcionalmente, você também pode implementar as classes [System. Management. Automation. host. Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)e [System. Management. Automation. host. Pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) e as interfaces [System. Management. Automation. host. Ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) e [System. Management. Automation. host. Ihostuisupportsmultiplechoiceselection](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection) .
