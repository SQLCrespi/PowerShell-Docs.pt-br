---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Configurar um cliente de pull usando nomes de configuração no PowerShell 5.0 e posterior
description: O artigo explica como configurar um cliente de pull usando Nomes de configuração no PowerShell 5.0 e posterior
ms.openlocfilehash: db2b08605dd8bc7e48d9d5153861ce9b36118e21
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644918"
---
# <a name="set-up-a-pull-client-using-configuration-names-in-powershell-50-and-later"></a><span data-ttu-id="2d7cf-104">Configurar um cliente de pull usando nomes de configuração no PowerShell 5.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="2d7cf-104">Set up a Pull Client using Configuration Names in PowerShell 5.0 and later</span></span>

> <span data-ttu-id="2d7cf-105">Aplica-se a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="2d7cf-105">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d7cf-106">O Servidor de Recepção (Recurso do Windows *Serviço DSC* ) é um componente compatível com o Windows Server, no entanto, não há planos de oferecer novos recursos ou funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="2d7cf-107">É recomendável começar a fazer a transição dos clientes gerenciados para o [DSC de Automação do Azure](/azure/automation/automation-dsc-getting-started) (inclui recursos além do Servidor de Recepção no Windows Server) ou para uma das soluções da comunidade listadas [aqui](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="2d7cf-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="2d7cf-108">Antes de configurar um cliente de pull, você deve configurar um servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-108">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="2d7cf-109">Embora essa ordem não seja obrigatória, ela ajuda na solução de problemas e ajuda a garantir que o registro seja bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-109">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="2d7cf-110">Para configurar um servidor de pull, você pode usar os guias a seguir:</span><span class="sxs-lookup"><span data-stu-id="2d7cf-110">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="2d7cf-111">Configurar um servidor de pull SMB de DSC</span><span class="sxs-lookup"><span data-stu-id="2d7cf-111">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="2d7cf-112">Configurar um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="2d7cf-112">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="2d7cf-113">Cada nó de destino pode ser configurado para baixar configurações, recursos e até mesmo relatar seu status.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-113">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="2d7cf-114">As seções a seguir mostram como configurar um cliente de pull com um compartilhamento SMB ou servidor de pull de DSC HTTP.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-114">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="2d7cf-115">Quando o nó do LCM for atualizado, ele entrará em contato com a localização configurada para baixar as configurações atribuídas.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-115">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="2d7cf-116">Se algum dos recursos necessários não existir no nó, ele será baixado automaticamente da localização configurada.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-116">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="2d7cf-117">Se o nó for configurado com um [Servidor de relatório](reportServer.md), ele relatará o status da operação.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-117">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

> [!NOTE]
> <span data-ttu-id="2d7cf-118">Este tópico se aplica ao PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-118">This topic applies to PowerShell 5.0.</span></span> <span data-ttu-id="2d7cf-119">Para obter informações sobre como configurar um cliente de pull no PowerShell 4.0, confira [Configurar um cliente de pull usando uma ID de configuração no PowerShell 4.0](pullClientConfigID4.md)</span><span class="sxs-lookup"><span data-stu-id="2d7cf-119">For information on setting up a pull client in PowerShell 4.0, see [Set up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="2d7cf-120">Configurar o LCM do cliente de pull</span><span class="sxs-lookup"><span data-stu-id="2d7cf-120">Configure the pull client LCM</span></span>

<span data-ttu-id="2d7cf-121">A execução de qualquer um dos exemplos abaixo cria uma nova pasta de saída denominada **PullClientConfigName** e coloca nela um arquivo MOF de metaconfiguração.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-121">Executing any of the examples below creates a new output folder named **PullClientConfigName** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="2d7cf-122">Nesse caso, o arquivo MOF de metaconfiguração será nomeado `localhost.meta.mof`.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-122">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="2d7cf-123">Para aplicar a configuração, chame o cmdlet **Set-DscLocalConfigurationManager** , com **Path** definido como a localização do arquivo MOF de metaconfiguração.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-123">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="2d7cf-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2d7cf-124">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigName –Verbose.
```

## <a name="configuration-name"></a><span data-ttu-id="2d7cf-125">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="2d7cf-125">Configuration Name</span></span>

<span data-ttu-id="2d7cf-126">Os exemplos a seguir definem a propriedade **ConfigurationName** do LCM como o nome de uma configuração compilada anteriormente, criada para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-126">The examples below sets the **ConfigurationName** property of the LCM to the name of a previously compiled Configuration, created for this purpose.</span></span> <span data-ttu-id="2d7cf-127">O **ConfigurationName** é usado pelo LCM para localizar a configuração apropriada no servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-127">The **ConfigurationName** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="2d7cf-128">O arquivo MOF da configuração no servidor de pull deve ser denominado `<ConfigurationName>.mof`, nesse caso, "ClientConfig.mof".</span><span class="sxs-lookup"><span data-stu-id="2d7cf-128">The configuration MOF file on the pull server must be named `<ConfigurationName>.mof`, in this case, "ClientConfig.mof".</span></span> <span data-ttu-id="2d7cf-129">Para obter mais informações, confira [Publicar configurações em um servidor de pull (v4/v5)](publishConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="2d7cf-129">For more information, see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="2d7cf-130">Configurar um cliente de pull para baixar configurações</span><span class="sxs-lookup"><span data-stu-id="2d7cf-130">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="2d7cf-131">Cada cliente deve ser configurado no modo **Pull** e receber a URL do servidor de pull em que sua configuração está armazenada.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-131">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="2d7cf-132">Para fazer isso, você precisa configurar o Gerenciador de Configurações Local (LCM) com as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-132">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="2d7cf-133">Para configurar o LCM, é criado um tipo especial de configuração, decorada com o atributo **DSCLocalConfigurationManager**.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-133">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="2d7cf-134">Para obter mais informações sobre como configurar o LCM, consulte [Configurando o Gerenciador de Configurações Local](../managing-nodes/metaConfig.md).</span><span class="sxs-lookup"><span data-stu-id="2d7cf-134">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

<span data-ttu-id="2d7cf-135">O script a seguir configura o LCM para efetuar o pull de configurações de um servidor chamado "CONTOSO-PullSrv".</span><span class="sxs-lookup"><span data-stu-id="2d7cf-135">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

- <span data-ttu-id="2d7cf-136">No script, o bloco **ConfigurationRepositoryWeb** define o servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-136">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="2d7cf-137">A propriedade **ServerURL** especifica o ponto de extremidade para o servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-137">The **ServerURL** property specifies the endpoint for the pull server.</span></span>

- <span data-ttu-id="2d7cf-138">A propriedade **RegistrationKey** é uma chave compartilhada entre todos os nós de cliente para um servidor de pull e esse servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-138">The **RegistrationKey** property is a shared key between all client nodes for a pull server and that pull server.</span></span> <span data-ttu-id="2d7cf-139">O mesmo valor é armazenado em um arquivo no servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-139">The same value is stored in a file on the pull server.</span></span><span data-ttu-id="2d7cf-140"> > [!NOTE] > As chaves de registro funcionam apenas com servidores de pull da **Web**.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-140"> > [!NOTE] > Registration keys work only with **web** pull servers.</span></span> <span data-ttu-id="2d7cf-141">Você ainda deve usar **ConfigurationID** com um servidor de pull de **SMB**.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-141">You must still use **ConfigurationID** with an **SMB** pull server.</span></span> <span data-ttu-id="2d7cf-142">> Para obter informações sobre como configurar um servidor de pull usando **ConfigurationID** , confira [Configurar um cliente de pull usando uma ID de configuração](pullClientConfigId.md)</span><span class="sxs-lookup"><span data-stu-id="2d7cf-142">> For information about configuring a pull server by using **ConfigurationID** , see [Setting up a pull client using configuration ID](pullClientConfigId.md)</span></span>

- <span data-ttu-id="2d7cf-143">A propriedade **ConfigurationNames** em uma matriz que especifica os nomes das configurações destinadas ao nó do cliente.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-143">The **ConfigurationNames** property is an array that specifies the names of the configurations intended for the client node.</span></span><span data-ttu-id="2d7cf-144"> >**Observação:** Se você especificar mais de um valor em **ConfigurationNames** , também será necessário especificar blocos **PartialConfiguration** na configuração.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-144"> >**Note:** If you specify more than one value in the **ConfigurationNames** , you must also specify **PartialConfiguration** blocks in your configuration.</span></span> <span data-ttu-id="2d7cf-145">> Para obter informações sobre configurações parciais, veja [Configurações parciais do Desired State Configuration do PowerShell](partialConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="2d7cf-145">>For information about partial configurations, see [PowerShell Desired State Configuration partial configurations](partialConfigs.md).</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
            ConfigurationNames = @('ClientConfig')
        }
    }
}
PullClientConfigNames
```

## <a name="set-up-a-pull-client-to-download-resources"></a><span data-ttu-id="2d7cf-146">Configurar um cliente de pull para baixar recursos</span><span class="sxs-lookup"><span data-stu-id="2d7cf-146">Set up a Pull Client to download Resources</span></span>

<span data-ttu-id="2d7cf-147">Se você especificar apenas um bloco **ConfigurationRepositoryWeb** ou **ConfigurationRepositoryShare** em sua configuração LCM (como no exemplo anterior), o cliente de pull efetuará pull dos recursos na mesma localização em que seus arquivos “.mof” estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-147">If you specify only a **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous example), the pull client will pull resources from same location where your ".mof" files are stored.</span></span> <span data-ttu-id="2d7cf-148">Você também pode especificar locais diferentes nos quais os clientes podem baixar recursos.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-148">You can also specify different locations where clients can download resources.</span></span> <span data-ttu-id="2d7cf-149">Para especificar um servidor de recurso, utilize um bloco **ResourceRepositoryWeb** (para um servidor de pull da Web) ou um bloco **ResourceRepositoryShare** (para um servidor de pull de SMB).</span><span class="sxs-lookup"><span data-stu-id="2d7cf-149">To specify a resource server, you use either a **ResourceRepositoryWeb** (for a web pull server) or a **ResourceRepositoryShare** block (for an SMB pull server).</span></span>

<span data-ttu-id="2d7cf-150">O exemplo a seguir mostra uma metaconfiguração que configura um cliente para baixar configurações de um servidor de pull e recursos de um compartilhamento SMB.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-150">The following example shows a metaconfiguration that sets up a client to download configurations from a Pull Server, and resources from an SMB share.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }

        ResourceRepositoryShare SMBResources
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigNames
```

## <a name="set-up-a-pull-client-to-report-status"></a><span data-ttu-id="2d7cf-151">Configurar um cliente de pull para relatar o status</span><span class="sxs-lookup"><span data-stu-id="2d7cf-151">Set up a Pull Client to report status</span></span>

<span data-ttu-id="2d7cf-152">Você pode usar um único servidor de pull para emissão de relatórios, recursos e configurações.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-152">You can use a single pull server for configurations, resources, and reporting.</span></span> <span data-ttu-id="2d7cf-153">A emissão de relatórios não está configurada para os clientes por padrão.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-153">Reporting is not configured for clients by default.</span></span> <span data-ttu-id="2d7cf-154">Para configurar um cliente para relatar o status, você precisa criar um bloco **ReportRepositoryWeb**.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-154">To configure a client to report status, you have to create a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="2d7cf-155">O exemplo a seguir mostra uma metaconfiguração que configura um cliente para efetuar pull de recursos e configurações, além de enviar dados de relatórios, para um único servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-155">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

> [!NOTE]
> <span data-ttu-id="2d7cf-156">Um servidor de relatório não pode ser um compartilhamento SMB.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-156">A report server cannot be an SMB share.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }
    }
}
PullClientConfigNames
```

## <a name="see-also"></a><span data-ttu-id="2d7cf-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d7cf-157">See Also</span></span>

- [<span data-ttu-id="2d7cf-158">Configurando um cliente de pull com uma ID de configuração</span><span class="sxs-lookup"><span data-stu-id="2d7cf-158">Setting up a pull client with configuration ID</span></span>](PullClientConfigNames.md)
- [<span data-ttu-id="2d7cf-159">Configurando um servidor de pull da Web de DSC</span><span class="sxs-lookup"><span data-stu-id="2d7cf-159">Setting up a DSC web pull server</span></span>](pullServer.md)
