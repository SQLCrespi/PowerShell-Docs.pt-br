---
description: Arquivos de configuração do PowerShell Core, substituindo a configuração do registro.
keywords: powershell
Locale: en-US
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Config
ms.openlocfilehash: e1eabd71dde71f0191ca8bb991b5bee8f615c312
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195679"
---
# <a name="about-powershell-config"></a><span data-ttu-id="bd0b2-104">Sobre a configuração do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd0b2-104">About PowerShell Config</span></span>

## <a name="short-description"></a><span data-ttu-id="bd0b2-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="bd0b2-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="bd0b2-106">Arquivos de configuração do PowerShell Core, substituindo a configuração do registro.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-106">Configuration files for PowerShell Core, replacing Registry configuration.</span></span>

## <a name="long-description"></a><span data-ttu-id="bd0b2-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="bd0b2-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="bd0b2-108">O `powershell.config.json` arquivo contém definições de configuração para o PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-108">The `powershell.config.json` file contains configuration settings for PowerShell Core.</span></span> <span data-ttu-id="bd0b2-109">O PowerShell carrega essa configuração na inicialização.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-109">PowerShell loads this configuration at startup.</span></span> <span data-ttu-id="bd0b2-110">As configurações também podem ser modificadas em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-110">The settings can also be modified at runtime.</span></span> <span data-ttu-id="bd0b2-111">Anteriormente, essas configurações eram armazenadas no registro do Windows para o PowerShell, mas agora estão contidas em um arquivo para habilitar a configuração no macOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-111">Previously, these settings were stored in the Windows Registry for PowerShell, but are now contained in a file to enable configuration on macOS and Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="bd0b2-112">Se o `powershell.config.json` arquivo contiver um PowerShell JSON inválido não poderá iniciar uma sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-112">If the `powershell.config.json` file contains invalid JSON PowerShell cannot start an interactive session.</span></span>
> <span data-ttu-id="bd0b2-113">Se isso ocorrer, você deverá corrigir o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-113">If this occurs, you must fix the configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="bd0b2-114">Chaves não reconhecidas ou valores inválidos no arquivo de configuração serão ignorados silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-114">Unrecognized keys or invalid values in the configuration file will be silently ignored.</span></span>

### <a name="allusers-shared-configuration"></a><span data-ttu-id="bd0b2-115">Configuração de AllUsers (compartilhado)</span><span class="sxs-lookup"><span data-stu-id="bd0b2-115">AllUsers (shared) configuration</span></span>

<span data-ttu-id="bd0b2-116">Um `powershell.config.json` arquivo no `$PSHOME` diretório define a configuração para todas as sessões do PowerShell Core em execução a partir da instalação do PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-116">A `powershell.config.json` file in the `$PSHOME` directory defines the configuration for all PowerShell Core sessions running from that PowerShell Core installation.</span></span>

> [!NOTE]
> <span data-ttu-id="bd0b2-117">O `$PSHOME` local é definido como o mesmo diretório que o assembly de System.Management.Automation.dll em execução.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-117">The `$PSHOME` location is defined as the same directory as the executing System.Management.Automation.dll assembly.</span></span> <span data-ttu-id="bd0b2-118">Isso se aplica a instâncias do SDK do PowerShell hospedadas também.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-118">This applies to hosted PowerShell SDK instances as well.</span></span>

### <a name="currentuser-per-user-configurations"></a><span data-ttu-id="bd0b2-119">Configurações CurrentUser (por usuário)</span><span class="sxs-lookup"><span data-stu-id="bd0b2-119">CurrentUser (per-user) configurations</span></span>

<span data-ttu-id="bd0b2-120">Você também pode configurar o PowerShell em uma base por usuário colocando o arquivo no diretório de configuração de escopo do usuário.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-120">You can also configure PowerShell on a per-user basis by placing the file in the user-scope configuration directory.</span></span> <span data-ttu-id="bd0b2-121">O diretório de configuração do usuário pode ser encontrado em várias plataformas com o comando `Split-Path $PROFILE.CurrentUserCurrentHost` .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-121">The user configuration directory can be found across platforms with the command `Split-Path $PROFILE.CurrentUserCurrentHost`.</span></span>

## <a name="general-configuration-settings"></a><span data-ttu-id="bd0b2-122">Definições de configuração geral</span><span class="sxs-lookup"><span data-stu-id="bd0b2-122">General configuration settings</span></span>

### <a name="executionpolicy"></a><span data-ttu-id="bd0b2-123">ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="bd0b2-123">ExecutionPolicy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd0b2-124">Essa configuração se aplica somente a plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-124">This configuration only applies on Windows platforms.</span></span>

<span data-ttu-id="bd0b2-125">Configura a política de execução para sessões do PowerShell, determinando quais scripts podem ser executados.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-125">Configures the execution policy for PowerShell sessions, determining what scripts can be run.</span></span> <span data-ttu-id="bd0b2-126">Por padrão, o PowerShell usa a política de execução existente.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-126">By default, PowerShell uses the existing execution policy.</span></span>

<span data-ttu-id="bd0b2-127">Para configurações AllUsers, isso define a política de execução **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-127">For AllUsers configurations, this sets the **LocalMachine** execution policy.</span></span>
<span data-ttu-id="bd0b2-128">Para configurações CurrentUser, isso define a política de execução **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-128">For CurrentUser configurations, this sets the **CurrentUser** execution policy.</span></span>

> [!NOTE]
> <span data-ttu-id="bd0b2-129">O [`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy) cmdlet modifica essa configuração no arquivo de configuração AllUsers quando invocado com `-Scope LocalMachine` o e modifica essa configuração no arquivo de configuração CurrentUser quando invocado com `-Scope CurrentUser` .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-129">The [`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy) cmdlet modifies this setting in the AllUsers configuration file when invoked with `-Scope LocalMachine`, and modifies this setting in the CurrentUser configuration file when invoked with `-Scope CurrentUser`.</span></span>

```Schema
"<shell-id>:ExecutionPolicy": "<execution-policy>"
```

<span data-ttu-id="bd0b2-130">Em que:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-130">Where:</span></span>

- <span data-ttu-id="bd0b2-131">`<shell-id>` refere-se à ID do host do PowerShell atual.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-131">`<shell-id>` refers to the ID of the current PowerShell host.</span></span>
  <span data-ttu-id="bd0b2-132">Para o PowerShell Core normal, isso é `Microsoft.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-132">For normal PowerShell Core, this is `Microsoft.PowerShell`.</span></span>
  <span data-ttu-id="bd0b2-133">Em qualquer sessão do PowerShell, você pode descobri-lo com o `$ShellId` .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-133">In any PowerShell session, you can discover it with `$ShellId`.</span></span>
- <span data-ttu-id="bd0b2-134">`<execution-policy>` refere-se a um nome de política de execução válido.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-134">`<execution-policy>` refers to a valid execution policy name.</span></span>

<span data-ttu-id="bd0b2-135">O exemplo a seguir define a política de execução do PowerShell para `RemoteSigned` .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-135">The following example sets the execution policy of PowerShell to `RemoteSigned`.</span></span>

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "RemoteSigned"
}
```

<span data-ttu-id="bd0b2-136">No Windows, as chaves de registro equivalentes podem ser encontradas em `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` em `HKEY_LOCAL_MACHINE` e `HKEY_CURRENT_USER` .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-136">In Windows, the equivalent registry keys can be found in `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` under `HKEY_LOCAL_MACHINE` and `HKEY_CURRENT_USER`.</span></span>

### <a name="psmodulepath"></a><span data-ttu-id="bd0b2-137">PSModulePath</span><span class="sxs-lookup"><span data-stu-id="bd0b2-137">PSModulePath</span></span>

<span data-ttu-id="bd0b2-138">Substitui um componente PSModulePath para esta sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-138">Overrides a PSModulePath component for this PowerShell session.</span></span> <span data-ttu-id="bd0b2-139">Se a configuração for para o usuário atual, define o caminho do módulo CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-139">If the configuration is for the current user, sets the CurrentUser module path.</span></span> <span data-ttu-id="bd0b2-140">Se a configuração for para todos os usuários, define o caminho do módulo do usuário.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-140">If the configuration is for all users, sets the AllUser module path.</span></span>

> [!WARNING]
> <span data-ttu-id="bd0b2-141">Configurar um caminho de módulo AllUsers ou CurrentUser aqui não alterará o local de instalação com escopo para módulos do PowerShellGet [, como install-Module](/powershell/module/powershellget/install-module).</span><span class="sxs-lookup"><span data-stu-id="bd0b2-141">Configuring an AllUsers or CurrentUser module path here will not change the scoped installation location for PowerShellGet modules like [Install-Module](/powershell/module/powershellget/install-module).</span></span>
> <span data-ttu-id="bd0b2-142">Esses cmdlets sempre usam os caminhos de módulo *padrão* .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-142">These cmdlets always use the *default* module paths.</span></span>

<span data-ttu-id="bd0b2-143">Se nenhum valor for definido, o valor padrão do respectivo componente de caminho do módulo será usado.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-143">If no value is set, the default value for the respective module path component will be used.</span></span> <span data-ttu-id="bd0b2-144">Consulte [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) para obter mais detalhes sobre esses padrões.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-144">See [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) for more details on these defaults.</span></span>

<span data-ttu-id="bd0b2-145">Essa configuração permite que as variáveis de ambiente sejam usadas inserindo-as entre `%` caracteres, como `"%HOME%\Documents\PowerShell\Modules"` , da mesma maneira que o cmd permite.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-145">This setting allows environment variables to be used by embedding them between `%` characters, like `"%HOME%\Documents\PowerShell\Modules"`, in the same way as CMD allows.</span></span> <span data-ttu-id="bd0b2-146">Essa sintaxe também se aplica ao Linux e ao macOS.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-146">This syntax also applies on Linux and macOS.</span></span> <span data-ttu-id="bd0b2-147">Consulte abaixo para obter exemplos.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-147">See below for examples.</span></span>

```Schema
"PSModulePath": "<ps-module-path>"
```

<span data-ttu-id="bd0b2-148">Em que:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-148">Where:</span></span>

- <span data-ttu-id="bd0b2-149">`<ps-module-path>` é o caminho absoluto para um diretório de módulo.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-149">`<ps-module-path>` is the absolute path to a module directory.</span></span> <span data-ttu-id="bd0b2-150">Para todas as configurações de usuário, esse é o diretório de módulo compartilhado AllUsers.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-150">For all user configurations, this is the AllUsers shared module directory.</span></span> <span data-ttu-id="bd0b2-151">Para as configurações de usuário atuais, este é o diretório de módulo CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-151">For current user configurations, this is CurrentUser module directory.</span></span>

<span data-ttu-id="bd0b2-152">Este exemplo mostra uma configuração de PSModulePath para um ambiente do Windows:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-152">This example shows a PSModulePath configuration for a Windows environment:</span></span>

```json
{
  "PSModulePath": "C:\\Program Files\\PowerShell\\6\\Modules"
}
```

<span data-ttu-id="bd0b2-153">Este exemplo mostra uma configuração de PSModulePath para um ambiente macOS ou Linux:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-153">This example shows a PSModulePath configuration for a macOS or Linux environment:</span></span>

```json
{
  "PSModulePath": "/opt/powershell/6/Modules"
}
```

<span data-ttu-id="bd0b2-154">Este exemplo mostra a inserção de uma variável de ambiente em uma configuração de PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-154">This example shows embedding an environment variable in a PSModulePath configuration.</span></span> <span data-ttu-id="bd0b2-155">Observe que, usando a `HOME` variável de ambiente e o `/` separador de diretório, isso funcionará no Windows, no MacOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-155">Note that using the `HOME` environment variable and the `/` directory separator, this will work on Windows, macOS and Linux.</span></span>

```json
{
  "PSModulePath": "%HOME%/Documents/PowerShell/Modules"
}
```

<span data-ttu-id="bd0b2-156">Este exemplo mostra a inserção de uma variável de ambiente em uma configuração PSModulePath que só funcionará no macOS e no Linux:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-156">This example shows embedding an environment variable in a PSModulePath configuration that will only work on macOS and Linux:</span></span>

```json
{
  "PSModulePath": "%XDG_CONFIG_HOME%/powershell/Modules"
}
```

> [!NOTE]
> <span data-ttu-id="bd0b2-157">As variáveis do PowerShell não podem ser inseridas em configurações do PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-157">PowerShell variables cannot be embedded in PSModulePath configurations.</span></span>
> <span data-ttu-id="bd0b2-158">As configurações do PSModulePath no Linux e no macOS diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-158">PSModulePath configurations on Linux and macOS are case-sensitive.</span></span> <span data-ttu-id="bd0b2-159">Uma configuração PSModulePath deve usar separadores de diretório válidos para a plataforma.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-159">A PSModulePath configuration must use valid directory separators for the platform.</span></span> <span data-ttu-id="bd0b2-160">No macOS e no Linux, isso significa `/` .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-160">On macOS and Linux, this means `/`.</span></span> <span data-ttu-id="bd0b2-161">No Windows, `/` e `\` funcionarão.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-161">On Windows, both `/` and `\` will work.</span></span>

### <a name="experimentalfeatures"></a><span data-ttu-id="bd0b2-162">ExperimentalFeatures</span><span class="sxs-lookup"><span data-stu-id="bd0b2-162">ExperimentalFeatures</span></span>

<span data-ttu-id="bd0b2-163">Os nomes dos recursos experimentais a serem habilitados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-163">The names of the experimental features to enable in PowerShell.</span></span>
<span data-ttu-id="bd0b2-164">Por padrão, nenhum recurso experimental está habilitado.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-164">By default, no experimental features are enabled.</span></span>
<span data-ttu-id="bd0b2-165">O valor padrão é uma matriz vazia.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-165">The default value is an empty array.</span></span>

```Schema
"ExperimentalFeatures": ["<experimental-feature-name>", ...]
```

<span data-ttu-id="bd0b2-166">Em que:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-166">Where:</span></span>

- <span data-ttu-id="bd0b2-167">`<experimental-feature-name>` é o nome de um recurso experimental a ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-167">`<experimental-feature-name>` is the name of an experimental feature to enable.</span></span>

<span data-ttu-id="bd0b2-168">O exemplo a seguir habilita os recursos experimentais **PSImplicitRemoting** e **PSUseAbbreviationExpansion** quando o PowerShell é iniciado.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-168">The following example enables the **PSImplicitRemoting** and **PSUseAbbreviationExpansion** experimental features when PowerShell starts up.</span></span>

```json
{
  "ExperimentalFeatures": [
    "PSImplicitRemotingBatching",
    "PSUseAbbreviationExpansion"
  ]
}
```

<span data-ttu-id="bd0b2-169">Para obter mais informações sobre recursos experimentais, consulte [PowerShell RFC 29][RFC0029].</span><span class="sxs-lookup"><span data-stu-id="bd0b2-169">For more information on experimental features, see [PowerShell RFC 29][RFC0029].</span></span>

## <a name="non-windows-logging-configuration"></a><span data-ttu-id="bd0b2-170">Configuração de log não Windows</span><span class="sxs-lookup"><span data-stu-id="bd0b2-170">Non-Windows logging configuration</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd0b2-171">As opções de configuração nesta seção se aplicam somente ao macOS e ao Linux.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-171">The configuration options in this section only apply to macOS and Linux.</span></span>
> <span data-ttu-id="bd0b2-172">O registro em log do Windows é gerenciado pelo Visualizador de Eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-172">Logging for Windows is managed by the Windows Event Viewer.</span></span>

<span data-ttu-id="bd0b2-173">O registro em log do PowerShell no macOS e no Linux pode ser configurado no arquivo de configuração do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-173">PowerShell's logging on macOS and Linux can be configured in the PowerShell configuration file.</span></span> <span data-ttu-id="bd0b2-174">Para obter uma descrição completa do log do PowerShell para sistemas que não são do Windows, consulte [sobre registro em log](./about_Logging_Non-Windows.md).</span><span class="sxs-lookup"><span data-stu-id="bd0b2-174">For a full description of PowerShell logging for non-Windows systems, see [About Logging](./about_Logging_Non-Windows.md).</span></span>

### <a name="logidentity"></a><span data-ttu-id="bd0b2-175">LogIdentity</span><span class="sxs-lookup"><span data-stu-id="bd0b2-175">LogIdentity</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd0b2-176">Essa configuração só pode ser usada no macOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-176">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="bd0b2-177">Define o nome de identidade usado para gravar no log do sistema.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-177">Sets the identity name used to write to the system log.</span></span> <span data-ttu-id="bd0b2-178">O valor padrão é "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="bd0b2-178">The default value is "powershell".</span></span>

```Schema
"LogIdentity": "<log-identity>"
```

<span data-ttu-id="bd0b2-179">Em que:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-179">Where:</span></span>

- <span data-ttu-id="bd0b2-180">`<log-identity>` é a identidade de cadeia de caracteres que o PowerShell deve usar para gravar no syslog.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-180">`<log-identity>` is the string identity that PowerShell should use for writing to syslog.</span></span>

> [!NOTE]
> <span data-ttu-id="bd0b2-181">Talvez você queira ter diferentes valores de **LogIdentity** para cada instância diferente do PowerShell que você instalou.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-181">You may want to have different **LogIdentity** values for each different instance of PowerShell you have installed.</span></span>

<span data-ttu-id="bd0b2-182">Neste exemplo, estamos Configurando o **LogIdentity** para uma versão de visualização do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-182">In this example, we are configuring the **LogIdentity** for a preview release of PowerShell.</span></span>

```json
{
  "LogIdentity": "powershell-preview"
}
```

### <a name="loglevel"></a><span data-ttu-id="bd0b2-183">LogLevel</span><span class="sxs-lookup"><span data-stu-id="bd0b2-183">LogLevel</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd0b2-184">Essa configuração só pode ser usada no macOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-184">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="bd0b2-185">Especifica o nível de severidade mínimo no qual o PowerShell deve registrar.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-185">Specifies the minimum severity level at which PowerShell should log.</span></span>

```Schema
"LogLevel": "<log-level>|default"
```

<span data-ttu-id="bd0b2-186">Em que:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-186">Where:</span></span>

- <span data-ttu-id="bd0b2-187">`<log-level>` é um de:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-187">`<log-level>` is one of:</span></span>
  - <span data-ttu-id="bd0b2-188">Always</span><span class="sxs-lookup"><span data-stu-id="bd0b2-188">Always</span></span>
  - <span data-ttu-id="bd0b2-189">Crítico</span><span class="sxs-lookup"><span data-stu-id="bd0b2-189">Critical</span></span>
  - <span data-ttu-id="bd0b2-190">Erro</span><span class="sxs-lookup"><span data-stu-id="bd0b2-190">Error</span></span>
  - <span data-ttu-id="bd0b2-191">Aviso</span><span class="sxs-lookup"><span data-stu-id="bd0b2-191">Warning</span></span>
  - <span data-ttu-id="bd0b2-192">Informativo</span><span class="sxs-lookup"><span data-stu-id="bd0b2-192">Informational</span></span>
  - <span data-ttu-id="bd0b2-193">Detalhado</span><span class="sxs-lookup"><span data-stu-id="bd0b2-193">Verbose</span></span>
  - <span data-ttu-id="bd0b2-194">Depurar</span><span class="sxs-lookup"><span data-stu-id="bd0b2-194">Debug</span></span>

> [!NOTE]
> <span data-ttu-id="bd0b2-195">A configuração de um nível de log habilita todos os níveis de log acima dele.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-195">Setting a the log level enables all log levels above it.</span></span>

<span data-ttu-id="bd0b2-196">Definir essa configuração como **padrão** será interpretado como o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-196">Setting this setting to **default** will be interpreted as the default value.</span></span>
<span data-ttu-id="bd0b2-197">O valor padrão é **informativo** .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-197">The default value is **Informational** .</span></span>

<span data-ttu-id="bd0b2-198">O exemplo a seguir define o valor como **Verbose** .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-198">The following example sets the value to **Verbose** .</span></span>

```json
{
  "LogLevel": "Verbose"
}
```

### <a name="logchannels"></a><span data-ttu-id="bd0b2-199">LogChannels</span><span class="sxs-lookup"><span data-stu-id="bd0b2-199">LogChannels</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd0b2-200">Essa configuração só pode ser usada no macOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-200">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="bd0b2-201">Determina quais canais de log estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-201">Determines which logging channels are enabled.</span></span>

```Schema
"LogChannels": "<log-channel>,..."
```

<span data-ttu-id="bd0b2-202">Em que:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-202">Where:</span></span>

- <span data-ttu-id="bd0b2-203">`<log-channel>` é um de:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-203">`<log-channel>` is one of:</span></span>
  - <span data-ttu-id="bd0b2-204">Operacional-registra informações básicas sobre as atividades do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd0b2-204">Operational - logs basic information about PowerShell activities</span></span>
  - <span data-ttu-id="bd0b2-205">Análise-registra informações de diagnóstico mais detalhadas</span><span class="sxs-lookup"><span data-stu-id="bd0b2-205">Analytic - logs more detailed diagnostic information</span></span>

<span data-ttu-id="bd0b2-206">O valor padrão é **operacional** .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-206">The default value is **Operational** .</span></span> <span data-ttu-id="bd0b2-207">Para habilitar ambos os canais, inclua os dois valores como uma única cadeia de caracteres separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-207">To enable both channels, include both values as a single comma-separated string.</span></span> <span data-ttu-id="bd0b2-208">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-208">For example:</span></span>

```json
{
  "LogChannels": "Operational,Analytic"
}
```

### <a name="logkeywords"></a><span data-ttu-id="bd0b2-209">LogKeywords</span><span class="sxs-lookup"><span data-stu-id="bd0b2-209">LogKeywords</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd0b2-210">Essa configuração só pode ser usada no macOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-210">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="bd0b2-211">Determina quais partes do PowerShell são registradas.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-211">Determines which parts of PowerShell are logged.</span></span> <span data-ttu-id="bd0b2-212">Por padrão, todas as palavras-chave de log são habilitadas.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-212">By default, all log keywords are enabled.</span></span> <span data-ttu-id="bd0b2-213">Para habilitar várias palavras-chave, liste os valores em uma única cadeia de caracteres separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-213">To enable multiple keywords, list the values in a single comma-separated string.</span></span>

```Schema
"LogKeywords": "<log-keyword>,..."
```

<span data-ttu-id="bd0b2-214">Em que:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-214">Where:</span></span>

- <span data-ttu-id="bd0b2-215">`<log-keyword>` é um de:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-215">`<log-keyword>` is one of:</span></span>
  - <span data-ttu-id="bd0b2-216">Runspace-gerenciamento de runspace</span><span class="sxs-lookup"><span data-stu-id="bd0b2-216">Runspace - runspace management</span></span>
  - <span data-ttu-id="bd0b2-217">Pipeline – operações de pipeline</span><span class="sxs-lookup"><span data-stu-id="bd0b2-217">Pipeline - pipeline operations</span></span>
  - <span data-ttu-id="bd0b2-218">Protocolo – tratamento de protocolo de comunicação, como PSRP</span><span class="sxs-lookup"><span data-stu-id="bd0b2-218">Protocol - communication protocol handling, such as PSRP</span></span>
  - <span data-ttu-id="bd0b2-219">Suporte de camada de transporte de transporte, como SSH</span><span class="sxs-lookup"><span data-stu-id="bd0b2-219">Transport - transport layer support, such as SSH</span></span>
  - <span data-ttu-id="bd0b2-220">Funcionalidade host-PowerShell host, por exemplo, interação do console</span><span class="sxs-lookup"><span data-stu-id="bd0b2-220">Host - PowerShell host functionality, for example console interaction</span></span>
  - <span data-ttu-id="bd0b2-221">Cmdlets – cmdlets internos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd0b2-221">Cmdlets -PowerShell builtin cmdlets</span></span>
  - <span data-ttu-id="bd0b2-222">Serializador-lógica de serialização</span><span class="sxs-lookup"><span data-stu-id="bd0b2-222">Serializer - serialization logic</span></span>
  - <span data-ttu-id="bd0b2-223">Sessão-estado de sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd0b2-223">Session - PowerShell session state</span></span>
  - <span data-ttu-id="bd0b2-224">ManagedPlugin-plug-in do WSMan</span><span class="sxs-lookup"><span data-stu-id="bd0b2-224">ManagedPlugin - WSMan plugin</span></span>

> [!NOTE]
> <span data-ttu-id="bd0b2-225">Geralmente, é aconselhável deixar esse valor definido, a menos que você esteja tentando diagnosticar um comportamento específico em uma parte conhecida do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-225">It is generally advised to leave this value unset unless you are trying to diagnose a specific behavior in a known part of PowerShell.</span></span>
> <span data-ttu-id="bd0b2-226">A alteração desse valor diminui apenas a quantidade de informações registradas.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-226">Changing this value only decreases the amount of information logged.</span></span>

<span data-ttu-id="bd0b2-227">Este exemplo limita o registro em log para operações de runspace, lógica de pipeline e uso de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-227">This example limits the logging to runspace operations, pipeline logic, and cmdlet use.</span></span> <span data-ttu-id="bd0b2-228">Todos os outros logs serão omitidos.</span><span class="sxs-lookup"><span data-stu-id="bd0b2-228">All other logging will be omitted.</span></span>

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

## <a name="more-example-configurations"></a><span data-ttu-id="bd0b2-229">Mais configurações de exemplo</span><span class="sxs-lookup"><span data-stu-id="bd0b2-229">More example configurations</span></span>

### <a name="example-windows-configuration"></a><span data-ttu-id="bd0b2-230">Configuração do Windows de exemplo</span><span class="sxs-lookup"><span data-stu-id="bd0b2-230">Example Windows configuration</span></span>

<span data-ttu-id="bd0b2-231">Essa configuração tem mais configurações definidas explicitamente:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-231">This configuration has more settings explicitly set:</span></span>

- <span data-ttu-id="bd0b2-232">A política de execução para esta instalação do PowerShell é `AllSigned`</span><span class="sxs-lookup"><span data-stu-id="bd0b2-232">Execution policy for this PowerShell installation is `AllSigned`</span></span>
- <span data-ttu-id="bd0b2-233">O caminho do módulo CurrentUser é definido como um diretório de módulo em uma unidade compartilhada</span><span class="sxs-lookup"><span data-stu-id="bd0b2-233">The CurrentUser module path is set to a module directory on a shared drive</span></span>
- <span data-ttu-id="bd0b2-234">O `PSImplicitRemotingBatching` recurso experimental está habilitado</span><span class="sxs-lookup"><span data-stu-id="bd0b2-234">The `PSImplicitRemotingBatching` experimental feature is enabled</span></span>

> [!NOTE]
> <span data-ttu-id="bd0b2-235">As `ExecutionPolicy` `PSModulePath` configurações e aqui só funcionariam em uma plataforma Windows, já que o caminho do módulo usa `\` e `;` caracteres separadores e a política de execução não é `Unrestricted` (a única política permitida em plataformas semelhantes a UNIX).</span><span class="sxs-lookup"><span data-stu-id="bd0b2-235">The `ExecutionPolicy` and `PSModulePath` settings here would only work on a Windows platform, since the module path uses `\` and `;` separator characters and the execution policy is not `Unrestricted` (the only policy allowed on UNIX-like platforms).</span></span>

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "AllSigned",
  "PSModulePath": "Z:\\Marisol's Shared Drive\\Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
}
```

### <a name="example-non-windows-configuration"></a><span data-ttu-id="bd0b2-236">Exemplo de configuração não Windows</span><span class="sxs-lookup"><span data-stu-id="bd0b2-236">Example non-Windows configuration</span></span>

<span data-ttu-id="bd0b2-237">Essa configuração define várias opções que funcionam apenas no macOS ou Linux:</span><span class="sxs-lookup"><span data-stu-id="bd0b2-237">This configuration sets a number of options that only work in macOS or Linux:</span></span>

- <span data-ttu-id="bd0b2-238">O caminho do módulo CurrentUser é definido como um diretório de módulo personalizado no `$HOME`</span><span class="sxs-lookup"><span data-stu-id="bd0b2-238">The CurrentUser module path is set to a custom module directory in `$HOME`</span></span>
- <span data-ttu-id="bd0b2-239">O recurso experimental do **PSImplicitRemotingBatching** está habilitado</span><span class="sxs-lookup"><span data-stu-id="bd0b2-239">The **PSImplicitRemotingBatching** experimental feature is enabled</span></span>
- <span data-ttu-id="bd0b2-240">O nível de log do PowerShell é definido como **detalhado** , para obter mais registro em log</span><span class="sxs-lookup"><span data-stu-id="bd0b2-240">The PowerShell logging level is set to **Verbose** , for more logging</span></span>
- <span data-ttu-id="bd0b2-241">Essa instalação do PowerShell grava nos logs usando a identidade do **PowerShell inicial** .</span><span class="sxs-lookup"><span data-stu-id="bd0b2-241">This PowerShell installation writes to the logs using the **home-powershell** identity.</span></span>

```json
{
  "PSModulePath": "%HOME%/.powershell/Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
  "LogLevel": "Verbose",
  "LogIdentity": "home-powershell"
}
```

## <a name="see-also"></a><span data-ttu-id="bd0b2-242">Confira também</span><span class="sxs-lookup"><span data-stu-id="bd0b2-242">See also</span></span>

[<span data-ttu-id="bd0b2-243">Sobre as políticas de execução</span><span class="sxs-lookup"><span data-stu-id="bd0b2-243">About Execution Policies</span></span>](./about_Execution_Policies.md)

[<span data-ttu-id="bd0b2-244">Sobre variáveis automáticas</span><span class="sxs-lookup"><span data-stu-id="bd0b2-244">About Automatic Variables</span></span>](./about_Automatic_Variables.md)

[RFC0029]: https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md
