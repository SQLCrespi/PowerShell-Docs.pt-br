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
ms.openlocfilehash: 4f0be193fb5b5c753d040a48e5f49235ece11708
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366005"
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

- [Adicionando atividades do Windows PowerShell à caixa de ferramentas do Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)

- [Criando um fluxo de trabalho com atividades do Windows PowerShell](./creating-a-workflow-with-windows-powershell-activities.md)

- [Criando um fluxo de trabalho usando um script do Windows PowerShell](./creating-a-workflow-by-using-a-windows-powershell-script.md)

- [Importando e invocando um fluxo de trabalho do Windows PowerShell](./importing-and-invoking-a-windows-powershell-workflow.md)

- [Criando uma atividade de fluxo de trabalho a partir de um cmdlet do Windows PowerShell](./creating-a-workflow-activity-from-a-windows-powershell-cmdlet.md)