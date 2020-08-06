---
title: Definindo conjuntos de membros padrão para objetos | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 80e1f54890d3aac1702414699ead16fcf38271e1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774619"
---
# <a name="defining-default-member-sets-for-objects"></a><span data-ttu-id="38d55-102">Definir os conjuntos de membro padrão para objetos</span><span class="sxs-lookup"><span data-stu-id="38d55-102">Defining Default Member Sets for Objects</span></span>

<span data-ttu-id="38d55-103">O conjunto de membros PSStandardMembers é usado pelo Windows PowerShell para definir os conjuntos de propriedades padrão para um objeto.</span><span class="sxs-lookup"><span data-stu-id="38d55-103">The PSStandardMembers member set is used by Windows PowerShell to define the default property sets for an object.</span></span> <span data-ttu-id="38d55-104">Os conjuntos de propriedades padrão podem ser usados por comandos como os cmdlets de formatação para exibir somente as propriedades definidas pelo conjunto de propriedades.</span><span class="sxs-lookup"><span data-stu-id="38d55-104">The default property sets can be used by commands such as the formatting cmdlets to display only those properties that are defined by the property set.</span></span> <span data-ttu-id="38d55-105">Os conjuntos de propriedades padrão incluem DefaultDisplayProperty, DefaultDisplayPropertySet e DefaultKeyPropertySet.</span><span class="sxs-lookup"><span data-stu-id="38d55-105">The default property sets include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="38d55-106">O Windows PowerShell ignora todos os outros conjuntos de membros e quaisquer outros conjuntos de propriedades adicionados ao conjunto de membros PSStandardMembers.</span><span class="sxs-lookup"><span data-stu-id="38d55-106">Windows PowerShell ignores all other member sets and any other property sets added to the PSStandardMembers member set.</span></span>

## <a name="member-set-for-systemdiagnosticsprocess"></a><span data-ttu-id="38d55-107">Conjunto de membros para System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="38d55-107">Member Set for System.Diagnostics.Process</span></span>

<span data-ttu-id="38d55-108">No exemplo a seguir, o conjunto de membros PSStandardMembers define o conjunto de propriedades DefaultDisplayPropertySet para objetos [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="38d55-108">In the following example, the PSStandardMembers member set defines the DefaultDisplayPropertySet property set for [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects.</span></span> <span data-ttu-id="38d55-109">Esse conjunto de propriedades é usado pelo cmdlet [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) .</span><span class="sxs-lookup"><span data-stu-id="38d55-109">This property set is used by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span>

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

<span data-ttu-id="38d55-110">A saída a seguir mostra as propriedades padrão retornadas pelo cmdlet [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) .</span><span class="sxs-lookup"><span data-stu-id="38d55-110">The following output shows the default properties returned by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span> <span data-ttu-id="38d55-111">Somente as `Id` `Handles` Propriedades,, e `CPU` `Name` são retornadas para cada objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="38d55-111">Only the `Id`, `Handles`, `CPU`, and `Name` properties are returned for each process object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="38d55-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38d55-112">See Also</span></span>

[<span data-ttu-id="38d55-113">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38d55-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
