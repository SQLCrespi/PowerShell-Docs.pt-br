---
description: Explica como criar objetos no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_object_creation?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Object_Creation
ms.openlocfilehash: 885218848081aae364e662c3060500af3f5759ab
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195579"
---
# <a name="about-object-creation"></a><span data-ttu-id="aa7aa-104">Sobre a criação de objeto</span><span class="sxs-lookup"><span data-stu-id="aa7aa-104">About Object Creation</span></span>

## <a name="short-description"></a><span data-ttu-id="aa7aa-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="aa7aa-105">Short description</span></span>

<span data-ttu-id="aa7aa-106">Explica como criar objetos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-106">Explains how to create objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="aa7aa-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="aa7aa-107">Long description</span></span>

<span data-ttu-id="aa7aa-108">Você pode criar objetos no PowerShell e usar os objetos que você cria em comandos e scripts.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-108">You can create objects in PowerShell and use the objects that you create in commands and scripts.</span></span>

<span data-ttu-id="aa7aa-109">Há várias maneiras de criar objetos, essa lista não é definitiva:</span><span class="sxs-lookup"><span data-stu-id="aa7aa-109">There are many ways to create objects, this list is not definitive:</span></span>

- <span data-ttu-id="aa7aa-110">[New-Object](xref:Microsoft.PowerShell.Utility.New-Object): cria uma instância de um objeto de .NET Framework ou objeto com.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-110">[New-Object](xref:Microsoft.PowerShell.Utility.New-Object): Creates an instance of a .NET Framework object or COM object.</span></span>
- <span data-ttu-id="aa7aa-111">[Importar-CSV](xref:Microsoft.PowerShell.Utility.Import-Csv) /
   [ConvertFrom-CSV](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): cria objetos personalizados ( **PSCustomObject** ) a partir dos itens definidos como valores separados por vírgula.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-111">[Import-Csv](xref:Microsoft.PowerShell.Utility.Import-Csv)/
  [ConvertFrom-CSV](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): Creates custom objects ( **PSCustomObject** ) from the items defined as comma separated values.</span></span>
- <span data-ttu-id="aa7aa-112">[ConvertFrom-JSON](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): cria objetos personalizados definidos em JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="aa7aa-112">[ConvertFrom-Json](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): Creates custom objects defined in JavaScript Object Notation (JSON).</span></span>
- <span data-ttu-id="aa7aa-113">[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): cria objetos personalizados definidos como pares chave-valor.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-113">[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): Creates custom objects defined as key value pairs.</span></span>
- <span data-ttu-id="aa7aa-114">[Adicionar tipo](xref:Microsoft.PowerShell.Utility.Add-Type): permite que você defina uma classe em sua sessão do PowerShell com a qual você pode criar uma instância `New-Object` .</span><span class="sxs-lookup"><span data-stu-id="aa7aa-114">[Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type): Allows you to define a class in your PowerShell session that you can instantiate with `New-Object`.</span></span>
- <span data-ttu-id="aa7aa-115">[New-Module](xref:Microsoft.PowerShell.Core.New-Module): o parâmetro **AsCustomObject** cria um objeto personalizado que você define usando o bloco de script.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-115">[New-Module](xref:Microsoft.PowerShell.Core.New-Module): The **AsCustomObject** parameter creates a custom object you define using script block.</span></span>
- <span data-ttu-id="aa7aa-116">[Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member): Adiciona propriedades a objetos existentes.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-116">[Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member): Adds properties to existing objects.</span></span> <span data-ttu-id="aa7aa-117">Você pode usar `Add-Member` para criar um objeto personalizado a partir de um tipo simples, como `[System.Int32]` .</span><span class="sxs-lookup"><span data-stu-id="aa7aa-117">You can use `Add-Member` to create a custom object out of a simple type, like `[System.Int32]`.</span></span>
- <span data-ttu-id="aa7aa-118">[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object): seleciona as propriedades em um objeto.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-118">[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object): Selects properties on an object.</span></span> <span data-ttu-id="aa7aa-119">Você pode usar `Select-Object` para criar propriedades personalizadas e calculadas em um objeto já instanciado.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-119">You can use `Select-Object` to create custom and calculated properties on an already instantiated object.</span></span>

<span data-ttu-id="aa7aa-120">Os seguintes métodos adicionais são abordados neste artigo:</span><span class="sxs-lookup"><span data-stu-id="aa7aa-120">The following additional methods are covered in this article:</span></span>

- <span data-ttu-id="aa7aa-121">Chamando o construtor de um tipo usando um `new()` método estático</span><span class="sxs-lookup"><span data-stu-id="aa7aa-121">By calling a type's constructor using a static `new()` method</span></span>
- <span data-ttu-id="aa7aa-122">Por tabelas de hash typecasting de nomes de propriedade e valores de propriedade</span><span class="sxs-lookup"><span data-stu-id="aa7aa-122">By typecasting hash tables of property names and property values</span></span>

## <a name="static-new-method"></a><span data-ttu-id="aa7aa-123">Método New () estático</span><span class="sxs-lookup"><span data-stu-id="aa7aa-123">Static new() method</span></span>

<span data-ttu-id="aa7aa-124">Todos os tipos .NET têm um `new()` método que permite construir instâncias mais facilmente.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-124">All .NET types have a `new()` method that allows you to construct instances more easily.</span></span> <span data-ttu-id="aa7aa-125">Você também pode ver todos os construtores disponíveis para um determinado tipo.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-125">You can also see all the available constructors for a given type.</span></span>

<span data-ttu-id="aa7aa-126">Para ver os construtores de um tipo, especifique o `new` nome do método após o nome do tipo e pressione `<ENTER>` .</span><span class="sxs-lookup"><span data-stu-id="aa7aa-126">To see the constructors for a type, specify the `new` method name after the type name and press `<ENTER>`.</span></span>

```powershell
[System.Uri]::new
```

```Output
OverloadDefinitions
-------------------
uri new(string uriString)
uri new(string uriString, bool dontEscape)
uri new(uri baseUri, string relativeUri, bool dontEscape)
uri new(string uriString, System.UriKind uriKind)
uri new(uri baseUri, string relativeUri)
uri new(uri baseUri, uri relativeUri)
```

<span data-ttu-id="aa7aa-127">Agora, você pode criar um **System. URI** especificando o construtor apropriado.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-127">Now, you can create a **System.Uri** by specifying the appropriate constructor.</span></span>

```powershell
[System.Uri]::new("https://www.bing.com")
```

```Output
AbsolutePath   : /
AbsoluteUri    : https://www.bing.com/
LocalPath      : /
Authority      : www.bing.com
...
```

<span data-ttu-id="aa7aa-128">Você pode usar o exemplo a seguir para determinar quais tipos .NET estão atualmente carregados para instanciar.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-128">You can use the following sample to determine what .NET types are currently loaded for you to instantiate.</span></span>

```powershell
[AppDomain]::CurrentDomain.GetAssemblies() |
  ForEach-Object {
    $_.GetExportedTypes() |
      ForEach-Object { $_.FullName }
  }
```

<span data-ttu-id="aa7aa-129">Objetos criados usando o `new()` método podem não ter as mesmas propriedades que objetos do mesmo tipo que são criados por cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-129">Objects created using the `new()` method may not have the same properties as objects of the same type that are created by PowerShell cmdlets.</span></span> <span data-ttu-id="aa7aa-130">Os cmdlets, provedores e o sistema de tipos estendidos do PowerShell podem adicionar propriedades extras à instância.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-130">PowerShell cmdlets, providers, and Extended Type System can add extra properties to the instance.</span></span>

<span data-ttu-id="aa7aa-131">Por exemplo, o provedor FileSystem no PowerShell adiciona seis valores **NoteProperty** ao objeto **DirectoryInfo** retornado por `Get-Item` .</span><span class="sxs-lookup"><span data-stu-id="aa7aa-131">For example, the FileSystem provider in PowerShell adds six **NoteProperty** values to the **DirectoryInfo** object returned by `Get-Item`.</span></span>

```powershell
$PSDirInfo = Get-Item /
$PSDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    6 NoteProperty
    1 ScriptProperty
   18 Method
```

<span data-ttu-id="aa7aa-132">Quando você cria um objeto **DirectoryInfo** diretamente, ele não tem esses seis valores de **notaproperty** .</span><span class="sxs-lookup"><span data-stu-id="aa7aa-132">When you create a **DirectoryInfo** object directly, it does not have those six **NoteProperty** values.</span></span>

```powershell
$NewDirInfo = [System.IO.DirectoryInfo]::new('/')
$NewDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    1 ScriptProperty
   18 Method
```

<span data-ttu-id="aa7aa-133">Para obter mais informações sobre o sistema de tipo estendido, consulte [about_Types.ps1XML](about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="aa7aa-133">For more information about the Extended Type System, see [about_Types.ps1xml](about_Types.ps1xml.md).</span></span>

<span data-ttu-id="aa7aa-134">Esse recurso foi adicionado no PowerShell 5,0</span><span class="sxs-lookup"><span data-stu-id="aa7aa-134">This feature was added in PowerShell 5.0</span></span>

## <a name="create-objects-from-hash-tables"></a><span data-ttu-id="aa7aa-135">Criar objetos a partir de tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="aa7aa-135">Create objects from hash tables</span></span>

<span data-ttu-id="aa7aa-136">Você pode criar um objeto de uma tabela de hash de propriedades e valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-136">You can create an object from a hash table of properties and property values.</span></span>

<span data-ttu-id="aa7aa-137">A sintaxe dela é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="aa7aa-137">The syntax is as follows:</span></span>

```
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

<span data-ttu-id="aa7aa-138">Esse método funciona somente para classes que têm um construtor sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-138">This method works only for classes that have a parameterless constructor.</span></span> <span data-ttu-id="aa7aa-139">As propriedades do objeto devem ser públicas e configurável.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-139">The object properties must be public and settable.</span></span>

<span data-ttu-id="aa7aa-140">Esse recurso foi adicionado no PowerShell versão 3,0</span><span class="sxs-lookup"><span data-stu-id="aa7aa-140">This feature was added in PowerShell version 3.0</span></span>

## <a name="create-custom-objects-from-hash-tables"></a><span data-ttu-id="aa7aa-141">Criar objetos personalizados a partir de tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="aa7aa-141">Create custom objects from hash tables</span></span>

<span data-ttu-id="aa7aa-142">Os objetos personalizados são muito úteis e são fáceis de criar usando o método de tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-142">Custom objects are very useful and are easy to create using the hash table method.</span></span> <span data-ttu-id="aa7aa-143">A classe **PSCustomObject** foi projetada especificamente para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-143">The **PSCustomObject** class is designed specifically for this purpose.</span></span>

<span data-ttu-id="aa7aa-144">Os objetos personalizados são uma excelente maneira de retornar a saída personalizada de uma função ou script.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-144">Custom objects are an excellent way to return customized output from a function or script.</span></span> <span data-ttu-id="aa7aa-145">Isso é mais útil do que retornar a saída formatada que não pode ser reformatada ou canalizada para outros comandos.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-145">This is more useful than returning formatted output that cannot be reformatted or piped to other commands.</span></span>

<span data-ttu-id="aa7aa-146">Os comandos no `Test-Object function` definem alguns valores de variáveis e, em seguida, usam esses valores para criar um objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-146">The commands in the `Test-Object function` set some variable values and then use those values to create a custom object.</span></span> <span data-ttu-id="aa7aa-147">Você pode ver esse objeto em uso na seção de exemplo do `Update-Help` tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-147">You can see this object in use in the example section of the `Update-Help` cmdlet help topic.</span></span>

```powershell
function Test-Object {
  $ModuleName = "PSScheduledJob"
  $HelpCulture = "en-us"
  $HelpVersion = "3.1.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
  $ModuleName = "PSWorkflow"
  $HelpCulture = "en-us"
  $HelpVersion = "3.0.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
}
Test-Object
```

<span data-ttu-id="aa7aa-148">A saída dessa função é uma coleção de objetos personalizados formatados como uma tabela por padrão.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-148">The output of this function is a collection of custom objects formatted as a table by default.</span></span>

```Output
ModuleName        UICulture      Version
---------         ---------      -------
PSScheduledJob    en-us          3.1.0.0
PSWorkflow        en-us          3.0.0.0
```

<span data-ttu-id="aa7aa-149">Os usuários podem gerenciar as propriedades dos objetos personalizados da mesma forma como fazem com objetos padrão.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-149">Users can manage the properties of the custom objects just as they do with standard objects.</span></span>

```powershell
(Test-Object).ModuleName
```

```Output
 PSScheduledJob
 PSWorkflow
```

## <a name="create-non-custom-objects-from-hash-tables"></a><span data-ttu-id="aa7aa-150">Criar objetos não personalizados a partir de tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="aa7aa-150">Create non-custom objects from hash tables</span></span>

<span data-ttu-id="aa7aa-151">Você também pode usar tabelas de hash para criar objetos para classes não personalizadas.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-151">You can also use hash tables to create objects for non-custom classes.</span></span> <span data-ttu-id="aa7aa-152">Quando você cria um objeto para uma classe não personalizada, o nome do tipo qualificado para namespace é necessário, embora você possa omitir qualquer componente de namespace de **sistema** inicial.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-152">When you create an object for a non-custom class, the namespace-qualified type name is required, although you may omit any initial **System** namespace component.</span></span>

<span data-ttu-id="aa7aa-153">Por exemplo, o comando a seguir cria um objeto de opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-153">For example, the following command creates a session option object.</span></span>

```powershell
[System.Management.Automation.Remoting.PSSessionOption]@{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
```

<span data-ttu-id="aa7aa-154">Os requisitos do recurso de tabela de hash, especialmente o requisito de construtor sem parâmetros, eliminam muitas classes existentes.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-154">The requirements of the hash table feature, especially the parameterless constructor requirement, eliminate many existing classes.</span></span> <span data-ttu-id="aa7aa-155">No entanto, a maioria das classes de _opção_ do PowerShell é projetada para trabalhar com esse recurso, bem como outras classes muito úteis, como a classe **ProcessStartInfo** .</span><span class="sxs-lookup"><span data-stu-id="aa7aa-155">However, most PowerShell _option_ classes are designed to work with this feature, as well as other very useful classes, such as the **ProcessStartInfo** class.</span></span>

```powershell
[System.Diagnostics.ProcessStartInfo]@{
  CreateNoWindow="$true"
  Verb="run as"
}
```

```Output
Arguments               :
ArgumentList            : {}
CreateNoWindow          : True
EnvironmentVariables    : {OneDriveConsumer, PROCESSOR_ARCHITECTURE,
                           CommonProgramFiles(x86), APPDATA...}
Environment             : {[OneDriveConsumer, C:\Users\user1\OneDrive],
                           [PROCESSOR_ARCHITECTURE, AMD64],
                           [CommonProgramFiles(x86),
                           C:\Program Files (x86)\Common Files],
                           [APPDATA, C:\Users\user1\AppData\Roaming]...}
RedirectStandardInput   : False
RedirectStandardOutput  : False
RedirectStandardError   : False
...
```

<span data-ttu-id="aa7aa-156">Você também pode usar o recurso de tabela de hash ao definir valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-156">You can also use the hash table feature when setting parameter values.</span></span> <span data-ttu-id="aa7aa-157">Por exemplo, o valor do parâmetro **SessionOption** do `New-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="aa7aa-157">For example, the value of the **SessionOption** parameter of the `New-PSSession`.</span></span>
<span data-ttu-id="aa7aa-158">o cmdlet pode ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-158">cmdlet can be a hash table.</span></span>

```powershell
New-PSSession -ComputerName Server01 -SessionOption @{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
Register-ScheduledJob Name Test -FilePath .\Get-Inventory.ps1 -Trigger @{
  Frequency="Daily"
  At="15:00"
}
```

## <a name="generic-objects"></a><span data-ttu-id="aa7aa-159">Objetos genéricos</span><span class="sxs-lookup"><span data-stu-id="aa7aa-159">Generic objects</span></span>

<span data-ttu-id="aa7aa-160">Você também pode criar objetos genéricos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-160">You can also create generic objects in PowerShell.</span></span> <span data-ttu-id="aa7aa-161">Genéricos são classes, estruturas, interfaces e métodos que possuem espaços reservados (parâmetros de tipo) para um ou mais dos tipos que eles armazenam ou usam.</span><span class="sxs-lookup"><span data-stu-id="aa7aa-161">Generics are classes, structures, interfaces, and methods that have placeholders (type parameters) for one or more of the types that they store or use.</span></span>

<span data-ttu-id="aa7aa-162">O exemplo a seguir cria um objeto **Dictionary** .</span><span class="sxs-lookup"><span data-stu-id="aa7aa-162">The following example creates a **Dictionary** object.</span></span>

```powershell
$dict = New-Object 'System.Collections.Generic.Dictionary[String,Int]'
$dict.Add("One", 1)
$dict
```

```Output
Key Value
--- -----
One     1
```

<span data-ttu-id="aa7aa-163">Para obter mais informações sobre os genéricos, consulte [genéricos no .net](/dotnet/standard/generics).</span><span class="sxs-lookup"><span data-stu-id="aa7aa-163">For more information on Generics, see [Generics in .NET](/dotnet/standard/generics).</span></span>

## <a name="see-also"></a><span data-ttu-id="aa7aa-164">Confira também</span><span class="sxs-lookup"><span data-stu-id="aa7aa-164">See also</span></span>

[<span data-ttu-id="aa7aa-165">about_Objects</span><span class="sxs-lookup"><span data-stu-id="aa7aa-165">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="aa7aa-166">about_Methods</span><span class="sxs-lookup"><span data-stu-id="aa7aa-166">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="aa7aa-167">about_Properties</span><span class="sxs-lookup"><span data-stu-id="aa7aa-167">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="aa7aa-168">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="aa7aa-168">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="aa7aa-169">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="aa7aa-169">about_Types.ps1xml</span></span>](about_Types.ps1xml.md)
