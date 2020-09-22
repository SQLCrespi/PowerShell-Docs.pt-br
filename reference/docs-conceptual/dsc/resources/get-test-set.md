---
ms.date: 07/08/2020
keywords: DSC,powershell,configuração,instalação
title: Get-Test-Set
ms.openlocfilehash: f7b7e947a85832365a783e40c25a25bfaa9fff8d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771508"
---
# <a name="get-test-set"></a><span data-ttu-id="40c5d-103">Get-Test-Set</span><span class="sxs-lookup"><span data-stu-id="40c5d-103">Get-Test-Set</span></span>

><span data-ttu-id="40c5d-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="40c5d-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="40c5d-105">O PowerShell Desired State Configuration é construído ao redor de um processo **Get**, **Test** e **Set**.</span><span class="sxs-lookup"><span data-stu-id="40c5d-105">PowerShell Desired State Configuration is constructed around a **Get**, **Test**, and **Set** process.</span></span> <span data-ttu-id="40c5d-106">Os [recursos](resources.md) do DSC contêm métodos para concluir cada uma dessas operações.</span><span class="sxs-lookup"><span data-stu-id="40c5d-106">DSC [resources](resources.md) each contains methods to complete each of these operations.</span></span>
<span data-ttu-id="40c5d-107">Em [Configuração](../configurations/configurations.md), você define os blocos de recursos para preencher as chaves que se tornam parâmetros para os métodos **Get**, **Test** e **Set** de recursos.</span><span class="sxs-lookup"><span data-stu-id="40c5d-107">In a [Configuration](../configurations/configurations.md), you define resource blocks to fill in keys that become parameters for a resource's **Get**, **Test**, and **Set** methods.</span></span>

<span data-ttu-id="40c5d-108">Esta é a sintaxe para um bloco de recurso de **Serviço**.</span><span class="sxs-lookup"><span data-stu-id="40c5d-108">This is the syntax for a **Service** resource block.</span></span> <span data-ttu-id="40c5d-109">O recurso **Serviço** configura os serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="40c5d-109">The **Service** resource configures Windows services.</span></span>

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

<span data-ttu-id="40c5d-110">Os métodos **Get**, **Test** e **Set** do recurso **Serviço** terão blocos de parâmetro que aceitam esses valores.</span><span class="sxs-lookup"><span data-stu-id="40c5d-110">The **Get**, **Test**, and **Set** methods of the **Service** resource will have parameter blocks that accept these values.</span></span>

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
> <span data-ttu-id="40c5d-111">O idioma e o método usados para definir o recurso determinam como os métodos **Get**, **Test** e **Set** serão definidos.</span><span class="sxs-lookup"><span data-stu-id="40c5d-111">The language and method used to define the resource determines how the **Get**, **Test**, and **Set** methods will be defined.</span></span>

<span data-ttu-id="40c5d-112">Como o recurso **Serviço** só tem uma chave necessária (`Name`), um recurso de bloco de **Serviço** pode ser tão simples quanto isso:</span><span class="sxs-lookup"><span data-stu-id="40c5d-112">Because the **Service** resource only has one required key (`Name`), a **Service** block resource could be as simple as this:</span></span>

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

<span data-ttu-id="40c5d-113">Quando você compila a Configuração acima, os valores especificados para uma chave são armazenados no arquivo `.mof` gerado.</span><span class="sxs-lookup"><span data-stu-id="40c5d-113">When you compile the Configuration above, the values you specify for a key are stored in the `.mof` file that is generated.</span></span> <span data-ttu-id="40c5d-114">Para saber mais, confira [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="40c5d-114">For more information, see [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>

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

<span data-ttu-id="40c5d-115">Quando aplicado, o [LCM](../managing-nodes/metaConfig.md) (Configuration Manager local) lerá o valor "Spooler" do arquivo `.mof` e o passará para o parâmetro **Name** dos métodos **Get**, **Test** e **Set** da instância "MyService" do recurso **Serviço**.</span><span class="sxs-lookup"><span data-stu-id="40c5d-115">When applied, the [Local Configuration Manager](../managing-nodes/metaConfig.md) (LCM) will read the value "Spooler" from the `.mof` file, and pass it to the **Name** parameter of the **Get**, **Test**, and **Set** methods for the "MyService" instance of the **Service** resource.</span></span>

## <a name="get"></a><span data-ttu-id="40c5d-116">Obter</span><span class="sxs-lookup"><span data-stu-id="40c5d-116">Get</span></span>

<span data-ttu-id="40c5d-117">O método **Get** de um recurso recupera o estado do recurso como está configurado no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="40c5d-117">The **Get** method of a resource, retrieves the state of the resource as it is configured on the target Node.</span></span> <span data-ttu-id="40c5d-118">Esse estado é retornado como uma [tabela de hash](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="40c5d-118">This state is returned as a [hashtable](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>
<span data-ttu-id="40c5d-119">As chaves da **tabela de hash** serão valores ou parâmetros configuráveis que o recurso aceita.</span><span class="sxs-lookup"><span data-stu-id="40c5d-119">The keys of the **hashtable** will be the configurable values, or parameters, the resource accepts.</span></span>

<span data-ttu-id="40c5d-120">O método **Get** mapeia diretamente no cmdlet [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="40c5d-120">The **Get** method maps directly to the [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="40c5d-121">Quando você chama `Get-DSCConfiguration`, o LCM executa o método **Get** de cada recurso na configuração aplicada no momento.</span><span class="sxs-lookup"><span data-stu-id="40c5d-121">When you call `Get-DSCConfiguration`, the LCM runs the **Get** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="40c5d-122">O LCM usa os valores de chave armazenados no arquivo `.mof` como parâmetros para cada instância do recurso correspondente.</span><span class="sxs-lookup"><span data-stu-id="40c5d-122">The LCM uses the key values stored in the `.mof` file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="40c5d-123">Isso é o exemplo de saída de um recurso **Serviço** que configura o serviço "Spooler".</span><span class="sxs-lookup"><span data-stu-id="40c5d-123">This is sample output from a **Service** resource that configures the "Spooler" service.</span></span>

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

<span data-ttu-id="40c5d-124">A saída mostra as propriedades do valor atual configurável pelo recurso **Serviço**.</span><span class="sxs-lookup"><span data-stu-id="40c5d-124">The output shows the current value properties configurable by the **Service** resource.</span></span>

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

## <a name="test"></a><span data-ttu-id="40c5d-125">Teste</span><span class="sxs-lookup"><span data-stu-id="40c5d-125">Test</span></span>

<span data-ttu-id="40c5d-126">O método **Test** de um recurso determina se o nó de destino é compatível atualmente com o _estado desejado_ do recurso.</span><span class="sxs-lookup"><span data-stu-id="40c5d-126">The **Test** method of a resource determines if the target node is currently compliant with the resource's _desired state_.</span></span> <span data-ttu-id="40c5d-127">O método **Test** retorna `$true` ou `$false` apenas para indicar se o nó está em conformidade.</span><span class="sxs-lookup"><span data-stu-id="40c5d-127">The **Test** method returns `$true` or `$false` only to indicate whether the Node is compliant.</span></span> <span data-ttu-id="40c5d-128">Quando você chama [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), o LCM chama o método **Test** de cada recurso na configuração aplicada no momento.</span><span class="sxs-lookup"><span data-stu-id="40c5d-128">When you call [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), the LCM calls the **Test** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="40c5d-129">O LCM usa os valores de chave armazenados no arquivo ".mof" como parâmetros para cada instância do recurso correspondente.</span><span class="sxs-lookup"><span data-stu-id="40c5d-129">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="40c5d-130">Se o resultado de qualquer recurso **Test** individual for `$false`, `Test-DSCConfiguration` retorna `$false` indicando que o nó não está em conformidade.</span><span class="sxs-lookup"><span data-stu-id="40c5d-130">If the result of any individual resource's **Test** is `$false`, `Test-DSCConfiguration` returns `$false` indicating that the Node is not compliant.</span></span> <span data-ttu-id="40c5d-131">Se todos os métodos **Test** do recurso retornam `$true`, `Test-DSCConfiguration` retorna `$true` para indicar que o nó está em conformidade.</span><span class="sxs-lookup"><span data-stu-id="40c5d-131">If all resource's **Test** methods return `$true`, `Test-DSCConfiguration` returns `$true` to indicate that the Node is compliant.</span></span>

```powershell
Test-DSCConfiguration
```

```output
True
```

<span data-ttu-id="40c5d-132">Começando no PowerShell 5.0, o parâmetro **Detailed** foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="40c5d-132">Beginning in PowerShell 5.0, the **Detailed** parameter was added.</span></span> <span data-ttu-id="40c5d-133">Especificar **Detailed** faz `Test-DSCConfiguration` retornar um objeto que contém os conjuntos de resultados para os recursos em conformidade e os que não estão em conformidade.</span><span class="sxs-lookup"><span data-stu-id="40c5d-133">Specifying **Detailed** causes `Test-DSCConfiguration` to return an object containing collections of results for compliant, and non-compliant resources.</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

<span data-ttu-id="40c5d-134">Para saber mais, confira [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span><span class="sxs-lookup"><span data-stu-id="40c5d-134">For more information, see [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span></span>

## <a name="set"></a><span data-ttu-id="40c5d-135">Definir</span><span class="sxs-lookup"><span data-stu-id="40c5d-135">Set</span></span>

<span data-ttu-id="40c5d-136">O método **Set** de um recurso tenta forçar o nó para estar em conformidade com o *estado desejado* do recurso.</span><span class="sxs-lookup"><span data-stu-id="40c5d-136">The **Set** method of a resource attempts to force the Node to become compliant with the resource's *desired state*.</span></span> <span data-ttu-id="40c5d-137">O método **Set** deve ser **idempotent**, o que significa que **Set** pode ser executado várias vezes e sempre obterá o mesmo resultado sem erros.</span><span class="sxs-lookup"><span data-stu-id="40c5d-137">The **Set** method is meant to be **idempotent**, which means that **Set** could be run multiple times and always get the same result without errors.</span></span> <span data-ttu-id="40c5d-138">Quando você chama [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), o LCM percorre cada recurso na configuração aplicada no momento.</span><span class="sxs-lookup"><span data-stu-id="40c5d-138">When you run [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), the LCM cycles through each resource in the currently applied configuration.</span></span> <span data-ttu-id="40c5d-139">O LCM recupera os valores de chave para a instância atual do recurso do arquivo ".mof" e os usa como parâmetros para o método **Test**.</span><span class="sxs-lookup"><span data-stu-id="40c5d-139">The LCM retrieves key values for the current resource instance from the ".mof" file and uses them as parameters for the **Test** method.</span></span> <span data-ttu-id="40c5d-140">Se o método **Test** retornar `$true`, o nó está em conformidade com o recurso atual e o método **Set** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="40c5d-140">If the **Test** method returns `$true`, the Node is compliant with the current resource, and the **Set** method is skipped.</span></span> <span data-ttu-id="40c5d-141">Se o **Test** retornar `$false`, o nó não está em conformidade.</span><span class="sxs-lookup"><span data-stu-id="40c5d-141">If the **Test** returns `$false`, the Node is non-compliant.</span></span> <span data-ttu-id="40c5d-142">O LCM passa os valores de chave da instância do recurso como parâmetros para do método **Set** do recurso, restaurando o nó para conformidade.</span><span class="sxs-lookup"><span data-stu-id="40c5d-142">The LCM passes the resource instance's key values as parameters to the resource's **Set** method, restoring the Node to compliance.</span></span>

<span data-ttu-id="40c5d-143">Especificando os parâmetros **Verbose** e **Wait**, você pode observar o progresso do cmdlet `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="40c5d-143">By specifying the **Verbose** and **Wait** parameters, you can watch the progress of the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="40c5d-144">Neste exemplo, o nó já está em conformidade.</span><span class="sxs-lookup"><span data-stu-id="40c5d-144">In this example, the Node is already compliant.</span></span> <span data-ttu-id="40c5d-145">A saída `Verbose` indica que o método **Set** foi ignorado.</span><span class="sxs-lookup"><span data-stu-id="40c5d-145">The `Verbose` output indicates that the **Set** method was skipped.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="40c5d-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="40c5d-146">See also</span></span>

- [<span data-ttu-id="40c5d-147">Visão geral do DSC de Automação do Azure</span><span class="sxs-lookup"><span data-stu-id="40c5d-147">Azure Automation DSC Overview</span></span>](/azure/automation/automation-dsc-overview)
- [<span data-ttu-id="40c5d-148">Configurando um servidor de pull da Web e SMB</span><span class="sxs-lookup"><span data-stu-id="40c5d-148">Setting up an SMB pull server</span></span>](../pull-server/pullServerSMB.md)
- [<span data-ttu-id="40c5d-149">Configurando um cliente de pull</span><span class="sxs-lookup"><span data-stu-id="40c5d-149">Configuring a pull client</span></span>](../pull-server/pullClientConfigID.md)
