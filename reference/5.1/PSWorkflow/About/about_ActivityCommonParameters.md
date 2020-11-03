---
description: Descreve os parâmetros que o fluxo de trabalho do Windows PowerShell adiciona às atividades.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_activitycommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_ActivityCommonParameters
ms.openlocfilehash: b745bf17e4ae26156042ecdc25211830177bc692
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195813"
---
# <a name="about-activitycommonparameters"></a><span data-ttu-id="9c13b-104">Sobre o ActivityCommonParameters</span><span class="sxs-lookup"><span data-stu-id="9c13b-104">About ActivityCommonParameters</span></span>

## <a name="short-description"></a><span data-ttu-id="9c13b-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="9c13b-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="9c13b-106">Descreve os parâmetros que o fluxo de trabalho do Windows PowerShell adiciona às atividades.</span><span class="sxs-lookup"><span data-stu-id="9c13b-106">Describes the parameters that Windows PowerShell Workflow adds to activities.</span></span>

## <a name="long-description"></a><span data-ttu-id="9c13b-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="9c13b-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="9c13b-108">O fluxo de trabalho do Windows PowerShell adiciona os parâmetros comuns da atividade às atividades derivadas da classe base PSActivity.</span><span class="sxs-lookup"><span data-stu-id="9c13b-108">Windows PowerShell Workflow adds the activity common parameters to activities that are derived from the PSActivity base class.</span></span> <span data-ttu-id="9c13b-109">Essa categoria inclui a atividade InlineScript e os cmdlets do Windows PowerShell que são implementados como atividades, como Get-Process e Get-WinEvent.</span><span class="sxs-lookup"><span data-stu-id="9c13b-109">This category includes the InlineScript activity and Windows PowerShell cmdlets that are implemented as activities, such as Get-Process and Get-WinEvent.</span></span>

<span data-ttu-id="9c13b-110">Os parâmetros comuns da atividade não são válidos nas atividades Suspend-Workflow e Checkpoint-Workflow e não são adicionados a cmdlets ou expressões que o fluxo de trabalho do Windows PowerShell executa automaticamente em um bloco de script InlineScript ou atividade semelhante.</span><span class="sxs-lookup"><span data-stu-id="9c13b-110">The activity common parameters are not valid on the Suspend-Workflow and Checkpoint-Workflow activities and they are not added to cmdlets or expressions that Windows PowerShell Workflow automatically runs in an InlineScript script block or similar activity.</span></span> <span data-ttu-id="9c13b-111">Os parâmetros comuns de atividade estão disponíveis na atividade InlineScript, mas não em comandos do bloco de script InlineScript.</span><span class="sxs-lookup"><span data-stu-id="9c13b-111">The activity common parameters are available on the InlineScript activity, but not on commands in the InlineScript script block.</span></span>

<span data-ttu-id="9c13b-112">Vários parâmetros comuns de atividade também são parâmetros comuns de fluxo de trabalho ou parâmetros comuns do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c13b-112">Several of the activity common parameters are also workflow common parameters or Windows PowerShell common parameters.</span></span> <span data-ttu-id="9c13b-113">Outros parâmetros comuns de atividade são exclusivos das atividades.</span><span class="sxs-lookup"><span data-stu-id="9c13b-113">Other activity common parameters are unique to activities.</span></span>

<span data-ttu-id="9c13b-114">Para obter informações sobre os parâmetros comuns de fluxos de trabalho, consulte about_WorkflowCommonParameters.</span><span class="sxs-lookup"><span data-stu-id="9c13b-114">For information about the workflow common parameters, see about_WorkflowCommonParameters.</span></span> <span data-ttu-id="9c13b-115">Para obter informações sobre os parâmetros comuns do Windows PowerShell, consulte about_CommonParameters.</span><span class="sxs-lookup"><span data-stu-id="9c13b-115">For information about the Windows PowerShell common parameters, see about_CommonParameters.</span></span>

### <a name="list-of-activity-common-parameters"></a><span data-ttu-id="9c13b-116">LISTA DE PARÂMETROS COMUNS DE ATIVIDADE</span><span class="sxs-lookup"><span data-stu-id="9c13b-116">LIST OF ACTIVITY COMMON PARAMETERS</span></span>

```
AppendOutput                      PSDebug
Debug                             PSDisableSerialization
DisplayName                       PSDisableSerializationPreference
ErrorAction                       PSError
Input                             PSPersist
MergeErrorToOutput                PSPort
PSActionRetryCount                PSProgress
PSActionRetryIntervalSec          PSProgressMessage
PSActionRunningTimeoutSec         PSRemotingBehavior
PSApplicationName                 PSRequiredModules
PSAuthentication                  PSSessionOption
PSCertificateThumbprint           PSUseSSL
PSComputerName                    PSVerbose
PSConfigurationName               PSWarning
PSConnectionRetryCount            Result
PSConnectionRetryIntervalSec      UseDefaultInput
PSConnectionURI                   Verbose
PSCredential                      WarningAction
```

### <a name="parameter-descriptions"></a><span data-ttu-id="9c13b-117">DESCRIÇÕES DE PARÂMETROS</span><span class="sxs-lookup"><span data-stu-id="9c13b-117">PARAMETER DESCRIPTIONS</span></span>

<span data-ttu-id="9c13b-118">Esta seção descreve os parâmetros comuns da atividade.</span><span class="sxs-lookup"><span data-stu-id="9c13b-118">This section describes the activity common parameters.</span></span>

#### <a name="appendoutput-boolean"></a><span data-ttu-id="9c13b-119">AppendOutput \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="9c13b-119">AppendOutput \<Boolean\></span></span>

<span data-ttu-id="9c13b-120">Um valor de `$True` adiciona a saída da atividade ao valor da variável.</span><span class="sxs-lookup"><span data-stu-id="9c13b-120">A value of `$True` adds the output of the activity to the value of the variable.</span></span>
<span data-ttu-id="9c13b-121">Um valor de `$False` não tem nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="9c13b-121">A value of `$False` has no effect.</span></span> <span data-ttu-id="9c13b-122">De modo padrão, atribuir um valor a uma variável substitui o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="9c13b-122">By default, assigning a value to a variable replaces the variable value.</span></span>

<span data-ttu-id="9c13b-123">Por exemplo, os comandos a seguir adicionam um objeto de processo ao objeto de serviço na `$x` variável.</span><span class="sxs-lookup"><span data-stu-id="9c13b-123">For example, the following commands add a process object to the service object in the `$x` variable.</span></span>

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x = Get-Process -AppendOutput $true
}
```

<span data-ttu-id="9c13b-124">Esse parâmetro é projetado para fluxos de trabalho baseados em XAML.</span><span class="sxs-lookup"><span data-stu-id="9c13b-124">This parameter is designed for XAML-based workflows.</span></span> <span data-ttu-id="9c13b-125">Em fluxos de trabalho de script, você também pode usar o operador de atribuição + = para adicionar saída ao valor de uma variável, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="9c13b-125">In script workflows, you can also use the += assignment operator to add output to the value of a variable, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x += Get-Process
}
```

#### <a name="debug-switchparameter"></a><span data-ttu-id="9c13b-126">Verificação \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="9c13b-126">Debug \<SwitchParameter\></span></span>

<span data-ttu-id="9c13b-127">Exibe detalhes no nível do programador sobre a operação executada pelo comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-127">Displays programmer-level detail about the operation performed by the command.</span></span>
<span data-ttu-id="9c13b-128">O parâmetro Debug substitui o valor da variável $DebugPreference para o comando atual.</span><span class="sxs-lookup"><span data-stu-id="9c13b-128">The Debug parameter overrides the value of the $DebugPreference variable for the current command.</span></span> <span data-ttu-id="9c13b-129">Esse parâmetro funciona somente quando o comando gera mensagens de depuração.</span><span class="sxs-lookup"><span data-stu-id="9c13b-129">This parameter works only when the command generates debugging messages.</span></span> <span data-ttu-id="9c13b-130">Esse parâmetro também é um parâmetro comum do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c13b-130">This parameter is also a Windows PowerShell common parameter.</span></span>

#### <a name="displayname-string"></a><span data-ttu-id="9c13b-131">DisplayName \<String\></span><span class="sxs-lookup"><span data-stu-id="9c13b-131">DisplayName \<String\></span></span>

<span data-ttu-id="9c13b-132">Especifica um nome amigável para a atividade.</span><span class="sxs-lookup"><span data-stu-id="9c13b-132">Specifies a friendly name for the activity.</span></span> <span data-ttu-id="9c13b-133">O valor DisplayName é exibido na barra de progresso enquanto o fluxo de trabalho é executado e no valor da Propriedade Progress da tarefa Workflow.</span><span class="sxs-lookup"><span data-stu-id="9c13b-133">The DisplayName value appears in the progress bar while the workflow runs and in the value of the Progress property of the workflow job.</span></span> <span data-ttu-id="9c13b-134">Quando o parâmetro PSProgressMessage também é incluído no comando, o conteúdo da barra de progresso aparece em \<DisplayName\> : \<PSProgressMessage\> Format.</span><span class="sxs-lookup"><span data-stu-id="9c13b-134">When the PSProgressMessage parameter is also included in the command, the progress bar content appears in \<DisplayName\>:\<PSProgressMessage\> format.</span></span>

#### <a name="erroraction-actionpreference"></a><span data-ttu-id="9c13b-135">ErrorAction \<ActionPreference\></span><span class="sxs-lookup"><span data-stu-id="9c13b-135">ErrorAction \<ActionPreference\></span></span>

<span data-ttu-id="9c13b-136">Determina como a atividade responde a um erro de não finalização do comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-136">Determines how the activity responds to a non-terminating error from the command.</span></span> <span data-ttu-id="9c13b-137">Ele não tem nenhum efeito sobre erros de encerramento.</span><span class="sxs-lookup"><span data-stu-id="9c13b-137">It has no effect on termination errors.</span></span> <span data-ttu-id="9c13b-138">Esse parâmetro funciona somente quando o comando gera um erro de não finalização, como os do cmdlet Write-Error.</span><span class="sxs-lookup"><span data-stu-id="9c13b-138">This parameter works only when the command generates a non-terminating error, such as those from the Write-Error cmdlet.</span></span> <span data-ttu-id="9c13b-139">O parâmetro ErrorAction substitui o valor da variável $ErrorActionPreference para o comando atual.</span><span class="sxs-lookup"><span data-stu-id="9c13b-139">The ErrorAction parameter overrides the value of the $ErrorActionPreference variable for the current command.</span></span> <span data-ttu-id="9c13b-140">Esse parâmetro também é um parâmetro comum do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c13b-140">This parameter is also a Windows PowerShell common parameter.</span></span>

<span data-ttu-id="9c13b-141">Valores válidos: </span><span class="sxs-lookup"><span data-stu-id="9c13b-141">Valid values:</span></span>

- <span data-ttu-id="9c13b-142">Continua.</span><span class="sxs-lookup"><span data-stu-id="9c13b-142">Continue.</span></span> <span data-ttu-id="9c13b-143">Exibe a mensagem de erro e continua executando o comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-143">Displays the error message and continues executing the command.</span></span> <span data-ttu-id="9c13b-144">"Continue" é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="9c13b-144">"Continue" is the default value.</span></span>

- <span data-ttu-id="9c13b-145">Ignorar.</span><span class="sxs-lookup"><span data-stu-id="9c13b-145">Ignore.</span></span> <span data-ttu-id="9c13b-146">Suprime a mensagem de erro e continua executando o comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-146">Suppresses the error message and continues executing the command.</span></span>
  <span data-ttu-id="9c13b-147">Ao contrário de SilentlyContinue, ignorar não adiciona a mensagem de erro à $Error variável automática.</span><span class="sxs-lookup"><span data-stu-id="9c13b-147">Unlike SilentlyContinue, Ignore does not add the error message to the $Error automatic variable.</span></span> <span data-ttu-id="9c13b-148">O valor de ignorar é introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="9c13b-148">The Ignore value is introduced in Windows PowerShell 3.0.</span></span>

- <span data-ttu-id="9c13b-149">Inquire.</span><span class="sxs-lookup"><span data-stu-id="9c13b-149">Inquire.</span></span> <span data-ttu-id="9c13b-150">Exibe a mensagem de erro e solicita a confirmação antes de continuar a execução.</span><span class="sxs-lookup"><span data-stu-id="9c13b-150">Displays the error message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="9c13b-151">Esse valor raramente é usado.</span><span class="sxs-lookup"><span data-stu-id="9c13b-151">This value is rarely used.</span></span>

- <span data-ttu-id="9c13b-152">Suspend.</span><span class="sxs-lookup"><span data-stu-id="9c13b-152">Suspend.</span></span> <span data-ttu-id="9c13b-153">Suspende automaticamente uma tarefa de fluxo de trabalho para permitir uma investigação adicional.</span><span class="sxs-lookup"><span data-stu-id="9c13b-153">Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="9c13b-154">Após a investigação, o fluxo de trabalho pode ser retomado.</span><span class="sxs-lookup"><span data-stu-id="9c13b-154">After investigation, the workflow can be resumed.</span></span>

- <span data-ttu-id="9c13b-155">SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="9c13b-155">SilentlyContinue.</span></span> <span data-ttu-id="9c13b-156">Suprime a mensagem de erro e continua executando o comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-156">Suppresses the error message and continues executing the command.</span></span>

- <span data-ttu-id="9c13b-157">Deixar.</span><span class="sxs-lookup"><span data-stu-id="9c13b-157">Stop.</span></span> <span data-ttu-id="9c13b-158">Exibe a mensagem de erro e para a execução do comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-158">Displays the error message and stops executing the command.</span></span>

#### <a name="input-object"></a><span data-ttu-id="9c13b-159">Entrada \<Object[]\></span><span class="sxs-lookup"><span data-stu-id="9c13b-159">Input \<Object[]\></span></span>

<span data-ttu-id="9c13b-160">Envia uma coleção de objetos a uma atividade.</span><span class="sxs-lookup"><span data-stu-id="9c13b-160">Submits a collection of objects to an activity.</span></span> <span data-ttu-id="9c13b-161">Essa é uma alternativa ao redirecionamento de objetos para a atividade, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="9c13b-161">This is an alternative to piping objects to the activity one at a time.</span></span>

#### <a name="mergeerrortooutput-boolean"></a><span data-ttu-id="9c13b-162">MergeErrorToOutput \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="9c13b-162">MergeErrorToOutput \<Boolean\></span></span>

<span data-ttu-id="9c13b-163">Um valor de `$True` adiciona erros ao fluxo de saída.</span><span class="sxs-lookup"><span data-stu-id="9c13b-163">A value of `$True` adds errors to the output stream.</span></span> <span data-ttu-id="9c13b-164">Um valor de `$False` não tem efeito.</span><span class="sxs-lookup"><span data-stu-id="9c13b-164">A value of `$False` has not effect.</span></span> <span data-ttu-id="9c13b-165">Use esse parâmetro com as `ForEach -Parallel` palavras-chave e paralelas para coletar erros e saída de vários comandos paralelos em uma única coleção.</span><span class="sxs-lookup"><span data-stu-id="9c13b-165">Use this parameter with the Parallel and `ForEach -Parallel` keywords to collect errors and output from multiple parallel commands in a single collection.</span></span>

#### <a name="psactionretrycount-int32"></a><span data-ttu-id="9c13b-166">PSActionRetryCount \<Int32\></span><span class="sxs-lookup"><span data-stu-id="9c13b-166">PSActionRetryCount \<Int32\></span></span>

<span data-ttu-id="9c13b-167">Tenta repetidamente executar a atividade, caso a primeira tentativa falhe.</span><span class="sxs-lookup"><span data-stu-id="9c13b-167">Tries repeatedly to run the activity if the first attempt fails.</span></span> <span data-ttu-id="9c13b-168">O valor padrão, 0, não tenta novamente.</span><span class="sxs-lookup"><span data-stu-id="9c13b-168">The default value, 0, does not retry.</span></span>

#### <a name="psactionretryintervalsec-int32"></a><span data-ttu-id="9c13b-169">PSActionRetryIntervalSec \<Int32\></span><span class="sxs-lookup"><span data-stu-id="9c13b-169">PSActionRetryIntervalSec \<Int32\></span></span>

<span data-ttu-id="9c13b-170">Determina o intervalo entre as tentativas de ação em segundos.</span><span class="sxs-lookup"><span data-stu-id="9c13b-170">Determines the interval between action retries in seconds.</span></span> <span data-ttu-id="9c13b-171">O valor padrão, 0, repete a ação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="9c13b-171">The default value, 0, retries the action immediately.</span></span> <span data-ttu-id="9c13b-172">Esse parâmetro é válido somente quando o parâmetro PSActionRetryCount também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-172">This parameter is valid only when the PSActionRetryCount parameter is also used in the command.</span></span>

#### <a name="psactionrunningtimeoutsec-int32"></a><span data-ttu-id="9c13b-173">PSActionRunningTimeoutSec \<Int32\></span><span class="sxs-lookup"><span data-stu-id="9c13b-173">PSActionRunningTimeoutSec \<Int32\></span></span>

<span data-ttu-id="9c13b-174">Determina quanto tempo a atividade pode ser executada em cada computador de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-174">Determines how long the activity can run on each target computer.</span></span> <span data-ttu-id="9c13b-175">Se a atividade não for concluída antes do tempo limite expirar, o fluxo de trabalho do Windows PowerShell gerará um erro de encerramento e interromperá o processamento do fluxo de trabalho no computador de destino afetado.</span><span class="sxs-lookup"><span data-stu-id="9c13b-175">If the activity does not complete before the timeout expires, Windows PowerShell Workflow generates a terminating error and stops processing the workflow on the affected target computer.</span></span>

#### <a name="psallowredirection-boolean"></a><span data-ttu-id="9c13b-176">PSAllowRedirection \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="9c13b-176">PSAllowRedirection \<Boolean\></span></span>

<span data-ttu-id="9c13b-177">Um valor de $True permite o redirecionamento da conexão para os computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-177">A value of $True allows redirection of the connection to the target computers.</span></span>
<span data-ttu-id="9c13b-178">Um valor de $False não tem nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="9c13b-178">A value of $False has no effect.</span></span> <span data-ttu-id="9c13b-179">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-179">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="9c13b-180">Quando você usa o parâmetro PSConnectionURI, o destino remoto pode retornar uma instrução para redirecionar para um URI diferente.</span><span class="sxs-lookup"><span data-stu-id="9c13b-180">When you use the PSConnectionURI parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="9c13b-181">Por padrão, o Windows PowerShell não redireciona conexões, mas você pode usar o parâmetro PSAllowRedirection com um valor de $True para permitir o redirecionamento da conexão com o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-181">By default, Windows PowerShell does not redirect connections, but you can use the PSAllowRedirection parameter with a value of $True to allow redirection of the connection to the target computer.</span></span>

<span data-ttu-id="9c13b-182">Você também pode limitar o número de vezes que a conexão é redirecionada definindo a propriedade MaximumConnectionRedirectionCount da variável de `$PSSessionOption` preferência ou a propriedade MaximumConnectionRedirectionCount do valor do parâmetro SSessionOption de cmdlets que criam uma sessão.</span><span class="sxs-lookup"><span data-stu-id="9c13b-182">You can also limit the number of times that the connection is redirected by setting the MaximumConnectionRedirectionCount property of the `$PSSessionOption` preference variable, or the MaximumConnectionRedirectionCount property of the value of the SSessionOption parameter of cmdlets that create a session.</span></span> <span data-ttu-id="9c13b-183">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="9c13b-183">The default value is 5.</span></span>

#### <a name="psapplicationname-string"></a><span data-ttu-id="9c13b-184">PSApplicationName \<String\></span><span class="sxs-lookup"><span data-stu-id="9c13b-184">PSApplicationName \<String\></span></span>

<span data-ttu-id="9c13b-185">Especifica o segmento de nome de aplicativo do URI de conexão que é usado para se conectar aos computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-185">Specifies the application name segment of the connection URI that is used to connect to the target computers.</span></span> <span data-ttu-id="9c13b-186">Use esse parâmetro para especificar o nome do aplicativo quando não estiver usando o parâmetro ConnectionURI no comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-186">Use this parameter to specify the application name when you are not using the ConnectionURI parameter in the command.</span></span> <span data-ttu-id="9c13b-187">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-187">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="9c13b-188">O valor padrão é o valor da `$PSSessionApplicationName` variável de preferência no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-188">The default value is the value of the `$PSSessionApplicationName` preference variable on the target computer.</span></span> <span data-ttu-id="9c13b-189">Se esta variável de preferência não estiver definida, o valor padrão é WSMAN.</span><span class="sxs-lookup"><span data-stu-id="9c13b-189">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="9c13b-190">Esse valor é adequado para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="9c13b-190">This value is appropriate for most uses.</span></span> <span data-ttu-id="9c13b-191">Para obter mais informações, consulte [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9c13b-191">For more information, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="9c13b-192">O serviço WinRM usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão.</span><span class="sxs-lookup"><span data-stu-id="9c13b-192">The WinRM service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="9c13b-193">O valor desse parâmetro deve corresponder ao valor da propriedade URLPrefix de um ouvinte no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9c13b-193">The value of this parameter should match the value of the URLPrefix property of a listener on the remote computer.</span></span>

#### <a name="psauthentication-authenticationmechanism"></a><span data-ttu-id="9c13b-194">PSAuthentication \<AuthenticationMechanism\></span><span class="sxs-lookup"><span data-stu-id="9c13b-194">PSAuthentication \<AuthenticationMechanism\></span></span>

<span data-ttu-id="9c13b-195">Especifica o mecanismo usado para autenticar as credenciais do usuário ao conectar-se aos computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-195">Specifies the mechanism that is used to authenticate the user's credentials when connecting to the target computers.</span></span> <span data-ttu-id="9c13b-196">Os valores válidos são Default, Basic, Credssp, Digest, Kerberos, Negotiate e NegotiateWithImplicitCredential.</span><span class="sxs-lookup"><span data-stu-id="9c13b-196">Valid values are Default, Basic, Credssp, Digest, Kerberos, Negotiate, and NegotiateWithImplicitCredential.</span></span> <span data-ttu-id="9c13b-197">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="9c13b-197">The default value is Default.</span></span> <span data-ttu-id="9c13b-198">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-198">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="9c13b-199">Para obter informações sobre os valores desse parâmetro, consulte a descrição da enumeração **System.Management.Automation.Runspaces.AuthenticationMechanism** no MSDN.</span><span class="sxs-lookup"><span data-stu-id="9c13b-199">For information about the values of this parameter, see the description of the **System.Management.Automation.Runspaces.AuthenticationMechanism** enumeration in MSDN.</span></span>

> [!WARNING]
> <span data-ttu-id="9c13b-200">A autenticação CredSSP (Credencial Security Service Provider), na qual as credenciais do usuário são transmitidas a um computador remoto para autenticação, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remota.</span><span class="sxs-lookup"><span data-stu-id="9c13b-200">Credential Security Service Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="9c13b-201">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="9c13b-201">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="9c13b-202">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="9c13b-202">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

#### <a name="pscertificatethumbprint-string"></a><span data-ttu-id="9c13b-203">PSCertificateThumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="9c13b-203">PSCertificateThumbprint \<String\></span></span>

<span data-ttu-id="9c13b-204">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="9c13b-204">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="9c13b-205">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="9c13b-205">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="9c13b-206">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-206">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="9c13b-207">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="9c13b-207">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="9c13b-208">Eles só podem ser mapeados para contas de usuário local. eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="9c13b-208">They can only be mapped to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="9c13b-209">Para obter um certificado, use os cmdlets [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) ou [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) na unidade CERT: do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c13b-209">To get a certificate, use the [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) or [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) cmdlets in the Windows PowerShell Cert: drive.</span></span>

#### <a name="pscomputername-string"></a><span data-ttu-id="9c13b-210">PSComputerName \<String[]\></span><span class="sxs-lookup"><span data-stu-id="9c13b-210">PSComputerName \<String[]\></span></span>

<span data-ttu-id="9c13b-211">Especifica os computadores de destino nos quais a atividade é executada.</span><span class="sxs-lookup"><span data-stu-id="9c13b-211">Specifies the target computers on which the activity run.</span></span> <span data-ttu-id="9c13b-212">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="9c13b-212">The default is the local computer.</span></span> <span data-ttu-id="9c13b-213">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-213">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="9c13b-214">Digite o nome NETBIOS, o endereço IP ou o nome de domínio totalmente qualificado de um ou mais computadores em uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="9c13b-214">Type the NETBIOS name, IP address, or fully-qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="9c13b-215">Para especificar o computador local, digite o nome do computador, "localhost" ou um ponto (.).</span><span class="sxs-lookup"><span data-stu-id="9c13b-215">To specify the local computer, type the computer name, "localhost", or a dot (.).</span></span>

<span data-ttu-id="9c13b-216">Para incluir o computador local no valor do parâmetro PSComputerName, abra o Windows PowerShell com a opção "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="9c13b-216">To include the local computer in the value of the PSComputerName parameter, open Windows PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="9c13b-217">Se esse parâmetro for omitido do comando ou o valor for $null ou uma cadeia de caracteres vazia, o destino do fluxo de trabalho será o computador local e a comunicação remota do Windows PowerShell não será usada para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-217">If this parameter is omitted from the command, or it value is $null or an empty string, the workflow target is the local computer and Windows PowerShell remoting is not used to run the command.</span></span>

<span data-ttu-id="9c13b-218">Para usar um endereço IP no valor do parâmetro ComputerName, o comando deve incluir o parâmetro PSCredential.</span><span class="sxs-lookup"><span data-stu-id="9c13b-218">To use an IP address in the value of the ComputerName parameter, the command must include the PSCredential parameter.</span></span> <span data-ttu-id="9c13b-219">Além disso, o computador deve ser configurado para o transporte HTTPS ou o endereço IP do computador remoto deve ser incluído na lista WinRM TrustedHosts no computador local.</span><span class="sxs-lookup"><span data-stu-id="9c13b-219">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="9c13b-220">Para obter instruções sobre como adicionar um nome de computador à lista TrustedHosts, consulte "como adicionar um computador à lista de hosts confiáveis" em [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="9c13b-220">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span></span>

#### <a name="psconfigurationname-string"></a><span data-ttu-id="9c13b-221">PSConfigurationName \<String\></span><span class="sxs-lookup"><span data-stu-id="9c13b-221">PSConfigurationName \<String\></span></span>

<span data-ttu-id="9c13b-222">Especifica as configurações de sessão que são usadas para criar sessões nos computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-222">Specifies the session configurations that are used to create sessions on the target computers.</span></span> <span data-ttu-id="9c13b-223">Insira o nome de uma configuração de sessão nos computadores de destino (não no computador que está executando o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-223">Enter the name of a session configuration on the target computers (not on the computer that is running the workflow.</span></span> <span data-ttu-id="9c13b-224">O padrão é Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c13b-224">The default is Microsoft.PowerShell.</span></span> <span data-ttu-id="9c13b-225">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-225">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionretrycount-uint"></a><span data-ttu-id="9c13b-226">PSConnectionRetryCount \<UInt\></span><span class="sxs-lookup"><span data-stu-id="9c13b-226">PSConnectionRetryCount \<UInt\></span></span>

<span data-ttu-id="9c13b-227">Especifica o número máximo de tentativas de conexão com cada computador de destino se a primeira tentativa de conexão falhar.</span><span class="sxs-lookup"><span data-stu-id="9c13b-227">Specifies the maximum number of attempts to connect to each target computer if the first connection attempt fails.</span></span> <span data-ttu-id="9c13b-228">Insira um número entre 1 e 4.294.967.295 (UInt. MaxValue).</span><span class="sxs-lookup"><span data-stu-id="9c13b-228">Enter a number between 1 and 4,294,967,295 (UInt.MaxValue).</span></span> <span data-ttu-id="9c13b-229">O valor padrão, zero (0), não representa novas tentativas.</span><span class="sxs-lookup"><span data-stu-id="9c13b-229">The default value, zero (0), represents no retry attempts.</span></span>
<span data-ttu-id="9c13b-230">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-230">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionretryintervalsec-uint"></a><span data-ttu-id="9c13b-231">PSConnectionRetryIntervalSec \<UInt\></span><span class="sxs-lookup"><span data-stu-id="9c13b-231">PSConnectionRetryIntervalSec \<UInt\></span></span>

<span data-ttu-id="9c13b-232">Especifica o atraso entre as tentativas de repetição de conexão em segundos.</span><span class="sxs-lookup"><span data-stu-id="9c13b-232">Specifies the delay between connection retry attempts in seconds.</span></span> <span data-ttu-id="9c13b-233">O valor padrão é zero (0).</span><span class="sxs-lookup"><span data-stu-id="9c13b-233">The default value is zero (0).</span></span> <span data-ttu-id="9c13b-234">Esse parâmetro é válido somente quando o valor de PSConnectionRetryCount é pelo menos 1.</span><span class="sxs-lookup"><span data-stu-id="9c13b-234">This parameter is valid only when the value of PSConnectionRetryCount is at least 1.</span></span> <span data-ttu-id="9c13b-235">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-235">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionuri-systemuri"></a><span data-ttu-id="9c13b-236">PSConnectionURI \<System.Uri\></span><span class="sxs-lookup"><span data-stu-id="9c13b-236">PSConnectionURI \<System.Uri\></span></span>

<span data-ttu-id="9c13b-237">Especifica um Uniform Resource Identifier (URI) que define o ponto de extremidade de conexão para a atividade no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-237">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint for the activity on the target computer.</span></span> <span data-ttu-id="9c13b-238">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="9c13b-238">The URI must be fully qualified.</span></span> <span data-ttu-id="9c13b-239">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-239">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="9c13b-240">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c13b-240">The format of this string is as follows:</span></span>

```
<Transport>://<ComputerName>:<Port>/<ApplicationName>
```

<span data-ttu-id="9c13b-241">O valor padrão é `http://localhost:5985/WSMAN`.</span><span class="sxs-lookup"><span data-stu-id="9c13b-241">The default value is `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="9c13b-242">Se você não especificar um PSConnectionURI, poderá usar os parâmetros PSUseSSL, PSComputerName, PSPort e PSApplicationName para especificar os valores de PSConnectionURI.</span><span class="sxs-lookup"><span data-stu-id="9c13b-242">If you do not specify a PSConnectionURI, you can use the PSUseSSL, PSComputerName, PSPort, and PSApplicationName parameters to specify the PSConnectionURI values.</span></span>

<span data-ttu-id="9c13b-243">Os valores válidos para o segmento Transport do URI são HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9c13b-243">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="9c13b-244">Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas de padrões: 80 para HTTP e 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9c13b-244">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="9c13b-245">Para utilizar as portas padrão para comunicação remota do Windows PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9c13b-245">To use the default ports for Windows PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

#### <a name="pscredential-pscredential"></a><span data-ttu-id="9c13b-246">PSCredential \<PSCredential\></span><span class="sxs-lookup"><span data-stu-id="9c13b-246">PSCredential \<PSCredential\></span></span>

<span data-ttu-id="9c13b-247">Especifica uma conta de usuário que tem permissão para executar a atividade no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-247">Specifies a user account that has permission to run the activity on the target computer.</span></span> <span data-ttu-id="9c13b-248">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="9c13b-248">The default is the current user.</span></span> <span data-ttu-id="9c13b-249">Esse parâmetro é válido somente quando o parâmetro PSComputerName é incluído no comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-249">This parameter is valid only when the PSComputerName parameter is included in the command.</span></span> <span data-ttu-id="9c13b-250">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-250">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="9c13b-251">Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira uma variável que contenha um objeto PSCredential, como um que o cmdlet Get-Credential retorna.</span><span class="sxs-lookup"><span data-stu-id="9c13b-251">Type a user name, such as "User01" or "Domain01\User01", or enter a variable that contains a PSCredential object, such as one that the Get-Credential cmdlet returns.</span></span> <span data-ttu-id="9c13b-252">Se você inserir apenas um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="9c13b-252">If you enter only a user name, you will be prompted for a password.</span></span>

#### <a name="psdebug-psdatacollectiondebugrecord"></a><span data-ttu-id="9c13b-253">PSDebug \<PSDataCollection[DebugRecord]\></span><span class="sxs-lookup"><span data-stu-id="9c13b-253">PSDebug \<PSDataCollection[DebugRecord]\></span></span>

<span data-ttu-id="9c13b-254">Adiciona mensagens de depuração da atividade para a coleção de registros de depuração especificada, em vez de gravar as mensagens de depuração no console ou para o valor da Propriedade Debug do trabalho de Workflow.</span><span class="sxs-lookup"><span data-stu-id="9c13b-254">Adds debug messages from the activity to the specified debug record collection, instead of writing the debug messages to the console or to the value of the Debug property of the workflow job.</span></span> <span data-ttu-id="9c13b-255">Você pode adicionar mensagens de depuração de várias atividades ao mesmo objeto de coleção de registros de depuração.</span><span class="sxs-lookup"><span data-stu-id="9c13b-255">You can add debug messages from multiple activities to the same debug record collection object.</span></span>

<span data-ttu-id="9c13b-256">Para usar esse parâmetro comum de atividade, use o cmdlet New-Object para criar um objeto PSDataCollection com um tipo de DebugRecord e salve o objeto em uma variável.</span><span class="sxs-lookup"><span data-stu-id="9c13b-256">To use this activity common parameter, use the New-Object cmdlet to create a PSDataCollection object with a type of DebugRecord and save the object in a variable.</span></span> <span data-ttu-id="9c13b-257">Em seguida, use a variável como o valor do parâmetro PSDebug de uma ou mais atividades, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="9c13b-257">Then, use the variable as the value of the PSDebug parameter of one or more activities, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
    $debugCollection = New-Object -Type `
    System.Management.Automation.PSDataCollection[System.Management.Automation.DebugRecord]
    InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    if ($debugCollection -like "Missing") { ...}
}
```

#### <a name="psdisableserialization-boolean"></a><span data-ttu-id="9c13b-258">PSDisableSerialization \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="9c13b-258">PSDisableSerialization \<Boolean\></span></span>

<span data-ttu-id="9c13b-259">Direciona a atividade para retornar objetos “ativos” (não serializados) ao fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-259">Directs the activity to return "live" (not serialized) objects to the workflow.</span></span>
<span data-ttu-id="9c13b-260">Os objetos resultantes têm métodos, bem como propriedades, mas não podem ser salvos quando um ponto de verificação é obtido.</span><span class="sxs-lookup"><span data-stu-id="9c13b-260">The resulting objects have methods, as well as properties, but they cannot be saved when a checkpoint is taken.</span></span>

#### <a name="psdisableserializationpreference-boolean"></a><span data-ttu-id="9c13b-261">PSDisableSerializationPreference \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="9c13b-261">PSDisableSerializationPreference \<Boolean\></span></span>

<span data-ttu-id="9c13b-262">Aplica o equivalente ao parâmetro PSDisableSerialization ao fluxo de trabalho inteiro, não apenas à atividade.</span><span class="sxs-lookup"><span data-stu-id="9c13b-262">Applies the equivalent of the PSDisableSerialization parameter to the entire workflow, not just the activity.</span></span> <span data-ttu-id="9c13b-263">A adição desse parâmetro geralmente não é recomendada, pois um fluxo de trabalho que não serializa seus objetos não pode ser retomado ou persistido.</span><span class="sxs-lookup"><span data-stu-id="9c13b-263">Adding this parameter is generally not recommended, because a workflow that doesn't serialize its objects cannot be resumed or persisted.</span></span>

<span data-ttu-id="9c13b-264">Valores válidos: </span><span class="sxs-lookup"><span data-stu-id="9c13b-264">Valid values:</span></span>

- <span data-ttu-id="9c13b-265">Os Se omitido, e você também não tiver adicionado o parâmetro PSDisableSerialization a uma atividade, os objetos serão serializados.</span><span class="sxs-lookup"><span data-stu-id="9c13b-265">(Default) If omitted, and you have also not added the PSDisableSerialization parameter to an activity, objects are serialized.</span></span>

- <span data-ttu-id="9c13b-266">`$True`.</span><span class="sxs-lookup"><span data-stu-id="9c13b-266">`$True`.</span></span> <span data-ttu-id="9c13b-267">direciona todas as atividades de um fluxo de trabalho a retornar objetos “ativos” (não serializados).</span><span class="sxs-lookup"><span data-stu-id="9c13b-267">Directs all activities within a workflow to return "live" (not serialized) objects.</span></span> <span data-ttu-id="9c13b-268">Os objetos resultantes têm métodos, bem como propriedades, mas não podem ser salvos quando um ponto de verificação é obtido.</span><span class="sxs-lookup"><span data-stu-id="9c13b-268">The resulting objects have methods, as well as properties, but they cannot be saved when a checkpoint is taken.</span></span>
- <span data-ttu-id="9c13b-269">`$False`.</span><span class="sxs-lookup"><span data-stu-id="9c13b-269">`$False`.</span></span> <span data-ttu-id="9c13b-270">os objetos de fluxo de trabalho são serializados.</span><span class="sxs-lookup"><span data-stu-id="9c13b-270">Workflow objects are serialized.</span></span>

#### <a name="pserror-psdatacollectionerrorrecord"></a><span data-ttu-id="9c13b-271">PSError \<PSDataCollection[ErrorRecord]\></span><span class="sxs-lookup"><span data-stu-id="9c13b-271">PSError \<PSDataCollection[ErrorRecord]\></span></span>

<span data-ttu-id="9c13b-272">Adiciona mensagens de erro da atividade à coleção de registros de erros especificada, em vez de gravar as mensagens de erro no console ou no valor da Propriedade Error do trabalho de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-272">Adds error messages from the activity to the specified error record collection, instead of writing the error messages to the console or to the value of the Error property of the workflow job.</span></span> <span data-ttu-id="9c13b-273">Você pode adicionar mensagens de erro de várias atividades ao mesmo objeto de coleção de registros de erro.</span><span class="sxs-lookup"><span data-stu-id="9c13b-273">You can add error messages from multiple activities to the same error record collection object.</span></span>

<span data-ttu-id="9c13b-274">Para usar esse parâmetro comum de atividade, use o `New-Object` cmdlet para criar um objeto PSDataCollection com um tipo de ErrorRecord e salve o objeto em uma variável.</span><span class="sxs-lookup"><span data-stu-id="9c13b-274">To use this activity common parameter, use the `New-Object` cmdlet to create a PSDataCollection object with a type of ErrorRecord and save the object in a variable.</span></span> <span data-ttu-id="9c13b-275">Em seguida, use a variável como o valor do parâmetro PSError de uma ou mais atividades, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="9c13b-275">Then, use the variable as the value of the PSError parameter of one or more activities, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
   $typeName = "System.Management.Automation.PSDataCollection"
   $typeName += '[System.Management.Automation.ErrorRecord]'
   $ec = New-Object $typeName
   InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSError $ec
   InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSError $ec
   if ($ec.Count -gt 2)
   {
      # Do Some Work.
   }
}
```

#### <a name="pspersist-boolean"></a><span data-ttu-id="9c13b-276">PSPersist \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="9c13b-276">PSPersist \<Boolean\></span></span>

<span data-ttu-id="9c13b-277">Usa um ponto de verificação após a atividade.</span><span class="sxs-lookup"><span data-stu-id="9c13b-277">Takes a checkpoint after the activity.</span></span> <span data-ttu-id="9c13b-278">Esse ponto de verificação é adicional aos pontos de verificação especificados no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-278">This checkpoint is in addition to any checkpoints that are specified in the workflow.</span></span> <span data-ttu-id="9c13b-279">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-279">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="9c13b-280">Um "ponto de verificação" ou "pontos de persistência" é um instantâneo do estado do fluxo de trabalho e dos dados que são capturados enquanto o fluxo de trabalho é executado e salvo em um repositório de persistência no disco.</span><span class="sxs-lookup"><span data-stu-id="9c13b-280">A "checkpoint" or "persistence point" is a snapshot of the workflow state and data that is captured while the workflow runs and is saved to a persistence store on disk.</span></span> <span data-ttu-id="9c13b-281">O fluxo de trabalho do Windows PowerShell usa os dados salvos para retomar um fluxo de trabalho suspenso ou interrompido do último ponto de persistência, em vez de reiniciar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-281">Windows PowerShell Workflow uses the saved data to resume a suspended or interrupted workflow from the last persistence point, rather than to restart the workflow.</span></span>

<span data-ttu-id="9c13b-282">Valores válidos: </span><span class="sxs-lookup"><span data-stu-id="9c13b-282">Valid values:</span></span>

- <span data-ttu-id="9c13b-283">Os Se você omitir esse parâmetro, nenhum ponto de verificação será adicionado.</span><span class="sxs-lookup"><span data-stu-id="9c13b-283">(Default) If you omit this parameter, no checkpoints are added.</span></span> <span data-ttu-id="9c13b-284">Os pontos de verificação são obtidos com base nas configurações do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-284">Checkpoints are taken based on the settings for the workflow.</span></span>

- <span data-ttu-id="9c13b-285">`$True`.</span><span class="sxs-lookup"><span data-stu-id="9c13b-285">`$True`.</span></span> <span data-ttu-id="9c13b-286">Usa um ponto de verificação após a conclusão da atividade.</span><span class="sxs-lookup"><span data-stu-id="9c13b-286">Takes a checkpoint after the activity completes.</span></span>
  <span data-ttu-id="9c13b-287">Esse ponto de verificação é adicional aos pontos de verificação especificados no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-287">This checkpoint is in addition to any checkpoints that are specified in the workflow.</span></span>

- <span data-ttu-id="9c13b-288">`$False`.</span><span class="sxs-lookup"><span data-stu-id="9c13b-288">`$False`.</span></span> <span data-ttu-id="9c13b-289">Nenhum ponto de verificação é adicionado.</span><span class="sxs-lookup"><span data-stu-id="9c13b-289">No checkpoints are added.</span></span> <span data-ttu-id="9c13b-290">Os pontos de verificação são obtidos somente quando especificado no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-290">Checkpoints are taken only when specified in the workflow.</span></span>

#### <a name="psport-int32"></a><span data-ttu-id="9c13b-291">PSPort \<Int32\></span><span class="sxs-lookup"><span data-stu-id="9c13b-291">PSPort \<Int32\></span></span>

<span data-ttu-id="9c13b-292">Especifica a porta de rede nos computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-292">Specifies the network port on the target computers.</span></span> <span data-ttu-id="9c13b-293">As portas padrão são 5985 (a porta de WinRM para HTTP) e 5986 (a porta de WinRM para HTTPS).</span><span class="sxs-lookup"><span data-stu-id="9c13b-293">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span> <span data-ttu-id="9c13b-294">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-294">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="9c13b-295">Não use o parâmetro PSPort, a menos que você precise.</span><span class="sxs-lookup"><span data-stu-id="9c13b-295">Do not use the PSPort parameter unless you must.</span></span> <span data-ttu-id="9c13b-296">A porta definida no comando aplica-se a todos os computadores ou sessões em que o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="9c13b-296">The port set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="9c13b-297">Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="9c13b-297">An alternate port setting might prevent the command from running on all computers.</span></span> <span data-ttu-id="9c13b-298">Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta.</span><span class="sxs-lookup"><span data-stu-id="9c13b-298">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>

#### <a name="psprogress-psdatacollectionprogressrecord"></a><span data-ttu-id="9c13b-299">PSProgress \<PSDataCollection[ProgressRecord]\></span><span class="sxs-lookup"><span data-stu-id="9c13b-299">PSProgress \<PSDataCollection[ProgressRecord]\></span></span>

<span data-ttu-id="9c13b-300">Adiciona as mensagens de progresso da atividade à coleção de registros de andamento especificada, em vez de gravar as mensagens de progresso no console ou no valor da Propriedade Progress do trabalho de fluxo.</span><span class="sxs-lookup"><span data-stu-id="9c13b-300">Adds progress messages from the activity to the specified progress record collection, instead of writing the progress messages to the console or to the value of the Progress property of the workflow job.</span></span> <span data-ttu-id="9c13b-301">Você pode adicionar mensagens de progresso de várias atividades ao mesmo objeto de coleção de registros de progresso.</span><span class="sxs-lookup"><span data-stu-id="9c13b-301">You can add progress messages from multiple activities to the same progress record collection object.</span></span>

#### <a name="psprogressmessage-string"></a><span data-ttu-id="9c13b-302">PSProgressMessage \<String\></span><span class="sxs-lookup"><span data-stu-id="9c13b-302">PSProgressMessage \<String\></span></span>

<span data-ttu-id="9c13b-303">Especifica uma descrição amigável da atividade.</span><span class="sxs-lookup"><span data-stu-id="9c13b-303">Specifies a friendly description of the activity.</span></span> <span data-ttu-id="9c13b-304">O valor PSProgressMessage aparece na barra de progresso enquanto o fluxo de trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="9c13b-304">The PSProgressMessage value appears in the progress bar while the workflow runs.</span></span> <span data-ttu-id="9c13b-305">Quando o DisplayName também é incluído no comando, o conteúdo da barra de progresso aparece em \<DisplayName\> : \<PSProgressMessage\> Format.</span><span class="sxs-lookup"><span data-stu-id="9c13b-305">When the DisplayName is also included in the command, the progress bar content appears in \<DisplayName\>:\<PSProgressMessage\> format.</span></span>

<span data-ttu-id="9c13b-306">Esse parâmetro é particularmente útil para identificar atividades em um bloco de script ForEach-Parallel.</span><span class="sxs-lookup"><span data-stu-id="9c13b-306">This parameter is particularly useful for identifying activities in a ForEach -Parallel script block.</span></span> <span data-ttu-id="9c13b-307">Sem essa mensagem, as atividades em todas as ramificações paralelas são identificadas pelo mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="9c13b-307">Without this message, activities in all parallel branches are identified by the same name.</span></span>

#### <a name="psremotingbehavior-remotingbehavior"></a><span data-ttu-id="9c13b-308">PSRemotingBehavior \<RemotingBehavior\></span><span class="sxs-lookup"><span data-stu-id="9c13b-308">PSRemotingBehavior \<RemotingBehavior\></span></span>

<span data-ttu-id="9c13b-309">Especifica como a comunicação remota é gerenciada quando a atividade é executada em computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-309">Specifies how remoting is managed when the activity is run on target computers.</span></span>
<span data-ttu-id="9c13b-310">O PowerShell é o padrão.</span><span class="sxs-lookup"><span data-stu-id="9c13b-310">PowerShell is the default.</span></span>

<span data-ttu-id="9c13b-311">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="9c13b-311">Valid values are:</span></span>

- <span data-ttu-id="9c13b-312">Nenhum: a atividade não é executada em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="9c13b-312">None: The activity is not run on remote computers.</span></span>

- <span data-ttu-id="9c13b-313">PowerShell: a comunicação remota do Windows PowerShell é usada para executar a atividade em computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-313">PowerShell: Windows PowerShell remoting is used to run the activity on target computers.</span></span>

- <span data-ttu-id="9c13b-314">Personalizado: a atividade dá suporte a seu próprio tipo de comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="9c13b-314">Custom: The activity supports its own type of remoting.</span></span> <span data-ttu-id="9c13b-315">Esse valor é válido quando o cmdlet que está sendo implementado como uma atividade define o valor do atributo RemotingCapability como SupportedByCommand e o comando inclui o parâmetro ComputerName.</span><span class="sxs-lookup"><span data-stu-id="9c13b-315">This value is valid when the cmdlet that is being implemented as an activity sets the value of the RemotingCapability attribute to SupportedByCommand and the command includes the ComputerName parameter.</span></span>

#### <a name="psrequiredmodules-string"></a><span data-ttu-id="9c13b-316">PSRequiredModules \<String[]\></span><span class="sxs-lookup"><span data-stu-id="9c13b-316">PSRequiredModules \<String[]\></span></span>

<span data-ttu-id="9c13b-317">Importa os módulos especificados antes de executar o comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-317">Imports the specified modules before running the command.</span></span> <span data-ttu-id="9c13b-318">Insira os nomes do módulo.</span><span class="sxs-lookup"><span data-stu-id="9c13b-318">Enter the module names.</span></span> <span data-ttu-id="9c13b-319">Os módulos devem ser instalados no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-319">The modules must be installed on the target computer.</span></span>

<span data-ttu-id="9c13b-320">Os módulos instalados em um caminho especificado na variável de ambiente PSModulePath são automaticamente importados na primeira utilização de qualquer comando no módulo.</span><span class="sxs-lookup"><span data-stu-id="9c13b-320">Modules that are installed in a path specified in the PSModulePath environment variable are automatically imported on first use of any command in the module.</span></span>
<span data-ttu-id="9c13b-321">Use esse parâmetro para importar módulos que não estão em um local PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="9c13b-321">Use this parameter to import modules that are not in a PSModulePath location.</span></span>

<span data-ttu-id="9c13b-322">Já que cada atividade em um fluxo de trabalho é executada em sua própria sessão, um comando Import-Module importa um módulo somente para a sessão na qual ele é executado.</span><span class="sxs-lookup"><span data-stu-id="9c13b-322">Because each activity in a workflow runs in its own session, an Import-Module command imports a module only into the session in which it runs.</span></span> <span data-ttu-id="9c13b-323">Ela não importa o módulo para sessões em que há outras atividades em execução.</span><span class="sxs-lookup"><span data-stu-id="9c13b-323">It does not import the module into sessions in which other activities run.</span></span>

#### <a name="pssessionoption-pssessionoption"></a><span data-ttu-id="9c13b-324">PSSessionOption \<PSSessionOption\></span><span class="sxs-lookup"><span data-stu-id="9c13b-324">PSSessionOption \<PSSessionOption\></span></span>

<span data-ttu-id="9c13b-325">Define opções avançadas para as sessões para os computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-325">Sets advanced options for the sessions to the target computers.</span></span> <span data-ttu-id="9c13b-326">Insira um objeto PSSessionOption, como um que você cria usando o cmdlet New-PSSessionOption.</span><span class="sxs-lookup"><span data-stu-id="9c13b-326">Enter a PSSessionOption object, such as one that you create by using the New-PSSessionOption cmdlet.</span></span> <span data-ttu-id="9c13b-327">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-327">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="9c13b-328">Os valores padrão para as opções de sessão são determinados pelo valor da `$PSSessionOption` variável de preferência, se estiver definido.</span><span class="sxs-lookup"><span data-stu-id="9c13b-328">The default values for the session options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="9c13b-329">Caso contrário, a sessão usará os valores especificados na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="9c13b-329">Otherwise, the session uses the values specified in the session configuration.</span></span>

<span data-ttu-id="9c13b-330">Para obter uma descrição das opções de sessão, incluindo os valores padrão, consulte o tópico da ajuda para o cmdlet New-PSSessionOption [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="9c13b-330">For a description of the session options, including the default values, see the help topic for the New-PSSessionOption cmdlet [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="9c13b-331">Para obter mais informações sobre a variável de preferência $PSSessionOption, consulte [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9c13b-331">For more information about the $PSSessionOption preference variable, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

#### <a name="psusessl-boolean"></a><span data-ttu-id="9c13b-332">PSUseSSL \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="9c13b-332">PSUseSSL \<Boolean\></span></span>

<span data-ttu-id="9c13b-333">Um valor de $True usa o protocolo de protocolo SSL (SSL) para estabelecer uma conexão com o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-333">A value of $True uses the Secure Sockets Layer (SSL) protocol to establish a connection to the target computer.</span></span> <span data-ttu-id="9c13b-334">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="9c13b-334">By default, SSL is not used.</span></span> <span data-ttu-id="9c13b-335">Um valor de $False não tem nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="9c13b-335">A value of $False has no effect.</span></span> <span data-ttu-id="9c13b-336">Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-336">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="9c13b-337">O WS-Management criptografa todo o conteúdo do Windows PowerShell transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="9c13b-337">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="9c13b-338">O UseSSL é uma proteção adicional que envia os dados em um HTTPS, em vez de HTTP.</span><span class="sxs-lookup"><span data-stu-id="9c13b-338">UseSSL is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span> <span data-ttu-id="9c13b-339">Se você usar esse parâmetro e o SSL não estiver disponível na porta usada para o comando, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="9c13b-339">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

#### <a name="psverbose-psdatacollectionverboserecord"></a><span data-ttu-id="9c13b-340">PSVerbose \<PSDataCollection[VerboseRecord]\></span><span class="sxs-lookup"><span data-stu-id="9c13b-340">PSVerbose \<PSDataCollection[VerboseRecord]\></span></span>

<span data-ttu-id="9c13b-341">Adiciona mensagens detalhadas da atividade à coleção de registros detalhados especificada, em vez de gravar as mensagens detalhadas no console ou no valor da propriedade Verbose do trabalho de fluxo.</span><span class="sxs-lookup"><span data-stu-id="9c13b-341">Adds verbose messages from the activity to the specified verbose record collection, instead of writing the verbose messages to the console or to the value of the Verbose property of the workflow job.</span></span> <span data-ttu-id="9c13b-342">Você pode adicionar mensagens detalhadas de várias atividades ao mesmo objeto de coleção de registros detalhados.</span><span class="sxs-lookup"><span data-stu-id="9c13b-342">You can add verbose messages from multiple activities to the same verbose record collection object.</span></span>

#### <a name="pswarning-psdatacollectionwarningrecord"></a><span data-ttu-id="9c13b-343">PSWarning \<PSDataCollection[WarningRecord]\></span><span class="sxs-lookup"><span data-stu-id="9c13b-343">PSWarning \<PSDataCollection[WarningRecord]\></span></span>

<span data-ttu-id="9c13b-344">Adiciona mensagens de aviso da atividade à coleção de registros de aviso especificada, em vez de gravar as mensagens de aviso no console ou no valor da propriedade de aviso do trabalho de fluxo.</span><span class="sxs-lookup"><span data-stu-id="9c13b-344">Adds warning messages from the activity to the specified warning record collection, instead of writing the warning messages to the console or to the value of the Warning property of the workflow job.</span></span> <span data-ttu-id="9c13b-345">Você pode adicionar mensagens de aviso de várias atividades ao mesmo objeto de coleção de registros de aviso.</span><span class="sxs-lookup"><span data-stu-id="9c13b-345">You can add warning messages from multiple activities to the same warning record collection object.</span></span>

#### <a name="result"></a><span data-ttu-id="9c13b-346">Resultado</span><span class="sxs-lookup"><span data-stu-id="9c13b-346">Result</span></span>

<span data-ttu-id="9c13b-347">Esse parâmetro só é válido em fluxos de trabalho XAML.</span><span class="sxs-lookup"><span data-stu-id="9c13b-347">This parameter is valid only in XAML workflows.</span></span>

#### <a name="usedefaultinput-boolean"></a><span data-ttu-id="9c13b-348">UseDefaultInput \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="9c13b-348">UseDefaultInput \<Boolean\></span></span>

<span data-ttu-id="9c13b-349">Aceita todas as entradas de fluxo de trabalho como entrada para a atividade por valor.</span><span class="sxs-lookup"><span data-stu-id="9c13b-349">Accepts all workflow input as input to the activity by value.</span></span>

<span data-ttu-id="9c13b-350">Por exemplo, a atividade Get-Process do exemplo de fluxo de trabalho a seguir usa o parâmetro comum de atividade UseDefaultInput para obter a entrada que é passada ao fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c13b-350">For example, the Get-Process activity in the following sample workflow uses the UseDefaultInput activity common parameter to get input that is passed to the workflow.</span></span> <span data-ttu-id="9c13b-351">Quando você executa o fluxo de trabalho com a entrada, essa entrada é usada pela atividade.</span><span class="sxs-lookup"><span data-stu-id="9c13b-351">When you run the workflow with input, that input is used by the activity.</span></span>

```powershell
workflow Test-Workflow
{
    Get-Service -UseDefaultInput $True
}

PS C:> Test-Workflow -InputObject WinRm
```

```output
Status   Name        DisplayName                            PSComputerName
------   ----        -----------                            --------------
Running  winrm       Windows Remote Management (WS-Manag... localhost
```

#### <a name="verbose-switchparameter"></a><span data-ttu-id="9c13b-352">Extensa \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="9c13b-352">Verbose \<SwitchParameter\></span></span>

<span data-ttu-id="9c13b-353">Exibe informações detalhadas sobre a operação executada pelo comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-353">Displays detailed information about the operation performed by the command.</span></span>
<span data-ttu-id="9c13b-354">Essas informações se assemelham às informações em um rastreamento ou em um log de transações.</span><span class="sxs-lookup"><span data-stu-id="9c13b-354">This information resembles the information in a trace or in a transaction log.</span></span>
<span data-ttu-id="9c13b-355">O parâmetro Verbose substitui o valor da variável $VerbosePreference para o comando atual.</span><span class="sxs-lookup"><span data-stu-id="9c13b-355">The Verbose parameter overrides the value of the $VerbosePreference variable for the current command.</span></span> <span data-ttu-id="9c13b-356">Esse parâmetro funciona somente quando o comando gera uma mensagem detalhada.</span><span class="sxs-lookup"><span data-stu-id="9c13b-356">This parameter works only when the command generates a verbose message.</span></span> <span data-ttu-id="9c13b-357">Esse parâmetro também é um parâmetro comum do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c13b-357">This parameter is also a Windows PowerShell common parameter.</span></span>

#### <a name="warningaction-actionpreference"></a><span data-ttu-id="9c13b-358">WarningAction \<ActionPreference\></span><span class="sxs-lookup"><span data-stu-id="9c13b-358">WarningAction \<ActionPreference\></span></span>

<span data-ttu-id="9c13b-359">Determina como a atividade responde a um aviso.</span><span class="sxs-lookup"><span data-stu-id="9c13b-359">Determines how the activity responds to a warning.</span></span> <span data-ttu-id="9c13b-360">"Continue" é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="9c13b-360">"Continue" is the default value.</span></span> <span data-ttu-id="9c13b-361">O parâmetro WarningAction substitui o valor da variável $WarningPreference para o comando atual.</span><span class="sxs-lookup"><span data-stu-id="9c13b-361">The WarningAction parameter overrides the value of the $WarningPreference variable for the current command.</span></span> <span data-ttu-id="9c13b-362">Esse parâmetro funciona somente quando o comando gera uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="9c13b-362">This parameter works only when the command generates a warning message.</span></span> <span data-ttu-id="9c13b-363">Esse parâmetro também é um parâmetro comum do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c13b-363">This parameter is also a Windows PowerShell common parameter.</span></span>

<span data-ttu-id="9c13b-364">Valores válidos:</span><span class="sxs-lookup"><span data-stu-id="9c13b-364">Valid Values:</span></span>

- <span data-ttu-id="9c13b-365">SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="9c13b-365">SilentlyContinue.</span></span> <span data-ttu-id="9c13b-366">Suprime a mensagem de aviso e continua executando o comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-366">Suppresses the warning message and continues executing the command.</span></span>

- <span data-ttu-id="9c13b-367">Continua.</span><span class="sxs-lookup"><span data-stu-id="9c13b-367">Continue.</span></span> <span data-ttu-id="9c13b-368">Exibe a mensagem de aviso e continua executando o comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-368">Displays the warning message and continues executing the command.</span></span>
  <span data-ttu-id="9c13b-369">"Continue" é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="9c13b-369">"Continue" is the default value.</span></span>

- <span data-ttu-id="9c13b-370">Inquire.</span><span class="sxs-lookup"><span data-stu-id="9c13b-370">Inquire.</span></span> <span data-ttu-id="9c13b-371">Exibe a mensagem de aviso e solicita sua confirmação antes de continuar a execução.</span><span class="sxs-lookup"><span data-stu-id="9c13b-371">Displays the warning message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="9c13b-372">Esse valor raramente é usado.</span><span class="sxs-lookup"><span data-stu-id="9c13b-372">This value is rarely used.</span></span>

- <span data-ttu-id="9c13b-373">Deixar.</span><span class="sxs-lookup"><span data-stu-id="9c13b-373">Stop.</span></span> <span data-ttu-id="9c13b-374">Exibe a mensagem de aviso e para a execução do comando.</span><span class="sxs-lookup"><span data-stu-id="9c13b-374">Displays the warning message and stops executing the command.</span></span>

> [!NOTE]
> <span data-ttu-id="9c13b-375">O parâmetro WarningAction não substitui o valor da variável de preferência $WarningAction quando o parâmetro é usado em um comando para executar um script ou uma função.</span><span class="sxs-lookup"><span data-stu-id="9c13b-375">The WarningAction parameter does not override the value of the $WarningAction preference variable when the parameter is used in a command to run a script or function.</span></span>

### <a name="examples"></a><span data-ttu-id="9c13b-376">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9c13b-376">EXAMPLES</span></span>

<span data-ttu-id="9c13b-377">Os parâmetros comuns de atividades são extremamente úteis.</span><span class="sxs-lookup"><span data-stu-id="9c13b-377">The activity common parameters are extremely useful.</span></span> <span data-ttu-id="9c13b-378">Por exemplo, você pode usar o parâmetro PSComputerName para executar atividades específicas apenas em um subconjunto dos computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="9c13b-378">For example, you can use the PSComputerName parameter to run particular activities on only a subset of the target computers.</span></span>

<span data-ttu-id="9c13b-379">Ou, você pode usar os parâmetros PSConnectionRetryCount e PSConnectionRetryIntervalSec para ajustar os valores de repetição para atividades específicas.</span><span class="sxs-lookup"><span data-stu-id="9c13b-379">Or, you might use the PSConnectionRetryCount and PSConnectionRetryIntervalSec parameters to adjust the retry values for particular activities.</span></span>

<span data-ttu-id="9c13b-380">O exemplo a seguir mostra como usar os parâmetros comuns da atividade PSComputerName para executar uma atividade de Get-EventLog somente em computadores que um domínio específico.</span><span class="sxs-lookup"><span data-stu-id="9c13b-380">The following example shows how to use the PSComputerName activity common parameters to run a Get-EventLog activity only on computers it a particular domain.</span></span>

```powershell
Workflow Test-Workflow
{
    $UserDomain = Get-Content -Path '.\UserComputers.txt'
    $Log = (Get-EventLog -LogName "Windows PowerShell" `
      -PSComputerName $UserDomain)

    if ($Log)
    {
        # Do Work Here.
    }
}
```

<!--
# KEYWORDS
[about_Activity_Common_Parameters](about_Activity_Common_Parameters.md)
[about_Activity_Parameters](about_Activity_Parameters.md)
[about_ActivityParameters]()about_ActivityParameters.md) -->

## <a name="see-also"></a><span data-ttu-id="9c13b-381">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="9c13b-381">SEE ALSO</span></span>

<span data-ttu-id="9c13b-382">[about_Workflows](about_workflows.md) 
 [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="9c13b-382">[about_Workflows](about_workflows.md)
[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)</span></span>
