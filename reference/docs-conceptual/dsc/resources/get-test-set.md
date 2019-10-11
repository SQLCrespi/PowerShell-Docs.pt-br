---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Get-Test-Set
ms.openlocfilehash: 42c1df6df2fbf65cbbb8407db613cac2e5b81cfb
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954283"
---
# <a name="get-test-set"></a>Get-Test-Set

>Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0

![Obter, testar e definir](../media/get-test-set.png)

O PowerShell Desired State Configuration é construído ao redor de um processo **Get**, **Test** e **Set**. Os [recursos](resources.md) do DSC contêm métodos para concluir cada uma dessas operações. Em [Configuração](../configurations/configurations.md), você define os blocos de recursos para preencher as chaves que se tornam parâmetros para os métodos **Get**, **Test** e **Set** de recursos.

Esta é a sintaxe para um bloco de recurso de **Serviço**. O recurso **Serviço** configura os serviços do Windows.

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

Os métodos **Get**, **Test** e **Set** do recurso **Serviço** terão blocos de parâmetro que aceitam esses valores.

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
> O idioma e o método usados para definir o recurso determinam como os métodos **Get**, **Test** e **Set** serão definidos.

Como o recurso **Serviço** só tem uma chave necessária (`Name`), um recurso de bloco de **Serviço** pode ser tão simples quanto isso:

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

Ao compilar a Configuração acima, os valores especificados para uma chave são armazenados no arquivo ".mof" gerado. Para saber mais, confira [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).

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

Quando aplicado, o LCM [(Configuration Manager local)](../managing-nodes/metaConfig.md) lerá o valor "Spooler" do arquivo ".mof" e o enviará para o parâmetro `-Name` dos métodos **Get**, **Test** e **Set** da instância "MyService" do recurso **Serviço**.

## <a name="get"></a>Get

O método **Get** de um recurso recupera o estado do recurso como está configurado no nó de destino. Esse estado é retornado como uma [tabela de hash](/powershell/module/microsoft.powershell.core/about/about_hash_tables). As chaves da **tabela de hash** serão valores ou parâmetros configuráveis que o recurso aceita.

O método **Get** mapeia diretamente no cmdlet [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration). Quando você chama `Get-DSCConfiguration`, o LCM executa o método **Get** de cada recurso na configuração aplicada no momento. O LCM usa os valores de chave armazenados no arquivo ".mof" como parâmetros para cada instância do recurso correspondente.

Isso é o exemplo de saída de um recurso **Serviço** que configura o serviço "Spooler".

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

A saída mostra as propriedades do valor atual configurável pelo recurso **Serviço**.

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

## <a name="test"></a>Teste

O método **Test** de um recurso determina se o nó de destino é compatível atualmente com o *estado desejado* do recurso. O método **Test** retorna `$True` ou `$False` apenas para indicar se o nó está em conformidade.
Quando você chama [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), o LCM chama o método **Test** de cada recurso na configuração aplicada no momento. O LCM usa os valores de chave armazenados no arquivo ".mof" como parâmetros para cada instância do recurso correspondente.

Se o resultado de qualquer recurso **Test** individual for `$False`, `Test-DSCConfiguration` retorna `$False` indicando que o nó não está em conformidade. Se todos os métodos **Test** do recurso retornam `$True`, `Test-DSCConfiguration` retorna `$True` para indicar que o nó está em conformidade.

```powershell
Test-DSCConfiguration
```

```output
True
```

Começando no PowerShell 5.0, o parâmetro `-Detailed` foi adicionado. Especificar `-Detailed` faz com que `Test-DSCConfiguration` retorne um objeto que contém os conjuntos de resultados para os recursos conformidade e fora de conformidade.

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

Para saber mais, confira [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)

## <a name="set"></a>Set

O método **Set** de um recurso tenta forçar o nó para estar em conformidade com o *estado desejado* do recurso. O método **Set** deve ser **idempotent**, o que significa que **Set** pode ser executado várias vezes e sempre obterá o mesmo resultado sem erros.  Quando você chama [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), o LCM percorre cada recurso na configuração aplicada no momento. O LCM recupera os valores de chave para a instância atual do recurso do arquivo ".mof" e os usa como parâmetros para o método **Test**. Se o método **Test** retornar `$True`, o nó está em conformidade com o recurso atual e o método **Set** será ignorado. Se o **Test** retornar `$False`, o nó não está em conformidade.  O LCM passa os valores de chave da instância do recurso como parâmetros para do método **Set** do recurso, restaurando o nó para conformidade.

Especificando os parâmetros `-Verbose` e `-Wait`, você pode observar o progresso do cmdlet `Start-DSCConfiguration`. Neste exemplo, o nó já está em conformidade. A saída `Verbose` indica que o método **Set** foi ignorado.

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

## <a name="see-also"></a>Consulte também

- [Visão geral do DSC de Automação do Azure](https://docs.microsoft.com/azure/automation/automation-dsc-overview)
- [Configurando um servidor de pull da Web e SMB](../pull-server/pullServerSMB.md)
- [Configurando um cliente de pull](../pull-server/pullClientConfigID.md)
