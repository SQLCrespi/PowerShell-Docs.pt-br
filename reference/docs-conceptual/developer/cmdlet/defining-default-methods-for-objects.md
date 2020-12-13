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
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="6f241-103">Definir os métodos padrão para objetos</span><span class="sxs-lookup"><span data-stu-id="6f241-103">Defining Default Methods for Objects</span></span>

<span data-ttu-id="6f241-104">Ao estender .NET Framework objetos, você pode adicionar métodos de código e métodos de script aos objetos.</span><span class="sxs-lookup"><span data-stu-id="6f241-104">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span>
<span data-ttu-id="6f241-105">O XML que é usado para definir esses métodos é descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="6f241-105">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="6f241-106">Os exemplos nas seções a seguir são do `Types.ps1xml` arquivo de tipos no diretório de instalação do Windows PowerShell ( `$PSHOME` ).</span><span class="sxs-lookup"><span data-stu-id="6f241-106">The examples in the following sections are from the `Types.ps1xml` types file in the Windows PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="6f241-107">Para obter mais informações, consulte [About Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="6f241-107">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="code-methods"></a><span data-ttu-id="6f241-108">Métodos de código</span><span class="sxs-lookup"><span data-stu-id="6f241-108">Code methods</span></span>

<span data-ttu-id="6f241-109">Um método de código faz referência a um método estático de um objeto .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f241-109">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="6f241-110">No exemplo a seguir, o método **ToString** é adicionado ao tipo de [ nóSystem.Xml.Xml](/dotnet/api/System.Xml.XmlNode) .</span><span class="sxs-lookup"><span data-stu-id="6f241-110">In the following example, the **ToString** method is added to the [System.Xml.XmlNode](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="6f241-111">O elemento [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) define o método estendido como um método de código.</span><span class="sxs-lookup"><span data-stu-id="6f241-111">The [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element defines the extended method as a code method.</span></span> <span data-ttu-id="6f241-112">O elemento [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) especifica o nome do método estendido.</span><span class="sxs-lookup"><span data-stu-id="6f241-112">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="6f241-113">E, o elemento [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference) especifica o método estático.</span><span class="sxs-lookup"><span data-stu-id="6f241-113">And, the [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference) element specifies the static method.</span></span> <span data-ttu-id="6f241-114">Você também pode adicionar o elemento [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) aos membros do elemento [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) .</span><span class="sxs-lookup"><span data-stu-id="6f241-114">You can also add the [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

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

## <a name="script-methods"></a><span data-ttu-id="6f241-115">Métodos de script</span><span class="sxs-lookup"><span data-stu-id="6f241-115">Script methods</span></span>

<span data-ttu-id="6f241-116">Um método de script define um método cujo valor é a saída de um script.</span><span class="sxs-lookup"><span data-stu-id="6f241-116">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="6f241-117">No exemplo a seguir, o método **ConvertToDateTime** é adicionado ao tipo [System. Management. ManagementObject](/dotnet/api/System.Management.ManagementObject) .</span><span class="sxs-lookup"><span data-stu-id="6f241-117">In the following example, the **ConvertToDateTime** method is added to the [System.Management.ManagementObject](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="6f241-118">O elemento [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) define o método estendido como um método de script.</span><span class="sxs-lookup"><span data-stu-id="6f241-118">The [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) element defines the extended method as a script method.</span></span> <span data-ttu-id="6f241-119">O elemento [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) especifica o nome do método estendido.</span><span class="sxs-lookup"><span data-stu-id="6f241-119">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="6f241-120">E o elemento [script](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script) especifica o script que gera o valor do método.</span><span class="sxs-lookup"><span data-stu-id="6f241-120">And, the [Script](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script) element specifies the script that generates the method value.</span></span> <span data-ttu-id="6f241-121">Você também pode adicionar o elemento [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) aos membros do elemento [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) .</span><span class="sxs-lookup"><span data-stu-id="6f241-121">You can also add the [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6f241-122">Veja também</span><span class="sxs-lookup"><span data-stu-id="6f241-122">See also</span></span>

<span data-ttu-id="6f241-123">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="6f241-123">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
