---
description: Descreve como você pode usar classes para desenvolver no PowerShell com a DSC (configuração de estado desejado).
keywords: powershell, cmdlet
Locale: en-US
ms.date: 1/11/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes_and_DSC
ms.openlocfilehash: 272d6872d096de864044ae41449caff472bb1799
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195931"
---
# <a name="about-classes-and-desired-state-configuration"></a><span data-ttu-id="7b440-104">Sobre classes e configuração de estado desejado</span><span class="sxs-lookup"><span data-stu-id="7b440-104">About Classes and Desired State Configuration</span></span>

## <a name="short-description"></a><span data-ttu-id="7b440-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="7b440-105">Short description</span></span>

<span data-ttu-id="7b440-106">Descreve como você pode usar classes para desenvolver no PowerShell com a DSC (configuração de estado desejado).</span><span class="sxs-lookup"><span data-stu-id="7b440-106">Describes how you can use classes to develop in PowerShell with Desired State Configuration (DSC).</span></span>

## <a name="long-description"></a><span data-ttu-id="7b440-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="7b440-107">Long description</span></span>

<span data-ttu-id="7b440-108">A partir do Windows PowerShell 5,0, o idioma foi adicionado para definir classes e outros tipos definidos pelo usuário, usando sintaxe formal e semântica que são semelhantes a outras linguagens de programação orientadas a objeto.</span><span class="sxs-lookup"><span data-stu-id="7b440-108">Starting in Windows PowerShell 5.0, language was added to define classes and other user-defined types, by using formal syntax and semantics that are similar to other object-oriented programming languages.</span></span> <span data-ttu-id="7b440-109">O objetivo é permitir que desenvolvedores e profissionais de ti adotem o PowerShell para uma variedade maior de casos de uso, simplifiquem o desenvolvimento de artefatos do PowerShell, como recursos de DSC, e acelerem a cobertura de superfícies de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="7b440-109">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts such as DSC resources, and accelerate coverage of management surfaces.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="7b440-110">Cenários com suporte</span><span class="sxs-lookup"><span data-stu-id="7b440-110">Supported scenarios</span></span>

<span data-ttu-id="7b440-111">Os cenários a seguir têm suporte:</span><span class="sxs-lookup"><span data-stu-id="7b440-111">The following scenarios are supported:</span></span>

- <span data-ttu-id="7b440-112">Defina os recursos de DSC e seus tipos associados usando a linguagem do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b440-112">Define DSC resources and their associated types by using the PowerShell language.</span></span>
- <span data-ttu-id="7b440-113">Defina tipos personalizados no PowerShell usando construções de programação orientada a objeto familiares, como classes, propriedades, métodos e herança.</span><span class="sxs-lookup"><span data-stu-id="7b440-113">Define custom types in PowerShell by using familiar object-oriented programming constructs, such as classes, properties, methods, and inheritance.</span></span>
- <span data-ttu-id="7b440-114">Tipos de depuração usando a linguagem do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b440-114">Debug types by using the PowerShell language.</span></span>
- <span data-ttu-id="7b440-115">Gere e manipule exceções usando mecanismos formais e no nível certo.</span><span class="sxs-lookup"><span data-stu-id="7b440-115">Generate and handle exceptions by using formal mechanisms, and at the right level.</span></span>

## <a name="define-dsc-resources-with-classes"></a><span data-ttu-id="7b440-116">Definir recursos de DSC com classes</span><span class="sxs-lookup"><span data-stu-id="7b440-116">Define DSC resources with classes</span></span>

<span data-ttu-id="7b440-117">Além das alterações de sintaxe, as principais diferenças entre um recurso de DSC definido por classe e um provedor de recursos de DSC de cmdlet são os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="7b440-117">Apart from syntax changes, the major differences between a class-defined DSC resource and a cmdlet DSC resource provider are the following items:</span></span>

- <span data-ttu-id="7b440-118">Um arquivo MOF (Management Object Format) não é necessário.</span><span class="sxs-lookup"><span data-stu-id="7b440-118">A Management Object Format (MOF) file is not required.</span></span>
- <span data-ttu-id="7b440-119">Uma subpasta DSCResource na pasta do módulo não é necessária.</span><span class="sxs-lookup"><span data-stu-id="7b440-119">A DSCResource subfolder in the module folder is not required.</span></span>
- <span data-ttu-id="7b440-120">Um arquivo de módulo do PowerShell pode conter várias classes de recursos DSC.</span><span class="sxs-lookup"><span data-stu-id="7b440-120">A PowerShell module file can contain multiple DSC resource classes.</span></span>

## <a name="create-a-class-defined-dsc-resource-provider"></a><span data-ttu-id="7b440-121">Criar um provedor de recursos DSC definido pela classe</span><span class="sxs-lookup"><span data-stu-id="7b440-121">Create a class-defined DSC resource provider</span></span>

<span data-ttu-id="7b440-122">O exemplo a seguir é um provedor de recursos DSC definido pela classe que é salvo como um módulo, MyDSCResource. psm1.</span><span class="sxs-lookup"><span data-stu-id="7b440-122">The following example is a class-defined DSC resource provider that is saved as a module, MyDSCResource.psm1.</span></span> <span data-ttu-id="7b440-123">Você sempre deve incluir uma propriedade de chave em um provedor de recursos de DSC definido pela classe.</span><span class="sxs-lookup"><span data-stu-id="7b440-123">You must always include a key property in a class-defined DSC resource provider.</span></span>

```powershell
enum Ensure
{
    Absent
    Present
}

<#
    This resource manages the file in a specific path.
    [DscResource()] indicates the class is a DSC resource
#>

[DscResource()]
class FileResource
{
    <#
        This property is the fully qualified path to the file that is
        expected to be present or absent.

        The [DscProperty(Key)] attribute indicates the property is a
        key and its value uniquely identifies a resource instance.
        Defining this attribute also means the property is required
        and DSC will ensure a value is set before calling the resource.

        A DSC resource must define at least one key property.
    #>
    [DscProperty(Key)]
    [string]$Path

    <#
        This property indicates if the settings should be present or absent
        on the system. For present, the resource ensures the file pointed
        to by $Path exists. For absent, it ensures the file point to by
        $Path does not exist.

        The [DscProperty(Mandatory)] attribute indicates the property is
        required and DSC will guarantee it is set.

        If Mandatory is not specified or if it is defined as
        Mandatory=$false, the value is not guaranteed to be set when DSC
        calls the resource.  This is appropriate for optional properties.
    #>
    [DscProperty(Mandatory)]
    [Ensure] $Ensure

    <#
        This property defines the fully qualified path to a file that will
        be placed on the system if $Ensure = Present and $Path does not
        exist.

        NOTE: This property is required because [DscProperty(Mandatory)] is
        set.
    #>
    [DscProperty(Mandatory)]
    [string] $SourcePath

    <#
        This property reports the file's create timestamp.

        [DscProperty(NotConfigurable)] attribute indicates the property is
        not configurable in DSC configuration.  Properties marked this way
        are populated by the Get() method to report additional details
        about the resource when it is present.

    #>
    [DscProperty(NotConfigurable)]
    [Nullable[datetime]] $CreationTime

    <#
        This method is equivalent of the Set-TargetResource script function.
        It sets the resource to the desired state.
    #>
    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)
        if($this.ensure -eq [Ensure]::Present)
        {
            if(-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    <#

        This method is equivalent of the Test-TargetResource script
        function. It should return True or False, showing whether the
        resource is in a desired state.
    #>
    [bool] Test()
    {
        $present = $this.TestFilePath($this.Path)

        if($this.Ensure -eq [Ensure]::Present)
        {
            return $present
        }
        else
{
            return -not $present
        }
    }

    <#
        This method is equivalent of the Get-TargetResource script function.
        The implementation should use the keys to find appropriate
        resources. This method returns an instance of this class with the
        updated key properties.
    #>
    [FileResource] Get()
    {
        $present = $this.TestFilePath($this.Path)

        if ($present)
        {
            $file = Get-ChildItem -LiteralPath $this.Path
            $this.CreationTime = $file.CreationTime
            $this.Ensure = [Ensure]::Present
        }
        else
        {
            $this.CreationTime = $null
            $this.Ensure = [Ensure]::Absent
        }
        return $this
    }

    <#
        Helper method to check if the file exists and it is correct file
    #>
    [bool] TestFilePath([string] $location)
    {
        $present = $true

        $item = Get-ChildItem -LiteralPath $location -ea Ignore
        if ($item -eq $null)
        {
            $present = $false
        }
        elseif( $item.PSProvider.Name -ne "FileSystem")
        {
            throw "Path $($location) is not a file path."
        }
        elseif($item.PSIsContainer)
        {
            throw "Path $($location) is a directory path."
        }
        return $present
    }

    <#
        Helper method to copy file from source to path
    #>
    [void] CopyFile()
    {
        if(-not $this.TestFilePath($this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        [System.IO.FileInfo]
        $destFileInfo = new-object System.IO.FileInfo($this.Path)

        if (-not $destFileInfo.Directory.Exists)
        {
            $FullName = $destFileInfo.Directory.FullName
            $Message = "Creating directory $FullName"

            Write-Verbose -Message $Message

            #use CreateDirectory instead of New-Item to avoid code
            # to handle the non-terminating error
            [System.IO.Directory]::CreateDirectory($FullName)
        }

        if(Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose -Message "Copying $this.SourcePath to $this.Path"

        #DSC engine catches and reports any error that occurs
        Copy-Item -Path $this.SourcePath -Destination $this.Path -Force
    }
}
# This module defines a class for a DSC "FileResource" provider.

enum Ensure
{
    Absent
    Present
}

<# This resource manages the file in a specific path.
[DscResource()] indicates the class is a DSC resource
#>

[DscResource()]
class FileResource{

    <# This is a key property
        [DscResourceKey()] also means the property is required.
        It is guaranteed to be set, other properties may not
        be set if the configuration did not specify values.
    #>
    [DscResourceKey()]
    [string]$Path

    <#
        [DscResourceMandatory()] means the property is required.
        It is guaranteed to be set, other properties may not be set
        if the configuration did not specify values.
    #>
    [DscResourceMandatory()]
    [Ensure] $Ensure

    <#
        [DscResourceMandatory()] means the property is required.
    #>
    [DscResourceMandatory()]
    [string] $SourcePath

    [DscResource

    <#
        This method replaces the Set-TargetResource DSC script function.
        It sets the resource to the desired state.
    #>
    [void] Set()
    {
        $fileExists = Test-Path -path $this.Path -PathType Leaf
        if($this.ensure -eq [Ensure]::Present)
        {
            if(-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if($fileExists)
            {
                Write-Verbose -Message "Deleting the file $this.Path"
                Remove-Item -LiteralPath $this.Path
            }
        }
    }

    <#

        This method replaces the Test-TargetResource function.
        It should return True or False, showing whether the resource
        is in a desired state.
    #>

    [bool] Test()
    {
        if(Test-Path -path $this.Path -PathType Container)
        {
            throw "Path '$this.Path' is a directory path."
        }

        $fileExists = Test-Path -path $this.Path -PathType Leaf

        if($this.ensure -eq [Ensure]::Present)
        {
            return $fileExists
        }

        return (-not $fileExists)
    }

    <#
        This method replaces the Get-TargetResource function.
        The implementation should use the keys to find appropriate
        resources. This method returns an instance of this class with the
        updated key properties.
    #>

    [FileResource] Get()
    {
        $file = Get-item $this.Path
        return $this
    }

    <#
        Helper method to copy file from source to path.
        Because this resource provider run under system,
        Only the Administrators and system have full
        access to the new created directory and file
    #>
    CopyFile()
    {
        if(Test-Path -path $this.SourcePath -PathType Container)
        {
            throw "SourcePath '$this.SourcePath' is a directory path"
        }

        if( -not (Test-Path -path $this.SourcePath -PathType Leaf))
        {
            throw "SourcePath '$this.SourcePath' is not found."
        }

        [System.IO.FileInfo]
        $destFileInfo = new-object System.IO.FileInfo($this.Path)

        if (-not $destFileInfo.Directory.Exists)
        {
            $FullName = $destFileInfo.Directory.FullName
            $Message = "Creating directory $FullName"

            Write-Verbose -Message $Message

            #use CreateDirectory instead of New-Item to avoid lines
            # to handle the non-terminating error
            [System.IO.Directory]::CreateDirectory($FullName)
        }

        if(Test-Path -path $this.Path -PathType Container)
        {
            throw "Path '$this.Path' is a directory path"
        }

        Write-Verbose -Message "Copying $this.SourcePath to $this.Path"

        #DSC engine catches and reports any error that occurs
        Copy-Item -Path $this.SourcePath -Destination $this.Path -Force
    }
}
```

## <a name="create-a-module-manifest"></a><span data-ttu-id="7b440-124">Criar um manifesto de módulo</span><span class="sxs-lookup"><span data-stu-id="7b440-124">Create a module manifest</span></span>

<span data-ttu-id="7b440-125">Depois de criar o provedor de recursos DSC definido por classe e salvá-lo como um módulo, crie um manifesto de módulo para o módulo.</span><span class="sxs-lookup"><span data-stu-id="7b440-125">After creating the class-defined DSC resource provider, and saving it as a module, create a module manifest for the module.</span></span> <span data-ttu-id="7b440-126">Para disponibilizar um recurso baseado em classes para o mecanismo de DSC, você precisa incluir uma declaração `DscResourcesToExport` no arquivo de manifesto que instrui o módulo para exportar recursos.</span><span class="sxs-lookup"><span data-stu-id="7b440-126">To make a class-based resource available to the DSC engine, you must include a `DscResourcesToExport` statement in the manifest file that instructs the module to export the resource.</span></span> <span data-ttu-id="7b440-127">Neste exemplo, o manifesto de módulo a seguir é salvo como MyDscResource.psd1.</span><span class="sxs-lookup"><span data-stu-id="7b440-127">In this example, the following module manifest is saved as MyDscResource.psd1.</span></span>

```powershell
@{

# Script module or binary module file associated with this manifest.
RootModule = 'MyDscResource.psm1'

DscResourcesToExport = 'FileResource'

# Version number of this module.
ModuleVersion = '1.0'

# ID used to uniquely identify this module
GUID = '81624038-5e71-40f8-8905-b1a87afe22d7'

# Author of this module
Author = 'Microsoft Corporation'

# Company or vendor of this module
CompanyName = 'Microsoft Corporation'

# Copyright statement for this module
Copyright = '(c) 2014 Microsoft. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the PowerShell engine required by this module
PowerShellVersion = '5.0'

# Name of the PowerShell host required by this module
# PowerShellHostName = ''

}
```

## <a name="deploy-a-dsc-resource-provider"></a><span data-ttu-id="7b440-128">Implantar um provedor de recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="7b440-128">Deploy a DSC resource provider</span></span>

<span data-ttu-id="7b440-129">Implante o novo provedor de recursos de DSC criando uma pasta MyDscResource no `$pshome\Modules` ou no `$env:SystemDrive\ProgramFiles\WindowsPowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="7b440-129">Deploy the new DSC resource provider by creating a MyDscResource folder in `$pshome\Modules` or `$env:SystemDrive\ProgramFiles\WindowsPowerShell\Modules`.</span></span>

<span data-ttu-id="7b440-130">Não é necessário criar uma subpasta DSCResource.</span><span class="sxs-lookup"><span data-stu-id="7b440-130">You do not need to create a DSCResource subfolder.</span></span> <span data-ttu-id="7b440-131">Faça uma cópia do módulo e dos arquivos de manifesto de módulo (MyDscResource.psm1 e MyDscResource.psd1) e cole-os na pasta MyDscResource.</span><span class="sxs-lookup"><span data-stu-id="7b440-131">Copy the module and module manifest files (MyDscResource.psm1 and MyDscResource.psd1) to the MyDscResource folder.</span></span>

<span data-ttu-id="7b440-132">Desse ponto em diante, você cria e executa um script de configuração como faria com qualquer recurso DSC.</span><span class="sxs-lookup"><span data-stu-id="7b440-132">From this point, you create and run a configuration script as you would with any DSC resource.</span></span>

## <a name="create-a-dsc-configuration-script"></a><span data-ttu-id="7b440-133">Criar um script de configuração da DSC</span><span class="sxs-lookup"><span data-stu-id="7b440-133">Create a DSC configuration script</span></span>

<span data-ttu-id="7b440-134">Depois de salvar a classe e os arquivos de manifesto na estrutura de pastas, conforme descrito anteriormente, você pode criar uma configuração que use o novo recurso.</span><span class="sxs-lookup"><span data-stu-id="7b440-134">After saving the class and manifest files in the folder structure as described earlier, you can create a configuration that uses the new resource.</span></span> <span data-ttu-id="7b440-135">A configuração a seguir faz referência ao módulo MyDSCResource.</span><span class="sxs-lookup"><span data-stu-id="7b440-135">The following configuration references the MyDSCResource module.</span></span> <span data-ttu-id="7b440-136">Salve a configuração como um script MyResource.ps1.</span><span class="sxs-lookup"><span data-stu-id="7b440-136">Save the configuration as a script, MyResource.ps1.</span></span>

<span data-ttu-id="7b440-137">Para obter informações sobre como executar uma configuração DSC, consulte [visão geral da configuração de estado desejado do Windows PowerShell](/powershell/scripting/dsc/overview/dscforengineers).</span><span class="sxs-lookup"><span data-stu-id="7b440-137">For information about how to run a DSC configuration, see [Windows PowerShell Desired State Configuration Overview](/powershell/scripting/dsc/overview/dscforengineers).</span></span>

<span data-ttu-id="7b440-138">Antes de executar a configuração, crie `C:\test.txt` .</span><span class="sxs-lookup"><span data-stu-id="7b440-138">Before you run the configuration, create `C:\test.txt`.</span></span> <span data-ttu-id="7b440-139">A configuração verifica se o arquivo existe em `c:\test\test.txt` .</span><span class="sxs-lookup"><span data-stu-id="7b440-139">The configuration checks if the file exists at `c:\test\test.txt`.</span></span> <span data-ttu-id="7b440-140">Se o arquivo não existir, a configuração copiará o arquivo de `C:\test.txt` .</span><span class="sxs-lookup"><span data-stu-id="7b440-140">If the file does not exist, the configuration copies the file from `C:\test.txt`.</span></span>

```powershell
Configuration Test
{
    Import-DSCResource -module MyDscResource
    FileResource file
    {
        Path = "C:\test\test.txt"
        SourcePath = "C:\test.txt"
        Ensure = "Present"
    }
}
Test
Start-DscConfiguration -Wait -Force Test
```

<span data-ttu-id="7b440-141">Execute esse script como faria com qualquer script de configuração DSC.</span><span class="sxs-lookup"><span data-stu-id="7b440-141">Run this script as you would any DSC configuration script.</span></span> <span data-ttu-id="7b440-142">Para iniciar a configuração, em um console do PowerShell com privilégios elevados, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7b440-142">To start the configuration, in an elevated PowerShell console, run the following:</span></span>

`PS C:\test> .\MyResource.ps1`

## <a name="inheritance-in-powershell-classes"></a><span data-ttu-id="7b440-143">Herança em classes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b440-143">Inheritance in PowerShell classes</span></span>

### <a name="declare-base-classes-for-powershell-classes"></a><span data-ttu-id="7b440-144">Declarar classes base para classes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b440-144">Declare base classes for PowerShell classes</span></span>

<span data-ttu-id="7b440-145">Você pode declarar uma classe do PowerShell como um tipo base para outra classe do PowerShell, conforme mostrado no exemplo a seguir, em que **fruta** é um tipo base para a **Apple** .</span><span class="sxs-lookup"><span data-stu-id="7b440-145">You can declare a PowerShell class as a base type for another PowerShell class, as shown in the following example, in which **fruit** is a base type for **apple** .</span></span>

```powershell
class fruit
{
    [int]sold() {return 100500}
}

class apple : fruit {}
    [apple]::new().sold() # return 100500
```

### <a name="declare-implemented-interfaces-for-powershell-classes"></a><span data-ttu-id="7b440-146">Declarar interfaces implementadas para classes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b440-146">Declare implemented interfaces for PowerShell classes</span></span>

<span data-ttu-id="7b440-147">Você pode declarar interfaces implementadas após os tipos base, ou imediatamente após dois-pontos ( `:` ) se não houver nenhum tipo base especificado.</span><span class="sxs-lookup"><span data-stu-id="7b440-147">You can declare implemented interfaces after base types, or immediately after a colon (`:`) if there is no base type specified.</span></span> <span data-ttu-id="7b440-148">Separe todos os nomes de tipo usando vírgulas.</span><span class="sxs-lookup"><span data-stu-id="7b440-148">Separate all type names by using commas.</span></span> <span data-ttu-id="7b440-149">Isso é semelhante à sintaxe C#.</span><span class="sxs-lookup"><span data-stu-id="7b440-149">This is similar to C# syntax.</span></span>

```powershell
class MyComparable : system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableTest : test, system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

### <a name="call-base-class-constructors"></a><span data-ttu-id="7b440-150">Chamar construtores de classe base</span><span class="sxs-lookup"><span data-stu-id="7b440-150">Call base class constructors</span></span>

<span data-ttu-id="7b440-151">Para chamar um construtor de classe base de uma subclasse, adicione a `base` palavra-chave, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="7b440-151">To call a base class constructor from a subclass, add the `base` keyword, as shown in the following example:</span></span>

```powershell
class A {
    [int]$a
    A([int]$a)
    {
        $this.a = $a
    }
}

class B : A
{
    B() : base(103) {}
}

    [B]::new().a # return 103
```

<span data-ttu-id="7b440-152">Se uma classe base tiver um construtor padrão (sem parâmetros), você poderá omitir uma chamada de Construtor explícita, conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="7b440-152">If a base class has a default constructor (no parameters), you can omit an explicit constructor call, as shown.</span></span>

```powershell
class C : B
{
    C([int]$c) {}
}
```

### <a name="call-base-class-methods"></a><span data-ttu-id="7b440-153">Chamar métodos de classe base</span><span class="sxs-lookup"><span data-stu-id="7b440-153">Call base class methods</span></span>

<span data-ttu-id="7b440-154">É possível substituir os métodos existentes nas subclasses.</span><span class="sxs-lookup"><span data-stu-id="7b440-154">You can override existing methods in subclasses.</span></span> <span data-ttu-id="7b440-155">Para fazer a substituição, declare métodos usando o mesmo nome e assinatura.</span><span class="sxs-lookup"><span data-stu-id="7b440-155">To do the override, declare methods by using the same name and signature.</span></span>

```powershell
class baseClass
{
    [int]days() {return 100500}
}
class childClass1 : baseClass
{
    [int]days () {return 200600}
}

    [childClass1]::new().days() # return 200600
```

<span data-ttu-id="7b440-156">Para chamar métodos de classe base de implementações substituídas, converta para a classe base `([baseclass]$this)` na invocação.</span><span class="sxs-lookup"><span data-stu-id="7b440-156">To call base class methods from overridden implementations, cast to the base class `([baseclass]$this)` on invocation.</span></span>

```powershell
class childClass2 : baseClass
{
    [int]days()
    {
        return 3 * ([baseClass]$this).days()
    }
}

    [childClass2]::new().days() # return 301500
```

<span data-ttu-id="7b440-157">Todos os métodos do PowerShell são virtuais.</span><span class="sxs-lookup"><span data-stu-id="7b440-157">All PowerShell methods are virtual.</span></span> <span data-ttu-id="7b440-158">Você pode ocultar métodos não virtuais do .NET em uma subclasse usando a mesma sintaxe que você faz para uma substituição: declare métodos com o mesmo nome e assinatura.</span><span class="sxs-lookup"><span data-stu-id="7b440-158">You can hide non-virtual .NET methods in a subclass by using the same syntax as you do for an override: declare methods with same name and signature.</span></span>

```powershell
class MyIntList : system.collections.generic.list[int]
{
    # Add is final in system.collections.generic.list
    [void] Add([int]$arg)
    {
        ([system.collections.generic.list[int]]$this).Add($arg * 2)
    }
}

$list = [MyIntList]::new()
$list.Add(100)
$list[0] # return 200
```

### <a name="current-limitations-with-class-inheritance"></a><span data-ttu-id="7b440-159">Limitações atuais com herança de classe</span><span class="sxs-lookup"><span data-stu-id="7b440-159">Current limitations with class inheritance</span></span>

<span data-ttu-id="7b440-160">Uma limitação com herança de classe é que não há nenhuma sintaxe para declarar interfaces no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b440-160">A limitation with class inheritance is that there is no syntax to declare interfaces in PowerShell.</span></span>

## <a name="defining-custom-types-in-powershell"></a><span data-ttu-id="7b440-161">Definindo tipos personalizados no PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b440-161">Defining custom types in PowerShell</span></span>

<span data-ttu-id="7b440-162">O Windows PowerShell 5,0 introduziu vários elementos de linguagem.</span><span class="sxs-lookup"><span data-stu-id="7b440-162">Windows PowerShell 5.0 introduced several language elements.</span></span>

### <a name="class-keyword"></a><span data-ttu-id="7b440-163">Palavra-chave class</span><span class="sxs-lookup"><span data-stu-id="7b440-163">Class keyword</span></span>

<span data-ttu-id="7b440-164">Define uma nova classe.</span><span class="sxs-lookup"><span data-stu-id="7b440-164">Defines a new class.</span></span>
<span data-ttu-id="7b440-165">A `class` palavra-chave é um tipo true .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7b440-165">The `class` keyword is a true .NET Framework type.</span></span>
<span data-ttu-id="7b440-166">Os membros da classe são públicos.</span><span class="sxs-lookup"><span data-stu-id="7b440-166">Class members are public.</span></span>

```powershell
class MyClass
{
}
```

### <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="7b440-167">Palavra-chave Enum e enumerações</span><span class="sxs-lookup"><span data-stu-id="7b440-167">Enum keyword and enumerations</span></span>

<span data-ttu-id="7b440-168">O suporte para a `enum` palavra-chave foi adicionado e é uma alteração significativa.</span><span class="sxs-lookup"><span data-stu-id="7b440-168">Support for the `enum` keyword was added and is a breaking change.</span></span> <span data-ttu-id="7b440-169">O `enum` delimitador é atualmente uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="7b440-169">The `enum` delimiter is currently a newline.</span></span> <span data-ttu-id="7b440-170">Uma solução alternativa para aqueles que já estão usando `enum` é inserir um e comercial ( `&` ) antes da palavra.</span><span class="sxs-lookup"><span data-stu-id="7b440-170">A workaround for those who are already using `enum` is to insert an ampersand (`&`) before the word.</span></span> <span data-ttu-id="7b440-171">Limitações atuais: não é possível definir um enumerador em termos de si mesmo, mas você pode inicializar `enum` em termos de outro `enum` , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="7b440-171">Current limitations: you cannot define an enumerator in terms of itself, but you can initialize `enum` in terms of another `enum`, as shown in the following example:</span></span>

<span data-ttu-id="7b440-172">O tipo base não pode ser especificado no momento.</span><span class="sxs-lookup"><span data-stu-id="7b440-172">The base type cannot currently be specified.</span></span> <span data-ttu-id="7b440-173">O tipo base é sempre [int].</span><span class="sxs-lookup"><span data-stu-id="7b440-173">The base type is always [int].</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="7b440-174">Um valor de enumeração deve ser uma constante de tempo de análise.</span><span class="sxs-lookup"><span data-stu-id="7b440-174">An enumerator value must be a parse time constant.</span></span> <span data-ttu-id="7b440-175">O valor do enumerador não pode ser definido como o resultado de um comando invocado.</span><span class="sxs-lookup"><span data-stu-id="7b440-175">The enumerator value cannot be set to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="7b440-176">`Enum` dá suporte a operações aritméticas, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="7b440-176">`Enum` supports arithmetic operations, as shown in the following example:</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="hidden-keyword"></a><span data-ttu-id="7b440-177">Palavra-chave Hidden</span><span class="sxs-lookup"><span data-stu-id="7b440-177">Hidden keyword</span></span>

<span data-ttu-id="7b440-178">A `hidden` palavra-chave, introduzida no Windows PowerShell 5,0, oculta os membros da classe dos `Get-Member` resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="7b440-178">The `hidden` keyword, introduced in Windows PowerShell 5.0, hides class members from default `Get-Member` results.</span></span> <span data-ttu-id="7b440-179">Especifique a Propriedade Hidden, conforme mostrado na seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="7b440-179">Specify the hidden property as shown in the following line:</span></span>

```powershell
hidden [type] $classmember = <value>
```

<span data-ttu-id="7b440-180">Os membros ocultos não são exibidos usando o preenchimento com Tab ou o IntelliSense, a menos que a conclusão ocorra na classe que define o membro oculto.</span><span class="sxs-lookup"><span data-stu-id="7b440-180">Hidden members are not displayed by using tab completion or IntelliSense, unless the completion occurs in the class that defines the hidden member.</span></span>

<span data-ttu-id="7b440-181">Um novo atributo, **System. Management. Automation. hiddenattribute** , foi adicionado, para que o código C# possa ter a mesma semântica no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b440-181">A new attribute, **System.Management.Automation.HiddenAttribute** , was added, so that C# code can have the same semantics within PowerShell.</span></span>

<span data-ttu-id="7b440-182">Para obter mais informações, consulte [about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md).</span><span class="sxs-lookup"><span data-stu-id="7b440-182">For more information, see [about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md).</span></span>

### <a name="import-dscresource"></a><span data-ttu-id="7b440-183">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="7b440-183">Import-DscResource</span></span>

<span data-ttu-id="7b440-184">`Import-DscResource` agora é uma palavra-chave dinâmica real.</span><span class="sxs-lookup"><span data-stu-id="7b440-184">`Import-DscResource` is now a true dynamic keyword.</span></span> <span data-ttu-id="7b440-185">O PowerShell analisa o módulo raiz do módulo especificado pesquisando classes que contêm o atributo DscResource.</span><span class="sxs-lookup"><span data-stu-id="7b440-185">PowerShell parses the specified module's root module, searching for classes that contain the DscResource attribute.</span></span>

### <a name="properties"></a><span data-ttu-id="7b440-186">Propriedades</span><span class="sxs-lookup"><span data-stu-id="7b440-186">Properties</span></span>

<span data-ttu-id="7b440-187">Um novo campo, `ImplementingAssembly` , foi adicionado a `ModuleInfo` .</span><span class="sxs-lookup"><span data-stu-id="7b440-187">A new field, `ImplementingAssembly`, was added to `ModuleInfo`.</span></span> <span data-ttu-id="7b440-188">Se o script definir classes ou se o assembly carregado para módulos binários `ImplementingAssembly` for definido como o assembly dinâmico criado para um módulo de script.</span><span class="sxs-lookup"><span data-stu-id="7b440-188">If the script defines classes, or the loaded assembly for binary modules `ImplementingAssembly` is set to the dynamic assembly created for a script module.</span></span> <span data-ttu-id="7b440-189">Ele não é definido quando ModuleType = Manifest.</span><span class="sxs-lookup"><span data-stu-id="7b440-189">It is not set when ModuleType = Manifest.</span></span>

<span data-ttu-id="7b440-190">A reflexão no `ImplementingAssembly` campo descobre os recursos em um módulo.</span><span class="sxs-lookup"><span data-stu-id="7b440-190">Reflection on the `ImplementingAssembly` field discovers resources in a module.</span></span> <span data-ttu-id="7b440-191">Isso significa que é possível descobrir recursos escritos no PowerShell ou em outras linguagens gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="7b440-191">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

<span data-ttu-id="7b440-192">Campos com inicializadores.</span><span class="sxs-lookup"><span data-stu-id="7b440-192">Fields with initializers.</span></span>

`[int] $i = 5`

<span data-ttu-id="7b440-193">Static tem suporte e funciona como um atributo, semelhante às restrições de tipo, para que possa ser especificado em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="7b440-193">Static is supported and works like an attribute, similar to the type constraints, so it can be specified in any order.</span></span>

`static [int] $count = 0`

<span data-ttu-id="7b440-194">Um tipo é opcional.</span><span class="sxs-lookup"><span data-stu-id="7b440-194">A type is optional.</span></span>

`$s = "hello"`

<span data-ttu-id="7b440-195">Todos os membros são públicos.</span><span class="sxs-lookup"><span data-stu-id="7b440-195">All members are public.</span></span> <span data-ttu-id="7b440-196">As propriedades exigem uma nova linha ou um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="7b440-196">Properties require either a newline or semicolon.</span></span> <span data-ttu-id="7b440-197">Se nenhum tipo de objeto for especificado, o tipo de propriedade será **objeto** .</span><span class="sxs-lookup"><span data-stu-id="7b440-197">If no object type is specified, the property type is **Object** .</span></span>

### <a name="constructors-and-instantiation"></a><span data-ttu-id="7b440-198">Construtores e instanciação</span><span class="sxs-lookup"><span data-stu-id="7b440-198">Constructors and instantiation</span></span>

<span data-ttu-id="7b440-199">As classes do PowerShell podem ter construtores que têm o mesmo nome de sua classe.</span><span class="sxs-lookup"><span data-stu-id="7b440-199">PowerShell classes can have constructors that have the same name as their class.</span></span> <span data-ttu-id="7b440-200">Os construtores podem ser sobrecarregados.</span><span class="sxs-lookup"><span data-stu-id="7b440-200">Constructors can be overloaded.</span></span> <span data-ttu-id="7b440-201">Há suporte para construtores estáticos.</span><span class="sxs-lookup"><span data-stu-id="7b440-201">Static constructors are supported.</span></span>
<span data-ttu-id="7b440-202">As propriedades com expressões de inicialização são inicializadas antes da execução de qualquer código em um construtor.</span><span class="sxs-lookup"><span data-stu-id="7b440-202">Properties with initialization expressions are initialized before running any code in a constructor.</span></span> <span data-ttu-id="7b440-203">As propriedades estáticas são inicializadas antes do corpo de um construtor estático, e as propriedades de instância são inicializadas antes do corpo do construtor não estático.</span><span class="sxs-lookup"><span data-stu-id="7b440-203">Static properties are initialized before the body of a static constructor, and instance properties are initialized before the body of the non-static constructor.</span></span> <span data-ttu-id="7b440-204">Atualmente, não há nenhuma sintaxe para chamar um construtor de outro construtor, como a sintaxe C#: `": this()")` .</span><span class="sxs-lookup"><span data-stu-id="7b440-204">Currently, there is no syntax for calling a constructor from another constructor such as the C# syntax: `": this()")`.</span></span> <span data-ttu-id="7b440-205">A solução alternativa é definir um método comum de Init.</span><span class="sxs-lookup"><span data-stu-id="7b440-205">The workaround is to define a common Init method.</span></span>

<span data-ttu-id="7b440-206">Veja a seguir as maneiras de instanciar classes:</span><span class="sxs-lookup"><span data-stu-id="7b440-206">The following are ways of instantiating classes:</span></span>

- <span data-ttu-id="7b440-207">Criando uma instância usando o construtor padrão.</span><span class="sxs-lookup"><span data-stu-id="7b440-207">Instantiating by using the default constructor.</span></span> <span data-ttu-id="7b440-208">Observe que `New-Object` o não tem suporte nesta versão.</span><span class="sxs-lookup"><span data-stu-id="7b440-208">Note that `New-Object` is not supported in this release.</span></span>

  `$a = [MyClass]::new()`

- <span data-ttu-id="7b440-209">Chamando um construtor com um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7b440-209">Calling a constructor with a parameter.</span></span>

  `$b = [MyClass]::new(42)`

- <span data-ttu-id="7b440-210">Passando uma matriz para um construtor com vários parâmetros</span><span class="sxs-lookup"><span data-stu-id="7b440-210">Passing an array to a constructor with multiple parameters</span></span>

  `$c = [MyClass]::new(@(42,43,44), "Hello")`

<span data-ttu-id="7b440-211">Para esta versão, o nome do tipo só é visível lexicalmente, o que significa que ele não é visível fora do módulo ou script que define a classe.</span><span class="sxs-lookup"><span data-stu-id="7b440-211">For this release, the type name is only visible lexically, meaning it is not visible outside of the module or script that defines the class.</span></span> <span data-ttu-id="7b440-212">As funções podem retornar instâncias de uma classe definida no PowerShell, e as instâncias funcionam bem fora do módulo ou script.</span><span class="sxs-lookup"><span data-stu-id="7b440-212">Functions can return instances of a class defined in PowerShell, and instances work well outside of the module or script.</span></span>

<span data-ttu-id="7b440-213">O `Get-Member` parâmetro **estático** lista construtores, para que você possa exibir sobrecargas como qualquer outro método.</span><span class="sxs-lookup"><span data-stu-id="7b440-213">The `Get-Member` **Static** parameter lists constructors, so you can view overloads like any other method.</span></span> <span data-ttu-id="7b440-214">O desempenho dessa sintaxe também é consideravelmente mais rápido do que o de `New-Object`.</span><span class="sxs-lookup"><span data-stu-id="7b440-214">The performance of this syntax is also considerably faster than `New-Object`.</span></span>

<span data-ttu-id="7b440-215">O método pseudoestático chamado **new** funciona com tipos do .NET, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="7b440-215">The pseudo-static method named **new** works with .NET types, as shown in the following example.</span></span> `[hashtable]::new()`

<span data-ttu-id="7b440-216">Agora você pode ver as sobrecargas do construtor com `Get-Member` ou conforme mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="7b440-216">You can now see constructor overloads with `Get-Member`, or as shown in this example:</span></span>

```powershell
[hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

### <a name="methods"></a><span data-ttu-id="7b440-217">Métodos</span><span class="sxs-lookup"><span data-stu-id="7b440-217">Methods</span></span>

<span data-ttu-id="7b440-218">Um método de classe do PowerShell é implementado como um **ScriptBlock** que tem apenas um bloco end.</span><span class="sxs-lookup"><span data-stu-id="7b440-218">A PowerShell class method is implemented as a **ScriptBlock** that has only an end block.</span></span> <span data-ttu-id="7b440-219">Todos os métodos são públicos.</span><span class="sxs-lookup"><span data-stu-id="7b440-219">All methods are public.</span></span> <span data-ttu-id="7b440-220">Veja a seguir um exemplo de definição de um método chamado **DoSomething** .</span><span class="sxs-lookup"><span data-stu-id="7b440-220">The following shows an example of defining a method named **DoSomething** .</span></span>

```powershell
class MyClass
{
    DoSomething($x)
    {
        $this._doSomething($x)       # method syntax
    }
    private _doSomething($a) {}
}
```

### <a name="method-invocation"></a><span data-ttu-id="7b440-221">Invocação de método</span><span class="sxs-lookup"><span data-stu-id="7b440-221">Method invocation</span></span>

<span data-ttu-id="7b440-222">Há suporte para métodos sobrecarregados.</span><span class="sxs-lookup"><span data-stu-id="7b440-222">Overloaded methods are supported.</span></span> <span data-ttu-id="7b440-223">Os métodos sobrecarregados são nomeados da mesma forma que um método existente, mas diferenciados pelos valores especificados.</span><span class="sxs-lookup"><span data-stu-id="7b440-223">Overloaded methods are named the same as an existing method but differentiated by their specified values.</span></span>

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

### <a name="invocation"></a><span data-ttu-id="7b440-224">Invocação</span><span class="sxs-lookup"><span data-stu-id="7b440-224">Invocation</span></span>

<span data-ttu-id="7b440-225">Consulte [invocação de método](#method-invocation).</span><span class="sxs-lookup"><span data-stu-id="7b440-225">See [Method invocation](#method-invocation).</span></span>

### <a name="attributes"></a><span data-ttu-id="7b440-226">Atributos</span><span class="sxs-lookup"><span data-stu-id="7b440-226">Attributes</span></span>

<span data-ttu-id="7b440-227">Três novos atributos foram adicionados: `DscResource` , `DscResourceKey` e `DscResourceMandatory` .</span><span class="sxs-lookup"><span data-stu-id="7b440-227">Three new attributes were added: `DscResource`, `DscResourceKey`, and `DscResourceMandatory`.</span></span>

### <a name="return-types"></a><span data-ttu-id="7b440-228">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="7b440-228">Return types</span></span>

<span data-ttu-id="7b440-229">O tipo de retorno é um contrato.</span><span class="sxs-lookup"><span data-stu-id="7b440-229">Return type is a contract.</span></span> <span data-ttu-id="7b440-230">O valor retornado é convertido para o tipo esperado.</span><span class="sxs-lookup"><span data-stu-id="7b440-230">The return value is converted to the expected type.</span></span>
<span data-ttu-id="7b440-231">Se nenhum tipo de retorno for especificado, o tipo de retorno será nulo.</span><span class="sxs-lookup"><span data-stu-id="7b440-231">If no return type is specified, the return type is void.</span></span> <span data-ttu-id="7b440-232">Não há nenhum streaming de objetos e os objetos não podem ser gravados no pipeline intencionalmente ou por acidente.</span><span class="sxs-lookup"><span data-stu-id="7b440-232">There is no streaming of objects and objects cannot be written to the pipeline either intentionally or by accident.</span></span>

### <a name="lexical-scoping-of-variables"></a><span data-ttu-id="7b440-233">Escopo léxico de variáveis</span><span class="sxs-lookup"><span data-stu-id="7b440-233">Lexical scoping of variables</span></span>

<span data-ttu-id="7b440-234">Apresentamos a seguir um exemplo de como o escopo léxico funciona nesta versão.</span><span class="sxs-lookup"><span data-stu-id="7b440-234">The following shows an example of how lexical scoping works in this release.</span></span>

```powershell
$d = 42  # Script scope

function bar
{
    $d = 0  # Function scope
    [MyClass]::DoSomething()
}

class MyClass
{
    static [object] DoSomething()
    {
        return $d  # error, not found dynamically
        return $script:d # no error

        $d = $script:d
        return $d # no error, found lexically
    }
}

$v = bar
$v -eq $d # true
```

## <a name="example-create-custom-classes"></a><span data-ttu-id="7b440-235">Exemplo: criar classes personalizadas</span><span class="sxs-lookup"><span data-stu-id="7b440-235">Example: Create custom classes</span></span>

<span data-ttu-id="7b440-236">O exemplo a seguir cria várias classes personalizadas novas para implementar uma DSL (linguagem de folha de estilos dinâmica) HTML.</span><span class="sxs-lookup"><span data-stu-id="7b440-236">The following example creates several new, custom classes to implement an HTML Dynamic Stylesheet Language (DSL).</span></span> <span data-ttu-id="7b440-237">O exemplo adiciona funções auxiliares para criar tipos de elementos específicos como parte da classe de elemento, como estilos de título e tabelas, porque os tipos não podem ser usados fora do escopo de um módulo.</span><span class="sxs-lookup"><span data-stu-id="7b440-237">The example adds helper functions to create specific element types as part of the element class, such as heading styles and tables, because types cannot be used outside the scope of a module.</span></span>

```powershell
# Classes that define the structure of the document
#
class Html
{
    [string] $docType
    [HtmlHead] $Head
    [Element[]] $Body

    [string] Render()
    {
        $text = "<html>`n<head>`n"
        $text += $Head
        $text += "`n</head>`n<body>`n"
        $text += $Body -join "`n" # Render all of the body elements
        $text += "</body>`n</html>"
        return $text
    }
    [string] ToString() { return $this.Render() }
}

class HtmlHead
{
    $Title
    $Base
    $Link
    $Style
    $Meta
    $Script
    [string] Render() { return "<title>$Title</title>" }
    [string] ToString() { return $this.Render() }
}

class Element
{
    [string] $Tag
    [string] $Text
    [hashtable] $Attributes
    [string] Render() {
        $attributesText= ""
        if ($Attributes)
        {
            foreach ($attr in $Attributes.Keys)
            {
                $attributesText = " $attr=`"$($Attributes[$attr])`""
            }
        }

        return "<${tag}${attributesText}>$text</$tag>`n"
    }
    [string] ToString() { return $this.Render() }
}

#
# Helper functions for creating specific element types on top of the classes.
# These are required because types aren't visible outside of the module.
#
function H1 {[Element] @{Tag = "H1"; Text = $args.foreach{$_} -join " "}}
function H2 {[Element] @{Tag = "H2"; Text = $args.foreach{$_} -join " "}}
function H3 {[Element] @{Tag = "H3"; Text = $args.foreach{$_} -join " "}}
function P  {[Element] @{Tag = "P" ; Text = $args.foreach{$_} -join " "}}
function B  {[Element] @{Tag = "B" ; Text = $args.foreach{$_} -join " "}}
function I  {[Element] @{Tag = "I" ; Text = $args.foreach{$_} -join " "}}
function HREF
{
    param (
        $Name,
        $Link
    )

    return [Element] @{
        Tag = "A"
        Attributes = @{ HREF = $link }
        Text = $name
    }
}
function Table
{
    param (
        [Parameter(Mandatory)]
        [object[]]
            $Data,
        [Parameter()]
        [string[]]
            $Properties = "*",
        [Parameter()]
        [hashtable]
            $Attributes = @{ border=2; cellpadding=2; cellspacing=2 }
    )

    $bodyText = ""
    # Add the header tags
    $bodyText +=  $Properties.foreach{TH $_}
    # Add the rows
    $bodyText += foreach ($row in $Data)
                {
                            TR (-join $Properties.Foreach{ TD ($row.$_) } )
                }

    $table = [Element] @{
                Tag = "Table"
                Attributes = $Attributes
                Text = $bodyText
            }
    $table
}
function TH  {([Element] @{Tag="TH"; Text=$args.foreach{$_} -join " "})}
function TR  {([Element] @{Tag="TR"; Text=$args.foreach{$_} -join " "})}
function TD  {([Element] @{Tag="TD"; Text=$args.foreach{$_} -join " "})}

function Style
{
    return  [Element]  @{
        Tag = "style"
        Text = "$args"
    }
}

# Takes a hash table, casts it to and HTML document
# and then returns the resulting type.
#
function Html ([HTML] $doc) { return $doc }
```

## <a name="see-also"></a><span data-ttu-id="7b440-238">Confira também</span><span class="sxs-lookup"><span data-stu-id="7b440-238">See also</span></span>

[<span data-ttu-id="7b440-239">about_Enum</span><span class="sxs-lookup"><span data-stu-id="7b440-239">about_Enum</span></span>](../../Microsoft.PowerShell.Core/About/about_Enum.md)

[<span data-ttu-id="7b440-240">about_Hidden</span><span class="sxs-lookup"><span data-stu-id="7b440-240">about_Hidden</span></span>](../../Microsoft.PowerShell.Core/About/about_hidden.md)

[<span data-ttu-id="7b440-241">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="7b440-241">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="7b440-242">about_Methods</span><span class="sxs-lookup"><span data-stu-id="7b440-242">about_Methods</span></span>](../../Microsoft.PowerShell.Core/About/about_Methods.md)

[<span data-ttu-id="7b440-243">Criar recursos personalizados de configuração de estado desejado do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b440-243">Build Custom PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/authoringResource)
