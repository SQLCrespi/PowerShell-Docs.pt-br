---
ms.date: 01/08/2020
keywords: DSC,powershell,configuração,instalação
title: Serviço de Pull de DSC
ms.openlocfilehash: c4e725569db776fe0dbd5395b2f0f8b8e70cbbeb
ms.sourcegitcommit: 105c69ecedfe5180d8c12e8015d667c5f1a71579
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85837470"
---
# <a name="desired-state-configuration-pull-service"></a><span data-ttu-id="d2334-103">Serviço de Pull de Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="d2334-103">Desired State Configuration Pull Service</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2334-104">O Servidor de Recepção (Recurso do Windows *Serviço DSC*) é um componente compatível com o Windows Server, no entanto, não há planos de oferecer novos recursos ou funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="d2334-104">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="d2334-105">É recomendável começar a fazer a transição dos clientes gerenciados para o [DSC de Automação do Azure](/azure/automation/automation-dsc-getting-started) (inclui recursos além do Servidor de Recepção no Windows Server) ou para uma das soluções da comunidade listadas [aqui](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="d2334-105">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="d2334-106">O LCM (Gerenciador de Configurações Local) pode ser gerenciado centralmente por uma solução de Serviço de Pull.</span><span class="sxs-lookup"><span data-stu-id="d2334-106">Local Configuration Manager (LCM) can be centrally managed by a Pull Service solution.</span></span> <span data-ttu-id="d2334-107">Ao usar essa abordagem, o nó que está sendo gerenciado é registrado com um serviço e uma configuração é atribuída a ele em configurações de LCM.</span><span class="sxs-lookup"><span data-stu-id="d2334-107">When using this approach, the node that is being managed is registered with a service and assigned a configuration in LCM settings.</span></span> <span data-ttu-id="d2334-108">A configuração e todos os recursos de DSC necessários como dependências para a configuração são baixados para o computador e usados pelo LCM para gerenciar a configuração.</span><span class="sxs-lookup"><span data-stu-id="d2334-108">The configuration and all DSC resources needed as dependencies for the configuration are downloaded to the machine and used by LCM to manage the configuration.</span></span> <span data-ttu-id="d2334-109">As informações sobre o estado do computador que está sendo gerenciado são carregadas no serviço para relatório.</span><span class="sxs-lookup"><span data-stu-id="d2334-109">Information about the state of the machine being managed is uploaded to the service for reporting.</span></span> <span data-ttu-id="d2334-110">Esse conceito é conhecido como "serviço de pull".</span><span class="sxs-lookup"><span data-stu-id="d2334-110">This concept is referred to as "pull service".</span></span>

<span data-ttu-id="d2334-111">As opções atuais para o serviço de pull incluem:</span><span class="sxs-lookup"><span data-stu-id="d2334-111">The current options for pull service include:</span></span>

- <span data-ttu-id="d2334-112">Serviço de Configuração de Estado Desejado da Automação do Azure</span><span class="sxs-lookup"><span data-stu-id="d2334-112">Azure Automation Desired State Configuration service</span></span>
- <span data-ttu-id="d2334-113">Um serviço de pull em execução no Windows Server</span><span class="sxs-lookup"><span data-stu-id="d2334-113">A pull service running on Windows Server</span></span>
- <span data-ttu-id="d2334-114">Soluções de software livre mantidas pela comunidade</span><span class="sxs-lookup"><span data-stu-id="d2334-114">Community maintained open-source solutions</span></span>
- <span data-ttu-id="d2334-115">Um compartilhamento SMB</span><span class="sxs-lookup"><span data-stu-id="d2334-115">An SMB share</span></span>

<span data-ttu-id="d2334-116">A escala recomendada para cada solução é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="d2334-116">The recommended scale for each solution is as follows:</span></span>

|                   <span data-ttu-id="d2334-117">Solução</span><span class="sxs-lookup"><span data-stu-id="d2334-117">Solution</span></span>                   |              <span data-ttu-id="d2334-118">Nós clientes</span><span class="sxs-lookup"><span data-stu-id="d2334-118">Client nodes</span></span>              |
| -------------------------------------------- | -------------------------------------- |
| <span data-ttu-id="d2334-119">Servidor de Pull do Windows usando o banco de dados MDB/ESENT</span><span class="sxs-lookup"><span data-stu-id="d2334-119">Windows Pull Server using MDB/ESENT database</span></span> | <span data-ttu-id="d2334-120">Até 500 nós</span><span class="sxs-lookup"><span data-stu-id="d2334-120">Up to 500 nodes</span></span>                        |
| <span data-ttu-id="d2334-121">Servidor de Pull do Windows usando o banco de dados SQL</span><span class="sxs-lookup"><span data-stu-id="d2334-121">Windows Pull Server using SQL database</span></span>       | <span data-ttu-id="d2334-122">Até 3.500 nós</span><span class="sxs-lookup"><span data-stu-id="d2334-122">Up to 3500 nodes</span></span>                       |
| <span data-ttu-id="d2334-123">DSC de Automação do Azure</span><span class="sxs-lookup"><span data-stu-id="d2334-123">Azure Automation DSC</span></span>                         | <span data-ttu-id="d2334-124">Ambientes pequenos e grandes</span><span class="sxs-lookup"><span data-stu-id="d2334-124">Both small and large environments</span></span>      |

<span data-ttu-id="d2334-125">**A solução recomendada**, e a opção com a maioria dos recursos disponíveis, é [DSC de Automação do Azure](/azure/automation/automation-dsc-getting-started).</span><span class="sxs-lookup"><span data-stu-id="d2334-125">**The recommended solution**, and the option with the most features available, is [Azure Automation DSC](/azure/automation/automation-dsc-getting-started).</span></span> <span data-ttu-id="d2334-126">Não foi identificado um limite superior para o número de nós por Conta de Automação.</span><span class="sxs-lookup"><span data-stu-id="d2334-126">An upper limit for number of nodes per Automation Account has not been identified.</span></span>

<span data-ttu-id="d2334-127">O serviço do Azure pode gerenciar nós localmente em datacenters privados ou em nuvens públicas, como AWS e o Azure.</span><span class="sxs-lookup"><span data-stu-id="d2334-127">The Azure service can manage nodes on-premises in private datacenters, or in public clouds such as Azure and AWS.</span></span> <span data-ttu-id="d2334-128">Para ambientes privados, onde os servidores não podem se conectar diretamente à Internet, considere limitar o tráfego de saída apenas ao intervalo de IPs do Azure publicado (consulte [Intervalos de IP de Datacenter do Azure](https://www.microsoft.com/download/details.aspx?id=41653)).</span><span class="sxs-lookup"><span data-stu-id="d2334-128">For private environments where servers cannot directly connect to the Internet, consider limiting outbound traffic to only the published Azure IP range (see [Azure Datacenter IP Ranges](https://www.microsoft.com/download/details.aspx?id=41653)).</span></span>

<span data-ttu-id="d2334-129">Entre os recursos do serviço online que não estão disponíveis no serviço de pull no Windows Server estão:</span><span class="sxs-lookup"><span data-stu-id="d2334-129">Features of the online service that are not currently available in the pull service on Windows Server include:</span></span>

- <span data-ttu-id="d2334-130">Todos os dados são criptografados em trânsito e em repouso</span><span class="sxs-lookup"><span data-stu-id="d2334-130">All data is encrypted in transit and at rest</span></span>
- <span data-ttu-id="d2334-131">Certificados de cliente são criados e gerenciados automaticamente</span><span class="sxs-lookup"><span data-stu-id="d2334-131">Client certificates are created and managed automatically</span></span>
- <span data-ttu-id="d2334-132">Armazenamento de segredos para gerenciar centralmente [senhas/credenciais](/azure/automation/automation-credentials), ou [variáveis](/azure/automation/automation-variables) como nomes de servidor ou cadeias de conexão</span><span class="sxs-lookup"><span data-stu-id="d2334-132">Secrets store for centrally managing [passwords/credentials](/azure/automation/automation-credentials), or [variables](/azure/automation/automation-variables) such as server names or connection strings</span></span>
- <span data-ttu-id="d2334-133">Gerenciar centralmente o nó [Configuração do LCM](../managing-nodes/metaConfig.md#basic-settings)</span><span class="sxs-lookup"><span data-stu-id="d2334-133">Centrally manage node [LCM configuration](../managing-nodes/metaConfig.md#basic-settings)</span></span>
- <span data-ttu-id="d2334-134">Atribuir centralmente configurações a nós do cliente</span><span class="sxs-lookup"><span data-stu-id="d2334-134">Centrally assign configurations to client nodes</span></span>
- <span data-ttu-id="d2334-135">Alterações na configuração de versão de "grupos canário" para teste antes de chegar à produção</span><span class="sxs-lookup"><span data-stu-id="d2334-135">Release configuration changes to "canary groups" for testing before reaching production</span></span>
- <span data-ttu-id="d2334-136">Relatório gráfico</span><span class="sxs-lookup"><span data-stu-id="d2334-136">Graphical reporting</span></span>
  - <span data-ttu-id="d2334-137">Detalhes de status no nível de granularidade de recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="d2334-137">Status detail at the DSC resource level of granularity</span></span>
  - <span data-ttu-id="d2334-138">Mensagens de erro detalhadas de computadores cliente para solução de problemas</span><span class="sxs-lookup"><span data-stu-id="d2334-138">Verbose error messages from client machines for troubleshooting</span></span>
- <span data-ttu-id="d2334-139">[Integração com o Azure Log Analytics](/azure/automation/automation-dsc-diagnostics) para alertas, tarefas automatizadas, aplicativo para Android/iOS para relatórios e alertas</span><span class="sxs-lookup"><span data-stu-id="d2334-139">[Integration with Azure Log Analytics](/azure/automation/automation-dsc-diagnostics) for alerting, automated tasks, Android/iOS app for reporting and alerting</span></span>

## <a name="dsc-pull-service-in-windows-server"></a><span data-ttu-id="d2334-140">Serviço de pull de DSC no Windows Server</span><span class="sxs-lookup"><span data-stu-id="d2334-140">DSC pull service in Windows Server</span></span>

<span data-ttu-id="d2334-141">É possível configurar um serviço de pull para ser executado no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="d2334-141">It is possible to configure a pull service to run on Windows Server.</span></span> <span data-ttu-id="d2334-142">Fique ciente de que a solução de serviço de pull incluída no Windows Server inclui apenas as funcionalidades de armazenamento de configurações/módulos para download e de captura de dados de relatório para um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d2334-142">Be advised that the pull service solution included in Windows Server includes only capabilities of storing configurations/modules for download and capturing report data into a database.</span></span> <span data-ttu-id="d2334-143">Ela não inclui muitas das funcionalidades oferecidas pelo serviço no Azure e, portanto, não é uma boa ferramenta para avaliar o modo como o serviço seria usado.</span><span class="sxs-lookup"><span data-stu-id="d2334-143">It does not include many of the capabilities offered by the service in Azure and so, is not a good tool for evaluating how the service would be used.</span></span>

<span data-ttu-id="d2334-144">O serviço de pull oferecido no Windows Server é um serviço Web no IIS que utiliza uma interface OData para disponibilizar arquivos de configuração DSC para nós de destino quando são pedidos por tais nós.</span><span class="sxs-lookup"><span data-stu-id="d2334-144">The pull service offered in Windows Server is a web service in IIS that uses an OData interface to make DSC configuration files available to target nodes when those nodes ask for them.</span></span>

<span data-ttu-id="d2334-145">Requisitos para usar um servidor de pull:</span><span class="sxs-lookup"><span data-stu-id="d2334-145">Requirements for using a pull server:</span></span>

- <span data-ttu-id="d2334-146">Um servidor que execute:</span><span class="sxs-lookup"><span data-stu-id="d2334-146">A server running:</span></span>
  - <span data-ttu-id="d2334-147">WMF/PowerShell 4.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="d2334-147">WMF/PowerShell 4.0 or greater</span></span>
  - <span data-ttu-id="d2334-148">Função de servidor do IIS</span><span class="sxs-lookup"><span data-stu-id="d2334-148">IIS server role</span></span>
  - <span data-ttu-id="d2334-149">Serviço de DSC</span><span class="sxs-lookup"><span data-stu-id="d2334-149">DSC Service</span></span>
- <span data-ttu-id="d2334-150">Idealmente, alguns meios de gerar um certificado para proteger as credenciais passadas para o Gerenciador de Configurações Local (LCM) em nós de destino</span><span class="sxs-lookup"><span data-stu-id="d2334-150">Ideally, some means of generating a certificate, to secure credentials passed to the Local Configuration Manager (LCM) on target nodes</span></span>

<span data-ttu-id="d2334-151">A melhor maneira de configurar o Windows Server para hospedar o serviço de pull é usar uma configuração DSC.</span><span class="sxs-lookup"><span data-stu-id="d2334-151">The best way to configure Windows Server to host pull service is to use a DSC configuration.</span></span> <span data-ttu-id="d2334-152">Um script de exemplo é fornecido abaixo.</span><span class="sxs-lookup"><span data-stu-id="d2334-152">An example script is provided below.</span></span>

### <a name="supported-database-systems"></a><span data-ttu-id="d2334-153">Sistemas de banco de dados com suporte</span><span class="sxs-lookup"><span data-stu-id="d2334-153">Supported database systems</span></span>

| <span data-ttu-id="d2334-154">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="d2334-154">WMF 4.0</span></span> |       <span data-ttu-id="d2334-155">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="d2334-155">WMF 5.0</span></span>        |       <span data-ttu-id="d2334-156">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="d2334-156">WMF 5.1</span></span>        | <span data-ttu-id="d2334-157">WMF 5.1 (Windows Server Insider Preview 17090)</span><span class="sxs-lookup"><span data-stu-id="d2334-157">WMF 5.1 (Windows Server Insider Preview 17090)</span></span> |
| ------- | -------------------- | -------------------- | ---------------------------------------------- |
| <span data-ttu-id="d2334-158">MDB</span><span class="sxs-lookup"><span data-stu-id="d2334-158">MDB</span></span>     | <span data-ttu-id="d2334-159">ESENT (padrão), MDB</span><span class="sxs-lookup"><span data-stu-id="d2334-159">ESENT (Default), MDB</span></span> | <span data-ttu-id="d2334-160">ESENT (padrão), MDB</span><span class="sxs-lookup"><span data-stu-id="d2334-160">ESENT (Default), MDB</span></span> | <span data-ttu-id="d2334-161">ESENT (padrão), SQL Server, MDB</span><span class="sxs-lookup"><span data-stu-id="d2334-161">ESENT (Default), SQL Server, MDB</span></span>               |

<span data-ttu-id="d2334-162">A partir da versão 17090 do Windows Server, o SQL Server é uma opção compatível com o serviço de pull (Recurso do Windows *Serviço DSC*).</span><span class="sxs-lookup"><span data-stu-id="d2334-162">Starting in release 17090 of Windows Server, SQL Server is a supported option for the Pull Service (Windows Feature *DSC-Service*).</span></span> <span data-ttu-id="d2334-163">Essa é uma nova opção para dimensionar grandes ambientes de DSC que não foram migrados para o [DSC de Automação do Azure](/azure/automation/automation-dsc-getting-started).</span><span class="sxs-lookup"><span data-stu-id="d2334-163">This provides a new option for scaling large DSC environments that have not migrated to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started).</span></span>

> [!NOTE]
> <span data-ttu-id="d2334-164">O suporte ao SQL Server não será adicionado às versões anteriores do WMF 5.1 (ou mais antigas) e só estará disponível nas versões do Windows Server maiores ou iguais à 17090.</span><span class="sxs-lookup"><span data-stu-id="d2334-164">SQL Server support will not be added to previous versions of WMF 5.1 (or earlier) and will only be available on Windows Server versions greater than or equal to 17090.</span></span>

<span data-ttu-id="d2334-165">Para configurar o servidor de recepção para usar o SQL Server, defina **SqlProvider** para `$true` e **SqlConnectionString** para uma cadeia de conexão válida do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d2334-165">To configure the pull server to use SQL Server, set **SqlProvider** to `$true` and **SqlConnectionString** to a valid SQL Server Connection String.</span></span> <span data-ttu-id="d2334-166">Para obter mais informações, confira [Cadeias de conexão SqlClient](/dotnet/framework/data/adonet/connection-string-syntax#sqlclient-connection-strings).</span><span class="sxs-lookup"><span data-stu-id="d2334-166">For more information, see [SqlClient Connection Strings](/dotnet/framework/data/adonet/connection-string-syntax#sqlclient-connection-strings).</span></span>
<span data-ttu-id="d2334-167">Para obter um exemplo de configuração do SQL Server com **xDscWebService**, primeiro leia [Usando o recurso xDscWebService](#using-the-xdscwebservice-resource) e, em seguida, examine [Sample_xDscWebServiceRegistration_UseSQLProvider.ps1 no GitHub](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Examples/Sample_xDscWebServiceRegistration_UseSQLProvider.ps1).</span><span class="sxs-lookup"><span data-stu-id="d2334-167">For an example of SQL Server configuration with **xDscWebService**, first read [Using the xDscWebService resource](#using-the-xdscwebservice-resource) and then review [Sample_xDscWebServiceRegistration_UseSQLProvider.ps1 on GitHub](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Examples/Sample_xDscWebServiceRegistration_UseSQLProvider.ps1).</span></span>

### <a name="using-the-xdscwebservice-resource"></a><span data-ttu-id="d2334-168">Usando o recurso xDscWebService</span><span class="sxs-lookup"><span data-stu-id="d2334-168">Using the xDscWebService resource</span></span>

<span data-ttu-id="d2334-169">A maneira mais fácil de configurar um servidor de recepção Web é usar o recurso **xDscWebService**, incluído no módulo **xPSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d2334-169">The easiest way to set up a web pull server is to use the **xDscWebService** resource, included in the **xPSDesiredStateConfiguration** module.</span></span> <span data-ttu-id="d2334-170">As etapas a seguir explicam como usar o recurso em uma `Configuration` que defina o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="d2334-170">The following steps explain how to use the resource in a `Configuration` that sets up the web service.</span></span>

1. <span data-ttu-id="d2334-171">Chame o cmdlet [Install-Module](/powershell/module/PowerShellGet/Install-Module) para instalar o módulo **xPSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d2334-171">Call the [Install-Module](/powershell/module/PowerShellGet/Install-Module) cmdlet to install the **xPSDesiredStateConfiguration** module.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d2334-172">`Install-Module` está incluído no módulo **PowerShellGet**, que está incluído no PowerShell 5.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="d2334-172">`Install-Module` is included in the **PowerShellGet** module, which is included in PowerShell 5.0 and higher.</span></span>

1. <span data-ttu-id="d2334-173">Obtenha um certificado SSL para o servidor de Pull de DSC de uma Autoridade de Certificação confiável, seja de dentro de sua organização ou de uma autoridade pública.</span><span class="sxs-lookup"><span data-stu-id="d2334-173">Get an SSL certificate for the DSC Pull server from a trusted Certificate Authority, either within your organization or a public authority.</span></span> <span data-ttu-id="d2334-174">O certificado recebido da autoridade geralmente está no formato PFX.</span><span class="sxs-lookup"><span data-stu-id="d2334-174">The certificate received from the authority is usually in the PFX format.</span></span>
1. <span data-ttu-id="d2334-175">Instale o certificado no nó que se tornará o servidor de pull de DSC na localização padrão, que deve ser `CERT:\LocalMachine\My`.</span><span class="sxs-lookup"><span data-stu-id="d2334-175">Install the certificate on the node that will become the DSC Pull server in the default location, which should be `CERT:\LocalMachine\My`.</span></span>
   - <span data-ttu-id="d2334-176">Anote a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="d2334-176">Make a note of the certificate thumbprint.</span></span>
1. <span data-ttu-id="d2334-177">Selecione um GUID a ser usado como a Chave de Registro.</span><span class="sxs-lookup"><span data-stu-id="d2334-177">Select a GUID to be used as the Registration Key.</span></span> <span data-ttu-id="d2334-178">Para gerar um usando o PowerShell, insira o seguinte no prompt do PS e pressione enter: `[guid]::newGuid()` ou `New-Guid`.</span><span class="sxs-lookup"><span data-stu-id="d2334-178">To generate one using PowerShell enter the following at the PS prompt and press enter: `[guid]::newGuid()` or `New-Guid`.</span></span> <span data-ttu-id="d2334-179">Essa chave será usada por nós de cliente como uma chave compartilhada para autenticação durante o registro.</span><span class="sxs-lookup"><span data-stu-id="d2334-179">This key will be used by client nodes as a shared key to authenticate during registration.</span></span> <span data-ttu-id="d2334-180">Para obter mais informações, confira a seção Chave de registro abaixo.</span><span class="sxs-lookup"><span data-stu-id="d2334-180">For more information, see the Registration Key section below.</span></span>
1. <span data-ttu-id="d2334-181">No ISE do PowerShell, inicie (<kbd>F5</kbd>) o script de configuração a seguir (incluído na pasta do módulo **xPSDesiredStateConfiguration** como `Sample_xDscWebServiceRegistration.ps1`).</span><span class="sxs-lookup"><span data-stu-id="d2334-181">In the PowerShell ISE, start (<kbd>F5</kbd>) the following configuration script (included in the folder of the **xPSDesiredStateConfiguration** module as `Sample_xDscWebServiceRegistration.ps1`) .</span></span> <span data-ttu-id="d2334-182">Esse script configura o servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="d2334-182">This script sets up the pull server.</span></span>

    ```powershell
    configuration Sample_xDscWebServiceRegistration
    {
        param
        (
            [string[]]$NodeName = 'localhost',

            [ValidateNotNullOrEmpty()]
            [string] $certificateThumbPrint,

            [Parameter(HelpMessage='This should be a string with enough entropy (randomness) to protect the registration of clients to the pull server.  We will use new GUID by default.')]
            [ValidateNotNullOrEmpty()]
            [string] $RegistrationKey   # A guid that clients use to initiate conversation with pull server
        )

        Import-DSCResource -ModuleName PSDesiredStateConfiguration
        Import-DSCResource -ModuleName xPSDesiredStateConfiguration

        Node $NodeName
        {
            WindowsFeature DSCServiceFeature
            {
                Ensure = "Present"
                Name   = "DSC-Service"
            }

            xDscWebService PSDSCPullServer
            {
                Ensure                  = "Present"
                EndpointName            = "PSDSCPullServer"
                Port                    = 8080
                PhysicalPath            = "$env:SystemDrive\inetpub\PSDSCPullServer"
                CertificateThumbPrint   = $certificateThumbPrint
                ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
                ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
                State                   = "Started"
                DependsOn               = "[WindowsFeature]DSCServiceFeature"
                RegistrationKeyPath     = "$env:PROGRAMFILES\WindowsPowerShell\DscService"
                AcceptSelfSignedCertificates = $true
                UseSecurityBestPractices     = $true
                Enable32BitAppOnWin64   = $false
            }

            File RegistrationKeyFile
            {
                Ensure          = 'Present'
                Type            = 'File'
                DestinationPath = "$env:ProgramFiles\WindowsPowerShell\DscService\RegistrationKeys.txt"
                Contents        = $RegistrationKey
            }
        }
    }
    ```

1. <span data-ttu-id="d2334-183">Execute a configuração, passando a impressão digital do certificado SSL como o parâmetro **certificateThumbPrint** e uma chave de Registro GUID como o parâmetro **RegistrationKey**:</span><span class="sxs-lookup"><span data-stu-id="d2334-183">Run the configuration, passing the thumbprint of the SSL certificate as the **certificateThumbPrint** parameter and a GUID registration key as the **RegistrationKey** parameter:</span></span>

    ```powershell
    # To find the Thumbprint for an installed SSL certificate for use with the pull server list all certificates in your local store
    # and then copy the thumbprint for the appropriate certificate by reviewing the certificate subjects
    dir Cert:\LocalMachine\my

    # Then include this thumbprint when running the configuration
    Sample_xDscWebServiceRegistration -certificateThumbprint 'A7000024B753FA6FFF88E966FD6E19301FAE9CCC' -RegistrationKey '140a952b-b9d6-406b-b416-e0f759c9c0e4' -OutputPath c:\Configs\PullServer

    # Run the compiled configuration to make the target node a DSC Pull Server
    Start-DscConfiguration -Path c:\Configs\PullServer -Wait -Verbose
    ```

#### <a name="registration-key"></a><span data-ttu-id="d2334-184">Chave de Registro</span><span class="sxs-lookup"><span data-stu-id="d2334-184">Registration Key</span></span>

<span data-ttu-id="d2334-185">Para permitir que os nós clientes sejam registrados no servidor para poderem usar nomes de configuração em vez de uma ID de configuração, uma chave de registro que foi criada pela configuração acima é salva em um arquivo chamado `RegistrationKeys.txt` em `C:\Program Files\WindowsPowerShell\DscService`.</span><span class="sxs-lookup"><span data-stu-id="d2334-185">To allow client nodes to register with the server so that they can use configuration names instead of a configuration ID, a registration key that was created by the above configuration is saved in a file named `RegistrationKeys.txt` in `C:\Program Files\WindowsPowerShell\DscService`.</span></span> <span data-ttu-id="d2334-186">A chave de registro funciona como um segredo compartilhado usado durante o registro inicial pelo cliente com o servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="d2334-186">The registration key functions as a shared secret used during the initial registration by the client with the pull server.</span></span> <span data-ttu-id="d2334-187">O cliente gerará um certificado autoassinado, que será usado para realizar uma autenticação exclusiva no servidor de recepção depois que o registro for concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="d2334-187">The client will generate a self-signed certificate that is used to uniquely authenticate to the pull server once registration is successfully completed.</span></span> <span data-ttu-id="d2334-188">A impressão digital do certificado é armazenada localmente e associada à URL do servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="d2334-188">The thumbprint of this certificate is stored locally and associated with the URL of the pull server.</span></span>

> [!NOTE]
> <span data-ttu-id="d2334-189">Não há suporte para chaves de registro no PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="d2334-189">Registration keys are not supported in PowerShell 4.0.</span></span>

<span data-ttu-id="d2334-190">Para configurar um nó para ser autenticado no servidor de recepção, a chave de registro deverá estar na metaconfiguração do nó de destino que será registrado nesse servidor de recepção.</span><span class="sxs-lookup"><span data-stu-id="d2334-190">In order to configure a node to authenticate with the pull server, the registration key needs to be in the metaconfiguration for any target node that will be registering with this pull server.</span></span> <span data-ttu-id="d2334-191">Observe que a **RegistrationKey** na metaconfiguração abaixo é removida após o computador de destino ser registrado com sucesso e que o valor deve corresponder ao valor armazenado no arquivo `RegistrationKeys.txt` no servidor de pull ('140a952b-b9d6-406b-b416-e0f759c9c0e4' neste exemplo).</span><span class="sxs-lookup"><span data-stu-id="d2334-191">Note that the **RegistrationKey** in the metaconfiguration below is removed after the target machine has successfully registered, and that the value must match the value stored in the `RegistrationKeys.txt` file on the pull server ('140a952b-b9d6-406b-b416-e0f759c9c0e4' for this example).</span></span> <span data-ttu-id="d2334-192">Sempre trate o valor da chave do registro com segurança, porque o conhecimento permite que qualquer computador de destino seja registrado com o servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="d2334-192">Always treat the registration key value securely, because knowing it allows any target machine to register with the pull server.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration Sample_MetaConfigurationToRegisterWithLessSecurePullServer
{
    param
    (
        [ValidateNotNullOrEmpty()]
        [string] $NodeName = 'localhost',

        [ValidateNotNullOrEmpty()]
        [string] $RegistrationKey, #same as the one used to set up pull server in previous configuration

        [ValidateNotNullOrEmpty()]
        [string] $ServerName = 'localhost' #node name of the pull server, same as $NodeName used in previous configuration
    )

    Node $NodeName
    {
        Settings
        {
            RefreshMode        = 'Pull'
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL          = "https://$ServerName`:8080/PSDSCPullServer.svc" # notice it is https
            RegistrationKey    = $RegistrationKey
            ConfigurationNames = @('ClientConfig')
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL       = "https://$ServerName`:8080/PSDSCPullServer.svc" # notice it is https
            RegistrationKey = $RegistrationKey
        }
    }
}

Sample_MetaConfigurationToRegisterWithLessSecurePullServer -RegistrationKey $RegistrationKey -OutputPath c:\Configs\TargetNodes
```

> [!NOTE]
> <span data-ttu-id="d2334-193">A seção **ReportServerWeb** permite que dados de relatório sejam enviados ao servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="d2334-193">The **ReportServerWeb** section allows reporting data to be sent to the pull server.</span></span>

<span data-ttu-id="d2334-194">A falta da propriedade **ConfigurationID** no arquivo de metaconfiguração significa implicitamente que esse servidor pull dá suporte à versão V2 do protocolo de servidor pull, de modo que um registro inicial é necessário.</span><span class="sxs-lookup"><span data-stu-id="d2334-194">The lack of the **ConfigurationID** property in the metaconfiguration file implicitly means that pull server is supporting the V2 version of the pull server protocol so an initial registration is required.</span></span> <span data-ttu-id="d2334-195">Por outro lado, a presença de uma **ConfigurationID** significa que a versão V1 do protocolo do servidor de pull é usada e não há nenhum processamento de registro.</span><span class="sxs-lookup"><span data-stu-id="d2334-195">Conversely, the presence of a **ConfigurationID** means that the V1 version of the pull server protocol is used and there is no registration processing.</span></span>

> [!NOTE]
> <span data-ttu-id="d2334-196">Em um cenário de PUSH, há um bug na versão atual que exige a definição de uma propriedade ConfigurationID no arquivo de metaconfiguração para nós que nunca foram registrados em um servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="d2334-196">In a PUSH scenario, a bug exists in the current release that makes it necessary to define a ConfigurationID property in the metaconfiguration file for nodes that have never registered with a pull server.</span></span> <span data-ttu-id="d2334-197">Isso forçará o uso do protocolo de Servidor de Pull V1 e evitará mensagens de falha de registro.</span><span class="sxs-lookup"><span data-stu-id="d2334-197">This will force the V1 Pull Server protocol and avoid registration failure messages.</span></span>

## <a name="placing-configurations-and-resources"></a><span data-ttu-id="d2334-198">Colocando configurações e recursos</span><span class="sxs-lookup"><span data-stu-id="d2334-198">Placing configurations and resources</span></span>

<span data-ttu-id="d2334-199">Após a instalação do servidor pull ser concluída, as pastas definidas pelas propriedades **ConfigurationPath** e **ModulePath** na configuração do servidor pull são onde você colocará módulos e configurações que estarão disponíveis para pull pelos nós de destino.</span><span class="sxs-lookup"><span data-stu-id="d2334-199">After the pull server setup completes, the folders defined by the **ConfigurationPath** and **ModulePath** properties in the pull server configuration are where you will place modules and configurations that will be available for target nodes to pull.</span></span> <span data-ttu-id="d2334-200">Esses arquivos precisam estar em um formato específico para que o servidor de recepção processe-os corretamente.</span><span class="sxs-lookup"><span data-stu-id="d2334-200">These files need to be in a specific format in order for the pull server to correctly process them.</span></span>

### <a name="dsc-resource-module-package-format"></a><span data-ttu-id="d2334-201">Formato de pacote do módulo de recursos DSC</span><span class="sxs-lookup"><span data-stu-id="d2334-201">DSC resource module package format</span></span>

<span data-ttu-id="d2334-202">Cada módulo de recurso precisa ser compactado e nomeado de acordo com o seguinte padrão `{Module Name}_{Module Version}.zip`.</span><span class="sxs-lookup"><span data-stu-id="d2334-202">Each resource module needs to be zipped and named according to the following pattern `{Module Name}_{Module Version}.zip`.</span></span>

<span data-ttu-id="d2334-203">Por exemplo, um módulo chamado **xWebAdminstration** com uma versão do módulo correspondente a 3.1.2.0 seria nomeado`xWebAdministration_3.1.2.0.zip`.</span><span class="sxs-lookup"><span data-stu-id="d2334-203">For example, a module named **xWebAdminstration** with a module version of 3.1.2.0 would be named `xWebAdministration_3.1.2.0.zip`.</span></span> <span data-ttu-id="d2334-204">Cada versão de um módulo deve estar contido em um único arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="d2334-204">Each version of a module must be contained in a single zip file.</span></span>
<span data-ttu-id="d2334-205">Como há apenas uma única versão de um recurso em cada arquivo zip, não há suporte para o formato do módulo adicionado ao WMF 5.0 com suporte para várias versões de módulo em um único diretório.</span><span class="sxs-lookup"><span data-stu-id="d2334-205">Since there is only a single version of a resource in each zip file, the module format added in WMF 5.0 with support for multiple module versions in a single directory is not supported.</span></span> <span data-ttu-id="d2334-206">Isso significa que antes de empacotar módulos de recursos DSC para uso com o servidor de pull, você precisará fazer uma pequena alteração na estrutura de diretórios.</span><span class="sxs-lookup"><span data-stu-id="d2334-206">This means that before packaging up DSC resource modules for use with pull server you will need to make a small change to the directory structure.</span></span> <span data-ttu-id="d2334-207">O formato padrão de módulos contendo recursos DSC no WMF 5.0 é `{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\`.</span><span class="sxs-lookup"><span data-stu-id="d2334-207">The default format of modules containing DSC resource in WMF 5.0 is `{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\`.</span></span> <span data-ttu-id="d2334-208">Antes de empacotar o servidor de pull, remova a pasta **{versão do módulo}** para que o caminho se torne `{Module Folder}\DscResources\{DSC Resource Folder}\`.</span><span class="sxs-lookup"><span data-stu-id="d2334-208">Before packaging up for the pull server, remove the **{Module version}** folder so the path becomes `{Module Folder}\DscResources\{DSC Resource Folder}\`.</span></span> <span data-ttu-id="d2334-209">Com essa alteração, compacte a pasta conforme descrito acima e coloque esses arquivos zip na pasta **ModulePath**.</span><span class="sxs-lookup"><span data-stu-id="d2334-209">With this change, zip the folder as described above and place these zip files in the **ModulePath** folder.</span></span>

<span data-ttu-id="d2334-210">Use `New-DscChecksum {module zip file}` para criar um arquivo de soma de verificação para o módulo recém-adicionado.</span><span class="sxs-lookup"><span data-stu-id="d2334-210">Use `New-DscChecksum {module zip file}` to create a checksum file for the newly added module.</span></span>

### <a name="configuration-mof-format"></a><span data-ttu-id="d2334-211">Formato MOF de configuração</span><span class="sxs-lookup"><span data-stu-id="d2334-211">Configuration MOF format</span></span>

<span data-ttu-id="d2334-212">Um arquivo MOF de configuração precisa ser emparelhado com um arquivo de soma de verificação para que um LCM em um nó de destino possa validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="d2334-212">A configuration MOF file needs to be paired with a checksum file so that an LCM on a target node can validate the configuration.</span></span> <span data-ttu-id="d2334-213">Para criar uma soma de verificação, chame o cmdlet [New-DscChecksum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum).</span><span class="sxs-lookup"><span data-stu-id="d2334-213">To create a checksum, call the [New-DscChecksum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet.</span></span> <span data-ttu-id="d2334-214">O cmdlet usa um parâmetro **Path** que especifica a pasta na qual se encontra o MOF de configuração.</span><span class="sxs-lookup"><span data-stu-id="d2334-214">The cmdlet takes a **Path** parameter that specifies the folder where the configuration MOF is located.</span></span> <span data-ttu-id="d2334-215">O cmdlet cria um arquivo de soma de verificação chamado `ConfigurationMOFName.mof.checksum`, em que `ConfigurationMOFName` é o nome do arquivo MOF de configuração.</span><span class="sxs-lookup"><span data-stu-id="d2334-215">The cmdlet creates a checksum file named `ConfigurationMOFName.mof.checksum`, where `ConfigurationMOFName` is the name of the configuration mof file.</span></span> <span data-ttu-id="d2334-216">Se houver mais de um arquivo MOF de configuração na pasta especificada, será criada uma soma de verificação para cada configuração na pasta.</span><span class="sxs-lookup"><span data-stu-id="d2334-216">If there are more than one configuration MOF files in the specified folder, a checksum is created for each configuration in the folder.</span></span> <span data-ttu-id="d2334-217">Coloque os arquivos MOF e os arquivos de soma de verificação associados na pasta **ConfigurationPath**.</span><span class="sxs-lookup"><span data-stu-id="d2334-217">Place the MOF files and their associated checksum files in the **ConfigurationPath** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="d2334-218">Se alterar o arquivo MOF de configuração de qualquer forma, você também deverá recriar o arquivo de soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="d2334-218">If you change the configuration MOF file in any way, you must also recreate the checksum file.</span></span>

### <a name="tooling"></a><span data-ttu-id="d2334-219">Ferramentas</span><span class="sxs-lookup"><span data-stu-id="d2334-219">Tooling</span></span>

<span data-ttu-id="d2334-220">Para facilitar a configuração, validação e gerenciamento do servidor de pull, as ferramentas a seguir são incluídas como exemplos na versão mais recente do módulo xPSDesiredStateConfiguration:</span><span class="sxs-lookup"><span data-stu-id="d2334-220">In order to make setting up, validating and managing the pull server easier, the following tools are included as examples in the latest version of the xPSDesiredStateConfiguration module:</span></span>

1. <span data-ttu-id="d2334-221">Um módulo que ajudará com empacotamento de módulos de recursos DSC e arquivos de configuração para uso no servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="d2334-221">A module that will help with packaging DSC resource modules and configuration files for use on the pull server.</span></span>
   <span data-ttu-id="d2334-222">[PublishModulesAndMofsToPullServer.psm1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Modules/DscPullServerSetup/DscPullServerSetup.psm1).</span><span class="sxs-lookup"><span data-stu-id="d2334-222">[PublishModulesAndMofsToPullServer.psm1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Modules/DscPullServerSetup/DscPullServerSetup.psm1).</span></span>
   <span data-ttu-id="d2334-223">Exemplos abaixo:</span><span class="sxs-lookup"><span data-stu-id="d2334-223">Examples below:</span></span>

    ```powershell
        # Example 1 - Package all versions of given modules installed locally and MOF files are in c:\LocalDepot
         $moduleList = @('xWebAdministration', 'xPhp')
         Publish-DSCModuleAndMof -Source C:\LocalDepot -ModuleNameList $moduleList

         # Example 2 - Package modules and mof documents from c:\LocalDepot
         Publish-DSCModuleAndMof -Source C:\LocalDepot -Force
    ```

1. <span data-ttu-id="d2334-224">Um script que valida o Servidor de Pull está configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="d2334-224">A script that validates the pull server is configured correctly.</span></span> <span data-ttu-id="d2334-225">[PullServerSetupTests.ps1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Modules/DscPullServerSetup/DscPullServerSetupTest/DscPullServerSetupTest.ps1).</span><span class="sxs-lookup"><span data-stu-id="d2334-225">[PullServerSetupTests.ps1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Modules/DscPullServerSetup/DscPullServerSetupTest/DscPullServerSetupTest.ps1).</span></span>

## <a name="community-solutions-for-pull-service"></a><span data-ttu-id="d2334-226">Soluções da comunidade para o Serviço de Pull</span><span class="sxs-lookup"><span data-stu-id="d2334-226">Community Solutions for Pull Service</span></span>

<span data-ttu-id="d2334-227">A comunidade de DSC criou várias soluções para implementar o protocolo de serviço de pull.</span><span class="sxs-lookup"><span data-stu-id="d2334-227">The DSC community has authored multiple solutions to implement the pull service protocol.</span></span> <span data-ttu-id="d2334-228">Para ambientes locais, elas oferecem funcionalidades de serviço de pull e uma oportunidade de retribuir à comunidade, contribuindo com melhorias incrementais.</span><span class="sxs-lookup"><span data-stu-id="d2334-228">For on-premises environments, these offer pull service capabilities and an opportunity to contribute back to the community with incremental enhancements.</span></span>

- [<span data-ttu-id="d2334-229">Tug</span><span class="sxs-lookup"><span data-stu-id="d2334-229">Tug</span></span>](https://github.com/powershellorg/tug)
- [<span data-ttu-id="d2334-230">DSC-TRÆK</span><span class="sxs-lookup"><span data-stu-id="d2334-230">DSC-TRÆK</span></span>](https://github.com/powershellorg/dsc-traek)

## <a name="pull-client-configuration"></a><span data-ttu-id="d2334-231">Configuração do cliente de pull</span><span class="sxs-lookup"><span data-stu-id="d2334-231">Pull client configuration</span></span>

<span data-ttu-id="d2334-232">Os tópicos a seguir descrevem em detalhes a configuração de clientes de pull:</span><span class="sxs-lookup"><span data-stu-id="d2334-232">The following topics describe setting up pull clients in detail:</span></span>

- [<span data-ttu-id="d2334-233">Configurar um cliente de pull de DSC usando uma ID de configuração</span><span class="sxs-lookup"><span data-stu-id="d2334-233">Set up a DSC pull client using a configuration ID</span></span>](pullClientConfigID.md)
- [<span data-ttu-id="d2334-234">Configurar um cliente de pull de DSC usando nomes de configuração</span><span class="sxs-lookup"><span data-stu-id="d2334-234">Set up a DSC pull client using configuration names</span></span>](pullClientConfigNames.md)
- [<span data-ttu-id="d2334-235">Configurações parciais</span><span class="sxs-lookup"><span data-stu-id="d2334-235">Partial configurations</span></span>](partialConfigs.md)

## <a name="see-also"></a><span data-ttu-id="d2334-236">Confira também</span><span class="sxs-lookup"><span data-stu-id="d2334-236">See also</span></span>

- [<span data-ttu-id="d2334-237">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2334-237">Windows PowerShell Desired State Configuration Overview</span></span>](../overview/overview.md)
- [<span data-ttu-id="d2334-238">Aplicando configurações</span><span class="sxs-lookup"><span data-stu-id="d2334-238">Enacting configurations</span></span>](enactingConfigurations.md)
- [<span data-ttu-id="d2334-239">Usando um servidor de relatório de DSC</span><span class="sxs-lookup"><span data-stu-id="d2334-239">Using a DSC report server</span></span>](reportServer.md)
- <span data-ttu-id="d2334-240">[[MS-DSCPM]: protocolo Desired State Configuration Pull Model](/openspecs/windows_protocols/ms-dscpm/ea744c01-51a2-4000-9ef2-312711dcc8c9)</span><span class="sxs-lookup"><span data-stu-id="d2334-240">[[MS-DSCPM]: Desired State Configuration Pull Model Protocol](/openspecs/windows_protocols/ms-dscpm/ea744c01-51a2-4000-9ef2-312711dcc8c9)</span></span>
- <span data-ttu-id="d2334-241">[[MS-DSCPM]: errata do protocolo Desired State Configuration Pull Model](/openspecs/windows_protocols/ms-winerrata/f5fc7ae3-9172-41e8-ac6a-2a5a5b7bfaf5)</span><span class="sxs-lookup"><span data-stu-id="d2334-241">[[MS-DSCPM]: Desired State Configuration Pull Model Protocol Errata](/openspecs/windows_protocols/ms-winerrata/f5fc7ae3-9172-41e8-ac6a-2a5a5b7bfaf5)</span></span>
