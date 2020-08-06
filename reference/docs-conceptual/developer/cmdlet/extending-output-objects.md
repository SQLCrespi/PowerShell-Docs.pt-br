---
title: Estendendo objetos de saída | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 48f4f2996159d84257ad72d499e3a796aeaa9116
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784309"
---
# <a name="extending-output-objects"></a><span data-ttu-id="f4d45-102">Estender os objetos de saída</span><span class="sxs-lookup"><span data-stu-id="f4d45-102">Extending Output Objects</span></span>

<span data-ttu-id="f4d45-103">Você pode estender os objetos de .NET Framework que são retornados por cmdlets, funções e scripts usando arquivos de tipos (. ps1xml).</span><span class="sxs-lookup"><span data-stu-id="f4d45-103">You can extend the .NET Framework objects that are returned by cmdlets, functions, and scripts by using types files (.ps1xml).</span></span> <span data-ttu-id="f4d45-104">Os arquivos de tipos são arquivos baseados em XML que permitem adicionar propriedades e métodos a objetos existentes.</span><span class="sxs-lookup"><span data-stu-id="f4d45-104">Types files are XML-based files that let you add properties and methods to existing objects.</span></span> <span data-ttu-id="f4d45-105">Por exemplo, o Windows PowerShell fornece o arquivo XML Types.ps1, que adiciona elementos a vários objetos .NET Framework existentes.</span><span class="sxs-lookup"><span data-stu-id="f4d45-105">For example, Windows PowerShell provides the Types.ps1xml file, which adds elements to several existing .NET Framework objects.</span></span> <span data-ttu-id="f4d45-106">O arquivo XML de Types.ps1está localizado no diretório de instalação do Windows PowerShell ( `$pshome` ).</span><span class="sxs-lookup"><span data-stu-id="f4d45-106">The Types.ps1xml file is located in the Windows PowerShell installation directory (`$pshome`).</span></span> <span data-ttu-id="f4d45-107">Você pode criar seu próprio arquivo de tipos para estender ainda mais esses objetos ou para estender outros objetos.</span><span class="sxs-lookup"><span data-stu-id="f4d45-107">You can create your own types file to further extend those objects or to extend other objects.</span></span> <span data-ttu-id="f4d45-108">Quando você estende um objeto usando um arquivo de tipos, qualquer instância do objeto é estendida com os novos elementos.</span><span class="sxs-lookup"><span data-stu-id="f4d45-108">When you extend an object by using a types file, any instance of the object is extended with the new elements.</span></span>

## <a name="extending-the-systemarray-object"></a><span data-ttu-id="f4d45-109">Estendendo o objeto System. array</span><span class="sxs-lookup"><span data-stu-id="f4d45-109">Extending the System.Array Object</span></span>

<span data-ttu-id="f4d45-110">O exemplo a seguir mostra como o Windows PowerShell estende o objeto [System. array](/dotnet/api/System.Array) no arquivo XML Types.ps1.</span><span class="sxs-lookup"><span data-stu-id="f4d45-110">The following example shows how Windows PowerShell extends the [System.Array](/dotnet/api/System.Array) object in the Types.ps1xml file.</span></span> <span data-ttu-id="f4d45-111">Por padrão, os objetos [System. array](/dotnet/api/System.Array) têm uma `Length` propriedade que lista o número de objetos na matriz.</span><span class="sxs-lookup"><span data-stu-id="f4d45-111">By default, [System.Array](/dotnet/api/System.Array) objects have a `Length` property that lists the number of objects in the array.</span></span> <span data-ttu-id="f4d45-112">No entanto, como o nome "Length" não descreve claramente a propriedade, o Windows PowerShell adiciona a `Count` Propriedade Alias, que exibe o mesmo valor que a `Length` propriedade.</span><span class="sxs-lookup"><span data-stu-id="f4d45-112">However, because the name "length" does not clearly describe the property, Windows PowerShell adds the `Count` alias property, which displays the same value as the `Length` property.</span></span> <span data-ttu-id="f4d45-113">O XML a seguir adiciona a `Count` propriedade ao tipo [System. array](/dotnet/api/System.Array) .</span><span class="sxs-lookup"><span data-stu-id="f4d45-113">The following XML adds the `Count` property to the [System.Array](/dotnet/api/System.Array) type.</span></span>

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

<span data-ttu-id="f4d45-114">Para ver essa nova propriedade de alias, use um comando [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) em qualquer matriz, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4d45-114">To see this new alias property, use a [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="f4d45-115">O comando retorna os seguintes resultados.</span><span class="sxs-lookup"><span data-stu-id="f4d45-115">The command returns the following results.</span></span>

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

<span data-ttu-id="f4d45-116">Você pode usar a `Count` propriedade ou a `Length` propriedade para determinar quantos objetos estão em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="f4d45-116">You can use either the `Count` property or the `Length` property to determine how many objects are in an array.</span></span> <span data-ttu-id="f4d45-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4d45-117">For example:</span></span>

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

## <a name="custom-types-files"></a><span data-ttu-id="f4d45-118">Arquivos de tipos personalizados</span><span class="sxs-lookup"><span data-stu-id="f4d45-118">Custom Types Files</span></span>

<span data-ttu-id="f4d45-119">Para criar um arquivo de tipos personalizados, comece copiando um arquivo de tipos existente.</span><span class="sxs-lookup"><span data-stu-id="f4d45-119">To create a custom types file, start by copying an existing types file.</span></span> <span data-ttu-id="f4d45-120">O novo arquivo pode ter qualquer nome, mas deve ter uma extensão de nome de arquivo. ps1xml.</span><span class="sxs-lookup"><span data-stu-id="f4d45-120">The new file can have any name, but it must have a .ps1xml file name extension.</span></span> <span data-ttu-id="f4d45-121">Ao copiar o arquivo, você pode colocá-lo em qualquer diretório que seja acessível ao Windows PowerShell, mas é útil colocá-los no diretório de instalação do Windows PowerShell ( `$pshome` ) ou em um subdiretório do diretório de instalação.</span><span class="sxs-lookup"><span data-stu-id="f4d45-121">When you copy the file, you can place the new file in any directory that is accessible to Windows PowerShell, but it is useful to place the files in the Windows PowerShell installation directory (`$pshome`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="f4d45-122">Para adicionar seus próprios tipos estendidos ao arquivo, adicione um elemento de tipos para cada objeto que você deseja estender.</span><span class="sxs-lookup"><span data-stu-id="f4d45-122">To add your own extended types to the file, add a types element for each object that you want to extend.</span></span> <span data-ttu-id="f4d45-123">Os tópicos a seguir fornecem exemplos.</span><span class="sxs-lookup"><span data-stu-id="f4d45-123">The following topics provide examples.</span></span>

- <span data-ttu-id="f4d45-124">Para obter mais informações sobre a adição de propriedades e conjuntos de propriedades, consulte [Propriedades estendidas](./extending-properties-for-objects.md)</span><span class="sxs-lookup"><span data-stu-id="f4d45-124">For more information about adding properties and property sets, see [Extended Properties](./extending-properties-for-objects.md)</span></span>

- <span data-ttu-id="f4d45-125">Para obter mais informações sobre como adicionar métodos, consulte [métodos estendidos](./defining-default-methods-for-objects.md).</span><span class="sxs-lookup"><span data-stu-id="f4d45-125">For more information about adding methods, see [Extended Methods](./defining-default-methods-for-objects.md).</span></span>

- <span data-ttu-id="f4d45-126">Para obter mais informações sobre como adicionar conjuntos de membros, consulte [conjuntos de membros estendidos](./defining-default-member-sets-for-objects.md).</span><span class="sxs-lookup"><span data-stu-id="f4d45-126">For more information about adding member sets, see [Extended Member Sets](./defining-default-member-sets-for-objects.md).</span></span>

<span data-ttu-id="f4d45-127">Depois de definir seus próprios tipos estendidos, use um dos seguintes métodos para disponibilizar seus objetos estendidos:</span><span class="sxs-lookup"><span data-stu-id="f4d45-127">After you define your own extended types, use one of the following methods to make your extended objects available:</span></span>

- <span data-ttu-id="f4d45-128">Para tornar o arquivo de tipos estendidos disponível para a sessão atual, use o cmdlet [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) para adicionar o novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="f4d45-128">To make your extended types file available to the current session, use the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet to add the new file.</span></span> <span data-ttu-id="f4d45-129">Se você quiser que seus tipos tenham precedência sobre os tipos que são definidos em outros tipos de arquivos (incluindo o arquivo XML Types.ps1), use o `PrependData` parâmetro do cmdlet [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) .</span><span class="sxs-lookup"><span data-stu-id="f4d45-129">If you want your types to take precedence over the types that are defined in other types files (including the Types.ps1xml file), use the `PrependData` parameter of the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet.</span></span>
- <span data-ttu-id="f4d45-130">Para disponibilizar o arquivo de tipos estendidos para todas as sessões futuras, adicione o arquivo de tipos a um módulo, exporte a sessão atual ou adicione o comando [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) ao seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4d45-130">To make your extended types file available to all future sessions, add the types file to a module, export the current session, or add the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) command to your Windows PowerShell profile.</span></span>

## <a name="signing-types-files"></a><span data-ttu-id="f4d45-131">Arquivos de tipos de assinatura</span><span class="sxs-lookup"><span data-stu-id="f4d45-131">Signing Types Files</span></span>

<span data-ttu-id="f4d45-132">Os arquivos de tipos devem ser assinados digitalmente para evitar a violação, pois o XML pode incluir blocos de script.</span><span class="sxs-lookup"><span data-stu-id="f4d45-132">Types files should be digitally signed to prevent tampering because the XML can include script blocks.</span></span> <span data-ttu-id="f4d45-133">Para obter mais informações sobre como adicionar assinaturas digitais, consulte [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span><span class="sxs-lookup"><span data-stu-id="f4d45-133">For more information about adding digital signatures, see [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span></span>

## <a name="see-also"></a><span data-ttu-id="f4d45-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4d45-134">See Also</span></span>

[<span data-ttu-id="f4d45-135">Definindo propriedades padrão para objetos</span><span class="sxs-lookup"><span data-stu-id="f4d45-135">Defining Default Properties for Objects</span></span>](./extending-properties-for-objects.md)

[<span data-ttu-id="f4d45-136">Definir os métodos padrão para objetos</span><span class="sxs-lookup"><span data-stu-id="f4d45-136">Defining Default Methods for Objects</span></span>](./defining-default-methods-for-objects.md)

[<span data-ttu-id="f4d45-137">Definir os conjuntos de membro padrão para objetos</span><span class="sxs-lookup"><span data-stu-id="f4d45-137">Defining Default Member Sets for Objects</span></span>](./defining-default-member-sets-for-objects.md)

[<span data-ttu-id="f4d45-138">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4d45-138">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
