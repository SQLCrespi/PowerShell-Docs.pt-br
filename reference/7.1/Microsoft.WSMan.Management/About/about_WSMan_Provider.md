---
description: WSMan
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_wsman_provider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor WSMan
ms.openlocfilehash: 7c693d29c6cc7743f7a423ae347889abb10ad255
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196377"
---
# <a name="wsman-provider"></a><span data-ttu-id="6826a-104">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="6826a-104">WSMan Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="6826a-105">Nome do provedor</span><span class="sxs-lookup"><span data-stu-id="6826a-105">Provider name</span></span>

<span data-ttu-id="6826a-106">WSMan</span><span class="sxs-lookup"><span data-stu-id="6826a-106">WSMan</span></span>

## <a name="drives"></a><span data-ttu-id="6826a-107">Unidades</span><span class="sxs-lookup"><span data-stu-id="6826a-107">Drives</span></span>

`WSMan:`

## <a name="short-description"></a><span data-ttu-id="6826a-108">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="6826a-108">Short description</span></span>

<span data-ttu-id="6826a-109">Fornece acesso a serviços Web para obter informações de configuração de gerenciamento (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="6826a-109">Provides access to Web Services for Management (WS-Management) configuration information.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="6826a-110">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="6826a-110">Detailed description</span></span>

<span data-ttu-id="6826a-111">O provedor **WSMan** para PowerShell permite que você adicione, altere, apague e exclua WS-Management dados de configuração em computadores locais ou remotos.</span><span class="sxs-lookup"><span data-stu-id="6826a-111">The **WSMan** provider for PowerShell lets you add, change, clear, and delete WS-Management configuration data on local or remote computers.</span></span>

<span data-ttu-id="6826a-112">O provedor **WSMan** expõe uma unidade do PowerShell com uma estrutura de diretório que corresponde a um agrupamento lógico de definições de configuração de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="6826a-112">The **WSMan** provider exposes a PowerShell drive with a directory structure that corresponds to a logical grouping of WS-Management configuration settings.</span></span> <span data-ttu-id="6826a-113">Esses agrupamentos são conhecidos como contêineres.</span><span class="sxs-lookup"><span data-stu-id="6826a-113">These groupings are known as containers.</span></span>

<span data-ttu-id="6826a-114">A partir do Windows PowerShell 3,0, o provedor **WSMan** foi atualizado para dar suporte a novas propriedades para configurações de sessão, como **OutputBufferingMode** .</span><span class="sxs-lookup"><span data-stu-id="6826a-114">Beginning in Windows PowerShell 3.0, the **WSMan** provider has been updated to support new properties for session configurations, such as **OutputBufferingMode** .</span></span> <span data-ttu-id="6826a-115">As configurações de sessão aparecem como itens no diretório de plug-in da `WSMan:` unidade e as propriedades aparecem como itens em cada configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="6826a-115">The session configurations appear as items in the Plugin directory of the `WSMan:` drive and the properties appear as items in each session configuration.</span></span>

<span data-ttu-id="6826a-116">O provedor **WSMan** dá suporte aos seguintes cmdlets, que são abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="6826a-116">The **WSMan** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="6826a-117">Get-Location</span><span class="sxs-lookup"><span data-stu-id="6826a-117">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="6826a-118">Set-Location</span><span class="sxs-lookup"><span data-stu-id="6826a-118">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="6826a-119">Get-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-119">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="6826a-120">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="6826a-120">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="6826a-121">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-121">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="6826a-122">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-122">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

> [!NOTE]
> <span data-ttu-id="6826a-123">Você pode usar os comandos na `WSMan:` unidade para alterar os valores das novas propriedades.</span><span class="sxs-lookup"><span data-stu-id="6826a-123">You can use commands in the `WSMan:` drive to change the values of the new properties.</span></span> <span data-ttu-id="6826a-124">No entanto, você não pode usar a `WSMan:` unidade no PowerShell 2,0 para alterar as propriedades introduzidas no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="6826a-124">However, you cannot use the `WSMan:` drive in PowerShell 2.0 to change properties that are introduced in Windows PowerShell 3.0.</span></span>
> <span data-ttu-id="6826a-125">Embora nenhum erro seja gerado, os comandos não são efetivos para alterar essas configurações, use a unidade **WSMan** no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="6826a-125">Although no error is generated, the commands are not effective To change these settings, use the **WSMan** drive in Windows PowerShell 3.0.</span></span>

### <a name="organization-of-the-wsman-drive"></a><span data-ttu-id="6826a-126">Organização da unidade WSMan:</span><span class="sxs-lookup"><span data-stu-id="6826a-126">Organization of the WSMan: Drive</span></span>

- <span data-ttu-id="6826a-127">**Cliente** : você pode configurar vários aspectos do cliente WS-Management.</span><span class="sxs-lookup"><span data-stu-id="6826a-127">**Client** : You can configure various aspects of the WS-Management client.</span></span> <span data-ttu-id="6826a-128">As informações de configuração são armazenadas no Registro.</span><span class="sxs-lookup"><span data-stu-id="6826a-128">The configuration information is stored in the registry.</span></span>

- <span data-ttu-id="6826a-129">**Serviço** : você pode configurar vários aspectos do serviço de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="6826a-129">**Service** : You can configure various aspects of the WS-Management service.</span></span>
  <span data-ttu-id="6826a-130">As informações de configuração são armazenadas no Registro.</span><span class="sxs-lookup"><span data-stu-id="6826a-130">The configuration information is stored in the registry.</span></span>
  > [!NOTE]
  > <span data-ttu-id="6826a-131">A configuração do serviço, às vezes, é chamada de configuração Server.</span><span class="sxs-lookup"><span data-stu-id="6826a-131">Service configuration is sometimes referred to as Server configuration.</span></span>

- <span data-ttu-id="6826a-132">**Shell** : você pode configurar vários aspectos do WS-Management Shell, como a configuração para permitir acesso de shell remoto ( **AllowRemoteShellAccess** ) e o número máximo de usuários simultâneos permitidos ( **MaxConcurrentUsers** ).</span><span class="sxs-lookup"><span data-stu-id="6826a-132">**Shell** : You can configure various aspects of the WS-Management shell, such as the setting to allow remote shell access ( **AllowRemoteShellAccess** ) and the maximum number of concurrent users allowed ( **MaxConcurrentUsers** ).</span></span>

- <span data-ttu-id="6826a-133">**Ouvinte** : você pode criar e configurar um ouvinte.</span><span class="sxs-lookup"><span data-stu-id="6826a-133">**Listener** : You can create and configure a listener.</span></span> <span data-ttu-id="6826a-134">Um ouvinte é um serviço de gerenciamento que implementa o protocolo WS-Management para enviar e receber mensagens.</span><span class="sxs-lookup"><span data-stu-id="6826a-134">A listener is a management service that implements the WS-Management protocol to send and to receive messages.</span></span>

- <span data-ttu-id="6826a-135">**Plugin** : os plug-ins são carregados e usados pelo serviço de WS-Management para fornecer várias funções.</span><span class="sxs-lookup"><span data-stu-id="6826a-135">**Plugin** : Plug-ins are loaded and used by the WS-Management service to provide various functions.</span></span> <span data-ttu-id="6826a-136">Por padrão, o PowerShell fornece três plug-ins:</span><span class="sxs-lookup"><span data-stu-id="6826a-136">By default, PowerShell provides three plug-ins:</span></span>
  - <span data-ttu-id="6826a-137">O plug-in de encaminhamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="6826a-137">The Event Forwarding plug-in.</span></span>
  - <span data-ttu-id="6826a-138">O plug-in do Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6826a-138">The Microsoft.PowerShell plug-in.</span></span>
  - <span data-ttu-id="6826a-139">O plug-in do provedor de Instrumentação de Gerenciamento do Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="6826a-139">The Windows Management Instrumentation (WMI) Provider plug-in.</span></span>
  <span data-ttu-id="6826a-140">Esses três plug-ins dão suporte ao encaminhamento de eventos, à configuração e ao acesso WMI.</span><span class="sxs-lookup"><span data-stu-id="6826a-140">These three plug-ins support event forwarding, configuration, and WMI access.</span></span>

- <span data-ttu-id="6826a-141">**ClientCertificate** : você pode criar e configurar um certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="6826a-141">**ClientCertificate** : You can create and configure a client certificate.</span></span>
  <span data-ttu-id="6826a-142">Um certificado de cliente é usado quando o cliente do WS-Management está configurado para usar a autenticação de certificado.</span><span class="sxs-lookup"><span data-stu-id="6826a-142">A client certificate is used when the WS-Management client is configured to use certificate authentication.</span></span>

### <a name="directory-hierarchy-of-the-wsman-provider"></a><span data-ttu-id="6826a-143">Hierarquia de diretórios do provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="6826a-143">Directory Hierarchy of the WSMan Provider</span></span>

<span data-ttu-id="6826a-144">A hierarquia de diretórios do provedor WSMan para o computador local é a seguinte.</span><span class="sxs-lookup"><span data-stu-id="6826a-144">The directory hierarchy of the WSMan provider for the local computer is as follows.</span></span>

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

<span data-ttu-id="6826a-145">A hierarquia de diretórios do provedor WSMan para um computador remoto é a mesmo que para um computador local.</span><span class="sxs-lookup"><span data-stu-id="6826a-145">The directory hierarchy of the WSMan provider for a remote computer is the same as a local computer.</span></span> <span data-ttu-id="6826a-146">No entanto, para acessar as configurações de um computador remoto, você precisa estabelecer uma conexão com o computador remoto usando [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span><span class="sxs-lookup"><span data-stu-id="6826a-146">However, in order to access the configuration settings of a remote computer, you need to make a connection to the remote computer using [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span> <span data-ttu-id="6826a-147">Depois que uma conexão é feita para um computador remoto, o nome do computador remoto aparece no provedor.</span><span class="sxs-lookup"><span data-stu-id="6826a-147">Once a connection is made to a remote computer, the name of the remote computer shows up in the provider.</span></span>

```
WSMan:\<Remote_Computer_Name>
```

## <a name="navigating-the-wsman-drive"></a><span data-ttu-id="6826a-148">Navegando na unidade WSMan:</span><span class="sxs-lookup"><span data-stu-id="6826a-148">Navigating the WSMan: Drive</span></span>

<span data-ttu-id="6826a-149">Esse comando usa o `Set-Location` cmdlet para alterar o local atual para a `WSMan:` unidade.</span><span class="sxs-lookup"><span data-stu-id="6826a-149">This command uses the `Set-Location` cmdlet to change the current location to the `WSMan:` drive.</span></span>

```powershell
Set-Location WSMan:
```

<span data-ttu-id="6826a-150">Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="6826a-150">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="6826a-151">Por exemplo, digite.</span><span class="sxs-lookup"><span data-stu-id="6826a-151">For example, type.</span></span>

```powershell
Set-Location C:
```

### <a name="navigating-to-a-remote-system-store-location"></a><span data-ttu-id="6826a-152">Navegando para um local de armazenamento do sistema remoto</span><span class="sxs-lookup"><span data-stu-id="6826a-152">Navigating to a remote system store location</span></span>

<span data-ttu-id="6826a-153">Esse comando usa o `Set-Location` comando para alterar o local atual para o local raiz no local de armazenamento do sistema remoto.</span><span class="sxs-lookup"><span data-stu-id="6826a-153">This command uses the `Set-Location` command to change the current location to the root location in the remote system store location.</span></span> <span data-ttu-id="6826a-154">Use uma barra invertida ou uma barra invertida `\` `/` para indicar um nível da `WSMan:` unidade.</span><span class="sxs-lookup"><span data-stu-id="6826a-154">Use a backslash `\` or forward slash `/` to indicate a level of the `WSMan:` drive.</span></span>

```powershell
Set-Location -Path  WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="6826a-155">O comando acima pressupõe que uma conexão com o sistema remoto já exista.</span><span class="sxs-lookup"><span data-stu-id="6826a-155">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="displaying-the-contents-of-the-wsman-drive"></a><span data-ttu-id="6826a-156">Exibindo o conteúdo da unidade WSMan:</span><span class="sxs-lookup"><span data-stu-id="6826a-156">Displaying the Contents of the WSMan: Drive</span></span>

<span data-ttu-id="6826a-157">Esse comando usa o `Get-Childitem` cmdlet para exibir os repositórios de WS-Management no local de armazenamento do localhost.</span><span class="sxs-lookup"><span data-stu-id="6826a-157">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the Localhost store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\Localhost
```

<span data-ttu-id="6826a-158">Se você estiver na `WSMan:` unidade, poderá omitir o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="6826a-158">If you are in the `WSMan:` drive, you can omit the drive name.</span></span>

<span data-ttu-id="6826a-159">Esse comando usa o `Get-Childitem` cmdlet para exibir os repositórios de WS-Management no local de armazenamento "Server01" do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="6826a-159">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the remote computer "SERVER01" store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="6826a-160">O comando acima pressupõe que uma conexão com o sistema remoto já exista.</span><span class="sxs-lookup"><span data-stu-id="6826a-160">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="setting-the-value-of-items-in-the--wsman-drive"></a><span data-ttu-id="6826a-161">Definindo o valor de itens na unidade WSMAN:</span><span class="sxs-lookup"><span data-stu-id="6826a-161">Setting the value of items in the  WSMAN: drive</span></span>

<span data-ttu-id="6826a-162">Você pode usar o `Set-Item` cmdlet para alterar as definições de configuração na `WSMAN` unidade.</span><span class="sxs-lookup"><span data-stu-id="6826a-162">You can use the `Set-Item` cmdlet to change configuration settings in the `WSMAN` drive.</span></span> <span data-ttu-id="6826a-163">O exemplo a seguir define o valor **TrustedHosts** para aceitar todos os hosts com o sufixo "contoso.com".</span><span class="sxs-lookup"><span data-stu-id="6826a-163">The following example sets the **TrustedHosts** value to accept all hosts with the suffix "contoso.com".</span></span>

```powershell
# You do not need to specify the -Path parameter name when using Set-Item.
PS WSMAN:\localhost\Client> Set-Item .\TrustedHosts -Value "*.contoso.com"
```

<span data-ttu-id="6826a-164">O `Set-Item` cmdlet dá suporte a um parâmetro adicional `-Concatenate` que acrescenta um valor em vez de alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="6826a-164">The `Set-Item` cmdlet supports an additional parameter `-Concatenate` that appends a value instead of changing it.</span></span> <span data-ttu-id="6826a-165">O exemplo a seguir acrescentará um novo valor "\*. domain2.com" ao valor antigo armazenado em `TrustedHost:`</span><span class="sxs-lookup"><span data-stu-id="6826a-165">The following example will append a new value "\*.domain2.com" to the old value stored in `TrustedHost:`</span></span>

```powershell
Set-Item WSMAN:\localhost\Client\TrustedHosts *.domain2.com -Concatenate
```

## <a name="creating-items-in-the-wsman-drive"></a><span data-ttu-id="6826a-166">Criando itens na unidade WSMAN:</span><span class="sxs-lookup"><span data-stu-id="6826a-166">Creating items in the WSMAN: drive</span></span>

### <a name="creating-a-new-listener"></a><span data-ttu-id="6826a-167">Criando um novo ouvinte</span><span class="sxs-lookup"><span data-stu-id="6826a-167">Creating a new listener</span></span>

<span data-ttu-id="6826a-168">O `New-Item` cmdlet cria itens em uma unidade de provedor.</span><span class="sxs-lookup"><span data-stu-id="6826a-168">The `New-Item` cmdlet creates items within a provider drive.</span></span> <span data-ttu-id="6826a-169">Cada provedor tem diferentes tipos de item que você pode criar.</span><span class="sxs-lookup"><span data-stu-id="6826a-169">Each provider has different item types that you can create.</span></span> <span data-ttu-id="6826a-170">Na `WSMAN:` unidade, você pode criar *ouvintes* que você configura para receber e responder a solicitações remotas.</span><span class="sxs-lookup"><span data-stu-id="6826a-170">In the `WSMAN:` drive, you can create *Listeners* which you configure to receive and respond to remote requests.</span></span> <span data-ttu-id="6826a-171">O comando a seguir cria um novo ouvinte HTTP usando o `New-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6826a-171">The following command creates a new HTTP listener using the `New-Item` cmdlet.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Listener -Address * -Transport HTTP -force
```

### <a name="creating-a-new-plug-in"></a><span data-ttu-id="6826a-172">Criando um novo plug-in</span><span class="sxs-lookup"><span data-stu-id="6826a-172">Creating a new plug-in</span></span>

<span data-ttu-id="6826a-173">Este comando cria (registra) um plug-in para o serviço WS-Management.</span><span class="sxs-lookup"><span data-stu-id="6826a-173">This command creates (registers) a plug-in for the WS-Management service.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin `
         -Plugin TestPlugin `
         -FileName %systemroot%\system32\WsmWmiPl.dll `
         -Resource http://schemas.dmtf.org/wbem/wscim/2/cim-schema `
         -SDKVersion 1 `
         -Capability "Get","Put","Invoke","Enumerate" `
         -XMLRenderingType text
```

### <a name="creating-a-new-resource-entry"></a><span data-ttu-id="6826a-174">Criando uma nova entrada de recurso</span><span class="sxs-lookup"><span data-stu-id="6826a-174">Creating a new resource entry</span></span>

<span data-ttu-id="6826a-175">Esse comando cria uma entrada de recurso no diretório de recursos de um TestPlugin.</span><span class="sxs-lookup"><span data-stu-id="6826a-175">This command creates a resource entry in the Resources directory of a TestPlugin.</span></span> <span data-ttu-id="6826a-176">Esse comando pressupõe que um TestPlugin foi criado usando um comando separado.</span><span class="sxs-lookup"><span data-stu-id="6826a-176">This command assumes that a TestPlugin has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\Resources `
         -ResourceUri http://schemas.dmtf.org/wbem/wscim/3/cim-schema `
         -Capability "Enumerate"

```

### <a name="creating-a-new-security-entry-for-a-resource"></a><span data-ttu-id="6826a-177">Criando uma nova entrada de segurança para um recurso</span><span class="sxs-lookup"><span data-stu-id="6826a-177">Creating a new security entry for a resource</span></span>

<span data-ttu-id="6826a-178">Este comando cria uma entrada de segurança no diretório Security do Resource_5967683 (um recurso específico).</span><span class="sxs-lookup"><span data-stu-id="6826a-178">This command creates a security entry in the Security directory of Resource_5967683 (a specific resource).</span></span> <span data-ttu-id="6826a-179">Esse comando pressupõe que a entrada de recurso tenha sido criada usando um comando separado.</span><span class="sxs-lookup"><span data-stu-id="6826a-179">This command assumes that the resource entry has been created using a separate command.</span></span>

```powershell
$path = "WSMan:\localhost\Plugin\TestPlugin\Resources\Resource_5967683"
New-Item -Path $path\Security `
         -Sddl "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GWGX;;;WD)"
```

### <a name="creating-a-new-client-certificate"></a><span data-ttu-id="6826a-180">Criando um novo certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="6826a-180">Creating a new Client Certificate</span></span>

<span data-ttu-id="6826a-181">Esse comando cria a entrada **ClientCertificate** que pode ser usada pelo cliente de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="6826a-181">This command creates **ClientCertificate** entry that can be used by the WS-Management client.</span></span> <span data-ttu-id="6826a-182">O novo **ClientCertificate** aparecerá no diretório **ClientCertificate** como "ClientCertificate_1234567890".</span><span class="sxs-lookup"><span data-stu-id="6826a-182">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="6826a-183">Todos os parâmetros são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="6826a-183">All of the parameters are mandatory.</span></span> <span data-ttu-id="6826a-184">O **emissor** precisa ser impressão digital do certificado dos emissores.</span><span class="sxs-lookup"><span data-stu-id="6826a-184">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* `
         -Credential $cred;
```

### <a name="creating-a-new-initialization-parameter"></a><span data-ttu-id="6826a-185">Criando um novo parâmetro de inicialização</span><span class="sxs-lookup"><span data-stu-id="6826a-185">Creating a new Initialization Parameter</span></span>

<span data-ttu-id="6826a-186">Este comando cria um parâmetro de inicialização chamado "testparametername" no diretório "InitializationParameters".</span><span class="sxs-lookup"><span data-stu-id="6826a-186">This command creates an Initialization parameter named "testparametername" in the "InitializationParameters" directory.</span></span> <span data-ttu-id="6826a-187">Esse comando pressupõe que "TestPlugin" foi criado usando um comando separado.</span><span class="sxs-lookup"><span data-stu-id="6826a-187">This command assumes that the "TestPlugin" has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\InitializationParameters `
         -ParamName testparametername `
         -ParamValue testparametervalue
```

## <a name="dynamic-parameters"></a><span data-ttu-id="6826a-188">Parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="6826a-188">Dynamic parameters</span></span>

<span data-ttu-id="6826a-189">Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.</span><span class="sxs-lookup"><span data-stu-id="6826a-189">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="address-string"></a><span data-ttu-id="6826a-190">Address \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-190">Address \<String\></span></span>

<span data-ttu-id="6826a-191">Especifica o endereço para o qual este ouvinte foi criado.</span><span class="sxs-lookup"><span data-stu-id="6826a-191">Specifies the address for which this listener was created.</span></span> <span data-ttu-id="6826a-192">O valor pode ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="6826a-192">The value can be one of the following:</span></span>

- <span data-ttu-id="6826a-193">A cadeia de caracteres literal "\*".</span><span class="sxs-lookup"><span data-stu-id="6826a-193">The literal string "\*".</span></span> <span data-ttu-id="6826a-194">(O caractere curinga ( `*` ) faz com que o comando vincule todos os endereços IP em todos os adaptadores de rede.)</span><span class="sxs-lookup"><span data-stu-id="6826a-194">(The wildcard character (`*`) makes the command bind all the IP addresses on all the network adapters.)</span></span>
- <span data-ttu-id="6826a-195">A cadeia de caracteres literal "IP:" seguida por um endereço IP válido em um formato decimal com ponto de IPv4 ou no formato hexadecimal clonado de IPv6.</span><span class="sxs-lookup"><span data-stu-id="6826a-195">The literal string "IP:" followed by a valid IP address in either IPv4 dotted-decimal format or in IPv6 cloned-hexadecimal format.</span></span>
- <span data-ttu-id="6826a-196">A cadeia de caracteres literal "MAC:" seguida pelo endereço MAC de um adaptador.</span><span class="sxs-lookup"><span data-stu-id="6826a-196">The literal string "MAC:" followed by the MAC address of an adapter.</span></span>
  <span data-ttu-id="6826a-197">Por exemplo: MAC: 32-a3-58 -90-ser-CC.</span><span class="sxs-lookup"><span data-stu-id="6826a-197">For example: MAC:32-a3-58-90-be-cc.</span></span>

> [!NOTE]
> <span data-ttu-id="6826a-198">O valor Address é definido durante a criação de um Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="6826a-198">The Address value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-199">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-199">Cmdlets supported</span></span>

- [<span data-ttu-id="6826a-200">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-200">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="capability-enumeration"></a><span data-ttu-id="6826a-201">Capability \<Enumeration\></span><span class="sxs-lookup"><span data-stu-id="6826a-201">Capability \<Enumeration\></span></span>

<span data-ttu-id="6826a-202">Ao trabalhar com *plug-ins,* esse parâmetro especifica uma operação com suporte neste Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="6826a-202">When working with *Plug-ins* this parameter specifies an operation that is supported on this Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="6826a-203">Você precisa criar uma entrada para cada tipo de operação ao qual o URI dá suporte.</span><span class="sxs-lookup"><span data-stu-id="6826a-203">You have to create one entry for each type of operation that the URI supports.</span></span> <span data-ttu-id="6826a-204">Você pode especificar qualquer atributo válido para uma determinada operação, se a operação oferecer suporte a ela.</span><span class="sxs-lookup"><span data-stu-id="6826a-204">You can specify any valid attributes for a given operation, if the operation supports it.</span></span>

<span data-ttu-id="6826a-205">Esses atributos incluem **SupportsFiltering** e **SupportsFragment** .</span><span class="sxs-lookup"><span data-stu-id="6826a-205">These attributes include **SupportsFiltering** and **SupportsFragment** .</span></span>

- <span data-ttu-id="6826a-206">**Create** : há suporte para operações Create no URI.</span><span class="sxs-lookup"><span data-stu-id="6826a-206">**Create** : Create operations are supported on the URI.</span></span>
  - <span data-ttu-id="6826a-207">O atributo **SupportFragment**  será usado se a operação de criação der suporte ao conceito.</span><span class="sxs-lookup"><span data-stu-id="6826a-207">The **SupportFragment**  attribute is used if the Create operation supports the concept.</span></span>
  - <span data-ttu-id="6826a-208">O atributo **SUPPORTFILTERING** não é válido para operações Create e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="6826a-208">The **SupportFiltering** attribute is NOT valid for Create operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="6826a-209">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="6826a-209">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="6826a-210">**Delete** : há suporte para operações Delete no URI.</span><span class="sxs-lookup"><span data-stu-id="6826a-210">**Delete** : Delete operations are supported on the URI.</span></span>
  - <span data-ttu-id="6826a-211">O atributo **SupportFragment** será usado se a operação de exclusão der suporte ao conceito.</span><span class="sxs-lookup"><span data-stu-id="6826a-211">The **SupportFragment** attribute is used if the Delete operation supports the concept.</span></span>
  - <span data-ttu-id="6826a-212">O atributo **SUPPORTFILTERING** não é válido para operações Delete e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="6826a-212">The **SupportFiltering** attribute is NOT valid for Delete operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="6826a-213">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="6826a-213">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="6826a-214">**Enumerar** : as operações de enumeração têm suporte no URI.</span><span class="sxs-lookup"><span data-stu-id="6826a-214">**Enumerate** : Enumerate operations are supported on the URI.</span></span>
  - <span data-ttu-id="6826a-215">O atributo **SUPPORTFRAGMENT** não tem suporte para operações de enumeração e deve ser definido como false.</span><span class="sxs-lookup"><span data-stu-id="6826a-215">The **SupportFragment** attribute is NOT supported for Enumerate operations and should be set to False.</span></span>
  - <span data-ttu-id="6826a-216">O atributo **SupportFiltering** é válido e, se o plug-in der suporte à filtragem, esse atributo deverá ser definido como "true".</span><span class="sxs-lookup"><span data-stu-id="6826a-216">The **SupportFiltering** attribute is valid, and if the plug-in supports filtering, this attribute should be set to "True".</span></span>
  > [!NOTE]
  > <span data-ttu-id="6826a-217">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="6826a-217">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="6826a-218">**Get** : há suporte para operações Get no URI.</span><span class="sxs-lookup"><span data-stu-id="6826a-218">**Get** : Get operations are supported on the URI.</span></span>
  - <span data-ttu-id="6826a-219">O atributo **SupportFragment** será usado se a operação get der suporte ao conceito.</span><span class="sxs-lookup"><span data-stu-id="6826a-219">The **SupportFragment** attribute is used if the Get operation supports the concept.</span></span>
  - <span data-ttu-id="6826a-220">O atributo **SUPPORTFILTERING** não é válido para operações Get e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="6826a-220">The **SupportFiltering** attribute is NOT valid for Get operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="6826a-221">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="6826a-221">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="6826a-222">As operações **Invoke** : Invoke têm suporte no URI.</span><span class="sxs-lookup"><span data-stu-id="6826a-222">**Invoke** : Invoke operations are supported on the URI.</span></span>
  - <span data-ttu-id="6826a-223">O atributo **SupportFragment** não tem suporte para operações Invoke e deve ser definido como false.</span><span class="sxs-lookup"><span data-stu-id="6826a-223">The **SupportFragment** attribute is not supported for Invoke operations and should be set to False.</span></span>
  - <span data-ttu-id="6826a-224">O atributo **SupportFiltering** não é válido e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="6826a-224">The **SupportFiltering** attribute is not valid and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="6826a-225">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="6826a-225">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="6826a-226">**Put** : as operações Put têm suporte no URI.</span><span class="sxs-lookup"><span data-stu-id="6826a-226">**Put** : Put operations are supported on the URI.</span></span>
  - <span data-ttu-id="6826a-227">O atributo **SupportFragment** será usado se a operação Put der suporte ao conceito.</span><span class="sxs-lookup"><span data-stu-id="6826a-227">The **SupportFragment** attribute is used if the Put operation supports the concept.</span></span>
  - <span data-ttu-id="6826a-228">O atributo **SupportFiltering** não é válido para operações Put e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="6826a-228">The **SupportFiltering** attribute is not valid for Put operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="6826a-229">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="6826a-229">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="6826a-230">**Assinar** : há suporte para operações de assinatura no URI.</span><span class="sxs-lookup"><span data-stu-id="6826a-230">**Subscribe** : Subscribe operations are supported on the URI.</span></span>
  - <span data-ttu-id="6826a-231">O atributo **SupportFragment** não tem suporte para operações de assinatura e deve ser definido como false.</span><span class="sxs-lookup"><span data-stu-id="6826a-231">The **SupportFragment** attribute is not supported for Subscribe operations and should be set to False.</span></span>
  - <span data-ttu-id="6826a-232">O atributo **SupportFiltering** não é válido para operações de assinatura e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="6826a-232">The **SupportFiltering** attribute is not valid for Subscribe operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="6826a-233">Essa operação não é válida para um URI se também há suporte para operações de Shell.</span><span class="sxs-lookup"><span data-stu-id="6826a-233">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="6826a-234">**Shell** : há suporte para operações de Shell no URI.</span><span class="sxs-lookup"><span data-stu-id="6826a-234">**Shell** : Shell operations are supported on the URI.</span></span>
  - <span data-ttu-id="6826a-235">O atributo **SupportFragment** não tem suporte para operações de shell e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="6826a-235">The **SupportFragment** attribute is not supported for Shell operations and should be set to "False".</span></span>
  - <span data-ttu-id="6826a-236">O atributo **SupportFiltering** não é válido para operações de shell e deve ser definido como "false".</span><span class="sxs-lookup"><span data-stu-id="6826a-236">The **SupportFiltering** attribute is not valid for Shell operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="6826a-237">Essa operação não será válida para um URI se qualquer outra operação também tiver suporte.</span><span class="sxs-lookup"><span data-stu-id="6826a-237">This operation is not valid for a URI if ANY other operation is also supported.</span></span>
  > [!NOTE]
  > <span data-ttu-id="6826a-238">Se uma operação Shell estiver configurada para uma operação URI, Get, Put, Create, Delete, Invoke e Enumerate será processada internamente no serviço WS-Management (WinRM) para gerenciar os shells.</span><span class="sxs-lookup"><span data-stu-id="6826a-238">If a Shell operation is configured for a URI, Get, Put, Create, Delete, Invoke, and Enumerate operations are processed internally within the WS-Management (WinRM) service to manage shells.</span></span> <span data-ttu-id="6826a-239">Como resultado, o plug-in não pode manipular as operações.</span><span class="sxs-lookup"><span data-stu-id="6826a-239">As a result, the plug-in cannot handle the operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-240">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-240">Cmdlets supported</span></span>

- [<span data-ttu-id="6826a-241">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-241">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="certificatethumbprint-string"></a><span data-ttu-id="6826a-242">CertificateThumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-242">CertificateThumbprint \<String\></span></span>

<span data-ttu-id="6826a-243">Especifica a impressão digital do certificado de serviço.</span><span class="sxs-lookup"><span data-stu-id="6826a-243">Specifies the thumbprint of the service certificate.</span></span>

<span data-ttu-id="6826a-244">Esse valor representa a cadeia de caracteres de valores de dois dígitos hexadecimais no campo Impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="6826a-244">This value represents the string of two-digit hexadecimal values in the Thumbprint field of the certificate.</span></span> <span data-ttu-id="6826a-245">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="6826a-245">It specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="6826a-246">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="6826a-246">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="6826a-247">Eles podem ser mapeados somente para contas de usuário locais; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="6826a-247">They can be mapped only to local user accounts, and they do not work with domain accounts.</span></span> <span data-ttu-id="6826a-248">Para obter uma impressão digital do certificado, use os `Get-Item` `Get-ChildItem` cmdlets ou na `Cert:` unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6826a-248">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell `Cert:` drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-249">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-249">Cmdlets supported</span></span>

- [<span data-ttu-id="6826a-250">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-250">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="enabled-boolean"></a><span data-ttu-id="6826a-251">Enabled \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="6826a-251">Enabled \<Boolean\></span></span>

<span data-ttu-id="6826a-252">Especifica se o ouvinte está habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="6826a-252">Specifies whether the listener is enabled or disabled.</span></span> <span data-ttu-id="6826a-253">O padrão é True.</span><span class="sxs-lookup"><span data-stu-id="6826a-253">The default is True.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-254">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-254">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-255">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-255">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="filename-plugin-string"></a><span data-ttu-id="6826a-256">FileName (Plugin) \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-256">FileName (Plugin) \<String\></span></span>

<span data-ttu-id="6826a-257">Especifica o nome do arquivo do plug-in de operações.</span><span class="sxs-lookup"><span data-stu-id="6826a-257">Specifies the file name of the operations plug-in.</span></span> <span data-ttu-id="6826a-258">Todas as variáveis de ambiente colocadas nessa entrada serão expandidas no contexto dos usuários quando uma solicitação for recebida.</span><span class="sxs-lookup"><span data-stu-id="6826a-258">Any environment variables that are put in this entry will be expanded in the users' context when a request is received.</span></span> <span data-ttu-id="6826a-259">Como cada usuário pode ter uma versão diferente da mesma variável de ambiente, cada usuário poderia ter um plug-in diferente.</span><span class="sxs-lookup"><span data-stu-id="6826a-259">Because each user could have a different version of the same environment variable, each user could have a different plug-in.</span></span> <span data-ttu-id="6826a-260">Essa entrada não pode ficar em branco e deve apontar para um plug-in válido.</span><span class="sxs-lookup"><span data-stu-id="6826a-260">This entry cannot be blank and must point to a valid plug-in.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-261">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-261">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-262">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-262">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="hostname-string"></a><span data-ttu-id="6826a-263">HostName \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-263">HostName \<String\></span></span>

<span data-ttu-id="6826a-264">Especifica o nome de host do computador no qual o serviço WS-Management (WinRM) está em execução.</span><span class="sxs-lookup"><span data-stu-id="6826a-264">Specifies the host name of the computer on which the WS-Management (WinRM) service is running.</span></span>

<span data-ttu-id="6826a-265">O valor deve ser um nome de domínio totalmente qualificado, uma cadeia de caracteres literal IPv4 ou IPv6 ou um caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="6826a-265">The value must be a fully qualified domain name, an IPv4 or IPv6 literal string, or a wildcard character.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-266">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-266">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-267">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-267">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="issuer-string"></a><span data-ttu-id="6826a-268">Issuer \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-268">Issuer \<String\></span></span>

<span data-ttu-id="6826a-269">Especifica o nome da autoridade de certificação que emitiu o certificado.</span><span class="sxs-lookup"><span data-stu-id="6826a-269">Specifies the name of the certification authority that issued the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-270">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-270">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-271">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-271">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="plugin--ws-management-plug-ins-are-native-dynamic-link-libraries-dlls"></a><span data-ttu-id="6826a-272">\<\>Plug-ins de WS-Management do plug-in são DLLs (bibliotecas de vínculo dinâmico) nativas</span><span class="sxs-lookup"><span data-stu-id="6826a-272">Plugin \<\> WS-Management plug-ins are native dynamic link libraries (DLLs)</span></span>

<span data-ttu-id="6826a-273">que se conectam e estendem a funcionalidade do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="6826a-273">that plug in to and extend the functionality of WS-Management .</span></span> <span data-ttu-id="6826a-274">A API de plug-in do WSW-Management fornece funcionalidade que permite que um usuário escreva plug-ins implementando determinadas APIs para operações e URIs de recursos com suporte.</span><span class="sxs-lookup"><span data-stu-id="6826a-274">The WSW-Management Plug-in API provides functionality that enables a user to write plug-ins by implementing certain APIs for supported resource URIs and operations.</span></span> <span data-ttu-id="6826a-275">Depois que os plug-ins estiverem configurados para o serviço WS-Management (WinRM) ou para Serviços de Informações da Internet (IIS), os plug-ins são carregados no host WS-Management ou no host IIS, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6826a-275">After the plug-ins are configured for either the WS-Management (WinRM) service or for Internet Information Services (IIS), the plug-ins are loaded in the WS-Management host or in the IIS host, respectively.</span></span> <span data-ttu-id="6826a-276">As solicitações remotas são roteadas para esses pontos de entrada de plug-in para executar operações.</span><span class="sxs-lookup"><span data-stu-id="6826a-276">Remote requests are routed to these plug-in entry points to perform operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-277">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-277">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-278">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-278">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="port-unsigned-short-integer"></a><span data-ttu-id="6826a-279">Port \<Unsigned Short Integer\></span><span class="sxs-lookup"><span data-stu-id="6826a-279">Port \<Unsigned Short Integer\></span></span>

<span data-ttu-id="6826a-280">Especifica a porta TCP para a qual este ouvinte é criado.</span><span class="sxs-lookup"><span data-stu-id="6826a-280">Specifies the TCP port for which this listener is created.</span></span> <span data-ttu-id="6826a-281">Você pode especificar qualquer valor entre 1 e 65535.</span><span class="sxs-lookup"><span data-stu-id="6826a-281">You can specify any value from 1 through 65535.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-282">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-282">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-283">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-283">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="6826a-284">Resource \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-284">Resource \<String\></span></span>

<span data-ttu-id="6826a-285">Especifica um ponto de extremidade que representa um tipo distinto de valor ou operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="6826a-285">Specifies an endpoint that represents a distinct type of management operation or value.</span></span> <span data-ttu-id="6826a-286">Um serviço expõe um ou mais recursos, e alguns recursos podem ter mais de uma instância.</span><span class="sxs-lookup"><span data-stu-id="6826a-286">A service exposes one or more resources, and some resources can have more than one instance.</span></span> <span data-ttu-id="6826a-287">Um recurso de gerenciamento é semelhante a uma classe WMI ou a uma tabela de banco de dados e uma instância é semelhante a uma instância da classe ou a uma linha na tabela.</span><span class="sxs-lookup"><span data-stu-id="6826a-287">A management resource is similar to a WMI class or to a database table, and an instance is similar to an instance of the class or to a row in the table.</span></span> <span data-ttu-id="6826a-288">Por exemplo, a classe **Win32_LogicalDisk** representa um recurso.</span><span class="sxs-lookup"><span data-stu-id="6826a-288">For example, the **Win32_LogicalDisk** class represents a resource.</span></span> <span data-ttu-id="6826a-289">`Win32_LogicalDisk="C:\\"` é uma instância específica do recurso.</span><span class="sxs-lookup"><span data-stu-id="6826a-289">`Win32_LogicalDisk="C:\\"` is a specific instance of the resource.</span></span>

<span data-ttu-id="6826a-290">Um identificador de recurso uniforme (URI) contém um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="6826a-290">A Uniform Resource Identifier (URI) contains a prefix and a path to a resource.</span></span>
<span data-ttu-id="6826a-291">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6826a-291">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-292">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-292">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-293">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-293">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="6826a-294">Resource \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-294">Resource \<String\></span></span>

<span data-ttu-id="6826a-295">Especifica o Uniform Resource identificador (URI) que identifica um tipo de recurso, como um disco ou um processo, em um computador específico.</span><span class="sxs-lookup"><span data-stu-id="6826a-295">Specifies the Uniform Resource Identifier (URI) that identifies a specific type of resource, such as a disk or a process, on a computer.</span></span>

<span data-ttu-id="6826a-296">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="6826a-296">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="6826a-297">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6826a-297">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-298">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-298">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-299">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-299">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sdkversion-string"></a><span data-ttu-id="6826a-300">SDKVersion \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-300">SDKVersion \<String\></span></span>

<span data-ttu-id="6826a-301">Especifica a versão do SDK do plug-in do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="6826a-301">Specifies the version of the WS-Management plug-in SDK.</span></span> <span data-ttu-id="6826a-302">O único valor válido é</span><span class="sxs-lookup"><span data-stu-id="6826a-302">The only valid value is</span></span>
1.

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-303">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-303">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-304">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-304">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="subject-string"></a><span data-ttu-id="6826a-305">Subject \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-305">Subject \<String\></span></span>

<span data-ttu-id="6826a-306">Especifica a entidade que é identificada pelo certificado.</span><span class="sxs-lookup"><span data-stu-id="6826a-306">Specifies the entity that is identified by the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-307">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-307">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-308">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-308">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="transport-string"></a><span data-ttu-id="6826a-309">Transport \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-309">Transport \<String\></span></span>

<span data-ttu-id="6826a-310">Especifica o transporte a ser usado para enviar e receber respostas e solicitações do protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="6826a-310">Specifies the transport to use to send and receive WS-Management protocol requests and responses.</span></span> <span data-ttu-id="6826a-311">O valor deve ser HTTP ou HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6826a-311">The value must be either HTTP or HTTPS.</span></span>

<span data-ttu-id="6826a-312">Observação: o valor de transporte é definido durante a criação de um ouvinte.</span><span class="sxs-lookup"><span data-stu-id="6826a-312">Note: The Transport value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-313">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-313">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-314">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-314">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="uri-string"></a><span data-ttu-id="6826a-315">URI \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-315">URI \<String\></span></span>

<span data-ttu-id="6826a-316">Identifica o URI para o qual o acesso é autorizado com base no valor do parâmetro Sddl.</span><span class="sxs-lookup"><span data-stu-id="6826a-316">Identifies the URI for which access is authorized based on the value of the Sddl parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-317">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-317">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-318">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-318">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="urlprefix-string"></a><span data-ttu-id="6826a-319">URLPrefix \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-319">URLPrefix \<String\></span></span>

<span data-ttu-id="6826a-320">Um prefixo de URL no qual aceitar solicitações de HTTP ou HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6826a-320">A URL prefix on which to accept HTTP or HTTPS requests.</span></span> <span data-ttu-id="6826a-321">Esta é uma cadeia de caracteres que contém apenas os caracteres `[a-z]` , `[A-Z]` ,, `[9-0]` sublinhado ( `_` ) e barra invertida ( `/` ).</span><span class="sxs-lookup"><span data-stu-id="6826a-321">This is a string containing only the characters `[a-z]`, `[A-Z]`, `[9-0]`, underscore (`_`) and backslash (`/`).</span></span> <span data-ttu-id="6826a-322">A cadeia de caracteres não deve começar com ou terminar com uma barra invertida ( `/` ).</span><span class="sxs-lookup"><span data-stu-id="6826a-322">The string must not start with or end with a backslash (`/`).</span></span> <span data-ttu-id="6826a-323">Por exemplo, se o nome do computador for "SampleComputer", o cliente WS-Management especificaria `http://SampleMachine/URLPrefix` no endereço de destino.</span><span class="sxs-lookup"><span data-stu-id="6826a-323">For example, if the computer name is "SampleComputer", the WS-Management client would specify `http://SampleMachine/URLPrefix` in the destination address.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-324">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-324">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-325">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-325">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="value-string"></a><span data-ttu-id="6826a-326">Value \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-326">Value \<String\></span></span>

<span data-ttu-id="6826a-327">Especifica o valor de um parâmetro de inicialização, que é um valor de plug-in específico usado para especificar opções de configuração.</span><span class="sxs-lookup"><span data-stu-id="6826a-327">Specifies the value of an initialization parameter, which is a plug-in-specific value that is used to specify configuration options.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-328">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-328">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-329">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-329">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="xmlrenderingtype-string"></a><span data-ttu-id="6826a-330">XMLRenderingType \<String\></span><span class="sxs-lookup"><span data-stu-id="6826a-330">XMLRenderingType \<String\></span></span>

<span data-ttu-id="6826a-331">Especifica o formato em que o XML é passado aos plug-ins por meio do objeto **WSMAN_DATA** .</span><span class="sxs-lookup"><span data-stu-id="6826a-331">Specifies the format in which XML is passed to plug-ins through the **WSMAN_DATA** object.</span></span> <span data-ttu-id="6826a-332">Os seguintes valores são válidos:</span><span class="sxs-lookup"><span data-stu-id="6826a-332">The following are valid values:</span></span>

- <span data-ttu-id="6826a-333">Text: os dados XML de entrada estão contidos em uma estrutura de **WSMAN_DATA_TYPE_TEXT** , que representa o XML como um buffer de memória **PCWSTR** .</span><span class="sxs-lookup"><span data-stu-id="6826a-333">Text: Incoming XML data is contained in a **WSMAN_DATA_TYPE_TEXT** structure, which represents the XML as a **PCWSTR** memory buffer.</span></span>
- <span data-ttu-id="6826a-334">XMLReader: os dados XML de entrada estão contidos em uma estrutura de **WSMAN_DATA_TYPE_WS_XML_READER** , que representa o XML como um objeto **XmlReader** , que é definido no arquivo de cabeçalho "WebServices. h".</span><span class="sxs-lookup"><span data-stu-id="6826a-334">XMLReader: Incoming XML data is contained in a **WSMAN_DATA_TYPE_WS_XML_READER** structure, which represents the XML as an **XmlReader** object, which is defined in the "WebServices.h" header file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6826a-335">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="6826a-335">Cmdlets Supported</span></span>

- [<span data-ttu-id="6826a-336">New-Item</span><span class="sxs-lookup"><span data-stu-id="6826a-336">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="6826a-337">Usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="6826a-337">Using the pipeline</span></span>

<span data-ttu-id="6826a-338">Os cmdlets do provedor aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="6826a-338">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="6826a-339">Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.</span><span class="sxs-lookup"><span data-stu-id="6826a-339">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="6826a-340">Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="6826a-340">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="6826a-341">Obtendo ajuda</span><span class="sxs-lookup"><span data-stu-id="6826a-341">Getting help</span></span>

<span data-ttu-id="6826a-342">A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="6826a-342">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="6826a-343">Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) para especificar uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="6826a-343">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path wsman:
```

## <a name="see-also"></a><span data-ttu-id="6826a-344">Confira também</span><span class="sxs-lookup"><span data-stu-id="6826a-344">See also</span></span>

[<span data-ttu-id="6826a-345">about_Providers</span><span class="sxs-lookup"><span data-stu-id="6826a-345">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)

