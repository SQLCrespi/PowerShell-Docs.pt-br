---
description: Fornece uma visão geral do Web Services for Management (WS-Management) como plano de fundo para usar os cmdlets WS-Management no Windows PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WS Management_Cmdlets
ms.openlocfilehash: c9d89d0559bf844927976c78bde6fca58ffa8855
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390500"
---
# <a name="about-ws-management-cmdlets"></a><span data-ttu-id="dcac3-104">Sobre WS-Management cmdlets</span><span class="sxs-lookup"><span data-stu-id="dcac3-104">About WS-Management Cmdlets</span></span>

## <a name="short-description"></a><span data-ttu-id="dcac3-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="dcac3-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="dcac3-106">Fornece uma visão geral do Web Services for Management (WS-Management) como plano de fundo para usar os cmdlets WS-Management no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dcac3-106">Provides an overview of Web Services for Management (WS-Management) as background for using the WS-Management cmdlets in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="dcac3-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="dcac3-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="dcac3-108">Este tópico fornece uma visão geral do Web Services for Management (WS-Management) como plano de fundo para usar os cmdlets WS-Management no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dcac3-108">This topic provides an overview of Web Services for Management (WS-Management) as background for using the WS-Management cmdlets in Windows PowerShell.</span></span> <span data-ttu-id="dcac3-109">Este tópico também fornece links para mais informações sobre o WS-Management.</span><span class="sxs-lookup"><span data-stu-id="dcac3-109">This topic also provides links to more information about WS-Management.</span></span> <span data-ttu-id="dcac3-110">A implementação de WS-Management da Microsoft também é conhecida como Gerenciamento Remoto do Windows (WinRM).</span><span class="sxs-lookup"><span data-stu-id="dcac3-110">The Microsoft implementation of WS-Management is also known as Windows Remote Management (WinRM).</span></span>

## <a name="about-ws-management"></a><span data-ttu-id="dcac3-111">Sobre WS-Management</span><span class="sxs-lookup"><span data-stu-id="dcac3-111">About WS-Management</span></span>

<span data-ttu-id="dcac3-112">Gerenciamento Remoto do Windows é a implementação da Microsoft do protocolo de WS-Management, um protocolo padrão baseado em SOAP, compatível com o firewall, que permite que os sistemas operacionais e de hardware de diferentes fornecedores interoperem.</span><span class="sxs-lookup"><span data-stu-id="dcac3-112">Windows Remote Management is the Microsoft implementation of the WS-Management protocol, a standard SOAP-based, firewall-friendly protocol that allows hardware and operating systems from different vendors to interoperate.</span></span> <span data-ttu-id="dcac3-113">A especificação do protocolo WS-Management fornece uma maneira comum para que os sistemas acessem e troquem informações de gerenciamento em uma infra-estrutura de ti (tecnologia da informação).</span><span class="sxs-lookup"><span data-stu-id="dcac3-113">The WS-Management protocol specification provides a common way for systems to access and exchange management information across an information technology (IT) infrastructure.</span></span> <span data-ttu-id="dcac3-114">A WS-Management e a IPMI (interface de gerenciamento de plataforma inteligente), juntamente com o coletor de eventos, são componentes dos recursos de gerenciamento de hardware do Windows.</span><span class="sxs-lookup"><span data-stu-id="dcac3-114">WS-Management and Intelligent Platform Management Interface (IPMI), along with the Event Collector, are components of the Windows Hardware Management features.</span></span>

<span data-ttu-id="dcac3-115">O protocolo WS-Management é baseado nas especificações de serviço Web padrão a seguir: HTTPS, SOAP sobre HTTP (perfil WS-I), SOAP 1,2, WS-Addressing, WS-Transfer, WS-Enumeration e WS-Eventing.</span><span class="sxs-lookup"><span data-stu-id="dcac3-115">The WS-Management protocol is based on the following standard Web service specifications: HTTPS, SOAP over HTTP (WS-I profile), SOAP 1.2, WS-Addressing, WS-Transfer, WS-Enumeration, and WS-Eventing.</span></span>

## <a name="ws-management-and-wmi"></a><span data-ttu-id="dcac3-116">WS-Management e WMI</span><span class="sxs-lookup"><span data-stu-id="dcac3-116">WS-Management and WMI</span></span>

<span data-ttu-id="dcac3-117">WS-Management pode ser usado para recuperar dados expostos por Instrumentação de Gerenciamento do Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="dcac3-117">WS-Management can be used to retrieve data exposed by Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="dcac3-118">Você pode obter dados do WMI com scripts ou aplicativos que usam a API de script WS-Management ou por meio da ferramenta de linha de comando WinRM.</span><span class="sxs-lookup"><span data-stu-id="dcac3-118">You can obtain WMI data with scripts or applications that use the WS-Management Scripting API or through the WinRM command-line tool.</span></span> <span data-ttu-id="dcac3-119">O WS-Management oferece suporte à maioria das classes e operações WMI familiares, incluindo objetos incorporados.</span><span class="sxs-lookup"><span data-stu-id="dcac3-119">WS-Management supports most of the familiar WMI classes and operations, including embedded objects.</span></span> <span data-ttu-id="dcac3-120">WS-Management pode aproveitar o WMI para coletar dados sobre recursos ou para gerenciar recursos em computadores baseados no Windows.</span><span class="sxs-lookup"><span data-stu-id="dcac3-120">WS-Management can leverage WMI to collect data about resources or to manage resources on a Windows-based computers.</span></span> <span data-ttu-id="dcac3-121">Isso significa que você pode obter dados sobre objetos como discos, adaptadores de rede, serviços ou processos em sua empresa por meio do conjunto existente de classes WMI.</span><span class="sxs-lookup"><span data-stu-id="dcac3-121">That means that you can obtain data about objects such as disks, network adapters, services, or processes in your enterprise through the existing set of WMI classes.</span></span> <span data-ttu-id="dcac3-122">Você também pode acessar os dados de hardware que estão disponíveis no provedor padrão de IPMI do WMI.</span><span class="sxs-lookup"><span data-stu-id="dcac3-122">You can also access the hardware data that is available from the standard WMI IPMI provider.</span></span>

## <a name="ws-management-windows-powershell-provider-wsman"></a><span data-ttu-id="dcac3-123">WS-Management o provedor do Windows PowerShell (WSMan)</span><span class="sxs-lookup"><span data-stu-id="dcac3-123">WS-Management Windows PowerShell Provider (WSMan)</span></span>

<span data-ttu-id="dcac3-124">O provedor WSMan fornece uma exibição hierárquica das definições de configuração do WS-Management disponíveis.</span><span class="sxs-lookup"><span data-stu-id="dcac3-124">The WSMan provider provides a hierarchical view into the available WS-Management configuration settings.</span></span> <span data-ttu-id="dcac3-125">O provedor permite explorar e definir as várias opções de configuração de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="dcac3-125">The provider allows you to explore and set the various WS-Management configuration options.</span></span>

## <a name="ws-management-configuration"></a><span data-ttu-id="dcac3-126">Configuração de WS-Management</span><span class="sxs-lookup"><span data-stu-id="dcac3-126">WS-Management Configuration</span></span>

<span data-ttu-id="dcac3-127">Se WS-Management não estiver instalado e configurado, a comunicação remota do Windows PowerShell não estará disponível, os cmdlets WS-Management não serão executados, WS-Management scripts não são executados e o provedor WSMan não pode executar operações de dados.</span><span class="sxs-lookup"><span data-stu-id="dcac3-127">If WS-Management is not installed and configured, Windows PowerShell remoting is not available, the WS-Management cmdlets do not run, WS-Management scripts do not run, and the WSMan provider cannot perform data operations.</span></span> <span data-ttu-id="dcac3-128">A ferramenta de linha de comando WS-Management, o WinRM e o encaminhamento de eventos também dependem da configuração de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="dcac3-128">The WS-Management command-line tool, WinRM, and event forwarding also depend on the WS-Management configuration.</span></span>

## <a name="ws-management-cmdlets"></a><span data-ttu-id="dcac3-129">WS-Management cmdlets</span><span class="sxs-lookup"><span data-stu-id="dcac3-129">WS-Management Cmdlets</span></span>

<span data-ttu-id="dcac3-130">WS-Management funcionalidade é implementada no Windows PowerShell por meio de um módulo que contém um conjunto de cmdlets e o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="dcac3-130">WS-Management functionality is implemented in Windows PowerShell through a module that contains a set of cmdlets and the WSMan provider.</span></span> <span data-ttu-id="dcac3-131">Você pode usar esses cmdlets para concluir as tarefas de ponta a ponta necessárias para gerenciar WS-Management configurações em computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="dcac3-131">You can use these cmdlets to complete the end-to-end tasks necessary to manage WS-Management settings on local and remote computers.</span></span>

<span data-ttu-id="dcac3-132">Os cmdlets WS-Management a seguir estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="dcac3-132">The following WS-Management cmdlets are available.</span></span>

## <a name="connection-cmdlets"></a><span data-ttu-id="dcac3-133">Cmdlets de conexão</span><span class="sxs-lookup"><span data-stu-id="dcac3-133">Connection Cmdlets</span></span>

- <span data-ttu-id="dcac3-134">Connect-WSMan: conecta o computador local ao serviço de WS-Management (WinRM) em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="dcac3-134">Connect-WSMan: Connects the local computer to the WS-Management (WinRM) service on a remote computer.</span></span>

- <span data-ttu-id="dcac3-135">Disconnect-WSMan: desconecta o computador local do serviço WS-Management (WinRM) em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="dcac3-135">Disconnect-WSMan: Disconnects the local computer from the WS-Management (WinRM) service on a remote computer.</span></span>

## <a name="management-data-cmdlets"></a><span data-ttu-id="dcac3-136">Management-Data cmdlets</span><span class="sxs-lookup"><span data-stu-id="dcac3-136">Management-Data Cmdlets</span></span>

- <span data-ttu-id="dcac3-137">Get-WSManInstance: exibe informações de gerenciamento para uma instância de recurso especificada por um URI de recurso.</span><span class="sxs-lookup"><span data-stu-id="dcac3-137">Get-WSManInstance: Displays management information for a resource instance that is specified by a resource URI.</span></span>

- <span data-ttu-id="dcac3-138">Invoke-WSManaction: invoca uma ação no objeto de destino que é especificado pelo URI de recurso e pelos seletores.</span><span class="sxs-lookup"><span data-stu-id="dcac3-138">Invoke-WSManAction: Invokes an action on the target object that is specified by the resource URI and by the selectors.</span></span>

- <span data-ttu-id="dcac3-139">New-WSManInstance: cria uma nova instância de recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="dcac3-139">New-WSManInstance: Creates a new management resource instance.</span></span>

- <span data-ttu-id="dcac3-140">Remove-WSManInstance: exclui uma instância de recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="dcac3-140">Remove-WSManInstance: Deletes a management resource instance.</span></span>

- <span data-ttu-id="dcac3-141">Set-WSManInstance: modifica as informações de gerenciamento relacionadas a um recurso.</span><span class="sxs-lookup"><span data-stu-id="dcac3-141">Set-WSManInstance: Modifies the management information that is related to a resource.</span></span>

## <a name="setup-and-configuration-cmdlets"></a><span data-ttu-id="dcac3-142">Cmdlets de instalação e configuração</span><span class="sxs-lookup"><span data-stu-id="dcac3-142">Setup and Configuration Cmdlets</span></span>

- <span data-ttu-id="dcac3-143">Set-WSManQuickConfig: configura o computador local para gerenciamento remoto.</span><span class="sxs-lookup"><span data-stu-id="dcac3-143">Set-WSManQuickConfig: Configures the local computer for remote management.</span></span>
  <span data-ttu-id="dcac3-144">Você pode usar o cmdlet Set-WSManQuickConfig para configurar WS-Management para permitir conexões remotas com o serviço do WS-Management (WinRM).</span><span class="sxs-lookup"><span data-stu-id="dcac3-144">You can use the Set-WSManQuickConfig cmdlet to configure WS-Management to allow remote connections to the WS-Management (WinRM) service.</span></span> <span data-ttu-id="dcac3-145">O cmdlet Set-WSManQuickConfig executa as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="dcac3-145">The Set-WSManQuickConfig cmdlet performs the following operations:</span></span>
  - <span data-ttu-id="dcac3-146">Ele determina se o serviço do WS-Management (WinRM) está em execução.</span><span class="sxs-lookup"><span data-stu-id="dcac3-146">It determines whether the WS-Management (WinRM) service is running.</span></span> <span data-ttu-id="dcac3-147">Se o serviço WinRM não estiver em execução, o cmdlet Set-WSManQuickConfig iniciará o serviço.</span><span class="sxs-lookup"><span data-stu-id="dcac3-147">If the WinRM service is not running, the Set-WSManQuickConfig cmdlet starts the service.</span></span>
  - <span data-ttu-id="dcac3-148">Ele define o tipo de inicialização do serviço WS-Management (WinRM) como automático.</span><span class="sxs-lookup"><span data-stu-id="dcac3-148">It sets the WS-Management (WinRM) service startup type to automatic.</span></span>
  - <span data-ttu-id="dcac3-149">Ele cria um ouvinte que aceita solicitações de qualquer endereço IP.</span><span class="sxs-lookup"><span data-stu-id="dcac3-149">It creates a listener that accepts requests from any IP address.</span></span> <span data-ttu-id="dcac3-150">O protocolo de transporte padrão é HTTP.</span><span class="sxs-lookup"><span data-stu-id="dcac3-150">The default transport protocol is HTTP.</span></span>
  - <span data-ttu-id="dcac3-151">Ele habilita uma exceção de firewall para tráfego de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="dcac3-151">It enables a firewall exception for WS-Management traffic.</span></span>

  <span data-ttu-id="dcac3-152">Observação: para executar esse cmdlet no Windows Vista, no Windows Server 2008 e em versões posteriores do Windows, você deve iniciar o Windows PowerShell com a opção "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="dcac3-152">Note: To run this cmdlet in Windows Vista, Windows Server 2008, and later versions of Windows, you must start Windows PowerShell with the "Run as administrator" option.</span></span>

- <span data-ttu-id="dcac3-153">Teste-WSMan: verifica se WS-Management está instalado e configurado.</span><span class="sxs-lookup"><span data-stu-id="dcac3-153">Test-WSMan: Verifies that WS-Management is installed and configured.</span></span> <span data-ttu-id="dcac3-154">O cmdlet Test-WSMan testa se o serviço de WS-Management (WinRM) está em execução e configurado em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="dcac3-154">The Test-WSMan cmdlet tests whether the WS-Management (WinRM) service is running and configured on a local or remote computer.</span></span>

- <span data-ttu-id="dcac3-155">Disable-WSManCredSSP: desabilita a autenticação CredSSP em um computador cliente.</span><span class="sxs-lookup"><span data-stu-id="dcac3-155">Disable-WSManCredSSP: Disables CredSSP authentication on a client computer.</span></span>

- <span data-ttu-id="dcac3-156">Enable-WSManCredSSP: habilita a autenticação CredSSP em um computador cliente.</span><span class="sxs-lookup"><span data-stu-id="dcac3-156">Enable-WSManCredSSP: Enables CredSSP authentication on a client computer.</span></span>

- <span data-ttu-id="dcac3-157">Get-WSManCredSSP: Obtém a configuração relacionada a CredSSP para um computador cliente.</span><span class="sxs-lookup"><span data-stu-id="dcac3-157">Get-WSManCredSSP: Gets the CredSSP-related configuration for a client computer.</span></span>

## <a name="ws-management-specific-cmdlets"></a><span data-ttu-id="dcac3-158">Cmdlets específicos do WS-Management</span><span class="sxs-lookup"><span data-stu-id="dcac3-158">WS-Management-Specific Cmdlets</span></span>

- <span data-ttu-id="dcac3-159">New-WSManSessionOption: cria um objeto WSManSessionOption para usar como entrada para um ou mais parâmetros de um cmdlet WS-Management.</span><span class="sxs-lookup"><span data-stu-id="dcac3-159">New-WSManSessionOption: Creates a WSManSessionOption object to use as input to one or more parameters of a WS-Management cmdlet.</span></span>

## <a name="additional-ws-management-information"></a><span data-ttu-id="dcac3-160">Informações adicionais de WS-Management</span><span class="sxs-lookup"><span data-stu-id="dcac3-160">Additional WS-Management Information</span></span>

<span data-ttu-id="dcac3-161">Para obter mais informações sobre o WS-Management, consulte os tópicos a seguir na documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="dcac3-161">For more information about WS-Management, see the following topics in the Windows documentation.</span></span>

[<span data-ttu-id="dcac3-162">Gerenciamento Remoto do Windows</span><span class="sxs-lookup"><span data-stu-id="dcac3-162">Windows Remote Management</span></span>](/windows/win32/winrm/portal)

[<span data-ttu-id="dcac3-163">Sobre Gerenciamento Remoto do Windows</span><span class="sxs-lookup"><span data-stu-id="dcac3-163">About Windows Remote Management</span></span>](/windows/win32/winrm/about-windows-remote-management)

[<span data-ttu-id="dcac3-164">Instalação e configuração para Gerenciamento Remoto do Windows</span><span class="sxs-lookup"><span data-stu-id="dcac3-164">Installation and Configuration for Windows Remote Management</span></span>](/windows/win32/winrm/installation-and-configuration-for-windows-remote-management)

[<span data-ttu-id="dcac3-165">Arquitetura de Gerenciamento Remoto do Windows</span><span class="sxs-lookup"><span data-stu-id="dcac3-165">Windows Remote Management Architecture</span></span>](/windows/win32/winrm/windows-remote-management-architecture)

[<span data-ttu-id="dcac3-166">Protocolo WS-Management</span><span class="sxs-lookup"><span data-stu-id="dcac3-166">WS-Management Protocol</span></span>](/windows/win32/winrm/ws-management-protocol)

[<span data-ttu-id="dcac3-167">Gerenciamento Remoto do Windows e WMI</span><span class="sxs-lookup"><span data-stu-id="dcac3-167">Windows Remote Management and WMI</span></span>](/windows/win32/winrm/windows-remote-management-and-wmi)

[<span data-ttu-id="dcac3-168">URIs do Recurso</span><span class="sxs-lookup"><span data-stu-id="dcac3-168">Resource URIs</span></span>](/windows/win32/winrm/resource-uris)

[<span data-ttu-id="dcac3-169">Gerenciamento de hardware remoto</span><span class="sxs-lookup"><span data-stu-id="dcac3-169">Remote Hardware Management</span></span>](/windows/win32/winrm/remote-hardware-management)

[<span data-ttu-id="dcac3-170">Eventos</span><span class="sxs-lookup"><span data-stu-id="dcac3-170">Events</span></span>](/windows/win32/winrm/events)

## <a name="see-also"></a><span data-ttu-id="dcac3-171">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="dcac3-171">SEE ALSO</span></span>

[<span data-ttu-id="dcac3-172">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="dcac3-172">Connect-WSMan</span></span>](xref:Microsoft.WSMan.Management.Connect-WSMan)

[<span data-ttu-id="dcac3-173">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="dcac3-173">Disable-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Disable-WSManCredSSP)

[<span data-ttu-id="dcac3-174">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="dcac3-174">Disconnect-WSMan</span></span>](xref:Microsoft.WSMan.Management.Disconnect-WSMan)

[<span data-ttu-id="dcac3-175">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="dcac3-175">Enable-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Enable-WSManCredSSP)

[<span data-ttu-id="dcac3-176">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="dcac3-176">Get-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Get-WSManCredSSP)

[<span data-ttu-id="dcac3-177">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="dcac3-177">Get-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Get-WSManInstance)

[<span data-ttu-id="dcac3-178">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="dcac3-178">Invoke-WSManAction</span></span>](xref:Microsoft.WSMan.Management.Invoke-WSManAction)

[<span data-ttu-id="dcac3-179">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="dcac3-179">New-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.New-WSManInstance)

[<span data-ttu-id="dcac3-180">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="dcac3-180">Remove-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Remove-WSManInstance)

[<span data-ttu-id="dcac3-181">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="dcac3-181">Set-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Set-WSManInstance)

[<span data-ttu-id="dcac3-182">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="dcac3-182">Set-WSManQuickConfig</span></span>](xref:Microsoft.WSMan.Management.Set-WSManQuickConfig)

[<span data-ttu-id="dcac3-183">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="dcac3-183">Test-WSMan</span></span>](xref:Microsoft.WSMan.Management.Test-WSMan)
