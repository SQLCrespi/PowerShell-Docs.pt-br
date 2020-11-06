---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Aplicar, obter e testar configurações em um nó
description: Este guia mostra como trabalhar com configurações em um nó de destino.
ms.openlocfilehash: 6bc9262bc0e2ce8eea7b85bd46ecc0c0a691276d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92651013"
---
# <a name="apply-get-and-test-configurations-on-a-node"></a><span data-ttu-id="0432f-104">Aplicar, obter e testar configurações em um nó</span><span class="sxs-lookup"><span data-stu-id="0432f-104">Apply, Get, and Test Configurations on a Node</span></span>

<span data-ttu-id="0432f-105">Este guia mostra como trabalhar com configurações em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="0432f-105">This guide will show you how to work with Configurations on a target Node.</span></span> <span data-ttu-id="0432f-106">Este guia é dividido nas seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="0432f-106">This guide is broken up into the following steps:</span></span>

## <a name="apply-a-configuration"></a><span data-ttu-id="0432f-107">Aplicar uma configuração</span><span class="sxs-lookup"><span data-stu-id="0432f-107">Apply a Configuration</span></span>

<span data-ttu-id="0432f-108">Para aplicar e gerenciar uma configuração, é necessário gerar um arquivo ".mof".</span><span class="sxs-lookup"><span data-stu-id="0432f-108">In order to apply and manage a Configuration, we need to generate a ".mof" file.</span></span> <span data-ttu-id="0432f-109">O código a seguir representará uma configuração simples a ser usada em todo este guia.</span><span class="sxs-lookup"><span data-stu-id="0432f-109">The following code will represent a simple Configuration that will be used throughout this guide.</span></span>

```powershell
Configuration Sample
{
    # This will generate two .mof files, a localhost.mof, and a server02.mof
    Node localhost, server02
    {
        File SampleFile
        {
            DestinationPath = 'C:\Temp\temp.txt'
            Contents = 'This is a simple resource to show Configuration functionality on a Node.'
        }
    }
}

# The -OutputPath parameter is built into every Configuration automatically.
# The value of -OutputPath determines where the .mof file should be stored, once compiled.
Sample -OutputPath "C:\Temp\"
```

<span data-ttu-id="0432f-110">Compilar essa configuração gerará dois arquivos ".mof".</span><span class="sxs-lookup"><span data-stu-id="0432f-110">Compiling this configuration will yield two ".mof" files.</span></span>

```Output
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a----       11/27/2018   7:29 AM     2.13KB localhost.mof
-a----       11/27/2018   7:29 AM     2.13KB server02.mof
```

<span data-ttu-id="0432f-111">Para aplicar uma configuração, use o cmdlet [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="0432f-111">To apply a Configuration, use the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="0432f-112">O parâmetro `-Path` especifica um diretório onde residem os arquivos ".mof".</span><span class="sxs-lookup"><span data-stu-id="0432f-112">The `-Path` parameter specifies a directory where ".mof" files reside.</span></span> <span data-ttu-id="0432f-113">Se nenhum `-Computername` for especificado, `Start-DSCConfiguration` tentará aplicar cada Configuração ao nome do computador especificado pelo nome do arquivo ".mof" (`<computername>.mof`).</span><span class="sxs-lookup"><span data-stu-id="0432f-113">If no `-Computername` is specified, `Start-DSCConfiguration` will attempt to apply each Configuration to the computer name specified by the name of the '.mof' file (`<computername>.mof`).</span></span> <span data-ttu-id="0432f-114">Especifique `-Verbose` como `Start-DSCConfiguration` para ver um resultado mais detalhado.</span><span class="sxs-lookup"><span data-stu-id="0432f-114">Specify `-Verbose` to `Start-DSCConfiguration` to see more verbose output.</span></span>

```powershell
Start-DSCConfiguration -Path C:\Temp\ -Verbose
```

<span data-ttu-id="0432f-115">Se `-Wait` não for especificado, você verá um trabalho criado.</span><span class="sxs-lookup"><span data-stu-id="0432f-115">If `-Wait` is not specified, you see one job created.</span></span> <span data-ttu-id="0432f-116">O trabalho criado terá um **ChildJob** para cada arquivo ".mof" processado por `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="0432f-116">The job created will have one **ChildJob** for each ".mof" file processed by `Start-DSCConfiguration`.</span></span>

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
45     Job45           Configuratio... Running       True            localhost,server02   Start-DSCConfiguration...
```

<span data-ttu-id="0432f-117">Se uma configuração está demorando muito e você deseja interrompê-la, use [Stop-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration) para interromper o aplicativo no nó local.</span><span class="sxs-lookup"><span data-stu-id="0432f-117">If a Configuration is taking a long time and you want to stop it, you can use [Stop-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration) to stop application on the local Node.</span></span>

```powershell
Stop-DSCConfiguration -Force
```

<span data-ttu-id="0432f-118">Uma vez concluído, você pode exibir o status dos trabalhos por meio do objeto de trabalho retornado por [Get-Job](/powershell/module/microsoft.powershell.core/get-job).</span><span class="sxs-lookup"><span data-stu-id="0432f-118">Once complete, you can view the status of the jobs through the job object returned by [Get-Job](/powershell/module/microsoft.powershell.core/get-job).</span></span>

```powershell
$job = Get-Job
$job.ChildJobs
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
49     Job49           Configuratio... Completed     True            localhost            Start-DSCConfiguration...
50     Job50           Configuratio... Completed     True            server02             Start-DSCConfiguration...
```

<span data-ttu-id="0432f-119">Para ver a saída **Verbose** , use os comandos a seguir para exibir o fluxo **Verbose** para cada **ChildJob**.</span><span class="sxs-lookup"><span data-stu-id="0432f-119">To see the **Verbose** output, use the following commands to view the **Verbose** stream for each **ChildJob**.</span></span> <span data-ttu-id="0432f-120">Para saber mais sobre trabalhos do PowerShell, confira [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).</span><span class="sxs-lookup"><span data-stu-id="0432f-120">For more about PowerShell jobs, see [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).</span></span>

```powershell
# View the verbose output of the localhost job using array indexing.
$job.ChildJobs[0].Verbose
```

```Output
Perform operation 'Invoke CimMethod' with following parameters, ''methodName' = SendConfigurationApply,
'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' = root/Microsoft/Windows/DesiredStateConfiguration'.
An LCM method call arrived from computer SERVER01 with user sid S-1-5-21-124525095-708259637-1543119021-1282804.
[SERVER01]: LCM:  [ Start  Set      ]
[SERVER01]: LCM:  [ Start  Resource ]  [[File]SampleFile]
[SERVER01]: LCM:  [ Start  Test     ]  [[File]SampleFile]
[SERVER01]:                            [[File]SampleFile] The destination object was found and no action is required.
[SERVER01]: LCM:  [ End    Test     ]  [[File]SampleFile]  in 0.0370 seconds.
[SERVER01]: LCM:  [ Skip   Set      ]  [[File]SampleFile]
[SERVER01]: LCM:  [ End    Resource ]  [[File]SampleFile]
[SERVER01]: LCM:  [ End    Set      ]
[SERVER01]: LCM:  [ End    Set      ]    in  0.2400 seconds.
Operation 'Invoke CimMethod' complete.
```

<span data-ttu-id="0432f-121">Começando no PowerShell 5.0, o parâmetro `-UseExisting` foi adicionado a `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="0432f-121">Beginning in PowerShell 5.0, the `-UseExisting` parameter was added to `Start-DSCConfiguration`.</span></span> <span data-ttu-id="0432f-122">Ao especificar `-UseExisting`, você instrui o cmdlet a usar a configuração aplicada existente ao invés de uma especificada pelo parâmetro `-Path`.</span><span class="sxs-lookup"><span data-stu-id="0432f-122">By specifying `-UseExisting`, you instruct the cmdlet to use the existing applied Configuration instead of one specified by the `-Path` parameter.</span></span>

```powershell
Start-DSCConfiguration -UseExisting -Verbose -Wait
```

## <a name="test-a-configuration"></a><span data-ttu-id="0432f-123">Testar uma configuração</span><span class="sxs-lookup"><span data-stu-id="0432f-123">Test a Configuration</span></span>

<span data-ttu-id="0432f-124">Você pode testar uma configuração aplicada atualmente usando [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0432f-124">You can test a currently applied Configuration using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span>
<span data-ttu-id="0432f-125">O `Test-DSCConfiguration` retornará `True` se o nó estiver em conformidade e `False` se não estiver.</span><span class="sxs-lookup"><span data-stu-id="0432f-125">`Test-DSCConfiguration` will return `True` if the Node is compliant, and `False` if it is not.</span></span>

```powershell
Test-DSCConfiguration
```

<span data-ttu-id="0432f-126">A partir do PowerShell 5.0, foi adicionado o parâmetro `-Detailed`, que retorna um objeto com coleções para **ResourcesInDesiredState** e **ResourcesNotInDesiredState**</span><span class="sxs-lookup"><span data-stu-id="0432f-126">Beginning in PowerShell 5.0, the `-Detailed` parameter was added which returns an object with collections for **ResourcesInDesiredState** and **ResourcesNotInDesiredState**</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

<span data-ttu-id="0432f-127">A partir do PowerShell 5.0, você pode testar uma configuração sem aplicá-la.</span><span class="sxs-lookup"><span data-stu-id="0432f-127">Beginning in PowerShell 5.0 you can test a Configuration without applying it.</span></span> <span data-ttu-id="0432f-128">O parâmetro `-ReferenceConfiguration` aceita o caminho de um arquivo ".mof" para testar o nó.</span><span class="sxs-lookup"><span data-stu-id="0432f-128">The `-ReferenceConfiguration` parameter accepts the path of a ".mof" file to test the Node against.</span></span> <span data-ttu-id="0432f-129">Nenhuma ação **Set** é executada em relação ao nó.</span><span class="sxs-lookup"><span data-stu-id="0432f-129">No **Set** actions are taken against the Node.</span></span> <span data-ttu-id="0432f-130">No PowerShell 4.0, há soluções alternativas para testar uma configuração sem aplicá-la, mas elas não são abordadas aqui.</span><span class="sxs-lookup"><span data-stu-id="0432f-130">In PowerShell 4.0, there are workarounds to test a Configuration without applying it, but they are not discussed here.</span></span>

## <a name="get-configuration-values"></a><span data-ttu-id="0432f-131">Obter valores de configuração</span><span class="sxs-lookup"><span data-stu-id="0432f-131">Get Configuration Values</span></span>

<span data-ttu-id="0432f-132">O cmdlet [Get-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) retorna os valores atuais de todos os recursos definidos na configuração aplicada no momento.</span><span class="sxs-lookup"><span data-stu-id="0432f-132">The [Get-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet returns the current values for any configured resources in the currently applied Configuration.</span></span>

```powershell
Get-DSCConfiguration
```

<span data-ttu-id="0432f-133">A saída da nossa configuração de exemplo terá esta aparência se for aplicada com êxito.</span><span class="sxs-lookup"><span data-stu-id="0432f-133">Output from our sample Configuration would look like this if applied successfully.</span></span>

```Output
ConfigurationName    : Sample
DependsOn            :
ModuleName           : PSDesiredStateConfiguration
ModuleVersion        :
PsDscRunAsCredential :
ResourceId           : [File]SampleFile
SourceInfo           :
Attributes           : {archive}
Checksum             :
Contents             :
CreatedDate          : 11/27/2018 7:16:06 AM
Credential           :
DestinationPath      : C:\Temp\temp.txt
Ensure               : present
Force                :
MatchSource          :
ModifiedDate         : 11/27/2018 7:16:06 AM
Recurse              :
Size                 : 75
SourcePath           :
SubItems             :
Type                 : file
PSComputerName       :
CimClassName         : MSFT_FileDirectoryConfiguration
```

## <a name="get-configuration-status"></a><span data-ttu-id="0432f-134">Obter status de configuração</span><span class="sxs-lookup"><span data-stu-id="0432f-134">Get Configuration Status</span></span>

<span data-ttu-id="0432f-135">A partir do PowerShell 5.0, o cmdlet [Get-DSCConfigurationStatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus) possibilita ver o histórico de configurações aplicadas ao nó.</span><span class="sxs-lookup"><span data-stu-id="0432f-135">Beginning in PowerShell 5.0 the [Get-DSCConfigurationStatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus) cmdlet allows you to see the history of applied Configurations to the node.</span></span> <span data-ttu-id="0432f-136">O DSC do PowerShell mantém o controle da última configuração de {{N}} aplicada no modo **Push** ou **Pull**.</span><span class="sxs-lookup"><span data-stu-id="0432f-136">PowerShell DSC keeps track of the last {{N}} Configurations applied in **Push** or **Pull** mode.</span></span> <span data-ttu-id="0432f-137">Isso inclui qualquer verificação de *consistência* executada pelo LCM.</span><span class="sxs-lookup"><span data-stu-id="0432f-137">This includes any *consistency* checks executed by the LCM.</span></span> <span data-ttu-id="0432f-138">Por padrão, `Get-DSCConfigurationStatus` mostra a última entrada do histórico.</span><span class="sxs-lookup"><span data-stu-id="0432f-138">By default, `Get-DSCConfigurationStatus` shows you the last history entry only.</span></span>

```powershell
Get-DSCConfigurationStatus
```

```Output
Status     StartDate                 Type            Mode  RebootRequested      NumberOfResources
------     ---------                 ----            ----  ---------------      -----------------
Success    11/27/2018 7:18:40 AM     Consistency     PUSH  False                1
```

<span data-ttu-id="0432f-139">Use o parâmetro `-All` para ver todo o histórico de Status de configuração.</span><span class="sxs-lookup"><span data-stu-id="0432f-139">Use the `-All` parameter to see all Configuration Status history.</span></span>

> [!NOTE]
> <span data-ttu-id="0432f-140">A saída é truncada para fins de brevidade.</span><span class="sxs-lookup"><span data-stu-id="0432f-140">Output is truncated for brevity.</span></span>

```powershell
Get-DSCConfigurationStatus -All
```

```Output
Status     StartDate                 Type            Mode  RebootRequested      NumberOfResources
------     ---------                 ----            ----  ---------------      -----------------
Success    11/27/2018 7:18:40 AM     Consistency     PUSH  False                1
Success    11/27/2018 7:16:06 AM     Initial         PUSH  False                1
Success    11/27/2018 7:04:53 AM     Initial         PUSH  False                1
Success    11/27/2018 7:03:45 AM     Consistency     PUSH  False                2
Success    11/27/2018 7:03:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:48:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:33:44 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:33:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:18:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:03:44 AM     Consistency     PUSH  False                2
```

## <a name="manage-configuration-documents"></a><span data-ttu-id="0432f-141">Gerenciar documentos de configuração</span><span class="sxs-lookup"><span data-stu-id="0432f-141">Manage Configuration Documents</span></span>

<span data-ttu-id="0432f-142">O LCM gerencia a configuração do nó trabalhando com **Documentos de configuração**.</span><span class="sxs-lookup"><span data-stu-id="0432f-142">The LCM manages the Configuration of the Node by working with **Configuration Documents**.</span></span> <span data-ttu-id="0432f-143">Esses arquivos ".mof" residem no diretório `C:\Windows\System32\Configuration`.</span><span class="sxs-lookup"><span data-stu-id="0432f-143">These ".mof" files reside in the `C:\Windows\System32\Configuration` directory.</span></span>

<span data-ttu-id="0432f-144">A partir do PowerShell 5.0, [Remove-DSCConfigurationDocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument) possibilita remover os arquivos ".mof" para interromper as verificações de consistência futuras ou remover uma configuração que gera erros quando aplicada.</span><span class="sxs-lookup"><span data-stu-id="0432f-144">Beginning in PowerShell 5.0 the [Remove-DSCConfigurationDocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument) allows you to remove the ".mof" files to stop future consistency checks or remove a Configuration that has errors when applied.</span></span> <span data-ttu-id="0432f-145">O parâmetro `-Stage` possibilita especificar o arquivo ".mof" que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="0432f-145">The `-Stage` parameter allows you to specify which ".mof" file you want to remove.</span></span>

```powershell
Remove-DSCConfigurationDocument -Stage Current
```

> [!NOTE]
> <span data-ttu-id="0432f-146">No PowerShell 4.0, você ainda pode remover esses arquivos ".mof" diretamente usando [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item).</span><span class="sxs-lookup"><span data-stu-id="0432f-146">In PowerShell 4.0, you can still remove these ".mof" files directly using [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item).</span></span>

## <a name="publish-configurations"></a><span data-ttu-id="0432f-147">Publicar configurações</span><span class="sxs-lookup"><span data-stu-id="0432f-147">Publish Configurations</span></span>

<span data-ttu-id="0432f-148">A partir do PowerShell 5.0, foi adicionado o cmdlet [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0432f-148">Beginning in PowerShell 5.0, the [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration) cmdlet was added.</span></span> <span data-ttu-id="0432f-149">Esse cmdlet permite publicar um arquivo ".mof" em computadores remotos sem aplicá-lo.</span><span class="sxs-lookup"><span data-stu-id="0432f-149">This cmdlet allows you to publish a ".mof" file to remote computers, without applying it.</span></span>

```powershell
Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

## <a name="see-also"></a><span data-ttu-id="0432f-150">Veja também</span><span class="sxs-lookup"><span data-stu-id="0432f-150">See also</span></span>

- [<span data-ttu-id="0432f-151">Obter, testar e definir</span><span class="sxs-lookup"><span data-stu-id="0432f-151">Get, Test, and Set</span></span>](../resources/get-test-set.md)
