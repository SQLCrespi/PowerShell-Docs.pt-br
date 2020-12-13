---
ms.date: 09/13/2016
ms.topic: reference
title: Código de exemplo GetProc03 (C#)
description: Código de exemplo GetProc03 (C#)
ms.openlocfilehash: c81ba04b2b335f4ce992c6b3ed2f019cf6d7d20f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355571"
---
# <a name="getproc03-c-sample-code"></a>Código de exemplo GetProc03 (C#)

O código a seguir mostra a implementação de um `Get-Process` cmdlet que pode aceitar entrada de pipeline. Essa implementação define um `Name` parâmetro que aceita entrada de pipeline, recupera informações de processo do computador local com base nos nomes fornecidos e, em seguida, usa o método [WriteObject (sistema. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) como o mecanismo de saída para enviar objetos para o pipeline.

> [!NOTE]
> Você pode baixar o arquivo de origem C# (getprov03.cs) para este cmdlet Get-Proc usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e os componentes de tempo de execução do .NET Framework 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="11-78":::

## <a name="see-also"></a>Consulte Também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
