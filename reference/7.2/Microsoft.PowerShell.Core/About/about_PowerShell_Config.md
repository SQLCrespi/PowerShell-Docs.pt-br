---
description: Arquivos de configuração do PowerShell Core, substituindo a configuração do registro.
Locale: en-US
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Config
ms.openlocfilehash: 7190484832958e778a21e6d2cc91771587bffdbf
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595374"
---
# <a name="about-powershell-config"></a><span data-ttu-id="31418-103">Sobre a configuração do PowerShell</span><span class="sxs-lookup"><span data-stu-id="31418-103">About PowerShell Config</span></span>

## <a name="short-description"></a><span data-ttu-id="31418-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="31418-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="31418-105">Arquivos de configuração do PowerShell Core, substituindo a configuração do registro.</span><span class="sxs-lookup"><span data-stu-id="31418-105">Configuration files for PowerShell Core, replacing Registry configuration.</span></span>

## <a name="long-description"></a><span data-ttu-id="31418-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="31418-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="31418-107">O `powershell.config.json` arquivo contém definições de configuração para o PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="31418-107">The `powershell.config.json` file contains configuration settings for PowerShell Core.</span></span> <span data-ttu-id="31418-108">O PowerShell carrega essa configuração na inicialização.</span><span class="sxs-lookup"><span data-stu-id="31418-108">PowerShell loads this configuration at startup.</span></span> <span data-ttu-id="31418-109">As configurações também podem ser modificadas em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="31418-109">The settings can also be modified at runtime.</span></span> <span data-ttu-id="31418-110">Anteriormente, essas configurações eram armazenadas no registro do Windows para o PowerShell, mas agora estão contidas em um arquivo para habilitar a configuração no macOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="31418-110">Previously, these settings were stored in the Windows Registry for PowerShell, but are now contained in a file to enable configuration on macOS and Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="31418-111">Se o `powershell.config.json` arquivo contiver um PowerShell JSON inválido não poderá iniciar uma sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="31418-111">If the `powershell.config.json` file contains invalid JSON PowerShell cannot start an interactive session.</span></span>
> <span data-ttu-id="31418-112">Se isso ocorrer, você deverá corrigir o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="31418-112">If this occurs, you must fix the configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="31418-113">Chaves não reconhecidas ou valores inválidos no arquivo de configuração serão ignorados silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="31418-113">Unrecognized keys or invalid values in the configuration file will be silently ignored.</span></span>

### <a name="allusers-shared-configuration"></a><span data-ttu-id="31418-114">Configuração de AllUsers (compartilhado)</span><span class="sxs-lookup"><span data-stu-id="31418-114">AllUsers (shared) configuration</span></span>

<span data-ttu-id="31418-115">Um `powershell.config.json` arquivo no `$PSHOME` diretório define a configuração para todas as sessões do PowerShell Core em execução a partir da instalação do PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="31418-115">A `powershell.config.json` file in the `$PSHOME` directory defines the configuration for all PowerShell Core sessions running from that PowerShell Core installation.</span></span>

> [!NOTE]
> <span data-ttu-id="31418-116">O `$PSHOME` local é definido como o mesmo diretório que o assembly de System.Management.Automation.dll em execução.</span><span class="sxs-lookup"><span data-stu-id="31418-116">The `$PSHOME` location is defined as the same directory as the executing System.Management.Automation.dll assembly.</span></span> <span data-ttu-id="31418-117">Isso se aplica a instâncias do SDK do PowerShell hospedadas também.</span><span class="sxs-lookup"><span data-stu-id="31418-117">This applies to hosted PowerShell SDK instances as well.</span></span>

### <a name="currentuser-per-user-configurations"></a><span data-ttu-id="31418-118">Configurações CurrentUser (por usuário)</span><span class="sxs-lookup"><span data-stu-id="31418-118">CurrentUser (per-user) configurations</span></span>

<span data-ttu-id="31418-119">Você também pode configurar o PowerShell em uma base por usuário colocando o arquivo no diretório de configuração de escopo do usuário.</span><span class="sxs-lookup"><span data-stu-id="31418-119">You can also configure PowerShell on a per-user basis by placing the file in the user-scope configuration directory.</span></span> <span data-ttu-id="31418-120">O diretório de configuração do usuário pode ser encontrado em várias plataformas com o comando `Split-Path $PROFILE.CurrentUserCurrentHost` .</span><span class="sxs-lookup"><span data-stu-id="31418-120">The user configuration directory can be found across platforms with the command `Split-Path $PROFILE.CurrentUserCurrentHost`.</span></span>

## <a name="general-configuration-settings"></a><span data-ttu-id="31418-121">Definições de configuração geral</span><span class="sxs-lookup"><span data-stu-id="31418-121">General configuration settings</span></span>

### <a name="executionpolicy"></a><span data-ttu-id="31418-122">ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="31418-122">ExecutionPolicy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31418-123">Essa configuração se aplica somente a plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="31418-123">This configuration only applies on Windows platforms.</span></span>

<span data-ttu-id="31418-124">Configura a política de execução para sessões do PowerShell, determinando quais scripts podem ser executados.</span><span class="sxs-lookup"><span data-stu-id="31418-124">Configures the execution policy for PowerShell sessions, determining what scripts can be run.</span></span> <span data-ttu-id="31418-125">Por padrão, o PowerShell usa a política de execução existente.</span><span class="sxs-lookup"><span data-stu-id="31418-125">By default, PowerShell uses the existing execution policy.</span></span>

<span data-ttu-id="31418-126">Para configurações AllUsers, isso define a política de execução **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="31418-126">For AllUsers configurations, this sets the **LocalMachine** execution policy.</span></span>
<span data-ttu-id="31418-127">Para configurações CurrentUser, isso define a política de execução **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="31418-127">For CurrentUser configurations, this sets the **CurrentUser** execution policy.</span></span>

> [!NOTE]
> <span data-ttu-id="31418-128">O [`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy) cmdlet modifica essa configuração no arquivo de configuração AllUsers quando invocado com `-Scope LocalMachine` o e modifica essa configuração no arquivo de configuração CurrentUser quando invocado com `-Scope CurrentUser` .</span><span class="sxs-lookup"><span data-stu-id="31418-128">The [`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy) cmdlet modifies this setting in the AllUsers configuration file when invoked with `-Scope LocalMachine`, and modifies this setting in the CurrentUser configuration file when invoked with `-Scope CurrentUser`.</span></span>

```Schema
"<shell-id>:ExecutionPolicy": "<execution-policy>"
```

<span data-ttu-id="31418-129">Em que:</span><span class="sxs-lookup"><span data-stu-id="31418-129">Where:</span></span>

- <span data-ttu-id="31418-130">`<shell-id>` refere-se à ID do host do PowerShell atual.</span><span class="sxs-lookup"><span data-stu-id="31418-130">`<shell-id>` refers to the ID of the current PowerShell host.</span></span>
  <span data-ttu-id="31418-131">Para o PowerShell Core normal, isso é `Microsoft.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="31418-131">For normal PowerShell Core, this is `Microsoft.PowerShell`.</span></span>
  <span data-ttu-id="31418-132">Em qualquer sessão do PowerShell, você pode descobri-lo com o `$ShellId` .</span><span class="sxs-lookup"><span data-stu-id="31418-132">In any PowerShell session, you can discover it with `$ShellId`.</span></span>
- <span data-ttu-id="31418-133">`<execution-policy>` refere-se a um nome de política de execução válido.</span><span class="sxs-lookup"><span data-stu-id="31418-133">`<execution-policy>` refers to a valid execution policy name.</span></span>

<span data-ttu-id="31418-134">O exemplo a seguir define a política de execução do PowerShell para `RemoteSigned` .</span><span class="sxs-lookup"><span data-stu-id="31418-134">The following example sets the execution policy of PowerShell to `RemoteSigned`.</span></span>

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "RemoteSigned"
}
```

<span data-ttu-id="31418-135">No Windows, as chaves de registro equivalentes podem ser encontradas em `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` em `HKEY_LOCAL_MACHINE` e `HKEY_CURRENT_USER` .</span><span class="sxs-lookup"><span data-stu-id="31418-135">In Windows, the equivalent registry keys can be found in `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` under `HKEY_LOCAL_MACHINE` and `HKEY_CURRENT_USER`.</span></span>

### <a name="psmodulepath"></a><span data-ttu-id="31418-136">PSModulePath</span><span class="sxs-lookup"><span data-stu-id="31418-136">PSModulePath</span></span>

<span data-ttu-id="31418-137">Substitui um componente PSModulePath para esta sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31418-137">Overrides a PSModulePath component for this PowerShell session.</span></span> <span data-ttu-id="31418-138">Se a configuração for para o usuário atual, define o caminho do módulo CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="31418-138">If the configuration is for the current user, sets the CurrentUser module path.</span></span> <span data-ttu-id="31418-139">Se a configuração for para todos os usuários, define o caminho do módulo do usuário.</span><span class="sxs-lookup"><span data-stu-id="31418-139">If the configuration is for all users, sets the AllUser module path.</span></span>

> [!WARNING]
> <span data-ttu-id="31418-140">Configurar um caminho de módulo AllUsers ou CurrentUser aqui não alterará o local de instalação com escopo para módulos do PowerShellGet [, como install-Module](/powershell/module/powershellget/install-module).</span><span class="sxs-lookup"><span data-stu-id="31418-140">Configuring an AllUsers or CurrentUser module path here will not change the scoped installation location for PowerShellGet modules like [Install-Module](/powershell/module/powershellget/install-module).</span></span>
> <span data-ttu-id="31418-141">Esses cmdlets sempre usam os caminhos de módulo *padrão* .</span><span class="sxs-lookup"><span data-stu-id="31418-141">These cmdlets always use the *default* module paths.</span></span>

<span data-ttu-id="31418-142">Se nenhum valor for definido, o valor padrão do respectivo componente de caminho do módulo será usado.</span><span class="sxs-lookup"><span data-stu-id="31418-142">If no value is set, the default value for the respective module path component will be used.</span></span> <span data-ttu-id="31418-143">Consulte [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) para obter mais detalhes sobre esses padrões.</span><span class="sxs-lookup"><span data-stu-id="31418-143">See [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) for more details on these defaults.</span></span>

<span data-ttu-id="31418-144">Essa configuração permite que as variáveis de ambiente sejam usadas inserindo-as entre `%` caracteres, como `"%HOME%\Documents\PowerShell\Modules"` , da mesma maneira que o cmd permite.</span><span class="sxs-lookup"><span data-stu-id="31418-144">This setting allows environment variables to be used by embedding them between `%` characters, like `"%HOME%\Documents\PowerShell\Modules"`, in the same way as CMD allows.</span></span> <span data-ttu-id="31418-145">Essa sintaxe também se aplica ao Linux e ao macOS.</span><span class="sxs-lookup"><span data-stu-id="31418-145">This syntax also applies on Linux and macOS.</span></span> <span data-ttu-id="31418-146">Consulte abaixo para obter exemplos.</span><span class="sxs-lookup"><span data-stu-id="31418-146">See below for examples.</span></span>

```Schema
"PSModulePath": "<ps-module-path>"
```

<span data-ttu-id="31418-147">Em que:</span><span class="sxs-lookup"><span data-stu-id="31418-147">Where:</span></span>

- <span data-ttu-id="31418-148">`<ps-module-path>` é o caminho absoluto para um diretório de módulo.</span><span class="sxs-lookup"><span data-stu-id="31418-148">`<ps-module-path>` is the absolute path to a module directory.</span></span> <span data-ttu-id="31418-149">Para todas as configurações de usuário, esse é o diretório de módulo compartilhado AllUsers.</span><span class="sxs-lookup"><span data-stu-id="31418-149">For all user configurations, this is the AllUsers shared module directory.</span></span> <span data-ttu-id="31418-150">Para as configurações de usuário atuais, este é o diretório de módulo CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="31418-150">For current user configurations, this is CurrentUser module directory.</span></span>

<span data-ttu-id="31418-151">Este exemplo mostra uma configuração de PSModulePath para um ambiente do Windows:</span><span class="sxs-lookup"><span data-stu-id="31418-151">This example shows a PSModulePath configuration for a Windows environment:</span></span>

```json
{
  "PSModulePath": "C:\\Program Files\\PowerShell\\6\\Modules"
}
```

<span data-ttu-id="31418-152">Este exemplo mostra uma configuração de PSModulePath para um ambiente macOS ou Linux:</span><span class="sxs-lookup"><span data-stu-id="31418-152">This example shows a PSModulePath configuration for a macOS or Linux environment:</span></span>

```json
{
  "PSModulePath": "/opt/powershell/6/Modules"
}
```

<span data-ttu-id="31418-153">Este exemplo mostra a inserção de uma variável de ambiente em uma configuração de PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="31418-153">This example shows embedding an environment variable in a PSModulePath configuration.</span></span> <span data-ttu-id="31418-154">Observe que, usando a `HOME` variável de ambiente e o `/` separador de diretório, isso funcionará no Windows, no MacOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="31418-154">Note that using the `HOME` environment variable and the `/` directory separator, this will work on Windows, macOS and Linux.</span></span>

```json
{
  "PSModulePath": "%HOME%/Documents/PowerShell/Modules"
}
```

<span data-ttu-id="31418-155">Este exemplo mostra a inserção de uma variável de ambiente em uma configuração PSModulePath que só funcionará no macOS e no Linux:</span><span class="sxs-lookup"><span data-stu-id="31418-155">This example shows embedding an environment variable in a PSModulePath configuration that will only work on macOS and Linux:</span></span>

```json
{
  "PSModulePath": "%XDG_CONFIG_HOME%/powershell/Modules"
}
```

> [!NOTE]
> <span data-ttu-id="31418-156">As variáveis do PowerShell não podem ser inseridas em configurações do PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="31418-156">PowerShell variables cannot be embedded in PSModulePath configurations.</span></span>
> <span data-ttu-id="31418-157">As configurações do PSModulePath no Linux e no macOS diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="31418-157">PSModulePath configurations on Linux and macOS are case-sensitive.</span></span> <span data-ttu-id="31418-158">Uma configuração PSModulePath deve usar separadores de diretório válidos para a plataforma.</span><span class="sxs-lookup"><span data-stu-id="31418-158">A PSModulePath configuration must use valid directory separators for the platform.</span></span> <span data-ttu-id="31418-159">No macOS e no Linux, isso significa `/` .</span><span class="sxs-lookup"><span data-stu-id="31418-159">On macOS and Linux, this means `/`.</span></span> <span data-ttu-id="31418-160">No Windows, `/` e `\` funcionarão.</span><span class="sxs-lookup"><span data-stu-id="31418-160">On Windows, both `/` and `\` will work.</span></span>

### <a name="experimentalfeatures"></a><span data-ttu-id="31418-161">ExperimentalFeatures</span><span class="sxs-lookup"><span data-stu-id="31418-161">ExperimentalFeatures</span></span>

<span data-ttu-id="31418-162">Os nomes dos recursos experimentais a serem habilitados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31418-162">The names of the experimental features to enable in PowerShell.</span></span>
<span data-ttu-id="31418-163">Por padrão, nenhum recurso experimental está habilitado.</span><span class="sxs-lookup"><span data-stu-id="31418-163">By default, no experimental features are enabled.</span></span>
<span data-ttu-id="31418-164">O valor padrão é uma matriz vazia.</span><span class="sxs-lookup"><span data-stu-id="31418-164">The default value is an empty array.</span></span>

```Schema
"ExperimentalFeatures": ["<experimental-feature-name>", ...]
```

<span data-ttu-id="31418-165">Em que:</span><span class="sxs-lookup"><span data-stu-id="31418-165">Where:</span></span>

- <span data-ttu-id="31418-166">`<experimental-feature-name>` é o nome de um recurso experimental a ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="31418-166">`<experimental-feature-name>` is the name of an experimental feature to enable.</span></span>

<span data-ttu-id="31418-167">O exemplo a seguir habilita os recursos experimentais **PSImplicitRemoting** e **PSUseAbbreviationExpansion** quando o PowerShell é iniciado.</span><span class="sxs-lookup"><span data-stu-id="31418-167">The following example enables the **PSImplicitRemoting** and **PSUseAbbreviationExpansion** experimental features when PowerShell starts up.</span></span>

```json
{
  "ExperimentalFeatures": [
    "PSImplicitRemotingBatching",
    "PSUseAbbreviationExpansion"
  ]
}
```

<span data-ttu-id="31418-168">Para obter mais informações sobre recursos experimentais, consulte [PowerShell RFC 29][RFC0029].</span><span class="sxs-lookup"><span data-stu-id="31418-168">For more information on experimental features, see [PowerShell RFC 29][RFC0029].</span></span>

## <a name="non-windows-logging-configuration"></a><span data-ttu-id="31418-169">Configuração de log não Windows</span><span class="sxs-lookup"><span data-stu-id="31418-169">Non-Windows logging configuration</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31418-170">As opções de configuração nesta seção se aplicam somente ao macOS e ao Linux.</span><span class="sxs-lookup"><span data-stu-id="31418-170">The configuration options in this section only apply to macOS and Linux.</span></span>
> <span data-ttu-id="31418-171">O registro em log do Windows é gerenciado pelo Visualizador de Eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="31418-171">Logging for Windows is managed by the Windows Event Viewer.</span></span>

<span data-ttu-id="31418-172">O registro em log do PowerShell no macOS e no Linux pode ser configurado no arquivo de configuração do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31418-172">PowerShell's logging on macOS and Linux can be configured in the PowerShell configuration file.</span></span> <span data-ttu-id="31418-173">Para obter uma descrição completa do log do PowerShell para sistemas que não são do Windows, consulte [sobre registro em log](./about_Logging_Non-Windows.md).</span><span class="sxs-lookup"><span data-stu-id="31418-173">For a full description of PowerShell logging for non-Windows systems, see [About Logging](./about_Logging_Non-Windows.md).</span></span>

### <a name="logidentity"></a><span data-ttu-id="31418-174">LogIdentity</span><span class="sxs-lookup"><span data-stu-id="31418-174">LogIdentity</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31418-175">Essa configuração só pode ser usada no macOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="31418-175">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="31418-176">Define o nome de identidade usado para gravar no log do sistema.</span><span class="sxs-lookup"><span data-stu-id="31418-176">Sets the identity name used to write to the system log.</span></span> <span data-ttu-id="31418-177">O valor padrão é "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="31418-177">The default value is "powershell".</span></span>

```Schema
"LogIdentity": "<log-identity>"
```

<span data-ttu-id="31418-178">Em que:</span><span class="sxs-lookup"><span data-stu-id="31418-178">Where:</span></span>

- <span data-ttu-id="31418-179">`<log-identity>` é a identidade de cadeia de caracteres que o PowerShell deve usar para gravar no syslog.</span><span class="sxs-lookup"><span data-stu-id="31418-179">`<log-identity>` is the string identity that PowerShell should use for writing to syslog.</span></span>

> [!NOTE]
> <span data-ttu-id="31418-180">Talvez você queira ter diferentes valores de **LogIdentity** para cada instância diferente do PowerShell que você instalou.</span><span class="sxs-lookup"><span data-stu-id="31418-180">You may want to have different **LogIdentity** values for each different instance of PowerShell you have installed.</span></span>

<span data-ttu-id="31418-181">Neste exemplo, estamos Configurando o **LogIdentity** para uma versão de visualização do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31418-181">In this example, we are configuring the **LogIdentity** for a preview release of PowerShell.</span></span>

```json
{
  "LogIdentity": "powershell-preview"
}
```

### <a name="loglevel"></a><span data-ttu-id="31418-182">LogLevel</span><span class="sxs-lookup"><span data-stu-id="31418-182">LogLevel</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31418-183">Essa configuração só pode ser usada no macOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="31418-183">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="31418-184">Especifica o nível de severidade mínimo no qual o PowerShell deve registrar.</span><span class="sxs-lookup"><span data-stu-id="31418-184">Specifies the minimum severity level at which PowerShell should log.</span></span>

```Schema
"LogLevel": "<log-level>|default"
```

<span data-ttu-id="31418-185">Em que:</span><span class="sxs-lookup"><span data-stu-id="31418-185">Where:</span></span>

- <span data-ttu-id="31418-186">`<log-level>` pode ser:</span><span class="sxs-lookup"><span data-stu-id="31418-186">`<log-level>` is one of:</span></span>
  - <span data-ttu-id="31418-187">Sempre</span><span class="sxs-lookup"><span data-stu-id="31418-187">Always</span></span>
  - <span data-ttu-id="31418-188">Crítico</span><span class="sxs-lookup"><span data-stu-id="31418-188">Critical</span></span>
  - <span data-ttu-id="31418-189">Erro</span><span class="sxs-lookup"><span data-stu-id="31418-189">Error</span></span>
  - <span data-ttu-id="31418-190">Aviso</span><span class="sxs-lookup"><span data-stu-id="31418-190">Warning</span></span>
  - <span data-ttu-id="31418-191">Informativo</span><span class="sxs-lookup"><span data-stu-id="31418-191">Informational</span></span>
  - <span data-ttu-id="31418-192">Detalhado</span><span class="sxs-lookup"><span data-stu-id="31418-192">Verbose</span></span>
  - <span data-ttu-id="31418-193">Depurar</span><span class="sxs-lookup"><span data-stu-id="31418-193">Debug</span></span>

> [!NOTE]
> <span data-ttu-id="31418-194">A configuração de um nível de log habilita todos os níveis de log acima dele.</span><span class="sxs-lookup"><span data-stu-id="31418-194">Setting a the log level enables all log levels above it.</span></span>

<span data-ttu-id="31418-195">Definir essa configuração como **padrão** será interpretado como o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="31418-195">Setting this setting to **default** will be interpreted as the default value.</span></span>
<span data-ttu-id="31418-196">O valor padrão é **informativo**.</span><span class="sxs-lookup"><span data-stu-id="31418-196">The default value is **Informational**.</span></span>

<span data-ttu-id="31418-197">O exemplo a seguir define o valor como **Verbose**.</span><span class="sxs-lookup"><span data-stu-id="31418-197">The following example sets the value to **Verbose**.</span></span>

```json
{
  "LogLevel": "Verbose"
}
```

### <a name="logchannels"></a><span data-ttu-id="31418-198">LogChannels</span><span class="sxs-lookup"><span data-stu-id="31418-198">LogChannels</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31418-199">Essa configuração só pode ser usada no macOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="31418-199">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="31418-200">Determina quais canais de log estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="31418-200">Determines which logging channels are enabled.</span></span>

```Schema
"LogChannels": "<log-channel>,..."
```

<span data-ttu-id="31418-201">Em que:</span><span class="sxs-lookup"><span data-stu-id="31418-201">Where:</span></span>

- <span data-ttu-id="31418-202">`<log-channel>` pode ser:</span><span class="sxs-lookup"><span data-stu-id="31418-202">`<log-channel>` is one of:</span></span>
  - <span data-ttu-id="31418-203">Operacional-registra informações básicas sobre as atividades do PowerShell</span><span class="sxs-lookup"><span data-stu-id="31418-203">Operational - logs basic information about PowerShell activities</span></span>
  - <span data-ttu-id="31418-204">Análise-registra informações de diagnóstico mais detalhadas</span><span class="sxs-lookup"><span data-stu-id="31418-204">Analytic - logs more detailed diagnostic information</span></span>

<span data-ttu-id="31418-205">O valor padrão é **operacional**.</span><span class="sxs-lookup"><span data-stu-id="31418-205">The default value is **Operational**.</span></span> <span data-ttu-id="31418-206">Para habilitar ambos os canais, inclua os dois valores como uma única cadeia de caracteres separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="31418-206">To enable both channels, include both values as a single comma-separated string.</span></span> <span data-ttu-id="31418-207">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="31418-207">For example:</span></span>

```json
{
  "LogChannels": "Operational,Analytic"
}
```

### <a name="logkeywords"></a><span data-ttu-id="31418-208">LogKeywords</span><span class="sxs-lookup"><span data-stu-id="31418-208">LogKeywords</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31418-209">Essa configuração só pode ser usada no macOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="31418-209">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="31418-210">Determina quais partes do PowerShell são registradas.</span><span class="sxs-lookup"><span data-stu-id="31418-210">Determines which parts of PowerShell are logged.</span></span> <span data-ttu-id="31418-211">Por padrão, todas as palavras-chave de log são habilitadas.</span><span class="sxs-lookup"><span data-stu-id="31418-211">By default, all log keywords are enabled.</span></span> <span data-ttu-id="31418-212">Para habilitar várias palavras-chave, liste os valores em uma única cadeia de caracteres separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="31418-212">To enable multiple keywords, list the values in a single comma-separated string.</span></span>

```Schema
"LogKeywords": "<log-keyword>,..."
```

<span data-ttu-id="31418-213">Em que:</span><span class="sxs-lookup"><span data-stu-id="31418-213">Where:</span></span>

- <span data-ttu-id="31418-214">`<log-keyword>` pode ser:</span><span class="sxs-lookup"><span data-stu-id="31418-214">`<log-keyword>` is one of:</span></span>
  - <span data-ttu-id="31418-215">Runspace-gerenciamento de runspace</span><span class="sxs-lookup"><span data-stu-id="31418-215">Runspace - runspace management</span></span>
  - <span data-ttu-id="31418-216">Pipeline – operações de pipeline</span><span class="sxs-lookup"><span data-stu-id="31418-216">Pipeline - pipeline operations</span></span>
  - <span data-ttu-id="31418-217">Protocolo – tratamento de protocolo de comunicação, como PSRP</span><span class="sxs-lookup"><span data-stu-id="31418-217">Protocol - communication protocol handling, such as PSRP</span></span>
  - <span data-ttu-id="31418-218">Suporte de camada de transporte de transporte, como SSH</span><span class="sxs-lookup"><span data-stu-id="31418-218">Transport - transport layer support, such as SSH</span></span>
  - <span data-ttu-id="31418-219">Funcionalidade host-PowerShell host, por exemplo, interação do console</span><span class="sxs-lookup"><span data-stu-id="31418-219">Host - PowerShell host functionality, for example console interaction</span></span>
  - <span data-ttu-id="31418-220">Cmdlets – cmdlets internos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="31418-220">Cmdlets -PowerShell builtin cmdlets</span></span>
  - <span data-ttu-id="31418-221">Serializador-lógica de serialização</span><span class="sxs-lookup"><span data-stu-id="31418-221">Serializer - serialization logic</span></span>
  - <span data-ttu-id="31418-222">Sessão-estado de sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="31418-222">Session - PowerShell session state</span></span>
  - <span data-ttu-id="31418-223">ManagedPlugin-plug-in do WSMan</span><span class="sxs-lookup"><span data-stu-id="31418-223">ManagedPlugin - WSMan plugin</span></span>

> [!NOTE]
> <span data-ttu-id="31418-224">Geralmente, é aconselhável deixar esse valor definido, a menos que você esteja tentando diagnosticar um comportamento específico em uma parte conhecida do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31418-224">It is generally advised to leave this value unset unless you are trying to diagnose a specific behavior in a known part of PowerShell.</span></span>
> <span data-ttu-id="31418-225">A alteração desse valor diminui apenas a quantidade de informações registradas.</span><span class="sxs-lookup"><span data-stu-id="31418-225">Changing this value only decreases the amount of information logged.</span></span>

<span data-ttu-id="31418-226">Este exemplo limita o registro em log para operações de runspace, lógica de pipeline e uso de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="31418-226">This example limits the logging to runspace operations, pipeline logic, and cmdlet use.</span></span> <span data-ttu-id="31418-227">Todos os outros logs serão omitidos.</span><span class="sxs-lookup"><span data-stu-id="31418-227">All other logging will be omitted.</span></span>

```json
"LogKeywords": "Runspace,Pipeline,Cmdlets"
```

<!--

## Group policy configuration

### ScriptExecution

### ScriptBlockLogging

### ProtectedEventLogging

### Transcription

### UpdateableHelp

### ConsoleSessionConfiguration

-->

## <a name="more-example-configurations"></a><span data-ttu-id="31418-228">Mais configurações de exemplo</span><span class="sxs-lookup"><span data-stu-id="31418-228">More example configurations</span></span>

### <a name="example-windows-configuration"></a><span data-ttu-id="31418-229">Configuração do Windows de exemplo</span><span class="sxs-lookup"><span data-stu-id="31418-229">Example Windows configuration</span></span>

<span data-ttu-id="31418-230">Essa configuração tem mais configurações definidas explicitamente:</span><span class="sxs-lookup"><span data-stu-id="31418-230">This configuration has more settings explicitly set:</span></span>

- <span data-ttu-id="31418-231">A política de execução para esta instalação do PowerShell é `AllSigned`</span><span class="sxs-lookup"><span data-stu-id="31418-231">Execution policy for this PowerShell installation is `AllSigned`</span></span>
- <span data-ttu-id="31418-232">O caminho do módulo CurrentUser é definido como um diretório de módulo em uma unidade compartilhada</span><span class="sxs-lookup"><span data-stu-id="31418-232">The CurrentUser module path is set to a module directory on a shared drive</span></span>
- <span data-ttu-id="31418-233">O `PSImplicitRemotingBatching` recurso experimental está habilitado</span><span class="sxs-lookup"><span data-stu-id="31418-233">The `PSImplicitRemotingBatching` experimental feature is enabled</span></span>

> [!NOTE]
> <span data-ttu-id="31418-234">As `ExecutionPolicy` `PSModulePath` configurações e aqui só funcionariam em uma plataforma Windows, já que o caminho do módulo usa `\` e `;` caracteres separadores e a política de execução não é `Unrestricted` (a única política permitida em plataformas semelhantes a UNIX).</span><span class="sxs-lookup"><span data-stu-id="31418-234">The `ExecutionPolicy` and `PSModulePath` settings here would only work on a Windows platform, since the module path uses `\` and `;` separator characters and the execution policy is not `Unrestricted` (the only policy allowed on UNIX-like platforms).</span></span>

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "AllSigned",
  "PSModulePath": "Z:\\Marisol's Shared Drive\\Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
}
```

### <a name="example-non-windows-configuration"></a><span data-ttu-id="31418-235">Exemplo de configuração não Windows</span><span class="sxs-lookup"><span data-stu-id="31418-235">Example non-Windows configuration</span></span>

<span data-ttu-id="31418-236">Essa configuração define várias opções que funcionam apenas no macOS ou Linux:</span><span class="sxs-lookup"><span data-stu-id="31418-236">This configuration sets a number of options that only work in macOS or Linux:</span></span>

- <span data-ttu-id="31418-237">O caminho do módulo CurrentUser é definido como um diretório de módulo personalizado no `$HOME`</span><span class="sxs-lookup"><span data-stu-id="31418-237">The CurrentUser module path is set to a custom module directory in `$HOME`</span></span>
- <span data-ttu-id="31418-238">O recurso experimental do **PSImplicitRemotingBatching** está habilitado</span><span class="sxs-lookup"><span data-stu-id="31418-238">The **PSImplicitRemotingBatching** experimental feature is enabled</span></span>
- <span data-ttu-id="31418-239">O nível de log do PowerShell é definido como **detalhado**, para obter mais registro em log</span><span class="sxs-lookup"><span data-stu-id="31418-239">The PowerShell logging level is set to **Verbose**, for more logging</span></span>
- <span data-ttu-id="31418-240">Essa instalação do PowerShell grava nos logs usando a identidade do **PowerShell inicial** .</span><span class="sxs-lookup"><span data-stu-id="31418-240">This PowerShell installation writes to the logs using the **home-powershell** identity.</span></span>

```json
{
  "PSModulePath": "%HOME%/.powershell/Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
  "LogLevel": "Verbose",
  "LogIdentity": "home-powershell"
}
```

## <a name="see-also"></a><span data-ttu-id="31418-241">Consulte também</span><span class="sxs-lookup"><span data-stu-id="31418-241">See also</span></span>

[<span data-ttu-id="31418-242">Sobre as políticas de execução</span><span class="sxs-lookup"><span data-stu-id="31418-242">About Execution Policies</span></span>](./about_Execution_Policies.md)

[<span data-ttu-id="31418-243">Sobre variáveis automáticas</span><span class="sxs-lookup"><span data-stu-id="31418-243">About Automatic Variables</span></span>](./about_Automatic_Variables.md)

[RFC0029]: https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md

