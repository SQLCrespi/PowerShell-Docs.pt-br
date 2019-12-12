---
title: Criando uma interface do usuário personalizada | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7286443-eed4-43d5-b809-50cdcdcba088
caps.latest.revision: 4
ms.openlocfilehash: 23518c625fe1138e1bd2bcc895274cb21d7daf8a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367625"
---
# <a name="creating-a-custom-user-interface"></a>Criar uma interface do usuário personalizada

O Windows PowerShell fornece classes e interfaces abstratas que permitem criar uma interface do usuário interativa personalizada que hospeda o mecanismo do Windows PowerShell. Para criar uma interface do usuário personalizada, você deve implementar a classe [System. Management. Automation. host. PSHost](/dotnet/api/System.Management.Automation.Host.PSHost) . Opcionalmente, você também pode implementar as classes [System. Management. Automation. host. Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)e [System. Management. Automation. host. Pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) e as interfaces [System. Management. Automation. host. Ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) e [System. Management. Automation. host. Ihostuisupportsmultiplechoiceselection](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection) .
