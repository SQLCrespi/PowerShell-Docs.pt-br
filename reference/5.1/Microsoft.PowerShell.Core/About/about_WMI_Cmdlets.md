---
description: Fornece informações de segundo plano sobre WMI (Instrumentação de Gerenciamento do Windows) e Windows PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI_Cmdlets
ms.openlocfilehash: c2099c005cedf64e9621d66d6757419320c9b43e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196132"
---
# <a name="about-wmi-cmdlets"></a><span data-ttu-id="51aeb-104">Sobre os cmdlets do WMI</span><span class="sxs-lookup"><span data-stu-id="51aeb-104">About WMI Cmdlets</span></span>

## <a name="short-description"></a><span data-ttu-id="51aeb-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="51aeb-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="51aeb-106">Fornece informações de segundo plano sobre WMI (Instrumentação de Gerenciamento do Windows) e Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51aeb-106">Provides background information about Windows Management Instrumentation (WMI) and Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="51aeb-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="51aeb-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="51aeb-108">Este tópico fornece informações sobre a tecnologia do WMI, os cmdlets do WMI para Windows PowerShell, comunicação remota baseada em WMI, aceleradores de WMI e solução de problemas de WMI.</span><span class="sxs-lookup"><span data-stu-id="51aeb-108">This topic provides information about WMI technology, the WMI cmdlets for Windows PowerShell, WMI-based remoting, WMI accelerators, and WMI troubleshooting.</span></span> <span data-ttu-id="51aeb-109">Este tópico também fornece links para outras informações sobre WMI.</span><span class="sxs-lookup"><span data-stu-id="51aeb-109">This topic also provides links to more information about WMI.</span></span>

### <a name="about-wmi"></a><span data-ttu-id="51aeb-110">SOBRE O WMI</span><span class="sxs-lookup"><span data-stu-id="51aeb-110">ABOUT WMI</span></span>

<span data-ttu-id="51aeb-111">A WMI (Instrumentação de Gerenciamento do Windows) é a implementação do WBEM (Gerenciamento Corporativo Baseado na Web) da Microsoft, que é uma iniciativa de mercado para desenvolver uma tecnologia padrão para acessar informações de gerenciamento em um ambiente corporativo.</span><span class="sxs-lookup"><span data-stu-id="51aeb-111">Windows Management Instrumentation (WMI) is the Microsoft implementation of Web-Based Enterprise Management (WBEM), which is an industry initiative to develop a standard technology for accessing management information in an enterprise environment.</span></span> <span data-ttu-id="51aeb-112">A WMI usa o padrão de mercado CIM (Modelo de Informação Comum) para representar sistemas, aplicativos, redes, dispositivos e outros componentes gerenciados.</span><span class="sxs-lookup"><span data-stu-id="51aeb-112">WMI uses the Common Information Model (CIM) industry standard to represent systems, applications, networks, devices, and other managed components.</span></span> <span data-ttu-id="51aeb-113">O CIM é desenvolvido e mantido pela DMTF (Distributed Management Task Force).</span><span class="sxs-lookup"><span data-stu-id="51aeb-113">CIM is developed and maintained by the Distributed Management Task Force (DMTF).</span></span> <span data-ttu-id="51aeb-114">Você pode usar o WMI para gerenciar computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="51aeb-114">You can use WMI to manage both local and remote computers.</span></span> <span data-ttu-id="51aeb-115">Por exemplo, você pode usar o WMI para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="51aeb-115">For example, you can use WMI to do the following:</span></span>

- <span data-ttu-id="51aeb-116">Iniciar um processo em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="51aeb-116">Start a process on a remote computer.</span></span>
- <span data-ttu-id="51aeb-117">Reinicie um computador remotamente.</span><span class="sxs-lookup"><span data-stu-id="51aeb-117">Restart a computer remotely.</span></span>
- <span data-ttu-id="51aeb-118">Obtenha uma lista dos aplicativos que estão instalados em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="51aeb-118">Get a list of the applications that are installed on a local or remote computer.</span></span>
- <span data-ttu-id="51aeb-119">Consulte os logs de eventos do Windows em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="51aeb-119">Query the Windows event logs on a local or remote computer.</span></span>

### <a name="the-wmi-cmdlets-for-windows-powershell"></a><span data-ttu-id="51aeb-120">OS CMDLETS DO WMI PARA O WINDOWS POWERSHELL</span><span class="sxs-lookup"><span data-stu-id="51aeb-120">THE WMI CMDLETS FOR WINDOWS POWERSHELL</span></span>

<span data-ttu-id="51aeb-121">O Windows PowerShell implementa a funcionalidade do WMI por meio de um conjunto de cmdlets que estão disponíveis no Windows PowerShell por padrão.</span><span class="sxs-lookup"><span data-stu-id="51aeb-121">Windows PowerShell implements WMI functionality through a set of cmdlets that are available in Windows PowerShell by default.</span></span> <span data-ttu-id="51aeb-122">Você pode usar esses cmdlets para concluir as tarefas de ponta a ponta necessárias para gerenciar computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="51aeb-122">You can use these cmdlets to complete the end-to-end tasks necessary to manage local and remote computers.</span></span>

<span data-ttu-id="51aeb-123">Os cmdlets do WMI a seguir estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="51aeb-123">The following WMI cmdlets are included.</span></span>

|<span data-ttu-id="51aeb-124">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="51aeb-124">Cmdlet</span></span>           |<span data-ttu-id="51aeb-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="51aeb-125">Description</span></span>                                   |
|-----------------|----------------------------------------------|
|<span data-ttu-id="51aeb-126">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="51aeb-126">Get-WmiObject</span></span>    |<span data-ttu-id="51aeb-127">Obtém instâncias de informações ou classes WMI</span><span class="sxs-lookup"><span data-stu-id="51aeb-127">Gets instances of WMI classes or information</span></span>  |
|                 |<span data-ttu-id="51aeb-128">sobre as classes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="51aeb-128">about the available classes.</span></span>                  |
|<span data-ttu-id="51aeb-129">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="51aeb-129">Invoke-WmiMethod</span></span> |<span data-ttu-id="51aeb-130">Chama os métodos WMI.</span><span class="sxs-lookup"><span data-stu-id="51aeb-130">Calls WMI methods.</span></span>                            |
|<span data-ttu-id="51aeb-131">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="51aeb-131">Register-WmiEvent</span></span>|<span data-ttu-id="51aeb-132">Assina um evento WMI.</span><span class="sxs-lookup"><span data-stu-id="51aeb-132">Subscribes to a WMI event.</span></span>                    |
|<span data-ttu-id="51aeb-133">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="51aeb-133">Remove-WmiObject</span></span> |<span data-ttu-id="51aeb-134">Exclui instâncias e classes do WMI.</span><span class="sxs-lookup"><span data-stu-id="51aeb-134">Deletes WMI classes and instances.</span></span>            |
|<span data-ttu-id="51aeb-135">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="51aeb-135">Set-WmiInstance</span></span>  |<span data-ttu-id="51aeb-136">Cria ou modifica instâncias de classes WMI.</span><span class="sxs-lookup"><span data-stu-id="51aeb-136">Creates or modifies instances of WMI classes.</span></span> |

### <a name="sample-commands"></a><span data-ttu-id="51aeb-137">COMANDOS DE EXEMPLO</span><span class="sxs-lookup"><span data-stu-id="51aeb-137">SAMPLE COMMANDS</span></span>
<span data-ttu-id="51aeb-138">O comando a seguir exibe as informações do BIOS para o computador local.</span><span class="sxs-lookup"><span data-stu-id="51aeb-138">The following command displays the BIOS information for the local computer.</span></span>

```powershell
C:\PS> get-wmiobject win32_bios | format-list *
```

<span data-ttu-id="51aeb-139">O comando a seguir exibe informações sobre o serviço WinRM para três computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="51aeb-139">The following command displays information about the WinRM service for three remote computers.</span></span>

```powershell
$wql = "select * from win32_service where name='WinRM'"
get-wmiobject -query $wql -computername server01, server01, server03
```

<span data-ttu-id="51aeb-140">O comando mais complexo a seguir sai de todas as instâncias de um programa.</span><span class="sxs-lookup"><span data-stu-id="51aeb-140">The following more complex command exits all instances of a program.</span></span>

```powershell
C:\PS> notepad.exe
C:\PS> $wql = "select * from win32_process where name='notepad.exe'"
C:\PS> $np = get-wmiobject -query $wql
C:\PS> $np | remove-wmiobject
```

### <a name="wmi-based-remoting"></a><span data-ttu-id="51aeb-141">COMUNICAÇÃO REMOTA BASEADA EM WMI</span><span class="sxs-lookup"><span data-stu-id="51aeb-141">WMI-BASED REMOTING</span></span>

<span data-ttu-id="51aeb-142">Embora a capacidade de gerenciar um sistema local por meio do WMI seja útil, são recursos de comunicação remota que tornam o WMI uma ferramenta administrativa poderosa.</span><span class="sxs-lookup"><span data-stu-id="51aeb-142">While the ability to manage a local system through WMI is useful, it is the remoting capabilities that make WMI a powerful administrative tool.</span></span> <span data-ttu-id="51aeb-143">O WMI usa o DCOM (Component Object Model distribuído) da Microsoft para se conectar e gerenciar sistemas.</span><span class="sxs-lookup"><span data-stu-id="51aeb-143">WMI uses Microsoft's Distributed Component Object Model (DCOM) to connect to and manage systems.</span></span> <span data-ttu-id="51aeb-144">Talvez seja necessário configurar alguns sistemas para permitir conexões DCOM.</span><span class="sxs-lookup"><span data-stu-id="51aeb-144">You might have to configure some systems to allow DCOM connections.</span></span>
<span data-ttu-id="51aeb-145">As configurações de firewall e as permissões DCOM bloqueadas podem bloquear a capacidade do WMI de gerenciar sistemas remotamente.</span><span class="sxs-lookup"><span data-stu-id="51aeb-145">Firewall settings and locked-down DCOM permissions can block WMI's ability to remotely manage systems.</span></span>

### <a name="wmi-type-accelerators"></a><span data-ttu-id="51aeb-146">ACELERADORES DE TIPOS DO WMI</span><span class="sxs-lookup"><span data-stu-id="51aeb-146">WMI TYPE ACCELERATORS</span></span>

<span data-ttu-id="51aeb-147">O Windows PowerShell inclui aceleradores de tipos do WMI.</span><span class="sxs-lookup"><span data-stu-id="51aeb-147">Windows PowerShell includes WMI type accelerators.</span></span> <span data-ttu-id="51aeb-148">Esses aceleradores de tipo WMI (atalhos) permitem um acesso mais direto a objetos WMI do que uma abordagem de acelerador sem tipo permitiria.</span><span class="sxs-lookup"><span data-stu-id="51aeb-148">These WMI type accelerators (shortcuts) allow more direct access to a WMI objects than a non-type accelerator approach would allow.</span></span>

<span data-ttu-id="51aeb-149">Os seguintes aceleradores de tipos têm suporte com o WMI:</span><span class="sxs-lookup"><span data-stu-id="51aeb-149">The following type accelerators are supported with WMI:</span></span>

<span data-ttu-id="51aeb-150">[WMISEARCHER]-um atalho para pesquisar objetos WMI.</span><span class="sxs-lookup"><span data-stu-id="51aeb-150">[WMISEARCHER] - A shortcut for searching for WMI objects.</span></span>

<span data-ttu-id="51aeb-151">[WMICLASS]-um atalho para acessar as propriedades e os métodos estáticos de uma classe.</span><span class="sxs-lookup"><span data-stu-id="51aeb-151">[WMICLASS] - A shortcut for accessing the static properties and methods of a class.</span></span>

<span data-ttu-id="51aeb-152">[WMI]-um atalho para obter uma única instância de uma classe.</span><span class="sxs-lookup"><span data-stu-id="51aeb-152">[WMI] - A shortcut for getting a single instance of a class.</span></span>

<span data-ttu-id="51aeb-153">[WMISEARCHER] é um acelerador de tipo para um ManagementObjectSearcher.</span><span class="sxs-lookup"><span data-stu-id="51aeb-153">[WMISEARCHER] is a type accelerator for a ManagementObjectSearcher.</span></span> <span data-ttu-id="51aeb-154">Ele pode pegar um construtor de cadeia de caracteres para criar um pesquisador que você pode então fazer um GET () em.</span><span class="sxs-lookup"><span data-stu-id="51aeb-154">It can take a string constructor to create a searcher that you can then do a GET() on.</span></span>

<span data-ttu-id="51aeb-155">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="51aeb-155">For example:</span></span>

```powershell
PS> $s = [WmiSearcher]'Select * from Win32_Process where Handlecount > 1000'
PS> $s.Get() |sort handlecount |ft handlecount,__path,name -auto

count  __PATH                                              name
-----  ------                                              ----
1105   \\SERVER01\root\cimv2:Win32_Process.Handle="3724"   PowerShell...
1132   \\SERVER01\root\cimv2:Win32_Process.Handle="1388"   winlogon.exe
1495   \\SERVER01\root\cimv2:Win32_Process.Handle="2852"   iexplore.exe
1699   \\SERVER01\root\cimv2:Win32_Process.Handle="1204"   OUTLOOK.EXE
1719   \\SERVER01\root\cimv2:Win32_Process.Handle="1912"   iexplore.exe
2579   \\SERVER01\root\cimv2:Win32_Process.Handle="1768"   svchost.exe
```

<span data-ttu-id="51aeb-156">[WMICLASS] é um acelerador de tipo para ManagementClass.</span><span class="sxs-lookup"><span data-stu-id="51aeb-156">[WMICLASS] is a type accelerator for ManagementClass.</span></span> <span data-ttu-id="51aeb-157">Isso tem um construtor de cadeia de caracteres que usa um caminho WMI local ou absoluto para uma classe WMI e retorna um objeto que está associado a essa classe.</span><span class="sxs-lookup"><span data-stu-id="51aeb-157">This has a string constructor that takes a local or absolute WMI path to a WMI class and returns an object that is bound to that class.</span></span>

<span data-ttu-id="51aeb-158">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="51aeb-158">For example:</span></span>

```powershell
PS> $c = [WMICLASS]"root\cimv2:WIn32_Process"
PS> $c |fl *
Name             : Win32_Process
__GENUS          : 1
__CLASS          : Win32_Process
__SUPERCLASS     : CIM_Process
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Process
__PROPERTY_COUNT : 45
__DERIVATION     : {CIM_Process, CIM_LogicalElement,
                   CIM_ManagedSystemElement}
__SERVER         : SERVER01
__NAMESPACE      : ROOT\cimv2
__PATH           : \\SERVER01\ROOT\cimv2:Win32_Process
```

<span data-ttu-id="51aeb-159">[WMI] é um acelerador de tipo para ManagementObject.</span><span class="sxs-lookup"><span data-stu-id="51aeb-159">[WMI] is a type accelerator for ManagementObject.</span></span> <span data-ttu-id="51aeb-160">Isso tem um construtor de cadeia de caracteres que usa um caminho WMI local ou absoluto para uma instância do WMI e retorna um objeto que está associado a essa instância.</span><span class="sxs-lookup"><span data-stu-id="51aeb-160">This has a string constructor that takes a local or absolute WMI path to a WMI instance and returns an object that is bound to that instance.</span></span>

<span data-ttu-id="51aeb-161">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="51aeb-161">For example:</span></span>

```powershell
PS> $p = [WMI]'\\SERVER01\root\cimv2:Win32_Process.Handle="1204"'
PS> $p.Name
OUTLOOK.EXE
```

### <a name="wmi-troubleshooting"></a><span data-ttu-id="51aeb-162">SOLUÇÃO DE PROBLEMAS DO WMI</span><span class="sxs-lookup"><span data-stu-id="51aeb-162">WMI TROUBLESHOOTING</span></span>

<span data-ttu-id="51aeb-163">Os problemas a seguir são os problemas mais comuns que podem ocorrer quando você tenta se conectar a um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="51aeb-163">The following problems are the most common problems that might occur when you try to connect to a remote computer.</span></span>

<span data-ttu-id="51aeb-164">Problema 1: o computador remoto não está online.</span><span class="sxs-lookup"><span data-stu-id="51aeb-164">Problem 1: The remote computer is not online.</span></span>

<span data-ttu-id="51aeb-165">Se um computador estiver offline, você não poderá se conectar a ele usando o WMI.</span><span class="sxs-lookup"><span data-stu-id="51aeb-165">If a computer is offline, you will not be able to connect to it by using WMI.</span></span>
<span data-ttu-id="51aeb-166">Você pode ver a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="51aeb-166">You may receive the following error message:</span></span>

```
Remote server machine does not exist or is unavailable
```

<span data-ttu-id="51aeb-167">Se você receber essa mensagem de erro, verifique se o computador está online.</span><span class="sxs-lookup"><span data-stu-id="51aeb-167">If you receive this error message, verify that the computer is online.</span></span> <span data-ttu-id="51aeb-168">Tente executar o ping no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="51aeb-168">Try to ping the remote computer.</span></span>

<span data-ttu-id="51aeb-169">Problema 2: você não tem direitos de administrador local no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="51aeb-169">Problem 2: You do not have local administrator rights on the remote computer.</span></span>

<span data-ttu-id="51aeb-170">Para usar o WMI remotamente, você deve ter direitos de administrador local no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="51aeb-170">To use WMI remotely, you must have local administrator rights on the remote computer.</span></span> <span data-ttu-id="51aeb-171">Se você não fizer isso, o acesso a esse computador será negado.</span><span class="sxs-lookup"><span data-stu-id="51aeb-171">If you do not, access to that computer will be denied.</span></span>

<span data-ttu-id="51aeb-172">Para verificar a segurança do namespace:</span><span class="sxs-lookup"><span data-stu-id="51aeb-172">To verify namespace security:</span></span>

1. <span data-ttu-id="51aeb-173">Clique em Iniciar, clique com o botão direito do mouse em Meu Computador e clique em gerenciar.</span><span class="sxs-lookup"><span data-stu-id="51aeb-173">Click Start, right-click My Computer, and then click Manage.</span></span>
2. <span data-ttu-id="51aeb-174">Em gerenciamento do computador, expanda Serviços e aplicativos, clique com o botão direito do mouse em controle WMI e clique em Propriedades.</span><span class="sxs-lookup"><span data-stu-id="51aeb-174">In Computer Management, expand Services and Applications, right-click WMI Control, and then click Properties.</span></span>
3. <span data-ttu-id="51aeb-175">Na caixa de diálogo Propriedades do controle WMI, clique na guia segurança.</span><span class="sxs-lookup"><span data-stu-id="51aeb-175">In the WMI Control Properties dialog box, click  the Security tab.</span></span>

<span data-ttu-id="51aeb-176">Problema 3: um firewall está bloqueando o acesso ao computador remoto.</span><span class="sxs-lookup"><span data-stu-id="51aeb-176">Problem 3: A firewall is blocking access to the remote computer.</span></span>

<span data-ttu-id="51aeb-177">O WMI usa os protocolos DCOM (COM distribuído) e RPC (chamada de procedimento remoto) para atravessar a rede.</span><span class="sxs-lookup"><span data-stu-id="51aeb-177">WMI uses the DCOM (Distributed COM) and RPC (Remote Procedure Call) protocols to traverse the network.</span></span> <span data-ttu-id="51aeb-178">Por padrão, muitos firewalls bloqueiam o tráfego de DCOM e RPC.</span><span class="sxs-lookup"><span data-stu-id="51aeb-178">By default, many firewalls block DCOM and RPC traffic.</span></span> <span data-ttu-id="51aeb-179">Se o firewall estiver bloqueando esses protocolos, a conexão falhará.</span><span class="sxs-lookup"><span data-stu-id="51aeb-179">If your firewall is blocking these protocols, your connection will fail.</span></span> <span data-ttu-id="51aeb-180">Por exemplo, o Firewall do Windows no Microsoft Windows XP Service Pack 2 está configurado para bloquear automaticamente todo o tráfego de rede não solicitado, incluindo DCOM e WMI.</span><span class="sxs-lookup"><span data-stu-id="51aeb-180">For example, Windows Firewall in Microsoft Windows XP Service Pack 2 is configured to automatically block all unsolicited network traffic, including DCOM and WMI.</span></span> <span data-ttu-id="51aeb-181">Em sua configuração padrão, o Firewall do Windows rejeita uma solicitação WMI de entrada e você recebe a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="51aeb-181">In its default configuration, Windows Firewall rejects an incoming WMI request, and you receive the following error message:</span></span>

```
Remote server machine does not exist or is unavailable
```

## <a name="see-also"></a><span data-ttu-id="51aeb-182">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="51aeb-182">SEE ALSO</span></span>

[<span data-ttu-id="51aeb-183">Sobre o WMI</span><span class="sxs-lookup"><span data-stu-id="51aeb-183">About WMI</span></span>](/windows/win32/wmisdk/about-wmi)

[<span data-ttu-id="51aeb-184">Solução de problemas do WMI</span><span class="sxs-lookup"><span data-stu-id="51aeb-184">WMI Troubleshooting</span></span>](/windows/win32/wmisdk/wmi-troubleshooting)

[<span data-ttu-id="51aeb-185">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="51aeb-185">Get-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[<span data-ttu-id="51aeb-186">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="51aeb-186">Invoke-WmiMethod</span></span>](xref:Microsoft.PowerShell.Management.Invoke-WmiMethod)

[<span data-ttu-id="51aeb-187">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="51aeb-187">Register-WmiEvent</span></span>](xref:Microsoft.PowerShell.Management.Register-WmiEvent)

[<span data-ttu-id="51aeb-188">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="51aeb-188">Remove-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Remove-WmiObject)

[<span data-ttu-id="51aeb-189">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="51aeb-189">Set-WmiInstance</span></span>](xref:Microsoft.PowerShell.Management.Set-WmiInstance)
