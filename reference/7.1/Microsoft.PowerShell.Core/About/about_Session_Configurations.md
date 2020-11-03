---
description: Descreve as configurações de sessão, que determinam os usuários que podem se conectar ao computador remotamente e os comandos que eles podem executar.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 12/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configurations?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configurations
ms.openlocfilehash: 98e0766c4728021a1ea9b2b015fa4b7f5d9df25a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195542"
---
# <a name="about-session-configurations"></a><span data-ttu-id="d677f-104">Sobre as configurações de sessão</span><span class="sxs-lookup"><span data-stu-id="d677f-104">About Session Configurations</span></span>

## <a name="short-description"></a><span data-ttu-id="d677f-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="d677f-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="d677f-106">Descreve as configurações de sessão, que determinam os usuários que podem se conectar ao computador remotamente e os comandos que eles podem executar.</span><span class="sxs-lookup"><span data-stu-id="d677f-106">Describes session configurations, which determine the users who can connect to the computer remotely and the commands they can run.</span></span>

## <a name="long-description"></a><span data-ttu-id="d677f-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="d677f-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="d677f-108">Uma configuração de sessão, também conhecida como "ponto de extremidade", é um grupo de configurações no computador local que define o ambiente para as sessões do PowerShell que são criadas quando os usuários remotos ou locais se conectam ao PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="d677f-108">A session configuration, also known as an "endpoint" is a group of settings on the local computer that define the environment for the PowerShell sessions that are created when remote or local users connect to PowerShell on the local computer.</span></span>

<span data-ttu-id="d677f-109">Os administradores do computador podem usar configurações de sessão para proteger o computador e definir ambientes personalizados para usuários que se conectam ao computador.</span><span class="sxs-lookup"><span data-stu-id="d677f-109">Administrators of the computer can use session configurations to protect the computer and to define custom environments for users who connect to the computer.</span></span>

<span data-ttu-id="d677f-110">Os administradores também podem usar as configurações de sessão para determinar as permissões necessárias para se conectar ao computador remotamente.</span><span class="sxs-lookup"><span data-stu-id="d677f-110">Administrators can also use session configurations to determine the permissions that are required to connect to the computer remotely.</span></span> <span data-ttu-id="d677f-111">Por padrão, somente os membros do grupo Administradores têm permissão para usar a configuração de sessão para se conectar remotamente, mas você pode alterar as configurações padrão para permitir que todos os usuários ou usuários selecionados se conectem remotamente ao seu computador.</span><span class="sxs-lookup"><span data-stu-id="d677f-111">By default, only members of the Administrators group have permission to use the session configuration to connect remotely, but you can change the default settings to allow all users, or selected users, to connect remotely to your computer.</span></span>

<span data-ttu-id="d677f-112">A partir do PowerShell 3,0, você pode usar um arquivo de configuração de sessão para definir os elementos de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d677f-112">Beginning in PowerShell 3.0, you can use a session configuration file to define the elements of a session configuration.</span></span> <span data-ttu-id="d677f-113">Esse recurso facilita a personalização de sessões sem escrever código e descobrir as propriedades de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d677f-113">This feature makes it easy to customize sessions without writing code and to discover the properties of a session configuration.</span></span> <span data-ttu-id="d677f-114">Para criar um arquivo de configuração de sessão, use o cmdlet New-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d677f-114">To create a session configuration file, use the New-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="d677f-115">Para obter mais informações sobre como criar arquivos de configuração, confira [about_Session_Configuration_Files](about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="d677f-115">For more information about session configuration files, see [about_Session_Configuration_Files](about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="d677f-116">As configurações de sessão são um recurso da comunicação remota do PowerShell baseada em Web Services para gerenciamento (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="d677f-116">Session configurations are a feature of Web Services for Management (WS-Management) based PowerShell remoting.</span></span> <span data-ttu-id="d677f-117">Eles são usados somente quando você usa os cmdlets New-PSSession, Invoke-Command ou Enter-PSSession para se conectar a um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d677f-117">They are used only when you use the New-PSSession, Invoke-Command, or Enter-PSSession cmdlets to connect to a remote computer.</span></span>

<span data-ttu-id="d677f-118">Observação: para gerenciar as configurações de sessão, inicie o PowerShell com a opção "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="d677f-118">Note: To manage the session configurations, start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="d677f-119">Sobre as configurações de sessão</span><span class="sxs-lookup"><span data-stu-id="d677f-119">About Session Configurations</span></span>

<span data-ttu-id="d677f-120">Cada sessão do PowerShell usa uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d677f-120">Every PowerShell session uses a session configuration.</span></span> <span data-ttu-id="d677f-121">Isso inclui sessões persistentes que você cria usando os cmdlets New-PSSession ou Enter-PSSession e as sessões temporárias que o PowerShell cria quando você usa o parâmetro ComputerName de um cmdlet que usa a tecnologia de comunicação remota baseada no WS-Management, como Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="d677f-121">This includes persistent sessions that you create by using the New-PSSession or Enter-PSSession cmdlets, and the temporary sessions that PowerShell creates when you use the ComputerName parameter of a cmdlet that uses WS-Management-based remoting technology, such as Invoke-Command.</span></span>

<span data-ttu-id="d677f-122">Os administradores podem usar as configurações de sessão para proteger os recursos do computador e criar ambientes personalizados para os usuários que se conectam ao computador.</span><span class="sxs-lookup"><span data-stu-id="d677f-122">Administrators can use session configurations to protect the resources of the computer and to create custom environments for users who connect to the computer.</span></span> <span data-ttu-id="d677f-123">Por exemplo, você pode usar uma configuração de sessão para limitar o tamanho dos objetos que o computador recebe na sessão, para definir o modo de linguagem da sessão e para especificar os cmdlets, provedores e funções que estão disponíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="d677f-123">For example, you can use a session configuration to limit the size of objects that the computer receives in the session, to define the language mode of the session, and to specify the cmdlets, providers, and functions that are available in the session.</span></span>

<span data-ttu-id="d677f-124">Ao configurar o descritor de segurança de uma configuração de sessão, você determina quem pode usar a configuração de sessão para se conectar ao computador.</span><span class="sxs-lookup"><span data-stu-id="d677f-124">By configuring the security descriptor of a session configuration, you determine who can use the session configuration to connect to the computer.</span></span>
<span data-ttu-id="d677f-125">Os usuários devem ter permissão de execução para uma configuração de sessão para usá-la em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d677f-125">Users must have Execute permission to a session configuration to use it in a session.</span></span> <span data-ttu-id="d677f-126">Se um usuário não tiver as permissões necessárias para usar qualquer uma das configurações de sessão em um computador, o usuário não poderá se conectar ao computador remotamente.</span><span class="sxs-lookup"><span data-stu-id="d677f-126">If a user does not have the required permissions to use any of the session configurations on a computer, the user cannot connect to the computer remotely.</span></span>

<span data-ttu-id="d677f-127">Por padrão, somente os administradores do computador têm permissão para usar as configurações de sessão padrão.</span><span class="sxs-lookup"><span data-stu-id="d677f-127">By default, only Administrators of the computer have permission to use the default session configurations.</span></span> <span data-ttu-id="d677f-128">Porém, você pode alterar os descritores de segurança para permitir que todos, nenhum ou apenas usuários selecionados usem as configurações de sessão no seu computador.</span><span class="sxs-lookup"><span data-stu-id="d677f-128">But, you can change the security descriptors to allow everyone, no one, or only selected users to use the session configurations on your computer.</span></span>

<span data-ttu-id="d677f-129">Configurações de sessão internas</span><span class="sxs-lookup"><span data-stu-id="d677f-129">Built-in Session Configurations</span></span>

<span data-ttu-id="d677f-130">O PowerShell 3,0 inclui configurações de sessão internas chamadas Microsoft. PowerShell e Microsoft. PowerShell. Workflow.</span><span class="sxs-lookup"><span data-stu-id="d677f-130">PowerShell 3.0 includes built-in session configurations named Microsoft.PowerShell and Microsoft.PowerShell.Workflow.</span></span> <span data-ttu-id="d677f-131">Em computadores que executam versões de 64 bits do Windows, o PowerShell também fornece o Microsoft. PowerShell32, uma configuração de sessão de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="d677f-131">On computers running 64-bit versions of Windows, PowerShell also provides Microsoft.PowerShell32, a 32-bit session configuration.</span></span>

<span data-ttu-id="d677f-132">A configuração de sessão do Microsoft. PowerShell é usada para sessões por padrão, ou seja, quando um comando para criar uma sessão não inclui o parâmetro ConfigurationName do cmdlet New-PSSession, Enter-PSSession ou Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="d677f-132">The Microsoft.PowerShell session configuration is used for sessions by default, that is, when a command to create a session does not include the ConfigurationName parameter of the New-PSSession, Enter-PSSession, or Invoke-Command cmdlet.</span></span>

<span data-ttu-id="d677f-133">Os descritores de segurança para as configurações de sessão padrão permitem que somente membros do grupo Administradores no computador local os usem.</span><span class="sxs-lookup"><span data-stu-id="d677f-133">The security descriptors for the default session configurations allow only members of the Administrators group on the local computer to use them.</span></span> <span data-ttu-id="d677f-134">Assim, somente os membros do grupo Administradores podem se conectar ao computador remotamente, a menos que você altere as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="d677f-134">As such, only members of the Administrators group can connect to the computer remotely unless you change the default settings.</span></span>

<span data-ttu-id="d677f-135">Você pode alterar as configurações de sessão padrão usando a variável de preferência $PSSessionConfigurationName.</span><span class="sxs-lookup"><span data-stu-id="d677f-135">You can change the default session configurations by using the $PSSessionConfigurationName preference variable.</span></span> <span data-ttu-id="d677f-136">Para obter mais informações, consulte about_preference_variables.</span><span class="sxs-lookup"><span data-stu-id="d677f-136">For more information, see about_Preference_Variables.</span></span>

<span data-ttu-id="d677f-137">Exibindo configurações de sessão no computador local</span><span class="sxs-lookup"><span data-stu-id="d677f-137">Viewing Session Configurations on the Local Computer</span></span>

<span data-ttu-id="d677f-138">Para obter as configurações de sessão no computador local, use o cmdlet Get-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d677f-138">To get the session configurations on your local computer, use the Get-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="d677f-139">Por exemplo, digite:</span><span class="sxs-lookup"><span data-stu-id="d677f-139">For example, type:</span></span>

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property Name, Permission

Name       : microsoft.powershell
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell.workflow
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell32
Permission : BUILTIN\Administrators AccessAllowed
```

<span data-ttu-id="d677f-140">O objeto de configuração de sessão é expandido no PowerShell 3,0 para exibir as propriedades da configuração de sessão que são configuradas usando um arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d677f-140">The session configuration object is expanded in PowerShell 3.0 to display the properties of the session configuration that are configured by using a session configuration file.</span></span>

<span data-ttu-id="d677f-141">Por exemplo, para ver todas as propriedades de um objeto de configuração de sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="d677f-141">For example, to see all of the properties of a session configuration object, type:</span></span>

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property *
```

<span data-ttu-id="d677f-142">Você também pode usar o provedor WSMan no PowerShell para exibir as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="d677f-142">You can also use the WSMan provider in PowerShell to view session configurations.</span></span> <span data-ttu-id="d677f-143">O provedor WSMan cria uma unidade WSMAN: em sua sessão.</span><span class="sxs-lookup"><span data-stu-id="d677f-143">The WSMan provider creates a WSMAN: drive in your session.</span></span>

<span data-ttu-id="d677f-144">Na unidade WSMAN:, as configurações de sessão estão no nó plugin.</span><span class="sxs-lookup"><span data-stu-id="d677f-144">In the WSMAN: drive, session configurations are in the Plugin node.</span></span> <span data-ttu-id="d677f-145">(Todas as configurações de sessão estão no nó plugin, mas há itens no nó plug-in que não são configurações de sessão.)</span><span class="sxs-lookup"><span data-stu-id="d677f-145">(All session configurations are in the Plugin node, but there are items in the Plugin node that are not session configurations.)</span></span>

<span data-ttu-id="d677f-146">Por exemplo, para exibir as configurações de sessão no computador local, digite:</span><span class="sxs-lookup"><span data-stu-id="d677f-146">For example, to view the session configurations on the local computer, type:</span></span>

```powershell
PS C:> dir wsman:\localhost\plugin\microsoft*

WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

<span data-ttu-id="d677f-147">Exibindo configurações de sessão em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="d677f-147">Viewing Session Configurations on a Remote Computer</span></span>

<span data-ttu-id="d677f-148">Para exibir as configurações de sessão em um computador remoto, use o cmdlet Connect-WSMan para adicionar uma nota para o computador remoto para a unidade WSMAN: no computador local e, em seguida, use a unidade WSMAN: para exibir as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="d677f-148">To view the session configurations on a remote computer, use the Connect-WSMan cmdlet to add a note for the remote computer to the WSMAN: drive on your local computer, and then use the WSMAN: drive to view the session configurations.</span></span>

<span data-ttu-id="d677f-149">Por exemplo, o comando a seguir adiciona um nó para o computador remoto Server01 à unidade WSMAN: no computador local.</span><span class="sxs-lookup"><span data-stu-id="d677f-149">For example, the following command adds a node for the Server01 remote computer to the WSMAN: drive on the local computer.</span></span>

```powershell
PS C:> Connect-WSMan server01.corp.fabrikam.com
```

<span data-ttu-id="d677f-150">Quando o comando for concluído, você poderá navegar até o nó do computador Server01 para exibir as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="d677f-150">When the command is complete, you can navigate to the node for the Server01 computer to view the session configurations.</span></span>

<span data-ttu-id="d677f-151">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d677f-151">For example:</span></span>

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

<span data-ttu-id="d677f-152">Alterando o descritor de segurança de uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="d677f-152">Changing the Security Descriptor of a Session Configuration</span></span>

<span data-ttu-id="d677f-153">No Windows Server 2012 e versões mais recentes do Windows Server, as configurações de sessão internas são habilitadas para usuários remotos por padrão.</span><span class="sxs-lookup"><span data-stu-id="d677f-153">In Windows Server 2012 and newer releases of Windows Server, the built-in session configurations are enabled for remote users by default.</span></span> <span data-ttu-id="d677f-154">Em outras versões com suporte do Windows, você deve alterar os descritores de segurança das configurações de sessão para permitir o acesso remoto.</span><span class="sxs-lookup"><span data-stu-id="d677f-154">In other supported versions of Windows, you must change the security descriptors of the session configurations to allow remote access.</span></span>

<span data-ttu-id="d677f-155">Para habilitar o acesso remoto às configurações de sessão no computador, use o cmdlet Enable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="d677f-155">To enable remote access to the session configurations on the computer, use the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="d677f-156">Esse cmdlet cria duas configurações de sessão:</span><span class="sxs-lookup"><span data-stu-id="d677f-156">This cmdlet creates two session configurations:</span></span>

- <span data-ttu-id="d677f-157">com o nome definido como: "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="d677f-157">with the name defined as: "PowerShell."</span></span> <span data-ttu-id="d677f-158">+ "versão atual do PowerShell"</span><span class="sxs-lookup"><span data-stu-id="d677f-158">+ "current PowerShell version"</span></span>
- <span data-ttu-id="d677f-159">com o nome "PowerShell. 6", não vinculado a nenhuma versão específica do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d677f-159">with name "PowerShell.6", untied to any specific PowerShell version.</span></span>

<span data-ttu-id="d677f-160">Além disso, por padrão, somente os membros do grupo Administradores no computador têm a permissão executar para as configurações de sessão padrão, mas você pode alterar os descritores de segurança nas configurações de sessão padrão e em todas as configurações de sessão que você criar.</span><span class="sxs-lookup"><span data-stu-id="d677f-160">Also, by default, only members of the Administrators group on the computer have Execute permission to the default session configurations, but you can change the security descriptors on the default session configurations and on any session configurations that you create.</span></span>

<span data-ttu-id="d677f-161">Para conceder a outros usuários permissão para se conectar ao computador remotamente, use o cmdlet Set-PSSessionConfiguration para adicionar permissões "executar" para esses usuários aos descritores de segurança das configurações de sessão Microsoft. PowerShell e Microsoft. PowerShell32.</span><span class="sxs-lookup"><span data-stu-id="d677f-161">To give other users permission to connect to the computer remotely, use the Set-PSSessionConfiguration cmdlet to add "Execute" permissions for those users to the security descriptors of the Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span>

<span data-ttu-id="d677f-162">Por exemplo, o comando a seguir abre uma página de propriedades que permite alterar o descritor de segurança para a configuração de sessão padrão do Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d677f-162">For example, the following command opens a property page that lets you change the security descriptor for the Microsoft.PowerShell default session configuration.</span></span>

```powershell
Set-PSSessionConfiguration -name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

<span data-ttu-id="d677f-163">Para negar a permissão Everyone para todas as configurações de sessão no computador, use o cmdlet Disable-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d677f-163">To deny everyone permission to all the session configurations on the computer, use the Disable-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="d677f-164">Por exemplo, o comando a seguir desabilita as configurações de sessão padrão no computador.</span><span class="sxs-lookup"><span data-stu-id="d677f-164">For example, the following command disables the default session configurations on the computer.</span></span>

```powershell
PS C:> Disable-PSSessionConfiguration -Name Microsoft.PowerShell
```

<span data-ttu-id="d677f-165">Para impedir que usuários remotos se conectem ao computador, mas permitir que os usuários locais se conectem, use o cmdlet Disable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="d677f-165">To prevent remote users from connecting to the computer, but allow local users to connect, use the Disable-PSRemoting cmdlet.</span></span> <span data-ttu-id="d677f-166">Disable-PSRemoting adiciona uma entrada "Network_Deny_All" a todas as configurações de sessão no computador.</span><span class="sxs-lookup"><span data-stu-id="d677f-166">Disable-PSRemoting adds a "Network_Deny_All" entry to all session configurations on the computer.</span></span>

```powershell
PS C:> Disable-PSRemoting
```

<span data-ttu-id="d677f-167">Para permitir que usuários remotos usem todas as configurações de sessão no computador, use o cmdlet Enable-PSRemoting ou Enable-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d677f-167">To allow remote users to use all session configurations on the computer, use the Enable-PSRemoting or Enable-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="d677f-168">Por exemplo, o comando a seguir habilita o acesso remoto às configurações de sessão internas.</span><span class="sxs-lookup"><span data-stu-id="d677f-168">For example, the following command enables remote access to the built-in session configurations.</span></span>

```powershell
PS C:> Enable-PSSessionConfiguration -name Microsoft.Power*
```

<span data-ttu-id="d677f-169">Para fazer outras alterações no descritor de segurança de uma configuração de sessão, use o cmdlet Set-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d677f-169">To make other changes to the security descriptor of a session configuration, use the Set-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="d677f-170">Use o parâmetro SecurityDescriptorSDDL para enviar um valor de cadeia de caracteres SDDL.</span><span class="sxs-lookup"><span data-stu-id="d677f-170">Use the SecurityDescriptorSDDL parameter to submit an SDDL string value.</span></span> <span data-ttu-id="d677f-171">Use o parâmetro ShowSecurityDescriptorUI dos para exibir uma folha de propriedades da interface do usuário que ajuda você a criar uma nova SDDL.</span><span class="sxs-lookup"><span data-stu-id="d677f-171">Use the ShowSecurityDescriptorUI parameter to display a user interface property sheet that helps you to create a new SDDL.</span></span>

<span data-ttu-id="d677f-172">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d677f-172">For example:</span></span>

```powershell
Set-PSSessionConfiguration -Name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

<span data-ttu-id="d677f-173">Criando uma nova configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="d677f-173">Creating a New Session Configuration</span></span>

<span data-ttu-id="d677f-174">Para criar uma nova configuração de sessão no computador local, use o cmdlet Register-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d677f-174">To create a new session configuration on the local computer, use the Register-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="d677f-175">Para definir a nova configuração de sessão, você pode usar um assembly C#, um script do PowerShell e os parâmetros do cmdlet Register-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d677f-175">To define the new session configuration, you can use a C# assembly, a PowerShell script, and the parameters of the Register-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="d677f-176">Por exemplo, o comando a seguir cria uma configuração de sessão que é idêntica à configuração de sessão do Microsoft. PowerShell, exceto pelo fato de que ela limita os dados recebidos de um comando remoto para 20 megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="d677f-176">For example, the following command creates a session configuration that is identical the Microsoft.PowerShell session configuration, except that it limits the data received from a remote command to 20 megabytes (MB).</span></span> <span data-ttu-id="d677f-177">(O padrão é 50 MB).</span><span class="sxs-lookup"><span data-stu-id="d677f-177">(The default is 50 MB).</span></span>

```powershell
Register-PSSessionConfiguration -Name NewConfig `
  -MaximumReceivedDataSizePerCommandMB 20
```

<span data-ttu-id="d677f-178">Ao criar uma configuração de sessão, você pode gerenciá-la usando os outros cmdlets de configuração de sessão e ela aparece na unidade WSMAN:.</span><span class="sxs-lookup"><span data-stu-id="d677f-178">When you create a session configuration, you can manage it by using the other session configuration cmdlets, and it appears in the WSMAN: drive.</span></span>

<span data-ttu-id="d677f-179">Para obter mais informações, consulte Register-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d677f-179">For more information, see Register-PSSessionConfiguration.</span></span>

<span data-ttu-id="d677f-180">Removendo uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="d677f-180">Removing a Session Configuration</span></span>

<span data-ttu-id="d677f-181">Para remover uma configuração de sessão do computador local, use o cmdlet Unregister-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d677f-181">To remove a session configuration from the local computer, use the Unregister-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="d677f-182">Por exemplo, o comando a seguir remove a configuração de sessão NewConfig do computador.</span><span class="sxs-lookup"><span data-stu-id="d677f-182">For example, the following command removes the NewConfig session configuration from the computer.</span></span>

```powershell
PS C:> Unregister-PSSessionConfiguration -Name NewConfig
```

<span data-ttu-id="d677f-183">Para obter mais informações, consulte Unregister-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d677f-183">For more information, see Unregister-PSSessionConfiguration.</span></span>

<span data-ttu-id="d677f-184">Restaurando uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="d677f-184">Restoring a Session Configuration</span></span>

<span data-ttu-id="d677f-185">Para restaurar uma configuração de sessão padrão que foi excluída (não registrada) acidentalmente, use o cmdlet Enable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="d677f-185">To restore a default session configuration that was deleted (unregistered) accidentally, use the Enable-PSRemoting cmdlet.</span></span>

<span data-ttu-id="d677f-186">O cmdlet Enable-PSRemoting recria todas as configurações de sessões padrão que não existem no computador.</span><span class="sxs-lookup"><span data-stu-id="d677f-186">The Enable-PSRemoting cmdlet recreates all default sessions configurations that do not exist on the computer.</span></span> <span data-ttu-id="d677f-187">Ele não substitui nem altera os valores de propriedade das configurações de sessão existentes.</span><span class="sxs-lookup"><span data-stu-id="d677f-187">It does not overwrite or change the property values of existing session configurations.</span></span>

<span data-ttu-id="d677f-188">Para restaurar os valores de propriedade originais de uma configuração de sessão padrão, use o Unregister-PSSessionConfiguration para excluir a configuração de sessão e, em seguida, use o cmdlet Enable-PSRemoting para recriá-lo.</span><span class="sxs-lookup"><span data-stu-id="d677f-188">To restore the original property values of a default session configuration, use the Unregister-PSSessionConfiguration to delete the session configuration and then use the Enable-PSRemoting cmdlet to recreate it.</span></span>

<span data-ttu-id="d677f-189">Selecionando uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="d677f-189">Selecting a Session Configuration</span></span>

<span data-ttu-id="d677f-190">Para selecionar uma configuração de sessão específica para uma sessão, use o parâmetro ConfigurationName de New-PSSession, Enter-PSSession ou Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="d677f-190">To select a particular session configuration for a session, use the ConfigurationName parameter of New-PSSession, Enter-PSSession, or Invoke-Command.</span></span>

<span data-ttu-id="d677f-191">Por exemplo, esse comando usa o cmdlet New-PSSession para iniciar uma PSSession no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="d677f-191">For example, this command uses the New-PSSession cmdlet to start a PSSession on the Server01 computer.</span></span> <span data-ttu-id="d677f-192">O comando usa o parâmetro ConfigurationName para selecionar a configuração WithProfile no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="d677f-192">The command uses the ConfigurationName parameter to select the WithProfile configuration on the Server01 computer.</span></span>

```powershell
PS C:> New-PSSession -ComputerName Server01 -ConfigurationName WithProfile
```

<span data-ttu-id="d677f-193">Esse comando só terá sucesso se o usuário atual tiver permissão para usar a configuração de sessão WithProfile ou puder fornecer as credenciais de um usuário que tem as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="d677f-193">This command will succeed only if the current user has permission to use the WithProfile session configuration or can supply the credentials of a user who has the required permissions.</span></span>

<span data-ttu-id="d677f-194">Você também pode usar a variável de preferência $PSSessionConfigurationName para alterar a configuração de sessão padrão no computador.</span><span class="sxs-lookup"><span data-stu-id="d677f-194">You can also use the $PSSessionConfigurationName preference variable to change the default session configuration on the computer.</span></span> <span data-ttu-id="d677f-195">Para obter mais informações sobre a variável de preferência $PSSessionConfigurationName, consulte about_Preference_Variables.</span><span class="sxs-lookup"><span data-stu-id="d677f-195">For more information about the $PSSessionConfigurationName preference variable, see about_Preference_Variables.</span></span>

## <a name="keywords"></a><span data-ttu-id="d677f-196">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="d677f-196">KEYWORDS</span></span>

<span data-ttu-id="d677f-197">about_Endpoints about_SessionConfigurations</span><span class="sxs-lookup"><span data-stu-id="d677f-197">about_Endpoints about_SessionConfigurations</span></span>

## <a name="see-also"></a><span data-ttu-id="d677f-198">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="d677f-198">SEE ALSO</span></span>

[<span data-ttu-id="d677f-199">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="d677f-199">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="d677f-200">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="d677f-200">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="d677f-201">about_Remote</span><span class="sxs-lookup"><span data-stu-id="d677f-201">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="d677f-202">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="d677f-202">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)

[<span data-ttu-id="d677f-203">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="d677f-203">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="d677f-204">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d677f-204">Disable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[<span data-ttu-id="d677f-205">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d677f-205">Enable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[<span data-ttu-id="d677f-206">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d677f-206">Get-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[<span data-ttu-id="d677f-207">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="d677f-207">New-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[<span data-ttu-id="d677f-208">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d677f-208">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[<span data-ttu-id="d677f-209">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d677f-209">Set-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[<span data-ttu-id="d677f-210">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="d677f-210">Test-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[<span data-ttu-id="d677f-211">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d677f-211">Unregister-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)

