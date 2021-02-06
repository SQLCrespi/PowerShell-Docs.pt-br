---
description: Descreve como usar propriedades de objeto no PowerShell.
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Properties
ms.openlocfilehash: c5cc7abdd580a0fa57134f9c79616d1d8290a7e1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597598"
---
# <a name="about-properties"></a><span data-ttu-id="f0da0-103">Sobre propriedades</span><span class="sxs-lookup"><span data-stu-id="f0da0-103">About Properties</span></span>

## <a name="short-description"></a><span data-ttu-id="f0da0-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="f0da0-104">Short description</span></span>
<span data-ttu-id="f0da0-105">Descreve como usar propriedades de objeto no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0da0-105">Describes how to use object properties in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="f0da0-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="f0da0-106">Long description</span></span>

<span data-ttu-id="f0da0-107">O PowerShell usa coleções estruturadas de informações chamadas de objetos para representar os itens em armazenamentos de dados ou o estado do computador.</span><span class="sxs-lookup"><span data-stu-id="f0da0-107">PowerShell uses structured collections of information called objects to represent the items in data stores or the state of the computer.</span></span> <span data-ttu-id="f0da0-108">Normalmente, você trabalha com objetos que fazem parte do Microsoft .NET Framework, mas também pode criar objetos personalizados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0da0-108">Typically, you work with object that are part of the Microsoft .NET Framework, but you can also create custom objects in PowerShell.</span></span>

<span data-ttu-id="f0da0-109">A associação entre um item e seu objeto é muito próxima.</span><span class="sxs-lookup"><span data-stu-id="f0da0-109">The association between an item and its object is very close.</span></span> <span data-ttu-id="f0da0-110">Ao alterar um objeto, você geralmente altera o item que ele representa.</span><span class="sxs-lookup"><span data-stu-id="f0da0-110">When you change an object, you usually change the item that it represents.</span></span> <span data-ttu-id="f0da0-111">Por exemplo, quando você recebe um arquivo no PowerShell, não obtém o arquivo real.</span><span class="sxs-lookup"><span data-stu-id="f0da0-111">For example, when you get a file in PowerShell, you do not get the actual file.</span></span> <span data-ttu-id="f0da0-112">Em vez disso, você recebe um objeto FileInfo que representa o arquivo.</span><span class="sxs-lookup"><span data-stu-id="f0da0-112">Instead, you get a FileInfo object that represents the file.</span></span> <span data-ttu-id="f0da0-113">Quando você altera o objeto FileInfo, o arquivo também é alterado.</span><span class="sxs-lookup"><span data-stu-id="f0da0-113">When you change the FileInfo object, the file changes too.</span></span>

<span data-ttu-id="f0da0-114">A maioria dos objetos tem propriedades.</span><span class="sxs-lookup"><span data-stu-id="f0da0-114">Most objects have properties.</span></span> <span data-ttu-id="f0da0-115">Propriedades são os dados associados a um objeto.</span><span class="sxs-lookup"><span data-stu-id="f0da0-115">Properties are the data that is associated with an object.</span></span> <span data-ttu-id="f0da0-116">Tipos diferentes de objeto têm propriedades diferentes.</span><span class="sxs-lookup"><span data-stu-id="f0da0-116">Different types of object have different properties.</span></span> <span data-ttu-id="f0da0-117">Por exemplo, um objeto FileInfo, que representa um arquivo, tem uma propriedade **IsReadOnly** que contém $true se o arquivo for o atributo somente leitura e $false se não tiver.</span><span class="sxs-lookup"><span data-stu-id="f0da0-117">For example, a FileInfo object, which represents a file, has an **IsReadOnly** property that contains $True if the file the read-only attribute and $False if it does not.</span></span>
<span data-ttu-id="f0da0-118">Um objeto DirectoryInfo, que representa um diretório do sistema de arquivos, tem uma propriedade Parent que contém o caminho até o diretório pai.</span><span class="sxs-lookup"><span data-stu-id="f0da0-118">A DirectoryInfo object, which represents a file system directory, has a Parent property that contains the path to the parent directory.</span></span>

### <a name="object-properties"></a><span data-ttu-id="f0da0-119">Propriedades do objeto</span><span class="sxs-lookup"><span data-stu-id="f0da0-119">Object properties</span></span>

<span data-ttu-id="f0da0-120">Para obter as propriedades de um objeto, use o `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f0da0-120">To get the properties of an object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="f0da0-121">Por exemplo, para obter as propriedades de um objeto **FileInfo** , use o `Get-ChildItem` cmdlet para obter o objeto FileInfo que representa um arquivo.</span><span class="sxs-lookup"><span data-stu-id="f0da0-121">For example, to get the properties of a **FileInfo** object, use the `Get-ChildItem` cmdlet to get the FileInfo object that represents a file.</span></span> <span data-ttu-id="f0da0-122">Em seguida, use um operador de pipeline (&#124;) para o qual enviar o objeto **FileInfo** `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="f0da0-122">Then, use a pipeline operator (&#124;) to send the **FileInfo** object to `Get-Member`.</span></span> <span data-ttu-id="f0da0-123">O comando a seguir obtém o arquivo PowerShell.exe e o envia para o `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="f0da0-123">The following command gets the PowerShell.exe file and sends it to `Get-Member`.</span></span>
<span data-ttu-id="f0da0-124">A \$ variável automática pshome contém o caminho do diretório de instalação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0da0-124">The \$Pshome automatic variable contains the path of the PowerShell installation directory.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member
```

<span data-ttu-id="f0da0-125">A saída do comando lista os membros do objeto **FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="f0da0-125">The output of the command lists the members of the **FileInfo** object.</span></span>
<span data-ttu-id="f0da0-126">Os membros incluem propriedades e métodos.</span><span class="sxs-lookup"><span data-stu-id="f0da0-126">Members include both properties and methods.</span></span> <span data-ttu-id="f0da0-127">Quando você trabalha no PowerShell, tem acesso a todos os membros dos objetos.</span><span class="sxs-lookup"><span data-stu-id="f0da0-127">When you work in PowerShell, you have access to all the members of the objects.</span></span>

<span data-ttu-id="f0da0-128">Para obter apenas as propriedades de um objeto e não os métodos, use o parâmetro MemberType do `Get-Member` cmdlet com um valor de "Property", conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="f0da0-128">To get only the properties of an object and not the methods, use the MemberType parameter of the `Get-Member` cmdlet with a value of "property", as shown in the following example.</span></span>

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

<span data-ttu-id="f0da0-129">Depois de localizar as propriedades, você pode usá-las em seus comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0da0-129">After you find the properties, you can use them in your PowerShell commands.</span></span>

## <a name="property-values"></a><span data-ttu-id="f0da0-130">Valores de propriedade</span><span class="sxs-lookup"><span data-stu-id="f0da0-130">Property values</span></span>

<span data-ttu-id="f0da0-131">Embora todo objeto de um tipo específico tenha as mesmas propriedades, os valores dessas propriedades descrevem o objeto específico.</span><span class="sxs-lookup"><span data-stu-id="f0da0-131">Although every object of a specific type has the same properties, the values of those properties describe the particular object.</span></span> <span data-ttu-id="f0da0-132">Por exemplo, cada objeto FileInfo tem uma propriedade CreationTime, mas o valor dessa propriedade é diferente para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="f0da0-132">For example, every FileInfo object has a CreationTime property, but the value of that property differs for each file.</span></span>

<span data-ttu-id="f0da0-133">A maneira mais comum para obter os valores das propriedades de um objeto é usar o método de ponto.</span><span class="sxs-lookup"><span data-stu-id="f0da0-133">The most common way to get the values of the properties of an object is to use the dot method.</span></span> <span data-ttu-id="f0da0-134">Digite uma referência ao objeto, como uma variável que contém o objeto, ou um comando que obtém o objeto.</span><span class="sxs-lookup"><span data-stu-id="f0da0-134">Type a reference to the object, such as a variable that contains the object, or a command that gets the object.</span></span> <span data-ttu-id="f0da0-135">Em seguida, digite um ponto (.) seguido pelo nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="f0da0-135">Then, type a dot (.) followed by the property name.</span></span>

<span data-ttu-id="f0da0-136">Por exemplo, o comando a seguir exibe o valor da propriedade CreationTime do arquivo PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="f0da0-136">For example, the following command displays the value of the CreationTime property of the PowerShell.exe file.</span></span> <span data-ttu-id="f0da0-137">O `Get-ChildItem` comando retorna um objeto FileInfo que representa o arquivo de PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="f0da0-137">The `Get-ChildItem` command returns a FileInfo object that represents the PowerShell.exe file.</span></span> <span data-ttu-id="f0da0-138">O comando é colocado entre parênteses para garantir sua execução antes que qualquer propriedade seja acessada.</span><span class="sxs-lookup"><span data-stu-id="f0da0-138">The command is enclosed in parentheses to make sure that it is executed before any properties are accessed.</span></span> <span data-ttu-id="f0da0-139">O `Get-ChildItem` comando é seguido por um ponto e o nome da propriedade CreationTime, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f0da0-139">The `Get-ChildItem` command is followed by a dot and the name of the CreationTime property, as follows:</span></span>

```powershell
(Get-ChildItem $pshome\PowerShell.exe).creationtime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

<span data-ttu-id="f0da0-140">Você pode também salvar um objeto em uma variável e, em seguida, obter suas propriedades usando o método do ponto, conforme mostra o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="f0da0-140">You can also save an object in a variable and then get its properties by using the dot method, as shown in the following example:</span></span>

```powershell
$a = Get-ChildItem $pshome\PowerShell.exe
$a.CreationTime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

<span data-ttu-id="f0da0-141">Você também pode usar os `Select-Object` `Format-List` cmdlets e para exibir os valores de propriedade de um objeto.</span><span class="sxs-lookup"><span data-stu-id="f0da0-141">You can also use the `Select-Object` and `Format-List` cmdlets to display the property values of an object.</span></span> <span data-ttu-id="f0da0-142">`Select-Object` e `Format-List` cada um tem um parâmetro **Property** .</span><span class="sxs-lookup"><span data-stu-id="f0da0-142">`Select-Object` and `Format-List` each have a **Property** parameter.</span></span> <span data-ttu-id="f0da0-143">Você pode usar o parâmetro **Property** para especificar uma ou mais propriedades e seus valores.</span><span class="sxs-lookup"><span data-stu-id="f0da0-143">You can use the **Property** parameter to specify one or more properties and their values.</span></span> <span data-ttu-id="f0da0-144">Ou você pode usar o caractere curinga (\*) para representar todas as propriedades.</span><span class="sxs-lookup"><span data-stu-id="f0da0-144">Or, you can use the wildcard character (\*) to represent all the properties.</span></span>

<span data-ttu-id="f0da0-145">Por exemplo, o comando a seguir exibe os valores de todas as propriedades do arquivo PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="f0da0-145">For example, the following command displays the values of all the properties of the PowerShell.exe file.</span></span>

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

### <a name="static-properties"></a><span data-ttu-id="f0da0-146">Propriedades estáticas</span><span class="sxs-lookup"><span data-stu-id="f0da0-146">Static properties</span></span>

<span data-ttu-id="f0da0-147">Você pode usar as propriedades estáticas de classes .NET no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0da0-147">You can use the static properties of .NET classes in PowerShell.</span></span> <span data-ttu-id="f0da0-148">Propriedades estáticas são propriedades de classe, ao contrário das propriedades padrão, que são propriedades de um objeto.</span><span class="sxs-lookup"><span data-stu-id="f0da0-148">Static properties are properties of class, unlike standard properties, which are properties of an object.</span></span>

<span data-ttu-id="f0da0-149">Para obter as propriedades estáticas de uma classe, use o parâmetro Static do cmdlet Get-Member.</span><span class="sxs-lookup"><span data-stu-id="f0da0-149">To get the static properties of an class, use the Static parameter of the Get-Member cmdlet.</span></span>

<span data-ttu-id="f0da0-150">Por exemplo, o comando a seguir obtém as propriedades estáticas da `System.DateTime` classe.</span><span class="sxs-lookup"><span data-stu-id="f0da0-150">For example, the following command gets the static properties of the `System.DateTime` class.</span></span>

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

<span data-ttu-id="f0da0-151">Para obter o valor de uma propriedade estática, use a sintaxe a seguir.</span><span class="sxs-lookup"><span data-stu-id="f0da0-151">To get the value of a static property, use the following syntax.</span></span>

```
[<ClassName>]::<Property>
```

<span data-ttu-id="f0da0-152">Por exemplo, o comando a seguir obtém o valor da propriedade estática UtcNow da `System.DateTime` classe.</span><span class="sxs-lookup"><span data-stu-id="f0da0-152">For example, the following command gets the value of the UtcNow static property of the `System.DateTime` class.</span></span>

```powershell
[System.DateTime]::UtcNow
```

### <a name="properties-of-scalar-objects-and-collections"></a><span data-ttu-id="f0da0-153">Propriedades de objetos e coleções escalares</span><span class="sxs-lookup"><span data-stu-id="f0da0-153">Properties of scalar objects and collections</span></span>

<span data-ttu-id="f0da0-154">Normalmente, as propriedades de um objeto ("escalar") de um tipo específico são diferentes das propriedades de uma coleção de objetos do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="f0da0-154">The properties of one ("scalar") object of a particular type are often different from the properties of a collection of objects of the same type.</span></span>
<span data-ttu-id="f0da0-155">Por exemplo, cada serviço tem como propriedade **DisplayName** , mas uma coleção de serviços não tem uma propriedade **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="f0da0-155">For example, every service has as **DisplayName** property, but a collection of services does not have a **DisplayName** property.</span></span>

<span data-ttu-id="f0da0-156">O comando a seguir obtém o valor da propriedade **DisplayName** do serviço ' AudioSrv '.</span><span class="sxs-lookup"><span data-stu-id="f0da0-156">The following command gets the value of the **DisplayName** property of the 'Audiosrv' service.</span></span>

```powershell
(Get-Service Audiosrv).DisplayName
```

```output
Windows Audio
```

<span data-ttu-id="f0da0-157">A partir do PowerShell 3,0, o PowerShell tenta evitar erros de script que resultam das diferentes propriedades de coleções e objetos escalares.</span><span class="sxs-lookup"><span data-stu-id="f0da0-157">Beginning in PowerShell 3.0, PowerShell tries to prevent scripting errors that result from the differing properties of scalar objects and collections.</span></span> <span data-ttu-id="f0da0-158">O mesmo comando retorna o valor da propriedade **DisplayName** de cada serviço que `Get-Service` retorna.</span><span class="sxs-lookup"><span data-stu-id="f0da0-158">The same command returns the value of the **DisplayName** property of every service that `Get-Service` returns.</span></span>

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

<span data-ttu-id="f0da0-159">Quando você envia uma coleção, mas solicita uma propriedade que existe somente em objetos únicos ("escalares"), o PowerShell retorna o valor dessa propriedade para cada objeto na coleção.</span><span class="sxs-lookup"><span data-stu-id="f0da0-159">When you submit a collection, but request a property that exists only on single ("scalar") objects, PowerShell returns the value of that property for every object in the collection.</span></span>

<span data-ttu-id="f0da0-160">Todas as coleções têm uma propriedade **Count** que retorna quantos objetos estão na coleção.</span><span class="sxs-lookup"><span data-stu-id="f0da0-160">All collections have a **Count** property that returns how many objects are in the collection.</span></span>

```powershell
(Get-Service).Count
```

```output
176
```

<span data-ttu-id="f0da0-161">A partir do PowerShell 3,0, se você solicitar a propriedade Count ou length de zero Objects ou um objeto, o PowerShell retornará o valor correto.</span><span class="sxs-lookup"><span data-stu-id="f0da0-161">Beginning in PowerShell 3.0, if you request the Count or Length property of zero objects or one object, PowerShell returns the correct value.</span></span>

```powershell
(Get-Service Audiosrv).Count
```

```output
1
```

<span data-ttu-id="f0da0-162">Se uma propriedade existir nos objetos individuais e na coleção, somente a propriedade da coleção será retornada.</span><span class="sxs-lookup"><span data-stu-id="f0da0-162">If a property exists on the individual objects and on the collection, only the collection's property is returned.</span></span>

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

<span data-ttu-id="f0da0-163">Esse recurso também funciona em métodos de objetos escalares e de coleções.</span><span class="sxs-lookup"><span data-stu-id="f0da0-163">This feature also works on methods of scalar objects and collections.</span></span> <span data-ttu-id="f0da0-164">Para obter mais informações, consulte [about_Methods](about_methods.md).</span><span class="sxs-lookup"><span data-stu-id="f0da0-164">For more information, see [about_Methods](about_methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0da0-165">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f0da0-165">See also</span></span>

[<span data-ttu-id="f0da0-166">about_Methods</span><span class="sxs-lookup"><span data-stu-id="f0da0-166">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="f0da0-167">about_Objects</span><span class="sxs-lookup"><span data-stu-id="f0da0-167">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="f0da0-168">Get-Member</span><span class="sxs-lookup"><span data-stu-id="f0da0-168">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

[<span data-ttu-id="f0da0-169">Select-Object</span><span class="sxs-lookup"><span data-stu-id="f0da0-169">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

[<span data-ttu-id="f0da0-170">Format-List</span><span class="sxs-lookup"><span data-stu-id="f0da0-170">Format-List</span></span>](xref:Microsoft.PowerShell.Utility.Format-List)

