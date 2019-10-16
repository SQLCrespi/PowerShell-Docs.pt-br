---
title: Estendendo objetos de saída | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a252e0ec-d456-42d7-bd49-d6b8bc57f388
caps.latest.revision: 11
ms.openlocfilehash: 9c9d50c880f843e21621e5735c800e3afb48b2ad
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369715"
---
# <a name="extending-output-objects"></a><span data-ttu-id="c3d6b-102">Estender os objetos de saída</span><span class="sxs-lookup"><span data-stu-id="c3d6b-102">Extending Output Objects</span></span>

<span data-ttu-id="c3d6b-103">Você pode estender os objetos de .NET Framework que são retornados por cmdlets, funções e scripts usando arquivos de tipos (. ps1xml).</span><span class="sxs-lookup"><span data-stu-id="c3d6b-103">You can extend the .NET Framework objects that are returned by cmdlets, functions, and scripts by using types files (.ps1xml).</span></span> <span data-ttu-id="c3d6b-104">Os arquivos de tipos são arquivos baseados em XML que permitem adicionar propriedades e métodos a objetos existentes.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-104">Types files are XML-based files that let you add properties and methods to existing objects.</span></span> <span data-ttu-id="c3d6b-105">Por exemplo, o Windows PowerShell fornece o arquivo Types. ps1xml, que adiciona elementos a vários objetos de .NET Framework existentes.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-105">For example, Windows PowerShell provides the Types.ps1xml file, which adds elements to several existing .NET Framework objects.</span></span> <span data-ttu-id="c3d6b-106">O arquivo Types. ps1xml está localizado no diretório de instalação do Windows PowerShell (`$pshome`).</span><span class="sxs-lookup"><span data-stu-id="c3d6b-106">The Types.ps1xml file is located in the Windows PowerShell installation directory (`$pshome`).</span></span> <span data-ttu-id="c3d6b-107">Você pode criar seu próprio arquivo de tipos para estender ainda mais esses objetos ou para estender outros objetos.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-107">You can create your own types file to further extend those objects or to extend other objects.</span></span> <span data-ttu-id="c3d6b-108">Quando você estende um objeto usando um arquivo de tipos, qualquer instância do objeto é estendida com os novos elementos.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-108">When you extend an object by using a types file, any instance of the object is extended with the new elements.</span></span>

## <a name="extending-the-systemarray-object"></a><span data-ttu-id="c3d6b-109">Estendendo o objeto System. array</span><span class="sxs-lookup"><span data-stu-id="c3d6b-109">Extending the System.Array Object</span></span>

<span data-ttu-id="c3d6b-110">O exemplo a seguir mostra como o Windows PowerShell estende o objeto [System. array](/dotnet/api/System.Array) no arquivo Types. ps1xml.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-110">The following example shows how Windows PowerShell extends the [System.Array](/dotnet/api/System.Array) object in the Types.ps1xml file.</span></span> <span data-ttu-id="c3d6b-111">Por padrão, os objetos [System. array](/dotnet/api/System.Array) têm uma propriedade `Length` que lista o número de objetos na matriz.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-111">By default, [System.Array](/dotnet/api/System.Array) objects have a `Length` property that lists the number of objects in the array.</span></span> <span data-ttu-id="c3d6b-112">No entanto, como o nome "Length" não descreve claramente a propriedade, o Windows PowerShell adiciona a propriedade de alias `Count`, que exibe o mesmo valor que a propriedade `Length`.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-112">However, because the name "length" does not clearly describe the property, Windows PowerShell adds the `Count` alias property, which displays the same value as the `Length` property.</span></span> <span data-ttu-id="c3d6b-113">O XML a seguir adiciona a propriedade `Count` ao tipo [System. array](/dotnet/api/System.Array) .</span><span class="sxs-lookup"><span data-stu-id="c3d6b-113">The following XML adds the `Count` property to the [System.Array](/dotnet/api/System.Array) type.</span></span>

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

<span data-ttu-id="c3d6b-114">Para ver essa nova propriedade de alias, use um comando [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) em qualquer matriz, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-114">To see this new alias property, use a [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="c3d6b-115">O comando retorna os seguintes resultados.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-115">The command returns the following results.</span></span>
```output
Name           MemberType    Definition
----           ----------    ----------
Count          AliasProperty Count = Length
Address        Method        System.Object& Address(Int32 )
Clone          Method        System.Object Clone()
CopyTo         Method        System.Void CopyTo(Array array, Int32 index):
Equals         Method        System.Boolean Equals(Object obj)
Get            Method        System.Object Get(Int32 )
...
Length         Property      System.Int32 Length {get;}
```
<span data-ttu-id="c3d6b-116">Você pode usar a propriedade `Count` ou a propriedade `Length` para determinar quantos objetos estão em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-116">You can use either the `Count` property or the `Length` property to determine how many objects are in an array.</span></span> <span data-ttu-id="c3d6b-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c3d6b-117">For example:</span></span>

```powershell
PS> (1, 2, 3, 4).Count
```

```output
4
```

```powershell
PS> (1, 2, 3, 4).Length
```

```output
4
```

## <a name="custom-types-files"></a><span data-ttu-id="c3d6b-118">Arquivos de tipos personalizados</span><span class="sxs-lookup"><span data-stu-id="c3d6b-118">Custom Types Files</span></span>

<span data-ttu-id="c3d6b-119">Para criar um arquivo de tipos personalizados, comece copiando um arquivo de tipos existente.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-119">To create a custom types file, start by copying an existing types file.</span></span> <span data-ttu-id="c3d6b-120">O novo arquivo pode ter qualquer nome, mas deve ter uma extensão de nome de arquivo. ps1xml.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-120">The new file can have any name, but it must have a .ps1xml file name extension.</span></span> <span data-ttu-id="c3d6b-121">Ao copiar o arquivo, você pode colocá-lo em qualquer diretório acessível ao Windows PowerShell, mas é útil colocá-los no diretório de instalação do Windows PowerShell (`$pshome`) ou em um subdiretório do diretório de instalação.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-121">When you copy the file, you can place the new file in any directory that is accessible to Windows PowerShell, but it is useful to place the files in the Windows PowerShell installation directory (`$pshome`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="c3d6b-122">Para adicionar seus próprios tipos estendidos ao arquivo, adicione um elemento de tipos para cada objeto que você deseja estender.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-122">To add your own extended types to the file, add a types element for each object that you want to extend.</span></span> <span data-ttu-id="c3d6b-123">Os tópicos a seguir fornecem exemplos.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-123">The following topics provide examples.</span></span>

- <span data-ttu-id="c3d6b-124">Para obter mais informações sobre a adição de propriedades e conjuntos de propriedades, consulte [Propriedades estendidas](./extending-properties-for-objects.md)</span><span class="sxs-lookup"><span data-stu-id="c3d6b-124">For more information about adding properties and property sets, see [Extended Properties](./extending-properties-for-objects.md)</span></span>

- <span data-ttu-id="c3d6b-125">Para obter mais informações sobre como adicionar métodos, consulte [métodos estendidos](./defining-default-methods-for-objects.md).</span><span class="sxs-lookup"><span data-stu-id="c3d6b-125">For more information about adding methods, see [Extended Methods](./defining-default-methods-for-objects.md).</span></span>

- <span data-ttu-id="c3d6b-126">Para obter mais informações sobre como adicionar conjuntos de membros, consulte [conjuntos de membros estendidos](./defining-default-member-sets-for-objects.md).</span><span class="sxs-lookup"><span data-stu-id="c3d6b-126">For more information about adding member sets, see [Extended Member Sets](./defining-default-member-sets-for-objects.md).</span></span>

<span data-ttu-id="c3d6b-127">Depois de definir seus próprios tipos estendidos, use um dos seguintes métodos para disponibilizar seus objetos estendidos:</span><span class="sxs-lookup"><span data-stu-id="c3d6b-127">After you define your own extended types, use one of the following methods to make your extended objects available:</span></span>

- <span data-ttu-id="c3d6b-128">Para tornar o arquivo de tipos estendidos disponível para a sessão atual, use o cmdlet [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) para adicionar o novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-128">To make your extended types file available to the current session, use the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet to add the new file.</span></span> <span data-ttu-id="c3d6b-129">Se você quiser que seus tipos tenham precedência sobre os tipos que são definidos em outros tipos de arquivos (incluindo o arquivo Types. ps1xml), use o parâmetro `PrependData` do cmdlet [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) .</span><span class="sxs-lookup"><span data-stu-id="c3d6b-129">If you want your types to take precedence over the types that are defined in other types files (including the Types.ps1xml file), use the `PrependData` parameter of the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet.</span></span>
- <span data-ttu-id="c3d6b-130">Para disponibilizar o arquivo de tipos estendidos para todas as sessões futuras, adicione o arquivo de tipos a um módulo, exporte a sessão atual ou adicione o comando [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) ao seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-130">To make your extended types file available to all future sessions, add the types file to a module, export the current session, or add the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) command to your Windows PowerShell profile.</span></span>

## <a name="signing-types-files"></a><span data-ttu-id="c3d6b-131">Arquivos de tipos de assinatura</span><span class="sxs-lookup"><span data-stu-id="c3d6b-131">Signing Types Files</span></span>

<span data-ttu-id="c3d6b-132">Os arquivos de tipos devem ser assinados digitalmente para evitar a violação, pois o XML pode incluir blocos de script.</span><span class="sxs-lookup"><span data-stu-id="c3d6b-132">Types files should be digitally signed to prevent tampering because the XML can include script blocks.</span></span> <span data-ttu-id="c3d6b-133">Para obter mais informações sobre como adicionar assinaturas digitais, consulte [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span><span class="sxs-lookup"><span data-stu-id="c3d6b-133">For more information about adding digital signatures, see [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span></span>

## <a name="see-also"></a><span data-ttu-id="c3d6b-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3d6b-134">See Also</span></span>

[<span data-ttu-id="c3d6b-135">Definindo propriedades padrão para objetos</span><span class="sxs-lookup"><span data-stu-id="c3d6b-135">Defining Default Properties for Objects</span></span>](./extending-properties-for-objects.md)

[<span data-ttu-id="c3d6b-136">Definindo métodos padrão para objetos</span><span class="sxs-lookup"><span data-stu-id="c3d6b-136">Defining Default Methods for Objects</span></span>](./defining-default-methods-for-objects.md)

[<span data-ttu-id="c3d6b-137">Definindo conjuntos de membros padrão para objetos</span><span class="sxs-lookup"><span data-stu-id="c3d6b-137">Defining Default Member Sets for Objects</span></span>](./defining-default-member-sets-for-objects.md)

<span data-ttu-id="c3d6b-138">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c3d6b-138">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
