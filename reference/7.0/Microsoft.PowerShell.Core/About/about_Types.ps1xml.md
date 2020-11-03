---
description: Explica como usar `Types.ps1xml` arquivos para estender os tipos de objetos que são usados no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_`Types.ps1xml`?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Types.ps1xml
ms.openlocfilehash: c2b5cb2e0b97b31ee584baf743cb33c1c9b61ccd
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195939"
---
# <a name="about-typesps1xml"></a><span data-ttu-id="a93e2-104">Sobre o Types.ps1XML</span><span class="sxs-lookup"><span data-stu-id="a93e2-104">About Types.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="a93e2-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="a93e2-105">Short description</span></span>
<span data-ttu-id="a93e2-106">Explica como usar `Types.ps1xml` arquivos para estender os tipos de objetos que são usados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-106">Explains how to use `Types.ps1xml` files to extend the types of objects that are used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="a93e2-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="a93e2-107">Long description</span></span>

<span data-ttu-id="a93e2-108">Os dados de tipo estendido definem propriedades e métodos adicionais ("Membros") de tipos de objeto no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-108">Extended type data defines additional properties and methods ("members") of object types in PowerShell.</span></span> <span data-ttu-id="a93e2-109">Há duas técnicas para adicionar dados de tipo estendido a uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-109">There are two techniques for adding extended type data to a PowerShell session.</span></span>

- <span data-ttu-id="a93e2-110">`Types.ps1xml` arquivo: um arquivo XML que define dados de tipo estendido.</span><span class="sxs-lookup"><span data-stu-id="a93e2-110">`Types.ps1xml` file: An XML file that defines extended type data.</span></span>
- <span data-ttu-id="a93e2-111">`Update-TypeData`: Um cmdlet que recarrega `Types.ps1xml` arquivos e define dados estendidos para tipos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a93e2-111">`Update-TypeData`: A cmdlet that reloads `Types.ps1xml` files and defines extended data for types in the current session.</span></span>

<span data-ttu-id="a93e2-112">Este tópico descreve `Types.ps1xml` os arquivos do.</span><span class="sxs-lookup"><span data-stu-id="a93e2-112">This topic describes `Types.ps1xml` files.</span></span> <span data-ttu-id="a93e2-113">Para obter mais informações sobre como usar o `Update-TypeData` cmdlet para adicionar dados de tipo estendido dinâmico à sessão atual [, consulte Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span><span class="sxs-lookup"><span data-stu-id="a93e2-113">For more information about using the `Update-TypeData` cmdlet to add dynamic extended type data to the current session see [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span></span>

## <a name="about-extended-type-data"></a><span data-ttu-id="a93e2-114">Sobre os dados de tipo estendido</span><span class="sxs-lookup"><span data-stu-id="a93e2-114">About extended type data</span></span>

<span data-ttu-id="a93e2-115">Os dados de tipo estendido definem propriedades e métodos adicionais ("Membros") de tipos de objeto no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-115">Extended type data defines additional properties and methods ("members") of object types in PowerShell.</span></span> <span data-ttu-id="a93e2-116">Você pode estender qualquer tipo com suporte no PowerShell e usar as propriedades e os métodos adicionados da mesma maneira que usa as propriedades definidas nos tipos de objeto.</span><span class="sxs-lookup"><span data-stu-id="a93e2-116">You can extend any type that is supported by PowerShell and use the added properties and methods in the same way that you use the properties that are defined on the object types.</span></span>

<span data-ttu-id="a93e2-117">Por exemplo, o PowerShell adiciona uma propriedade **DateTime** a todos os `System.DateTime` objetos, como aqueles que o `Get-Date` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="a93e2-117">For example, PowerShell adds a **DateTime** property to all `System.DateTime` objects, such as the ones that the `Get-Date` cmdlet returns.</span></span>

```powershell
(Get-Date).DateTime
```

```Output
Sunday, January 29, 2012 9:43:57 AM
```

<span data-ttu-id="a93e2-118">Você não encontrará a propriedade **DateTime** na descrição da estrutura [System. DateTime](/dotnet/api/system.datetime) , porque o PowerShell adiciona a propriedade e ela é visível somente no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-118">You won't find the **DateTime** property in the description of the [System.DateTime](/dotnet/api/system.datetime) structure, because PowerShell adds the property and it is visible only in PowerShell.</span></span>

<span data-ttu-id="a93e2-119">O PowerShell define internamente um conjunto padrão de tipos estendidos.</span><span class="sxs-lookup"><span data-stu-id="a93e2-119">PowerShell internally defines a default set of extended types.</span></span> <span data-ttu-id="a93e2-120">Essas informações de tipo são carregadas em todas as sessões do PowerShell na inicialização.</span><span class="sxs-lookup"><span data-stu-id="a93e2-120">This type information is loaded in every PowerShell session at startup.</span></span> <span data-ttu-id="a93e2-121">A propriedade **DateTime** faz parte desse conjunto padrão.</span><span class="sxs-lookup"><span data-stu-id="a93e2-121">The **DateTime** property is part of this default set.</span></span> <span data-ttu-id="a93e2-122">Antes do PowerShell 6, as definições de tipo eram armazenadas no `Types.ps1xml` diretório de instalação do PowerShell ( `$PSHOME` ).</span><span class="sxs-lookup"><span data-stu-id="a93e2-122">Prior to PowerShell 6, the type definitions were stored the `Types.ps1xml` file in the PowerShell installation directory (`$PSHOME`).</span></span>

## <a name="adding-extended-type-data-to-powershell"></a><span data-ttu-id="a93e2-123">Adicionando dados de tipo estendido ao PowerShell</span><span class="sxs-lookup"><span data-stu-id="a93e2-123">Adding extended type data to PowerShell</span></span>

<span data-ttu-id="a93e2-124">Há três fontes de dados de tipo estendido em sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-124">There are three sources of extended type data in PowerShell sessions.</span></span>

- <span data-ttu-id="a93e2-125">O definido pelo PowerShell e é carregado automaticamente em cada sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-125">The defined by PowerShell and is loaded automatically into every PowerShell session.</span></span> <span data-ttu-id="a93e2-126">A partir do PowerShell 6, essas informações são compiladas no PowerShell e não são mais enviadas em um `Types.ps1xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="a93e2-126">Beginning with PowerShell 6, this information is compiled into PowerShell and is no longer shipped in a `Types.ps1xml` file.</span></span>

- <span data-ttu-id="a93e2-127">Os `Types.ps1xml` arquivos que os módulos exportam são carregados quando o módulo é importado para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a93e2-127">The `Types.ps1xml` files that modules export are loaded when the module is imported into the current session.</span></span>

- <span data-ttu-id="a93e2-128">Os dados de tipo estendido que são definidos usando o `Update-TypeData` cmdlet são adicionados somente à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a93e2-128">Extended type data that is defined by using the `Update-TypeData` cmdlet is added only to the current session.</span></span> <span data-ttu-id="a93e2-129">Ele não é salvo em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a93e2-129">It is not saved in a file.</span></span>

<span data-ttu-id="a93e2-130">Na sessão, os dados de tipo estendido das três fontes são aplicados aos objetos da mesma maneira e estão disponíveis em todos os objetos dos tipos especificados.</span><span class="sxs-lookup"><span data-stu-id="a93e2-130">In the session, the extended type data from the three sources is applied to objects in the same way and is available on all objects of the specified types.</span></span>

## <a name="the-typedata-cmdlets"></a><span data-ttu-id="a93e2-131">Os cmdlets TypeData</span><span class="sxs-lookup"><span data-stu-id="a93e2-131">The TypeData cmdlets</span></span>

<span data-ttu-id="a93e2-132">Os cmdlets a seguir estão incluídos no módulo **Microsoft. PowerShell. Utility** no PowerShell 3,0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="a93e2-132">The following cmdlets are included in the **Microsoft.PowerShell.Utility** module in PowerShell 3.0 and later.</span></span>

- <span data-ttu-id="a93e2-133">`Get-TypeData`: Obtém dados de tipo estendido na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a93e2-133">`Get-TypeData`: Gets extended type data in the current session.</span></span>
- <span data-ttu-id="a93e2-134">`Update-TypeData`: Recarrega `Types.ps1xml` os arquivos.</span><span class="sxs-lookup"><span data-stu-id="a93e2-134">`Update-TypeData`: Reloads `Types.ps1xml` files.</span></span> <span data-ttu-id="a93e2-135">Adiciona dados de tipo estendido à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a93e2-135">Adds extended type data to the current session.</span></span>
- <span data-ttu-id="a93e2-136">`Remove-TypeData`: Remove dados de tipo estendido da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a93e2-136">`Remove-TypeData`: Removes extended type data from the current session.</span></span>

<span data-ttu-id="a93e2-137">Para obter mais informações sobre esses cmdlets, consulte o tópico da ajuda para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a93e2-137">For more information about these cmdlets, see the help topic for each cmdlet.</span></span>

## <a name="built-in-typesps1xml-files"></a><span data-ttu-id="a93e2-138">Arquivos XML internos Types.ps1</span><span class="sxs-lookup"><span data-stu-id="a93e2-138">Built-in Types.ps1xml files</span></span>

<span data-ttu-id="a93e2-139">Os `Types.ps1xml` arquivos no `$PSHOME` diretório são adicionados automaticamente a cada sessão.</span><span class="sxs-lookup"><span data-stu-id="a93e2-139">The `Types.ps1xml` files in the `$PSHOME` directory are added automatically to every session.</span></span>

<span data-ttu-id="a93e2-140">O `Types.ps1xml` arquivo no diretório de instalação do PowerShell ( `$PSHOME` ) é um arquivo de texto baseado em XML que permite adicionar propriedades e métodos aos objetos usados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-140">The `Types.ps1xml` file in the PowerShell installation directory (`$PSHOME`) is an XML-based text file that lets you add properties and methods to the objects that are used in PowerShell.</span></span> <span data-ttu-id="a93e2-141">O PowerShell tem arquivos internos `Types.ps1xml` que adicionam vários elementos aos tipos .net, mas você pode criar arquivos adicionais `Types.ps1xml` para estender ainda mais os tipos.</span><span class="sxs-lookup"><span data-stu-id="a93e2-141">PowerShell has built-in `Types.ps1xml` files that add several elements to the .NET types, but you can create additional `Types.ps1xml` files to further extend the types.</span></span>

<span data-ttu-id="a93e2-142">Por exemplo, por padrão, os objetos de matriz ( `System.Array` ) têm uma propriedade **Length** que lista o número de objetos na matriz.</span><span class="sxs-lookup"><span data-stu-id="a93e2-142">For example, by default, array objects (`System.Array`) have a **Length** property that lists the number of objects in the array.</span></span> <span data-ttu-id="a93e2-143">No entanto, como o **comprimento** do nome não descreve claramente a propriedade, o PowerShell adiciona uma propriedade de alias chamada **Count** que exibe o mesmo valor.</span><span class="sxs-lookup"><span data-stu-id="a93e2-143">However, because the name **Length** does not clearly describe the property, PowerShell adds an alias property named **Count** that displays the same value.</span></span> <span data-ttu-id="a93e2-144">O XML a seguir adiciona a propriedade **Count** ao `System.Array` tipo.</span><span class="sxs-lookup"><span data-stu-id="a93e2-144">The following XML adds the **Count** property to the `System.Array` type.</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>
        Length
      </ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

<span data-ttu-id="a93e2-145">Para obter o novo **AliasProperty** , use um `Get-Member` comando em qualquer matriz, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="a93e2-145">To get the new **AliasProperty** , use a `Get-Member` command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="a93e2-146">O comando retorna os seguintes resultados.</span><span class="sxs-lookup"><span data-stu-id="a93e2-146">The command returns the following results.</span></span>

```Output
Name       MemberType    Definition
----       ----------    ----------
Count      AliasProperty Count = Length
Address    Method        System.Object& Address(Int32)
Clone      Method        System.Object Clone()
CopyTo     Method        System.Void CopyTo(Array array, Int32 index):
Equals     Method        System.Boolean Equals(Object obj)
Get        Method        System.Object Get(Int32)
# ...
```

<span data-ttu-id="a93e2-147">Como resultado, você pode usar a propriedade **Count** ou a propriedade **Length** de matrizes no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-147">As a result, you can use either the **Count** property or the **Length** property of arrays in PowerShell.</span></span> <span data-ttu-id="a93e2-148">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a93e2-148">For example:</span></span>

```powershell
(1, 2, 3, 4).count
4
```

```powershell
(1, 2, 3, 4).length
4
```

## <a name="creating-new-typesps1xml-files"></a><span data-ttu-id="a93e2-149">Criando novos arquivos XML Types.ps1</span><span class="sxs-lookup"><span data-stu-id="a93e2-149">Creating new Types.ps1xml files</span></span>

<span data-ttu-id="a93e2-150">Os `.ps1xml` arquivos instalados com o PowerShell são assinados digitalmente para evitar a violação, pois a formatação pode incluir blocos de script.</span><span class="sxs-lookup"><span data-stu-id="a93e2-150">The `.ps1xml` files that are installed with PowerShell are digitally signed to prevent tampering because the formatting can include script blocks.</span></span> <span data-ttu-id="a93e2-151">Portanto, para adicionar uma propriedade ou um método a um tipo .NET, crie seus próprios `Types.ps1xml` arquivos e, em seguida, adicione-os à sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-151">Therefore, to add a property or method to a .NET type, create your own `Types.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="a93e2-152">Para criar um novo arquivo, comece copiando um `Types.ps1xml` arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="a93e2-152">To create a new file, start by copying an existing `Types.ps1xml` file.</span></span> <span data-ttu-id="a93e2-153">O novo arquivo pode ter qualquer nome, mas deve ter uma `.ps1xml` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="a93e2-153">The new file can have any name, but it must have a `.ps1xml` file name extension.</span></span> <span data-ttu-id="a93e2-154">Você pode posicionar o novo arquivo em qualquer diretório que esteja acessível ao PowerShell, mas é útil posicionar os arquivos no diretório de instalação do PowerShell ( `$PSHOME` ) ou em um subdiretório do diretório de instalação.</span><span class="sxs-lookup"><span data-stu-id="a93e2-154">You can place the new file in any directory that is accessible to PowerShell, but it is useful to place the files in the PowerShell installation directory (`$PSHOME`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="a93e2-155">Depois de salvar o novo arquivo, use o `Update-TypeData` cmdlet para adicionar o novo arquivo à sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-155">When you have saved the new file, use the `Update-TypeData` cmdlet to add the new file to your PowerShell session.</span></span> <span data-ttu-id="a93e2-156">Se você quiser que os tipos tenham precedência sobre os tipos internos definidos, use o parâmetro **PrependData** do `Update-TypeData` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a93e2-156">If you want your types to take precedence over the built-in types that are defined, use the **PrependData** parameter of the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="a93e2-157">`Update-TypeData` afeta apenas a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a93e2-157">`Update-TypeData` affects only the current session.</span></span> <span data-ttu-id="a93e2-158">Para fazer a alteração em todas as sessões futuras, exporte o console ou adicione o `Update-TypeData` comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-158">To make the change to all future sessions, export the console, or add the `Update-TypeData` command to your PowerShell profile.</span></span>

## <a name="typesps1xml-and-add-member"></a><span data-ttu-id="a93e2-159">Types.ps1XML e Add-Member</span><span class="sxs-lookup"><span data-stu-id="a93e2-159">Types.ps1xml and Add-Member</span></span>

<span data-ttu-id="a93e2-160">Os `Types.ps1xml` arquivos adicionam Propriedades e métodos a todas as instâncias dos objetos do tipo .net especificado na sessão do PowerShell afetada.</span><span class="sxs-lookup"><span data-stu-id="a93e2-160">The `Types.ps1xml` files add properties and methods to all the instances of the objects of the specified .NET type in the affected PowerShell session.</span></span> <span data-ttu-id="a93e2-161">No entanto, se você precisar adicionar propriedades ou métodos somente a uma instância de um objeto, use o `Add-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a93e2-161">However, if you need to add properties or methods only to one instance of an object, use the `Add-Member` cmdlet.</span></span>

<span data-ttu-id="a93e2-162">Para obter mais informações, consulte [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).</span><span class="sxs-lookup"><span data-stu-id="a93e2-162">For more information, see [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).</span></span>

## <a name="example-adding-an-age-member-to-fileinfo-objects"></a><span data-ttu-id="a93e2-163">Exemplo: adicionando um membro age a objetos FileInfo</span><span class="sxs-lookup"><span data-stu-id="a93e2-163">Example: Adding an Age member to FileInfo objects</span></span>

<span data-ttu-id="a93e2-164">Este exemplo mostra como adicionar uma propriedade **age** aos objetos **System. IO. FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="a93e2-164">This example shows how to add an **Age** property to **System.IO.FileInfo** objects.</span></span> <span data-ttu-id="a93e2-165">A idade de um arquivo é a diferença entre sua hora de criação e a hora atual em dias.</span><span class="sxs-lookup"><span data-stu-id="a93e2-165">The age of a file is the difference between its creation time and the current time in days.</span></span>

<span data-ttu-id="a93e2-166">Como a propriedade **age** é calculada usando um bloco de script, localize uma `<ScriptProperty>` marca a ser usada como modelo para a nova propriedade **age** .</span><span class="sxs-lookup"><span data-stu-id="a93e2-166">Because the **Age** property is calculated by using a script block, find a `<ScriptProperty>` tag to use as a model for the new **Age** property.</span></span>

<span data-ttu-id="a93e2-167">Salve o código XML a seguir no arquivo `$PSHOME\MyTypes.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="a93e2-167">Save the follow XML code to the file `$PSHOME\MyTypes.ps1xml`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Types>
  <Type>
    <Name>System.IO.FileInfo</Name>
    <Members>
      <ScriptProperty>
        <Name>Age</Name>
        <GetScriptBlock>
          ((Get-Date) - ($this.CreationTime)).Days
        </GetScriptBlock>
      </ScriptProperty>
    </Members>
  </Type>
</Types>
```

<span data-ttu-id="a93e2-168">Execute `Update-TypeData` para adicionar o novo `Types.ps1xml` arquivo à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a93e2-168">Run `Update-TypeData` to add the new `Types.ps1xml` file to the current session.</span></span> <span data-ttu-id="a93e2-169">O comando usa o parâmetro **PrependData** para posicionar o novo arquivo em uma ordem de precedência maior do que as definições originais.</span><span class="sxs-lookup"><span data-stu-id="a93e2-169">The command uses the **PrependData** parameter to place the new file in a precedence order higher than the original definitions.</span></span>

<span data-ttu-id="a93e2-170">Para obter mais informações sobre o `Update-TypeData` , consulte [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span><span class="sxs-lookup"><span data-stu-id="a93e2-170">For more information about `Update-TypeData`, see [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span></span>

```powershell
Update-Typedata -PrependPath $PSHOME\MyTypes.ps1xml
```

<span data-ttu-id="a93e2-171">Para testar a alteração, execute um `Get-ChildItem` comando para obter o arquivo de PowerShell.exe no `$PSHOME` diretório e, em seguida, direcione o arquivo para o `Format-List` cmdlet para listar todas as propriedades do arquivo.</span><span class="sxs-lookup"><span data-stu-id="a93e2-171">To test the change, run a `Get-ChildItem` command to get the PowerShell.exe file in the `$PSHOME` directory, and then pipe the file to the `Format-List` cmdlet to list all of the properties of the file.</span></span> <span data-ttu-id="a93e2-172">Como resultado da alteração, a propriedade **age** aparece na lista.</span><span class="sxs-lookup"><span data-stu-id="a93e2-172">As a result of the change, the **Age** property appears in the list.</span></span>

```powershell
Get-ChildItem $PSHOME\pwsh.exe | Select-Object Age
```

```Output
142
```

## <a name="the-xml-in-typesps1xml-files"></a><span data-ttu-id="a93e2-173">O XML em arquivos Types.ps1XML</span><span class="sxs-lookup"><span data-stu-id="a93e2-173">The XML in Types.ps1xml files</span></span>

<span data-ttu-id="a93e2-174">A definição de esquema completa pode ser encontrada em [Types. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) no repositório de código-fonte do PowerShell no github.</span><span class="sxs-lookup"><span data-stu-id="a93e2-174">The full schema definition can be found in [Types.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="a93e2-175">A `<Types>` marca inclui todos os tipos que estão definidos no arquivo.</span><span class="sxs-lookup"><span data-stu-id="a93e2-175">The `<Types>` tag encloses all of the types that are defined in the file.</span></span> <span data-ttu-id="a93e2-176">Deve haver apenas uma `<Types>` marca.</span><span class="sxs-lookup"><span data-stu-id="a93e2-176">There should be only one `<Types>` tag.</span></span>

<span data-ttu-id="a93e2-177">Cada tipo de .NET mencionado no arquivo deve ser representado por uma `<Type>` marca.</span><span class="sxs-lookup"><span data-stu-id="a93e2-177">Each .NET type mentioned in the file should be represented by a `<Type>` tag.</span></span>

<span data-ttu-id="a93e2-178">As marcas de tipo devem conter as seguintes marcas:</span><span class="sxs-lookup"><span data-stu-id="a93e2-178">The type tags must contain the following tags:</span></span>

<span data-ttu-id="a93e2-179">`<Name>`: Inclui o nome do tipo .NET afetado.</span><span class="sxs-lookup"><span data-stu-id="a93e2-179">`<Name>`: Encloses the name of the affected .NET type.</span></span>

<span data-ttu-id="a93e2-180">`<Members>`: Inclui as marcas para as novas propriedades e métodos que são definidos para o tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="a93e2-180">`<Members>`: Encloses the tags for the new properties and methods that are defined for the .NET type.</span></span>

<span data-ttu-id="a93e2-181">Qualquer uma das seguintes marcas de membro pode estar dentro da `<Members>` marca.</span><span class="sxs-lookup"><span data-stu-id="a93e2-181">Any of the following member tags can be inside the `<Members>` tag.</span></span>

<span data-ttu-id="a93e2-182">`<AliasProperty>`: Define um novo nome para uma propriedade existente.</span><span class="sxs-lookup"><span data-stu-id="a93e2-182">`<AliasProperty>`: Defines a new name for an existing property.</span></span>

<span data-ttu-id="a93e2-183">A `<AliasProperty>` marca deve ter uma `<Name>` marca que especifica o nome da nova propriedade e uma `<ReferencedMemberName>` marca que especifica a propriedade existente.</span><span class="sxs-lookup"><span data-stu-id="a93e2-183">The `<AliasProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<ReferencedMemberName>` tag that specifies the existing property.</span></span>

<span data-ttu-id="a93e2-184">Por exemplo, a propriedade de alias **Count** é um alias para a propriedade **Length** de objetos de matriz.</span><span class="sxs-lookup"><span data-stu-id="a93e2-184">For example, the **Count** alias property is an alias for the **Length** property of array objects.</span></span>

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

<span data-ttu-id="a93e2-185">`<CodeMethod>`: Faz referência a um método estático de uma classe .NET.</span><span class="sxs-lookup"><span data-stu-id="a93e2-185">`<CodeMethod>`:  References a static method of a .NET class.</span></span>

<span data-ttu-id="a93e2-186">A `<CodeMethod>` marca deve ter uma `<Name>` marca que especifica o nome do novo método e uma `<GetCodeReference>` marca que especifica o código no qual o método é definido.</span><span class="sxs-lookup"><span data-stu-id="a93e2-186">The `<CodeMethod>` tag must have a `<Name>` tag that specifies the name of the new method and a `<GetCodeReference>` tag that specifies the code in which the method is defined.</span></span>

<span data-ttu-id="a93e2-187">Por exemplo, a propriedade **Mode** de `System.IO.DirectoryInfo` objetos é uma propriedade de código definida no provedor de sistema de arquivos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-187">For example, the **Mode** property of `System.IO.DirectoryInfo` objects is a code property defined in the PowerShell FileSystem provider.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

<span data-ttu-id="a93e2-188">`<CodeProperty>`: Faz referência a um método estático de uma classe .NET.</span><span class="sxs-lookup"><span data-stu-id="a93e2-188">`<CodeProperty>`: References a static method of a .NET class.</span></span>

<span data-ttu-id="a93e2-189">A `<CodeProperty>` marca deve ter uma `<Name>` marca que especifica o nome da nova propriedade e uma `<GetCodeReference>` marca que especifica o código no qual a propriedade é definida.</span><span class="sxs-lookup"><span data-stu-id="a93e2-189">The `<CodeProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<GetCodeReference>` tag that specifies the code in which the property is defined.</span></span>

<span data-ttu-id="a93e2-190">Por exemplo, a propriedade **Mode** de `System.IO.DirectoryInfo` objetos é uma propriedade de código definida no provedor de sistema de arquivos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-190">For example, the **Mode** property of `System.IO.DirectoryInfo` objects is a code property defined in the PowerShell FileSystem provider.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

<span data-ttu-id="a93e2-191">`<MemberSet>`: Define uma coleção de Membros (Propriedades e métodos).</span><span class="sxs-lookup"><span data-stu-id="a93e2-191">`<MemberSet>`: Defines a collection of members (properties and methods).</span></span>

<span data-ttu-id="a93e2-192">As `<MemberSet>` marcas aparecem dentro das marcas primárias `<Members>` .</span><span class="sxs-lookup"><span data-stu-id="a93e2-192">The `<MemberSet>` tags appear within the primary `<Members>` tags.</span></span> <span data-ttu-id="a93e2-193">As marcas devem incluir uma `<Name>` marca ao redor do nome do conjunto de membros e uma `<Members>` marca secundária que envolve os membros (Propriedades e métodos) no conjunto.</span><span class="sxs-lookup"><span data-stu-id="a93e2-193">The tags must enclose a `<Name>` tag surrounding the name of the member set and a secondary `<Members>` tag that surround the members (properties and methods) in the set.</span></span> <span data-ttu-id="a93e2-194">Qualquer uma das marcas que criam uma propriedade (como `<NoteProperty>` ou `<ScriptProperty>` ) ou um método (como `<Method>` ou `<ScriptMethod>` ) pode ser membros do conjunto.</span><span class="sxs-lookup"><span data-stu-id="a93e2-194">Any of the tags that create a property (such as `<NoteProperty>` or `<ScriptProperty>`) or a method (such as `<Method>` or `<ScriptMethod>`) can be members of the set.</span></span>

<span data-ttu-id="a93e2-195">Em `Types.ps1xml` arquivos, a `<MemberSet>` marca é usada para definir as exibições padrão dos objetos .net no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-195">In `Types.ps1xml` files, the `<MemberSet>` tag is used to define the default views of the .NET objects in PowerShell.</span></span> <span data-ttu-id="a93e2-196">Nesse caso, o nome do conjunto de Membros (o valor dentro das `<Name>` marcas) é sempre **PSStandardMembers** e os nomes das propriedades (o valor da `<Name>` marca) são um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="a93e2-196">In this case, the name of the member set (the value within the `<Name>` tags) is always **PsStandardMembers** , and the names of the properties (the value of the `<Name>` tag) are one of the following:</span></span>

- <span data-ttu-id="a93e2-197">`DefaultDisplayProperty`: Uma única propriedade de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a93e2-197">`DefaultDisplayProperty`: A single property of an object.</span></span>

- <span data-ttu-id="a93e2-198">`DefaultDisplayPropertySet`: Uma ou mais propriedades de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a93e2-198">`DefaultDisplayPropertySet`: One or more properties of an object.</span></span>

- <span data-ttu-id="a93e2-199">`DefaultKeyPropertySet`: Uma ou mais propriedades de chave de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a93e2-199">`DefaultKeyPropertySet`: One or more key properties of an object.</span></span> <span data-ttu-id="a93e2-200">Uma propriedade de chave identifica instâncias de valores de propriedade, como o número de identificação de itens em um histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="a93e2-200">A key property identifies instances of property values, such as the ID number of items in a session history.</span></span>

<span data-ttu-id="a93e2-201">Por exemplo, o XML a seguir define a exibição padrão de serviços ( `System.ServiceProcess.ServiceController` objetos) que são retornados pelo `Get-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a93e2-201">For example, the following XML defines the default display of services (`System.ServiceProcess.ServiceController` objects) that are returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="a93e2-202">Ele define um conjunto de membros denominado **PSStandardMembers** que consiste em uma propriedade padrão definida com as propriedades **status** , **Name** e **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="a93e2-202">It defines a member set named **PsStandardMembers** that consists of a default property set with the **Status** , **Name** , and **DisplayName** properties.</span></span>

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
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

<span data-ttu-id="a93e2-203">`<Method>`: Faz referência a um método nativo do objeto subjacente.</span><span class="sxs-lookup"><span data-stu-id="a93e2-203">`<Method>`: References a native method of the underlying object.</span></span>

<span data-ttu-id="a93e2-204">`<Methods>`: Uma coleção de métodos do objeto.</span><span class="sxs-lookup"><span data-stu-id="a93e2-204">`<Methods>`: A collection of the methods of the object.</span></span>

<span data-ttu-id="a93e2-205">`<NoteProperty>`: Define uma propriedade com um valor estático.</span><span class="sxs-lookup"><span data-stu-id="a93e2-205">`<NoteProperty>`: Defines a property with a static value.</span></span>

<span data-ttu-id="a93e2-206">A `<NoteProperty>` marca deve ter uma `<Name>` marca que especifica o nome da nova propriedade e uma `<Value>` marca que especifica o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="a93e2-206">The `<NoteProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<Value>` tag that specifies the value of the property.</span></span>

<span data-ttu-id="a93e2-207">Por exemplo, o XML a seguir cria uma propriedade de **status** para objetos **System. IO. DirectoryInfo** .</span><span class="sxs-lookup"><span data-stu-id="a93e2-207">For example, the following XML creates a **Status** property for **System.IO.DirectoryInfo** objects.</span></span> <span data-ttu-id="a93e2-208">O valor da propriedade **status** é sempre **êxito** .</span><span class="sxs-lookup"><span data-stu-id="a93e2-208">The value of the **Status** property is always **Success** .</span></span>

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

<span data-ttu-id="a93e2-209">`<ParameterizedProperty>`: Propriedades que usam argumentos e retornam um valor.</span><span class="sxs-lookup"><span data-stu-id="a93e2-209">`<ParameterizedProperty>`: Properties that take arguments and return a value.</span></span>

<span data-ttu-id="a93e2-210">`<Properties>`: Uma coleção das propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="a93e2-210">`<Properties>`: A collection of the properties of the object.</span></span>

<span data-ttu-id="a93e2-211">`<Property>`: Uma propriedade do objeto base.</span><span class="sxs-lookup"><span data-stu-id="a93e2-211">`<Property>`: A property of the base object.</span></span>

<span data-ttu-id="a93e2-212">`<PropertySet>`: Define uma coleção de propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="a93e2-212">`<PropertySet>`: Defines a collection of properties of the object.</span></span>

<span data-ttu-id="a93e2-213">A `<PropertySet>` marca deve ter uma `<Name>` marca que especifica o nome do conjunto de propriedades e uma `<ReferencedProperty>` marca que especifica as propriedades.</span><span class="sxs-lookup"><span data-stu-id="a93e2-213">The `<PropertySet>` tag must have a `<Name>` tag that specifies the name of the property set and a `<ReferencedProperty>` tag that specifies the properties.</span></span> <span data-ttu-id="a93e2-214">Os nomes das propriedades são colocados na `<Name>` marca.</span><span class="sxs-lookup"><span data-stu-id="a93e2-214">The names of the properties are enclosed in `<Name>` tag.</span></span>

<span data-ttu-id="a93e2-215">No `Types.ps1xml` , as `<PropertySet>` marcas são usadas para definir conjuntos de propriedades para a exibição padrão de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a93e2-215">In `Types.ps1xml`, `<PropertySet>` tags are used to define sets of properties for the default display of an object.</span></span> <span data-ttu-id="a93e2-216">Você pode identificar as exibições padrão pelo valor **PSStandardMembers** na `<Name>` marca de uma `<MemberSet>` marca.</span><span class="sxs-lookup"><span data-stu-id="a93e2-216">You can identify the default displays by the value **PsStandardMembers** in the `<Name>` tag of a `<MemberSet>` tag.</span></span>

<span data-ttu-id="a93e2-217">Por exemplo, o XML a seguir cria uma propriedade de **status** para o `System.IO.DirectoryInfo` objeto.</span><span class="sxs-lookup"><span data-stu-id="a93e2-217">For example, the following XML creates a **Status** property for the `System.IO.DirectoryInfo` object.</span></span> <span data-ttu-id="a93e2-218">O valor da propriedade **status** é sempre **êxito** .</span><span class="sxs-lookup"><span data-stu-id="a93e2-218">The value of the **Status** property is always **Success** .</span></span>

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
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

<span data-ttu-id="a93e2-219">`<ScriptMethod>`: Define um método cujo valor é a saída de um script.</span><span class="sxs-lookup"><span data-stu-id="a93e2-219">`<ScriptMethod>`: Defines a method whose value is the output of a script.</span></span>

<span data-ttu-id="a93e2-220">A `<ScriptMethod>` marca deve ter uma `<Name>` marca que especifica o nome do novo método e uma `<Script>` marca que inclui o bloco de script que retorna o resultado do método.</span><span class="sxs-lookup"><span data-stu-id="a93e2-220">The `<ScriptMethod>` tag must have a `<Name>` tag that specifies the name of the new method and a `<Script>` tag that encloses the script block that returns the method result.</span></span>

<span data-ttu-id="a93e2-221">Por exemplo, os `ConvertToDateTime` `ConvertFromDateTime` métodos e dos objetos de gerenciamento ( `System.System.Management.ManagementObject` ) são métodos de script que usam os `ToDateTime` `ToDmtfDateTime` métodos estáticos e da `System.Management.ManagementDateTimeConverter` classe.</span><span class="sxs-lookup"><span data-stu-id="a93e2-221">For example, the `ConvertToDateTime` and `ConvertFromDateTime` methods of management objects (`System.System.Management.ManagementObject`) are script methods that use the `ToDateTime` and `ToDmtfDateTime` static methods of the `System.Management.ManagementDateTimeConverter` class.</span></span>

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
 <ScriptMethod>
   <Name>ConvertFromDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDmtfDateTime($args[0])
   </Script>
 </ScriptMethod>
 </Members>
</Type>
```

<span data-ttu-id="a93e2-222">`<ScriptProperty>`: Define uma propriedade cujo valor é a saída de um script.</span><span class="sxs-lookup"><span data-stu-id="a93e2-222">`<ScriptProperty>`: Defines a property whose value is the output of a script.</span></span>

<span data-ttu-id="a93e2-223">A `<ScriptProperty>` marca deve ter uma `<Name>` marca que especifica o nome da nova propriedade e uma `<GetScriptBlock>` marca que inclui o bloco de script que retorna o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="a93e2-223">The `<ScriptProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<GetScriptBlock>` tag that encloses the script block that returns the property value.</span></span>

<span data-ttu-id="a93e2-224">Por exemplo, a propriedade **VERSIONINFO** do objeto **System. IO. FileInfo** é uma propriedade de script resultante do uso da propriedade **FullName** do método estático **GetVersionInfo** de objetos **System. Diagnostics. FileVersionInfo** .</span><span class="sxs-lookup"><span data-stu-id="a93e2-224">For example, the **VersionInfo** property of the **System.IO.FileInfo** object is a script property that results from using the **FullName** property of the **GetVersionInfo** static method of **System.Diagnostics.FileVersionInfo** objects.</span></span>

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

<span data-ttu-id="a93e2-225">Para obter mais informações, consulte o [SDK (Software Development Kit) do Windows PowerShell](/powershell/scripting/developer/windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="a93e2-225">For more information, see the [Windows PowerShell Software Development Kit (SDK)](/powershell/scripting/developer/windows-powershell).</span></span>

## <a name="update-typedata"></a><span data-ttu-id="a93e2-226">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="a93e2-226">Update-TypeData</span></span>

<span data-ttu-id="a93e2-227">Para carregar os `Types.ps1xml` arquivos em uma sessão do PowerShell, execute o `Update-TypeData` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a93e2-227">To load your `Types.ps1xml` files into a PowerShell session, run the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="a93e2-228">Se você quiser que os tipos em seu arquivo tenham precedência sobre os tipos no arquivo interno `Types.ps1xml` , adicione o parâmetro **PrependData** de `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="a93e2-228">If you want the types in your file to take precedence over types in the built-in `Types.ps1xml` file, add the **PrependData** parameter of `Update-TypeData`.</span></span> <span data-ttu-id="a93e2-229">`Update-TypeData` afeta apenas a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a93e2-229">`Update-TypeData` affects only the current session.</span></span> <span data-ttu-id="a93e2-230">Para fazer a alteração em todas as sessões futuras, exporte a sessão ou adicione o `Update-TypeData` comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a93e2-230">To make the change to all future sessions, export the session, or add the `Update-TypeData` command to your PowerShell profile.</span></span>

<span data-ttu-id="a93e2-231">Exceções que ocorrem em Propriedades ou adicionando Propriedades a um `Update-TypeData` comando, não Relate erros ao `StdErr` .</span><span class="sxs-lookup"><span data-stu-id="a93e2-231">Exceptions that occur in properties, or from adding properties to an `Update-TypeData` command, do not report errors to `StdErr`.</span></span> <span data-ttu-id="a93e2-232">Isso é para suprimir exceções que podem ocorrer em muitos tipos comuns durante a formatação e a saída.</span><span class="sxs-lookup"><span data-stu-id="a93e2-232">This is to suppress exceptions that would occur in many common types during formatting and outputting.</span></span> <span data-ttu-id="a93e2-233">Se você estiver obtendo propriedades do .NET, poderá contornar a supressão de exceções usando a sintaxe do método, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="a93e2-233">If you are getting .NET properties, you can work around the suppression of exceptions by using method syntax instead, as shown in the following example:</span></span>

```powershell
"hello".get_Length()
```

<span data-ttu-id="a93e2-234">Observe que a sintaxe do método só pode ser usada com as propriedades do .NET.</span><span class="sxs-lookup"><span data-stu-id="a93e2-234">Note that method syntax can only be used with .NET properties.</span></span> <span data-ttu-id="a93e2-235">As propriedades que são adicionadas executando o `Update-TypeData` cmdlet não podem usar a sintaxe do método.</span><span class="sxs-lookup"><span data-stu-id="a93e2-235">Properties that are added by running the `Update-TypeData` cmdlet cannot use method syntax.</span></span>

## <a name="signing-a-typesps1xml-file"></a><span data-ttu-id="a93e2-236">Assinando um arquivo XML Types.ps1</span><span class="sxs-lookup"><span data-stu-id="a93e2-236">Signing a Types.ps1xml file</span></span>

<span data-ttu-id="a93e2-237">Para proteger os usuários de seu `Types.ps1xml` arquivo, você pode assinar o arquivo usando uma assinatura digital.</span><span class="sxs-lookup"><span data-stu-id="a93e2-237">To protect users of your `Types.ps1xml` file, you can sign the file using a digital signature.</span></span> <span data-ttu-id="a93e2-238">Para obter mais informações, consulte [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="a93e2-238">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a93e2-239">Confira também</span><span class="sxs-lookup"><span data-stu-id="a93e2-239">See also</span></span>

[<span data-ttu-id="a93e2-240">about_Signing</span><span class="sxs-lookup"><span data-stu-id="a93e2-240">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="a93e2-241">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="a93e2-241">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)

[<span data-ttu-id="a93e2-242">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a93e2-242">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

[<span data-ttu-id="a93e2-243">Get-Member</span><span class="sxs-lookup"><span data-stu-id="a93e2-243">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

[<span data-ttu-id="a93e2-244">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="a93e2-244">Get-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Get-TypeData)

[<span data-ttu-id="a93e2-245">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="a93e2-245">Remove-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Remove-TypeData)

[<span data-ttu-id="a93e2-246">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="a93e2-246">Update-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Update-TypeData)
