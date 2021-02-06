---
description: Fornece uma visão geral do Web Services for Management (WS-Management) como plano de fundo para usar os cmdlets WS-Management no Windows PowerShell.
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WS Management_Cmdlets
ms.openlocfilehash: faf0f0b08d604f7568ac316557788eea21feea8d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597637"
---
# <a name="about-ws-management-cmdlets"></a><span data-ttu-id="88c8b-103">Sobre WS-Management cmdlets</span><span class="sxs-lookup"><span data-stu-id="88c8b-103">About WS-Management Cmdlets</span></span>

## <a name="short-description"></a><span data-ttu-id="88c8b-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="88c8b-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="88c8b-105">Fornece uma visão geral do Web Services for Management (WS-Management) como plano de fundo para usar os cmdlets WS-Management no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88c8b-105">Provides an overview of Web Services for Management (WS-Management) as background for using the WS-Management cmdlets in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="88c8b-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="88c8b-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="88c8b-107">Este tópico fornece uma visão geral do Web Services for Management (WS-Management) como plano de fundo para usar os cmdlets WS-Management no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88c8b-107">This topic provides an overview of Web Services for Management (WS-Management) as background for using the WS-Management cmdlets in Windows PowerShell.</span></span> <span data-ttu-id="88c8b-108">Este tópico também fornece links para mais informações sobre o WS-Management.</span><span class="sxs-lookup"><span data-stu-id="88c8b-108">This topic also provides links to more information about WS-Management.</span></span> <span data-ttu-id="88c8b-109">A implementação de WS-Management da Microsoft também é conhecida como Gerenciamento Remoto do Windows (WinRM).</span><span class="sxs-lookup"><span data-stu-id="88c8b-109">The Microsoft implementation of WS-Management is also known as Windows Remote Management (WinRM).</span></span>

## <a name="about-ws-management"></a><span data-ttu-id="88c8b-110">Sobre WS-Management</span><span class="sxs-lookup"><span data-stu-id="88c8b-110">About WS-Management</span></span>

<span data-ttu-id="88c8b-111">Gerenciamento Remoto do Windows é a implementação da Microsoft do protocolo de WS-Management, um protocolo padrão baseado em SOAP, compatível com o firewall, que permite que os sistemas operacionais e de hardware de diferentes fornecedores interoperem.</span><span class="sxs-lookup"><span data-stu-id="88c8b-111">Windows Remote Management is the Microsoft implementation of the WS-Management protocol, a standard SOAP-based, firewall-friendly protocol that allows hardware and operating systems from different vendors to interoperate.</span></span> <span data-ttu-id="88c8b-112">A especificação do protocolo WS-Management fornece uma maneira comum para que os sistemas acessem e troquem informações de gerenciamento em uma infra-estrutura de ti (tecnologia da informação).</span><span class="sxs-lookup"><span data-stu-id="88c8b-112">The WS-Management protocol specification provides a common way for systems to access and exchange management information across an information technology (IT) infrastructure.</span></span> <span data-ttu-id="88c8b-113">A WS-Management e a IPMI (interface de gerenciamento de plataforma inteligente), juntamente com o coletor de eventos, são componentes dos recursos de gerenciamento de hardware do Windows.</span><span class="sxs-lookup"><span data-stu-id="88c8b-113">WS-Management and Intelligent Platform Management Interface (IPMI), along with the Event Collector, are components of the Windows Hardware Management features.</span></span>

<span data-ttu-id="88c8b-114">O protocolo WS-Management é baseado nas especificações de serviço Web padrão a seguir: HTTPS, SOAP sobre HTTP (perfil WS-I), SOAP 1,2, WS-Addressing, WS-Transfer, WS-Enumeration e WS-Eventing.</span><span class="sxs-lookup"><span data-stu-id="88c8b-114">The WS-Management protocol is based on the following standard Web service specifications: HTTPS, SOAP over HTTP (WS-I profile), SOAP 1.2, WS-Addressing, WS-Transfer, WS-Enumeration, and WS-Eventing.</span></span>

## <a name="ws-management-and-wmi"></a><span data-ttu-id="88c8b-115">WS-Management e WMI</span><span class="sxs-lookup"><span data-stu-id="88c8b-115">WS-Management and WMI</span></span>

<span data-ttu-id="88c8b-116">WS-Management pode ser usado para recuperar dados expostos por Instrumentação de Gerenciamento do Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="88c8b-116">WS-Management can be used to retrieve data exposed by Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="88c8b-117">Você pode obter dados do WMI com scripts ou aplicativos que usam a API de script WS-Management ou por meio da ferramenta de linha de comando WinRM.</span><span class="sxs-lookup"><span data-stu-id="88c8b-117">You can obtain WMI data with scripts or applications that use the WS-Management Scripting API or through the WinRM command-line tool.</span></span> <span data-ttu-id="88c8b-118">O WS-Management oferece suporte à maioria das classes e operações WMI familiares, incluindo objetos incorporados.</span><span class="sxs-lookup"><span data-stu-id="88c8b-118">WS-Management supports most of the familiar WMI classes and operations, including embedded objects.</span></span> <span data-ttu-id="88c8b-119">WS-Management pode aproveitar o WMI para coletar dados sobre recursos ou para gerenciar recursos em computadores baseados no Windows.</span><span class="sxs-lookup"><span data-stu-id="88c8b-119">WS-Management can leverage WMI to collect data about resources or to manage resources on a Windows-based computers.</span></span> <span data-ttu-id="88c8b-120">Isso significa que você pode obter dados sobre objetos como discos, adaptadores de rede, serviços ou processos em sua empresa por meio do conjunto existente de classes WMI.</span><span class="sxs-lookup"><span data-stu-id="88c8b-120">That means that you can obtain data about objects such as disks, network adapters, services, or processes in your enterprise through the existing set of WMI classes.</span></span> <span data-ttu-id="88c8b-121">Você também pode acessar os dados de hardware que estão disponíveis no provedor padrão de IPMI do WMI.</span><span class="sxs-lookup"><span data-stu-id="88c8b-121">You can also access the hardware data that is available from the standard WMI IPMI provider.</span></span>

## <a name="ws-management-windows-powershell-provider-wsman"></a><span data-ttu-id="88c8b-122">WS-Management o provedor do Windows PowerShell (WSMan)</span><span class="sxs-lookup"><span data-stu-id="88c8b-122">WS-Management Windows PowerShell Provider (WSMan)</span></span>

<span data-ttu-id="88c8b-123">O provedor WSMan fornece uma exibição hierárquica das definições de configuração do WS-Management disponíveis.</span><span class="sxs-lookup"><span data-stu-id="88c8b-123">The WSMan provider provides a hierarchical view into the available WS-Management configuration settings.</span></span> <span data-ttu-id="88c8b-124">O provedor permite explorar e definir as várias opções de configuração de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="88c8b-124">The provider allows you to explore and set the various WS-Management configuration options.</span></span>

## <a name="ws-management-configuration"></a><span data-ttu-id="88c8b-125">Configuração de WS-Management</span><span class="sxs-lookup"><span data-stu-id="88c8b-125">WS-Management Configuration</span></span>

<span data-ttu-id="88c8b-126">Se WS-Management não estiver instalado e configurado, a comunicação remota do Windows PowerShell não estará disponível, os cmdlets WS-Management não serão executados, WS-Management scripts não são executados e o provedor WSMan não pode executar operações de dados.</span><span class="sxs-lookup"><span data-stu-id="88c8b-126">If WS-Management is not installed and configured, Windows PowerShell remoting is not available, the WS-Management cmdlets do not run, WS-Management scripts do not run, and the WSMan provider cannot perform data operations.</span></span> <span data-ttu-id="88c8b-127">A ferramenta de linha de comando WS-Management, o WinRM e o encaminhamento de eventos também dependem da configuração de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="88c8b-127">The WS-Management command-line tool, WinRM, and event forwarding also depend on the WS-Management configuration.</span></span>

## <a name="ws-management-cmdlets"></a><span data-ttu-id="88c8b-128">WS-Management cmdlets</span><span class="sxs-lookup"><span data-stu-id="88c8b-128">WS-Management Cmdlets</span></span>

<span data-ttu-id="88c8b-129">WS-Management funcionalidade é implementada no Windows PowerShell por meio de um módulo que contém um conjunto de cmdlets e o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="88c8b-129">WS-Management functionality is implemented in Windows PowerShell through a module that contains a set of cmdlets and the WSMan provider.</span></span> <span data-ttu-id="88c8b-130">Você pode usar esses cmdlets para concluir as tarefas de ponta a ponta necessárias para gerenciar WS-Management configurações em computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="88c8b-130">You can use these cmdlets to complete the end-to-end tasks necessary to manage WS-Management settings on local and remote computers.</span></span>

<span data-ttu-id="88c8b-131">Os cmdlets WS-Management a seguir estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="88c8b-131">The following WS-Management cmdlets are available.</span></span>

## <a name="connection-cmdlets"></a><span data-ttu-id="88c8b-132">Cmdlets de conexão</span><span class="sxs-lookup"><span data-stu-id="88c8b-132">Connection Cmdlets</span></span>

- <span data-ttu-id="88c8b-133">Connect-WSMan: conecta o computador local ao serviço de WS-Management (WinRM) em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="88c8b-133">Connect-WSMan: Connects the local computer to the WS-Management (WinRM) service on a remote computer.</span></span>

- <span data-ttu-id="88c8b-134">Disconnect-WSMan: desconecta o computador local do serviço WS-Management (WinRM) em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="88c8b-134">Disconnect-WSMan: Disconnects the local computer from the WS-Management (WinRM) service on a remote computer.</span></span>

## <a name="management-data-cmdlets"></a><span data-ttu-id="88c8b-135">Management-Data cmdlets</span><span class="sxs-lookup"><span data-stu-id="88c8b-135">Management-Data Cmdlets</span></span>

- <span data-ttu-id="88c8b-136">Get-WSManInstance: exibe informações de gerenciamento para uma instância de recurso especificada por um URI de recurso.</span><span class="sxs-lookup"><span data-stu-id="88c8b-136">Get-WSManInstance: Displays management information for a resource instance that is specified by a resource URI.</span></span>

- <span data-ttu-id="88c8b-137">Invoke-WSManaction: invoca uma ação no objeto de destino que é especificado pelo URI de recurso e pelos seletores.</span><span class="sxs-lookup"><span data-stu-id="88c8b-137">Invoke-WSManAction: Invokes an action on the target object that is specified by the resource URI and by the selectors.</span></span>

- <span data-ttu-id="88c8b-138">New-WSManInstance: cria uma nova instância de recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="88c8b-138">New-WSManInstance: Creates a new management resource instance.</span></span>

- <span data-ttu-id="88c8b-139">Remove-WSManInstance: exclui uma instância de recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="88c8b-139">Remove-WSManInstance: Deletes a management resource instance.</span></span>

- <span data-ttu-id="88c8b-140">Set-WSManInstance: modifica as informações de gerenciamento relacionadas a um recurso.</span><span class="sxs-lookup"><span data-stu-id="88c8b-140">Set-WSManInstance: Modifies the management information that is related to a resource.</span></span>

## <a name="setup-and-configuration-cmdlets"></a><span data-ttu-id="88c8b-141">Cmdlets de instalação e configuração</span><span class="sxs-lookup"><span data-stu-id="88c8b-141">Setup and Configuration Cmdlets</span></span>

- <span data-ttu-id="88c8b-142">Set-WSManQuickConfig: configura o computador local para gerenciamento remoto.</span><span class="sxs-lookup"><span data-stu-id="88c8b-142">Set-WSManQuickConfig: Configures the local computer for remote management.</span></span>
  <span data-ttu-id="88c8b-143">Você pode usar o cmdlet Set-WSManQuickConfig para configurar WS-Management para permitir conexões remotas com o serviço do WS-Management (WinRM).</span><span class="sxs-lookup"><span data-stu-id="88c8b-143">You can use the Set-WSManQuickConfig cmdlet to configure WS-Management to allow remote connections to the WS-Management (WinRM) service.</span></span> <span data-ttu-id="88c8b-144">O cmdlet Set-WSManQuickConfig executa as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="88c8b-144">The Set-WSManQuickConfig cmdlet performs the following operations:</span></span>
  - <span data-ttu-id="88c8b-145">Ele determina se o serviço do WS-Management (WinRM) está em execução.</span><span class="sxs-lookup"><span data-stu-id="88c8b-145">It determines whether the WS-Management (WinRM) service is running.</span></span> <span data-ttu-id="88c8b-146">Se o serviço WinRM não estiver em execução, o cmdlet Set-WSManQuickConfig iniciará o serviço.</span><span class="sxs-lookup"><span data-stu-id="88c8b-146">If the WinRM service is not running, the Set-WSManQuickConfig cmdlet starts the service.</span></span>
  - <span data-ttu-id="88c8b-147">Ele define o tipo de inicialização do serviço WS-Management (WinRM) como automático.</span><span class="sxs-lookup"><span data-stu-id="88c8b-147">It sets the WS-Management (WinRM) service startup type to automatic.</span></span>
  - <span data-ttu-id="88c8b-148">Ele cria um ouvinte que aceita solicitações de qualquer endereço IP.</span><span class="sxs-lookup"><span data-stu-id="88c8b-148">It creates a listener that accepts requests from any IP address.</span></span> <span data-ttu-id="88c8b-149">O protocolo de transporte padrão é HTTP.</span><span class="sxs-lookup"><span data-stu-id="88c8b-149">The default transport protocol is HTTP.</span></span>
  - <span data-ttu-id="88c8b-150">Ele habilita uma exceção de firewall para tráfego de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="88c8b-150">It enables a firewall exception for WS-Management traffic.</span></span>

  <span data-ttu-id="88c8b-151">Observação: para executar esse cmdlet no Windows Vista, no Windows Server 2008 e em versões posteriores do Windows, você deve iniciar o Windows PowerShell com a opção "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="88c8b-151">Note: To run this cmdlet in Windows Vista, Windows Server 2008, and later versions of Windows, you must start Windows PowerShell with the "Run as administrator" option.</span></span>

- <span data-ttu-id="88c8b-152">Teste-WSMan: verifica se WS-Management está instalado e configurado.</span><span class="sxs-lookup"><span data-stu-id="88c8b-152">Test-WSMan: Verifies that WS-Management is installed and configured.</span></span> <span data-ttu-id="88c8b-153">O cmdlet Test-WSMan testa se o serviço de WS-Management (WinRM) está em execução e configurado em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="88c8b-153">The Test-WSMan cmdlet tests whether the WS-Management (WinRM) service is running and configured on a local or remote computer.</span></span>

- <span data-ttu-id="88c8b-154">Disable-WSManCredSSP: desabilita a autenticação CredSSP em um computador cliente.</span><span class="sxs-lookup"><span data-stu-id="88c8b-154">Disable-WSManCredSSP: Disables CredSSP authentication on a client computer.</span></span>

- <span data-ttu-id="88c8b-155">Enable-WSManCredSSP: habilita a autenticação CredSSP em um computador cliente.</span><span class="sxs-lookup"><span data-stu-id="88c8b-155">Enable-WSManCredSSP: Enables CredSSP authentication on a client computer.</span></span>

- <span data-ttu-id="88c8b-156">Get-WSManCredSSP: Obtém a configuração relacionada a CredSSP para um computador cliente.</span><span class="sxs-lookup"><span data-stu-id="88c8b-156">Get-WSManCredSSP: Gets the CredSSP-related configuration for a client computer.</span></span>

## <a name="ws-management-specific-cmdlets"></a><span data-ttu-id="88c8b-157">Cmdlets específicos do WS-Management</span><span class="sxs-lookup"><span data-stu-id="88c8b-157">WS-Management-Specific Cmdlets</span></span>

- <span data-ttu-id="88c8b-158">New-WSManSessionOption: cria um objeto WSManSessionOption para usar como entrada para um ou mais parâmetros de um cmdlet WS-Management.</span><span class="sxs-lookup"><span data-stu-id="88c8b-158">New-WSManSessionOption: Creates a WSManSessionOption object to use as input to one or more parameters of a WS-Management cmdlet.</span></span>

## <a name="additional-ws-management-information"></a><span data-ttu-id="88c8b-159">Informações adicionais de WS-Management</span><span class="sxs-lookup"><span data-stu-id="88c8b-159">Additional WS-Management Information</span></span>

<span data-ttu-id="88c8b-160">Para obter mais informações sobre o WS-Management, consulte os tópicos a seguir na documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="88c8b-160">For more information about WS-Management, see the following topics in the Windows documentation.</span></span>

[<span data-ttu-id="88c8b-161">Gerenciamento Remoto do Windows</span><span class="sxs-lookup"><span data-stu-id="88c8b-161">Windows Remote Management</span></span>](/windows/win32/winrm/portal)

[<span data-ttu-id="88c8b-162">Sobre Gerenciamento Remoto do Windows</span><span class="sxs-lookup"><span data-stu-id="88c8b-162">About Windows Remote Management</span></span>](/windows/win32/winrm/about-windows-remote-management)

[<span data-ttu-id="88c8b-163">Instalação e configuração para Gerenciamento Remoto do Windows</span><span class="sxs-lookup"><span data-stu-id="88c8b-163">Installation and Configuration for Windows Remote Management</span></span>](/windows/win32/winrm/installation-and-configuration-for-windows-remote-management)

[<span data-ttu-id="88c8b-164">Arquitetura de Gerenciamento Remoto do Windows</span><span class="sxs-lookup"><span data-stu-id="88c8b-164">Windows Remote Management Architecture</span></span>](/windows/win32/winrm/windows-remote-management-architecture)

[<span data-ttu-id="88c8b-165">Protocolo WS-Management</span><span class="sxs-lookup"><span data-stu-id="88c8b-165">WS-Management Protocol</span></span>](/windows/win32/winrm/ws-management-protocol)

[<span data-ttu-id="88c8b-166">Gerenciamento Remoto do Windows e WMI</span><span class="sxs-lookup"><span data-stu-id="88c8b-166">Windows Remote Management and WMI</span></span>](/windows/win32/winrm/windows-remote-management-and-wmi)

[<span data-ttu-id="88c8b-167">URIs do Recurso</span><span class="sxs-lookup"><span data-stu-id="88c8b-167">Resource URIs</span></span>](/windows/win32/winrm/resource-uris)

[<span data-ttu-id="88c8b-168">Gerenciamento de hardware remoto</span><span class="sxs-lookup"><span data-stu-id="88c8b-168">Remote Hardware Management</span></span>](/windows/win32/winrm/remote-hardware-management)

[<span data-ttu-id="88c8b-169">Eventos</span><span class="sxs-lookup"><span data-stu-id="88c8b-169">Events</span></span>](/windows/win32/winrm/events)

## <a name="see-also"></a><span data-ttu-id="88c8b-170">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="88c8b-170">SEE ALSO</span></span>

[<span data-ttu-id="88c8b-171">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="88c8b-171">Connect-WSMan</span></span>](xref:Microsoft.WSMan.Management.Connect-WSMan)

[<span data-ttu-id="88c8b-172">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="88c8b-172">Disable-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Disable-WSManCredSSP)

[<span data-ttu-id="88c8b-173">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="88c8b-173">Disconnect-WSMan</span></span>](xref:Microsoft.WSMan.Management.Disconnect-WSMan)

[<span data-ttu-id="88c8b-174">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="88c8b-174">Enable-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Enable-WSManCredSSP)

[<span data-ttu-id="88c8b-175">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="88c8b-175">Get-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Get-WSManCredSSP)

[<span data-ttu-id="88c8b-176">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="88c8b-176">Get-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Get-WSManInstance)

[<span data-ttu-id="88c8b-177">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="88c8b-177">Invoke-WSManAction</span></span>](xref:Microsoft.WSMan.Management.Invoke-WSManAction)

[<span data-ttu-id="88c8b-178">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="88c8b-178">New-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.New-WSManInstance)

[<span data-ttu-id="88c8b-179">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="88c8b-179">Remove-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Remove-WSManInstance)

[<span data-ttu-id="88c8b-180">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="88c8b-180">Set-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Set-WSManInstance)

[<span data-ttu-id="88c8b-181">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="88c8b-181">Set-WSManQuickConfig</span></span>](xref:Microsoft.WSMan.Management.Set-WSManQuickConfig)

[<span data-ttu-id="88c8b-182">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="88c8b-182">Test-WSMan</span></span>](xref:Microsoft.WSMan.Management.Test-WSMan)
