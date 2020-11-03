---
description: Descreve as configurações de Política de Grupo do PowerShell
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_group_policy_settings?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Group_Policy_Settings
ms.openlocfilehash: df2a3e9349dd3afbe621bd11b92ac5cdf552492a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195559"
---
# <a name="about-group-policy-settings"></a><span data-ttu-id="c98c5-104">Sobre configurações de Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="c98c5-104">About Group Policy Settings</span></span>

## <a name="short-description"></a><span data-ttu-id="c98c5-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="c98c5-105">Short description</span></span>
<span data-ttu-id="c98c5-106">Descreve as configurações de Política de Grupo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c98c5-106">Describes the Group Policy settings for PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="c98c5-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="c98c5-107">Long description</span></span>

<span data-ttu-id="c98c5-108">O PowerShell inclui Política de Grupo configurações para ajudá-lo a definir valores de configuração consistentes para computadores Windows em um ambiente empresarial.</span><span class="sxs-lookup"><span data-stu-id="c98c5-108">PowerShell includes Group Policy settings to help you define consistent configuration values for Windows computers in an enterprise environment.</span></span>

<span data-ttu-id="c98c5-109">As configurações de Política de Grupo do PowerShell estão nos seguintes caminhos de Política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="c98c5-109">The PowerShell Group Policy settings are in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    PowerShell Core

User Configuration\
  Administrative Templates\
    PowerShell Core
```

<span data-ttu-id="c98c5-110">As configurações de política de grupo no caminho de configuração do usuário têm precedência sobre Política de Grupo configurações no caminho de configuração do computador.</span><span class="sxs-lookup"><span data-stu-id="c98c5-110">Group policy settings in the User Configuration path take precedence over Group Policy settings in the Computer Configuration path.</span></span>

<span data-ttu-id="c98c5-111">O PowerShell 7 inclui modelos de Política de Grupo e um script de instalação em `$PSHOME`.</span><span class="sxs-lookup"><span data-stu-id="c98c5-111">PowerShell 7 includes Group Policy templates and an installation script in `$PSHOME`.</span></span>

<span data-ttu-id="c98c5-112">As ferramentas de Política de Grupo usam arquivos de modelos administrativos (`.admx`, `.adml`) para preencher as configurações de políticas na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="c98c5-112">Group Policy tools use administrative template files (`.admx`, `.adml`) to populate policy settings in the user interface.</span></span> <span data-ttu-id="c98c5-113">Assim, os administradores podem gerenciar as configurações de políticas com base no registro.</span><span class="sxs-lookup"><span data-stu-id="c98c5-113">This allows administrators to manage registry-based policy settings.</span></span> <span data-ttu-id="c98c5-114">O `InstallPSCorePolicyDefinitions.ps1` script instala o **PowerShell Core modelos administrativos** no computador local.</span><span class="sxs-lookup"><span data-stu-id="c98c5-114">The `InstallPSCorePolicyDefinitions.ps1` script installs **PowerShell Core Administrative Templates** on the local machine.</span></span>

```powershell
Get-ChildItem -Path $PSHOME -Filter *Core*Policy*
```

```Output
    Directory: C:\Program Files\PowerShell\7

Mode       LastWriteTime         Length Name
----       -------------         ------ ----
-a---      2/27/2020 12:38 AM     15861 InstallPSCorePolicyDefinitions.ps1
-a---      2/27/2020 12:28 AM      9675 PowerShellCoreExecutionPolicy.adml
-a---      2/27/2020 12:28 AM      6201 PowerShellCoreExecutionPolicy.admx
```

<span data-ttu-id="c98c5-115">Depois de instalar os modelos, você pode editar essas configurações no editor de Política de Grupo ( `gpedit.msc` ).</span><span class="sxs-lookup"><span data-stu-id="c98c5-115">After installing the templates, you can edit these settings in the Group Policy editor (`gpedit.msc`).</span></span>

<span data-ttu-id="c98c5-116">As políticas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="c98c5-116">The policies are as follows:</span></span>

- <span data-ttu-id="c98c5-117">Configuração de sessão do console: define um ponto de extremidade de configuração em que o PowerShell é executado.</span><span class="sxs-lookup"><span data-stu-id="c98c5-117">Console session configuration: Sets a configuration endpoint in which PowerShell is run.</span></span>
- <span data-ttu-id="c98c5-118">Ativar registro em log de módulo: define a propriedade **LogPipelineExecutionDetails** de módulos.</span><span class="sxs-lookup"><span data-stu-id="c98c5-118">Turn on Module Logging: Sets the **LogPipelineExecutionDetails** property of modules.</span></span>
- <span data-ttu-id="c98c5-119">Ativar o Registro em Log de Blocos de Script do PowerShell: ativa o registro em log detalhado de todos os scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c98c5-119">Turn on PowerShell Script Block Logging: Enables detailed logging of all PowerShell scripts.</span></span>
- <span data-ttu-id="c98c5-120">Ativar a Execução do Script: define a política de execução do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c98c5-120">Turn on Script Execution: Sets the PowerShell execution policy.</span></span>
- <span data-ttu-id="c98c5-121">Ativar a Transcrição do PowerShell: ativa a captura de entradas e saídas dos comandos do PowerShell como transcrições baseadas em texto.</span><span class="sxs-lookup"><span data-stu-id="c98c5-121">Turn on PowerShell Transcription: enables capturing of input and output of PowerShell commands into text-based transcripts.</span></span>
- <span data-ttu-id="c98c5-122">Definir o caminho de origem padrão para `Update-Help` : define a fonte para a ajuda atualizável para um diretório, não para a Internet.</span><span class="sxs-lookup"><span data-stu-id="c98c5-122">Set the default source path for `Update-Help`: Sets the source for Updatable Help to a directory, not the Internet.</span></span>

<span data-ttu-id="c98c5-123">Cada configuração de Política de Grupo do PowerShell tem uma opção (' Use o campo configuração de política do Windows PowerShell ') para usar o valor de uma configuração semelhante do Windows PowerShell Política de Grupo que está localizada nos seguintes caminhos de Política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="c98c5-123">Each PowerShell Group Policy setting has an option ('Use Windows PowerShell Policy setting' field) to use the value from a similar Windows PowerShell Group Policy setting that is located in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

> [!NOTE]
> <span data-ttu-id="c98c5-124">Essas **modelos administrativos do PowerShell Core** não incluem configurações para o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c98c5-124">These **PowerShell Core Administrative Templates** do not include settings for Windows PowerShell.</span></span> <span data-ttu-id="c98c5-125">Para obter mais informações sobre como adquirir outros modelos e configurar a política de grupo, consulte [como criar e gerenciar o armazenamento central para Política de Grupo modelos administrativos no Windows][gpstore].</span><span class="sxs-lookup"><span data-stu-id="c98c5-125">For more information about acquiring other templates and configuring Group policy, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows][gpstore].</span></span>

## <a name="console-session-configuration"></a><span data-ttu-id="c98c5-126">Configuração de sessão do console</span><span class="sxs-lookup"><span data-stu-id="c98c5-126">Console session configuration</span></span>

<span data-ttu-id="c98c5-127">A configuração de política de **configuração de sessão de console** especifica um ponto de extremidade de configuração no qual o PowerShell é executado.</span><span class="sxs-lookup"><span data-stu-id="c98c5-127">The **Console session configuration** policy setting specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="c98c5-128">Pode ser qualquer ponto de extremidade registrado no computador local, incluindo os pontos de extremidade remotos de comunicação remota do PowerShell ou um ponto de extremidades personalizado com recursos de função de usuário específicos.</span><span class="sxs-lookup"><span data-stu-id="c98c5-128">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

## <a name="turn-on-module-logging"></a><span data-ttu-id="c98c5-129">Ativar o registro em log de módulo</span><span class="sxs-lookup"><span data-stu-id="c98c5-129">Turn on module logging</span></span>

<span data-ttu-id="c98c5-130">A configuração ativar política de **log de módulo** ativa o registro em log para os módulos selecionados do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c98c5-130">The **Turn on Module Logging** policy setting turns on logging for selected PowerShell modules.</span></span> <span data-ttu-id="c98c5-131">A configuração é eficaz em todas as sessões em todos os computadores afetados.</span><span class="sxs-lookup"><span data-stu-id="c98c5-131">The setting is effective in all sessions on all affected computers.</span></span>

<span data-ttu-id="c98c5-132">Se você habilitar essa configuração de política e especificar um ou mais módulos, os eventos de execução de pipeline para os módulos especificados serão registrados no log do Windows PowerShell em Visualizador de Eventos.</span><span class="sxs-lookup"><span data-stu-id="c98c5-132">If you enable this policy setting and specify one or more modules, pipeline execution events for the specified modules are recorded in the Windows PowerShell log in Event Viewer.</span></span>

<span data-ttu-id="c98c5-133">Se você desabilitar essa configuração de política, o log de eventos de execução será desabilitado para todos os módulos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c98c5-133">If you disable this policy setting, logging of execution events is disabled for all PowerShell modules.</span></span>

<span data-ttu-id="c98c5-134">Se essa configuração de política não estiver configurada, a propriedade **LogPipelineExecutionDetails** de cada módulo determinará se os eventos de execução de um módulo são registrados.</span><span class="sxs-lookup"><span data-stu-id="c98c5-134">If this policy setting is not configured, the **LogPipelineExecutionDetails** property of each module determines whether the execution events of a module are logged.</span></span> <span data-ttu-id="c98c5-135">Por padrão, a propriedade **LogPipelineExecutionDetails** de todos os módulos é definida como false.</span><span class="sxs-lookup"><span data-stu-id="c98c5-135">By default, the **LogPipelineExecutionDetails** property of all modules is set to False.</span></span>

<span data-ttu-id="c98c5-136">Para ativar o log de módulo para um módulo, use o seguinte formato de comando.</span><span class="sxs-lookup"><span data-stu-id="c98c5-136">To turn on module logging for a module, use the following command format.</span></span> <span data-ttu-id="c98c5-137">O módulo deve ser importado para a sessão e a configuração só é eficaz na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="c98c5-137">The module must be imported into the session and the setting is effective only in the current session.</span></span>

```powershell
Import-Module <Module-Name>
(Get-Module <Module-Name>).LogPipelineExecutionDetails = $true
```

<span data-ttu-id="c98c5-138">Para ativar o log de módulo para todas as sessões em um computador específico, adicione os comandos anteriores ao perfil do PowerShell ' todos os usuários ' ( `$Profile.AllUsersAllHosts` ).</span><span class="sxs-lookup"><span data-stu-id="c98c5-138">To turn on module logging for all sessions on a particular computer, add the previous commands to the 'All Users' PowerShell profile (`$Profile.AllUsersAllHosts`).</span></span>

<span data-ttu-id="c98c5-139">Para obter mais informações sobre o log de módulo, consulte [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="c98c5-139">For more information about module logging, see [about_Modules](about_Modules.md).</span></span>

## <a name="turn-on-powershell-script-block-logging"></a><span data-ttu-id="c98c5-140">Ativar o log de bloco de script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c98c5-140">Turn on PowerShell script block logging</span></span>

<span data-ttu-id="c98c5-141">A configuração de política **Ativar log de bloco de script do PowerShell** habilita o log de todas as entradas de script do PowerShell para o log de eventos Microsoft-Windows-PowerShell/Operational.</span><span class="sxs-lookup"><span data-stu-id="c98c5-141">The **Turn on PowerShell Script Block Logging** policy setting enables logging of all PowerShell script input to the Microsoft-Windows-PowerShell/Operational event log.</span></span> <span data-ttu-id="c98c5-142">Se você habilitar essa configuração de política, o PowerShell Core registrará em log o processamento de comandos, blocos de script, funções e scripts – sejam invocados interativamente ou através da automação.</span><span class="sxs-lookup"><span data-stu-id="c98c5-142">If you enable this policy setting, PowerShell Core will log the processing of commands, script blocks, functions, and scripts - whether invoked interactively, or through automation.</span></span>

<span data-ttu-id="c98c5-143">Se você desabilitar essa configuração de política, o registro em log da entrada de script do PowerShell será desabilitado.</span><span class="sxs-lookup"><span data-stu-id="c98c5-143">If you disable this policy setting, logging of PowerShell script input is disabled.</span></span> <span data-ttu-id="c98c5-144">Se você habilitar o registro em log da invocação do bloco de script, o PowerShell registrará eventos adicionalmente quando a invocação de um comando, um bloco de script, uma função ou um script for iniciada ou interrompida.</span><span class="sxs-lookup"><span data-stu-id="c98c5-144">If you enable the Script Block Invocation Logging, PowerShell additionally logs events when invocation of a command, script block, function, or script starts or stops.</span></span> <span data-ttu-id="c98c5-145">Habilitar o registro em log de invocação gera um alto volume de logs de eventos.</span><span class="sxs-lookup"><span data-stu-id="c98c5-145">Enabling Invocation Logging generates a high volume of event logs.</span></span>

## <a name="turn-on-script-execution"></a><span data-ttu-id="c98c5-146">Ativar a execução do script</span><span class="sxs-lookup"><span data-stu-id="c98c5-146">Turn on script execution</span></span>

<span data-ttu-id="c98c5-147">A configuração ativar política de **execução de script** define a política de execução para computadores e usuários, que determina quais scripts podem ser executados.</span><span class="sxs-lookup"><span data-stu-id="c98c5-147">The **Turn on Script Execution** policy setting sets the execution policy for computers and users, which determines which scripts are permitted to run.</span></span>

<span data-ttu-id="c98c5-148">Se você habilitar a configuração de política, poderá selecionar entre as seguintes configurações de política.</span><span class="sxs-lookup"><span data-stu-id="c98c5-148">If you enable the policy setting, you can select from among the following policy settings.</span></span>

- <span data-ttu-id="c98c5-149">**Permitir somente scripts assinados** permite que os scripts sejam executados somente se forem assinados por um fornecedor confiável.</span><span class="sxs-lookup"><span data-stu-id="c98c5-149">**Allow only signed scripts** allows scripts to execute only if they are signed by a trusted publisher.</span></span> <span data-ttu-id="c98c5-150">Essa configuração de política é equivalente à política de execução AllSigned.</span><span class="sxs-lookup"><span data-stu-id="c98c5-150">This policy setting is equivalent to the AllSigned execution policy.</span></span>

- <span data-ttu-id="c98c5-151">**Permitir scripts locais e scripts remotos assinados** permite que todos os scripts locais sejam executados.</span><span class="sxs-lookup"><span data-stu-id="c98c5-151">**Allow local scripts and remote signed scripts** allows all local scripts to run.</span></span> <span data-ttu-id="c98c5-152">Os scripts originados na Internet devem ser assinados por um fornecedor confiável.</span><span class="sxs-lookup"><span data-stu-id="c98c5-152">Scripts that originate from the Internet must be signed by a trusted publisher.</span></span> <span data-ttu-id="c98c5-153">Essa configuração de política é equivalente à política de execução RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="c98c5-153">This policy setting is equivalent to the RemoteSigned execution policy.</span></span>

- <span data-ttu-id="c98c5-154">**Permitir todos os scripts** permite a execução de todos os scripts.</span><span class="sxs-lookup"><span data-stu-id="c98c5-154">**Allow all scripts** allows all scripts to run.</span></span> <span data-ttu-id="c98c5-155">Essa configuração de política é equivalente à política de execução irrestrita.</span><span class="sxs-lookup"><span data-stu-id="c98c5-155">This policy setting is equivalent to the Unrestricted execution policy.</span></span>

<span data-ttu-id="c98c5-156">Se você desabilitar essa configuração de política, nenhum script poderá ser executado.</span><span class="sxs-lookup"><span data-stu-id="c98c5-156">If you disable this policy setting, no scripts are allowed to run.</span></span> <span data-ttu-id="c98c5-157">Essa configuração de política é equivalente à política de execução restrita.</span><span class="sxs-lookup"><span data-stu-id="c98c5-157">This policy setting is equivalent to the Restricted execution policy.</span></span>

<span data-ttu-id="c98c5-158">Se você desabilitar ou não definir essa configuração de política, a política de execução definida para o computador ou usuário pelo `Set-ExecutionPolicy` cmdlet determinará se os scripts têm permissão para serem executados.</span><span class="sxs-lookup"><span data-stu-id="c98c5-158">If you disable or do not configure this policy setting, the execution policy that is set for the computer or user by the `Set-ExecutionPolicy` cmdlet determines whether scripts are permitted to run.</span></span> <span data-ttu-id="c98c5-159">O valor padrão é Restricted.</span><span class="sxs-lookup"><span data-stu-id="c98c5-159">The default value is Restricted.</span></span>

<span data-ttu-id="c98c5-160">Para obter mais informações, consulte [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="c98c5-160">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

## <a name="turn-on-powershell-transcription"></a><span data-ttu-id="c98c5-161">Ativar transcrição do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c98c5-161">Turn on powershell transcription</span></span>

<span data-ttu-id="c98c5-162">A configuração da política **Ativar transcrição do PowerShell** permite capturar a entrada e a saída de comandos do PowerShell Core em transcrições baseadas em texto.</span><span class="sxs-lookup"><span data-stu-id="c98c5-162">The **Turn on PowerShell Transcription** policy setting lets you capture the input and output of PowerShell Core commands into text-based transcripts.</span></span> <span data-ttu-id="c98c5-163">Se você habilitar essa configuração de política, o PowerShell Core habilitará o log de transcrição para o PowerShell Core e quaisquer outros aplicativos que utilizem o mecanismo do PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="c98c5-163">If you enable this policy setting, PowerShell Core will enable transcription logging for PowerShell Core and any other applications that leverage the PowerShell Core engine.</span></span> <span data-ttu-id="c98c5-164">Por padrão, o PowerShell Core registrará a saída da transcrição no diretório meus documentos de cada usuário, com um nome de arquivo que inclui ' PowerShell_transcript ', junto com o nome do computador e a hora de início.</span><span class="sxs-lookup"><span data-stu-id="c98c5-164">By default, PowerShell Core will record transcript output to each users' My Documents directory, with a file name that includes 'PowerShell_transcript', along with the computer name and time started.</span></span>
<span data-ttu-id="c98c5-165">Habilitar essa política é equivalente a chamar o cmdlet Start-Transcript em cada sessão do PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="c98c5-165">Enabling this policy is equivalent to calling the Start-Transcript cmdlet on each PowerShell Core session.</span></span>

<span data-ttu-id="c98c5-166">Se você desabilitar essa configuração de política, o log de transcrição de aplicativos baseados no PowerShell será desabilitado por padrão, embora a transcrição ainda possa ser habilitada por meio do cmdlet Start-Transcript.</span><span class="sxs-lookup"><span data-stu-id="c98c5-166">If you disable this policy setting, transcription logging of PowerShell-based applications is disabled by default, although transcripting can still be enabled through the Start-Transcript cmdlet.</span></span>

<span data-ttu-id="c98c5-167">Se você usar a configuração OutputDirectory para habilitar o registro em log de transcrição para um local compartilhado, certifique-se de limitar o acesso a esse diretório para impedir que os usuários exibam as transcrições de outros usuários ou computadores.</span><span class="sxs-lookup"><span data-stu-id="c98c5-167">If you use the OutputDirectory setting to enable transcription logging to a shared location, be sure to limit access to that directory to prevent users from viewing the transcripts of other users or computers.</span></span>

## <a name="set-the-default-source-path-for-update-help"></a><span data-ttu-id="c98c5-168">Defina o caminho de origem padrão para Update-Help</span><span class="sxs-lookup"><span data-stu-id="c98c5-168">Set the default source path for Update-Help</span></span>

<span data-ttu-id="c98c5-169">A configuração **definir o caminho de origem padrão para a política de atualização-ajuda** define um valor padrão para o parâmetro **SourcePath** do `Update-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c98c5-169">The **Set the Default Source Path for Update-Help** policy setting sets a default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span>
<span data-ttu-id="c98c5-170">Essa configuração impede que os usuários usem o `Update-Help` cmdlet para baixar arquivos de ajuda da Internet.</span><span class="sxs-lookup"><span data-stu-id="c98c5-170">This setting prevents users from using the `Update-Help` cmdlet to download help files from the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="c98c5-171">Essa configuração de Política de Grupo aparece em **configuração do computador** e configuração do **usuário** .</span><span class="sxs-lookup"><span data-stu-id="c98c5-171">This Group Policy setting appears under **Computer Configuration** and **User Configuration** .</span></span> <span data-ttu-id="c98c5-172">No entanto, somente a configuração Política de Grupo em **configuração do computador** é eficaz.</span><span class="sxs-lookup"><span data-stu-id="c98c5-172">However, only the Group Policy setting under **Computer Configuration** is effective.</span></span> <span data-ttu-id="c98c5-173">A configuração Política de Grupo em **configuração do usuário** é ignorada.</span><span class="sxs-lookup"><span data-stu-id="c98c5-173">The Group Policy setting under **User Configuration** is ignored.</span></span>

<span data-ttu-id="c98c5-174">O `Update-Help` cmdlet baixa e instala os arquivos de ajuda mais recentes para os módulos do PowerShell e os instala no computador.</span><span class="sxs-lookup"><span data-stu-id="c98c5-174">The `Update-Help` cmdlet downloads and installs the newest help files for PowerShell modules and installs them on the computer.</span></span> <span data-ttu-id="c98c5-175">Por padrão, `Update-Help` o baixa novos arquivos de ajuda de um local de Internet especificado pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="c98c5-175">By default, `Update-Help` downloads new help files from an Internet location specified by the module.</span></span>

<span data-ttu-id="c98c5-176">No entanto, você pode usar o `Save-Help` cmdlet para baixar os arquivos de ajuda mais recentes para um local do sistema de arquivos, como um compartilhamento de rede e, em seguida, usar o `Update-Help` cmdlet para obter os arquivos de ajuda do local do sistema de arquivos e instalá-los no computador.</span><span class="sxs-lookup"><span data-stu-id="c98c5-176">However, you can use the `Save-Help` cmdlet to download the newest help files to a file system location, such as a network share, and then use the `Update-Help` cmdlet to get the help files from the file system location and install them on the computer.</span></span> <span data-ttu-id="c98c5-177">O parâmetro **SourcePath** do `Update-Help` cmdlet especifica o local do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c98c5-177">The **SourcePath** parameter of the `Update-Help` cmdlet specifies the file system location.</span></span>

<span data-ttu-id="c98c5-178">Ao fornecer um valor padrão para o parâmetro **SourcePath** , essa configuração de política de grupo adiciona implicitamente o parâmetro **SourcePath** a todos os `Update-Help` comandos.</span><span class="sxs-lookup"><span data-stu-id="c98c5-178">By providing a default value for the **SourcePath** parameter, this Group Policy setting implicitly adds the **SourcePath** parameter to all `Update-Help` commands.</span></span> <span data-ttu-id="c98c5-179">Os usuários podem substituir o local do sistema de arquivos específico especificado como o valor padrão inserindo um local diferente do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c98c5-179">Users can override the particular file system location specified as the default value by entering a different file system location.</span></span>
<span data-ttu-id="c98c5-180">Mas não podem remover o parâmetro **SourcePath** do `Update-Help` comando.</span><span class="sxs-lookup"><span data-stu-id="c98c5-180">But they cannot remove the **SourcePath** parameter from the `Update-Help` command.</span></span>

<span data-ttu-id="c98c5-181">Se você habilitar essa configuração de política, poderá especificar um valor padrão para o parâmetro **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="c98c5-181">If you enable this policy setting, you can specify a default value for the **SourcePath** parameter.</span></span> <span data-ttu-id="c98c5-182">Insira um local do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c98c5-182">Enter a file system location.</span></span>

<span data-ttu-id="c98c5-183">Se essa configuração de política estiver desabilitada ou não estiver configurada, não haverá valor padrão para o parâmetro **SourcePath** do `Update-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c98c5-183">If this policy setting is disabled or not configured, there is no default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span> <span data-ttu-id="c98c5-184">Os usuários podem baixar a ajuda da Internet ou de qualquer local do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c98c5-184">Users can download help from the Internet or from any file system location.</span></span>

<span data-ttu-id="c98c5-185">Para obter mais informações, consulte [about_Updatable_Help](about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="c98c5-185">For more information, see [about_Updatable_Help](about_Updatable_Help.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="c98c5-186">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="c98c5-186">Keywords</span></span>

<span data-ttu-id="c98c5-187">about_Group_Policies about_GroupPolicy</span><span class="sxs-lookup"><span data-stu-id="c98c5-187">about_Group_Policies about_GroupPolicy</span></span>

## <a name="see-also"></a><span data-ttu-id="c98c5-188">Confira também</span><span class="sxs-lookup"><span data-stu-id="c98c5-188">See also</span></span>

[<span data-ttu-id="c98c5-189">RFC da política do PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="c98c5-189">PowerShell Core Policy RFC</span></span>](https://github.com/PowerShell/PowerShell-RFC/blob/master/4-Experimental-Accepted/RFC0041-Policy.md)

[<span data-ttu-id="c98c5-190">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="c98c5-190">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="c98c5-191">about_Modules</span><span class="sxs-lookup"><span data-stu-id="c98c5-191">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="c98c5-192">about_Updatable_Help</span><span class="sxs-lookup"><span data-stu-id="c98c5-192">about_Updatable_Help</span></span>](about_Updatable_Help.md)

[<span data-ttu-id="c98c5-193">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="c98c5-193">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="c98c5-194">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="c98c5-194">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="c98c5-195">Get-Module</span><span class="sxs-lookup"><span data-stu-id="c98c5-195">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="c98c5-196">Update-Help</span><span class="sxs-lookup"><span data-stu-id="c98c5-196">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)

[<span data-ttu-id="c98c5-197">Save-Help</span><span class="sxs-lookup"><span data-stu-id="c98c5-197">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

<!-- link references -->
[gpstore]: https://support.microsoft.com/help/3087759

