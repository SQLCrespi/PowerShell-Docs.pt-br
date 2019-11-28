---
ms.date: 07/10/2019
keywords: jea,powershell,segurança
title: Registrando Configurações de JEA
ms.openlocfilehash: dbed5c7dd71f2f7a09d97416be56dff675799548
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417606"
---
# <a name="registering-jea-configurations"></a><span data-ttu-id="bdd0c-103">Registrando Configurações de JEA</span><span class="sxs-lookup"><span data-stu-id="bdd0c-103">Registering JEA Configurations</span></span>

<span data-ttu-id="bdd0c-104">Depois que você criar as [capacidades de função](role-capabilities.md) e o [arquivo de configuração de sessão](session-configurations.md), a última etapa será registrar o ponto de extremidade JEA.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-104">Once you have your [role capabilities](role-capabilities.md) and [session configuration file](session-configurations.md) created, the last step is to register the JEA endpoint.</span></span> <span data-ttu-id="bdd0c-105">Registrar o ponto de extremidade JEA no sistema torna o ponto de extremidade disponível para uso pelos usuários e pelos mecanismos de automação.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-105">Registering the JEA endpoint with the system makes the endpoint available for use by users and automation engines.</span></span>

## <a name="single-machine-configuration"></a><span data-ttu-id="bdd0c-106">Configuração de computador único</span><span class="sxs-lookup"><span data-stu-id="bdd0c-106">Single machine configuration</span></span>

<span data-ttu-id="bdd0c-107">Em ambientes pequenos, você pode implantar o JEA ao registrar o arquivo de configuração de sessão usando o cmdlet [Register-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/register-pssessionconfiguration).</span><span class="sxs-lookup"><span data-stu-id="bdd0c-107">For small environments, you can deploy JEA by registering the session configuration file using the [Register-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/register-pssessionconfiguration) cmdlet.</span></span>

<span data-ttu-id="bdd0c-108">Antes de começar, verifique se os pré-requisitos a seguir foram atendidos:</span><span class="sxs-lookup"><span data-stu-id="bdd0c-108">Before you begin, ensure that the following prerequisites have been met:</span></span>

- <span data-ttu-id="bdd0c-109">Uma ou mais funções foram criadas e colocadas na pasta **RoleCapabilities** de um módulo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-109">One or more roles has been created and placed in the **RoleCapabilities** folder of a PowerShell module.</span></span>
- <span data-ttu-id="bdd0c-110">Um arquivo de configuração de sessão foi criado e testado.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-110">A session configuration file has been created and tested.</span></span>
- <span data-ttu-id="bdd0c-111">O usuário que está registrando a configuração JEA tem direitos de administrador no sistema.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-111">The user registering the JEA configuration has administrator rights on the system.</span></span>
- <span data-ttu-id="bdd0c-112">Você selecionou um nome para o ponto de extremidade JEA.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-112">You've selected a name for your JEA endpoint.</span></span>

<span data-ttu-id="bdd0c-113">O nome do ponto de extremidade JEA será necessário quando os usuários se conectarem ao sistema usando o JEA.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-113">The name of the JEA endpoint is required when users connect to the system using JEA.</span></span> <span data-ttu-id="bdd0c-114">O cmdlet [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) lista os nomes dos pontos de extremidade em um sistema.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-114">The [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) cmdlet lists the names of the endpoints on a system.</span></span> <span data-ttu-id="bdd0c-115">Os pontos de extremidade que começam com `microsoft` geralmente são fornecidos com o Windows.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-115">Endpoints that start with `microsoft` are typically shipped with Windows.</span></span> <span data-ttu-id="bdd0c-116">O ponto de extremidade `microsoft.powershell` é o ponto de extremidade padrão usado ao se conectar a um ponto de extremidade remoto do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-116">The `microsoft.powershell` endpoint is the default endpoint used when connecting to a remote PowerShell endpoint.</span></span>

```powershell
Get-PSSessionConfiguration | Select-Object Name
```

```Output
Name
----
microsoft.powershell
microsoft.powershell.workflow
microsoft.powershell32
```

<span data-ttu-id="bdd0c-117">Execute o comando a seguir para registrar o ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-117">Run the following command to register the endpoint.</span></span>

```powershell
Register-PSSessionConfiguration -Path .\MyJEAConfig.pssc -Name 'JEAMaintenance' -Force
```

> [!WARNING]
> <span data-ttu-id="bdd0c-118">O comando anterior reinicia o serviço WinRM no sistema.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-118">The previous command restarts the WinRM service on the system.</span></span> <span data-ttu-id="bdd0c-119">Isso termina todas as sessões de comunicação remota do PowerShell, bem como as configurações DSC em andamento.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-119">This terminates all PowerShell remoting sessions and any ongoing DSC configurations.</span></span> <span data-ttu-id="bdd0c-120">Recomendamos que você coloque todos os computadores de produção offline antes de executar o comando para evitar interromper as operações de negócios.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-120">We recommended you take production machines offline before running the command to avoid disrupting business operations.</span></span>

<span data-ttu-id="bdd0c-121">Após o registro, você estará pronto para [usar o JEA](using-jea.md).</span><span class="sxs-lookup"><span data-stu-id="bdd0c-121">After registration, you're ready to [use JEA](using-jea.md).</span></span> <span data-ttu-id="bdd0c-122">Você poderá excluir o arquivo de configuração de sessão a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-122">You may delete the session configuration file at any time.</span></span> <span data-ttu-id="bdd0c-123">O arquivo de configuração não é usado após o registro do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-123">The configuration file isn't used after registration of the endpoint.</span></span>

## <a name="multi-machine-configuration-with-dsc"></a><span data-ttu-id="bdd0c-124">Configuração de vários computadores com o DSC</span><span class="sxs-lookup"><span data-stu-id="bdd0c-124">Multi-machine configuration with DSC</span></span>

<span data-ttu-id="bdd0c-125">Se você estiver implantando o JEA em vários computadores, o modelo de implantação mais simples usará o recurso [DSC (Desired State Configuration)](/powershell/scripting/dsc/overview) do JEA para implantar o JEA de forma rápida e consistente em cada computador.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-125">When deploying JEA on multiple machines, the simplest deployment model uses the JEA [Desired State Configuration (DSC)](/powershell/scripting/dsc/overview) resource to quickly and consistently deploy JEA on each machine.</span></span>

<span data-ttu-id="bdd0c-126">Para implantar o JEA com o DSC, garanta que os seguintes pré-requisitos sejam atendidos:</span><span class="sxs-lookup"><span data-stu-id="bdd0c-126">To deploy JEA with DSC, ensure the following prerequisites are met:</span></span>

- <span data-ttu-id="bdd0c-127">Uma ou mais capacidades de função foram criadas e adicionadas a um módulo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-127">One or more role capabilities have been authored and added to a PowerShell module.</span></span>
- <span data-ttu-id="bdd0c-128">O módulo do PowerShell que contém as funções é armazenado em um compartilhamento de arquivo (somente leitura) acessível por cada computador.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-128">The PowerShell module containing the roles is stored on a (read-only) file share accessible by each machine.</span></span>
- <span data-ttu-id="bdd0c-129">As configurações para a configuração de sessão foram determinadas.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-129">Settings for the session configuration have been determined.</span></span> <span data-ttu-id="bdd0c-130">Não é necessário criar um arquivo de configuração de sessão ao usar o recurso DSC do JEA.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-130">You don't need to create a session configuration file when using the JEA DSC resource.</span></span>
- <span data-ttu-id="bdd0c-131">Você tem credenciais que permitem ações administrativas em cada computador ou tem acesso ao servidor de pull DSC usado para gerenciar os computadores.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-131">You have credentials that allow administrative actions on each machine or access to the DSC pull server used to manage the machines.</span></span>
- <span data-ttu-id="bdd0c-132">Você baixou o [recurso DSC do JEA](https://github.com/powershell/JEA/tree/master/DSC%20Resource).</span><span class="sxs-lookup"><span data-stu-id="bdd0c-132">You've downloaded the [JEA DSC resource](https://github.com/powershell/JEA/tree/master/DSC%20Resource).</span></span>

<span data-ttu-id="bdd0c-133">Crie uma configuração DSC para o ponto de extremidade JEA em um computador de destino ou um servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-133">Create a DSC configuration for your JEA endpoint on a target machine or pull server.</span></span> <span data-ttu-id="bdd0c-134">Nessa configuração, o recurso DSC **JustEnoughAdministration** define o arquivo de configuração de sessão e o recurso **File** copia as capacidades de função do compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-134">In this configuration, the **JustEnoughAdministration** DSC resource defines the session configuration file and the **File** resource copies the role capabilities from the file share.</span></span>

<span data-ttu-id="bdd0c-135">As seguintes propriedades são configuráveis usando o recurso de DSC:</span><span class="sxs-lookup"><span data-stu-id="bdd0c-135">The following properties are configurable using the DSC resource:</span></span>

- <span data-ttu-id="bdd0c-136">Definições de Função</span><span class="sxs-lookup"><span data-stu-id="bdd0c-136">Role Definitions</span></span>
- <span data-ttu-id="bdd0c-137">Grupos de contas virtuais</span><span class="sxs-lookup"><span data-stu-id="bdd0c-137">Virtual account groups</span></span>
- <span data-ttu-id="bdd0c-138">Nome da conta de serviço gerenciado de grupo</span><span class="sxs-lookup"><span data-stu-id="bdd0c-138">Group-managed service account name</span></span>
- <span data-ttu-id="bdd0c-139">Diretório de transcrição</span><span class="sxs-lookup"><span data-stu-id="bdd0c-139">Transcript directory</span></span>
- <span data-ttu-id="bdd0c-140">Unidade de usuário</span><span class="sxs-lookup"><span data-stu-id="bdd0c-140">User drive</span></span>
- <span data-ttu-id="bdd0c-141">Regras de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="bdd0c-141">Conditional access rules</span></span>
- <span data-ttu-id="bdd0c-142">Scripts de inicialização para a sessão JEA</span><span class="sxs-lookup"><span data-stu-id="bdd0c-142">Startup scripts for the JEA session</span></span>

<span data-ttu-id="bdd0c-143">A sintaxe para cada uma dessas propriedades em uma configuração DSC é consistente com o arquivo de configuração de sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-143">The syntax for each of these properties in a DSC configuration is consistent with the PowerShell session configuration file.</span></span>

<span data-ttu-id="bdd0c-144">Abaixo está um exemplo de configuração de DSC para um módulo de manutenção geral do servidor.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-144">Below is a sample DSC configuration for a general server maintenance module.</span></span> <span data-ttu-id="bdd0c-145">Ele pressupõe que um módulo do PowerShell válido contendo as capacidades de função esteja localizado no compartilhamento de arquivo `\\myfileshare\JEA`.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-145">It assumes that a valid PowerShell module containing role capabilities is located on the `\\myfileshare\JEA` file share.</span></span>

```powershell
Configuration JEAMaintenance
{
    Import-DscResource -Module JustEnoughAdministration, PSDesiredStateConfiguration

    File MaintenanceModule
    {
        SourcePath = "\\myfileshare\JEA\ContosoMaintenance"
        DestinationPath = "C:\Program Files\WindowsPowerShell\Modules\ContosoMaintenance"
        Checksum = "SHA-256"
        Ensure = "Present"
        Type = "Directory"
        Recurse = $true
    }

    JeaEndpoint JEAMaintenanceEndpoint
    {
        EndpointName = "JEAMaintenance"
        RoleDefinitions = "@{ 'CONTOSO\JEAMaintenanceAuditors' = @{ RoleCapabilities = 'GeneralServerMaintenance-Audit' }; 'CONTOSO\JEAMaintenanceAdmins' = @{ RoleCapabilities = 'GeneralServerMaintenance-Audit', 'GeneralServerMaintenance-Admin' } }"
        TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
        DependsOn = '[File]MaintenanceModule'
    }
}
```

<span data-ttu-id="bdd0c-146">Em seguida, a configuração é aplicada em um sistema pela invocação direta do [Gerenciador de Configurações Local](/powershell/scripting/dsc/managing-nodes/metaConfig) ou pela atualização da [configuração do servidor de pull](/powershell/scripting/dsc/pull-server/pullServer).</span><span class="sxs-lookup"><span data-stu-id="bdd0c-146">Next, the configuration is applied on a system by directly invoking the [Local Configuration Manager](/powershell/scripting/dsc/managing-nodes/metaConfig) or updating the [pull server configuration](/powershell/scripting/dsc/pull-server/pullServer).</span></span>

<span data-ttu-id="bdd0c-147">O recurso DSC também permite que você substitua o ponto de extremidade **Microsoft.PowerShell** padrão.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-147">The DSC resource also allows you to replace the default **Microsoft.PowerShell** endpoint.</span></span> <span data-ttu-id="bdd0c-148">Quando substituído, o recurso registra automaticamente um ponto de extremidade de backup chamado **Microsoft.PowerShell.Restricted**.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-148">When replaced, the resource automatically registers a backup endpoint named **Microsoft.PowerShell.Restricted**.</span></span> <span data-ttu-id="bdd0c-149">O ponto de extremidade de backup tem a ACL padrão do WinRM que permite acesso aos Usuários do Gerenciamento Remoto e aos membros do grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-149">The backup endpoint has the default WinRM ACL that allows Remote Management Users and local Administrators group members to access it.</span></span>

## <a name="unregistering-jea-configurations"></a><span data-ttu-id="bdd0c-150">Cancelando o registro de configurações de JEA</span><span class="sxs-lookup"><span data-stu-id="bdd0c-150">Unregistering JEA configurations</span></span>

<span data-ttu-id="bdd0c-151">O cmdlet [Unregister-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/Unregister-PSSessionConfiguration) remove um ponto de extremidade JEA.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-151">The [Unregister-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/Unregister-PSSessionConfiguration) cmdlet removes a JEA endpoint.</span></span> <span data-ttu-id="bdd0c-152">O cancelamento do registro de um ponto de extremidade JEA impede que novos usuários criem novas sessões de JEA no sistema.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-152">Unregistering a JEA endpoint prevents new users from creating new JEA sessions on the system.</span></span> <span data-ttu-id="bdd0c-153">Ele também permite que você atualize uma configuração de JEA, registrando novamente um arquivo de configuração de sessão atualizado usando o mesmo nome de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-153">It also allows you to update a JEA configuration by re-registering an updated session configuration file using the same endpoint name.</span></span>

```powershell
# Unregister the JEA endpoint called "ContosoMaintenance"
Unregister-PSSessionConfiguration -Name 'ContosoMaintenance' -Force
```

> [!WARNING]
> <span data-ttu-id="bdd0c-154">O cancelamento do registro de um ponto de extremidade JEA faz com que o serviço WinRM seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-154">Unregistering a JEA endpoint causes the WinRM service to restart.</span></span> <span data-ttu-id="bdd0c-155">Isso interrompe a maioria das operações de gerenciamento remotas em andamento, incluindo outras sessões do PowerShell, invocações de WMI e algumas ferramentas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-155">This interrupts most remote management operations in progress, including other PowerShell sessions, WMI invocations, and some management tools.</span></span> <span data-ttu-id="bdd0c-156">Cancele o registro de pontos de extremidade do PowerShell somente durante janelas de manutenção planejadas.</span><span class="sxs-lookup"><span data-stu-id="bdd0c-156">Only unregister PowerShell endpoints during planned maintenance windows.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bdd0c-157">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="bdd0c-157">Next steps</span></span>

[<span data-ttu-id="bdd0c-158">Testar o ponto de extremidade JEA</span><span class="sxs-lookup"><span data-stu-id="bdd0c-158">Test the JEA endpoint</span></span>](using-jea.md)
