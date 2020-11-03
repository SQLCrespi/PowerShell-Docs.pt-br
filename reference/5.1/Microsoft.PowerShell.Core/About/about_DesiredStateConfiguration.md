---
description: Fornece uma breve introdução ao recurso de configuração de estado desejado (DSC) do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_desiredstateconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_DesiredStateConfiguration
ms.openlocfilehash: 2f043104c67078b98355b3e54171a8993e534837
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196556"
---
# <a name="about_desiredstateconfiguration"></a><span data-ttu-id="ab493-104">about_DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="ab493-104">about_DesiredStateConfiguration</span></span>

## <a name="short-description"></a><span data-ttu-id="ab493-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="ab493-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="ab493-106">Fornece uma breve introdução ao recurso de configuração de estado desejado (DSC) do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab493-106">Provides a brief introduction to the PowerShell Desired State Configuration (DSC) feature.</span></span>

## <a name="long-description"></a><span data-ttu-id="ab493-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="ab493-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ab493-108">O DSC é uma plataforma de gerenciamento no PowerShell que permite a implantação e o gerenciamento de dados de configuração para serviços de software e o gerenciamento do ambiente no qual esses serviços são executados.</span><span class="sxs-lookup"><span data-stu-id="ab493-108">DSC is a management platform in PowerShell that enables deploying and managing configuration data for software services, and managing the environment in which these services run.</span></span>

<span data-ttu-id="ab493-109">A DSC fornece um conjunto de extensões de linguagem do PowerShell, novos cmdlets e recursos que você pode usar para especificar declarativamente como deseja que o estado do seu ambiente de software seja configurado.</span><span class="sxs-lookup"><span data-stu-id="ab493-109">DSC provides a set of PowerShell language extensions, new cmdlets, and resources that you can use to declaratively specify how you want the state of your software environment to be configured.</span></span> <span data-ttu-id="ab493-110">Também fornece um meio para manter e gerenciar as configurações existentes.</span><span class="sxs-lookup"><span data-stu-id="ab493-110">It also provides a means to maintain and manage existing configurations.</span></span>

<span data-ttu-id="ab493-111">A DSC é introduzida no PowerShell 4,0.</span><span class="sxs-lookup"><span data-stu-id="ab493-111">DSC is introduced in PowerShell 4.0.</span></span>

<span data-ttu-id="ab493-112">Para obter informações detalhadas sobre a DSC, consulte [visão geral da configuração de estado desejado do PowerShell](/powershell/scripting/dsc/overview/overview) na biblioteca do TechNet.</span><span class="sxs-lookup"><span data-stu-id="ab493-112">For detailed information about DSC, see [PowerShell Desired State Configuration Overview](/powershell/scripting/dsc/overview/overview) in the TechNet Library.</span></span>

## <a name="developing-dsc-resources-with-classes"></a><span data-ttu-id="ab493-113">DESENVOLVENDO RECURSOS DE DSC COM CLASSES</span><span class="sxs-lookup"><span data-stu-id="ab493-113">DEVELOPING DSC RESOURCES WITH CLASSES</span></span>

<span data-ttu-id="ab493-114">A partir do PowerShell 5,0, você pode desenvolver recursos de DSC usando classes.</span><span class="sxs-lookup"><span data-stu-id="ab493-114">Starting in PowerShell 5.0, you can develop DSC resources by using classes.</span></span>
<span data-ttu-id="ab493-115">Para obter mais informações, consulte [about_Classes](about_Classes.md)e [escrevendo um recurso personalizado de DSC com classes do PowerShell](/previous-versions//dn948461(v=technet.10)) no Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="ab493-115">For more information, see [about_Classes](about_Classes.md), and [Writing a custom DSC resource with PowerShell classes](/previous-versions//dn948461(v=technet.10)) on Microsoft TechNet.</span></span>

## <a name="using-dsc"></a><span data-ttu-id="ab493-116">USANDO O DSC</span><span class="sxs-lookup"><span data-stu-id="ab493-116">USING DSC</span></span>

<span data-ttu-id="ab493-117">Para usar a DSC para configurar seu ambiente, primeiro defina um bloco de script do PowerShell usando a palavra-chave Configuration, seguido por um identificador, que, por sua vez, é seguido pelo par de chaves que delimitam o bloco.</span><span class="sxs-lookup"><span data-stu-id="ab493-117">To use DSC to configure your environment, first define a PowerShell script block using the Configuration keyword, followed by an identifier, which is in turn followed by the pair of curly braces delimiting the block.</span></span> <span data-ttu-id="ab493-118">Dentro do bloco de configuração, você pode definir blocos de nós que especificam o estado de configuração desejado para cada nó (computador) no ambiente.</span><span class="sxs-lookup"><span data-stu-id="ab493-118">Inside the configuration block you can define node blocks that specify the desired configuration state for each node (computer) in the environment.</span></span> <span data-ttu-id="ab493-119">Um bloco de nó começa com a palavra-chave node, seguida pelo nome do computador de destino, que pode ser uma variável.</span><span class="sxs-lookup"><span data-stu-id="ab493-119">A node block starts with the Node keyword, followed by the name of the target computer, which can be a variable.</span></span> <span data-ttu-id="ab493-120">Depois do nome do computador, vêm as chaves que delimitam o bloco de nós.</span><span class="sxs-lookup"><span data-stu-id="ab493-120">After the computer name, come the curly braces that delimit the node block.</span></span> <span data-ttu-id="ab493-121">Dentro do bloco de nó, você pode definir blocos de recursos para configurar recursos específicos.</span><span class="sxs-lookup"><span data-stu-id="ab493-121">Inside the node block, you can define resource blocks to configure specific resources.</span></span> <span data-ttu-id="ab493-122">Um bloco de recursos começa com o nome do tipo do recurso, seguido pelo identificador que você deseja especificar para esse bloco, seguido pelas chaves que delimitam o bloco, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="ab493-122">A resource block starts with the type name of the resource, followed by the identifier you want to specify for that block, followed by the curly braces that delimit the block, as shown in the following example.</span></span>

```powershell
Configuration MyWebConfig {
    # Parameters are optional
    param ($MachineName, $WebsiteFilePath)
    # A Configuration block can have one or more Node blocks
    Node $MachineName
    {
        # Next, specify one or more resource blocks
        # WindowsFeature is one of the resources you can use in a Node block
        # This example ensures the Web Server (IIS) role is installed
        WindowsFeature IIS
        {
            # To ensure that the role is not installed, set Ensure to "Absent"
            Ensure = "Present"
            Name = "Web-Server" # Use the Name property from Get-WindowsFeature
        }

        # You can use the File resource to create files and folders
        # "WebDirectory" is the name you want to use to refer to this instance
        File WebDirectory
        {
            Ensure = "Present"  # You can also set Ensure to "Absent"
            Type = "Directory" # Default is "File"
            Recurse = $true
            SourcePath = $WebsiteFilePath
            DestinationPath = "C:\inetpub\wwwroot"

            # Ensure that the IIS block is successfully run first before
            # configuring this resource
            DependsOn = "[WindowsFeature]IIS"  # Use for dependencies
        }
    }
}
```

<span data-ttu-id="ab493-123">Para criar uma configuração, invoque o bloco de configuração da mesma forma que você invocaria uma função do PowerShell, passando quaisquer parâmetros esperados que você tenha definido (dois no exemplo acima).</span><span class="sxs-lookup"><span data-stu-id="ab493-123">To create a configuration, invoke the Configuration block the same way you would invoke a PowerShell function, passing in any expected parameters you may have defined (two in the example above).</span></span> <span data-ttu-id="ab493-124">Por exemplo, neste caso:</span><span class="sxs-lookup"><span data-stu-id="ab493-124">For example, in this case:</span></span>

```powershell
MyWebConfig -MachineName "TestMachine" -WebsiteFilePath `
  "\\filesrv\WebFiles" -OutputPath "C:\Windows\system32\temp"
# OutputPath is optional
```

<span data-ttu-id="ab493-125">Isso gera um arquivo MOF por nó no caminho que você especificar.</span><span class="sxs-lookup"><span data-stu-id="ab493-125">This generates a MOF file per node at the path you specify.</span></span> <span data-ttu-id="ab493-126">Esses arquivos MOF especificam a configuração desejada para cada nó.</span><span class="sxs-lookup"><span data-stu-id="ab493-126">These MOF files specify the desired configuration for each node.</span></span> <span data-ttu-id="ab493-127">Em seguida, use o cmdlet a seguir para analisar os arquivos MOF de configuração, enviar a cada nó sua configuração correspondente e aplicar essas configurações.</span><span class="sxs-lookup"><span data-stu-id="ab493-127">Next, use the following cmdlet to parse the configuration MOF files, send each node its corresponding configuration, and enact those configurations.</span></span> <span data-ttu-id="ab493-128">Observe que você não precisa criar um arquivo MOF separado para recursos de DSC baseados em classe.</span><span class="sxs-lookup"><span data-stu-id="ab493-128">Note that you do not need to create a separate MOF file for class-based DSC resources.</span></span>

```powershell
Start-DscConfiguration -Verbose -Wait -Path "C:\Windows\system32\temp"
```

## <a name="using-dsc-to-maintain-configuration-state"></a><span data-ttu-id="ab493-129">USANDO A DSC PARA MANTER O ESTADO DE CONFIGURAÇÃO</span><span class="sxs-lookup"><span data-stu-id="ab493-129">USING DSC TO MAINTAIN CONFIGURATION STATE</span></span>

<span data-ttu-id="ab493-130">Com a DSC, a configuração é idempotente.</span><span class="sxs-lookup"><span data-stu-id="ab493-130">With DSC, configuration is idempotent.</span></span> <span data-ttu-id="ab493-131">Isso significa que, se você usar a DSC para aplicar a mesma configuração mais de uma vez, o estado de configuração resultante sempre será o mesmo.</span><span class="sxs-lookup"><span data-stu-id="ab493-131">This means that if you use DSC to enact the same configuration more than once, the resulting configuration state will always be the same.</span></span> <span data-ttu-id="ab493-132">Por isso, se você suspeitar que qualquer nó em seu ambiente pode ter sido desfeito do estado desejado da configuração, você pode aplicar a mesma configuração de DSC novamente para trazê-las de volta para o estado desejado.</span><span class="sxs-lookup"><span data-stu-id="ab493-132">Because of this, if you suspect that any nodes in your environment may have drifted from the desired state of configuration, you can enact the same DSC configuration again to bring them back to the desired state.</span></span> <span data-ttu-id="ab493-133">Você não precisa modificar o script de configuração para endereçar apenas os recursos cujo estado foi desfeito do estado desejado.</span><span class="sxs-lookup"><span data-stu-id="ab493-133">You do not need to modify the configuration script to address only those resources whose state has drifted from the desired state.</span></span>

<span data-ttu-id="ab493-134">O exemplo a seguir mostra como você pode verificar se o estado real da configuração em um determinado nó foi descompasso da última configuração DSC aplicada no nó.</span><span class="sxs-lookup"><span data-stu-id="ab493-134">The following example shows how you can verify whether the actual state of configuration on a given node has drifted from the last DSC configuration enacted on the node.</span></span> <span data-ttu-id="ab493-135">Neste exemplo, verificamos a configuração do computador local.</span><span class="sxs-lookup"><span data-stu-id="ab493-135">In this example we are checking the configuration of the local computer.</span></span>

```powershell
$session = New-CimSession -ComputerName "localhost"
Test-DscConfiguration -CimSession $session
```

## <a name="built-in-dsc-resources"></a><span data-ttu-id="ab493-136">RECURSOS INTERNOS DE DSC</span><span class="sxs-lookup"><span data-stu-id="ab493-136">BUILT-IN DSC RESOURCES</span></span>

<span data-ttu-id="ab493-137">Você pode usar os seguintes recursos internos em seus scripts de configuração:</span><span class="sxs-lookup"><span data-stu-id="ab493-137">You can use the following built-in resources in your configuration scripts:</span></span>

|<span data-ttu-id="ab493-138">Name</span><span class="sxs-lookup"><span data-stu-id="ab493-138">Name</span></span>                  |<span data-ttu-id="ab493-139">Propriedades</span><span class="sxs-lookup"><span data-stu-id="ab493-139">Properties</span></span>                                         |
|----------------------|---------------------------------------------------|
|<span data-ttu-id="ab493-140">Arquivo</span><span class="sxs-lookup"><span data-stu-id="ab493-140">File</span></span>                  |<span data-ttu-id="ab493-141">{DestinationPath, Attributes, checksum, Content...}</span><span class="sxs-lookup"><span data-stu-id="ab493-141">{DestinationPath, Attributes, Checksum, Content...}</span></span>|
|<span data-ttu-id="ab493-142">Archive</span><span class="sxs-lookup"><span data-stu-id="ab493-142">Archive</span></span>               |<span data-ttu-id="ab493-143">{Destino, caminho, soma de verificação, credencial...}</span><span class="sxs-lookup"><span data-stu-id="ab493-143">{Destination, Path, Checksum, Credential...}</span></span>       |
|<span data-ttu-id="ab493-144">Ambiente</span><span class="sxs-lookup"><span data-stu-id="ab493-144">Environment</span></span>           |<span data-ttu-id="ab493-145">{Name, depende, verifique, caminho...}</span><span class="sxs-lookup"><span data-stu-id="ab493-145">{Name, DependsOn, Ensure, Path...}</span></span>                 |
|<span data-ttu-id="ab493-146">Grupo</span><span class="sxs-lookup"><span data-stu-id="ab493-146">Group</span></span>                 |<span data-ttu-id="ab493-147">{GroupName, Credential, depend, Description...}</span><span class="sxs-lookup"><span data-stu-id="ab493-147">{GroupName, Credential, DependsOn, Description...}</span></span> |
|<span data-ttu-id="ab493-148">Registro</span><span class="sxs-lookup"><span data-stu-id="ab493-148">Log</span></span>                   |<span data-ttu-id="ab493-149">{Mensagem, depende, PsDscRunAsCredential}</span><span class="sxs-lookup"><span data-stu-id="ab493-149">{Message, DependsOn, PsDscRunAsCredential}</span></span>         |
|<span data-ttu-id="ab493-150">Pacote</span><span class="sxs-lookup"><span data-stu-id="ab493-150">Package</span></span>               |<span data-ttu-id="ab493-151">{Name, Path, ProductId, Arguments...}</span><span class="sxs-lookup"><span data-stu-id="ab493-151">{Name, Path, ProductId, Arguments...}</span></span>              |
|<span data-ttu-id="ab493-152">Registro</span><span class="sxs-lookup"><span data-stu-id="ab493-152">Registry</span></span>              |<span data-ttu-id="ab493-153">{Key, valueName, depende, verifique...}</span><span class="sxs-lookup"><span data-stu-id="ab493-153">{Key, ValueName, DependsOn, Ensure...}</span></span>             |
|<span data-ttu-id="ab493-154">script</span><span class="sxs-lookup"><span data-stu-id="ab493-154">Script</span></span>                |<span data-ttu-id="ab493-155">{GetScript, setscript, TestScript, credencial...}</span><span class="sxs-lookup"><span data-stu-id="ab493-155">{GetScript, SetScript, TestScript, Credential...}</span></span>  |
|<span data-ttu-id="ab493-156">Serviço</span><span class="sxs-lookup"><span data-stu-id="ab493-156">Service</span></span>               |<span data-ttu-id="ab493-157">{Nome, BuiltInAccount, credencial, dependências...}</span><span class="sxs-lookup"><span data-stu-id="ab493-157">{Name, BuiltInAccount, Credential, Dependencies...}</span></span>|
|<span data-ttu-id="ab493-158">Usuário</span><span class="sxs-lookup"><span data-stu-id="ab493-158">User</span></span>                  |<span data-ttu-id="ab493-159">{Nome de usuário, depende, descrição, desabilitado...}</span><span class="sxs-lookup"><span data-stu-id="ab493-159">{UserName, DependsOn, Description, Disabled...}</span></span>    |
|<span data-ttu-id="ab493-160">WaitForAll</span><span class="sxs-lookup"><span data-stu-id="ab493-160">WaitForAll</span></span>            |<span data-ttu-id="ab493-161">{NodeName, resourceName, dependo, PsDscRunAsC...}</span><span class="sxs-lookup"><span data-stu-id="ab493-161">{NodeName, ResourceName, DependsOn, PsDscRunAsC...}</span></span>|
|<span data-ttu-id="ab493-162">WaitForAny</span><span class="sxs-lookup"><span data-stu-id="ab493-162">WaitForAny</span></span>            |<span data-ttu-id="ab493-163">{NodeName, resourceName, dependo, PsDscRunAsC...}</span><span class="sxs-lookup"><span data-stu-id="ab493-163">{NodeName, ResourceName, DependsOn, PsDscRunAsC...}</span></span>|
|<span data-ttu-id="ab493-164">WaitForSome</span><span class="sxs-lookup"><span data-stu-id="ab493-164">WaitForSome</span></span>           |<span data-ttu-id="ab493-165">{NodeCount, NodeName, resourceName, depende...}</span><span class="sxs-lookup"><span data-stu-id="ab493-165">{NodeCount, NodeName, ResourceName, DependsOn...}</span></span>  |
|<span data-ttu-id="ab493-166">WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="ab493-166">WindowsFeature</span></span>        |<span data-ttu-id="ab493-167">{Nome, credencial, depende, garantir...}</span><span class="sxs-lookup"><span data-stu-id="ab493-167">{Name, Credential, DependsOn, Ensure...}</span></span>           |
|<span data-ttu-id="ab493-168">WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="ab493-168">WindowsOptionalFeature</span></span>|<span data-ttu-id="ab493-169">{Name, depende, verifique, LogLevel...}</span><span class="sxs-lookup"><span data-stu-id="ab493-169">{Name, DependsOn, Ensure, LogLevel...}</span></span>             |
|<span data-ttu-id="ab493-170">WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="ab493-170">WindowsProcess</span></span>        |<span data-ttu-id="ab493-171">{Argumentos, caminho, credencial, depende...}</span><span class="sxs-lookup"><span data-stu-id="ab493-171">{Arguments, Path, Credential, DependsOn...}</span></span>        |

<span data-ttu-id="ab493-172">Para obter uma lista de recursos de DSC disponíveis no seu sistema, execute o `Get-DscResource` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ab493-172">To get a list of available DSC resources on your system, run the `Get-DscResource` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="ab493-173">Nas versões do PowerShell antes de 7.0, `Get-DscResource` não encontra recursos de DSC baseados em classe.</span><span class="sxs-lookup"><span data-stu-id="ab493-173">In PowerShell versions below 7.0, `Get-DscResource` does not find Class based DSC resources.</span></span>

<span data-ttu-id="ab493-174">O exemplo neste tópico demonstra como usar os recursos File e WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="ab493-174">The example in this topic demonstrates how to use the File and WindowsFeature resources.</span></span> <span data-ttu-id="ab493-175">Para ver todas as propriedades que você pode usar com um recurso, insira o cursor na palavra-chave Resource (por exemplo, File) em seu script de configuração no ISE do <kbd>CTRL</kbd>PowerShell, mantenha a + <kbd>barra de espaços</kbd> CTRL</span><span class="sxs-lookup"><span data-stu-id="ab493-175">To see all properties that you can use with a resource, insert the cursor in the resource keyword (for example, File) within your configuration script in PowerShell ISE, hold down <kbd>CTRL</kbd>+<kbd>SPACEBAR</kbd></span></span>

## <a name="find-more-resources"></a><span data-ttu-id="ab493-176">ENCONTRAR MAIS RECURSOS</span><span class="sxs-lookup"><span data-stu-id="ab493-176">FIND MORE RESOURCES</span></span>

<span data-ttu-id="ab493-177">Você pode baixar, instalar e aprender sobre muitos outros recursos de DSC disponíveis que foram criados pela comunidade de usuários do PowerShell e do DSC e pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ab493-177">You can download, install, and learn about many other available DSC resources that have been created by the PowerShell and DSC user community, and by Microsoft.</span></span> <span data-ttu-id="ab493-178">Visite a [Galeria do PowerShell](https://www.powershellgallery.com/) para procurar e saber mais sobre os recursos de DSC disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ab493-178">Visit the [PowerShell Gallery](https://www.powershellgallery.com/) to browse and learn about available DSC resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab493-179">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="ab493-179">SEE ALSO</span></span>

[<span data-ttu-id="ab493-180">Visão geral da configuração de estado desejado do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab493-180">PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="ab493-181">Recursos internos de configuração de estado desejado do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab493-181">Built-In PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/resources)

[<span data-ttu-id="ab493-182">Criar recursos personalizados de configuração de estado desejado do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab493-182">Build Custom PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/authoringResource)
