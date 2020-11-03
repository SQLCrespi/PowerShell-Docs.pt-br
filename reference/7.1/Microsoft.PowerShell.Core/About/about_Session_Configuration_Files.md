---
description: Descreve os arquivos de configuração de sessão, que são usados em uma configuração de sessão (também conhecida como "ponto de extremidade") para definir o ambiente de sessões que usam a configuração de sessão.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configuration_files?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configuration_Files
ms.openlocfilehash: 45c8a6e0ba8478e0a49cb287cd4311d7556a42ea
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195544"
---
# <a name="about-session-configuration-files"></a><span data-ttu-id="1a619-104">Sobre arquivos de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="1a619-104">About Session Configuration Files</span></span>

## <a name="short-description"></a><span data-ttu-id="1a619-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="1a619-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="1a619-106">Descreve os arquivos de configuração de sessão, que são usados em uma configuração de sessão (também conhecida como "ponto de extremidade") para definir o ambiente de sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-106">Describes session configuration files, which are used in a session configuration (also known as an "endpoint") to define the environment of sessions that use the session configuration.</span></span>

## <a name="long-description"></a><span data-ttu-id="1a619-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="1a619-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="1a619-108">Um "arquivo de configuração de sessão" é um arquivo de texto com uma extensão de nome de arquivo. PSSC que contém uma tabela de hash de valores e propriedades de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-108">A "session configuration file" is a text file with a .pssc file name extension that contains a hash table of session configuration properties and values.</span></span> <span data-ttu-id="1a619-109">Você pode usar um arquivo de configuração de sessão para definir as propriedades de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-109">You can use a session configuration file to set the properties of a session configuration.</span></span> <span data-ttu-id="1a619-110">Isso define o ambiente de todas as sessões do PowerShell que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-110">Doing so defines the environment of any PowerShell sessions that use that session configuration.</span></span>

<span data-ttu-id="1a619-111">Os arquivos de configuração de sessão facilitam a criação de configurações de sessão personalizadas sem usar módulos ou scripts C# complexos.</span><span class="sxs-lookup"><span data-stu-id="1a619-111">Session configuration files make it easy to create custom session configurations without using complex C# assemblies or scripts.</span></span>

<span data-ttu-id="1a619-112">Uma "configuração de sessão" ou "ponto de extremidade" é uma coleção de configurações do computador local que determinam coisas como quais usuários podem criar sessões no computador; quais comandos os usuários podem executar nessas sessões; e se a sessão deve ser executada como uma conta virtual privilegiada.</span><span class="sxs-lookup"><span data-stu-id="1a619-112">A "session configuration" or "endpoint" is a collection of local computer settings that determine such things as which users can create sessions on the computer; which commands users can run in those sessions; and whether the session should run as a privileged virtual account.</span></span> <span data-ttu-id="1a619-113">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="1a619-113">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

<span data-ttu-id="1a619-114">As configurações de sessão foram introduzidas no Windows PowerShell 2,0, e os arquivos de configuração de sessão foram introduzidos no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="1a619-114">Session configurations were introduced in Windows PowerShell 2.0, and session configuration files were introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="1a619-115">Você deve usar o Windows PowerShell 3,0 para incluir um arquivo de configuração de sessão em uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-115">You must use Windows PowerShell 3.0 to include a session configuration file in a session configuration.</span></span> <span data-ttu-id="1a619-116">No entanto, os usuários do Windows PowerShell 2,0 (e posterior) são afetados pelas configurações na configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-116">However, users of Windows PowerShell 2.0 (and later) are affected by the settings in the session configuration.</span></span>

## <a name="creating-custom-sessions"></a><span data-ttu-id="1a619-117">Criando sessões personalizadas</span><span class="sxs-lookup"><span data-stu-id="1a619-117">Creating Custom Sessions</span></span>

<span data-ttu-id="1a619-118">Você pode personalizar muitos recursos de uma sessão do PowerShell especificando propriedades de sessão em uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-118">You can customize many features of a PowerShell session by specifying session properties in a session configuration.</span></span> <span data-ttu-id="1a619-119">Você pode personalizar uma sessão escrevendo um programa em C# que define um runspace personalizado ou pode usar um arquivo de configuração de sessão para definir as propriedades das sessões criadas usando a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-119">You can customize a session by writing a C# program that defines a custom runspace, or you can use a session configuration file to define the properties of sessions created by using the session configuration.</span></span> <span data-ttu-id="1a619-120">Como regra geral, é mais fácil usar o arquivo de configuração de sessão do que escrever um programa em C#.</span><span class="sxs-lookup"><span data-stu-id="1a619-120">As a general rule, it is easier to use the session configuration file than to write a C# program.</span></span>

<span data-ttu-id="1a619-121">Você pode usar um arquivo de configuração de sessão para criar itens como sessões totalmente funcionais para usuários altamente confiáveis; sessões bloqueadas que permitem o acesso mínimo; sessões projetadas para particular e que contêm apenas os módulos necessários para essas tarefas; e sessões em que os usuários sem privilégios só podem executar comandos específicos como uma conta com privilégios.</span><span class="sxs-lookup"><span data-stu-id="1a619-121">You can use a session configuration file to create items such as fully-functioning sessions for highly trusted users; locked-down sessions that allow minimal access; sessions designed for particular and that contain only the modules required for those tasks; and sessions where unprivileged users can only run specific commands as a privileged account.</span></span>

<span data-ttu-id="1a619-122">Além disso, você pode gerenciar se os usuários da sessão podem usar elementos de linguagem do PowerShell, como blocos de script, ou se eles só podem executar comandos.</span><span class="sxs-lookup"><span data-stu-id="1a619-122">In addition to that, you can manage whether users of the session can use PowerShell language elements such as script blocks, or whether they can only run commands.</span></span> <span data-ttu-id="1a619-123">Você pode gerenciar a versão dos usuários do PowerShell que podem ser executados na sessão; gerenciar quais módulos são importados para a sessão; e gerenciar quais cmdlets, funções e aliases de sessão os usuários podem executar.</span><span class="sxs-lookup"><span data-stu-id="1a619-123">You can manage the version of PowerShell users can run in the session; manage which modules are imported into the session; and manage which cmdlets, functions, and aliases session users can run.</span></span> <span data-ttu-id="1a619-124">Ao usar o campo RoleDefinitions, você pode fornecer aos usuários recursos diferentes na sessão com base na associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="1a619-124">When using the RoleDefinitions field, you can give users different capabilities in the session based on group membership.</span></span>

<span data-ttu-id="1a619-125">Para obter mais informações sobre RoleDefinitions e como definir esse valor, consulte o tópico da ajuda para o cmdlet New-PSRoleCapabilityFile.</span><span class="sxs-lookup"><span data-stu-id="1a619-125">For more information about RoleDefinitions and how to define this Value, see the help topic for the New-PSRoleCapabilityFile Cmdlet.</span></span>

## <a name="creating-a-session-configuration-file"></a><span data-ttu-id="1a619-126">Criando um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="1a619-126">Creating a Session Configuration File</span></span>

<span data-ttu-id="1a619-127">A maneira mais fácil de criar um arquivo de configuração de sessão é usando o cmdlet New-PSSessionConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="1a619-127">The easiest way to create a session configuration file is by using the New-PSSessionConfigurationFile cmdlet.</span></span> <span data-ttu-id="1a619-128">Esse cmdlet gera um arquivo que usa a sintaxe e o formato corretos e que verifica automaticamente muitos dos valores de Propriedade do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="1a619-128">This cmdlet generates a file that uses the correct syntax and format, and that automatically verifies many of the configuration file property values.</span></span>

<span data-ttu-id="1a619-129">Para obter descrições detalhadas das propriedades que podem ser definidas em um arquivo de configuração de sessão, consulte o tópico da ajuda para o cmdlet New-PSSessionConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="1a619-129">For detailed descriptions of the properties that you can set in a session configuration file, see the help topic for the New-PSSessionConfigurationFile cmdlet.</span></span>

<span data-ttu-id="1a619-130">O comando a seguir cria um arquivo de configuração de sessão que usa os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="1a619-130">The following command creates a session configuration file that uses the default values.</span></span> <span data-ttu-id="1a619-131">O arquivo de configuração resultante usa apenas os valores padrão porque nenhum parâmetro diferente do parâmetro de caminho (que especifica o caminho do arquivo) está incluído:</span><span class="sxs-lookup"><span data-stu-id="1a619-131">The resulting configuration file uses only the default values because no parameters other than the Path parameter (which specifies the file path) are included:</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\Defaults.pssc
```

<span data-ttu-id="1a619-132">Para exibir o novo arquivo de configuração em seu editor de texto padrão, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="1a619-132">To view the new configuration file in your default text editor, use the following command:</span></span>

```powershell
Invoke-Item -Path .\Defaults.pssc
```

<span data-ttu-id="1a619-133">Para criar uma configuração de sessão para sessões em que o usuário pode executar comandos, mas não usar outros elementos da linguagem PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="1a619-133">To create a session configuration for sessions in which user can run commands, but not use other elements of the PowerShell language, type:</span></span>

```powershell
New-PSSessionConfigurationFile -LanguageMode NoLanguage
-Path .\NoLanguage.pssc
```

<span data-ttu-id="1a619-134">No comando anterior, definir o parâmetro Languagemode como nolanguage impede que os usuários façam coisas como gravar ou executar scripts ou usar variáveis.</span><span class="sxs-lookup"><span data-stu-id="1a619-134">In the preceding command, setting the LanguageMode parameter to NoLanguage prevents users from doing such things as writing or running scripts, or using variables.</span></span>

<span data-ttu-id="1a619-135">Para criar uma configuração de sessão para sessões nas quais os usuários podem usar apenas cmdlets Get, digite:</span><span class="sxs-lookup"><span data-stu-id="1a619-135">To create a session configuration for sessions in which users can use only Get cmdlets, type:</span></span>

```powershell
New-PSSessionConfigurationFile -VisibleCmdlets Get-*
-Path .\GetSessions.pssc
```

<span data-ttu-id="1a619-136">No exemplo anterior, definir o parâmetro VisibleCmdlets como Get-\* limita os usuários aos cmdlets que têm nomes que começam com o valor de cadeia de caracteres "Get-".</span><span class="sxs-lookup"><span data-stu-id="1a619-136">In the preceding example, setting the VisibleCmdlets parameter to Get-\* limits users to cmdlets that have names that start with the string value "Get-".</span></span>

<span data-ttu-id="1a619-137">Para criar uma configuração de sessão para sessões executadas em uma conta virtual privilegiada em vez das credenciais do usuário, digite:</span><span class="sxs-lookup"><span data-stu-id="1a619-137">To create a session configuration for sessions that run under a privileged virtual account instead of the user's credentials, type:</span></span>

```powershell
New-PSSessionConfigurationFile -RunAsVirtualAccount
-Path .\VirtualAccount.pssc
```

<span data-ttu-id="1a619-138">Para criar uma configuração de sessão para sessões em que os comandos visíveis para o usuário são especificados em um arquivo de recursos de função, digite:</span><span class="sxs-lookup"><span data-stu-id="1a619-138">To create a session configuration for sessions in which the commands visible to the user are specified in a role capabilities file, type:</span></span>

```powershell
New-PSSessionConfigurationFile -RoleDefinitions
@{ 'CONTOSO\User' = @{ RoleCapabilities = 'Maintenance' }}
-Path .\Maintenance.pssc
```

### <a name="using-a-session-configuration-file"></a><span data-ttu-id="1a619-139">Usando um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="1a619-139">Using a Session Configuration File</span></span>

<span data-ttu-id="1a619-140">Você pode incluir um arquivo de configuração de sessão ao criar uma configuração de sessão ou adicionar. você pode adicionar um arquivo à configuração de sessão posteriormente.</span><span class="sxs-lookup"><span data-stu-id="1a619-140">You can include a session configuration file when you create a session configuration or add you can add a file to the session configuration at a later time.</span></span>

<span data-ttu-id="1a619-141">Para incluir um arquivo de configuração de sessão ao criar uma configuração de sessão, use o parâmetro Path do cmdlet Register-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="1a619-141">To include a session configuration file when creating a session configuration, use the Path parameter of the Register-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="1a619-142">Por exemplo, o comando a seguir usa o arquivo nolanguage. PSSC quando ele cria uma configuração de sessão nolanguage.</span><span class="sxs-lookup"><span data-stu-id="1a619-142">For example, the following command uses the NoLanguage.pssc file when it creates a NoLanguage session configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name NoLanguage
-Path .\NoLanguage.pssc
```

<span data-ttu-id="1a619-143">Quando uma nova sessão nolanguage for iniciada, os usuários só terão acesso aos comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a619-143">When a new NoLanguage session starts, users will only have access to PowerShell commands.</span></span>

<span data-ttu-id="1a619-144">Para adicionar um arquivo de configuração de sessão a uma configuração de sessão existente, use o cmdlet Set-PSSessionConfiguration e o parâmetro Path.</span><span class="sxs-lookup"><span data-stu-id="1a619-144">To add a session configuration file to an existing session configuration, use the Set-PSSessionConfiguration cmdlet and the Path parameter.</span></span> <span data-ttu-id="1a619-145">Isso afeta todas as novas sessões criadas com a configuração de sessão especificada.</span><span class="sxs-lookup"><span data-stu-id="1a619-145">This affects any new sessions created with the specified session configuration.</span></span> <span data-ttu-id="1a619-146">Observe que o cmdlet Set-PSSessionConfiguration altera a sessão em si e não modifica o arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-146">Note that the Set-PSSessionConfiguration cmdlet changes the session itself and does not modify the session configuration file.</span></span>

<span data-ttu-id="1a619-147">Por exemplo, o comando a seguir adiciona o arquivo nolanguage. PSSC à configuração de sessão LockedDown.</span><span class="sxs-lookup"><span data-stu-id="1a619-147">For example, the following command adds the NoLanguage.pssc file to the LockedDown session configuration.</span></span>

```powershell
Set-PSSessionConfiguration -Name LockedDown
-Path .\NoLanguage.pssc
```

<span data-ttu-id="1a619-148">Quando os usuários usam a configuração de sessão LockedDown para criar uma sessão, eles poderão executar cmdlets, mas não poderão criar ou usar variáveis, atribuir valores ou usar outros elementos de linguagem do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a619-148">When users use the LockedDown session configuration to create a session, they will be able to run cmdlets but they will not be able to create or use variables, assign values, or use other PowerShell language elements.</span></span>

<span data-ttu-id="1a619-149">O comando a seguir usa o cmdlet New-PSSession para criar uma sessão no computador Srv01 que usa a configuração de sessão LockedDown, salvando uma referência de objeto na sessão na variável $s.</span><span class="sxs-lookup"><span data-stu-id="1a619-149">The following command uses the New-PSSession cmdlet to create a session on the computer Srv01 that uses the LockedDown session configuration, saving an object reference to the session in the $s variable.</span></span> <span data-ttu-id="1a619-150">A ACL (lista de controle de acesso) da configuração de sessão determina quem pode usá-la para criar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-150">The ACL (access control list) of the session configuration determines who can use it to create a session.</span></span>

```powershell
$s = New-PSSession -ComputerName Srv01
-ConfigurationName LockedDown
```

<span data-ttu-id="1a619-151">Como as restrições nolanguage foram adicionadas à configuração de sessão do LockedDown, os usuários em sessões do LockedDown só poderão executar os comandos e cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a619-151">Because the NoLanguage constraints were added to the LockedDown session configuration, users in LockedDown sessions will only be able to run PowerShell commands and cmdlets.</span></span> <span data-ttu-id="1a619-152">Por exemplo, os dois comandos a seguir usam o cmdlet Invoke-Command para executar comandos na sessão referenciada na variável $s.</span><span class="sxs-lookup"><span data-stu-id="1a619-152">For example, the following two commands use the Invoke-Command cmdlet to run commands in the session referenced in the $s variable.</span></span> <span data-ttu-id="1a619-153">O primeiro comando, que executa o cmdlet Get-UICulture e não usa nenhuma variável, é bem sucedido.</span><span class="sxs-lookup"><span data-stu-id="1a619-153">The first command, which runs the Get-UICulture cmdlet and does not use any variables, succeeds.</span></span> <span data-ttu-id="1a619-154">O segundo comando, que obtém o valor da variável $PSUICulture, falha.</span><span class="sxs-lookup"><span data-stu-id="1a619-154">The second command, which gets the value of the $PSUICulture variable, fails.</span></span>

```
Invoke-Command -Session $s {Get-UICulture}
en-US

Invoke-Command -Session $s {$PSUICulture}
The syntax is not supported by this runspace. This might be
because it is in no-language mode.
+ CategoryInfo          : ParserError: ($PSUICulture:String) [],
ParseException
+ FullyQualifiedErrorId : ScriptsNotAllowed
```

## <a name="editing-a-session-configuration-file"></a><span data-ttu-id="1a619-155">Editando um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="1a619-155">Editing a Session Configuration File</span></span>

<span data-ttu-id="1a619-156">Todas as configurações em uma configuração de sessão, exceto para RunAsVirtualAccount e RunAsVirtualAccountGroups, podem ser modificadas editando o arquivo de configuração de sessão usado pela configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-156">All settings in a session configuration except for RunAsVirtualAccount and RunAsVirtualAccountGroups can be modified by editing the session configuration file used by the session configuration.</span></span> <span data-ttu-id="1a619-157">Para fazer isso, comece localizando a cópia ativa do arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-157">To do this, begin by locating the active copy of the session configuration file.</span></span>

<span data-ttu-id="1a619-158">Quando você usa um arquivo de configuração de sessão em uma configuração de sessão, o PowerShell cria uma cópia ativa do arquivo de configuração de sessão e a armazena no \$ \\ diretório pshome SessionConfig no computador local.</span><span class="sxs-lookup"><span data-stu-id="1a619-158">When you use a session configuration file in a session configuration, PowerShell creates an active copy of the session configuration file and stores it in the \$pshome\\SessionConfig directory on the local computer.</span></span>

<span data-ttu-id="1a619-159">O local da cópia ativa de um arquivo de configuração de sessão é armazenado na propriedade ConfigFilePath do objeto de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-159">The location of the active copy of a session configuration file is stored in the ConfigFilePath property of the session configuration object.</span></span>

<span data-ttu-id="1a619-160">O comando a seguir obtém o local do arquivo de configuração de sessão para a configuração da sessão nolanguage.</span><span class="sxs-lookup"><span data-stu-id="1a619-160">The following command gets the location of the session configuration file for the NoLanguage session configuration.</span></span>

```powershell
(Get-PSSessionConfiguration -Name NoLanguage).ConfigFilePath
```

<span data-ttu-id="1a619-161">Esse comando retorna um caminho de arquivo semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="1a619-161">That command returns a file path similar to the following:</span></span>

```
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

<span data-ttu-id="1a619-162">Você pode editar o arquivo. PSSC em qualquer editor de texto.</span><span class="sxs-lookup"><span data-stu-id="1a619-162">You can edit the .pssc file in any text editor.</span></span> <span data-ttu-id="1a619-163">Depois que o arquivo for salvo, ele será empregado por novas sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-163">After the file is saved it will be employed by any new sessions that use the session configuration.</span></span>

<span data-ttu-id="1a619-164">Se precisar modificar as configurações de RunAsVirtualAccount ou RunAsVirtualAccountGroups, você deverá cancelar o registro da configuração de sessão e registrar novamente um arquivo de configuração de sessão que inclui os valores editados.</span><span class="sxs-lookup"><span data-stu-id="1a619-164">If you need to modify the RunAsVirtualAccount or the RunAsVirtualAccountGroups settings, you must un-register the session configuration and re-register a session configuration file that includes the edited values.</span></span>

## <a name="testing-a-session-configuration-file"></a><span data-ttu-id="1a619-165">Testando um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="1a619-165">Testing a Session Configuration File</span></span>

<span data-ttu-id="1a619-166">Use o cmdlet Test-PSSessionConfigurationFile para testar arquivos de configuração de sessão editados manualmente.</span><span class="sxs-lookup"><span data-stu-id="1a619-166">Use the Test-PSSessionConfigurationFile cmdlet to test manually edited session configuration files.</span></span> <span data-ttu-id="1a619-167">Isso é importante: se a sintaxe do arquivo e os valores não forem válidos, os usuários não poderão usar a configuração de sessão para criar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-167">That's important: if the file syntax and values are not valid users will not be able to use the session configuration to create a session.</span></span>

<span data-ttu-id="1a619-168">Por exemplo, o comando a seguir testa o arquivo de configuração de sessão ativa da configuração de sessão nolanguage.</span><span class="sxs-lookup"><span data-stu-id="1a619-168">For example, the following command tests the active session configuration file of the NoLanguage session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path C:\WINDOWS\System32\
WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

<span data-ttu-id="1a619-169">Se a sintaxe e os valores no arquivo de configuração forem válidos Test-PSSessionConfigurationFile retornará true.</span><span class="sxs-lookup"><span data-stu-id="1a619-169">If the syntax and values in the configuration file are valid Test-PSSessionConfigurationFile returns True.</span></span> <span data-ttu-id="1a619-170">Se a sintaxe e os valores não forem válidos, o cmdlet retornará false.</span><span class="sxs-lookup"><span data-stu-id="1a619-170">If the syntax and values are not valid then the cmdlet returns False.</span></span>

<span data-ttu-id="1a619-171">Você pode usar Test-PSSessionConfigurationFile para testar qualquer arquivo de configuração de sessão, incluindo os arquivos que o cmdlet New-PSSessionConfiguration cria.</span><span class="sxs-lookup"><span data-stu-id="1a619-171">You can use Test-PSSessionConfigurationFile to test any session configuration file, including files that the New-PSSessionConfiguration cmdlet creates.</span></span> <span data-ttu-id="1a619-172">Para obter mais informações, consulte o tópico da ajuda para o cmdlet Test-PSSessionConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="1a619-172">For more information, see the help topic for the Test-PSSessionConfigurationFile cmdlet.</span></span>

## <a name="removing-a-session-configuration-file"></a><span data-ttu-id="1a619-173">Removendo um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="1a619-173">Removing a Session Configuration File</span></span>

<span data-ttu-id="1a619-174">Não é possível remover um arquivo de configuração de sessão de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-174">You cannot remove a session configuration file from a session configuration.</span></span>
<span data-ttu-id="1a619-175">No entanto, você pode substituir o arquivo por um novo arquivo que usa as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="1a619-175">However, you can replace the file with a new file that uses the default settings.</span></span> <span data-ttu-id="1a619-176">Isso efetivamente cancela as configurações usadas pelo arquivo de configuração original.</span><span class="sxs-lookup"><span data-stu-id="1a619-176">This effectively cancels the settings used by the original configuration file.</span></span>

<span data-ttu-id="1a619-177">Para substituir um arquivo de configuração de sessão, crie um novo arquivo de configuração de sessão que use as configurações padrão e, em seguida, use o cmdlet Set-PSSessionConfiguration para substituir o arquivo de configuração de sessão Personalizada pelo novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="1a619-177">To replace a session configuration file, create a new session configuration file that uses the default settings, then use the Set-PSSessionConfiguration cmdlet to replace the custom session configuration file with the new file.</span></span>

<span data-ttu-id="1a619-178">Por exemplo, os comandos a seguir criam um arquivo de configuração de sessão padrão e substituem o arquivo de configuração de sessão ativa na configuração de sessão nolanguage.</span><span class="sxs-lookup"><span data-stu-id="1a619-178">For example, the following commands create a Default session configuration file and then replace the active session configuration file in the NoLanguage session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\Default.pssc
Set-PSSessionConfiguration -Name NoLanguage
-Path .\Default.pssc
```

<span data-ttu-id="1a619-179">Quando esses comandos forem concluídos, a configuração da sessão nolanguage realmente fornecerá suporte completo a idiomas (a configuração padrão) para todas as sessões criadas com essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-179">When these commands finish, the NoLanguage session configuration will actually provide full language support (the default setting) for all sessions created with that session configuration.</span></span>

<span data-ttu-id="1a619-180">Exibindo as propriedades de uma configuração de sessão os objetos de configuração de sessão que representam as configurações de sessão usando arquivos de configuração de sessão têm propriedades adicionais que facilitam a descoberta e a análise da configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="1a619-180">Viewing the Properties of a Session Configuration The session configuration objects that represent session configurations using session configuration files have additional properties that make it easy to discover and analyze the session configuration.</span></span> <span data-ttu-id="1a619-181">(Observe que o nome do tipo mostrado abaixo inclui uma definição de exibição formatada.) Você pode exibir as propriedades executando o cmdlet Get-PSSessionConfiguration e canalizando os dados retornados para o cmdlet Get-Member:</span><span class="sxs-lookup"><span data-stu-id="1a619-181">(Note that the type name shown below includes a formatted view definition.) You can view the properties by running the Get-PSSessionConfiguration cmdlet and piping the returned data to the Get-Member cmdlet:</span></span>

```powershell
Get-PSSessionConfiguration NoLanguage | Get-Member
```

```output
TypeName: Microsoft.PowerShell.Commands.PSSessionConfigurationCommands
#PSSessionConfiguration

Name                          MemberType     Definition
----                          ----------     ----------
Equals                        Method         bool Equals(System.O...
GetHashCode                   Method         int GetHashCode()
GetType                       Method         type GetType()
ToString                      Method         string ToString()
Architecture                  NoteProperty   System.String Archit...
Author                        NoteProperty   System.String Author...
AutoRestart                   NoteProperty   System.String AutoRe...
Capability                    NoteProperty   System.Object[] Capa...
CompanyName                   NoteProperty   System.String Compan...
configfilepath                NoteProperty   System.String config...
Copyright                     NoteProperty   System.String Copyri...
Enabled                       NoteProperty   System.String Enable...
ExactMatch                    NoteProperty   System.String ExactM...
ExecutionPolicy               NoteProperty   System.String Execut...
Filename                      NoteProperty   System.String Filena...
GUID                          NoteProperty   System.String GUID=0...
ProcessIdleTimeoutSec         NoteProperty   System.String Proces...
IdleTimeoutms                 NoteProperty   System.String IdleTi...
lang                          NoteProperty   System.String lang=e...
LanguageMode                  NoteProperty   System.String Langua...
MaxConcurrentCommandsPerShell NoteProperty   System.String MaxCon...
MaxConcurrentUsers            NoteProperty   System.String MaxCon...
MaxIdleTimeoutms              NoteProperty   System.String MaxIdl...
MaxMemoryPerShellMB           NoteProperty   System.String MaxMem...
MaxProcessesPerShell          NoteProperty   System.String MaxPro...
MaxShells                     NoteProperty   System.String MaxShells
MaxShellsPerUser              NoteProperty   System.String MaxShe...
Name                          NoteProperty   System.String Name=N...
PSVersion                     NoteProperty   System.String PSVersion
ResourceUri                   NoteProperty   System.String Resour...
RunAsPassword                 NoteProperty   System.String RunAsP...
RunAsUser                     NoteProperty   System.String RunAsUser
SchemaVersion                 NoteProperty   System.String Schema...
SDKVersion                    NoteProperty   System.String SDKVer...
OutputBufferingMode           NoteProperty   System.String Output...
SessionType                   NoteProperty   System.String Sessio...
UseSharedProcess              NoteProperty   System.String UseSha...
SupportsOptions               NoteProperty   System.String Suppor...
xmlns                         NoteProperty   System.String xmlns=...
XmlRenderingType              NoteProperty   System.String XmlRen...
Permission                    ScriptProperty System.Object Permis...
```

<span data-ttu-id="1a619-182">Essas propriedades facilitam a pesquisa de configurações de sessão específicas.</span><span class="sxs-lookup"><span data-stu-id="1a619-182">These properties make it easy to search for specific session configurations.</span></span>
<span data-ttu-id="1a619-183">Por exemplo, você pode usar a propriedade ExecutionPolicy para encontrar uma configuração de sessão que dê suporte a sessões com a política de execução RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="1a619-183">For example, you can use the ExecutionPolicy property to find a session configuration that supports sessions with the RemoteSigned execution policy.</span></span>
<span data-ttu-id="1a619-184">Observe que, como a propriedade ExecutionPolicy existe somente em sessões que usam arquivos de configuração de sessão, o comando pode não retornar todas as configurações de sessão qualificadas.</span><span class="sxs-lookup"><span data-stu-id="1a619-184">Note that, because the ExecutionPolicy property exists only on sessions that use session configuration files, the command might not return all qualifying session configurations.</span></span>

```powershell
Get-PSSessionConfiguration |
where {$_.ExecutionPolicy -eq "RemoteSigned"}
```

<span data-ttu-id="1a619-185">O comando a seguir obtém as configurações de sessão nas quais RunAsUser é o administrador do Exchange.</span><span class="sxs-lookup"><span data-stu-id="1a619-185">The following command gets session configurations in which the RunAsUser is the Exchange administrator.</span></span>

```powershell
 Get-PSSessionConfiguration |
where {$_.RunAsUser -eq "Exchange01\Admin01"}
```

<span data-ttu-id="1a619-186">Para exibir informações sobre as definições de função associadas a uma configuração, use o cmdlet Get-PSSessionCapability.</span><span class="sxs-lookup"><span data-stu-id="1a619-186">To view information about the role definitions associated with a configuration use the Get-PSSessionCapability cmdlet.</span></span> <span data-ttu-id="1a619-187">Esse cmdlet permite que você determine os comandos e o ambiente disponíveis para usuários específicos em pontos de extremidade específicos.</span><span class="sxs-lookup"><span data-stu-id="1a619-187">This cmdlet enables you to determine the commands and environment available to specific users in specific endpoints.</span></span>

## <a name="notes"></a><span data-ttu-id="1a619-188">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1a619-188">NOTES</span></span>

<span data-ttu-id="1a619-189">As configurações de sessão também dão suporte a um tipo de sessão conhecido como uma sessão "vazia".</span><span class="sxs-lookup"><span data-stu-id="1a619-189">Session configurations also support a type of session known as an "empty" session.</span></span> <span data-ttu-id="1a619-190">Um tipo de sessão vazia permite que você crie sessões personalizadas com os comandos selecionados.</span><span class="sxs-lookup"><span data-stu-id="1a619-190">An Empty session type enables you to create custom sessions with selected commands.</span></span> <span data-ttu-id="1a619-191">Se você não adicionar módulos, funções ou scripts a uma sessão vazia, a sessão será limitada a expressões e talvez não seja de uso prático.</span><span class="sxs-lookup"><span data-stu-id="1a619-191">If you do not add modules, functions, or scripts to an empty session, the session is limited to expressions and might not be of any practical use.</span></span> <span data-ttu-id="1a619-192">A propriedade SessionType informa se você está trabalhando ou não com uma sessão vazia.</span><span class="sxs-lookup"><span data-stu-id="1a619-192">The SessionType property tells you whether or not you are working with an empty session.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a619-193">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="1a619-193">SEE ALSO</span></span>

[<span data-ttu-id="1a619-194">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="1a619-194">about_Session_Configurations</span></span>](about_Session_Configurations.md)

[<span data-ttu-id="1a619-195">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="1a619-195">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="1a619-196">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a619-196">Disable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[<span data-ttu-id="1a619-197">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a619-197">Enable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[<span data-ttu-id="1a619-198">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a619-198">Get-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[<span data-ttu-id="1a619-199">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="1a619-199">New-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[<span data-ttu-id="1a619-200">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a619-200">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[<span data-ttu-id="1a619-201">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a619-201">Set-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[<span data-ttu-id="1a619-202">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="1a619-202">Test-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[<span data-ttu-id="1a619-203">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a619-203">Unregister-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)

[<span data-ttu-id="1a619-204">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="1a619-204">Get-PSSessionCapability</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionCapability)

[<span data-ttu-id="1a619-205">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="1a619-205">New-PSRoleCapabilityFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSRoleCapabilityFile)

