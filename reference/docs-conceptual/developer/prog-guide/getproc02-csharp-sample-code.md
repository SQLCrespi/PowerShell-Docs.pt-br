---
ms.date: 09/13/2016
ms.topic: reference
title: Código de exemplo GetProc02 (C#)
description: Código de exemplo GetProc02 (C#)
ms.openlocfilehash: 17fd0d0c0829ed21ef955fd2e62e9ee089d62190
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355605"
---
# <a name="getproc02-c-sample-code"></a>Código de exemplo GetProc02 (C#)

O código a seguir mostra a implementação de um `Get-Process` cmdlet que aceita a entrada de linha de comando. Observe que essa implementação define um `Name` parâmetro para permitir a entrada da linha de comando e usa o método [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) como o mecanismo de saída para enviar objetos de saída para o pipeline.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample02/GetProcessSample02.cs" range="11-76":::

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
