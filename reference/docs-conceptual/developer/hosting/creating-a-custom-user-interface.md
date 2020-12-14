---
ms.date: 09/13/2016
ms.topic: reference
title: Criar uma interface do usuário personalizada
description: Criar uma interface do usuário personalizada
ms.openlocfilehash: 411165f868cd524c0cef0ba9cce3188c60a7dbdf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645408"
---
# <a name="creating-a-custom-user-interface"></a>Criar uma interface do usuário personalizada

O Windows PowerShell fornece classes e interfaces abstratas que permitem criar uma interface do usuário interativa personalizada que hospeda o mecanismo do Windows PowerShell. Para criar uma interface do usuário personalizada, você deve implementar a classe [System. Management. Automation. host. PSHost](/dotnet/api/System.Management.Automation.Host.PSHost) . Opcionalmente, você também pode implementar as classes [System. Management. Automation. host. Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)e [System. Management. Automation. host. Pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) e as interfaces [System. Management. Automation. host. Ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) e [System. Management. Automation. host. Ihostuisupportsmultiplechoiceselection](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection) .
