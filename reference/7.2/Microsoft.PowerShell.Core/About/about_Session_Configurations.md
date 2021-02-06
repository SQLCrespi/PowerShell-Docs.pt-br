---
description: Descreve as configurações de sessão, que determinam os usuários que podem se conectar ao computador remotamente e os comandos que eles podem executar.
Locale: en-US
ms.date: 12/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configurations?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configurations
ms.openlocfilehash: 4c6d5494f49bc271a7fe128fbce7b27c9d1f675f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599043"
---
# <a name="about-session-configurations"></a><span data-ttu-id="59500-103">Sobre as configurações de sessão</span><span class="sxs-lookup"><span data-stu-id="59500-103">About Session Configurations</span></span>

## <a name="short-description"></a><span data-ttu-id="59500-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="59500-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="59500-105">Descreve as configurações de sessão, que determinam os usuários que podem se conectar ao computador remotamente e os comandos que eles podem executar.</span><span class="sxs-lookup"><span data-stu-id="59500-105">Describes session configurations, which determine the users who can connect to the computer remotely and the commands they can run.</span></span>

## <a name="long-description"></a><span data-ttu-id="59500-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="59500-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="59500-107">Uma configuração de sessão, também conhecida como "ponto de extremidade", é um grupo de configurações no computador local que define o ambiente para as sessões do PowerShell que são criadas quando os usuários remotos ou locais se conectam ao PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="59500-107">A session configuration, also known as an "endpoint" is a group of settings on the local computer that define the environment for the PowerShell sessions that are created when remote or local users connect to PowerShell on the local computer.</span></span>

<span data-ttu-id="59500-108">Os administradores do computador podem usar configurações de sessão para proteger o computador e definir ambientes personalizados para usuários que se conectam ao computador.</span><span class="sxs-lookup"><span data-stu-id="59500-108">Administrators of the computer can use session configurations to protect the computer and to define custom environments for users who connect to the computer.</span></span>

<span data-ttu-id="59500-109">Os administradores também podem usar as configurações de sessão para determinar as permissões necessárias para se conectar ao computador remotamente.</span><span class="sxs-lookup"><span data-stu-id="59500-109">Administrators can also use session configurations to determine the permissions that are required to connect to the computer remotely.</span></span> <span data-ttu-id="59500-110">Por padrão, somente os membros do grupo Administradores têm permissão para usar a configuração de sessão para se conectar remotamente, mas você pode alterar as configurações padrão para permitir que todos os usuários ou usuários selecionados se conectem remotamente ao seu computador.</span><span class="sxs-lookup"><span data-stu-id="59500-110">By default, only members of the Administrators group have permission to use the session configuration to connect remotely, but you can change the default settings to allow all users, or selected users, to connect remotely to your computer.</span></span>

<span data-ttu-id="59500-111">A partir do PowerShell 3,0, você pode usar um arquivo de configuração de sessão para definir os elementos de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="59500-111">Beginning in PowerShell 3.0, you can use a session configuration file to define the elements of a session configuration.</span></span> <span data-ttu-id="59500-112">Esse recurso facilita a personalização de sessões sem escrever código e descobrir as propriedades de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="59500-112">This feature makes it easy to customize sessions without writing code and to discover the properties of a session configuration.</span></span> <span data-ttu-id="59500-113">Para criar um arquivo de configuração de sessão, use o cmdlet New-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="59500-113">To create a session configuration file, use the New-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="59500-114">Para obter mais informações sobre como criar arquivos de configuração, confira [about_Session_Configuration_Files](about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="59500-114">For more information about session configuration files, see [about_Session_Configuration_Files](about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="59500-115">As configurações de sessão são um recurso da comunicação remota do PowerShell baseada em Web Services para gerenciamento (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="59500-115">Session configurations are a feature of Web Services for Management (WS-Management) based PowerShell remoting.</span></span> <span data-ttu-id="59500-116">Eles são usados somente quando você usa os cmdlets New-PSSession, Invoke-Command ou Enter-PSSession para se conectar a um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="59500-116">They are used only when you use the New-PSSession, Invoke-Command, or Enter-PSSession cmdlets to connect to a remote computer.</span></span>

<span data-ttu-id="59500-117">Observação: para gerenciar as configurações de sessão, inicie o PowerShell com a opção "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="59500-117">Note: To manage the session configurations, start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="59500-118">Sobre as configurações de sessão</span><span class="sxs-lookup"><span data-stu-id="59500-118">About Session Configurations</span></span>

<span data-ttu-id="59500-119">Cada sessão do PowerShell usa uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="59500-119">Every PowerShell session uses a session configuration.</span></span> <span data-ttu-id="59500-120">Isso inclui sessões persistentes que você cria usando os cmdlets New-PSSession ou Enter-PSSession e as sessões temporárias que o PowerShell cria quando você usa o parâmetro ComputerName de um cmdlet que usa a tecnologia de comunicação remota baseada no WS-Management, como Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="59500-120">This includes persistent sessions that you create by using the New-PSSession or Enter-PSSession cmdlets, and the temporary sessions that PowerShell creates when you use the ComputerName parameter of a cmdlet that uses WS-Management-based remoting technology, such as Invoke-Command.</span></span>

<span data-ttu-id="59500-121">Os administradores podem usar as configurações de sessão para proteger os recursos do computador e criar ambientes personalizados para os usuários que se conectam ao computador.</span><span class="sxs-lookup"><span data-stu-id="59500-121">Administrators can use session configurations to protect the resources of the computer and to create custom environments for users who connect to the computer.</span></span> <span data-ttu-id="59500-122">Por exemplo, você pode usar uma configuração de sessão para limitar o tamanho dos objetos que o computador recebe na sessão, para definir o modo de linguagem da sessão e para especificar os cmdlets, provedores e funções que estão disponíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="59500-122">For example, you can use a session configuration to limit the size of objects that the computer receives in the session, to define the language mode of the session, and to specify the cmdlets, providers, and functions that are available in the session.</span></span>

<span data-ttu-id="59500-123">Ao configurar o descritor de segurança de uma configuração de sessão, você determina quem pode usar a configuração de sessão para se conectar ao computador.</span><span class="sxs-lookup"><span data-stu-id="59500-123">By configuring the security descriptor of a session configuration, you determine who can use the session configuration to connect to the computer.</span></span>
<span data-ttu-id="59500-124">Os usuários devem ter permissão de execução para uma configuração de sessão para usá-la em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="59500-124">Users must have Execute permission to a session configuration to use it in a session.</span></span> <span data-ttu-id="59500-125">Se um usuário não tiver as permissões necessárias para usar qualquer uma das configurações de sessão em um computador, o usuário não poderá se conectar ao computador remotamente.</span><span class="sxs-lookup"><span data-stu-id="59500-125">If a user does not have the required permissions to use any of the session configurations on a computer, the user cannot connect to the computer remotely.</span></span>

<span data-ttu-id="59500-126">Por padrão, somente os administradores do computador têm permissão para usar as configurações de sessão padrão.</span><span class="sxs-lookup"><span data-stu-id="59500-126">By default, only Administrators of the computer have permission to use the default session configurations.</span></span> <span data-ttu-id="59500-127">Porém, você pode alterar os descritores de segurança para permitir que todos, nenhum ou apenas usuários selecionados usem as configurações de sessão no seu computador.</span><span class="sxs-lookup"><span data-stu-id="59500-127">But, you can change the security descriptors to allow everyone, no one, or only selected users to use the session configurations on your computer.</span></span>

<span data-ttu-id="59500-128">Configurações de sessão internas</span><span class="sxs-lookup"><span data-stu-id="59500-128">Built-in Session Configurations</span></span>

<span data-ttu-id="59500-129">O PowerShell 3,0 inclui configurações de sessão internas chamadas Microsoft. PowerShell e Microsoft. PowerShell. Workflow.</span><span class="sxs-lookup"><span data-stu-id="59500-129">PowerShell 3.0 includes built-in session configurations named Microsoft.PowerShell and Microsoft.PowerShell.Workflow.</span></span> <span data-ttu-id="59500-130">Em computadores que executam versões de 64 bits do Windows, o PowerShell também fornece o Microsoft. PowerShell32, uma configuração de sessão de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="59500-130">On computers running 64-bit versions of Windows, PowerShell also provides Microsoft.PowerShell32, a 32-bit session configuration.</span></span>

<span data-ttu-id="59500-131">A configuração de sessão do Microsoft. PowerShell é usada para sessões por padrão, ou seja, quando um comando para criar uma sessão não inclui o parâmetro ConfigurationName do cmdlet New-PSSession, Enter-PSSession ou Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="59500-131">The Microsoft.PowerShell session configuration is used for sessions by default, that is, when a command to create a session does not include the ConfigurationName parameter of the New-PSSession, Enter-PSSession, or Invoke-Command cmdlet.</span></span>

<span data-ttu-id="59500-132">Os descritores de segurança para as configurações de sessão padrão permitem que somente membros do grupo Administradores no computador local os usem.</span><span class="sxs-lookup"><span data-stu-id="59500-132">The security descriptors for the default session configurations allow only members of the Administrators group on the local computer to use them.</span></span> <span data-ttu-id="59500-133">Assim, somente os membros do grupo Administradores podem se conectar ao computador remotamente, a menos que você altere as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="59500-133">As such, only members of the Administrators group can connect to the computer remotely unless you change the default settings.</span></span>

<span data-ttu-id="59500-134">Você pode alterar as configurações de sessão padrão usando a variável de preferência $PSSessionConfigurationName.</span><span class="sxs-lookup"><span data-stu-id="59500-134">You can change the default session configurations by using the $PSSessionConfigurationName preference variable.</span></span> <span data-ttu-id="59500-135">Para obter mais informações, consulte about_preference_variables.</span><span class="sxs-lookup"><span data-stu-id="59500-135">For more information, see about_Preference_Variables.</span></span>

<span data-ttu-id="59500-136">Exibindo configurações de sessão no computador local</span><span class="sxs-lookup"><span data-stu-id="59500-136">Viewing Session Configurations on the Local Computer</span></span>

<span data-ttu-id="59500-137">Para obter as configurações de sessão no computador local, use o cmdlet Get-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="59500-137">To get the session configurations on your local computer, use the Get-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="59500-138">Por exemplo, digite:</span><span class="sxs-lookup"><span data-stu-id="59500-138">For example, type:</span></span>

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property Name, Permission

Name       : microsoft.powershell
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell.workflow
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell32
Permission : BUILTIN\Administrators AccessAllowed
```

<span data-ttu-id="59500-139">O objeto de configuração de sessão é expandido no PowerShell 3,0 para exibir as propriedades da configuração de sessão que são configuradas usando um arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="59500-139">The session configuration object is expanded in PowerShell 3.0 to display the properties of the session configuration that are configured by using a session configuration file.</span></span>

<span data-ttu-id="59500-140">Por exemplo, para ver todas as propriedades de um objeto de configuração de sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="59500-140">For example, to see all of the properties of a session configuration object, type:</span></span>

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property *
```

<span data-ttu-id="59500-141">Você também pode usar o provedor WSMan no PowerShell para exibir as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="59500-141">You can also use the WSMan provider in PowerShell to view session configurations.</span></span> <span data-ttu-id="59500-142">O provedor WSMan cria uma unidade WSMAN: em sua sessão.</span><span class="sxs-lookup"><span data-stu-id="59500-142">The WSMan provider creates a WSMAN: drive in your session.</span></span>

<span data-ttu-id="59500-143">Na unidade WSMAN:, as configurações de sessão estão no nó plugin.</span><span class="sxs-lookup"><span data-stu-id="59500-143">In the WSMAN: drive, session configurations are in the Plugin node.</span></span> <span data-ttu-id="59500-144">(Todas as configurações de sessão estão no nó plugin, mas há itens no nó plug-in que não são configurações de sessão.)</span><span class="sxs-lookup"><span data-stu-id="59500-144">(All session configurations are in the Plugin node, but there are items in the Plugin node that are not session configurations.)</span></span>

<span data-ttu-id="59500-145">Por exemplo, para exibir as configurações de sessão no computador local, digite:</span><span class="sxs-lookup"><span data-stu-id="59500-145">For example, to view the session configurations on the local computer, type:</span></span>

```powershell
PS C:> dir wsman:\localhost\plugin\microsoft*

WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

<span data-ttu-id="59500-146">Exibindo configurações de sessão em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="59500-146">Viewing Session Configurations on a Remote Computer</span></span>

<span data-ttu-id="59500-147">Para exibir as configurações de sessão em um computador remoto, use o cmdlet Connect-WSMan para adicionar uma nota para o computador remoto para a unidade WSMAN: no computador local e, em seguida, use a unidade WSMAN: para exibir as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="59500-147">To view the session configurations on a remote computer, use the Connect-WSMan cmdlet to add a note for the remote computer to the WSMAN: drive on your local computer, and then use the WSMAN: drive to view the session configurations.</span></span>

<span data-ttu-id="59500-148">Por exemplo, o comando a seguir adiciona um nó para o computador remoto Server01 à unidade WSMAN: no computador local.</span><span class="sxs-lookup"><span data-stu-id="59500-148">For example, the following command adds a node for the Server01 remote computer to the WSMAN: drive on the local computer.</span></span>

```powershell
PS C:> Connect-WSMan server01.corp.fabrikam.com
```

<span data-ttu-id="59500-149">Quando o comando for concluído, você poderá navegar até o nó do computador Server01 para exibir as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="59500-149">When the command is complete, you can navigate to the node for the Server01 computer to view the session configurations.</span></span>

<span data-ttu-id="59500-150">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59500-150">For example:</span></span>

```powershell
PS C:> cd wsman:

PS WSMan:> dir

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01.corp.fabrikam.com                    Container

PS WSMan:> dir server01\plugin\

WSManConfig: Microsoft.WSMan.Management\WSMan::server01.corp.fabrikam.com\Pl
ugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

<span data-ttu-id="59500-151">Alterando o descritor de segurança de uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="59500-151">Changing the Security Descriptor of a Session Configuration</span></span>

<span data-ttu-id="59500-152">No Windows Server 2012 e versões mais recentes do Windows Server, as configurações de sessão internas são habilitadas para usuários remotos por padrão.</span><span class="sxs-lookup"><span data-stu-id="59500-152">In Windows Server 2012 and newer releases of Windows Server, the built-in session configurations are enabled for remote users by default.</span></span> <span data-ttu-id="59500-153">Em outras versões com suporte do Windows, você deve alterar os descritores de segurança das configurações de sessão para permitir o acesso remoto.</span><span class="sxs-lookup"><span data-stu-id="59500-153">In other supported versions of Windows, you must change the security descriptors of the session configurations to allow remote access.</span></span>

<span data-ttu-id="59500-154">Para habilitar o acesso remoto às configurações de sessão no computador, use o cmdlet Enable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="59500-154">To enable remote access to the session configurations on the computer, use the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="59500-155">Esse cmdlet cria duas configurações de sessão:</span><span class="sxs-lookup"><span data-stu-id="59500-155">This cmdlet creates two session configurations:</span></span>

- <span data-ttu-id="59500-156">com o nome definido como: "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="59500-156">with the name defined as: "PowerShell."</span></span> <span data-ttu-id="59500-157">+ "versão atual do PowerShell"</span><span class="sxs-lookup"><span data-stu-id="59500-157">+ "current PowerShell version"</span></span>
- <span data-ttu-id="59500-158">com o nome "PowerShell. 6", não vinculado a nenhuma versão específica do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59500-158">with name "PowerShell.6", untied to any specific PowerShell version.</span></span>

<span data-ttu-id="59500-159">Além disso, por padrão, somente os membros do grupo Administradores no computador têm a permissão executar para as configurações de sessão padrão, mas você pode alterar os descritores de segurança nas configurações de sessão padrão e em todas as configurações de sessão que você criar.</span><span class="sxs-lookup"><span data-stu-id="59500-159">Also, by default, only members of the Administrators group on the computer have Execute permission to the default session configurations, but you can change the security descriptors on the default session configurations and on any session configurations that you create.</span></span>

<span data-ttu-id="59500-160">Para conceder a outros usuários permissão para se conectar ao computador remotamente, use o cmdlet Set-PSSessionConfiguration para adicionar permissões "executar" para esses usuários aos descritores de segurança das configurações de sessão Microsoft. PowerShell e Microsoft. PowerShell32.</span><span class="sxs-lookup"><span data-stu-id="59500-160">To give other users permission to connect to the computer remotely, use the Set-PSSessionConfiguration cmdlet to add "Execute" permissions for those users to the security descriptors of the Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span>

<span data-ttu-id="59500-161">Por exemplo, o comando a seguir abre uma página de propriedades que permite alterar o descritor de segurança para a configuração de sessão padrão do Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59500-161">For example, the following command opens a property page that lets you change the security descriptor for the Microsoft.PowerShell default session configuration.</span></span>

```powershell
Set-PSSessionConfiguration -name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

<span data-ttu-id="59500-162">Para negar a permissão Everyone para todas as configurações de sessão no computador, use o cmdlet Disable-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="59500-162">To deny everyone permission to all the session configurations on the computer, use the Disable-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="59500-163">Por exemplo, o comando a seguir desabilita as configurações de sessão padrão no computador.</span><span class="sxs-lookup"><span data-stu-id="59500-163">For example, the following command disables the default session configurations on the computer.</span></span>

```powershell
PS C:> Disable-PSSessionConfiguration -Name Microsoft.PowerShell
```

<span data-ttu-id="59500-164">Para impedir que usuários remotos se conectem ao computador, mas permitir que os usuários locais se conectem, use o cmdlet Disable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="59500-164">To prevent remote users from connecting to the computer, but allow local users to connect, use the Disable-PSRemoting cmdlet.</span></span> <span data-ttu-id="59500-165">Disable-PSRemoting adiciona uma entrada "Network_Deny_All" a todas as configurações de sessão no computador.</span><span class="sxs-lookup"><span data-stu-id="59500-165">Disable-PSRemoting adds a "Network_Deny_All" entry to all session configurations on the computer.</span></span>

```powershell
PS C:> Disable-PSRemoting
```

<span data-ttu-id="59500-166">Para permitir que usuários remotos usem todas as configurações de sessão no computador, use o cmdlet Enable-PSRemoting ou Enable-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="59500-166">To allow remote users to use all session configurations on the computer, use the Enable-PSRemoting or Enable-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="59500-167">Por exemplo, o comando a seguir habilita o acesso remoto às configurações de sessão internas.</span><span class="sxs-lookup"><span data-stu-id="59500-167">For example, the following command enables remote access to the built-in session configurations.</span></span>

```powershell
PS C:> Enable-PSSessionConfiguration -name Microsoft.Power*
```

<span data-ttu-id="59500-168">Para fazer outras alterações no descritor de segurança de uma configuração de sessão, use o cmdlet Set-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="59500-168">To make other changes to the security descriptor of a session configuration, use the Set-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="59500-169">Use o parâmetro SecurityDescriptorSDDL para enviar um valor de cadeia de caracteres SDDL.</span><span class="sxs-lookup"><span data-stu-id="59500-169">Use the SecurityDescriptorSDDL parameter to submit an SDDL string value.</span></span> <span data-ttu-id="59500-170">Use o parâmetro ShowSecurityDescriptorUI dos para exibir uma folha de propriedades da interface do usuário que ajuda você a criar uma nova SDDL.</span><span class="sxs-lookup"><span data-stu-id="59500-170">Use the ShowSecurityDescriptorUI parameter to display a user interface property sheet that helps you to create a new SDDL.</span></span>

<span data-ttu-id="59500-171">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59500-171">For example:</span></span>

```powershell
Set-PSSessionConfiguration -Name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

<span data-ttu-id="59500-172">Criando uma nova configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="59500-172">Creating a New Session Configuration</span></span>

<span data-ttu-id="59500-173">Para criar uma nova configuração de sessão no computador local, use o cmdlet Register-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="59500-173">To create a new session configuration on the local computer, use the Register-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="59500-174">Para definir a nova configuração de sessão, você pode usar um assembly C#, um script do PowerShell e os parâmetros do cmdlet Register-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="59500-174">To define the new session configuration, you can use a C# assembly, a PowerShell script, and the parameters of the Register-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="59500-175">Por exemplo, o comando a seguir cria uma configuração de sessão que é idêntica à configuração de sessão do Microsoft. PowerShell, exceto pelo fato de que ela limita os dados recebidos de um comando remoto para 20 megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="59500-175">For example, the following command creates a session configuration that is identical the Microsoft.PowerShell session configuration, except that it limits the data received from a remote command to 20 megabytes (MB).</span></span> <span data-ttu-id="59500-176">(O padrão é 50 MB).</span><span class="sxs-lookup"><span data-stu-id="59500-176">(The default is 50 MB).</span></span>

```powershell
Register-PSSessionConfiguration -Name NewConfig `
  -MaximumReceivedDataSizePerCommandMB 20
```

<span data-ttu-id="59500-177">Ao criar uma configuração de sessão, você pode gerenciá-la usando os outros cmdlets de configuração de sessão e ela aparece na unidade WSMAN:.</span><span class="sxs-lookup"><span data-stu-id="59500-177">When you create a session configuration, you can manage it by using the other session configuration cmdlets, and it appears in the WSMAN: drive.</span></span>

<span data-ttu-id="59500-178">Para obter mais informações, consulte Register-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="59500-178">For more information, see Register-PSSessionConfiguration.</span></span>

<span data-ttu-id="59500-179">Removendo uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="59500-179">Removing a Session Configuration</span></span>

<span data-ttu-id="59500-180">Para remover uma configuração de sessão do computador local, use o cmdlet Unregister-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="59500-180">To remove a session configuration from the local computer, use the Unregister-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="59500-181">Por exemplo, o comando a seguir remove a configuração de sessão NewConfig do computador.</span><span class="sxs-lookup"><span data-stu-id="59500-181">For example, the following command removes the NewConfig session configuration from the computer.</span></span>

```powershell
PS C:> Unregister-PSSessionConfiguration -Name NewConfig
```

<span data-ttu-id="59500-182">Para obter mais informações, consulte Unregister-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="59500-182">For more information, see Unregister-PSSessionConfiguration.</span></span>

<span data-ttu-id="59500-183">Restaurando uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="59500-183">Restoring a Session Configuration</span></span>

<span data-ttu-id="59500-184">Para restaurar uma configuração de sessão padrão que foi excluída (não registrada) acidentalmente, use o cmdlet Enable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="59500-184">To restore a default session configuration that was deleted (unregistered) accidentally, use the Enable-PSRemoting cmdlet.</span></span>

<span data-ttu-id="59500-185">O cmdlet Enable-PSRemoting recria todas as configurações de sessões padrão que não existem no computador.</span><span class="sxs-lookup"><span data-stu-id="59500-185">The Enable-PSRemoting cmdlet recreates all default sessions configurations that do not exist on the computer.</span></span> <span data-ttu-id="59500-186">Ele não substitui nem altera os valores de propriedade das configurações de sessão existentes.</span><span class="sxs-lookup"><span data-stu-id="59500-186">It does not overwrite or change the property values of existing session configurations.</span></span>

<span data-ttu-id="59500-187">Para restaurar os valores de propriedade originais de uma configuração de sessão padrão, use o Unregister-PSSessionConfiguration para excluir a configuração de sessão e, em seguida, use o cmdlet Enable-PSRemoting para recriá-lo.</span><span class="sxs-lookup"><span data-stu-id="59500-187">To restore the original property values of a default session configuration, use the Unregister-PSSessionConfiguration to delete the session configuration and then use the Enable-PSRemoting cmdlet to recreate it.</span></span>

<span data-ttu-id="59500-188">Selecionando uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="59500-188">Selecting a Session Configuration</span></span>

<span data-ttu-id="59500-189">Para selecionar uma configuração de sessão específica para uma sessão, use o parâmetro ConfigurationName de New-PSSession, Enter-PSSession ou Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="59500-189">To select a particular session configuration for a session, use the ConfigurationName parameter of New-PSSession, Enter-PSSession, or Invoke-Command.</span></span>

<span data-ttu-id="59500-190">Por exemplo, esse comando usa o cmdlet New-PSSession para iniciar uma PSSession no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="59500-190">For example, this command uses the New-PSSession cmdlet to start a PSSession on the Server01 computer.</span></span> <span data-ttu-id="59500-191">O comando usa o parâmetro ConfigurationName para selecionar a configuração WithProfile no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="59500-191">The command uses the ConfigurationName parameter to select the WithProfile configuration on the Server01 computer.</span></span>

```powershell
PS C:> New-PSSession -ComputerName Server01 -ConfigurationName WithProfile
```

<span data-ttu-id="59500-192">Esse comando só terá sucesso se o usuário atual tiver permissão para usar a configuração de sessão WithProfile ou puder fornecer as credenciais de um usuário que tem as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="59500-192">This command will succeed only if the current user has permission to use the WithProfile session configuration or can supply the credentials of a user who has the required permissions.</span></span>

<span data-ttu-id="59500-193">Você também pode usar a variável de preferência $PSSessionConfigurationName para alterar a configuração de sessão padrão no computador.</span><span class="sxs-lookup"><span data-stu-id="59500-193">You can also use the $PSSessionConfigurationName preference variable to change the default session configuration on the computer.</span></span> <span data-ttu-id="59500-194">Para obter mais informações sobre a variável de preferência $PSSessionConfigurationName, consulte about_Preference_Variables.</span><span class="sxs-lookup"><span data-stu-id="59500-194">For more information about the $PSSessionConfigurationName preference variable, see about_Preference_Variables.</span></span>

## <a name="keywords"></a><span data-ttu-id="59500-195">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="59500-195">KEYWORDS</span></span>

<span data-ttu-id="59500-196">about_Endpoints about_SessionConfigurations</span><span class="sxs-lookup"><span data-stu-id="59500-196">about_Endpoints about_SessionConfigurations</span></span>

## <a name="see-also"></a><span data-ttu-id="59500-197">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="59500-197">SEE ALSO</span></span>

[<span data-ttu-id="59500-198">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="59500-198">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="59500-199">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="59500-199">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="59500-200">about_Remote</span><span class="sxs-lookup"><span data-stu-id="59500-200">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="59500-201">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="59500-201">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)

[<span data-ttu-id="59500-202">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="59500-202">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="59500-203">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="59500-203">Disable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[<span data-ttu-id="59500-204">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="59500-204">Enable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[<span data-ttu-id="59500-205">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="59500-205">Get-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[<span data-ttu-id="59500-206">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="59500-206">New-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[<span data-ttu-id="59500-207">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="59500-207">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[<span data-ttu-id="59500-208">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="59500-208">Set-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[<span data-ttu-id="59500-209">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="59500-209">Test-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[<span data-ttu-id="59500-210">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="59500-210">Unregister-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)

