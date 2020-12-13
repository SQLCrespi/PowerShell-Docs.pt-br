---
ms.date: 09/12/2016
ms.topic: reference
title: Código de exemplo GetProc03 (VB.NET)
description: Código de exemplo GetProc03 (VB.NET)
ms.openlocfilehash: fc70496178c85e101b380e68aacd64c8d1f350e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355554"
---
# <a name="getproc03-vbnet-sample-code"></a>Código de exemplo GetProc03 (VB.NET)

O código a seguir mostra a implementação de um `Get-Process` cmdlet que pode aceitar entrada de pipeline. Essa implementação define um `Name` parâmetro que aceita entrada de pipeline, recupera informações de processo do computador local com base nos nomes fornecidos e, em seguida, usa o método [WriteObject (sistema. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) como o mecanismo de saída para enviar objetos para o pipeline.

## <a name="code-sample"></a>Exemplo de código

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
