---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Get-Test-Set
ms.openlocfilehash: bf409f71c07c434fbc7389789e16575868d21b42
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "78278403"
---
# <a name="get-test-set"></a><span data-ttu-id="29bf9-103">Get-Test-Set</span><span class="sxs-lookup"><span data-stu-id="29bf9-103">Get-Test-Set</span></span>

><span data-ttu-id="29bf9-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="29bf9-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

![Obter, testar e definir](media/get-test-set/get-test-set.png)

<span data-ttu-id="29bf9-106">O PowerShell Desired State Configuration é construído ao redor de um processo **Get**, **Test** e **Set**.</span><span class="sxs-lookup"><span data-stu-id="29bf9-106">PowerShell Desired State Configuration is constructed around a **Get**, **Test**, and **Set** process.</span></span> <span data-ttu-id="29bf9-107">Os [recursos](resources.md) do DSC contêm métodos para concluir cada uma dessas operações.</span><span class="sxs-lookup"><span data-stu-id="29bf9-107">DSC [resources](resources.md) each contains methods to complete each of these operations.</span></span> <span data-ttu-id="29bf9-108">Em [Configuração](../configurations/configurations.md), você define os blocos de recursos para preencher as chaves que se tornam parâmetros para os métodos **Get**, **Test** e **Set** de recursos.</span><span class="sxs-lookup"><span data-stu-id="29bf9-108">In a [Configuration](../configurations/configurations.md), you define resource blocks to fill in keys that become parameters for a resource's **Get**, **Test**, and **Set** methods.</span></span>

<span data-ttu-id="29bf9-109">Esta é a sintaxe para um bloco de recurso de **Serviço**.</span><span class="sxs-lookup"><span data-stu-id="29bf9-109">This is the syntax for a **Service** resource block.</span></span> <span data-ttu-id="29bf9-110">O recurso **Serviço** configura os serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="29bf9-110">The **Service** resource configures Windows services.</span></span>

```syntax
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

<span data-ttu-id="29bf9-111">Os métodos **Get**, **Test** e **Set** do recurso **Serviço** terão blocos de parâmetro que aceitam esses valores.</span><span class="sxs-lookup"><span data-stu-id="29bf9-111">The **Get**, **Test**, and **Set** methods of the **Service** resource will have parameter blocks that accept these values.</span></span>

```powershell
    param
    (
        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [System.String]
        $Name,

        [System.String]
        [ValidateSet("Automatic", "Manual", "Disabled")]
        $StartupType,

        [System.String]
        [ValidateSet("LocalSystem", "LocalService", "NetworkService")]
        $BuiltInAccount,

        [System.Management.Automation.PSCredential]
        [ValidateNotNull()]
        $Credential,

        [System.String]
        [ValidateSet("Running", "Stopped")]
        $State="Running",

        [System.String]
        [ValidateNotNullOrEmpty()]
        $DisplayName,

        [System.String]
        [ValidateNotNullOrEmpty()]
        $Description,

        [System.String]
        [ValidateNotNullOrEmpty()]
        $Path,

        [System.String[]]
        [ValidateNotNullOrEmpty()]
        $Dependencies,

        [System.String]
        [ValidateSet("Present", "Absent")]
        $Ensure="Present"
    )
```

> [!NOTE]
> <span data-ttu-id="29bf9-112">O idioma e o método usados para definir o recurso determinam como os métodos **Get**, **Test** e **Set** serão definidos.</span><span class="sxs-lookup"><span data-stu-id="29bf9-112">The language and method used to define the resource determines how the **Get**, **Test**, and **Set** methods will be defined.</span></span>

<span data-ttu-id="29bf9-113">Como o recurso **Serviço** só tem uma chave necessária (`Name`), um recurso de bloco de **Serviço** pode ser tão simples quanto isso:</span><span class="sxs-lookup"><span data-stu-id="29bf9-113">Because the **Service** resource only has one required key (`Name`), a **Service** block resource could be as simple as this:</span></span>

```powershell
Configuration TestConfig
{
    Import-DSCResource -Name Service
    Node localhost
    {
        Service "MyService"
        {
            Name = "Spooler"
        }
    }
}
```

<span data-ttu-id="29bf9-114">Ao compilar a Configuração acima, os valores especificados para uma chave são armazenados no arquivo ".mof" gerado.</span><span class="sxs-lookup"><span data-stu-id="29bf9-114">When you compile the Configuration above, the values you specify for a key are stored in the ".mof" file that is generated.</span></span> <span data-ttu-id="29bf9-115">Para saber mais, confira [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="29bf9-115">For more information, see [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>

```
instance of MSFT_ServiceResource as $MSFT_ServiceResource1ref
{
SourceInfo = "::5::1::Service";
 ModuleName = "PsDesiredStateConfiguration";
 ResourceID = "[Service]MyService";
 Name = "Spooler";

ModuleVersion = "1.0";

 ConfigurationName = "Test";

};
```

<span data-ttu-id="29bf9-116">Quando aplicado, o LCM [(Configuration Manager local)](../managing-nodes/metaConfig.md) lerá o valor "Spooler" do arquivo ".mof" e o enviará para o parâmetro `-Name` dos métodos **Get**, **Test** e **Set** da instância "MyService" do recurso **Serviço**.</span><span class="sxs-lookup"><span data-stu-id="29bf9-116">When applied, the [Local Configuration Manager](../managing-nodes/metaConfig.md) (LCM) will read the value "Spooler" from the ".mof" file, and pass it to the `-Name` parameter of the **Get**, **Test**, and **Set** methods for the "MyService" instance of the **Service** resource.</span></span>

## <a name="get"></a><span data-ttu-id="29bf9-117">Obter</span><span class="sxs-lookup"><span data-stu-id="29bf9-117">Get</span></span>

<span data-ttu-id="29bf9-118">O método **Get** de um recurso recupera o estado do recurso como está configurado no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="29bf9-118">The **Get** method of a resource, retrieves the state of the resource as it is configured on the target Node.</span></span> <span data-ttu-id="29bf9-119">Esse estado é retornado como uma [tabela de hash](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="29bf9-119">This state is returned as a [hashtable](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span> <span data-ttu-id="29bf9-120">As chaves da **tabela de hash** serão valores ou parâmetros configuráveis que o recurso aceita.</span><span class="sxs-lookup"><span data-stu-id="29bf9-120">The keys of the **hashtable** will be the configurable values, or parameters, the resource accepts.</span></span>

<span data-ttu-id="29bf9-121">O método **Get** mapeia diretamente no cmdlet [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="29bf9-121">The **Get** method maps directly to the [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="29bf9-122">Quando você chama `Get-DSCConfiguration`, o LCM executa o método **Get** de cada recurso na configuração aplicada no momento.</span><span class="sxs-lookup"><span data-stu-id="29bf9-122">When you call `Get-DSCConfiguration`, the LCM runs the **Get** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="29bf9-123">O LCM usa os valores de chave armazenados no arquivo ".mof" como parâmetros para cada instância do recurso correspondente.</span><span class="sxs-lookup"><span data-stu-id="29bf9-123">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="29bf9-124">Isso é o exemplo de saída de um recurso **Serviço** que configura o serviço "Spooler".</span><span class="sxs-lookup"><span data-stu-id="29bf9-124">This is sample output from a **Service** resource that configures the "Spooler" service.</span></span>

```output
ConfigurationName    : Test
DependsOn            :
ModuleName           : PsDesiredStateConfiguration
ModuleVersion        : 1.1
PsDscRunAsCredential :
ResourceId           : [Service]Spooler
SourceInfo           :
BuiltInAccount       : LocalSystem
Credential           :
Dependencies         : {RPCSS, http}
Description          : This service spools print jobs and handles interaction with the printer.  If you turn off
                       this service, you won't be able to print or see your printers.
DisplayName          : Print Spooler
Ensure               :
Name                 : Spooler
Path                 : C:\WINDOWS\System32\spoolsv.exe
StartupType          : Automatic
State                : Running
Status               :
PSComputerName       :
CimClassName         : MSFT_ServiceResource
```

<span data-ttu-id="29bf9-125">A saída mostra as propriedades do valor atual configurável pelo recurso **Serviço**.</span><span class="sxs-lookup"><span data-stu-id="29bf9-125">The output shows the current value properties configurable by the **Service** resource.</span></span>

```syntax
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

## <a name="test"></a><span data-ttu-id="29bf9-126">Teste</span><span class="sxs-lookup"><span data-stu-id="29bf9-126">Test</span></span>

<span data-ttu-id="29bf9-127">O método **Test** de um recurso determina se o nó de destino é compatível atualmente com o *estado desejado* do recurso.</span><span class="sxs-lookup"><span data-stu-id="29bf9-127">The **Test** method of a resource determines if the target node is currently compliant with the resource's *desired state*.</span></span> <span data-ttu-id="29bf9-128">O método **Test** retorna `$True` ou `$False` apenas para indicar se o nó está em conformidade.</span><span class="sxs-lookup"><span data-stu-id="29bf9-128">The **Test** method returns `$True` or `$False` only to indicate whether the Node is compliant.</span></span>
<span data-ttu-id="29bf9-129">Quando você chama [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), o LCM chama o método **Test** de cada recurso na configuração aplicada no momento.</span><span class="sxs-lookup"><span data-stu-id="29bf9-129">When you call [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), the LCM calls the **Test** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="29bf9-130">O LCM usa os valores de chave armazenados no arquivo ".mof" como parâmetros para cada instância do recurso correspondente.</span><span class="sxs-lookup"><span data-stu-id="29bf9-130">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="29bf9-131">Se o resultado de qualquer recurso **Test** individual for `$False`, `Test-DSCConfiguration` retorna `$False` indicando que o nó não está em conformidade.</span><span class="sxs-lookup"><span data-stu-id="29bf9-131">If the result of any individual resource's **Test** is `$False`, `Test-DSCConfiguration` returns `$False` indicating that the Node is not compliant.</span></span> <span data-ttu-id="29bf9-132">Se todos os métodos **Test** do recurso retornam `$True`, `Test-DSCConfiguration` retorna `$True` para indicar que o nó está em conformidade.</span><span class="sxs-lookup"><span data-stu-id="29bf9-132">If all resource's **Test** methods return `$True`, `Test-DSCConfiguration` returns `$True` to indicate that the Node is compliant.</span></span>

```powershell
Test-DSCConfiguration
```

```output
True
```

<span data-ttu-id="29bf9-133">Começando no PowerShell 5.0, o parâmetro `-Detailed` foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="29bf9-133">Beginning in PowerShell 5.0, the `-Detailed` parameter was added.</span></span> <span data-ttu-id="29bf9-134">Especificar `-Detailed` faz com que `Test-DSCConfiguration` retorne um objeto que contém os conjuntos de resultados para os recursos conformidade e fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="29bf9-134">Specifying `-Detailed` causes `Test-DSCConfiguration` to return an object containing collections of results for compliant, and non-compliant resources.</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

<span data-ttu-id="29bf9-135">Para saber mais, confira [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span><span class="sxs-lookup"><span data-stu-id="29bf9-135">For more information, see [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span></span>

## <a name="set"></a><span data-ttu-id="29bf9-136">Definir</span><span class="sxs-lookup"><span data-stu-id="29bf9-136">Set</span></span>

<span data-ttu-id="29bf9-137">O método **Set** de um recurso tenta forçar o nó para estar em conformidade com o *estado desejado* do recurso.</span><span class="sxs-lookup"><span data-stu-id="29bf9-137">The **Set** method of a resource attempts to force the Node to become compliant with the resource's *desired state*.</span></span> <span data-ttu-id="29bf9-138">O método **Set** deve ser **idempotent**, o que significa que **Set** pode ser executado várias vezes e sempre obterá o mesmo resultado sem erros.</span><span class="sxs-lookup"><span data-stu-id="29bf9-138">The **Set** method is meant to be **idempotent**, which means that **Set** could be run multiple times and always get the same result without errors.</span></span>  <span data-ttu-id="29bf9-139">Quando você chama [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), o LCM percorre cada recurso na configuração aplicada no momento.</span><span class="sxs-lookup"><span data-stu-id="29bf9-139">When you run [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), the LCM cycles through each resource in the currently applied configuration.</span></span> <span data-ttu-id="29bf9-140">O LCM recupera os valores de chave para a instância atual do recurso do arquivo ".mof" e os usa como parâmetros para o método **Test**.</span><span class="sxs-lookup"><span data-stu-id="29bf9-140">The LCM retrieves key values for the current resource instance from the ".mof" file and uses them as parameters for the **Test** method.</span></span> <span data-ttu-id="29bf9-141">Se o método **Test** retornar `$True`, o nó está em conformidade com o recurso atual e o método **Set** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="29bf9-141">If the **Test** method returns `$True`, the Node is compliant with the current resource, and the **Set** method is skipped.</span></span> <span data-ttu-id="29bf9-142">Se o **Test** retornar `$False`, o nó não está em conformidade.</span><span class="sxs-lookup"><span data-stu-id="29bf9-142">If the **Test** returns `$False`, the Node is non-compliant.</span></span>  <span data-ttu-id="29bf9-143">O LCM passa os valores de chave da instância do recurso como parâmetros para do método **Set** do recurso, restaurando o nó para conformidade.</span><span class="sxs-lookup"><span data-stu-id="29bf9-143">The LCM passes the resource instance's key values as parameters to the resource's **Set** method, restoring the Node to compliance.</span></span>

<span data-ttu-id="29bf9-144">Especificando os parâmetros `-Verbose` e `-Wait`, você pode observar o progresso do cmdlet `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="29bf9-144">By specifying the `-Verbose` and `-Wait` parameters, you can watch the progress of the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="29bf9-145">Neste exemplo, o nó já está em conformidade.</span><span class="sxs-lookup"><span data-stu-id="29bf9-145">In this example, the Node is already compliant.</span></span> <span data-ttu-id="29bf9-146">A saída `Verbose` indica que o método **Set** foi ignorado.</span><span class="sxs-lookup"><span data-stu-id="29bf9-146">The `Verbose` output indicates that the **Set** method was skipped.</span></span>

```
PS> Start-DSCConfiguration -Verbose -Wait -UseExisting

VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' =
ApplyConfiguration,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' =
root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer SERVER01 with user sid
S-1-5-21-124525095-708259637-1543119021-1282804.
VERBOSE: [SERVER01]:                            [] Starting consistency engine.
VERBOSE: [SERVER01]:                            [] Checking consistency for current configuration.
VERBOSE: [SERVER01]:                            [DSCEngine] Importing the module
C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\DscResources\MSFT_ServiceResource\MSFT
_ServiceResource.psm1 in force mode.
VERBOSE: [SERVER01]: LCM:  [ Start  Resource ]  [[Service]Spooler]
VERBOSE: [SERVER01]: LCM:  [ Start  Test     ]  [[Service]Spooler]
VERBOSE: [SERVER01]:                            [[Service]Spooler] Importing the module MSFT_ServiceResource in
force mode.
VERBOSE: [SERVER01]: LCM:  [ End    Test     ]  [[Service]Spooler]  in 0.2540 seconds.
VERBOSE: [SERVER01]: LCM:  [ Skip   Set      ]  [[Service]Spooler]
VERBOSE: [SERVER01]: LCM:  [ End    Resource ]  [[Service]Spooler]
VERBOSE: [SERVER01]:                            [] Consistency check completed.
VERBOSE: Operation 'Invoke CimMethod' complete.
VERBOSE: Time taken for configuration job to complete is 1.379 seconds
```

## <a name="see-also"></a><span data-ttu-id="29bf9-147">Confira também</span><span class="sxs-lookup"><span data-stu-id="29bf9-147">See also</span></span>

- [<span data-ttu-id="29bf9-148">Visão geral do DSC de Automação do Azure</span><span class="sxs-lookup"><span data-stu-id="29bf9-148">Azure Automation DSC Overview</span></span>](https://docs.microsoft.com/azure/automation/automation-dsc-overview)
- [<span data-ttu-id="29bf9-149">Configurando um servidor de pull da Web e SMB</span><span class="sxs-lookup"><span data-stu-id="29bf9-149">Setting up an SMB pull server</span></span>](../pull-server/pullServerSMB.md)
- [<span data-ttu-id="29bf9-150">Configurando um cliente de pull</span><span class="sxs-lookup"><span data-stu-id="29bf9-150">Configuring a pull client</span></span>](../pull-server/pullClientConfigID.md)
