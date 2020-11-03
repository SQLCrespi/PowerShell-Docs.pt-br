---
description: Descreve como usar propriedades de objeto no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Properties
ms.openlocfilehash: d4d3cd93e6b177e80d85315f125c647219fc4a45
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196343"
---
# <a name="about-properties"></a><span data-ttu-id="0ed0a-104">Sobre propriedades</span><span class="sxs-lookup"><span data-stu-id="0ed0a-104">About Properties</span></span>

## <a name="short-description"></a><span data-ttu-id="0ed0a-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="0ed0a-105">Short description</span></span>
<span data-ttu-id="0ed0a-106">Descreve como usar propriedades de objeto no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-106">Describes how to use object properties in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="0ed0a-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="0ed0a-107">Long description</span></span>

<span data-ttu-id="0ed0a-108">O PowerShell usa coleções estruturadas de informações chamadas de objetos para representar os itens em armazenamentos de dados ou o estado do computador.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-108">PowerShell uses structured collections of information called objects to represent the items in data stores or the state of the computer.</span></span> <span data-ttu-id="0ed0a-109">Normalmente, você trabalha com objetos que fazem parte do Microsoft .NET Framework, mas também pode criar objetos personalizados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-109">Typically, you work with object that are part of the Microsoft .NET Framework, but you can also create custom objects in PowerShell.</span></span>

<span data-ttu-id="0ed0a-110">A associação entre um item e seu objeto é muito próxima.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-110">The association between an item and its object is very close.</span></span> <span data-ttu-id="0ed0a-111">Ao alterar um objeto, você geralmente altera o item que ele representa.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-111">When you change an object, you usually change the item that it represents.</span></span> <span data-ttu-id="0ed0a-112">Por exemplo, quando você recebe um arquivo no PowerShell, não obtém o arquivo real.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-112">For example, when you get a file in PowerShell, you do not get the actual file.</span></span> <span data-ttu-id="0ed0a-113">Em vez disso, você recebe um objeto FileInfo que representa o arquivo.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-113">Instead, you get a FileInfo object that represents the file.</span></span> <span data-ttu-id="0ed0a-114">Quando você altera o objeto FileInfo, o arquivo também é alterado.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-114">When you change the FileInfo object, the file changes too.</span></span>

<span data-ttu-id="0ed0a-115">A maioria dos objetos tem propriedades.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-115">Most objects have properties.</span></span> <span data-ttu-id="0ed0a-116">Propriedades são os dados associados a um objeto.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-116">Properties are the data that is associated with an object.</span></span> <span data-ttu-id="0ed0a-117">Tipos diferentes de objeto têm propriedades diferentes.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-117">Different types of object have different properties.</span></span> <span data-ttu-id="0ed0a-118">Por exemplo, um objeto FileInfo, que representa um arquivo, tem uma propriedade **IsReadOnly** que contém $true se o arquivo for o atributo somente leitura e $false se não tiver.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-118">For example, a FileInfo object, which represents a file, has an **IsReadOnly** property that contains $True if the file the read-only attribute and $False if it does not.</span></span>
<span data-ttu-id="0ed0a-119">Um objeto DirectoryInfo, que representa um diretório do sistema de arquivos, tem uma propriedade Parent que contém o caminho até o diretório pai.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-119">A DirectoryInfo object, which represents a file system directory, has a Parent property that contains the path to the parent directory.</span></span>

### <a name="object-properties"></a><span data-ttu-id="0ed0a-120">Propriedades do objeto</span><span class="sxs-lookup"><span data-stu-id="0ed0a-120">Object properties</span></span>

<span data-ttu-id="0ed0a-121">Para obter as propriedades de um objeto, use o `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-121">To get the properties of an object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="0ed0a-122">Por exemplo, para obter as propriedades de um objeto **FileInfo** , use o `Get-ChildItem` cmdlet para obter o objeto FileInfo que representa um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-122">For example, to get the properties of a **FileInfo** object, use the `Get-ChildItem` cmdlet to get the FileInfo object that represents a file.</span></span> <span data-ttu-id="0ed0a-123">Em seguida, use um operador de pipeline (&#124;) para o qual enviar o objeto **FileInfo** `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="0ed0a-123">Then, use a pipeline operator (&#124;) to send the **FileInfo** object to `Get-Member`.</span></span> <span data-ttu-id="0ed0a-124">O comando a seguir obtém o arquivo PowerShell.exe e o envia para o `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="0ed0a-124">The following command gets the PowerShell.exe file and sends it to `Get-Member`.</span></span>
<span data-ttu-id="0ed0a-125">A \$ variável automática pshome contém o caminho do diretório de instalação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-125">The \$Pshome automatic variable contains the path of the PowerShell installation directory.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member
```

<span data-ttu-id="0ed0a-126">A saída do comando lista os membros do objeto **FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="0ed0a-126">The output of the command lists the members of the **FileInfo** object.</span></span>
<span data-ttu-id="0ed0a-127">Os membros incluem propriedades e métodos.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-127">Members include both properties and methods.</span></span> <span data-ttu-id="0ed0a-128">Quando você trabalha no PowerShell, tem acesso a todos os membros dos objetos.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-128">When you work in PowerShell, you have access to all the members of the objects.</span></span>

<span data-ttu-id="0ed0a-129">Para obter apenas as propriedades de um objeto e não os métodos, use o parâmetro MemberType do `Get-Member` cmdlet com um valor de "Property", conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-129">To get only the properties of an object and not the methods, use the MemberType parameter of the `Get-Member` cmdlet with a value of "property", as shown in the following example.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member -MemberType property
```

```Output
TypeName: System.IO.FileInfo

Name              MemberType Definition
----              ---------- ----------
Attributes        Property   System.IO.FileAttributes Attributes {get;set;}
CreationTime      Property   System.DateTime CreationTime {get;set;}
CreationTimeUtc   Property   System.DateTime CreationTimeUtc {get;set;}
Directory         Property   System.IO.DirectoryInfo Directory {get;}
DirectoryName     Property   System.String DirectoryName {get;}
Exists            Property   System.Boolean Exists {get;}
Extension         Property   System.String Extension {get;}
FullName          Property   System.String FullName {get;}
IsReadOnly        Property   System.Boolean IsReadOnly {get;set;}
LastAccessTime    Property   System.DateTime LastAccessTime {get;set;}
LastAccessTimeUtc Property   System.DateTime LastAccessTimeUtc {get;set;}
LastWriteTime     Property   System.DateTime LastWriteTime {get;set;}
LastWriteTimeUtc  Property   System.DateTime LastWriteTimeUtc {get;set;}
Length            Property   System.Int64 Length {get;}
Name              Property   System.String Name {get;}
```

<span data-ttu-id="0ed0a-130">Depois de localizar as propriedades, você pode usá-las em seus comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-130">After you find the properties, you can use them in your PowerShell commands.</span></span>

## <a name="property-values"></a><span data-ttu-id="0ed0a-131">Valores de propriedade</span><span class="sxs-lookup"><span data-stu-id="0ed0a-131">Property values</span></span>

<span data-ttu-id="0ed0a-132">Embora todo objeto de um tipo específico tenha as mesmas propriedades, os valores dessas propriedades descrevem o objeto específico.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-132">Although every object of a specific type has the same properties, the values of those properties describe the particular object.</span></span> <span data-ttu-id="0ed0a-133">Por exemplo, cada objeto FileInfo tem uma propriedade CreationTime, mas o valor dessa propriedade é diferente para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-133">For example, every FileInfo object has a CreationTime property, but the value of that property differs for each file.</span></span>

<span data-ttu-id="0ed0a-134">A maneira mais comum para obter os valores das propriedades de um objeto é usar o método de ponto.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-134">The most common way to get the values of the properties of an object is to use the dot method.</span></span> <span data-ttu-id="0ed0a-135">Digite uma referência ao objeto, como uma variável que contém o objeto, ou um comando que obtém o objeto.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-135">Type a reference to the object, such as a variable that contains the object, or a command that gets the object.</span></span> <span data-ttu-id="0ed0a-136">Em seguida, digite um ponto (.) seguido pelo nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-136">Then, type a dot (.) followed by the property name.</span></span>

<span data-ttu-id="0ed0a-137">Por exemplo, o comando a seguir exibe o valor da propriedade CreationTime do arquivo PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-137">For example, the following command displays the value of the CreationTime property of the PowerShell.exe file.</span></span> <span data-ttu-id="0ed0a-138">O `Get-ChildItem` comando retorna um objeto FileInfo que representa o arquivo de PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-138">The `Get-ChildItem` command returns a FileInfo object that represents the PowerShell.exe file.</span></span> <span data-ttu-id="0ed0a-139">O comando é colocado entre parênteses para garantir sua execução antes que qualquer propriedade seja acessada.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-139">The command is enclosed in parentheses to make sure that it is executed before any properties are accessed.</span></span> <span data-ttu-id="0ed0a-140">O `Get-ChildItem` comando é seguido por um ponto e o nome da propriedade CreationTime, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="0ed0a-140">The `Get-ChildItem` command is followed by a dot and the name of the CreationTime property, as follows:</span></span>

```powershell
(Get-ChildItem $pshome\PowerShell.exe).creationtime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

<span data-ttu-id="0ed0a-141">Você pode também salvar um objeto em uma variável e, em seguida, obter suas propriedades usando o método do ponto, conforme mostra o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="0ed0a-141">You can also save an object in a variable and then get its properties by using the dot method, as shown in the following example:</span></span>

```powershell
$a = Get-ChildItem $pshome\PowerShell.exe
$a.CreationTime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

<span data-ttu-id="0ed0a-142">Você também pode usar os `Select-Object` `Format-List` cmdlets e para exibir os valores de propriedade de um objeto.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-142">You can also use the `Select-Object` and `Format-List` cmdlets to display the property values of an object.</span></span> <span data-ttu-id="0ed0a-143">`Select-Object` e `Format-List` cada um tem um parâmetro **Property** .</span><span class="sxs-lookup"><span data-stu-id="0ed0a-143">`Select-Object` and `Format-List` each have a **Property** parameter.</span></span> <span data-ttu-id="0ed0a-144">Você pode usar o parâmetro **Property** para especificar uma ou mais propriedades e seus valores.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-144">You can use the **Property** parameter to specify one or more properties and their values.</span></span> <span data-ttu-id="0ed0a-145">Ou você pode usar o caractere curinga (\*) para representar todas as propriedades.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-145">Or, you can use the wildcard character (\*) to represent all the properties.</span></span>

<span data-ttu-id="0ed0a-146">Por exemplo, o comando a seguir exibe os valores de todas as propriedades do arquivo PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-146">For example, the following command displays the values of all the properties of the PowerShell.exe file.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Format-List -Property *
```

```output
PSPath            : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0\PowerShell.exe
PSParentPath      : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0
PSChildName       : PowerShell.exe
PSDrive           : C
PSProvider        : Microsoft.PowerShell.Core\FileSystem
PSIsContainer     : False
Mode              : -a----
VersionInfo       : File:             C:\Windows\System32\WindowsPowerShell\
                    v1.0\PowerShell.exe
                    InternalName:     POWERSHELL
                    OriginalFilename: PowerShell.EXE.MUI
                    FileVersion:      10.0.16299.15 (WinBuild.160101.0800)
                    FileDescription:  Windows PowerShell
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.16299.15
                    Debug:            False
                    Patched:          False
                    PreRelease:       False
                    PrivateBuild:     False
                    SpecialBuild:     False
                    Language:         English (United States)

BaseName          : PowerShell
Target            : {C:\Windows\WinSxS\amd64_microsoft-windows-powershell-ex
                    e_31bf3856ad364e35_10.0.16299.15_none_8c022aa6735716ae\p
                    owershell.exe}
LinkType          : HardLink
Name              : PowerShell.exe
Length            : 449024
DirectoryName     : C:\Windows\System32\WindowsPowerShell\v1.0
Directory         : C:\Windows\System32\WindowsPowerShell\v1.0
IsReadOnly        : False
Exists            : True
FullName          : C:\Windows\System32\WindowsPowerShell\v1.0\PowerShell.ex
Extension         : .exe
CreationTime      : 9/29/2017 6:43:19 AM
CreationTimeUtc   : 9/29/2017 1:43:19 PM
LastAccessTime    : 9/29/2017 6:43:19 AM
LastAccessTimeUtc : 9/29/2017 1:43:19 PM
LastWriteTime     : 9/29/2017 6:43:19 AM
LastWriteTimeUtc  : 9/29/2017 1:43:19 PM
Attributes        : Archive
```

### <a name="static-properties"></a><span data-ttu-id="0ed0a-147">Propriedades estáticas</span><span class="sxs-lookup"><span data-stu-id="0ed0a-147">Static properties</span></span>

<span data-ttu-id="0ed0a-148">Você pode usar as propriedades estáticas de classes .NET no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-148">You can use the static properties of .NET classes in PowerShell.</span></span> <span data-ttu-id="0ed0a-149">Propriedades estáticas são propriedades de classe, ao contrário das propriedades padrão, que são propriedades de um objeto.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-149">Static properties are properties of class, unlike standard properties, which are properties of an object.</span></span>

<span data-ttu-id="0ed0a-150">Para obter as propriedades estáticas de uma classe, use o parâmetro Static do cmdlet Get-Member.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-150">To get the static properties of an class, use the Static parameter of the Get-Member cmdlet.</span></span>

<span data-ttu-id="0ed0a-151">Por exemplo, o comando a seguir obtém as propriedades estáticas da `System.DateTime` classe.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-151">For example, the following command gets the static properties of the `System.DateTime` class.</span></span>

```powershell
Get-Date | Get-Member -MemberType Property -Static
```

```Output
TypeName: System.DateTime

Name     MemberType Definition
----     ---------- ----------
MaxValue Property   static datetime MaxValue {get;}
MinValue Property   static datetime MinValue {get;}
Now      Property   datetime Now {get;}
Today    Property   datetime Today {get;}
UtcNow   Property   datetime UtcNow {get;}
```

<span data-ttu-id="0ed0a-152">Para obter o valor de uma propriedade estática, use a sintaxe a seguir.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-152">To get the value of a static property, use the following syntax.</span></span>

```
[<ClassName>]::<Property>
```

<span data-ttu-id="0ed0a-153">Por exemplo, o comando a seguir obtém o valor da propriedade estática UtcNow da `System.DateTime` classe.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-153">For example, the following command gets the value of the UtcNow static property of the `System.DateTime` class.</span></span>

```powershell
[System.DateTime]::UtcNow
```

### <a name="properties-of-scalar-objects-and-collections"></a><span data-ttu-id="0ed0a-154">Propriedades de objetos e coleções escalares</span><span class="sxs-lookup"><span data-stu-id="0ed0a-154">Properties of scalar objects and collections</span></span>

<span data-ttu-id="0ed0a-155">Normalmente, as propriedades de um objeto ("escalar") de um tipo específico são diferentes das propriedades de uma coleção de objetos do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-155">The properties of one ("scalar") object of a particular type are often different from the properties of a collection of objects of the same type.</span></span>
<span data-ttu-id="0ed0a-156">Por exemplo, cada serviço tem como propriedade **DisplayName** , mas uma coleção de serviços não tem uma propriedade **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="0ed0a-156">For example, every service has as **DisplayName** property, but a collection of services does not have a **DisplayName** property.</span></span>

<span data-ttu-id="0ed0a-157">O comando a seguir obtém o valor da propriedade **DisplayName** do serviço ' AudioSrv '.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-157">The following command gets the value of the **DisplayName** property of the 'Audiosrv' service.</span></span>

```powershell
(Get-Service Audiosrv).DisplayName
```

```output
Windows Audio
```

<span data-ttu-id="0ed0a-158">A partir do PowerShell 3,0, o PowerShell tenta evitar erros de script que resultam das diferentes propriedades de coleções e objetos escalares.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-158">Beginning in PowerShell 3.0, PowerShell tries to prevent scripting errors that result from the differing properties of scalar objects and collections.</span></span> <span data-ttu-id="0ed0a-159">O mesmo comando retorna o valor da propriedade **DisplayName** de cada serviço que `Get-Service` retorna.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-159">The same command returns the value of the **DisplayName** property of every service that `Get-Service` returns.</span></span>

```powershell
(Get-Service).DisplayName
```

```output
Application Experience
Application Layer Gateway Service
Windows All-User Install Agent
Application Identity
Application Information
...
```

<span data-ttu-id="0ed0a-160">Quando você envia uma coleção, mas solicita uma propriedade que existe somente em objetos únicos ("escalares"), o PowerShell retorna o valor dessa propriedade para cada objeto na coleção.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-160">When you submit a collection, but request a property that exists only on single ("scalar") objects, PowerShell returns the value of that property for every object in the collection.</span></span>

<span data-ttu-id="0ed0a-161">Todas as coleções têm uma propriedade **Count** que retorna quantos objetos estão na coleção.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-161">All collections have a **Count** property that returns how many objects are in the collection.</span></span>

```powershell
(Get-Service).Count
```

```output
176
```

<span data-ttu-id="0ed0a-162">A partir do PowerShell 3,0, se você solicitar a propriedade Count ou length de zero Objects ou um objeto, o PowerShell retornará o valor correto.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-162">Beginning in PowerShell 3.0, if you request the Count or Length property of zero objects or one object, PowerShell returns the correct value.</span></span>

```powershell
(Get-Service Audiosrv).Count
```

```output
1
```

<span data-ttu-id="0ed0a-163">Se uma propriedade existir nos objetos individuais e na coleção, somente a propriedade da coleção será retornada.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-163">If a property exists on the individual objects and on the collection, only the collection's property is returned.</span></span>

 ```powershell
 $collection = @(
 [pscustomobject]@{length = "foo"}
 [pscustomobject]@{length = "bar"}
 )
 # PowerShell returns the collection's Length.
 $collection.length
 ```

 ```output
 2
 ```

<span data-ttu-id="0ed0a-164">Esse recurso também funciona em métodos de objetos escalares e de coleções.</span><span class="sxs-lookup"><span data-stu-id="0ed0a-164">This feature also works on methods of scalar objects and collections.</span></span> <span data-ttu-id="0ed0a-165">Para obter mais informações, consulte [about_Methods](about_methods.md).</span><span class="sxs-lookup"><span data-stu-id="0ed0a-165">For more information, see [about_Methods](about_methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ed0a-166">Confira também</span><span class="sxs-lookup"><span data-stu-id="0ed0a-166">See also</span></span>

[<span data-ttu-id="0ed0a-167">about_Methods</span><span class="sxs-lookup"><span data-stu-id="0ed0a-167">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="0ed0a-168">about_Objects</span><span class="sxs-lookup"><span data-stu-id="0ed0a-168">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="0ed0a-169">Get-Member</span><span class="sxs-lookup"><span data-stu-id="0ed0a-169">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

[<span data-ttu-id="0ed0a-170">Select-Object</span><span class="sxs-lookup"><span data-stu-id="0ed0a-170">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

[<span data-ttu-id="0ed0a-171">Format-List</span><span class="sxs-lookup"><span data-stu-id="0ed0a-171">Format-List</span></span>](xref:Microsoft.PowerShell.Utility.Format-List)

