---
title: Definindo os métodos padrão para objetos | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53fe744a-485f-4c21-9623-1cb546372211
caps.latest.revision: 9
ms.openlocfilehash: fa0f0371856d8723af7ec17a4306de209a481a18
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068208"
---
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="f04f6-102">Definir os métodos padrão para objetos</span><span class="sxs-lookup"><span data-stu-id="f04f6-102">Defining Default Methods for Objects</span></span>

<span data-ttu-id="f04f6-103">Quando você estende objetos do .NET Framework, você pode adicionar métodos de código e de script para os objetos.</span><span class="sxs-lookup"><span data-stu-id="f04f6-103">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span> <span data-ttu-id="f04f6-104">O XML que é usado para definir esses métodos é descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="f04f6-104">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="f04f6-105">Os exemplos nas seções a seguir são do arquivo de tipos ps1xml no diretório de instalação do Windows PowerShell (`$pshome`).</span><span class="sxs-lookup"><span data-stu-id="f04f6-105">The examples in the following sections are from the Types.ps1xml types file in the Windows PowerShell installation directory (`$pshome`).</span></span>

## <a name="code-methods"></a><span data-ttu-id="f04f6-106">Métodos de código</span><span class="sxs-lookup"><span data-stu-id="f04f6-106">Code Methods</span></span>

<span data-ttu-id="f04f6-107">Um método de código faz referência a um método estático de um objeto do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f04f6-107">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="f04f6-108">No exemplo a seguir, o **ConvertLargeIntegerToInt64** método é adicionado para o [XmlNode? Displayproperty = Fullname](/dotnet/api/System.Xml.XmlNode) tipo.</span><span class="sxs-lookup"><span data-stu-id="f04f6-108">In the following example, the **ConvertLargeIntegerToInt64** method is added to the [System.Xml.Xmlnode?Displayproperty=Fullname](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="f04f6-109">O [CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05) elemento define o método estendido como um método de código.</span><span class="sxs-lookup"><span data-stu-id="f04f6-109">The [CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05) element defines the extended method as a code method.</span></span> <span data-ttu-id="f04f6-110">O [nome](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) elemento Especifica o nome do método estendido.</span><span class="sxs-lookup"><span data-stu-id="f04f6-110">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the extended method.</span></span> <span data-ttu-id="f04f6-111">Além disso, o [CodeReference](http://msdn.microsoft.com/en-us/70017b85-18d2-4f55-8357-92f309d5618b) elemento Especifica o método estático.</span><span class="sxs-lookup"><span data-stu-id="f04f6-111">And, the [CodeReference](http://msdn.microsoft.com/en-us/70017b85-18d2-4f55-8357-92f309d5618b) element specifies the static method.</span></span> <span data-ttu-id="f04f6-112">(Você também pode adicionar o [CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05) elemento aos membros do [conjuntos](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) elemento.)</span><span class="sxs-lookup"><span data-stu-id="f04f6-112">(You can also add the [CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05) element to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

```xml
<Type>
  <Name>System.Xml.XmlNode</Name>
  <Members>
    <CodeMethod>
      <Name>ToString</Name>
      <CodeReference>
        <TypeName>Microsoft.PowerShell.ToStringCodemethods</TypeName>
        <MethodName>XmlNode</MethodName>
      </CodeReference>
    </CodeMethod>
  </Members>
</Type>
```

## <a name="script-methods"></a><span data-ttu-id="f04f6-113">Métodos de script</span><span class="sxs-lookup"><span data-stu-id="f04f6-113">Script Methods</span></span>

<span data-ttu-id="f04f6-114">Um método de script define um método cujo valor é a saída de um script.</span><span class="sxs-lookup"><span data-stu-id="f04f6-114">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="f04f6-115">No exemplo a seguir, o **ConvertToDateTime** método é adicionado para o [System.Management.Managementobject? Displayproperty = Fullname](/dotnet/api/System.Management.ManagementObject) tipo.</span><span class="sxs-lookup"><span data-stu-id="f04f6-115">In the following example, the **ConvertToDateTime** method is added to the [System.Management.Managementobject?Displayproperty=Fullname](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="f04f6-116">O [ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c) elemento define o método estendido como um método de script.</span><span class="sxs-lookup"><span data-stu-id="f04f6-116">The [ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c) element defines the extended method as a script method.</span></span> <span data-ttu-id="f04f6-117">O [nome](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) elemento Especifica o nome do método estendido.</span><span class="sxs-lookup"><span data-stu-id="f04f6-117">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the extended method.</span></span> <span data-ttu-id="f04f6-118">Além disso, o [Script](http://msdn.microsoft.com/en-us/1937ad1b-bb2b-4512-9864-01fc0767d46f) elemento Especifica o script que gera o valor do método.</span><span class="sxs-lookup"><span data-stu-id="f04f6-118">And, the [Script](http://msdn.microsoft.com/en-us/1937ad1b-bb2b-4512-9864-01fc0767d46f) element specifies the script that generates the method value.</span></span> <span data-ttu-id="f04f6-119">(Você também pode adicionar o [ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c) elemento aos membros do [conjuntos](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) elemento.)</span><span class="sxs-lookup"><span data-stu-id="f04f6-119">(You can also add the [ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c) element to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f04f6-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f04f6-120">See Also</span></span>

<span data-ttu-id="f04f6-121">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f04f6-121">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>