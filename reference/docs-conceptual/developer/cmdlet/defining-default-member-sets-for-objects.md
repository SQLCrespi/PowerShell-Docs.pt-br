---
title: Definindo conjuntos de membros padrão para objetos | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f94326-8ffe-4d40-bd2a-b79fb0b4a4e5
caps.latest.revision: 8
ms.openlocfilehash: 2d634e7638ec0e0117d65ca0b2d08e68f0068a03
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369775"
---
# <a name="defining-default-member-sets-for-objects"></a><span data-ttu-id="f4c1c-102">Definir os conjuntos de membro padrão para objetos</span><span class="sxs-lookup"><span data-stu-id="f4c1c-102">Defining Default Member Sets for Objects</span></span>

<span data-ttu-id="f4c1c-103">O conjunto de membros PSStandardMembers é usado pelo Windows PowerShell para definir os conjuntos de propriedades padrão para um objeto.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-103">The PSStandardMembers member set is used by Windows PowerShell to define the default property sets for an object.</span></span> <span data-ttu-id="f4c1c-104">Os conjuntos de propriedades padrão podem ser usados por comandos como os cmdlets de formatação para exibir somente as propriedades definidas pelo conjunto de propriedades.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-104">The default property sets can be used by commands such as the formatting cmdlets to display only those properties that are defined by the property set.</span></span> <span data-ttu-id="f4c1c-105">Os conjuntos de propriedades padrão incluem DefaultDisplayProperty, DefaultDisplayPropertySet e DefaultKeyPropertySet.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-105">The default property sets include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="f4c1c-106">O Windows PowerShell ignora todos os outros conjuntos de membros e quaisquer outros conjuntos de propriedades adicionados ao conjunto de membros PSStandardMembers.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-106">Windows PowerShell ignores all other member sets and any other property sets added to the PSStandardMembers member set.</span></span>

## <a name="member-set-for-systemdiagnosticsprocess"></a><span data-ttu-id="f4c1c-107">Conjunto de membros para System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="f4c1c-107">Member Set for System.Diagnostics.Process</span></span>

<span data-ttu-id="f4c1c-108">No exemplo a seguir, o conjunto de membros PSStandardMembers define o conjunto de propriedades DefaultDisplayPropertySet para objetos [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="f4c1c-108">In the following example, the PSStandardMembers member set defines the DefaultDisplayPropertySet property set for [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects.</span></span> <span data-ttu-id="f4c1c-109">Esse conjunto de propriedades é usado pelo cmdlet [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) .</span><span class="sxs-lookup"><span data-stu-id="f4c1c-109">This property set is used by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span>

```xml
<Type>
  <Name>System.Diagnostics.Process</Name>
  <Members>
    <MemberSet>
     <Name>PSStandardMembers</Name>
     <Members>
       <PropertySet>
         <Name>DefaultDisplayPropertySet</Name>
         <ReferencedProperties>
           <Name>Id</Name>
           <Name>Handles</Name>
           <Name>CPU</Name>
           <Name>Name</Name>
         </ReferencedProperties>
      </PropertySet>
    </Members>
  </MemberSet>
```

<span data-ttu-id="f4c1c-110">A saída a seguir mostra as propriedades padrão retornadas pelo cmdlet [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) .</span><span class="sxs-lookup"><span data-stu-id="f4c1c-110">The following output shows the default properties returned by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span> <span data-ttu-id="f4c1c-111">Somente as propriedades `Id`, `Handles`, `CPU` e `Name` são retornadas para cada objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-111">Only the `Id`, `Handles`, `CPU`, and `Name` properties are returned for each process object.</span></span>

```powershell
Get-Process | format-list
```

```output
Id      : 2036
Handles : 27
CPU     :
Name    : AEADISRV

Id      : 272
Handles : 38
CPU     :
Name    : agrsmsvc
...
```

## <a name="see-also"></a><span data-ttu-id="f4c1c-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4c1c-112">See Also</span></span>

<span data-ttu-id="f4c1c-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f4c1c-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
