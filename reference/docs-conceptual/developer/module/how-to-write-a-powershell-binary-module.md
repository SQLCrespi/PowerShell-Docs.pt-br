---
ms.date: 09/13/2016
ms.topic: reference
title: Como escrever um módulo binário do Windows PowerShell
description: Como escrever um módulo binário do Windows PowerShell
ms.openlocfilehash: 1d5cea474ac418f78cc782360b7c23b7614d6669
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92663069"
---
# <a name="how-to-write-a-powershell-binary-module"></a><span data-ttu-id="7694a-103">Como escrever um módulo binário do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7694a-103">How to Write a PowerShell Binary Module</span></span>

<span data-ttu-id="7694a-104">Um módulo binário pode ser qualquer assembly (. dll) que contenha classes de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7694a-104">A binary module can be any assembly (.dll) that contains cmdlet classes.</span></span> <span data-ttu-id="7694a-105">Por padrão, todos os cmdlets no assembly são importados quando o módulo binário é importado.</span><span class="sxs-lookup"><span data-stu-id="7694a-105">By default, all the cmdlets in the assembly are imported when the binary module is imported.</span></span> <span data-ttu-id="7694a-106">No entanto, você pode restringir os cmdlets que são importados criando um manifesto de módulo cujo módulo raiz é o assembly.</span><span class="sxs-lookup"><span data-stu-id="7694a-106">However, you can restrict the cmdlets that are imported by creating a module manifest whose root module is the assembly.</span></span> <span data-ttu-id="7694a-107">(Por exemplo, a chave CmdletsToExport do manifesto pode ser usada para exportar somente os cmdlets necessários.) Além disso, um módulo binário pode conter arquivos adicionais, uma estrutura de diretório e outras informações de gerenciamento úteis que um único cmdlet não pode.</span><span class="sxs-lookup"><span data-stu-id="7694a-107">(For example, the CmdletsToExport key of the manifest can be used to export only those cmdlets that are needed.) In addition, a binary module can contain additional files, a directory structure, and other pieces of useful management information that a single cmdlet cannot.</span></span>

<span data-ttu-id="7694a-108">O procedimento a seguir descreve como criar e instalar um módulo binário do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7694a-108">The following procedure describes how to create and install a PowerShell binary module.</span></span>

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a><span data-ttu-id="7694a-109">Como criar e instalar um módulo binário do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7694a-109">How to create and install a PowerShell binary module</span></span>

1. <span data-ttu-id="7694a-110">Crie uma solução binária do PowerShell (como um cmdlet escrito em C#), com os recursos necessários e certifique-se de que ela seja executada corretamente.</span><span class="sxs-lookup"><span data-stu-id="7694a-110">Create a binary PowerShell solution (such as a cmdlet written in C#), with the capabilities you need, and ensure that it runs properly.</span></span>

   <span data-ttu-id="7694a-111">De uma perspectiva de código, o núcleo de um módulo binário é simplesmente um assembly de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7694a-111">From a code perspective, the core of a binary module is simply a cmdlet assembly.</span></span> <span data-ttu-id="7694a-112">Na verdade, o PowerShell tratará um único assembly de cmdlet como um módulo, em termos de carregamento e descarregamento, sem esforço adicional por parte do desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="7694a-112">In fact, PowerShell will treat a single cmdlet assembly as a module, in terms of loading and unloading, with no additional effort on the part of the developer.</span></span> <span data-ttu-id="7694a-113">Para obter mais informações sobre como escrever um cmdlet, consulte [escrevendo um cmdlet do Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="7694a-113">For more information about writing a cmdlet, see [Writing a Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span></span>

2. <span data-ttu-id="7694a-114">Se necessário, crie o restante da sua solução: (cmdlets adicionais, arquivos XML e assim por diante) e descreva-os com um manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="7694a-114">If necessary, create the rest of your solution: (additional cmdlets, XML files, and so on) and describe them with a module manifest.</span></span>

   <span data-ttu-id="7694a-115">Além de descrever os assemblies de cmdlet em sua solução, um manifesto de módulo pode descrever como você deseja que seu módulo seja exportado e importado, quais cmdlets serão expostos e quais arquivos adicionais serão inseridos no módulo.</span><span class="sxs-lookup"><span data-stu-id="7694a-115">In addition to describing the cmdlet assemblies in your solution, a module manifest can describe how you want your module exported and imported, what cmdlets will be exposed, and what additional files will go into the module.</span></span>
   <span data-ttu-id="7694a-116">Como mencionado anteriormente, o PowerShell pode tratar um cmdlet binário como um módulo sem esforço adicional.</span><span class="sxs-lookup"><span data-stu-id="7694a-116">As stated previously however, PowerShell can treat a binary cmdlet like a module with no additional effort.</span></span>
   <span data-ttu-id="7694a-117">Dessa forma, um manifesto de módulo é útil principalmente para combinar vários arquivos em um único pacote ou para controlar explicitamente a publicação para um determinado assembly.</span><span class="sxs-lookup"><span data-stu-id="7694a-117">As such, a module manifest is useful mainly for combining multiple files into a single package, or for explicitly controlling publication for a given assembly.</span></span>
   <span data-ttu-id="7694a-118">Para obter mais informações, consulte [como escrever um manifesto de módulo do PowerShell](how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="7694a-118">For more information, see [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

   <span data-ttu-id="7694a-119">O código a seguir é um bloco de código C# extremamente simples que contém três cmdlets no mesmo arquivo que pode ser usado como um módulo.</span><span class="sxs-lookup"><span data-stu-id="7694a-119">The following code is an extremely simple C# code block that contains three cmdlets in the same file that can be used as a module.</span></span>

   ```csharp
   using System.Management.Automation;           // Windows PowerShell namespace.

   namespace ModuleCmdlets
   {
     [Cmdlet(VerbsDiagnostic.Test,"BinaryModuleCmdlet1")]
     public class TestBinaryModuleCmdlet1Command : Cmdlet
     {
       protected override void BeginProcessing()
       {
         WriteObject("BinaryModuleCmdlet1 exported by the ModuleCmdlets module.");
       }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet2")]
     public class TestBinaryModuleCmdlet2Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet2 exported by the ModuleCmdlets module.");
         }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet3")]
     public class TestBinaryModuleCmdlet3Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet3 exported by the ModuleCmdlets module.");
         }
     }

   }
   ```

3. <span data-ttu-id="7694a-120">Empacote sua solução e salve o pacote em algum lugar no caminho do módulo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7694a-120">Package your solution, and save the package to somewhere in the PowerShell module path.</span></span>

   <span data-ttu-id="7694a-121">A `PSModulePath` variável de ambiente global descreve os caminhos padrão que o PowerShell usará para localizar o módulo.</span><span class="sxs-lookup"><span data-stu-id="7694a-121">The `PSModulePath` global environment variable describes the default paths that PowerShell will use to locate your module.</span></span> <span data-ttu-id="7694a-122">Por exemplo, um caminho comum para salvar um módulo em um sistema seria `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>` .</span><span class="sxs-lookup"><span data-stu-id="7694a-122">For example, a common path to save a module on a system would be `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>`.</span></span> <span data-ttu-id="7694a-123">Se você não usar os caminhos padrão, será necessário declarar explicitamente o local do seu módulo durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="7694a-123">If you do not use the default paths, you will need to explicitly state the location of your module during installation.</span></span> <span data-ttu-id="7694a-124">Certifique-se de criar uma pasta na qual salvar o módulo, pois talvez seja necessário que a pasta armazene vários assemblies e arquivos para sua solução.</span><span class="sxs-lookup"><span data-stu-id="7694a-124">Be sure to create a folder to save your module in, as you may need the folder to store multiple assemblies and files for your solution.</span></span>

   <span data-ttu-id="7694a-125">Observe que, tecnicamente, não é necessário instalar seu módulo em qualquer lugar no `PSModulePath` -aqueles são simplesmente os locais padrão que o PowerShell procurará no seu módulo.</span><span class="sxs-lookup"><span data-stu-id="7694a-125">Note that technically you do not need to install your module anywhere on the `PSModulePath` - those are simply the default locations that PowerShell will look for your module.</span></span> <span data-ttu-id="7694a-126">No entanto, é considerado a prática recomendada fazer isso, a menos que você tenha um bom motivo para armazenar seu módulo em outro lugar.</span><span class="sxs-lookup"><span data-stu-id="7694a-126">However, it is considered best practice to do so, unless you have a good reason for storing your module somewhere else.</span></span> <span data-ttu-id="7694a-127">Para obter mais informações, consulte [instalando um módulo do PowerShell](./installing-a-powershell-module.md) e [modificando o caminho de instalação do módulo do PowerShell](./modifying-the-psmodulepath-installation-path.md).</span><span class="sxs-lookup"><span data-stu-id="7694a-127">For more information, see [Installing a PowerShell Module](./installing-a-powershell-module.md) and [Modifying the PowerShell Module Installation Path](./modifying-the-psmodulepath-installation-path.md).</span></span>

4. <span data-ttu-id="7694a-128">Importe seu módulo no PowerShell com uma chamada para [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span><span class="sxs-lookup"><span data-stu-id="7694a-128">Import your module into PowerShell with a call to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span></span>

   <span data-ttu-id="7694a-129">Chamar para [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) carregará seu módulo na memória ativa.</span><span class="sxs-lookup"><span data-stu-id="7694a-129">Calling to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) will load your module into active memory.</span></span> <span data-ttu-id="7694a-130">Se você estiver usando o PowerShell 3,0 e posterior, simplesmente chamar o nome do seu módulo no código também irá importá-lo; para obter mais informações, consulte [importando um módulo do PowerShell](./importing-a-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="7694a-130">If you are using PowerShell 3.0 and later, simply calling the name of your module in code will also import it; for more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="importing-snap-in-assemblies-as-modules"></a><span data-ttu-id="7694a-131">Importando assemblies de snap-in como módulos</span><span class="sxs-lookup"><span data-stu-id="7694a-131">Importing Snap-in Assemblies as Modules</span></span>

<span data-ttu-id="7694a-132">Os cmdlets e provedores que existem em assemblies de snap-in podem ser carregados como módulos binários.</span><span class="sxs-lookup"><span data-stu-id="7694a-132">Cmdlets and providers that exist in snap-in assemblies can be loaded as binary modules.</span></span> <span data-ttu-id="7694a-133">Quando os assemblies de snap-in são carregados como módulos binários, os cmdlets e provedores no snap-in estão disponíveis para o usuário, mas a classe de snap-in no assembly é ignorada e o snap-in não é registrado.</span><span class="sxs-lookup"><span data-stu-id="7694a-133">When the snap-in assemblies are loaded as binary modules, the cmdlets and providers in the snap-in are available to the user, but the snap-in class in the assembly is ignored, and the snap-in is not registered.</span></span> <span data-ttu-id="7694a-134">Como resultado, os cmdlets de snap-in fornecidos pelo Windows PowerShell não podem detectar o snap-in, embora os cmdlets e provedores estejam disponíveis para a sessão.</span><span class="sxs-lookup"><span data-stu-id="7694a-134">As a result, the snap-in cmdlets provided by Windows PowerShell cannot detect the snap-in even though the cmdlets and providers are available to the session.</span></span>

<span data-ttu-id="7694a-135">Além disso, todos os arquivos de formatação ou tipos que são referenciados pelo snap-in não podem ser importados como parte de um módulo binário.</span><span class="sxs-lookup"><span data-stu-id="7694a-135">In addition, any formatting or types files that are referenced by the snap-in cannot be imported as part of a binary module.</span></span>
<span data-ttu-id="7694a-136">Para importar os arquivos de formatação e tipos, você deve criar um manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="7694a-136">To import the formatting and types files you must create a module manifest.</span></span>
<span data-ttu-id="7694a-137">Consulte [como escrever um manifesto de módulo do PowerShell](how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="7694a-137">See, [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7694a-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7694a-138">See Also</span></span>

[<span data-ttu-id="7694a-139">Escrever um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7694a-139">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
