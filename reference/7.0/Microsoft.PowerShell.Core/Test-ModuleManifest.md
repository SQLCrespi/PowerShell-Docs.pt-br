---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-modulemanifest?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ModuleManifest
ms.openlocfilehash: 41b5ef4471ec2bef0bf4b30f8996f2e0010eceff
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192774"
---
# <span data-ttu-id="4c31c-103">Test-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="4c31c-103">Test-ModuleManifest</span></span>

## <span data-ttu-id="4c31c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4c31c-104">SYNOPSIS</span></span>
<span data-ttu-id="4c31c-105">Verifica se um arquivo de manifesto de módulo descreve com precisão o conteúdo de um módulo.</span><span class="sxs-lookup"><span data-stu-id="4c31c-105">Verifies that a module manifest file accurately describes the contents of a module.</span></span>

## <span data-ttu-id="4c31c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4c31c-106">SYNTAX</span></span>

```
Test-ModuleManifest [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="4c31c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4c31c-107">DESCRIPTION</span></span>

<span data-ttu-id="4c31c-108">O cmdlet **Test-ModuleManifest** verifica se os arquivos listados no arquivo de manifesto do módulo (. psd1) estão na verdade nos caminhos especificados.</span><span class="sxs-lookup"><span data-stu-id="4c31c-108">The **Test-ModuleManifest** cmdlet verifies that the files that are listed in the module manifest (.psd1) file are actually in the specified paths.</span></span>

<span data-ttu-id="4c31c-109">Este cmdlet é projetado para ajudar os autores de módulo a testar seus arquivos de manifesto.</span><span class="sxs-lookup"><span data-stu-id="4c31c-109">This cmdlet is designed to help module authors test their manifest files.</span></span>
<span data-ttu-id="4c31c-110">Os usuários do módulo também podem usar esse cmdlet em scripts e comandos para detectar erros antes de executarem scripts que dependem do módulo.</span><span class="sxs-lookup"><span data-stu-id="4c31c-110">Module users can also use this cmdlet in scripts and commands to detect errors before they run scripts that depend on the module.</span></span>

<span data-ttu-id="4c31c-111">**Test-ModuleManifest** retorna um objeto que representa o módulo.</span><span class="sxs-lookup"><span data-stu-id="4c31c-111">**Test-ModuleManifest** returns an object that represents the module.</span></span>
<span data-ttu-id="4c31c-112">Esse é o mesmo tipo de objeto que Get-Module retorna.</span><span class="sxs-lookup"><span data-stu-id="4c31c-112">This is the same type of object that Get-Module returns.</span></span>
<span data-ttu-id="4c31c-113">Se algum arquivo não estiver nos locais especificados no manifesto, o cmdlet também gera um erro para cada arquivo faltante.</span><span class="sxs-lookup"><span data-stu-id="4c31c-113">If any files are not in the locations specified in the manifest, the cmdlet also generates an error for each missing file.</span></span>

## <span data-ttu-id="4c31c-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4c31c-114">EXAMPLES</span></span>

### <span data-ttu-id="4c31c-115">Exemplo 1: testar um manifesto</span><span class="sxs-lookup"><span data-stu-id="4c31c-115">Example 1: Test a manifest</span></span>

```powershell
test-ModuleManifest -Path "$pshome\Modules\TestModule.psd1"
```

<span data-ttu-id="4c31c-116">Este comando testa o manifesto de módulo TestModule.psd1.</span><span class="sxs-lookup"><span data-stu-id="4c31c-116">This command tests the TestModule.psd1 module manifest.</span></span>

### <span data-ttu-id="4c31c-117">Exemplo 2: testar um manifesto usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="4c31c-117">Example 2: Test a manifest by using the pipeline</span></span>

```powershell
"$pshome\Modules\TestModule.psd1" | test-modulemanifest
```

```Output
Test-ModuleManifest : The specified type data file 'C:\Windows\System32\Wi
ndowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml' could not be processed because the file was not found. Please correct the path and try again.
At line:1 char:34
+ "$pshome\Modules\TestModule.psd1" | test-modulemanifest <<<<
+ CategoryInfo          : ResourceUnavailable: (C:\Windows\System32\WindowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml:String) [Test-ModuleManifest], FileNotFoundException
+ FullyQualifiedErrorId : Modules_TypeDataFileNotFound,Microsoft.PowerShell.Commands.TestModuleManifestCommandName

Name              : TestModule
Path              : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule\TestModule.psd1
Description       :
Guid              : 6f0f1387-cd25-4902-b7b4-22cff6aefa7b
Version           : 1.0
ModuleBase        : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule
ModuleType        : Manifest
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {}
ExportedVariables : {}
NestedModules     : {}
```

<span data-ttu-id="4c31c-118">Esse comando usa um operador de pipeline (|) para enviar uma cadeia de caracteres de caminho para **Test-ModuleManifest** .</span><span class="sxs-lookup"><span data-stu-id="4c31c-118">This command uses a pipeline operator (|) to send a path string to **Test-ModuleManifest** .</span></span>

<span data-ttu-id="4c31c-119">A saída do comando mostra que o teste falhou, porque o arquivo TestTypes.ps1xml, que estava listado no manifesto, não foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="4c31c-119">The command output shows that the test failed, because the TestTypes.ps1xml file, which was listed in the manifest, was not found.</span></span>

### <span data-ttu-id="4c31c-120">Exemplo 3: escrever uma função para testar um manifesto de módulo</span><span class="sxs-lookup"><span data-stu-id="4c31c-120">Example 3: Write a function to test a module manifest</span></span>

```powershell
function Test-ManifestBool ($path)
```

```Output
{$a = dir $path | Test-ModuleManifest -ErrorAction SilentlyContinue; $?}
```

<span data-ttu-id="4c31c-121">Essa função é como **Test-ModuleManifest** , mas retorna um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="4c31c-121">This function is like **Test-ModuleManifest** , but it returns a Boolean value.</span></span>
<span data-ttu-id="4c31c-122">A função retornará $True se o manifesto tiver passado o teste e $False caso contrário.</span><span class="sxs-lookup"><span data-stu-id="4c31c-122">The function returns $True if the manifest passed the test and $False otherwise.</span></span>

<span data-ttu-id="4c31c-123">A função usa o cmdlet Get-ChildItem, alias = dir, para obter o manifesto do módulo especificado pela variável $path.</span><span class="sxs-lookup"><span data-stu-id="4c31c-123">The function uses the Get-ChildItem cmdlet, alias = dir, to get the module manifest specified by the $path variable.</span></span>
<span data-ttu-id="4c31c-124">O comando usa um operador de pipeline (|) para passar o objeto de arquivo para **Test-ModuleManifest** .</span><span class="sxs-lookup"><span data-stu-id="4c31c-124">The command uses a pipeline operator (|) to pass the file object to **Test-ModuleManifest** .</span></span>

<span data-ttu-id="4c31c-125">**Test-ModuleManifest** usa o parâmetro de *erro* comum com um valor de SilentlyContinue para suprimir a exibição de quaisquer erros gerados pelo comando.</span><span class="sxs-lookup"><span data-stu-id="4c31c-125">**Test-ModuleManifest** uses the *ErrorAction* common parameter with a value of SilentlyContinue to suppress the display of any errors that the command generates.</span></span>
<span data-ttu-id="4c31c-126">Ele também salva o objeto **PSModuleInfo** que **Test-ModuleManifest** retorna na variável $a.</span><span class="sxs-lookup"><span data-stu-id="4c31c-126">It also saves the **PSModuleInfo** object that **Test-ModuleManifest** returns in the $a variable.</span></span>
<span data-ttu-id="4c31c-127">Portanto, o objeto não é exibido.</span><span class="sxs-lookup"><span data-stu-id="4c31c-127">Therefore, the object is not displayed.</span></span>

<span data-ttu-id="4c31c-128">Em seguida, em um comando separado, a função exibe o valor de $?</span><span class="sxs-lookup"><span data-stu-id="4c31c-128">Then, in a separate command, the function displays the value of the $?</span></span>
<span data-ttu-id="4c31c-129">variável automática.</span><span class="sxs-lookup"><span data-stu-id="4c31c-129">automatic variable.</span></span>
<span data-ttu-id="4c31c-130">Se o comando anterior não gerar nenhum erro, o comando exibirá $True e $False caso contrário.</span><span class="sxs-lookup"><span data-stu-id="4c31c-130">If the previous command generates no error, the command displays $True, and $False otherwise.</span></span>

<span data-ttu-id="4c31c-131">Você pode usar essa função em instruções condicionais, como aquelas que podem preceder um comando **Import-Module** ou um comando que usa o módulo.</span><span class="sxs-lookup"><span data-stu-id="4c31c-131">You can use this function in conditional statements, such as those that might precede an **Import-Module** command or a command that uses the module.</span></span>

## <span data-ttu-id="4c31c-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4c31c-132">PARAMETERS</span></span>

### <span data-ttu-id="4c31c-133">-Path</span><span class="sxs-lookup"><span data-stu-id="4c31c-133">-Path</span></span>

<span data-ttu-id="4c31c-134">Especifica um caminho e um nome de arquivo para o arquivo de manifesto.</span><span class="sxs-lookup"><span data-stu-id="4c31c-134">Specifies a path and file name for the manifest file.</span></span>
<span data-ttu-id="4c31c-135">Insira um caminho opcional e o nome do arquivo de manifesto de módulo que tem a extensão de nome de arquivo. psd1.</span><span class="sxs-lookup"><span data-stu-id="4c31c-135">Enter an optional path and name of the module manifest file that has the .psd1 file name extension.</span></span>
<span data-ttu-id="4c31c-136">O local padrão é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="4c31c-136">The default location is the current directory.</span></span>
<span data-ttu-id="4c31c-137">Os caracteres curinga têm suporte, mas devem ser resolvidos para um único arquivo de manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="4c31c-137">Wildcard characters are supported, but must resolve to a single module manifest file.</span></span>
<span data-ttu-id="4c31c-138">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="4c31c-138">This parameter is required.</span></span>
<span data-ttu-id="4c31c-139">Você também pode canalizar um caminho para **Test-ModuleManifest** .</span><span class="sxs-lookup"><span data-stu-id="4c31c-139">You can also pipe a path to **Test-ModuleManifest** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="4c31c-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4c31c-140">CommonParameters</span></span>

<span data-ttu-id="4c31c-141">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4c31c-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4c31c-142">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4c31c-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4c31c-143">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4c31c-143">INPUTS</span></span>

### <span data-ttu-id="4c31c-144">System.String</span><span class="sxs-lookup"><span data-stu-id="4c31c-144">System.String</span></span>

<span data-ttu-id="4c31c-145">É possível canalizar o caminho para um manifesto de módulo para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4c31c-145">You can pipe the path to a module manifest to this cmdlet.</span></span>

## <span data-ttu-id="4c31c-146">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4c31c-146">OUTPUTS</span></span>

### <span data-ttu-id="4c31c-147">System. Management. Automation. PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="4c31c-147">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="4c31c-148">Esse cmdlet retorna um objeto **PSModuleInfo** que representa o módulo.</span><span class="sxs-lookup"><span data-stu-id="4c31c-148">This cmdlet returns a **PSModuleInfo** object that represents the module.</span></span>
<span data-ttu-id="4c31c-149">Ele retornará este objeto mesmo se o manifesto apresentar erros.</span><span class="sxs-lookup"><span data-stu-id="4c31c-149">It returns this object even if the manifest has errors.</span></span>

## <span data-ttu-id="4c31c-150">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4c31c-150">NOTES</span></span>

## <span data-ttu-id="4c31c-151">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4c31c-151">RELATED LINKS</span></span>

[<span data-ttu-id="4c31c-152">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="4c31c-152">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="4c31c-153">Get-Module</span><span class="sxs-lookup"><span data-stu-id="4c31c-153">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="4c31c-154">Import-Module</span><span class="sxs-lookup"><span data-stu-id="4c31c-154">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="4c31c-155">New-Module</span><span class="sxs-lookup"><span data-stu-id="4c31c-155">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="4c31c-156">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="4c31c-156">New-ModuleManifest</span></span>](New-ModuleManifest.md)

[<span data-ttu-id="4c31c-157">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="4c31c-157">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="4c31c-158">about_Modules</span><span class="sxs-lookup"><span data-stu-id="4c31c-158">about_Modules</span></span>](About/about_Modules.md)
