---
ms.date: 08/15/2019
keywords: DSC,powershell,configuração,instalação
title: Introdução a DSC (Desired State Configuration) para Windows
ms.openlocfilehash: a9346b96693acdbad9bacbd4b6ca85971e17a3d1
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417754"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a><span data-ttu-id="c5af0-103">Introdução a DSC (Desired State Configuration) para Windows</span><span class="sxs-lookup"><span data-stu-id="c5af0-103">Get started with Desired State Configuration (DSC) for Windows</span></span>

<span data-ttu-id="c5af0-104">Este tópico explica como começar a usar a DSC (Desired State Configuration) do PowerShell para Windows.</span><span class="sxs-lookup"><span data-stu-id="c5af0-104">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Windows.</span></span>
<span data-ttu-id="c5af0-105">Para obter informações gerais sobre o DSC, consulte [Introdução à Configuração de Estado Desejado do Windows PowerShell](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="c5af0-105">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-windows-operation-system-versions"></a><span data-ttu-id="c5af0-106">Versões compatíveis do sistema operacional Windows</span><span class="sxs-lookup"><span data-stu-id="c5af0-106">Supported Windows operation system versions</span></span>

<span data-ttu-id="c5af0-107">As seguintes versões são compatíveis:</span><span class="sxs-lookup"><span data-stu-id="c5af0-107">The following versions are supported:</span></span>

- <span data-ttu-id="c5af0-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c5af0-108">Windows Server 2019</span></span>
- <span data-ttu-id="c5af0-109">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c5af0-109">Windows Server 2016</span></span>
- <span data-ttu-id="c5af0-110">Windows Server 2012R2</span><span class="sxs-lookup"><span data-stu-id="c5af0-110">Windows Server 2012R2</span></span>
- <span data-ttu-id="c5af0-111">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c5af0-111">Windows Server 2012</span></span>
- <span data-ttu-id="c5af0-112">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="c5af0-112">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="c5af0-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="c5af0-113">Windows 10</span></span>
- <span data-ttu-id="c5af0-114">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c5af0-114">Windows 8.1</span></span>
- <span data-ttu-id="c5af0-115">Windows 7</span><span class="sxs-lookup"><span data-stu-id="c5af0-115">Windows 7</span></span>

<span data-ttu-id="c5af0-116">O SKU do produto autônomo [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) não contém uma implementação da Desired State Configuration, portanto, não pode ser gerenciado pela Configuração de Estado da Automação do Azure ou DSC do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5af0-116">The [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) standalone product sku does not contain an implementation of Desired State Configuraion so it cannot be managed by PowerShell DSC or Azure Automation State Configuration.</span></span>

## <a name="installing-dsc"></a><span data-ttu-id="c5af0-117">Instalando a DSC</span><span class="sxs-lookup"><span data-stu-id="c5af0-117">Installing DSC</span></span>

<span data-ttu-id="c5af0-118">A Desired State Configuration do PowerShell está incluída no Windows e é atualizada por meio do Windows Management Framework.</span><span class="sxs-lookup"><span data-stu-id="c5af0-118">PowerShell Desired State Configuration is included in Windows and updated through Windows Management Framework.</span></span>
<span data-ttu-id="c5af0-119">A versão mais recente é [Windows Management Framework 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="c5af0-119">The latest version is [Windows Management Framework 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>

> [!NOTE]
> <span data-ttu-id="c5af0-120">Não é necessário habilitar o recurso “DSC-Service” do Windows Server para gerenciar um computador usando a DSC.</span><span class="sxs-lookup"><span data-stu-id="c5af0-120">You do not need to enable the Windows Server feature 'DSC-Service' to manage a machine using DSC.</span></span>
> <span data-ttu-id="c5af0-121">Esse recurso só é necessário ao criar uma instância de servidor de pull do Windows.</span><span class="sxs-lookup"><span data-stu-id="c5af0-121">That feature is only needed when building a Windows Pull Server instance.</span></span>

## <a name="using-dsc-for-windows"></a><span data-ttu-id="c5af0-122">Usar DSC para Windows</span><span class="sxs-lookup"><span data-stu-id="c5af0-122">Using DSC for Windows</span></span>

<span data-ttu-id="c5af0-123">As seções a seguir explicam como criar e executar configurações da DSC em computadores Windows.</span><span class="sxs-lookup"><span data-stu-id="c5af0-123">The following sections explain how to create and run DSC configurations on Windows computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="c5af0-124">Criando um documento MOF de configuração</span><span class="sxs-lookup"><span data-stu-id="c5af0-124">Creating a configuration MOF document</span></span>

<span data-ttu-id="c5af0-125">A palavra-chave Configuração do Windows PowerShell é usada para criar uma configuração.</span><span class="sxs-lookup"><span data-stu-id="c5af0-125">The Windows PowerShell Configuration keyword is used to create a configuration.</span></span>
<span data-ttu-id="c5af0-126">As etapas a seguir descrevem a criação de um documento de configuração usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5af0-126">The following steps describe the creation of a configuration document using Windows PowerShell.</span></span>

#### <a name="define-a-configuration-and-generate-the-configuration-document"></a><span data-ttu-id="c5af0-127">Definir uma configuração e gerar o documento de configuração:</span><span class="sxs-lookup"><span data-stu-id="c5af0-127">Define a configuration and generate the configuration document:</span></span>

```powershell
Configuration EnvironmentVariable_Path
{
    param ()

    Import-DscResource -ModuleName 'PSDscResources'

    Node localhost
    {
        Environment CreatePathEnvironmentVariable
        {
            Name = 'TestPathEnvironmentVariable'
            Value = 'TestValue'
            Ensure = 'Present'
            Path = $true
            Target = @('Process', 'Machine')
        }
    }
}

EnvironmentVariable_Path -OutputPath:"C:\EnvironmentVariable_Path"
```
#### <a name="install-a-module-containing-dsc-resources"></a><span data-ttu-id="c5af0-128">Instalar um módulo que contém recursos da DSC</span><span class="sxs-lookup"><span data-stu-id="c5af0-128">Install a module containing DSC resources</span></span>

<span data-ttu-id="c5af0-129">A Desired State Configuration do Windows PowerShell inclui módulos internos que contêm recursos da DSC.</span><span class="sxs-lookup"><span data-stu-id="c5af0-129">Windows PowerShell Desired State Configuration includes built-in modules containing DSC resources.</span></span>
<span data-ttu-id="c5af0-130">Você também pode carregar módulos de fontes externas, como o Galeria do PowerShell, usando os cmdlets do PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="c5af0-130">You can also load modules from external sources such as the PowerShell Gallery, using the PowerShellGet cmdlets.</span></span>

`Install-Module 'PSDscResources' -Verbose`

#### <a name="apply-the-configuration-to-the-machine"></a><span data-ttu-id="c5af0-131">Aplicar a configuração ao computador</span><span class="sxs-lookup"><span data-stu-id="c5af0-131">Apply the configuration to the machine</span></span>

<span data-ttu-id="c5af0-132">Documentos de configuração (arquivos MOF) podem ser aplicados ao computador usando o cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="c5af0-132">Configuration documents (MOF files) can be applied to the machine using the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

`Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose`

#### <a name="get-the-current-state-of-the-configuration"></a><span data-ttu-id="c5af0-133">Obter o estado atual da configuração</span><span class="sxs-lookup"><span data-stu-id="c5af0-133">Get the current state of the configuration</span></span>

<span data-ttu-id="c5af0-134">O cmdlet [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) consulta o status atual do computador e retorna os valores atuais para a configuração.</span><span class="sxs-lookup"><span data-stu-id="c5af0-134">The [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet queries the current status of the machine and returns the current values for the configuration.</span></span>

`Get-DscConfiguration`

<span data-ttu-id="c5af0-135">O cmdlet [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) retorna a metaconfiguração atual aplicada ao computador.</span><span class="sxs-lookup"><span data-stu-id="c5af0-135">The [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) cmdlet returns the current meta-configuration applied to the machine.</span></span>

`Get-DscLocalConfigurationManager`

#### <a name="remove-the-current-configuration-from-a-machine"></a><span data-ttu-id="c5af0-136">Remover a configuração atual de um computador</span><span class="sxs-lookup"><span data-stu-id="c5af0-136">Remove the current configuration from a machine</span></span>

<span data-ttu-id="c5af0-137">O [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span><span class="sxs-lookup"><span data-stu-id="c5af0-137">The [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span></span>

`Remove-DscConfigurationDocument -Stage Current -Verbose`

#### <a name="configure-settings-in-local-configuration-manager"></a><span data-ttu-id="c5af0-138">Configurar o Local Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c5af0-138">Configure settings in Local Configuration Manager</span></span>

<span data-ttu-id="c5af0-139">Aplique um arquivo MOF de metaconfiguração ao computador usando o cmdlet [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="c5af0-139">Apply a Meta Configuration MOF file to the machine using the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span>
<span data-ttu-id="c5af0-140">Exige o caminho até o MOF de metaconfiguração.</span><span class="sxs-lookup"><span data-stu-id="c5af0-140">Requires the path to the Meta Configuration MOF.</span></span>

`Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose`

## <a name="windows-powershell-desired-state-configuration-log-files"></a><span data-ttu-id="c5af0-141">Arquivo de log da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5af0-141">Windows PowerShell Desired State Configuration log files</span></span>

<span data-ttu-id="c5af0-142">Os logs para DSC são gravados no log de eventos do Windows no caminho `Microsoft-Windows-Dsc/Operational`.</span><span class="sxs-lookup"><span data-stu-id="c5af0-142">Logs for DSC are written to Windows Event Log in the path `Microsoft-Windows-Dsc/Operational`.</span></span>
<span data-ttu-id="c5af0-143">Logs adicionais para fins de depuração podem ser habilitados seguindo as etapas em [Onde ficam os logs de eventos da DSC](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs).</span><span class="sxs-lookup"><span data-stu-id="c5af0-143">Additional logs for debugging purposes can be enabled following the steps in [Where Are DSC Event Logs](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs).</span></span>
