---
description: O PowerShell registra em log as operações internas do mecanismo, provedores e cmdlets.
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging_non-windows?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging_Non-Windows
ms.openlocfilehash: e74e357d81eddf87ad27d023eb9a8ba2977156e9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597799"
---
# <a name="about-logging-non-windows"></a><span data-ttu-id="78fb7-103">Sobre o log de não Windows</span><span class="sxs-lookup"><span data-stu-id="78fb7-103">About Logging Non-Windows</span></span>

## <a name="short-description"></a><span data-ttu-id="78fb7-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="78fb7-104">Short description</span></span>
<span data-ttu-id="78fb7-105">O PowerShell registra em log as operações internas do mecanismo, provedores e cmdlets.</span><span class="sxs-lookup"><span data-stu-id="78fb7-105">PowerShell logs internal operations from the engine, providers, and cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="78fb7-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="78fb7-106">Long description</span></span>

<span data-ttu-id="78fb7-107">O PowerShell registra detalhes de operações do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78fb7-107">PowerShell logs details of PowerShell operations.</span></span> <span data-ttu-id="78fb7-108">Por exemplo, o PowerShell registrará operações como iniciar e parar o mecanismo e iniciar e parar provedores.</span><span class="sxs-lookup"><span data-stu-id="78fb7-108">For example, PowerShell will log operations such as starting and stopping the engine and starting and stopping providers.</span></span> <span data-ttu-id="78fb7-109">Ele também registrará em log detalhes sobre os comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78fb7-109">It will also log details about PowerShell commands.</span></span>

<span data-ttu-id="78fb7-110">O local dos logs do PowerShell depende da plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="78fb7-110">The location of PowerShell logs is dependent on the target platform.</span></span> <span data-ttu-id="78fb7-111">No **Linux**, os logs do PowerShell para **syslog** e **rsyslog. conf** podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="78fb7-111">On **Linux**, PowerShell logs to **syslog** and **rsyslog.conf** can be used.</span></span> <span data-ttu-id="78fb7-112">Para obter mais informações, consulte as páginas locais do computador Linux `man` .</span><span class="sxs-lookup"><span data-stu-id="78fb7-112">For more information, refer to the Linux computer's local `man` pages.</span></span> <span data-ttu-id="78fb7-113">No **MacOS**, o sistema de log de **os_log** é usado.</span><span class="sxs-lookup"><span data-stu-id="78fb7-113">On **macOS**, the **os_log** logging system is used.</span></span> <span data-ttu-id="78fb7-114">Para obter mais informações, consulte [os_log documentação do desenvolvedor](https://developer.apple.com/documentation/os/os_log).</span><span class="sxs-lookup"><span data-stu-id="78fb7-114">For more information, see [os_log developer documentation](https://developer.apple.com/documentation/os/os_log).</span></span>

## <a name="viewing-powershell-log-output-on-linux"></a><span data-ttu-id="78fb7-115">Exibindo a saída de log do PowerShell no Linux</span><span class="sxs-lookup"><span data-stu-id="78fb7-115">Viewing PowerShell log output on Linux</span></span>

<span data-ttu-id="78fb7-116">Os logs do PowerShell para **syslog** no Linux e qualquer uma das ferramentas normalmente usadas para exibir o conteúdo do **syslog** podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="78fb7-116">PowerShell logs to **syslog** on Linux and any of the tools commonly used to view **syslog** contents may be used.</span></span>

<span data-ttu-id="78fb7-117">O formato das entradas de log usa o seguinte modelo:</span><span class="sxs-lookup"><span data-stu-id="78fb7-117">The format of the log entries uses the following template:</span></span>

```
TIMESTAMP MACHINENAME powershell[PID]: (COMMITID:TID:CID)
  [EVENTID:TASK.OPCODE.LEVEL] MESSAGE
```

|<span data-ttu-id="78fb7-118">Campo</span><span class="sxs-lookup"><span data-stu-id="78fb7-118">Field</span></span>        |<span data-ttu-id="78fb7-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="78fb7-119">Description</span></span>                                             |
|-------------|--------------------------------------------------------|
|`TIMESTAMP`  |<span data-ttu-id="78fb7-120">Uma data/hora em que a entrada de log foi produzida.</span><span class="sxs-lookup"><span data-stu-id="78fb7-120">A date/time when the log entry was produced.</span></span>            |
|`MACHINENAME`|<span data-ttu-id="78fb7-121">O nome do sistema em que o log foi produzido.</span><span class="sxs-lookup"><span data-stu-id="78fb7-121">The name of the system where the log was produced.</span></span>      |
|`PID`        |<span data-ttu-id="78fb7-122">A ID do processo que gravou a entrada de log.</span><span class="sxs-lookup"><span data-stu-id="78fb7-122">The process ID of the process that wrote the log entry.</span></span> |
|`COMMITID`   |<span data-ttu-id="78fb7-123">A `git commit` ID ou a marca usada para produzir a compilação.</span><span class="sxs-lookup"><span data-stu-id="78fb7-123">The `git commit` ID or tag used to produce the build.</span></span>   |
|`TID`        |<span data-ttu-id="78fb7-124">A ID de thread do thread que gravou a entrada de log.</span><span class="sxs-lookup"><span data-stu-id="78fb7-124">The thread ID of the thread that wrote the log entry.</span></span>   |
|`CID`        |<span data-ttu-id="78fb7-125">O identificador do canal hex da entrada de log.</span><span class="sxs-lookup"><span data-stu-id="78fb7-125">The hex channel identifier of the log entry.</span></span>            |
|             |<span data-ttu-id="78fb7-126">10 = operacional, 11 = análise</span><span class="sxs-lookup"><span data-stu-id="78fb7-126">10 = Operational, 11 = Analytic</span></span>                         |
|`EVENTID`    |<span data-ttu-id="78fb7-127">O identificador de evento da entrada de log.</span><span class="sxs-lookup"><span data-stu-id="78fb7-127">The event identifier of the log entry.</span></span>                  |
|`TASK`       |<span data-ttu-id="78fb7-128">O identificador da tarefa para a entrada do evento</span><span class="sxs-lookup"><span data-stu-id="78fb7-128">The task identifier for the event entry</span></span>                 |
|`OPCODE`     |<span data-ttu-id="78fb7-129">O opcode para a entrada do evento</span><span class="sxs-lookup"><span data-stu-id="78fb7-129">The opcode for the event entry</span></span>                          |
|`LEVEL`      |<span data-ttu-id="78fb7-130">O nível de log para a entrada do evento</span><span class="sxs-lookup"><span data-stu-id="78fb7-130">The log level for the event entry</span></span>                       |
|`MESSAGE`    |<span data-ttu-id="78fb7-131">A mensagem associada à entrada do evento</span><span class="sxs-lookup"><span data-stu-id="78fb7-131">The message associated with the event entry</span></span>             |

> [!NOTE]
> <span data-ttu-id="78fb7-132">`EVENTID`, `TASK` , `OPCODE` e `LEVEL` são os mesmos valores usados ao fazer logon no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="78fb7-132">`EVENTID`, `TASK`, `OPCODE`, and `LEVEL` are the same values as used when logging to the Windows event log.</span></span>

### <a name="filtering-powershell-log-entries-using-rsyslog"></a><span data-ttu-id="78fb7-133">Filtrando entradas de log do PowerShell usando rsyslog</span><span class="sxs-lookup"><span data-stu-id="78fb7-133">Filtering PowerShell log entries using rsyslog</span></span>

<span data-ttu-id="78fb7-134">Normalmente, as entradas de log do PowerShell são gravadas no padrão `location/file` para **syslog**.</span><span class="sxs-lookup"><span data-stu-id="78fb7-134">Normally, PowerShell log entries are written to the default `location/file` for **syslog**.</span></span> <span data-ttu-id="78fb7-135">No entanto, é possível redirecionar as entradas para um arquivo personalizado.</span><span class="sxs-lookup"><span data-stu-id="78fb7-135">However, it's possible to redirect the entries to a custom file.</span></span>

1. <span data-ttu-id="78fb7-136">Crie uma conf para a configuração de log do PowerShell e forneça um número menor que 50 (para `50-default.conf` ), como `40-powershell.conf` .</span><span class="sxs-lookup"><span data-stu-id="78fb7-136">Create a conf for PowerShell log configuration and provide a number that's less than 50 (for `50-default.conf`), such as `40-powershell.conf`.</span></span> <span data-ttu-id="78fb7-137">O arquivo deve ser colocado em `/etc/rsyslog.d` .</span><span class="sxs-lookup"><span data-stu-id="78fb7-137">The file should be placed under `/etc/rsyslog.d`.</span></span>

1. <span data-ttu-id="78fb7-138">Adicione a seguinte entrada ao arquivo:</span><span class="sxs-lookup"><span data-stu-id="78fb7-138">Add the following entry to the file:</span></span>

   ```
   :syslogtag, contains, "powershell[" /var/log/powershell.log
   & stop
   ```

1. <span data-ttu-id="78fb7-139">Certifique-se `/etc/rsyslog.conf` de que o inclui o novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="78fb7-139">Make sure `/etc/rsyslog.conf` includes the new file.</span></span> <span data-ttu-id="78fb7-140">Geralmente, ele terá uma instrução include genérica semelhante à seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="78fb7-140">Often, it will have a generic include statement that looks like following configuration:</span></span>

   `$IncludeConfig /etc/rsyslog.d/*.conf`

   <span data-ttu-id="78fb7-141">Caso contrário, você precisará adicionar uma instrução include manualmente.</span><span class="sxs-lookup"><span data-stu-id="78fb7-141">If it doesn't, you'll need to add an include statement manually.</span></span>

1. <span data-ttu-id="78fb7-142">Verifique se os atributos e as permissões estão definidos adequadamente.</span><span class="sxs-lookup"><span data-stu-id="78fb7-142">Make sure attributes and permissions are set appropriately.</span></span>

   ```
   -rw-r--r-- 1 root root   67 Nov 28 12:51 40-powershell.conf
   ```

1. <span data-ttu-id="78fb7-143">Defina a propriedade como **raiz**.</span><span class="sxs-lookup"><span data-stu-id="78fb7-143">Set ownership to **root**.</span></span>

   ```
   chown root:root /etc/rsyslog.d/40-powershell.conf
   ```

1. <span data-ttu-id="78fb7-144">Definir permissões de acesso: a **raiz** tem leitura/gravação, **os usuários** têm lido.</span><span class="sxs-lookup"><span data-stu-id="78fb7-144">Set access permissions: **root** has read/write, **users** have read.</span></span>

   ```
   chmod 644 /etc/rsyslog.d/40-powershell.conf
   ```

## <a name="viewing-powershell-log-output-on-macos"></a><span data-ttu-id="78fb7-145">Exibindo a saída de log do PowerShell no macOS</span><span class="sxs-lookup"><span data-stu-id="78fb7-145">Viewing PowerShell log output on macOS</span></span>

<span data-ttu-id="78fb7-146">O método mais fácil para exibir a saída de log do PowerShell no macOS é usando o aplicativo de **console** .</span><span class="sxs-lookup"><span data-stu-id="78fb7-146">The easiest method for viewing PowerShell log output on macOS is using the **Console** application.</span></span>

1. <span data-ttu-id="78fb7-147">Pesquise o aplicativo de **console** e inicie-o.</span><span class="sxs-lookup"><span data-stu-id="78fb7-147">Search for the **Console** application and launch it.</span></span>
1. <span data-ttu-id="78fb7-148">Selecione o nome do computador em **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="78fb7-148">Select the Machine name under **Devices**.</span></span>
1. <span data-ttu-id="78fb7-149">No campo de **pesquisa** , insira `pwsh` para o binário principal do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78fb7-149">In the **Search** field, enter `pwsh` for the PowerShell main binary.</span></span>
1. <span data-ttu-id="78fb7-150">Altere o filtro de pesquisa de `Any` para `Process` .</span><span class="sxs-lookup"><span data-stu-id="78fb7-150">Change the search filter from `Any` to `Process`.</span></span>
1. <span data-ttu-id="78fb7-151">Execute as operações.</span><span class="sxs-lookup"><span data-stu-id="78fb7-151">Perform the operations.</span></span>
1. <span data-ttu-id="78fb7-152">Opcionalmente, salve a pesquisa para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="78fb7-152">Optionally, save the search for future use.</span></span>

<span data-ttu-id="78fb7-153">Para filtrar em uma instância de processo específica do PowerShell no **console** do, a variável `$pid` contém a ID do processo.</span><span class="sxs-lookup"><span data-stu-id="78fb7-153">To filter on a specific process instance of PowerShell in the **Console**, the variable `$pid` contains the process ID.</span></span>

1. <span data-ttu-id="78fb7-154">Insira o **pid** (ID do processo) no campo de **pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="78fb7-154">Enter the **pid** (Process ID) in the **Search** field.</span></span>
1. <span data-ttu-id="78fb7-155">Altere o filtro de pesquisa para `PID` .</span><span class="sxs-lookup"><span data-stu-id="78fb7-155">Change the search filter to `PID`.</span></span>
1. <span data-ttu-id="78fb7-156">Execute as operações.</span><span class="sxs-lookup"><span data-stu-id="78fb7-156">Perform the operations.</span></span>

### <a name="viewing-powershell-log-output-from-a-command-line"></a><span data-ttu-id="78fb7-157">Exibindo a saída de log do PowerShell de uma linha de comando</span><span class="sxs-lookup"><span data-stu-id="78fb7-157">Viewing PowerShell log output from a command line</span></span>

<span data-ttu-id="78fb7-158">O `log` comando pode ser usado para exibir entradas de log do PowerShell na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="78fb7-158">The `log` command can be used to view PowerShell log entries from the command line.</span></span>

```
sudo log stream --predicate 'process == "pwsh"' --info
```

### <a name="persisting-powershell-log-output"></a><span data-ttu-id="78fb7-159">Persistindo a saída de log do PowerShell</span><span class="sxs-lookup"><span data-stu-id="78fb7-159">Persisting PowerShell log output</span></span>

<span data-ttu-id="78fb7-160">Por padrão, o PowerShell usa o log somente de memória padrão no macOS.</span><span class="sxs-lookup"><span data-stu-id="78fb7-160">By default, PowerShell uses the default memory-only logging on macOS.</span></span> <span data-ttu-id="78fb7-161">Esse comportamento pode ser alterado para habilitar a persistência usando o `log config` comando.</span><span class="sxs-lookup"><span data-stu-id="78fb7-161">This behavior can be changed to enable persistence using the `log config` command.</span></span>

<span data-ttu-id="78fb7-162">O script a seguir habilita o registro em nível de informação e a persistência:</span><span class="sxs-lookup"><span data-stu-id="78fb7-162">The following script enables info level logging and persistence:</span></span>

```
log config --subsystem com.microsoft.powershell --mode=persist:info,level:info
```

<span data-ttu-id="78fb7-163">O comando a seguir reverte o log do PowerShell para o estado padrão:</span><span class="sxs-lookup"><span data-stu-id="78fb7-163">The following command reverts PowerShell logging to the default state:</span></span>

```
log config --subsystem com.microsoft.powershell --mode=persist:default,level:default
```

<span data-ttu-id="78fb7-164">Depois que a persistência é habilitada, o `log show` comando pode ser usado para exportar itens de log.</span><span class="sxs-lookup"><span data-stu-id="78fb7-164">After persistence is enabled, the `log show` command can be used to export log items.</span></span> <span data-ttu-id="78fb7-165">O comando fornece opções para exportar os últimos N itens, itens desde um determinado tempo ou itens dentro de um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="78fb7-165">The command provides options for exporting the last N items, items since a given time, or items within a given time span.</span></span>

<span data-ttu-id="78fb7-166">Por exemplo, o comando a seguir exporta itens desde o `9am on April 5 of 2018` :</span><span class="sxs-lookup"><span data-stu-id="78fb7-166">For example, the following command exports items since `9am on April 5 of 2018`:</span></span>

```
log show --info --start "2018-04-05 09:00:00" --predicate "process = 'pwsh'"
```

<span data-ttu-id="78fb7-167">Você pode obter ajuda para o `log` executando `log show --help` para obter detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="78fb7-167">You can get help for `log` by running `log show --help` for additional details.</span></span>

> [!TIP]
> <span data-ttu-id="78fb7-168">Ao executar qualquer um dos comandos de log de um prompt ou script do PowerShell, use aspas duplas em toda a cadeia de caracteres de predicado e aspas simples no.</span><span class="sxs-lookup"><span data-stu-id="78fb7-168">When executing any of the log commands from a PowerShell prompt or script, use double quotes around the entire predicate string and single quotes within.</span></span> <span data-ttu-id="78fb7-169">Isso evita a necessidade de escapar caracteres de aspas duplas dentro da cadeia de caracteres de predicado.</span><span class="sxs-lookup"><span data-stu-id="78fb7-169">This avoids the need to escape double quote characters within the predicate string.</span></span>

<span data-ttu-id="78fb7-170">Talvez você também queira salvar os logs de eventos em um local mais seguro, como um coletor de log de eventos central ou um agregador [Siem][] .</span><span class="sxs-lookup"><span data-stu-id="78fb7-170">You may also want to consider saving the event logs to a more secure location such as a central event log collector, or [SIEM][] aggregator.</span></span> <span data-ttu-id="78fb7-171">Você pode configurar o SIEM no Azure.</span><span class="sxs-lookup"><span data-stu-id="78fb7-171">You can set up SIEM in Azure.</span></span> <span data-ttu-id="78fb7-172">Para obter mais informações, consulte [integração de Siem genérico](/cloud-app-security/siem).</span><span class="sxs-lookup"><span data-stu-id="78fb7-172">For more information, see [Generic SIEM integration](/cloud-app-security/siem).</span></span>

## <a name="configuring-logging-on-a-non-windows-system"></a><span data-ttu-id="78fb7-173">Configurando o log em um sistema não Windows</span><span class="sxs-lookup"><span data-stu-id="78fb7-173">Configuring logging on a non-Windows system</span></span>

<span data-ttu-id="78fb7-174">No Windows, o registro em log é configurado Criando ouvintes de rastreamento ETW ou usando o Visualizador de Eventos para habilitar o log analítico.</span><span class="sxs-lookup"><span data-stu-id="78fb7-174">On Windows, logging is configured by creating ETW trace listeners or by using the Event Viewer to enable Analytic logging.</span></span> <span data-ttu-id="78fb7-175">No Linux e no macOS, o registro em log é configurado usando o arquivo `powershell.config.json` .</span><span class="sxs-lookup"><span data-stu-id="78fb7-175">On Linux and macOS, logging is configured using the file `powershell.config.json`.</span></span> <span data-ttu-id="78fb7-176">O restante desta seção discutirá a configuração do log do PowerShell em um sistema que não seja do Windows.</span><span class="sxs-lookup"><span data-stu-id="78fb7-176">The rest of this section will discuss configuring PowerShell logging on a non-Windows system.</span></span>

<span data-ttu-id="78fb7-177">Por padrão, o PowerShell habilita o log informativo para o canal operacional.</span><span class="sxs-lookup"><span data-stu-id="78fb7-177">By default, PowerShell enables informational logging to the operational channel.</span></span> <span data-ttu-id="78fb7-178">Isso significa que qualquer saída de log produzida pelo PowerShell que está marcada como operacional e tem um nível de log (rastreamento) maior que o informativo será registrado.</span><span class="sxs-lookup"><span data-stu-id="78fb7-178">What this means is any log output produced by PowerShell that is marked as operational and has a log (trace) level greater than informational will be logged.</span></span> <span data-ttu-id="78fb7-179">Ocasionalmente, os diagnósticos podem exigir uma saída de log adicional, como a saída de log detalhada ou a habilitação da saída de log analítico.</span><span class="sxs-lookup"><span data-stu-id="78fb7-179">Occasionally, diagnoses may require additional log output, such as verbose log output or enabling analytic log output.</span></span>

<span data-ttu-id="78fb7-180">O arquivo `powershell.config.json` é um arquivo **JSON** formatado que reside no diretório do PowerShell `$PSHOME` .</span><span class="sxs-lookup"><span data-stu-id="78fb7-180">The file `powershell.config.json` is a **JSON** formatted file residing in the PowerShell `$PSHOME` directory.</span></span> <span data-ttu-id="78fb7-181">Cada instalação do PowerShell usa sua própria cópia desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="78fb7-181">Each installation of PowerShell uses its own copy of this file.</span></span> <span data-ttu-id="78fb7-182">Para a operação normal, esse arquivo permanece inalterado.</span><span class="sxs-lookup"><span data-stu-id="78fb7-182">For normal operation, this file is left unchanged.</span></span> <span data-ttu-id="78fb7-183">Embora possa ser útil, alterar algumas das configurações no arquivo, para diagnóstico ou para distinguir entre várias versões do PowerShell no mesmo sistema ou até mesmo várias cópias da mesma versão (consulte `LogIdentity` a tabela abaixo).</span><span class="sxs-lookup"><span data-stu-id="78fb7-183">Although it can be useful, to change some of the settings in the file, for diagnosis or for distinguishing between multiple PowerShell versions on the same system or even multiple copies of the same version (See `LogIdentity` in the table below).</span></span>

<span data-ttu-id="78fb7-184">O código a seguir é uma configuração de exemplo:</span><span class="sxs-lookup"><span data-stu-id="78fb7-184">The following code is an example configuration:</span></span>

```json
{
  "Microsoft.PowerShell:ExecutionPolicy": "RemoteSigned",
  "PowerShellPolicies": {
    "ScriptExecution": {
      "ExecutionPolicy": "RemoteSigned",
      "EnableScripts": true
    },
    "ScriptBlockLogging": {
      "EnableScriptBlockInvocationLogging": true,
      "EnableScriptBlockLogging": true
    },
    "ModuleLogging": {
      "EnableModuleLogging": false,
      "ModuleNames": [
        "PSReadline",
        "PowerShellGet"
      ]
    },
    "ProtectedEventLogging": {
      "EnableProtectedEventLogging": false,
      "EncryptionCertificate": [
        "Joe"
      ]
    },
    "Transcription": {
      "EnableTranscripting": true,
      "EnableInvocationHeader": true,
      "OutputDirectory": "F:\\tmp\\new"
    },
    "UpdatableHelp": {
      "DefaultSourcePath": "f:\\temp"
    },
    "ConsoleSessionConfiguration": {
      "EnableConsoleSessionConfiguration": false,
      "ConsoleSessionConfigurationName": "name"
    }
  },
  "LogLevel": "verbose"
}
```

<span data-ttu-id="78fb7-185">As propriedades para configurar o log do PowerShell são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="78fb7-185">The properties for configuring PowerShell logging are listed in the following table.</span></span> <span data-ttu-id="78fb7-186">Valores marcados com um asterisco, como `Operational*` , indicam o valor padrão quando nenhum valor é fornecido no arquivo.</span><span class="sxs-lookup"><span data-stu-id="78fb7-186">Values marked with an asterisk, such as `Operational*`, indicate the default value when no value is provided in the file.</span></span>

|<span data-ttu-id="78fb7-187">Propriedade</span><span class="sxs-lookup"><span data-stu-id="78fb7-187">Property</span></span>   |<span data-ttu-id="78fb7-188">Valores</span><span class="sxs-lookup"><span data-stu-id="78fb7-188">Values</span></span>        |<span data-ttu-id="78fb7-189">Descrição</span><span class="sxs-lookup"><span data-stu-id="78fb7-189">Description</span></span>                                  |
|-----------|--------------|---------------------------------------------|
|`LogIdentity`|<span data-ttu-id="78fb7-190">(nome da cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="78fb7-190">(string name)</span></span> |<span data-ttu-id="78fb7-191">O nome a ser usado ao registrar em log.</span><span class="sxs-lookup"><span data-stu-id="78fb7-191">The name to use when logging.</span></span> <span data-ttu-id="78fb7-192">Por padrão, o</span><span class="sxs-lookup"><span data-stu-id="78fb7-192">By default,</span></span>  |
|           |<span data-ttu-id="78fb7-193">PowerShell</span><span class="sxs-lookup"><span data-stu-id="78fb7-193">powershell\*</span></span>   |<span data-ttu-id="78fb7-194">o PowerShell é a identidade.</span><span class="sxs-lookup"><span data-stu-id="78fb7-194">powershell is the identity.</span></span> <span data-ttu-id="78fb7-195">Esse valor pode ser </span><span class="sxs-lookup"><span data-stu-id="78fb7-195">This value can be</span></span>|
|           |              |<span data-ttu-id="78fb7-196">usado para informar a diferença entre dois</span><span class="sxs-lookup"><span data-stu-id="78fb7-196">used to tell the difference between two</span></span>      |
|           |              |<span data-ttu-id="78fb7-197">instâncias de uma instalação do PowerShell, como</span><span class="sxs-lookup"><span data-stu-id="78fb7-197">instances of a PowerShell installation, such</span></span> |
|           |              |<span data-ttu-id="78fb7-198">como versão beta e liberação.</span><span class="sxs-lookup"><span data-stu-id="78fb7-198">as a release and beta version.</span></span> <span data-ttu-id="78fb7-199">Esse valor é</span><span class="sxs-lookup"><span data-stu-id="78fb7-199">This value is</span></span> |
|           |              |<span data-ttu-id="78fb7-200">também usado para redirecionar a saída de log para um</span><span class="sxs-lookup"><span data-stu-id="78fb7-200">also used to redirect log output to a</span></span>        |
|           |              |<span data-ttu-id="78fb7-201">arquivo separado no Linux.</span><span class="sxs-lookup"><span data-stu-id="78fb7-201">separate file on Linux.</span></span> <span data-ttu-id="78fb7-202">Consulte a discussão de</span><span class="sxs-lookup"><span data-stu-id="78fb7-202">See the discussion of</span></span>|
|           |              |<span data-ttu-id="78fb7-203">**rsyslog** acima.</span><span class="sxs-lookup"><span data-stu-id="78fb7-203">**rsyslog** above.</span></span>                           |
|`LogChannels`|<span data-ttu-id="78fb7-204">Eficiência</span><span class="sxs-lookup"><span data-stu-id="78fb7-204">Operational\*</span></span>  |<span data-ttu-id="78fb7-205">Os canais a serem habilitados.</span><span class="sxs-lookup"><span data-stu-id="78fb7-205">The channels to enable.</span></span> <span data-ttu-id="78fb7-206">Separar os valores</span><span class="sxs-lookup"><span data-stu-id="78fb7-206">Separate the values</span></span>|
|           |<span data-ttu-id="78fb7-207">Analítico</span><span class="sxs-lookup"><span data-stu-id="78fb7-207">Analytic</span></span>      |<span data-ttu-id="78fb7-208">com uma vírgula ao especificar mais de um.</span><span class="sxs-lookup"><span data-stu-id="78fb7-208">with a comma when specifying more than one.</span></span>  |
|`LogLevel`   |<span data-ttu-id="78fb7-209">Sempre</span><span class="sxs-lookup"><span data-stu-id="78fb7-209">Always</span></span>        |<span data-ttu-id="78fb7-210">Especifique um único valor.</span><span class="sxs-lookup"><span data-stu-id="78fb7-210">Specify a single value.</span></span> <span data-ttu-id="78fb7-211">O valor habilita</span><span class="sxs-lookup"><span data-stu-id="78fb7-211">The value enables</span></span>  |
|           |<span data-ttu-id="78fb7-212">Crítico</span><span class="sxs-lookup"><span data-stu-id="78fb7-212">Critical</span></span>      |<span data-ttu-id="78fb7-213">a si mesmo e todos os valores acima dele no</span><span class="sxs-lookup"><span data-stu-id="78fb7-213">itself and all values above it in the</span></span>        |
|           |<span data-ttu-id="78fb7-214">Erro do</span><span class="sxs-lookup"><span data-stu-id="78fb7-214">Error</span></span>         |<span data-ttu-id="78fb7-215">lista à esquerda.</span><span class="sxs-lookup"><span data-stu-id="78fb7-215">list to the left.</span></span>                            |
|           |<span data-ttu-id="78fb7-216">Aviso</span><span class="sxs-lookup"><span data-stu-id="78fb7-216">Warning</span></span>       |                                             |
|           |<span data-ttu-id="78fb7-217">Informativa</span><span class="sxs-lookup"><span data-stu-id="78fb7-217">Informational\*</span></span>|                                             |
|           |<span data-ttu-id="78fb7-218">Detalhado</span><span class="sxs-lookup"><span data-stu-id="78fb7-218">Verbose</span></span>       |                                             |
|           |<span data-ttu-id="78fb7-219">Depurar</span><span class="sxs-lookup"><span data-stu-id="78fb7-219">Debug</span></span>         |                                             |
|`LogKeywords`|<span data-ttu-id="78fb7-220">Runspace</span><span class="sxs-lookup"><span data-stu-id="78fb7-220">Runspace</span></span>      |<span data-ttu-id="78fb7-221">As palavras-chave fornecem a capacidade de limitar o registro em log</span><span class="sxs-lookup"><span data-stu-id="78fb7-221">Keywords provide the ability to limit logging</span></span>|
|           |<span data-ttu-id="78fb7-222">Pipeline</span><span class="sxs-lookup"><span data-stu-id="78fb7-222">Pipeline</span></span>      |<span data-ttu-id="78fb7-223">para componentes específicos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78fb7-223">to specific components within PowerShell.</span></span> <span data-ttu-id="78fb7-224">Por</span><span class="sxs-lookup"><span data-stu-id="78fb7-224">By</span></span> |
|           |<span data-ttu-id="78fb7-225">Protocolo</span><span class="sxs-lookup"><span data-stu-id="78fb7-225">Protocol</span></span>      |<span data-ttu-id="78fb7-226">padrão, todas as palavras-chave são habilitadas e alteradas</span><span class="sxs-lookup"><span data-stu-id="78fb7-226">default, all keywords are enabled and change</span></span> |
|           |<span data-ttu-id="78fb7-227">Transport</span><span class="sxs-lookup"><span data-stu-id="78fb7-227">Transport</span></span>     |<span data-ttu-id="78fb7-228">Esse valor só é útil para</span><span class="sxs-lookup"><span data-stu-id="78fb7-228">this value is only useful for very</span></span>           |
|           |<span data-ttu-id="78fb7-229">Host</span><span class="sxs-lookup"><span data-stu-id="78fb7-229">Host</span></span>          |<span data-ttu-id="78fb7-230">solução de problemas especializada.</span><span class="sxs-lookup"><span data-stu-id="78fb7-230">specialized troubleshooting.</span></span>                |
|           |<span data-ttu-id="78fb7-231">Cmdlets</span><span class="sxs-lookup"><span data-stu-id="78fb7-231">Cmdlets</span></span>       |                                             |
|           |<span data-ttu-id="78fb7-232">serializador</span><span class="sxs-lookup"><span data-stu-id="78fb7-232">Serializer</span></span>    |                                             |
|           |<span data-ttu-id="78fb7-233">Sessão</span><span class="sxs-lookup"><span data-stu-id="78fb7-233">Session</span></span>       |                                             |
|           |<span data-ttu-id="78fb7-234">ManagedPlugin</span><span class="sxs-lookup"><span data-stu-id="78fb7-234">ManagedPlugin</span></span> |                                             |

## <a name="see-also"></a><span data-ttu-id="78fb7-235">Consulte também</span><span class="sxs-lookup"><span data-stu-id="78fb7-235">See also</span></span>

<span data-ttu-id="78fb7-236">Para obter informações sobre o **syslog** do Linux e o **rsyslog. conf** , consulte as páginas locais do computador Linux `man` .</span><span class="sxs-lookup"><span data-stu-id="78fb7-236">For Linux **syslog** and **rsyslog.conf** information, refer to the Linux computer's local `man` pages.</span></span>

<span data-ttu-id="78fb7-237">Para obter informações sobre o macOS **os_log** , consulte [os_log documentação do desenvolvedor](https://developer.apple.com/documentation/os/os_log).</span><span class="sxs-lookup"><span data-stu-id="78fb7-237">For macOS **os_log** information, see [os_log developer documentation](https://developer.apple.com/documentation/os/os_log).</span></span>

[<span data-ttu-id="78fb7-238">about_Logging_Windows</span><span class="sxs-lookup"><span data-stu-id="78fb7-238">about_Logging_Windows</span></span>](about_Logging_Windows.md)

[<span data-ttu-id="78fb7-239">Integração genérica ao SIEM</span><span class="sxs-lookup"><span data-stu-id="78fb7-239">Generic SIEM integration</span></span>](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management
