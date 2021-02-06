---
description: WSMan
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_wsman_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor WSMan
ms.openlocfilehash: 32baaaec3589fc9d6f4c2319f47d56bca777f738
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598842"
---
# <a name="wsman-provider"></a><span data-ttu-id="539ad-103">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="539ad-103">WSMan Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="539ad-104">Nome do provedor</span><span class="sxs-lookup"><span data-stu-id="539ad-104">Provider name</span></span>

<span data-ttu-id="539ad-105">WSMan</span><span class="sxs-lookup"><span data-stu-id="539ad-105">WSMan</span></span>

## <a name="drives"></a><span data-ttu-id="539ad-106">Unidades</span><span class="sxs-lookup"><span data-stu-id="539ad-106">Drives</span></span>

`WSMan:`

## <a name="short-description"></a><span data-ttu-id="539ad-107">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="539ad-107">Short description</span></span>

<span data-ttu-id="539ad-108">Fornece acesso a serviços Web para obter informações de configuração de gerenciamento (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="539ad-108">Provides access to Web Services for Management (WS-Management) configuration information.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="539ad-109">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="539ad-109">Detailed description</span></span>

<span data-ttu-id="539ad-110">O provedor **WSMan** para PowerShell permite que você adicione, altere, apague e exclua WS-Management dados de configuração em computadores locais ou remotos.</span><span class="sxs-lookup"><span data-stu-id="539ad-110">The **WSMan** provider for PowerShell lets you add, change, clear, and delete WS-Management configuration data on local or remote computers.</span></span>

<span data-ttu-id="539ad-111">O provedor **WSMan** expõe uma unidade do PowerShell com uma estrutura de diretório que corresponde a um agrupamento lógico de definições de configuração de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="539ad-111">The **WSMan** provider exposes a PowerShell drive with a directory structure that corresponds to a logical grouping of WS-Management configuration settings.</span></span> <span data-ttu-id="539ad-112">Esses agrupamentos são conhecidos como contêineres.</span><span class="sxs-lookup"><span data-stu-id="539ad-112">These groupings are known as containers.</span></span>

<span data-ttu-id="539ad-113">A partir do Windows PowerShell 3,0, o provedor **WSMan** foi atualizado para dar suporte a novas propriedades para configurações de sessão, como **OutputBufferingMode**.</span><span class="sxs-lookup"><span data-stu-id="539ad-113">Beginning in Windows PowerShell 3.0, the **WSMan** provider has been updated to support new properties for session configurations, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="539ad-114">As configurações de sessão aparecem como itens no diretório de plug-in da `WSMan:` unidade e as propriedades aparecem como itens em cada configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="539ad-114">The session configurations appear as items in the Plugin directory of the `WSMan:` drive and the properties appear as items in each session configuration.</span></span>

<span data-ttu-id="539ad-115">O provedor **WSMan** dá suporte aos seguintes cmdlets, que são abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="539ad-115">The **WSMan** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="539ad-116">Get-Location</span><span class="sxs-lookup"><span data-stu-id="539ad-116">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="539ad-117">Set-Location</span><span class="sxs-lookup"><span data-stu-id="539ad-117">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="539ad-118">Get-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-118">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="539ad-119">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="539ad-119">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="539ad-120">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-120">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="539ad-121">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-121">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

> [!NOTE]
> <span data-ttu-id="539ad-122">Você pode usar os comandos na `WSMan:` unidade para alterar os valores das novas propriedades.</span><span class="sxs-lookup"><span data-stu-id="539ad-122">You can use commands in the `WSMan:` drive to change the values of the new properties.</span></span> <span data-ttu-id="539ad-123">No entanto, você não pode usar a `WSMan:` unidade no PowerShell 2,0 para alterar as propriedades introduzidas no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="539ad-123">However, you cannot use the `WSMan:` drive in PowerShell 2.0 to change properties that are introduced in Windows PowerShell 3.0.</span></span>
> <span data-ttu-id="539ad-124">Embora nenhum erro seja gerado, os comandos não são efetivos para alterar essas configurações, use a unidade **WSMan** no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="539ad-124">Although no error is generated, the commands are not effective To change these settings, use the **WSMan** drive in Windows PowerShell 3.0.</span></span>

### <a name="organization-of-the-wsman-drive"></a><span data-ttu-id="539ad-125">Organização da unidade WSMan:</span><span class="sxs-lookup"><span data-stu-id="539ad-125">Organization of the WSMan: Drive</span></span>

- <span data-ttu-id="539ad-126">**Cliente**: você pode configurar vários aspectos do cliente WS-Management.</span><span class="sxs-lookup"><span data-stu-id="539ad-126">**Client**: You can configure various aspects of the WS-Management client.</span></span> <span data-ttu-id="539ad-127">As informações de configuração são armazenadas no Registro.</span><span class="sxs-lookup"><span data-stu-id="539ad-127">The configuration information is stored in the registry.</span></span>

- <span data-ttu-id="539ad-128">**Serviço**: você pode configurar vários aspectos do serviço de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="539ad-128">**Service**: You can configure various aspects of the WS-Management service.</span></span>
  <span data-ttu-id="539ad-129">As informações de configuração são armazenadas no Registro.</span><span class="sxs-lookup"><span data-stu-id="539ad-129">The configuration information is stored in the registry.</span></span>
  > [!NOTE]
  > <span data-ttu-id="539ad-130">A configuração do serviço, às vezes, é chamada de configuração Server.</span><span class="sxs-lookup"><span data-stu-id="539ad-130">Service configuration is sometimes referred to as Server configuration.</span></span>

- <span data-ttu-id="539ad-131">**Shell**: você pode configurar vários aspectos do WS-Management Shell, como a configuração para permitir acesso de shell remoto (**AllowRemoteShellAccess**) e o número máximo de usuários simultâneos permitidos (**MaxConcurrentUsers**).</span><span class="sxs-lookup"><span data-stu-id="539ad-131">**Shell**: You can configure various aspects of the WS-Management shell, such as the setting to allow remote shell access (**AllowRemoteShellAccess**) and the maximum number of concurrent users allowed (**MaxConcurrentUsers**).</span></span>

- <span data-ttu-id="539ad-132">**Ouvinte**: você pode criar e configurar um ouvinte.</span><span class="sxs-lookup"><span data-stu-id="539ad-132">**Listener**: You can create and configure a listener.</span></span> <span data-ttu-id="539ad-133">Um ouvinte é um serviço de gerenciamento que implementa o protocolo WS-Management para enviar e receber mensagens.</span><span class="sxs-lookup"><span data-stu-id="539ad-133">A listener is a management service that implements the WS-Management protocol to send and to receive messages.</span></span>

- <span data-ttu-id="539ad-134">**Plugin**: os plug-ins são carregados e usados pelo serviço de WS-Management para fornecer várias funções.</span><span class="sxs-lookup"><span data-stu-id="539ad-134">**Plugin**: Plug-ins are loaded and used by the WS-Management service to provide various functions.</span></span> <span data-ttu-id="539ad-135">Por padrão, o PowerShell fornece três plug-ins:</span><span class="sxs-lookup"><span data-stu-id="539ad-135">By default, PowerShell provides three plug-ins:</span></span>
  - <span data-ttu-id="539ad-136">O plug-in de encaminhamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="539ad-136">The Event Forwarding plug-in.</span></span>
  - <span data-ttu-id="539ad-137">O plug-in do Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="539ad-137">The Microsoft.PowerShell plug-in.</span></span>
  - <span data-ttu-id="539ad-138">O plug-in do provedor de Instrumentação de Gerenciamento do Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="539ad-138">The Windows Management Instrumentation (WMI) Provider plug-in.</span></span>
  <span data-ttu-id="539ad-139">Esses três plug-ins dão suporte ao encaminhamento de eventos, à configuração e ao acesso WMI.</span><span class="sxs-lookup"><span data-stu-id="539ad-139">These three plug-ins support event forwarding, configuration, and WMI access.</span></span>

- <span data-ttu-id="539ad-140">**ClientCertificate**: você pode criar e configurar um certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="539ad-140">**ClientCertificate**: You can create and configure a client certificate.</span></span>
  <span data-ttu-id="539ad-141">Um certificado de cliente é usado quando o cliente do WS-Management está configurado para usar a autenticação de certificado.</span><span class="sxs-lookup"><span data-stu-id="539ad-141">A client certificate is used when the WS-Management client is configured to use certificate authentication.</span></span>

### <a name="directory-hierarchy-of-the-wsman-provider"></a><span data-ttu-id="539ad-142">Hierarquia de diretórios do provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="539ad-142">Directory Hierarchy of the WSMan Provider</span></span>

<span data-ttu-id="539ad-143">A hierarquia de diretórios do provedor WSMan para o computador local é a seguinte.</span><span class="sxs-lookup"><span data-stu-id="539ad-143">The directory hierarchy of the WSMan provider for the local computer is as follows.</span></span>

```
WSMan:\localhost
--- Client
--- Service
--- Shell
--- Listener
------ <Specific_Listener>
--- Plugin
------ Event Forwarding Plugin
--------- InitializationParameters
--------- Resources
------------ Security
------ Microsoft.Powershell
--------- InitializationParameters
--------- Resources
------------ Security
------ WMI Provider
--------- InitializationParameters
--------- Resources
------------ Security
--- ClientCertificate
```

<span data-ttu-id="539ad-144">A hierarquia de diretórios do provedor WSMan para um computador remoto é a mesmo que para um computador local.</span><span class="sxs-lookup"><span data-stu-id="539ad-144">The directory hierarchy of the WSMan provider for a remote computer is the same as a local computer.</span></span> <span data-ttu-id="539ad-145">No entanto, para acessar as configurações de um computador remoto, você precisa estabelecer uma conexão com o computador remoto usando [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span><span class="sxs-lookup"><span data-stu-id="539ad-145">However, in order to access the configuration settings of a remote computer, you need to make a connection to the remote computer using [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span> <span data-ttu-id="539ad-146">Depois que uma conexão é feita para um computador remoto, o nome do computador remoto aparece no provedor.</span><span class="sxs-lookup"><span data-stu-id="539ad-146">Once a connection is made to a remote computer, the name of the remote computer shows up in the provider.</span></span>

```
WSMan:\<Remote_Computer_Name>
```

## <a name="navigating-the-wsman-drive"></a><span data-ttu-id="539ad-147">Navegando na unidade WSMan:</span><span class="sxs-lookup"><span data-stu-id="539ad-147">Navigating the WSMan: Drive</span></span>

<span data-ttu-id="539ad-148">Esse comando usa o `Set-Location` cmdlet para alterar o local atual para a `WSMan:` unidade.</span><span class="sxs-lookup"><span data-stu-id="539ad-148">This command uses the `Set-Location` cmdlet to change the current location to the `WSMan:` drive.</span></span>

```powershell
Set-Location WSMan:
```

<span data-ttu-id="539ad-149">Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="539ad-149">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="539ad-150">Por exemplo, digite.</span><span class="sxs-lookup"><span data-stu-id="539ad-150">For example, type.</span></span>

```powershell
Set-Location C:
```

### <a name="navigating-to-a-remote-system-store-location"></a><span data-ttu-id="539ad-151">Navegando para um local de armazenamento do sistema remoto</span><span class="sxs-lookup"><span data-stu-id="539ad-151">Navigating to a remote system store location</span></span>

<span data-ttu-id="539ad-152">Esse comando usa o `Set-Location` comando para alterar o local atual para o local raiz no local de armazenamento do sistema remoto.</span><span class="sxs-lookup"><span data-stu-id="539ad-152">This command uses the `Set-Location` command to change the current location to the root location in the remote system store location.</span></span> <span data-ttu-id="539ad-153">Use uma barra invertida ou uma barra invertida `\` `/` para indicar um nível da `WSMan:` unidade.</span><span class="sxs-lookup"><span data-stu-id="539ad-153">Use a backslash `\` or forward slash `/` to indicate a level of the `WSMan:` drive.</span></span>

```powershell
Set-Location -Path  WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="539ad-154">O comando acima pressupõe que uma conexão com o sistema remoto já exista.</span><span class="sxs-lookup"><span data-stu-id="539ad-154">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="displaying-the-contents-of-the-wsman-drive"></a><span data-ttu-id="539ad-155">Exibindo o conteúdo da unidade WSMan:</span><span class="sxs-lookup"><span data-stu-id="539ad-155">Displaying the Contents of the WSMan: Drive</span></span>

<span data-ttu-id="539ad-156">Esse comando usa o `Get-Childitem` cmdlet para exibir os repositórios de WS-Management no local de armazenamento do localhost.</span><span class="sxs-lookup"><span data-stu-id="539ad-156">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the Localhost store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\Localhost
```

<span data-ttu-id="539ad-157">Se você estiver na `WSMan:` unidade, poderá omitir o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="539ad-157">If you are in the `WSMan:` drive, you can omit the drive name.</span></span>

<span data-ttu-id="539ad-158">Esse comando usa o `Get-Childitem` cmdlet para exibir os repositórios de WS-Management no local de armazenamento "Server01" do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="539ad-158">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the remote computer "SERVER01" store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="539ad-159">O comando acima pressupõe que uma conexão com o sistema remoto já exista.</span><span class="sxs-lookup"><span data-stu-id="539ad-159">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="setting-the-value-of-items-in-the--wsman-drive"></a><span data-ttu-id="539ad-160">Definindo o valor de itens na unidade WSMAN:</span><span class="sxs-lookup"><span data-stu-id="539ad-160">Setting the value of items in the  WSMAN: drive</span></span>

<span data-ttu-id="539ad-161">Você pode usar o `Set-Item` cmdlet para alterar as definições de configuração na `WSMAN` unidade.</span><span class="sxs-lookup"><span data-stu-id="539ad-161">You can use the `Set-Item` cmdlet to change configuration settings in the `WSMAN` drive.</span></span> <span data-ttu-id="539ad-162">O exemplo a seguir define o valor **TrustedHosts** para aceitar todos os hosts com o sufixo "contoso.com".</span><span class="sxs-lookup"><span data-stu-id="539ad-162">The following example sets the **TrustedHosts** value to accept all hosts with the suffix "contoso.com".</span></span>

```powershell
# You do not need to specify the -Path parameter name when using Set-Item.
PS WSMAN:\localhost\Client> Set-Item .\TrustedHosts -Value "*.contoso.com"
```

<span data-ttu-id="539ad-163">O `Set-Item` cmdlet dá suporte a um parâmetro adicional `-Concatenate` que acrescenta um valor em vez de alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="539ad-163">The `Set-Item` cmdlet supports an additional parameter `-Concatenate` that appends a value instead of changing it.</span></span> <span data-ttu-id="539ad-164">O exemplo a seguir acrescentará um novo valor "\*. domain2.com" ao valor antigo armazenado em `TrustedHost:`</span><span class="sxs-lookup"><span data-stu-id="539ad-164">The following example will append a new value "\*.domain2.com" to the old value stored in `TrustedHost:`</span></span>

```powershell
Set-Item WSMAN:\localhost\Client\TrustedHosts *.domain2.com -Concatenate
```

## <a name="creating-items-in-the-wsman-drive"></a><span data-ttu-id="539ad-165">Criando itens na unidade WSMAN:</span><span class="sxs-lookup"><span data-stu-id="539ad-165">Creating items in the WSMAN: drive</span></span>

### <a name="creating-a-new-listener"></a><span data-ttu-id="539ad-166">Criando um novo ouvinte</span><span class="sxs-lookup"><span data-stu-id="539ad-166">Creating a new listener</span></span>

<span data-ttu-id="539ad-167">O `New-Item` cmdlet cria itens em uma unidade de provedor.</span><span class="sxs-lookup"><span data-stu-id="539ad-167">The `New-Item` cmdlet creates items within a provider drive.</span></span> <span data-ttu-id="539ad-168">Cada provedor tem diferentes tipos de item que você pode criar.</span><span class="sxs-lookup"><span data-stu-id="539ad-168">Each provider has different item types that you can create.</span></span> <span data-ttu-id="539ad-169">Na `WSMAN:` unidade, você pode criar *ouvintes* que você configura para receber e responder a solicitações remotas.</span><span class="sxs-lookup"><span data-stu-id="539ad-169">In the `WSMAN:` drive, you can create *Listeners* which you configure to receive and respond to remote requests.</span></span> <span data-ttu-id="539ad-170">O comando a seguir cria um novo ouvinte HTTP usando o `New-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="539ad-170">The following command creates a new HTTP listener using the `New-Item` cmdlet.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Listener -Address * -Transport HTTP -force
```

### <a name="creating-a-new-plug-in"></a><span data-ttu-id="539ad-171">Criando um novo plug-in</span><span class="sxs-lookup"><span data-stu-id="539ad-171">Creating a new plug-in</span></span>

<span data-ttu-id="539ad-172">Este comando cria (registra) um plug-in para o serviço WS-Management.</span><span class="sxs-lookup"><span data-stu-id="539ad-172">This command creates (registers) a plug-in for the WS-Management service.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin `
         -Plugin TestPlugin `
         -FileName %systemroot%\system32\WsmWmiPl.dll `
         -Resource http://schemas.dmtf.org/wbem/wscim/2/cim-schema `
         -SDKVersion 1 `
         -Capability "Get","Put","Invoke","Enumerate" `
         -XMLRenderingType text
```

### <a name="creating-a-new-resource-entry"></a><span data-ttu-id="539ad-173">Criando uma nova entrada de recurso</span><span class="sxs-lookup"><span data-stu-id="539ad-173">Creating a new resource entry</span></span>

<span data-ttu-id="539ad-174">Esse comando cria uma entrada de recurso no diretório de recursos de um TestPlugin.</span><span class="sxs-lookup"><span data-stu-id="539ad-174">This command creates a resource entry in the Resources directory of a TestPlugin.</span></span> <span data-ttu-id="539ad-175">Esse comando pressupõe que um TestPlugin foi criado usando um comando separado.</span><span class="sxs-lookup"><span data-stu-id="539ad-175">This command assumes that a TestPlugin has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\Resources `
         -ResourceUri http://schemas.dmtf.org/wbem/wscim/3/cim-schema `
         -Capability "Enumerate"

```

### <a name="creating-a-new-security-entry-for-a-resource"></a><span data-ttu-id="539ad-176">Criando uma nova entrada de segurança para um recurso</span><span class="sxs-lookup"><span data-stu-id="539ad-176">Creating a new security entry for a resource</span></span>

<span data-ttu-id="539ad-177">Este comando cria uma entrada de segurança no diretório Security do Resource_5967683 (um recurso específico).</span><span class="sxs-lookup"><span data-stu-id="539ad-177">This command creates a security entry in the Security directory of Resource_5967683 (a specific resource).</span></span> <span data-ttu-id="539ad-178">Esse comando pressupõe que a entrada de recurso tenha sido criada usando um comando separado.</span><span class="sxs-lookup"><span data-stu-id="539ad-178">This command assumes that the resource entry has been created using a separate command.</span></span>

```powershell
$path = "WSMan:\localhost\Plugin\TestPlugin\Resources\Resource_5967683"
New-Item -Path $path\Security `
         -Sddl "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GWGX;;;WD)"
```

### <a name="creating-a-new-client-certificate"></a><span data-ttu-id="539ad-179">Criando um novo certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="539ad-179">Creating a new Client Certificate</span></span>

<span data-ttu-id="539ad-180">Esse comando cria a entrada **ClientCertificate** que pode ser usada pelo cliente de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="539ad-180">This command creates **ClientCertificate** entry that can be used by the WS-Management client.</span></span> <span data-ttu-id="539ad-181">O novo **ClientCertificate** aparecerá no diretório **ClientCertificate** como "ClientCertificate_1234567890".</span><span class="sxs-lookup"><span data-stu-id="539ad-181">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="539ad-182">Todos os parâmetros são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="539ad-182">All of the parameters are mandatory.</span></span> <span data-ttu-id="539ad-183">O **emissor** precisa ser impressão digital do certificado dos emissores.</span><span class="sxs-lookup"><span data-stu-id="539ad-183">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* `
         -Credential $cred;
```

### <a name="creating-a-new-initialization-parameter"></a><span data-ttu-id="539ad-184">Criando um novo parâmetro de inicialização</span><span class="sxs-lookup"><span data-stu-id="539ad-184">Creating a new Initialization Parameter</span></span>

<span data-ttu-id="539ad-185">Este comando cria um parâmetro de inicialização chamado "testparametername" no diretório "InitializationParameters".</span><span class="sxs-lookup"><span data-stu-id="539ad-185">This command creates an Initialization parameter named "testparametername" in the "InitializationParameters" directory.</span></span> <span data-ttu-id="539ad-186">Esse comando pressupõe que "TestPlugin" foi criado usando um comando separado.</span><span class="sxs-lookup"><span data-stu-id="539ad-186">This command assumes that the "TestPlugin" has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\InitializationParameters `
         -ParamName testparametername `
         -ParamValue testparametervalue
```

## <a name="dynamic-parameters"></a><span data-ttu-id="539ad-187">Parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="539ad-187">Dynamic parameters</span></span>

<span data-ttu-id="539ad-188">Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.</span><span class="sxs-lookup"><span data-stu-id="539ad-188">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="address-string"></a><span data-ttu-id="539ad-189">Address \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-189">Address \<String\></span></span>

<span data-ttu-id="539ad-190">Especifica o endereço para o qual este ouvinte foi criado.</span><span class="sxs-lookup"><span data-stu-id="539ad-190">Specifies the address for which this listener was created.</span></span> <span data-ttu-id="539ad-191">O valor pode ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="539ad-191">The value can be one of the following:</span></span>

- <span data-ttu-id="539ad-192">A cadeia de caracteres literal "\*".</span><span class="sxs-lookup"><span data-stu-id="539ad-192">The literal string "\*".</span></span> <span data-ttu-id="539ad-193">(O caractere curinga ( `*` ) faz com que o comando vincule todos os endereços IP em todos os adaptadores de rede.)</span><span class="sxs-lookup"><span data-stu-id="539ad-193">(The wildcard character (`*`) makes the command bind all the IP addresses on all the network adapters.)</span></span>
- <span data-ttu-id="539ad-194">A cadeia de caracteres literal "IP:" seguida por um endereço IP válido em um formato decimal com ponto de IPv4 ou no formato hexadecimal clonado de IPv6.</span><span class="sxs-lookup"><span data-stu-id="539ad-194">The literal string "IP:" followed by a valid IP address in either IPv4 dotted-decimal format or in IPv6 cloned-hexadecimal format.</span></span>
- <span data-ttu-id="539ad-195">A cadeia de caracteres literal "MAC:" seguida pelo endereço MAC de um adaptador.</span><span class="sxs-lookup"><span data-stu-id="539ad-195">The literal string "MAC:" followed by the MAC address of an adapter.</span></span>
  <span data-ttu-id="539ad-196">Por exemplo: MAC: 32-a3-58 -90-ser-CC.</span><span class="sxs-lookup"><span data-stu-id="539ad-196">For example: MAC:32-a3-58-90-be-cc.</span></span>

> [!NOTE]
> <span data-ttu-id="539ad-197">O valor Address é definido durante a criação de um Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="539ad-197">The Address value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-198">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-198">Cmdlets supported</span></span>

- [<span data-ttu-id="539ad-199">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-199">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="capability-enumeration"></a><span data-ttu-id="539ad-200">Capability \<Enumeration\></span><span class="sxs-lookup"><span data-stu-id="539ad-200">Capability \<Enumeration\></span></span>

<span data-ttu-id="539ad-201">Ao trabalhar com *plug-ins,* esse parâmetro especifica uma operação com suporte neste Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="539ad-201">When working with *Plug-ins* this parameter specifies an operation that is supported on this Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="539ad-202">Você precisa criar uma entrada para cada tipo de operação ao qual o URI dá suporte.</span><span class="sxs-lookup"><span data-stu-id="539ad-202">You have to create one entry for each type of operation that the URI supports.</span></span> <span data-ttu-id="539ad-203">Você pode especificar qualquer atributo válido para uma determinada operação, se a operação oferecer suporte a ela.</span><span class="sxs-lookup"><span data-stu-id="539ad-203">You can specify any valid attributes for a given operation, if the operation supports it.</span></span>

<span data-ttu-id="539ad-204">Esses atributos incluem **SupportsFiltering** e **SupportsFragment**.</span><span class="sxs-lookup"><span data-stu-id="539ad-204">These attributes include **SupportsFiltering** and **SupportsFragment**.</span></span>

- <span data-ttu-id="539ad-205">**Create**: há suporte para operações Create no URI.</span><span class="sxs-lookup"><span data-stu-id="539ad-205">**Create**: Create operations are supported on the URI.</span></span>
  - <span data-ttu-id="539ad-206">O atributo **SupportFragment**  será usado se a operação de criação der suporte ao conceito.</span><span class="sxs-lookup"><span data-stu-id="539ad-206">The **SupportFragment**  attribute is used if the Create operation supports the concept.</span></span>
  - <span data-ttu-id="539ad-207">O atributo **SUPPORTFILTERING** não é válido para operações Create e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="539ad-207">The **SupportFiltering** attribute is NOT valid for Create operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="539ad-208">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="539ad-208">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="539ad-209">**Delete**: há suporte para operações Delete no URI.</span><span class="sxs-lookup"><span data-stu-id="539ad-209">**Delete**: Delete operations are supported on the URI.</span></span>
  - <span data-ttu-id="539ad-210">O atributo **SupportFragment** será usado se a operação de exclusão der suporte ao conceito.</span><span class="sxs-lookup"><span data-stu-id="539ad-210">The **SupportFragment** attribute is used if the Delete operation supports the concept.</span></span>
  - <span data-ttu-id="539ad-211">O atributo **SUPPORTFILTERING** não é válido para operações Delete e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="539ad-211">The **SupportFiltering** attribute is NOT valid for Delete operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="539ad-212">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="539ad-212">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="539ad-213">**Enumerar**: as operações de enumeração têm suporte no URI.</span><span class="sxs-lookup"><span data-stu-id="539ad-213">**Enumerate**: Enumerate operations are supported on the URI.</span></span>
  - <span data-ttu-id="539ad-214">O atributo **SUPPORTFRAGMENT** não tem suporte para operações de enumeração e deve ser definido como false.</span><span class="sxs-lookup"><span data-stu-id="539ad-214">The **SupportFragment** attribute is NOT supported for Enumerate operations and should be set to False.</span></span>
  - <span data-ttu-id="539ad-215">O atributo **SupportFiltering** é válido e, se o plug-in der suporte à filtragem, esse atributo deverá ser definido como "true".</span><span class="sxs-lookup"><span data-stu-id="539ad-215">The **SupportFiltering** attribute is valid, and if the plug-in supports filtering, this attribute should be set to "True".</span></span>
  > [!NOTE]
  > <span data-ttu-id="539ad-216">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="539ad-216">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="539ad-217">**Get**: há suporte para operações Get no URI.</span><span class="sxs-lookup"><span data-stu-id="539ad-217">**Get**: Get operations are supported on the URI.</span></span>
  - <span data-ttu-id="539ad-218">O atributo **SupportFragment** será usado se a operação get der suporte ao conceito.</span><span class="sxs-lookup"><span data-stu-id="539ad-218">The **SupportFragment** attribute is used if the Get operation supports the concept.</span></span>
  - <span data-ttu-id="539ad-219">O atributo **SUPPORTFILTERING** não é válido para operações Get e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="539ad-219">The **SupportFiltering** attribute is NOT valid for Get operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="539ad-220">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="539ad-220">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="539ad-221">As operações **Invoke**: Invoke têm suporte no URI.</span><span class="sxs-lookup"><span data-stu-id="539ad-221">**Invoke**: Invoke operations are supported on the URI.</span></span>
  - <span data-ttu-id="539ad-222">O atributo **SupportFragment** não tem suporte para operações Invoke e deve ser definido como false.</span><span class="sxs-lookup"><span data-stu-id="539ad-222">The **SupportFragment** attribute is not supported for Invoke operations and should be set to False.</span></span>
  - <span data-ttu-id="539ad-223">O atributo **SupportFiltering** não é válido e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="539ad-223">The **SupportFiltering** attribute is not valid and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="539ad-224">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="539ad-224">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="539ad-225">**Put**: as operações Put têm suporte no URI.</span><span class="sxs-lookup"><span data-stu-id="539ad-225">**Put**: Put operations are supported on the URI.</span></span>
  - <span data-ttu-id="539ad-226">O atributo **SupportFragment** será usado se a operação Put der suporte ao conceito.</span><span class="sxs-lookup"><span data-stu-id="539ad-226">The **SupportFragment** attribute is used if the Put operation supports the concept.</span></span>
  - <span data-ttu-id="539ad-227">O atributo **SupportFiltering** não é válido para operações Put e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="539ad-227">The **SupportFiltering** attribute is not valid for Put operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="539ad-228">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="539ad-228">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="539ad-229">**Assinar**: há suporte para operações de assinatura no URI.</span><span class="sxs-lookup"><span data-stu-id="539ad-229">**Subscribe**: Subscribe operations are supported on the URI.</span></span>
  - <span data-ttu-id="539ad-230">O atributo **SupportFragment** não tem suporte para operações de assinatura e deve ser definido como false.</span><span class="sxs-lookup"><span data-stu-id="539ad-230">The **SupportFragment** attribute is not supported for Subscribe operations and should be set to False.</span></span>
  - <span data-ttu-id="539ad-231">O atributo **SupportFiltering** não é válido para operações de assinatura e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="539ad-231">The **SupportFiltering** attribute is not valid for Subscribe operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="539ad-232">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="539ad-232">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="539ad-233">**Shell**: há suporte para operações de Shell no URI.</span><span class="sxs-lookup"><span data-stu-id="539ad-233">**Shell**: Shell operations are supported on the URI.</span></span>
  - <span data-ttu-id="539ad-234">O atributo **SupportFragment** não tem suporte para operações de shell e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="539ad-234">The **SupportFragment** attribute is not supported for Shell operations and should be set to "False".</span></span>
  - <span data-ttu-id="539ad-235">O atributo **SupportFiltering** não é válido para operações de shell e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="539ad-235">The **SupportFiltering** attribute is not valid for Shell operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="539ad-236">Essa operação não será válida para um URI se qualquer outra operação também tiver suporte.</span><span class="sxs-lookup"><span data-stu-id="539ad-236">This operation is not valid for a URI if ANY other operation is also supported.</span></span>
  > [!NOTE]
  > <span data-ttu-id="539ad-237">Se uma operação Shell estiver configurada para uma operação URI, Get, Put, Create, Delete, Invoke e Enumerate será processada internamente no serviço WS-Management (WinRM) para gerenciar os shells.</span><span class="sxs-lookup"><span data-stu-id="539ad-237">If a Shell operation is configured for a URI, Get, Put, Create, Delete, Invoke, and Enumerate operations are processed internally within the WS-Management (WinRM) service to manage shells.</span></span> <span data-ttu-id="539ad-238">Como resultado, o plug-in não pode manipular as operações.</span><span class="sxs-lookup"><span data-stu-id="539ad-238">As a result, the plug-in cannot handle the operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-239">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-239">Cmdlets supported</span></span>

- [<span data-ttu-id="539ad-240">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-240">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="certificatethumbprint-string"></a><span data-ttu-id="539ad-241">CertificateThumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-241">CertificateThumbprint \<String\></span></span>

<span data-ttu-id="539ad-242">Especifica a impressão digital do certificado de serviço.</span><span class="sxs-lookup"><span data-stu-id="539ad-242">Specifies the thumbprint of the service certificate.</span></span>

<span data-ttu-id="539ad-243">Esse valor representa a cadeia de caracteres de valores de dois dígitos hexadecimais no campo Impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="539ad-243">This value represents the string of two-digit hexadecimal values in the Thumbprint field of the certificate.</span></span> <span data-ttu-id="539ad-244">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="539ad-244">It specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="539ad-245">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="539ad-245">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="539ad-246">Eles podem ser mapeados somente para contas de usuário locais; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="539ad-246">They can be mapped only to local user accounts, and they do not work with domain accounts.</span></span> <span data-ttu-id="539ad-247">Para obter uma impressão digital do certificado, use os `Get-Item` `Get-ChildItem` cmdlets ou na `Cert:` unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="539ad-247">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell `Cert:` drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-248">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-248">Cmdlets supported</span></span>

- [<span data-ttu-id="539ad-249">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-249">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="enabled-boolean"></a><span data-ttu-id="539ad-250">Enabled \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="539ad-250">Enabled \<Boolean\></span></span>

<span data-ttu-id="539ad-251">Especifica se o ouvinte está habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="539ad-251">Specifies whether the listener is enabled or disabled.</span></span> <span data-ttu-id="539ad-252">O padrão é True.</span><span class="sxs-lookup"><span data-stu-id="539ad-252">The default is True.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-253">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-253">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-254">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-254">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="filename-plugin-string"></a><span data-ttu-id="539ad-255">FileName (Plugin) \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-255">FileName (Plugin) \<String\></span></span>

<span data-ttu-id="539ad-256">Especifica o nome do arquivo do plug-in de operações.</span><span class="sxs-lookup"><span data-stu-id="539ad-256">Specifies the file name of the operations plug-in.</span></span> <span data-ttu-id="539ad-257">Todas as variáveis de ambiente colocadas nessa entrada serão expandidas no contexto dos usuários quando uma solicitação for recebida.</span><span class="sxs-lookup"><span data-stu-id="539ad-257">Any environment variables that are put in this entry will be expanded in the users' context when a request is received.</span></span> <span data-ttu-id="539ad-258">Como cada usuário pode ter uma versão diferente da mesma variável de ambiente, cada usuário poderia ter um plug-in diferente.</span><span class="sxs-lookup"><span data-stu-id="539ad-258">Because each user could have a different version of the same environment variable, each user could have a different plug-in.</span></span> <span data-ttu-id="539ad-259">Essa entrada não pode ficar em branco e deve apontar para um plug-in válido.</span><span class="sxs-lookup"><span data-stu-id="539ad-259">This entry cannot be blank and must point to a valid plug-in.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-260">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-260">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-261">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-261">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="hostname-string"></a><span data-ttu-id="539ad-262">HostName \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-262">HostName \<String\></span></span>

<span data-ttu-id="539ad-263">Especifica o nome de host do computador no qual o serviço WS-Management (WinRM) está em execução.</span><span class="sxs-lookup"><span data-stu-id="539ad-263">Specifies the host name of the computer on which the WS-Management (WinRM) service is running.</span></span>

<span data-ttu-id="539ad-264">O valor deve ser um nome de domínio totalmente qualificado, uma cadeia de caracteres literal IPv4 ou IPv6 ou um caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="539ad-264">The value must be a fully qualified domain name, an IPv4 or IPv6 literal string, or a wildcard character.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-265">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-265">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-266">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-266">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="issuer-string"></a><span data-ttu-id="539ad-267">Issuer \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-267">Issuer \<String\></span></span>

<span data-ttu-id="539ad-268">Especifica o nome da autoridade de certificação que emitiu o certificado.</span><span class="sxs-lookup"><span data-stu-id="539ad-268">Specifies the name of the certification authority that issued the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-269">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-269">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-270">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-270">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="plugin--ws-management-plug-ins-are-native-dynamic-link-libraries-dlls"></a><span data-ttu-id="539ad-271">\<\>Plug-ins de WS-Management do plug-in são DLLs (bibliotecas de vínculo dinâmico) nativas</span><span class="sxs-lookup"><span data-stu-id="539ad-271">Plugin \<\> WS-Management plug-ins are native dynamic link libraries (DLLs)</span></span>

<span data-ttu-id="539ad-272">que se conectam e estendem a funcionalidade do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="539ad-272">that plug in to and extend the functionality of WS-Management .</span></span> <span data-ttu-id="539ad-273">A API de plug-in do WSW-Management fornece funcionalidade que permite que um usuário escreva plug-ins implementando determinadas APIs para operações e URIs de recursos com suporte.</span><span class="sxs-lookup"><span data-stu-id="539ad-273">The WSW-Management Plug-in API provides functionality that enables a user to write plug-ins by implementing certain APIs for supported resource URIs and operations.</span></span> <span data-ttu-id="539ad-274">Depois que os plug-ins estiverem configurados para o serviço WS-Management (WinRM) ou para Serviços de Informações da Internet (IIS), os plug-ins são carregados no host WS-Management ou no host IIS, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="539ad-274">After the plug-ins are configured for either the WS-Management (WinRM) service or for Internet Information Services (IIS), the plug-ins are loaded in the WS-Management host or in the IIS host, respectively.</span></span> <span data-ttu-id="539ad-275">As solicitações remotas são roteadas para esses pontos de entrada de plug-in para executar operações.</span><span class="sxs-lookup"><span data-stu-id="539ad-275">Remote requests are routed to these plug-in entry points to perform operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-276">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-276">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-277">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-277">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="port-unsigned-short-integer"></a><span data-ttu-id="539ad-278">Port \<Unsigned Short Integer\></span><span class="sxs-lookup"><span data-stu-id="539ad-278">Port \<Unsigned Short Integer\></span></span>

<span data-ttu-id="539ad-279">Especifica a porta TCP para a qual este ouvinte é criado.</span><span class="sxs-lookup"><span data-stu-id="539ad-279">Specifies the TCP port for which this listener is created.</span></span> <span data-ttu-id="539ad-280">Você pode especificar qualquer valor entre 1 e 65535.</span><span class="sxs-lookup"><span data-stu-id="539ad-280">You can specify any value from 1 through 65535.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-281">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-281">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-282">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-282">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="539ad-283">Resource \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-283">Resource \<String\></span></span>

<span data-ttu-id="539ad-284">Especifica um ponto de extremidade que representa um tipo distinto de valor ou operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="539ad-284">Specifies an endpoint that represents a distinct type of management operation or value.</span></span> <span data-ttu-id="539ad-285">Um serviço expõe um ou mais recursos, e alguns recursos podem ter mais de uma instância.</span><span class="sxs-lookup"><span data-stu-id="539ad-285">A service exposes one or more resources, and some resources can have more than one instance.</span></span> <span data-ttu-id="539ad-286">Um recurso de gerenciamento é semelhante a uma classe WMI ou a uma tabela de banco de dados e uma instância é semelhante a uma instância da classe ou a uma linha na tabela.</span><span class="sxs-lookup"><span data-stu-id="539ad-286">A management resource is similar to a WMI class or to a database table, and an instance is similar to an instance of the class or to a row in the table.</span></span> <span data-ttu-id="539ad-287">Por exemplo, a classe **Win32_LogicalDisk** representa um recurso.</span><span class="sxs-lookup"><span data-stu-id="539ad-287">For example, the **Win32_LogicalDisk** class represents a resource.</span></span> <span data-ttu-id="539ad-288">`Win32_LogicalDisk="C:\\"` é uma instância específica do recurso.</span><span class="sxs-lookup"><span data-stu-id="539ad-288">`Win32_LogicalDisk="C:\\"` is a specific instance of the resource.</span></span>

<span data-ttu-id="539ad-289">Um identificador de recurso uniforme (URI) contém um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="539ad-289">A Uniform Resource Identifier (URI) contains a prefix and a path to a resource.</span></span>
<span data-ttu-id="539ad-290">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="539ad-290">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-291">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-291">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-292">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-292">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="539ad-293">Resource \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-293">Resource \<String\></span></span>

<span data-ttu-id="539ad-294">Especifica o Uniform Resource identificador (URI) que identifica um tipo de recurso, como um disco ou um processo, em um computador específico.</span><span class="sxs-lookup"><span data-stu-id="539ad-294">Specifies the Uniform Resource Identifier (URI) that identifies a specific type of resource, such as a disk or a process, on a computer.</span></span>

<span data-ttu-id="539ad-295">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="539ad-295">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="539ad-296">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="539ad-296">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-297">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-297">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-298">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-298">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sdkversion-string"></a><span data-ttu-id="539ad-299">SDKVersion \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-299">SDKVersion \<String\></span></span>

<span data-ttu-id="539ad-300">Especifica a versão do SDK do plug-in do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="539ad-300">Specifies the version of the WS-Management plug-in SDK.</span></span> <span data-ttu-id="539ad-301">O único valor válido é</span><span class="sxs-lookup"><span data-stu-id="539ad-301">The only valid value is</span></span>
1.

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-302">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-302">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-303">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-303">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="subject-string"></a><span data-ttu-id="539ad-304">Subject \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-304">Subject \<String\></span></span>

<span data-ttu-id="539ad-305">Especifica a entidade que é identificada pelo certificado.</span><span class="sxs-lookup"><span data-stu-id="539ad-305">Specifies the entity that is identified by the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-306">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-306">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-307">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-307">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="transport-string"></a><span data-ttu-id="539ad-308">Transport \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-308">Transport \<String\></span></span>

<span data-ttu-id="539ad-309">Especifica o transporte a ser usado para enviar e receber respostas e solicitações do protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="539ad-309">Specifies the transport to use to send and receive WS-Management protocol requests and responses.</span></span> <span data-ttu-id="539ad-310">O valor deve ser HTTP ou HTTPS.</span><span class="sxs-lookup"><span data-stu-id="539ad-310">The value must be either HTTP or HTTPS.</span></span>

<span data-ttu-id="539ad-311">Observação: o valor de transporte é definido durante a criação de um ouvinte.</span><span class="sxs-lookup"><span data-stu-id="539ad-311">Note: The Transport value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-312">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-312">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-313">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-313">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="uri-string"></a><span data-ttu-id="539ad-314">URI \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-314">URI \<String\></span></span>

<span data-ttu-id="539ad-315">Identifica o URI para o qual o acesso é autorizado com base no valor do parâmetro Sddl.</span><span class="sxs-lookup"><span data-stu-id="539ad-315">Identifies the URI for which access is authorized based on the value of the Sddl parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-316">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-316">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-317">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-317">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="urlprefix-string"></a><span data-ttu-id="539ad-318">URLPrefix \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-318">URLPrefix \<String\></span></span>

<span data-ttu-id="539ad-319">Um prefixo de URL no qual aceitar solicitações de HTTP ou HTTPS.</span><span class="sxs-lookup"><span data-stu-id="539ad-319">A URL prefix on which to accept HTTP or HTTPS requests.</span></span> <span data-ttu-id="539ad-320">Esta é uma cadeia de caracteres que contém apenas os caracteres `[a-z]` , `[A-Z]` ,, `[9-0]` sublinhado ( `_` ) e barra invertida ( `/` ).</span><span class="sxs-lookup"><span data-stu-id="539ad-320">This is a string containing only the characters `[a-z]`, `[A-Z]`, `[9-0]`, underscore (`_`) and backslash (`/`).</span></span> <span data-ttu-id="539ad-321">A cadeia de caracteres não deve começar com ou terminar com uma barra invertida ( `/` ).</span><span class="sxs-lookup"><span data-stu-id="539ad-321">The string must not start with or end with a backslash (`/`).</span></span> <span data-ttu-id="539ad-322">Por exemplo, se o nome do computador for "SampleComputer", o cliente WS-Management especificaria `http://SampleMachine/URLPrefix` no endereço de destino.</span><span class="sxs-lookup"><span data-stu-id="539ad-322">For example, if the computer name is "SampleComputer", the WS-Management client would specify `http://SampleMachine/URLPrefix` in the destination address.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-323">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-323">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-324">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-324">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="value-string"></a><span data-ttu-id="539ad-325">Value \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-325">Value \<String\></span></span>

<span data-ttu-id="539ad-326">Especifica o valor de um parâmetro de inicialização, que é um valor de plug-in específico usado para especificar opções de configuração.</span><span class="sxs-lookup"><span data-stu-id="539ad-326">Specifies the value of an initialization parameter, which is a plug-in-specific value that is used to specify configuration options.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-327">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-327">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-328">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-328">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="xmlrenderingtype-string"></a><span data-ttu-id="539ad-329">XMLRenderingType \<String\></span><span class="sxs-lookup"><span data-stu-id="539ad-329">XMLRenderingType \<String\></span></span>

<span data-ttu-id="539ad-330">Especifica o formato em que o XML é passado aos plug-ins por meio do objeto **WSMAN_DATA** .</span><span class="sxs-lookup"><span data-stu-id="539ad-330">Specifies the format in which XML is passed to plug-ins through the **WSMAN_DATA** object.</span></span> <span data-ttu-id="539ad-331">Os seguintes valores são válidos:</span><span class="sxs-lookup"><span data-stu-id="539ad-331">The following are valid values:</span></span>

- <span data-ttu-id="539ad-332">Text: os dados XML de entrada estão contidos em uma estrutura de **WSMAN_DATA_TYPE_TEXT** , que representa o XML como um buffer de memória **PCWSTR** .</span><span class="sxs-lookup"><span data-stu-id="539ad-332">Text: Incoming XML data is contained in a **WSMAN_DATA_TYPE_TEXT** structure, which represents the XML as a **PCWSTR** memory buffer.</span></span>
- <span data-ttu-id="539ad-333">XMLReader: os dados XML de entrada estão contidos em uma estrutura de **WSMAN_DATA_TYPE_WS_XML_READER** , que representa o XML como um objeto **XmlReader** , que é definido no arquivo de cabeçalho "WebServices. h".</span><span class="sxs-lookup"><span data-stu-id="539ad-333">XMLReader: Incoming XML data is contained in a **WSMAN_DATA_TYPE_WS_XML_READER** structure, which represents the XML as an **XmlReader** object, which is defined in the "WebServices.h" header file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="539ad-334">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="539ad-334">Cmdlets Supported</span></span>

- [<span data-ttu-id="539ad-335">New-Item</span><span class="sxs-lookup"><span data-stu-id="539ad-335">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="539ad-336">Usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="539ad-336">Using the pipeline</span></span>

<span data-ttu-id="539ad-337">Os cmdlets do provedor aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="539ad-337">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="539ad-338">Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.</span><span class="sxs-lookup"><span data-stu-id="539ad-338">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="539ad-339">Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="539ad-339">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="539ad-340">Obtendo ajuda</span><span class="sxs-lookup"><span data-stu-id="539ad-340">Getting help</span></span>

<span data-ttu-id="539ad-341">A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="539ad-341">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="539ad-342">Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) para especificar uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="539ad-342">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path wsman:
```

## <a name="see-also"></a><span data-ttu-id="539ad-343">Consulte também</span><span class="sxs-lookup"><span data-stu-id="539ad-343">See also</span></span>

[<span data-ttu-id="539ad-344">about_Providers</span><span class="sxs-lookup"><span data-stu-id="539ad-344">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)

