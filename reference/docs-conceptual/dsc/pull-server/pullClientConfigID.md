---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Configurar um cliente de pull usando IDs de configuração no PowerShell 5.0 e posterior
description: Este artigo explica como configurar um cliente de pull usando IDs de configuração no PowerShell 5.0 e posterior
ms.openlocfilehash: 601858c08ce9a893a8941823d27fef3a60882b48
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664308"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-50-and-later"></a><span data-ttu-id="5cab9-104">Configurar um cliente de pull usando IDs de configuração no PowerShell 5.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="5cab9-104">Set up a Pull Client using Configuration IDs in PowerShell 5.0 and later</span></span>

> <span data-ttu-id="5cab9-105">Aplica-se a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="5cab9-105">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5cab9-106">O Servidor de Recepção (Recurso do Windows *Serviço DSC* ) é um componente compatível com o Windows Server, no entanto, não há planos de oferecer novos recursos ou funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="5cab9-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="5cab9-107">É recomendável começar a fazer a transição dos clientes gerenciados para o [DSC de Automação do Azure](/azure/automation/automation-dsc-getting-started) (inclui recursos além do Servidor de Recepção no Windows Server) ou para uma das soluções da comunidade listadas [aqui](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="5cab9-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="5cab9-108">Antes de configurar um cliente de pull, você deve configurar um servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="5cab9-108">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="5cab9-109">Embora essa ordem não seja obrigatória, ela ajuda na solução de problemas e ajuda a garantir que o registro seja bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="5cab9-109">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="5cab9-110">Para configurar um servidor de pull, você pode usar os guias a seguir:</span><span class="sxs-lookup"><span data-stu-id="5cab9-110">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="5cab9-111">Configurar um servidor de pull SMB de DSC</span><span class="sxs-lookup"><span data-stu-id="5cab9-111">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="5cab9-112">Configurar um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="5cab9-112">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="5cab9-113">Cada nó de destino pode ser configurado para baixar configurações, recursos e até mesmo relatar seu status.</span><span class="sxs-lookup"><span data-stu-id="5cab9-113">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="5cab9-114">As seções a seguir mostram como configurar um cliente de pull com um compartilhamento SMB ou servidor de pull de DSC HTTP.</span><span class="sxs-lookup"><span data-stu-id="5cab9-114">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="5cab9-115">Quando o nó do LCM for atualizado, ele entrará em contato com a localização configurada para baixar as configurações atribuídas.</span><span class="sxs-lookup"><span data-stu-id="5cab9-115">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="5cab9-116">Se algum dos recursos necessários não existir no nó, ele será baixado automaticamente da localização configurada.</span><span class="sxs-lookup"><span data-stu-id="5cab9-116">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="5cab9-117">Se o nó for configurado com um [Servidor de relatório](reportServer.md), ele relatará o status da operação.</span><span class="sxs-lookup"><span data-stu-id="5cab9-117">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

> [!NOTE]
> <span data-ttu-id="5cab9-118">Este tópico se aplica ao PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="5cab9-118">This topic applies to PowerShell 5.0.</span></span> <span data-ttu-id="5cab9-119">Para obter informações sobre como configurar um cliente de pull no PowerShell 4.0, consulte [Configurando um cliente de pull usando uma ID de configuração no PowerShell 4.0](pullClientConfigID4.md)</span><span class="sxs-lookup"><span data-stu-id="5cab9-119">For information on setting up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="5cab9-120">Configurar o LCM do cliente de pull</span><span class="sxs-lookup"><span data-stu-id="5cab9-120">Configure the pull client LCM</span></span>

<span data-ttu-id="5cab9-121">A execução de qualquer um dos exemplos abaixo cria uma nova pasta de saída denominada **PullClientConfigID** e coloca nela um arquivo MOF de metaconfiguração.</span><span class="sxs-lookup"><span data-stu-id="5cab9-121">Executing any of the examples below creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="5cab9-122">Nesse caso, o arquivo MOF de metaconfiguração será nomeado `localhost.meta.mof`.</span><span class="sxs-lookup"><span data-stu-id="5cab9-122">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="5cab9-123">Para aplicar a configuração, chame o cmdlet **Set-DscLocalConfigurationManager** , com **Path** definido como a localização do arquivo MOF de metaconfiguração.</span><span class="sxs-lookup"><span data-stu-id="5cab9-123">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="5cab9-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5cab9-124">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a><span data-ttu-id="5cab9-125">ID de configuração</span><span class="sxs-lookup"><span data-stu-id="5cab9-125">Configuration ID</span></span>

<span data-ttu-id="5cab9-126">Os exemplos abaixo definem a propriedade **ConfigurationID** do LCM para um **Guid** criado anteriormente para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="5cab9-126">The examples below sets the **ConfigurationID** property of the LCM to a **Guid** that had been previously created for this purpose.</span></span> <span data-ttu-id="5cab9-127">O **ConfigurationID** é usado pelo LCM para localizar a configuração apropriada no servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="5cab9-127">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="5cab9-128">O arquivo MOF de configuração no servidor de pull deve ser nomeado como `ConfigurationID.mof`, em que *ConfigurationID* é o valor da propriedade **ConfigurationID** do nó de destino do LCM.</span><span class="sxs-lookup"><span data-stu-id="5cab9-128">The configuration MOF file on the pull server must be named `ConfigurationID.mof`, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="5cab9-129">Para obter mais informações, confira [Publicar configurações em um servidor de pull (v4/v5)](publishConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="5cab9-129">For more information see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

<span data-ttu-id="5cab9-130">Você pode criar um **Guid** aleatório usando o exemplo abaixo ou usando o cmdlet [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid).</span><span class="sxs-lookup"><span data-stu-id="5cab9-130">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="5cab9-131">Para obter mais informações sobre o uso de **Guids** em seu ambiente, confira [Plan for Guids](secureserver.md#guids) (Planejar-se para usar Guids).</span><span class="sxs-lookup"><span data-stu-id="5cab9-131">For more information about using **Guids** in your environment, see [Plan for Guids](secureserver.md#guids).</span></span>

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="5cab9-132">Configurar um cliente de pull para baixar configurações</span><span class="sxs-lookup"><span data-stu-id="5cab9-132">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="5cab9-133">Cada cliente deve ser configurado no modo **Pull** e receber a URL do servidor de pull em que sua configuração está armazenada.</span><span class="sxs-lookup"><span data-stu-id="5cab9-133">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="5cab9-134">Para fazer isso, você precisa configurar o Gerenciador de Configurações Local (LCM) com as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="5cab9-134">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="5cab9-135">Para configurar o LCM, é criado um tipo especial de configuração, decorada com o atributo **DSCLocalConfigurationManager**.</span><span class="sxs-lookup"><span data-stu-id="5cab9-135">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="5cab9-136">Para obter mais informações sobre como configurar o LCM, consulte [Configurando o Gerenciador de Configurações Local](../managing-nodes/metaConfig.md).</span><span class="sxs-lookup"><span data-stu-id="5cab9-136">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="5cab9-137">Servidor de pull de DSC HTTP</span><span class="sxs-lookup"><span data-stu-id="5cab9-137">HTTP DSC Pull Server</span></span>

<span data-ttu-id="5cab9-138">O script a seguir configura o LCM para efetuar o pull de configurações de um servidor chamado "CONTOSO-PullSrv".</span><span class="sxs-lookup"><span data-stu-id="5cab9-138">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }
    }
}
PullClientConfigID
```

<span data-ttu-id="5cab9-139">No script, o bloco **ConfigurationRepositoryWeb** define o servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="5cab9-139">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="5cab9-140">A **ServerUrl** especifica a URL do Pull de DSC</span><span class="sxs-lookup"><span data-stu-id="5cab9-140">The **ServerUrl** specifies the url of the DSC Pull</span></span>

### <a name="smb-share"></a><span data-ttu-id="5cab9-141">Compartilhamento SMB</span><span class="sxs-lookup"><span data-stu-id="5cab9-141">SMB Share</span></span>

<span data-ttu-id="5cab9-142">O script a seguir configura o LCM para efetuar o pull de configurações do Compartilhamento SMB `\\SMBPullServer\Pull`.</span><span class="sxs-lookup"><span data-stu-id="5cab9-142">The following script configures the LCM to pull configurations from the SMB Share `\\SMBPullServer\Pull`.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\Pull'
        }
    }
}
PullClientConfigID
```

<span data-ttu-id="5cab9-143">No script, o bloco **ConfigurationRepositoryShare** define o servidor de pull, que nesse caso é apenas um compartilhamento SMB.</span><span class="sxs-lookup"><span data-stu-id="5cab9-143">In the script, the **ConfigurationRepositoryShare** block defines the pull server, which in this case, is just an SMB share.</span></span>

## <a name="set-up-a-pull-client-to-download-resources"></a><span data-ttu-id="5cab9-144">Configurar um cliente de pull para baixar recursos</span><span class="sxs-lookup"><span data-stu-id="5cab9-144">Set up a Pull Client to download Resources</span></span>

<span data-ttu-id="5cab9-145">Se você especificar apenas o bloco **ConfigurationRepositoryWeb** ou **ConfigurationRepositoryShare** em sua configuração do LCM (como no exemplo anterior), o cliente de pull efetuará pull dos recursos da mesma localização da qual recupera suas configurações.</span><span class="sxs-lookup"><span data-stu-id="5cab9-145">If you specify only the **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous examples), the pull client will pull resources from the same location it retrieves its configurations.</span></span> <span data-ttu-id="5cab9-146">Você também pode especificar locais separados para os recursos.</span><span class="sxs-lookup"><span data-stu-id="5cab9-146">You can also specify separate locations for resources.</span></span> <span data-ttu-id="5cab9-147">Para especificar uma localização de recurso como um servidor separado, use o bloco **ResourceRepositoryWeb**.</span><span class="sxs-lookup"><span data-stu-id="5cab9-147">To specify a resource location as a separate server, use the **ResourceRepositoryWeb** block.</span></span> <span data-ttu-id="5cab9-148">Para especificar uma localização de recurso como um compartilhamento SMB, use o bloco **ResourceRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="5cab9-148">To specify a resource location as an SMB share, use the **ResourceRepositoryShare** block.</span></span>

> [!NOTE]
> <span data-ttu-id="5cab9-149">Você pode combinar **ConfigurationRepositoryWeb** com **ResourceRepositoryShare** ou **ConfigurationRepositoryShare** com **ResourceRepositoryWeb**.</span><span class="sxs-lookup"><span data-stu-id="5cab9-149">You can combine **ConfigurationRepositoryWeb** with **ResourceRepositoryShare** or **ConfigurationRepositoryShare** with **ResourceRepositoryWeb**.</span></span> <span data-ttu-id="5cab9-150">Exemplos disso não são mostrados abaixo.</span><span class="sxs-lookup"><span data-stu-id="5cab9-150">Examples of this are not shown below.</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="5cab9-151">Servidor de pull de DSC HTTP</span><span class="sxs-lookup"><span data-stu-id="5cab9-151">HTTP DSC Pull Server</span></span>

<span data-ttu-id="5cab9-152">A metaconfiguração a seguir configura um cliente de pull para obter suas configurações de **CONTOSO-PullSrv** e seus recursos de **CONTOSO-ResourceSrv**.</span><span class="sxs-lookup"><span data-stu-id="5cab9-152">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

### <a name="smb-share"></a><span data-ttu-id="5cab9-153">Compartilhamento SMB</span><span class="sxs-lookup"><span data-stu-id="5cab9-153">SMB Share</span></span>

<span data-ttu-id="5cab9-154">O exemplo a seguir mostra uma metaconfiguração que configura um cliente para efetuar pull de configurações do compartilhamento SMB `\\SMBPullServer\Configurations` e de recursos do compartilhamento SMB `\\SMBPullServer\Resources`.</span><span class="sxs-lookup"><span data-stu-id="5cab9-154">The following example shows a metaconfiguration that sets up a client to pull configurations from the SMB share `\\SMBPullServer\Configurations`, and resources from the SMB share `\\SMBPullServer\Resources`.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\Configurations'
        }

        ResourceRepositoryShare SMBResourceServer
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigID
```

#### <a name="automatically-download-resources-in-push-mode"></a><span data-ttu-id="5cab9-155">Baixar recursos automaticamente no modo de envio por push</span><span class="sxs-lookup"><span data-stu-id="5cab9-155">Automatically download Resources in Push Mode</span></span>

<span data-ttu-id="5cab9-156">Começando no PowerShell 5.0, seus clientes de pull podem baixar módulos de um compartilhamento SMB, mesmo quando eles estão configurados para o modo de envio por **Push**.</span><span class="sxs-lookup"><span data-stu-id="5cab9-156">Beginning in PowerShell 5.0, your pull clients can download modules from an SMB share, even when they are configured for **Push** mode.</span></span> <span data-ttu-id="5cab9-157">Isso é especialmente útil em cenários em que você não quer configurar um servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="5cab9-157">This is especially useful in scenarios where you do not want to set up a Pull Server.</span></span> <span data-ttu-id="5cab9-158">O bloco **ResourceRepositoryShare** pode ser usado sem especificar um **ConfigurationRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="5cab9-158">The **ResourceRepositoryShare** block can be used without specifying a **ConfigurationRepositoryShare**.</span></span> <span data-ttu-id="5cab9-159">O exemplo a seguir mostra uma metaconfiguração que configura um cliente para efetuar pull de recursos de um compartilhamento SMB `\\SMBPullServer\Resources`.</span><span class="sxs-lookup"><span data-stu-id="5cab9-159">The following example shows a metaconfiguration that sets up a client to pull resources from an SMB Share `\\SMBPullServer\Resources`.</span></span> <span data-ttu-id="5cab9-160">Quando o nó é **RECEBE** uma configuração por push, ele baixa automaticamente todos os recursos necessários do compartilhamento especificado.</span><span class="sxs-lookup"><span data-stu-id="5cab9-160">When the Node is **PUSHED** a configuration, it will automatically download any required resources, from the share specified.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Push'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
        }

        ResourceRepositoryShare SMBResourceServer
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigID
```

## <a name="set-up-a-pull-client-to-report-status"></a><span data-ttu-id="5cab9-161">Configurar um cliente de pull para relatar o status</span><span class="sxs-lookup"><span data-stu-id="5cab9-161">Set up a Pull Client to report status</span></span>

<span data-ttu-id="5cab9-162">Por padrão, os nós não enviam relatórios a um servidor de pull configurado.</span><span class="sxs-lookup"><span data-stu-id="5cab9-162">By default, Nodes will not send reports to a configured Pull Server.</span></span> <span data-ttu-id="5cab9-163">Você pode usar um único servidor de pull para emissão de relatórios, recursos e configurações, mas é preciso criar um bloco **ReportRepositoryWeb** para configurar o relatório.</span><span class="sxs-lookup"><span data-stu-id="5cab9-163">You can use a single pull server for configurations, resources, and reporting, but you have to create a **ReportRepositoryWeb** block to set up reporting.</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="5cab9-164">Servidor de pull de DSC HTTP</span><span class="sxs-lookup"><span data-stu-id="5cab9-164">HTTP DSC Pull Server</span></span>

<span data-ttu-id="5cab9-165">O exemplo a seguir mostra uma metaconfiguração que configura um cliente para efetuar pull de recursos e configurações, além de enviar dados de relatórios, para um único servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="5cab9-165">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

<span data-ttu-id="5cab9-166">Para especificar um servidor de relatório, utilize um bloco **ReportRepositoryWeb**.</span><span class="sxs-lookup"><span data-stu-id="5cab9-166">To specify a report server, you use a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="5cab9-167">Um servidor de relatório não pode ser um servidor de SMB.</span><span class="sxs-lookup"><span data-stu-id="5cab9-167">A report server cannot be an SMB server.</span></span> <span data-ttu-id="5cab9-168">A metaconfiguração a seguir configura um cliente de pull para obter suas configurações de **CONTOSO-PullSrv** e seus recursos de **CONTOSO-ResourceSrv** , bem como enviar relatórios de status para **CONTOSO-ReportSrv** :</span><span class="sxs-lookup"><span data-stu-id="5cab9-168">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv** , and to send status reports to **CONTOSO-ReportSrv** :</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

### <a name="smb-share"></a><span data-ttu-id="5cab9-169">Compartilhamento SMB</span><span class="sxs-lookup"><span data-stu-id="5cab9-169">SMB Share</span></span>

<span data-ttu-id="5cab9-170">Um servidor de relatório não pode ser um compartilhamento SMB.</span><span class="sxs-lookup"><span data-stu-id="5cab9-170">A report server cannot be an SMB share.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5cab9-171">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5cab9-171">Next Steps</span></span>

<span data-ttu-id="5cab9-172">Após o cliente de pull ser configurado, você pode usar os guias a seguir para executar as próximas etapas:</span><span class="sxs-lookup"><span data-stu-id="5cab9-172">Once the pull client has been configured, you can use the following guides to perform the next steps:</span></span>

- [<span data-ttu-id="5cab9-173">Publicar configurações em um servidor de pull (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="5cab9-173">Publish Configurations to a Pull Server (v4/v5)</span></span>](publishConfigs.md)
- [<span data-ttu-id="5cab9-174">Empacotar e carregar recursos em um servidor de pull (v4)</span><span class="sxs-lookup"><span data-stu-id="5cab9-174">Package and Upload Resources to a Pull Server (v4)</span></span>](package-upload-resources.md)

## <a name="see-also"></a><span data-ttu-id="5cab9-175">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5cab9-175">See Also</span></span>

- [<span data-ttu-id="5cab9-176">Configurando um cliente de pull com nomes de configuração</span><span class="sxs-lookup"><span data-stu-id="5cab9-176">Setting up a pull client with configuration names</span></span>](pullClientConfigNames.md)
