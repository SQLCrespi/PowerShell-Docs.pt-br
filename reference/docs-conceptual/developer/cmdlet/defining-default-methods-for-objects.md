---
ms.date: 09/13/2016
ms.topic: reference
title: Definir os métodos padrão para objetos
description: Definir os métodos padrão para objetos
ms.openlocfilehash: c65ca91a7038f32d8c3ef62cfe7881e5ad4dba5a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355520"
---
# <a name="defining-default-methods-for-objects"></a>Definir os métodos padrão para objetos

Ao estender .NET Framework objetos, você pode adicionar métodos de código e métodos de script aos objetos.
O XML que é usado para definir esses métodos é descrito nas seções a seguir.

> [!NOTE]
> Os exemplos nas seções a seguir são do `Types.ps1xml` arquivo de tipos no diretório de instalação do Windows PowerShell ( `$PSHOME` ). Para obter mais informações, consulte [About Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).

## <a name="code-methods"></a>Métodos de código

Um método de código faz referência a um método estático de um objeto .NET Framework.

No exemplo a seguir, o método **ToString** é adicionado ao tipo de [ nóSystem.Xml.Xml](/dotnet/api/System.Xml.XmlNode) . O elemento [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) define o método estendido como um método de código. O elemento [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) especifica o nome do método estendido. E, o elemento [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference) especifica o método estático. Você também pode adicionar o elemento [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) aos membros do elemento [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) .

```xml
<Type>
  <Name>System.Xml.XmlNode</Name>
  <Members>
    <CodeMethod>
      <Name>ToString</Name>
      <CodeReference>
        <TypeName>Microsoft.PowerShell.ToStringCodeMethods</TypeName>
        <MethodName>XmlNode</MethodName>
      </CodeReference>
    </CodeMethod>
  </Members>
</Type>
```

## <a name="script-methods"></a>Métodos de script

Um método de script define um método cujo valor é a saída de um script. No exemplo a seguir, o método **ConvertToDateTime** é adicionado ao tipo [System. Management. ManagementObject](/dotnet/api/System.Management.ManagementObject) . O elemento [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) define o método estendido como um método de script. O elemento [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) especifica o nome do método estendido. E o elemento [script](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script) especifica o script que gera o valor do método. Você também pode adicionar o elemento [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) aos membros do elemento [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) .

```xml
<Type>
  <Name>System.Management.ManagementObject</Name>
  <Members>
    <ScriptMethod>
      <Name>ConvertToDateTime</Name>
      <Script>
        [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
      </Script>
    </ScriptMethod>
  </Members>
</Type>
```

## <a name="see-also"></a>Veja também

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
