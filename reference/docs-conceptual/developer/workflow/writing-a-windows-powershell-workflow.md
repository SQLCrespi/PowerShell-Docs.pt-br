---
title: Escrevendo um fluxo de trabalho do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2551ceed-836f-4275-9fc0-ea68446d6a35
caps.latest.revision: 7
ms.openlocfilehash: 0f8a9938a1685e9abc2f1dbfb18c3b2b9008d9be
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564919"
---
# <a name="writing-a-windows-powershell-workflow"></a>Escrevendo um Fluxo de Trabalho do Windows PowerShell

Você pode criar um fluxo de trabalho XAML adicionando atividades expostas por assemblies do Windows PowerShell ao designer de fluxo de trabalho no Visual Studio. Os assemblies do Windows PowerShell a seguir expõem atividades habilitadas para fluxo de trabalho.

> [!IMPORTANT]
> Um fluxo de trabalho XAML deve ser empacotado como um módulo se você quiser fornecer ajuda para o fluxo de trabalho. Para obter informações sobre módulos, consulte [escrevendo um módulo do Windows PowerShell](../module/writing-a-windows-powershell-module.md).

- [Microsoft. PowerShell. Activities](/dotnet/api/Microsoft.PowerShell.Activities)

- [Microsoft. PowerShell. Core. Activities](/dotnet/api/Microsoft.PowerShell.Core.Activities)

- [Microsoft. PowerShell. Diagnostics. Activities](/dotnet/api/Microsoft.PowerShell.Diagnostics.Activities)

- [Microsoft. PowerShell. Management. Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities)

- [Microsoft. PowerShell. Security. Activities](/dotnet/api/Microsoft.PowerShell.Security.Activities)

- [Microsoft. PowerShell. Utility. Activities](/dotnet/api/Microsoft.PowerShell.Utility.Activities)

  Os tópicos a seguir descrevem como criar um fluxo de trabalho usando atividades do Windows PowerShell.

- [Adicionar atividades do Windows PowerShell à caixa de ferramentas do Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)

- [Criar um fluxo de trabalho com atividades do Windows PowerShell](./creating-a-workflow-with-windows-powershell-activities.md)

- [Criar um fluxo de trabalho pelo uso de um script do Windows PowerShell](./creating-a-workflow-by-using-a-windows-powershell-script.md)

- [Importar e invocar um fluxo de trabalho do Windows PowerShell](./importing-and-invoking-a-windows-powershell-workflow.md)

- [Criar uma atividade de fluxo de trabalho de um cmdlet do Windows PowerShell](./creating-a-workflow-activity-from-a-windows-powershell-cmdlet.md)
