---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Especificando dependências de nó cruzado
description: A DSC fornece recursos especiais que podem ser usados em configurações para especificar dependências em configurações de outros nós.
ms.openlocfilehash: a9fc09af922839b37db476c24c113efc5e3e8cb1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658493"
---
# <a name="specifying-cross-node-dependencies"></a><span data-ttu-id="9679f-104">Especificando dependências de nó cruzado</span><span class="sxs-lookup"><span data-stu-id="9679f-104">Specifying cross-node dependencies</span></span>

> <span data-ttu-id="9679f-105">Aplica-se a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="9679f-105">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="9679f-106">O DSC fornece recursos especiais, **WaitForAll** , **WaitForAny** , e **WaitForSome** que podem ser usados em configurações para especificar dependências em configurações em outros nós.</span><span class="sxs-lookup"><span data-stu-id="9679f-106">DSC provides special resources, **WaitForAll** , **WaitForAny** , and **WaitForSome** that can be used in configurations to specify dependencies on configurations on other nodes.</span></span> <span data-ttu-id="9679f-107">O comportamento desses recursos é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9679f-107">The behavior of these resources is as follows:</span></span>

- <span data-ttu-id="9679f-108">**WaitForAll** : terá êxito se o recurso especificado estiver no estado desejado em todos os nós de destino definidos na propriedade **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="9679f-108">**WaitForAll** : Succeeds if the specified resource is in the desired state on all target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="9679f-109">**WaitForAny** : terá êxito se o recurso especificado estiver no estado desejado em pelo menos um dos nós de destino definidos na propriedade **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="9679f-109">**WaitForAny** : Succeeds if the specified resource is in the desired state on at least one of the target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="9679f-110">**WaitForSome** : especifica uma propriedade **NodeCount** além de uma propriedade **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="9679f-110">**WaitForSome** : Specifies a **NodeCount** property in addition to a **NodeName** property.</span></span> <span data-ttu-id="9679f-111">O recurso terá êxito se estiver no estado desejado em um número mínimo de nós (especificado por **NodeCount** ) definido pela propriedade **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="9679f-111">The resource succeeds if the resource is in the desired state on a minimum number of nodes (specified by **NodeCount** ) defined by the **NodeName** property.</span></span>

## <a name="syntax"></a><span data-ttu-id="9679f-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="9679f-112">Syntax</span></span>

<span data-ttu-id="9679f-113">Os recursos **WaitForAll** e **WaitForAny** compartilham a mesma sintaxe.</span><span class="sxs-lookup"><span data-stu-id="9679f-113">The **WaitForAll** and **WaitForAny** resources share the same syntax.</span></span> <span data-ttu-id="9679f-114">Substitua `<ResourceType>` no exemplo abaixo por **WaitForAny** ou **WaitForAll**.</span><span class="sxs-lookup"><span data-stu-id="9679f-114">Replace `<ResourceType>` in the example below with either **WaitForAny** or **WaitForAll**.</span></span> <span data-ttu-id="9679f-115">Como a palavra-chave **DependsOn** , você precisa formatar o nome como `[ResourceType]ResourceName`.</span><span class="sxs-lookup"><span data-stu-id="9679f-115">Like the **DependsOn** keyword, you will need to format the name as `[ResourceType]ResourceName`.</span></span> <span data-ttu-id="9679f-116">Se o recurso pertencer a uma [Configuração](configurations.md) separada, inclua **ConfigurationName** na cadeia de caracteres formatada `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span><span class="sxs-lookup"><span data-stu-id="9679f-116">If the resource belongs to a separate [Configuration](configurations.md), include the **ConfigurationName** in the formatted string `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span></span> <span data-ttu-id="9679f-117">O **NodeName** é o computador, ou Nó, no qual o recurso atual deve aguardar.</span><span class="sxs-lookup"><span data-stu-id="9679f-117">The **NodeName** is the computer, or Node, on which the current resource should wait.</span></span>

```
<ResourceType> [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential]]
    [ RetryCount = [Uint32] ]
    [ RetryIntervalSec = [Uint64] ]
    [ ThrottleLimit = [Uint32]]
}
```

<span data-ttu-id="9679f-118">O recurso **WaitForSome** tem uma sintaxe semelhante ao exemplo acima, mas adiciona a chave **NodeCount**.</span><span class="sxs-lookup"><span data-stu-id="9679f-118">The **WaitForSome** resource has a similar syntax to the example above, but adds the **NodeCount** key.</span></span> <span data-ttu-id="9679f-119">**NodeCount** indica por quantos Nós o recurso atual deve aguardar.</span><span class="sxs-lookup"><span data-stu-id="9679f-119">The **NodeCount** indicates how many Nodes the current resource should wait on.</span></span>

```
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [RetryCount = [UInt32]]
    [RetryIntervalSec = [UInt64]]
    [ThrottleLimit = [UInt32]]
}
```

<span data-ttu-id="9679f-120">Todos os **WaitForXXXX** compartilham as chaves de sintaxe a seguir.</span><span class="sxs-lookup"><span data-stu-id="9679f-120">All **WaitForXXXX** share the following syntax keys.</span></span>

|       <span data-ttu-id="9679f-121">Propriedade</span><span class="sxs-lookup"><span data-stu-id="9679f-121">Property</span></span>       |                                                                           <span data-ttu-id="9679f-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="9679f-122">Description</span></span>                                                                           |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="9679f-123">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="9679f-123">RetryIntervalSec</span></span>     | <span data-ttu-id="9679f-124">O número de segundos antes de tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="9679f-124">The number of seconds before retrying.</span></span> <span data-ttu-id="9679f-125">O mínimo é 1.</span><span class="sxs-lookup"><span data-stu-id="9679f-125">Minimum is 1.</span></span>                                                                                                            |
| <span data-ttu-id="9679f-126">RetryCount</span><span class="sxs-lookup"><span data-stu-id="9679f-126">RetryCount</span></span>           | <span data-ttu-id="9679f-127">O número máximo de tentativas.</span><span class="sxs-lookup"><span data-stu-id="9679f-127">The maximum number of times to retry.</span></span>                                                                                                                           |
| <span data-ttu-id="9679f-128">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="9679f-128">ThrottleLimit</span></span>        | <span data-ttu-id="9679f-129">O número de máquinas para conectar-se simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="9679f-129">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="9679f-130">O padrão é `New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="9679f-130">Default is `New-CimSession` default.</span></span>                                                                              |
| <span data-ttu-id="9679f-131">DependsOn</span><span class="sxs-lookup"><span data-stu-id="9679f-131">DependsOn</span></span>            | <span data-ttu-id="9679f-132">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="9679f-132">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="9679f-133">Para obter mais informações, confira [DependsOn](resource-depends-on.md)</span><span class="sxs-lookup"><span data-stu-id="9679f-133">For more information, see [DependsOn](resource-depends-on.md)</span></span> |
| <span data-ttu-id="9679f-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="9679f-134">PsDscRunAsCredential</span></span> | <span data-ttu-id="9679f-135">Confira [Usar DSC com credenciais do usuário](./runAsUser.md)</span><span class="sxs-lookup"><span data-stu-id="9679f-135">See [Using DSC with User Credentials](./runAsUser.md)</span></span>                                                                                                           |

## <a name="using-waitforxxxx-resources"></a><span data-ttu-id="9679f-136">Usando os recursos WaitForXXXX</span><span class="sxs-lookup"><span data-stu-id="9679f-136">Using WaitForXXXX resources</span></span>

<span data-ttu-id="9679f-137">Cada recurso **WaitForXXXX** aguarda os recursos especificados serem concluídos no Nó especificado.</span><span class="sxs-lookup"><span data-stu-id="9679f-137">Each **WaitForXXXX** resource waits for the specified resources to complete on the specified Node.</span></span>
<span data-ttu-id="9679f-138">Outros recursos na mesma Configuração podem *depender* do recurso **WaitForXXXX** usando a chave **DependsOn**.</span><span class="sxs-lookup"><span data-stu-id="9679f-138">Other resources in the same Configuration can then *depend on* the **WaitForXXXX** resource using the **DependsOn** key.</span></span>

<span data-ttu-id="9679f-139">Por exemplo, na configuração a seguir, o nó de destino aguarda que o recurso **xADDomain** seja concluído no nó **MyDC** com um número máximo de 30 novas tentativas, em intervalos de 15 segundos, antes que o nó de destino possa se unir ao domínio.</span><span class="sxs-lookup"><span data-stu-id="9679f-139">For example, in the following configuration, the target node is waiting for the **xADDomain** resource to finish on the **MyDC** node with maximum number of 30 retries, at 15-second intervals, before the target node can join the domain.</span></span>

<span data-ttu-id="9679f-140">Por padrão, os recursos **WaitForXXX** realizam uma tentativa e, em seguida, falham.</span><span class="sxs-lookup"><span data-stu-id="9679f-140">By default the **WaitForXXX** resources try one time and then fail.</span></span> <span data-ttu-id="9679f-141">Embora não seja obrigatório, você geralmente deve especificar **RetryCount** e **RetryIntervalSec**.</span><span class="sxs-lookup"><span data-stu-id="9679f-141">Although it is not required, you will typically want to specify a **RetryCount** and **RetryIntervalSec**.</span></span>

```powershell
Configuration JoinDomain
{
    Import-DscResource -Module xComputerManagement, xActiveDirectory

    Node myDC
    {
        WindowsFeature InstallAD
        {
            Ensure = 'Present'
            Name = 'AD-Domain-Services'
        }

        xADDomain NewDomain
        {
            DomainName = 'Contoso.com'
            DomainAdministratorCredential = (Get-Credential)
            SafemodeAdministratorPassword = (Get-Credential)
            DatabasePath = "C:\Windows\NTDS"
            LogPath = "C:\Windows\NTDS"
            SysvolPath = "C:\Windows\Sysvol"
        }
    }

    Node myDomainJoinedServer
    {
        WaitForAll DC
        {
            ResourceName      = '[xADDomain]NewDomain'
            NodeName          = 'MyDC'
            RetryIntervalSec  = 15
            RetryCount        = 30
        }

        xComputer JoinDomain
        {
            Name             = 'myPC'
            DomainName       = 'Contoso.com'
            Credential       = (Get-Credential)
            DependsOn        ='[WaitForAll]DC'
        }
    }
}
```

<span data-ttu-id="9679f-142">Quando você compila a Configuração, são gerados dois arquivos ".mof".</span><span class="sxs-lookup"><span data-stu-id="9679f-142">When you compile the Configuration, two ".mof" files are generated.</span></span> <span data-ttu-id="9679f-143">Aplique ambos os arquivos ".mof" aos Nós de destino usando o cmdlet [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)</span><span class="sxs-lookup"><span data-stu-id="9679f-143">Apply both ".mof" files to the target Nodes using the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet</span></span>

> [!NOTE]
> <span data-ttu-id="9679f-144">Os recursos **WaitForXXX** usam o Gerenciamento Remoto do Windows para verificar o estado dos outros nós.</span><span class="sxs-lookup"><span data-stu-id="9679f-144">**WaitForXXX** resources use Windows Remote Management to check the state of other Nodes.</span></span> <span data-ttu-id="9679f-145">Para obter mais informações sobre os requisitos de porta e segurança do WinRM, confira [Considerações sobre segurança da comunicação remota do PowerShell](/powershell/scripting/learn/remoting/winrmsecurity).</span><span class="sxs-lookup"><span data-stu-id="9679f-145">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity).</span></span>

## <a name="see-also"></a><span data-ttu-id="9679f-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9679f-146">See Also</span></span>

- [<span data-ttu-id="9679f-147">Configurações DSC</span><span class="sxs-lookup"><span data-stu-id="9679f-147">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="9679f-148">Usar dependências do recurso</span><span class="sxs-lookup"><span data-stu-id="9679f-148">Use Resource Dependencies</span></span>](resource-depends-on.md)
- [<span data-ttu-id="9679f-149">Recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="9679f-149">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="9679f-150">Configurando o Gerenciador de Configurações Local</span><span class="sxs-lookup"><span data-stu-id="9679f-150">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
