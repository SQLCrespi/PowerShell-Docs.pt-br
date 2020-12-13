---
ms.date: 08/21/2019
ms.topic: reference
title: Estender as propriedades para objetos
description: Estender as propriedades para objetos
ms.openlocfilehash: 37803d9fd87319204565c2abde62f269744481b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652881"
---
# <a name="extending-properties-for-objects"></a><span data-ttu-id="d2e9b-103">Estender as propriedades para objetos</span><span class="sxs-lookup"><span data-stu-id="d2e9b-103">Extending Properties for Objects</span></span>

<span data-ttu-id="d2e9b-104">Ao estender .NET Framework objetos, você pode adicionar propriedades de alias, propriedades de código, propriedades de observação, propriedades de script e conjuntos de propriedades aos objetos.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-104">When you extend .NET Framework objects, you can add alias properties, code properties, note properties, script properties, and property sets to the objects.</span></span> <span data-ttu-id="d2e9b-105">O XML que define essas propriedades é descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-105">The XML that defines these properties is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="d2e9b-106">Os exemplos nas seções a seguir são do arquivo de `Types.ps1xml` tipos padrão no diretório de instalação do PowerShell ( `$PSHOME` ).</span><span class="sxs-lookup"><span data-stu-id="d2e9b-106">The examples in the following sections are from the default `Types.ps1xml` types file in the PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="d2e9b-107">Para obter mais informações, consulte [About Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="d2e9b-107">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="alias-properties"></a><span data-ttu-id="d2e9b-108">Propriedades do alias</span><span class="sxs-lookup"><span data-stu-id="d2e9b-108">Alias properties</span></span>

<span data-ttu-id="d2e9b-109">Uma propriedade de alias define um novo nome para uma propriedade existente.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-109">An alias property defines a new name for an existing property.</span></span>

<span data-ttu-id="d2e9b-110">No exemplo a seguir, a propriedade **Count** é adicionada ao tipo [System. array](/dotnet/api/System.Array) .</span><span class="sxs-lookup"><span data-stu-id="d2e9b-110">In the following example, the **Count** property is added to the [System.Array](/dotnet/api/System.Array) type.</span></span> <span data-ttu-id="d2e9b-111">O elemento [AliasProperty](/dotnet/api/system.management.automation.psaliasproperty) define a propriedade estendida como uma propriedade de alias.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-111">The [AliasProperty](/dotnet/api/system.management.automation.psaliasproperty) element defines the extended property as an alias property.</span></span> <span data-ttu-id="d2e9b-112">O elemento [Name](/dotnet/api/system.management.automation.psmemberinfo.name) especifica o novo nome.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-112">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the new name.</span></span> <span data-ttu-id="d2e9b-113">E, o elemento [ReferencedMemberName](/dotnet/api/system.management.automation.psaliasproperty.referencedmembername) especifica a propriedade existente que é referenciada pelo alias.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-113">And, the [ReferencedMemberName](/dotnet/api/system.management.automation.psaliasproperty.referencedmembername) element specifies the existing property that is referenced by the alias.</span></span> <span data-ttu-id="d2e9b-114">Você também pode adicionar o `AliasProperty` elemento aos membros do elemento [MemberSets](/dotnet/api/system.management.automation.psmemberset) .</span><span class="sxs-lookup"><span data-stu-id="d2e9b-114">You can also add the `AliasProperty` element to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

## <a name="code-properties"></a><span data-ttu-id="d2e9b-115">Propriedades do código</span><span class="sxs-lookup"><span data-stu-id="d2e9b-115">Code properties</span></span>

<span data-ttu-id="d2e9b-116">Uma propriedade de código faz referência a uma propriedade estática de um objeto .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-116">A code property references a static property of a .NET Framework object.</span></span>

<span data-ttu-id="d2e9b-117">No exemplo a seguir, a propriedade **Mode** é adicionada ao tipo [System. IO. DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) .</span><span class="sxs-lookup"><span data-stu-id="d2e9b-117">In the following example, the **Mode** property is added to the [System.IO.DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) type.</span></span> <span data-ttu-id="d2e9b-118">O elemento [CodeProperty](/dotnet/api/system.management.automation.pscodeproperty) define a propriedade estendida como uma propriedade de código.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-118">The [CodeProperty](/dotnet/api/system.management.automation.pscodeproperty) element defines the extended property as a code property.</span></span> <span data-ttu-id="d2e9b-119">O elemento [Name](/dotnet/api/system.management.automation.psmemberinfo.name) especifica o nome da propriedade estendida.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-119">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the extended property.</span></span> <span data-ttu-id="d2e9b-120">E, o elemento [GetCodeReference](/dotnet/api/system.management.automation.pscodeproperty.gettercodereference) define o método estático que é referenciado pela propriedade estendida.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-120">And, the [GetCodeReference](/dotnet/api/system.management.automation.pscodeproperty.gettercodereference) element defines the static method that is referenced by the extended property.</span></span> <span data-ttu-id="d2e9b-121">Você também pode adicionar o `CodeProperty` elemento aos membros do elemento [MemberSets](/dotnet/api/system.management.automation.psmemberset) .</span><span class="sxs-lookup"><span data-stu-id="d2e9b-121">You can also add the `CodeProperty` element to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>Microsoft.PowerShell.Commands.FileSystemProvider</TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

## <a name="note-properties"></a><span data-ttu-id="d2e9b-122">Anotar propriedades</span><span class="sxs-lookup"><span data-stu-id="d2e9b-122">Note properties</span></span>

<span data-ttu-id="d2e9b-123">Uma propriedade Note define uma propriedade que tem um valor estático.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-123">A note property defines a property that has a static value.</span></span>

<span data-ttu-id="d2e9b-124">No exemplo a seguir, a propriedade **status** , cujo valor é sempre **êxito**, é adicionada ao tipo [System. IO. DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) .</span><span class="sxs-lookup"><span data-stu-id="d2e9b-124">In the following example, the **Status** property, whose value is always **Success**, is added to the [System.IO.DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) type.</span></span> <span data-ttu-id="d2e9b-125">O elemento [NoteProperty](/dotnet/api/system.management.automation.psnoteproperty) define a propriedade estendida como uma propriedade de observação.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-125">The [NoteProperty](/dotnet/api/system.management.automation.psnoteproperty) element defines the extended property as a note property.</span></span> <span data-ttu-id="d2e9b-126">O elemento [Name](/dotnet/api/system.management.automation.psmemberinfo.name) especifica o nome da propriedade estendida.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-126">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the extended property.</span></span> <span data-ttu-id="d2e9b-127">O elemento [Value](/dotnet/api/system.management.automation.psnoteproperty.value) especifica o valor estático da propriedade estendida.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-127">The [Value](/dotnet/api/system.management.automation.psnoteproperty.value) element specifies the static value of the extended property.</span></span> <span data-ttu-id="d2e9b-128">O `NoteProperty` elemento também pode ser adicionado aos membros do elemento [MemberSets](/dotnet/api/system.management.automation.psmemberset) .</span><span class="sxs-lookup"><span data-stu-id="d2e9b-128">The `NoteProperty` element can also be added to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <NoteProperty>
      <Name>Status</Name>
      <Value>Success</Value>
    </NoteProperty>
  </Members>
</Type>
```

## <a name="script-properties"></a><span data-ttu-id="d2e9b-129">Propriedades do script</span><span class="sxs-lookup"><span data-stu-id="d2e9b-129">Script properties</span></span>

<span data-ttu-id="d2e9b-130">Uma propriedade de script define uma propriedade cujo valor é a saída de um script.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-130">A script property defines a property whose value is the output of a script.</span></span>

<span data-ttu-id="d2e9b-131">No exemplo a seguir, a propriedade **VERSIONINFO** é adicionada ao tipo [System. IO. FileInfo](/dotnet/api/System.IO.FileInfo) .</span><span class="sxs-lookup"><span data-stu-id="d2e9b-131">In the following example, the **VersionInfo** property is added to the [System.IO.FileInfo](/dotnet/api/System.IO.FileInfo) type.</span></span> <span data-ttu-id="d2e9b-132">O elemento [ScriptProperty](/dotnet/api/system.management.automation.psscriptproperty) define a propriedade estendida como uma propriedade de script.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-132">The [ScriptProperty](/dotnet/api/system.management.automation.psscriptproperty) element defines the extended property as a script property.</span></span> <span data-ttu-id="d2e9b-133">O elemento [Name](/dotnet/api/system.management.automation.psmemberinfo.name) especifica o nome da propriedade estendida.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-133">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the extended property.</span></span> <span data-ttu-id="d2e9b-134">E, o elemento [getscriptblock](/dotnet/api/system.management.automation.psscriptproperty.getterscript) especifica o script que gera o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-134">And, the [GetScriptBlock](/dotnet/api/system.management.automation.psscriptproperty.getterscript) element specifies the script that generates the property value.</span></span> <span data-ttu-id="d2e9b-135">Você também pode adicionar o `ScriptProperty` elemento aos membros do elemento [MemberSets](/dotnet/api/system.management.automation.psmemberset) .</span><span class="sxs-lookup"><span data-stu-id="d2e9b-135">You can also add the `ScriptProperty` element to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.IO.FileInfo</Name>
  <Members>
    <ScriptProperty>
      <Name>VersionInfo</Name>
      <GetScriptBlock>
        [System.Diagnostics.FileVersionInfo]::GetVersionInfo($this.FullName)
      </GetScriptBlock>
    </ScriptProperty>
  </Members>
</Type>
```

## <a name="property-sets"></a><span data-ttu-id="d2e9b-136">Conjuntos de propriedades</span><span class="sxs-lookup"><span data-stu-id="d2e9b-136">Property sets</span></span>

<span data-ttu-id="d2e9b-137">Um conjunto de propriedades define um grupo de propriedades estendidas que podem ser referenciadas pelo nome do conjunto.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-137">A property set defines a group of extended properties that can be referenced by the name of the set.</span></span>
<span data-ttu-id="d2e9b-138">Por exemplo, o parâmetro de propriedade [Format-Table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table) 
  pode especificar um conjunto de propriedades específico a ser exibido.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-138">For example, the [Format-Table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table)
**Property** parameter can specify a specific property set to be displayed.</span></span> <span data-ttu-id="d2e9b-139">Quando um conjunto de propriedades é especificado, somente as propriedades que pertencem ao conjunto são exibidas.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-139">When a property set is specified, only those properties that belong to the set are displayed.</span></span>

<span data-ttu-id="d2e9b-140">Não há restrição quanto ao número de conjuntos de propriedades que podem ser definidos para um objeto.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-140">There's no restriction on the number of property sets that can be defined for an object.</span></span> <span data-ttu-id="d2e9b-141">No entanto, os conjuntos de propriedades usados para definir as propriedades de exibição padrão de um objeto devem ser especificados dentro do conjunto de membros **PSStandardMembers** .</span><span class="sxs-lookup"><span data-stu-id="d2e9b-141">However, the property sets used to define the default display properties of an object must be specified within the **PSStandardMembers** member set.</span></span> <span data-ttu-id="d2e9b-142">No `Types.ps1xml` arquivo Types, os nomes do conjunto de propriedades padrão incluem **DefaultDisplayProperty**, **DefaultDisplayPropertySet** e **DefaultKeyPropertySet**.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-142">In the `Types.ps1xml` types file, the default property set names include **DefaultDisplayProperty**, **DefaultDisplayPropertySet**, and **DefaultKeyPropertySet**.</span></span> <span data-ttu-id="d2e9b-143">Todos os conjuntos de propriedades adicionais que você adicionar ao conjunto de membros **PSStandardMembers** serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-143">Any additional property sets that you add to the **PSStandardMembers** member set are ignored.</span></span>

<span data-ttu-id="d2e9b-144">No exemplo a seguir, o conjunto de propriedades **DefaultDisplayPropertySet** é adicionado ao conjunto de membros **PSStandardMembers** do tipo [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="d2e9b-144">In the following example, the **DefaultDisplayPropertySet** property set is added to the **PSStandardMembers** member set of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) type.</span></span> <span data-ttu-id="d2e9b-145">O elemento [PropertySet](/dotnet/api/system.management.automation.pspropertyset) define o grupo de propriedades.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-145">The [PropertySet](/dotnet/api/system.management.automation.pspropertyset) element defines the group of properties.</span></span> <span data-ttu-id="d2e9b-146">O elemento [Name](/dotnet/api/system.management.automation.psmemberinfo.name) especifica o nome do conjunto de propriedades.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-146">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the property set.</span></span> <span data-ttu-id="d2e9b-147">E, o elemento [referenciaproperties](/dotnet/api/system.management.automation.pspropertyset.referencedpropertynames) especifica as propriedades do conjunto.</span><span class="sxs-lookup"><span data-stu-id="d2e9b-147">And, the [ReferencedProperties](/dotnet/api/system.management.automation.pspropertyset.referencedpropertynames) element specifies the properties of the set.</span></span> <span data-ttu-id="d2e9b-148">Você também pode adicionar o `PropertySet` elemento aos membros do elemento [Type](/dotnet/api/system.management.automation.pstypename) .</span><span class="sxs-lookup"><span data-stu-id="d2e9b-148">You can also add the `PropertySet` element to the members of the [Type](/dotnet/api/system.management.automation.pstypename) element.</span></span>

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
           <Name>DefaultDisplayPropertySet</Name>
           <ReferencedProperties>
            <Name>Status</Name
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

## <a name="see-also"></a><span data-ttu-id="d2e9b-149">Veja também</span><span class="sxs-lookup"><span data-stu-id="d2e9b-149">See also</span></span>

[<span data-ttu-id="d2e9b-150">Sobre o Types.ps1XML</span><span class="sxs-lookup"><span data-stu-id="d2e9b-150">About Types.ps1xml</span></span>](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)

[<span data-ttu-id="d2e9b-151">System.Management.Automation</span><span class="sxs-lookup"><span data-stu-id="d2e9b-151">System.Management.Automation</span></span>](/dotnet/api/System.Management.Automation)

<span data-ttu-id="d2e9b-152">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="d2e9b-152">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
