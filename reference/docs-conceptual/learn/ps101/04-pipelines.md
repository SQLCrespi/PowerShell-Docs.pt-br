---
title: One-liners and the pipeline (Uma linha e o pipeline)
description: Um comando de uma linha do PowerShell é um pipeline contínuo, contendo vários comandos, para realizar uma só tarefa.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: b8fd45e5e5dc408754ebac015757ef4241428978
ms.sourcegitcommit: 109f132360e8adbbdaf5dbc42a270be73d9dfa9b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84633338"
---
# <a name="chapter-4---one-liners-and-the-pipeline"></a><span data-ttu-id="48b5b-103">Capítulo 4 – Comandos de uma linha e o pipeline</span><span class="sxs-lookup"><span data-stu-id="48b5b-103">Chapter 4 - One-liners and the pipeline</span></span>

<span data-ttu-id="48b5b-104">Quando comecei a aprender a usar o PowerShell pela primeira vez, se eu não conseguia realizar uma tarefa com um comando de uma linha do PowerShell, voltava para a GUI.</span><span class="sxs-lookup"><span data-stu-id="48b5b-104">When I first started learning PowerShell, if I couldn't accomplish a task with a PowerShell one-liner, I went back to the GUI.</span></span> <span data-ttu-id="48b5b-105">Com o tempo, aprimorei minhas habilidades até conseguir escrever scripts, funções e módulos.</span><span class="sxs-lookup"><span data-stu-id="48b5b-105">Over time, I built my skills up to writing scripts, functions, and modules.</span></span> <span data-ttu-id="48b5b-106">Não se assuste com alguns dos exemplos mais avançados que você poderá ver na Internet.</span><span class="sxs-lookup"><span data-stu-id="48b5b-106">Don't allow yourself to become overwhelmed by some of the more advanced examples you may see on the internet.</span></span> <span data-ttu-id="48b5b-107">Ninguém é um especialista nato no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48b5b-107">No one is a natural expert with PowerShell.</span></span> <span data-ttu-id="48b5b-108">Em algum momento, todos éramos iniciantes.</span><span class="sxs-lookup"><span data-stu-id="48b5b-108">We were all beginners at one time.</span></span>

<span data-ttu-id="48b5b-109">Tenho um conselho para dar a vocês que ainda estão usando a GUI para administração: instale as ferramentas de gerenciamento na estação de trabalho de administração e gerencie seus servidores remotamente.</span><span class="sxs-lookup"><span data-stu-id="48b5b-109">I have a bit of advice to offer those of you who are still using the GUI for administration: install the management tools on your admin workstation and manage your servers remotely.</span></span> <span data-ttu-id="48b5b-110">Dessa forma, não importa se o servidor está executando uma instalação da GUI ou do Server Core do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="48b5b-110">This way it won't matter if the server is running a GUI or Server Core installation of the operating system.</span></span>
<span data-ttu-id="48b5b-111">Isso vai ajudar a preparar você para gerenciar servidores remotamente com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48b5b-111">It's going to help prepare you for managing servers remotely with PowerShell.</span></span>

<span data-ttu-id="48b5b-112">Assim como recomendamos nos capítulos anteriores, lembre-se de acompanhar os exemplos no computador do ambiente de laboratório do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="48b5b-112">As with previous chapters, be sure to follow along on your Windows 10 lab environment computer.</span></span>

## <a name="one-liners"></a><span data-ttu-id="48b5b-113">Comandos de uma linha</span><span class="sxs-lookup"><span data-stu-id="48b5b-113">One-Liners</span></span>

<span data-ttu-id="48b5b-114">Um comando de uma linha do PowerShell é um pipeline contínuo e, não necessariamente, um comando que esteja em uma linha física.</span><span class="sxs-lookup"><span data-stu-id="48b5b-114">A PowerShell one-liner is one continuous pipeline and not necessarily a command that’s on one physical line.</span></span> <span data-ttu-id="48b5b-115">Nem todos os comandos que estão em uma linha física são comandos de uma linha.</span><span class="sxs-lookup"><span data-stu-id="48b5b-115">Not all commands that are on one physical line are one-liners.</span></span>

<span data-ttu-id="48b5b-116">Embora o comando a seguir esteja em várias linhas físicas, ele é um comando de uma linha do PowerShell, pois é um pipeline contínuo.</span><span class="sxs-lookup"><span data-stu-id="48b5b-116">Even though the following command is on multiple physical lines, it's a PowerShell one-liner because it's one continuous pipeline.</span></span> <span data-ttu-id="48b5b-117">Ele pode ser escrito em uma linha física, mas optei pela quebra de linha no símbolo de barra vertical.</span><span class="sxs-lookup"><span data-stu-id="48b5b-117">It could be written on one physical line, but I've chosen to line break at the pipe symbol.</span></span> <span data-ttu-id="48b5b-118">O símbolo de barra vertical é um dos caracteres em que uma quebra de linha natural é permitida no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48b5b-118">The pipe symbol is one of the characters where a natural line break is allowed in PowerShell.</span></span>

```powershell
Get-Service |
  Where-Object CanPauseAndContinue -eq $true |
    Select-Object -Property *
```

```Output
Name                : LanmanWorkstation
RequiredServices    : {NSI, MRxSmb20, Bowser}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Workstation
DependentServices   : {SessionEnv, Netlogon, Browser}
MachineName         : .
ServiceName         : LanmanWorkstation
ServicesDependedOn  : {NSI, MRxSmb20, Bowser}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Automatic
Site                :
Container           :

Name                : Netlogon
RequiredServices    : {LanmanWorkstation}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Netlogon
DependentServices   : {}
MachineName         : .
ServiceName         : Netlogon
ServicesDependedOn  : {LanmanWorkstation}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Automatic
Site                :
Container           :

Name                : vmicheartbeat
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Heartbeat Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmicheartbeat
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmickvpexchange
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Data Exchange Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmickvpexchange
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmicrdv
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Remote Desktop Virtualization Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmicrdv
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmicshutdown
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Guest Shutdown Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmicshutdown
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmictimesync
RequiredServices    : {VmGid}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Time Synchronization Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmictimesync
ServicesDependedOn  : {VmGid}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmicvss
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Volume Shadow Copy Requestor
DependentServices   : {}
MachineName         : .
ServiceName         : vmicvss
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : Winmgmt
RequiredServices    : {RPCSS}
CanPauseAndContinue : True
CanShutdown         : True
CanStop             : True
DisplayName         : Windows Management Instrumentation
DependentServices   : {wscsvc, NcaSvc, iphlpsvc}
MachineName         : .
ServiceName         : Winmgmt
ServicesDependedOn  : {RPCSS}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Automatic
Site                :
Container           :
```

<span data-ttu-id="48b5b-119">As quebras de linha naturais podem ocorrer em caracteres comumente usados, incluindo vírgula (`,`) e colchetes de abertura (`[`), chaves (`{`) e parênteses (`(`).</span><span class="sxs-lookup"><span data-stu-id="48b5b-119">Natural line breaks can occur at commonly used characters including comma (`,`) and opening brackets (`[`), braces (`{`), and parenthesis (`(`).</span></span> <span data-ttu-id="48b5b-120">Outras que não são tão comuns incluem ponto e vírgula (`;`), sinal de igual (`=`) e aspas simples e duplas de abertura (`'`, `"`).</span><span class="sxs-lookup"><span data-stu-id="48b5b-120">Others that aren't so common include the semicolon (`;`), equals sign (`=`), and both opening single and double quotes (`'`,`"`).</span></span>

<span data-ttu-id="48b5b-121">O uso do caractere de acento grave (`` ` ``) como um caractere de continuação de linha é um tópico controverso.</span><span class="sxs-lookup"><span data-stu-id="48b5b-121">Using the backtick (`` ` ``) or grave accent character as a line continuation character is a controversial topic.</span></span> <span data-ttu-id="48b5b-122">Minha recomendação é tentar evitá-lo, se possível.</span><span class="sxs-lookup"><span data-stu-id="48b5b-122">My recommendation is to try to avoid it if at all possible.</span></span> <span data-ttu-id="48b5b-123">Em geral, vejo comandos do PowerShell escritos com um acento grave imediatamente após um caractere de quebra de linha natural.</span><span class="sxs-lookup"><span data-stu-id="48b5b-123">I often see PowerShell commands written using a backtick immediately after a natural line break character.</span></span>
<span data-ttu-id="48b5b-124">Não há motivo para ele estar lá.</span><span class="sxs-lookup"><span data-stu-id="48b5b-124">There's no reason for it to be there.</span></span>

```powershell
Get-Service -Name w32time |
>> Select-Object -Property *
```

```Output
Name                : w32time
RequiredServices    : {}
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
DisplayName         : Windows Time
DependentServices   : {}
MachineName         : .
ServiceName         : w32time
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :
```

<span data-ttu-id="48b5b-125">Os comandos mostrados nos dois exemplos anteriores funcionam bem no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48b5b-125">The commands shown in the previous two examples work fine in the PowerShell console.</span></span> <span data-ttu-id="48b5b-126">Mas se você tentar executá-los no painel de console do ISE do PowerShell, eles vão gerar um erro.</span><span class="sxs-lookup"><span data-stu-id="48b5b-126">But if you try to run them in the console pane of the PowerShell ISE, they'll generate an error.</span></span> <span data-ttu-id="48b5b-127">O painel de console do ISE do PowerShell não aguarda o restante do comando ser inserido na próxima linha, como o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48b5b-127">The console pane of the PowerShell ISE doesn't wait for the rest of the command to be entered on the next line like the PowerShell console does.</span></span> <span data-ttu-id="48b5b-128">Para evitar esse problema no painel de console do ISE do PowerShell, use <kbd>Shift</kbd>+<kbd>Enter</kbd> em vez de apenas selecionar <kbd>Enter</kbd> ao continuar um comando em outra linha.</span><span class="sxs-lookup"><span data-stu-id="48b5b-128">To avoid this problem in the console pane of the PowerShell ISE, use <kbd>Shift</kbd>+<kbd>Enter</kbd> instead of just pressing <kbd>Enter</kbd> when continuing a command on another line.</span></span>

<span data-ttu-id="48b5b-129">Este próximo exemplo não é um comando de uma linha do PowerShell porque não é um pipeline contínuo.</span><span class="sxs-lookup"><span data-stu-id="48b5b-129">This next example isn't a PowerShell one-liner because it's not one continuous pipeline.</span></span> <span data-ttu-id="48b5b-130">São dois comandos separados em uma linha, separados por ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="48b5b-130">It's two separate commands on one line, separated by a semicolon.</span></span>

```powershell
$Service = 'w32time'; Get-Service -Name $Service
```

```powershell
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="48b5b-131">Muitas linguagens de programação e script exigem um ponto e vírgula no final de cada linha.</span><span class="sxs-lookup"><span data-stu-id="48b5b-131">Many programming and scripting languages require a semicolon at the end of each line.</span></span> <span data-ttu-id="48b5b-132">Embora eles possam ser usados dessa forma no PowerShell, isso não é recomendado porque não são necessários.</span><span class="sxs-lookup"><span data-stu-id="48b5b-132">While they can be used that way in PowerShell, it's not recommended because they're not needed.</span></span>

## <a name="filtering-left"></a><span data-ttu-id="48b5b-133">Filtragem à esquerda</span><span class="sxs-lookup"><span data-stu-id="48b5b-133">Filtering Left</span></span>

<span data-ttu-id="48b5b-134">Os resultados dos comandos mostrados neste capítulo foram filtrados para um subconjunto.</span><span class="sxs-lookup"><span data-stu-id="48b5b-134">The results of the commands shown in this chapter have been filtered down to a subset.</span></span> <span data-ttu-id="48b5b-135">Por exemplo, `Get-Service` foi usado com o parâmetro **Name** para filtrar a lista de serviços que foram retornados apenas ao serviço de Tempo do Windows.</span><span class="sxs-lookup"><span data-stu-id="48b5b-135">For example, `Get-Service` was used with the **Name** parameter to filter the list of services that were returned to only the Windows Time service.</span></span>

<span data-ttu-id="48b5b-136">No pipeline, o ideal é sempre filtrar os resultados para o que você está procurando o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="48b5b-136">In the pipeline, you always want to filter the results down to what you're looking for as early as possible.</span></span> <span data-ttu-id="48b5b-137">Isso é feito usando parâmetros no primeiro comando ou aquele mais à esquerda.</span><span class="sxs-lookup"><span data-stu-id="48b5b-137">This is accomplished using parameters on the first command or, the one to the far left.</span></span>
<span data-ttu-id="48b5b-138">Isso, às vezes, é chamado de _filtragem à esquerda_.</span><span class="sxs-lookup"><span data-stu-id="48b5b-138">This is sometimes called _filtering left_.</span></span>

<span data-ttu-id="48b5b-139">O exemplo a seguir usa o parâmetro **Name** de `Get-Service` para filtrar imediatamente os resultados somente para o serviço de Tempo do Windows.</span><span class="sxs-lookup"><span data-stu-id="48b5b-139">The following example uses the **Name** parameter of `Get-Service` to immediately filter the results to the Windows Time service only.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="48b5b-140">Não é incomum ver exemplos em que o comando é direcionado para `Where-Object`, a fim de realizar a filtragem.</span><span class="sxs-lookup"><span data-stu-id="48b5b-140">It's not uncommon to see examples where the command is piped to `Where-Object` to perform the filtering.</span></span>

```powershell
Get-Service | Where-Object Name -eq w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  W32Time            Windows Time
```

<span data-ttu-id="48b5b-141">O primeiro exemplo realiza a filtragem na origem e retorna apenas os resultados para o serviço de Tempo do Windows.</span><span class="sxs-lookup"><span data-stu-id="48b5b-141">The first example filters at the source and only returns the results for the Windows Time service.</span></span>
<span data-ttu-id="48b5b-142">O segundo exemplo retorna todos os serviços e os direciona para outro comando a fim de realizar a filtragem.</span><span class="sxs-lookup"><span data-stu-id="48b5b-142">The second example returns all the services then pipes them to another command to perform the filtering.</span></span> <span data-ttu-id="48b5b-143">Embora isso possa não parecer ser um grande problema neste exemplo, imagine se você estiver consultando uma lista de usuários do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="48b5b-143">While this may not seem like a big deal in this example, imagine if you were querying a list of Active Directory users.</span></span> <span data-ttu-id="48b5b-144">Você realmente deseja retornar as informações para muitos milhares de contas de usuário do Active Directory apenas para direcioná-las para outro comando que as filtre em um pequeno subconjunto?</span><span class="sxs-lookup"><span data-stu-id="48b5b-144">Do you really want to return the information for many thousands of user accounts from Active Directory only to pipe them to another command that filters them down to a tiny subset?</span></span> <span data-ttu-id="48b5b-145">Minha recomendação é sempre realizar a filtragem à esquerda mesmo quando isso não parece importante.</span><span class="sxs-lookup"><span data-stu-id="48b5b-145">My recommendation is to always filter left even when it doesn't seem to matter.</span></span> <span data-ttu-id="48b5b-146">Você ficará tão acostumado com isso que realizará uma filtragem automática à esquerda quando for realmente importante.</span><span class="sxs-lookup"><span data-stu-id="48b5b-146">You'll be so use to it that you'll automatically filter left when it really does matter.</span></span>

<span data-ttu-id="48b5b-147">Uma vez, alguém me disse que a ordem na qual os comandos são especificados não importa.</span><span class="sxs-lookup"><span data-stu-id="48b5b-147">I once had someone tell me that the order you specify the commands in doesn't matter.</span></span> <span data-ttu-id="48b5b-148">Isso está longe de ser verdade.</span><span class="sxs-lookup"><span data-stu-id="48b5b-148">That couldn't be further from the truth.</span></span> <span data-ttu-id="48b5b-149">A ordem na qual os comandos são especificados é realmente importante ao realizar a filtragem.</span><span class="sxs-lookup"><span data-stu-id="48b5b-149">The order that the commands are specified in does indeed matter when performing filtering.</span></span> <span data-ttu-id="48b5b-150">Por exemplo, considere o cenário em que você está usando `Select-Object` para selecionar apenas algumas propriedades e `Where-Object` para filtrar as propriedades que não estarão na seleção.</span><span class="sxs-lookup"><span data-stu-id="48b5b-150">For example, consider the scenario where you are using `Select-Object` to select only a few properties and `Where-Object` to filter on properties that won't be in the selection.</span></span> <span data-ttu-id="48b5b-151">Nesse cenário, a filtragem precisará ocorrer primeiro, caso contrário, a propriedade não existirá no pipeline ao tentar realizar a filtragem.</span><span class="sxs-lookup"><span data-stu-id="48b5b-151">In that scenario, the filtering must occur first, otherwise the property won't exist in the pipeline when try to perform the filtering.</span></span>

```powershell
Get-Service |
Select-Object -Property DisplayName, Running, Status |
Where-Object CanPauseAndContinue
```

<span data-ttu-id="48b5b-152">O comando no exemplo anterior não retorna nenhum resultado, porque a propriedade **CanStopAndContinue** não existe quando os resultados de `Select-Object` são direcionados para `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="48b5b-152">The command in the previous example doesn't return any results because the **CanStopAndContinue** property doesn't exist when the results of `Select-Object` are piped to `Where-Object`.</span></span> <span data-ttu-id="48b5b-153">Essa propriedade específica não foi "selecionada".</span><span class="sxs-lookup"><span data-stu-id="48b5b-153">That particular property wasn't "selected".</span></span> <span data-ttu-id="48b5b-154">Em essência, ela foi filtrada. A reversão da ordem de `Select-Object` e `Where-Object` produz os resultados desejados.</span><span class="sxs-lookup"><span data-stu-id="48b5b-154">In essence, it was filtered out. Reversing the order of `Select-Object` and `Where-Object` produces the desired results.</span></span>

```powershell
Get-Service |
Where-Object CanPauseAndContinue |
Select-Object -Property DisplayName, Status
```

```Output
DisplayName                                    Status
-----------                                    ------
Workstation                                    Running
Netlogon                                       Running
Hyper-V Heartbeat Service                      Running
Hyper-V Data Exchange Service                  Running
Hyper-V Remote Desktop Virtualization Service  Running
Hyper-V Guest Shutdown Service                 Running
Hyper-V Time Synchronization Service           Running
Hyper-V Volume Shadow Copy Requestor           Running
Windows Management Instrumentation             Running
```

## <a name="the-pipeline"></a><span data-ttu-id="48b5b-155">O pipeline</span><span class="sxs-lookup"><span data-stu-id="48b5b-155">The Pipeline</span></span>

<span data-ttu-id="48b5b-156">Como você viu em muitos dos exemplos mostrados até agora neste livro, muitas vezes, a saída de um comando pode ser usada como a entrada de outro comando.</span><span class="sxs-lookup"><span data-stu-id="48b5b-156">As you've seen in many of the examples shown so far throughout this book, many times the output of one command can be used as input for another command.</span></span> <span data-ttu-id="48b5b-157">No Capítulo 3, `Get-Member` foi usado para determinar o tipo de objeto que um comando produz.</span><span class="sxs-lookup"><span data-stu-id="48b5b-157">In Chapter 3, `Get-Member` was used to determine what type of object a command produces.</span></span> <span data-ttu-id="48b5b-158">O Capítulo 3 também mostrou o uso do parâmetro **ParameterType** de `Get-Command` para determinar quais comandos aceitaram esse tipo de entrada, embora não necessariamente pela entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="48b5b-158">Chapter 3 also showed using the **ParameterType** parameter of `Get-Command` to determine what commands accepted that type of input, although not necessarily by pipeline input.</span></span>

<span data-ttu-id="48b5b-159">Dependendo da extensão da Ajuda de comandos, ela pode incluir uma seção **ENTRADAS** e **SAÍDAS**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-159">Depending on how thorough a commands help is, it may include an **INPUTS** and **OUTPUTS** section.</span></span>

```powershell
help Stop-Service -Full
```

```Output
...
INPUTS
    System.ServiceProcess.ServiceController, System.String
        You can pipe a service object or a string that contains the name of a service
        to this cmdlet.

OUTPUTS
    None, System.ServiceProcess.ServiceController
        This cmdlet generates a System.ServiceProcess.ServiceController object that
        represents the service, if you use the PassThru parameter. Otherwise, this
        cmdlet does not generate any output.
...
```

<span data-ttu-id="48b5b-160">Somente a seção relevante da Ajuda é mostrada nos resultados anteriores.</span><span class="sxs-lookup"><span data-stu-id="48b5b-160">Only the relevant section of the help is shown in the previous results.</span></span> <span data-ttu-id="48b5b-161">Como você pode ver, a seção **ENTRADAS** indica que um objeto **ServiceController** ou **String** pode ser direcionado para o cmdlet `Stop-Service`.</span><span class="sxs-lookup"><span data-stu-id="48b5b-161">As you can see, the **INPUTS** section states that a **ServiceController** or a **String** object can be piped to the `Stop-Service` cmdlet.</span></span> <span data-ttu-id="48b5b-162">Ele não informa quais parâmetros aceitam esse tipo de entrada.</span><span class="sxs-lookup"><span data-stu-id="48b5b-162">It doesn't tell you which parameters accept that type of input.</span></span> <span data-ttu-id="48b5b-163">Uma das maneiras mais fáceis de determinar essas informações é examinar os diferentes parâmetros na versão completa da Ajuda para o cmdlet `Stop-Service`.</span><span class="sxs-lookup"><span data-stu-id="48b5b-163">One of the easiest ways to determine that information is to look through the different parameters in the full version of the help for the `Stop-Service` cmdlet.</span></span>

```powershell
help Stop-Service -Full
```

```powershell
...
-DisplayName <String[]>
    Specifies the display names of the services to stop. Wildcard characters are
    permitted.

    Required?                    true
    Position?                    named
    Default value                None
    Accept pipeline input?       False
    Accept wildcard characters?  false

-InputObject <ServiceController[]>
    Specifies ServiceController objects that represent the services to stop. Enter a
    variable that contains the objects, or type a command or expression that gets the
    objects.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByValue)
    Accept wildcard characters?  false

-Name <String[]>
    Specifies the service names of the services to stop. Wildcard characters are
    permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  false
...
```

<span data-ttu-id="48b5b-164">Mais uma vez, mostrei apenas a parte relevante da Ajuda no conjunto de resultados anterior.</span><span class="sxs-lookup"><span data-stu-id="48b5b-164">Once again, I've only shown the relevant portion of the help in the previous set of results.</span></span> <span data-ttu-id="48b5b-165">Observe que o parâmetro **DisplayName** não aceita a entrada de pipeline, o parâmetro **InputObject** aceita a entrada do pipeline **por valor** para os objetos **ServiceController**, e o parâmetro **Name** aceita a entrada do pipeline **por valor** para objetos de **cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-165">Notice that the **DisplayName** parameter doesn't accept pipeline input, the **InputObject** parameter accepts pipeline input **by value** for **ServiceController** objects, and the **Name** parameter accepts pipeline input **by value** for **string** objects.</span></span> <span data-ttu-id="48b5b-166">Ele também aceita a entrada de pipeline **pelo nome da propriedade**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-166">It also accepts pipeline input **by property name**.</span></span>

<span data-ttu-id="48b5b-167">Quando um parâmetro aceita a entrada de pipeline pelo nome da propriedade e por valor, ele sempre tenta **por valor** primeiro.</span><span class="sxs-lookup"><span data-stu-id="48b5b-167">When a parameter accepts pipeline input by both property name and by value, it always tries **by value** first.</span></span> <span data-ttu-id="48b5b-168">Se **por valor** falhar, ele tentará **pelo nome da propriedade**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-168">If **by value** fails, then it tries **by property name**.</span></span> <span data-ttu-id="48b5b-169">**Por valor** é um pouco enganoso.</span><span class="sxs-lookup"><span data-stu-id="48b5b-169">**By value** is a little misleading.</span></span> <span data-ttu-id="48b5b-170">Prefiro chamá-lo de **por tipo**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-170">I prefer to call it **by type**.</span></span> <span data-ttu-id="48b5b-171">Isso significa que se você direcionar os resultados de um comando que produz um tipo de objeto **ServiceController** para `Stop-Service`, ele associará essa entrada ao parâmetro **InputObject**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-171">This means if you pipe the results of a command that produces a **ServiceController** object type to `Stop-Service`, it binds that input to the **InputObject** parameter.</span></span> <span data-ttu-id="48b5b-172">Porém, se você direcionar os resultados de um comando que produz a saída **String** para `Stop-Service`, ele o associará ao parâmetro **Name**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-172">But if you pipe the results of a command that produces **String** output to `Stop-Service`, it binds it to the **Name** parameter.</span></span> <span data-ttu-id="48b5b-173">Se você direcionar os resultados de um comando que não produz um objeto **ServiceController** ou **String** para `Stop-Service`, mas que produz uma saída contendo uma propriedade chamada **Name**, ele associará a propriedade **Name** da saída ao parâmetro **Name** de `Stop-Service`.</span><span class="sxs-lookup"><span data-stu-id="48b5b-173">If you pipe the results of a command that doesn't produce a **ServiceController** or **String** object to `Stop-Service`, but it does produce output containing a property called **Name**, then it binds the **Name** property from the output to the **Name** parameter of `Stop-Service`.</span></span>

<span data-ttu-id="48b5b-174">Determine o tipo de saída produzido pelo comando `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="48b5b-174">Determine what type of output the `Get-Service` command produces.</span></span>

```powershell
Get-Service -Name w32time | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController
```

<span data-ttu-id="48b5b-175">`Get-Service` produz um tipo de objeto ServiceController.</span><span class="sxs-lookup"><span data-stu-id="48b5b-175">`Get-Service` produces a ServiceController object type.</span></span>

<span data-ttu-id="48b5b-176">Como vimos anteriormente na Ajuda, o parâmetro **InputObject** de `Stop-Service` aceita objetos **ServiceController** por meio do pipeline **por valor** (por tipo).</span><span class="sxs-lookup"><span data-stu-id="48b5b-176">As you previously saw in the help, the **InputObject** parameter of `Stop-Service` accepts **ServiceController** objects via the pipeline **by value** (by type).</span></span> <span data-ttu-id="48b5b-177">Isso significa que, quando os resultados do cmdlet `Get-Service` são direcionados para `Stop-Service`, eles se associam ao parâmetro **InputObject** de `Stop-Service`.</span><span class="sxs-lookup"><span data-stu-id="48b5b-177">This means that when the results of the `Get-Service` cmdlet are piped to `Stop-Service`, they bind to the **InputObject** parameter of `Stop-Service`.</span></span>

```powershell
Get-Service -Name w32time | Stop-Service
```

<span data-ttu-id="48b5b-178">Agora, para experimentar a entrada da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="48b5b-178">Now to try string input.</span></span> <span data-ttu-id="48b5b-179">Direcione `w32time` para `Get-Member` apenas para confirmar que ela é uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="48b5b-179">Pipe `w32time` to `Get-Member` just to confirm that it's a string.</span></span>

```powershell
'w32time' | Get-Member
```

```Output
   TypeName: System.String
```

<span data-ttu-id="48b5b-180">Conforme mostrado anteriormente na Ajuda, o direcionamento de uma cadeia de caracteres para `Stop-Service` a associa **por valor** ao parâmetro **Name** de `Stop-Service`.</span><span class="sxs-lookup"><span data-stu-id="48b5b-180">As previously shown in the help, piping a string to `Stop-Service` binds it **by value** to the **Name** parameter of `Stop-Service`.</span></span> <span data-ttu-id="48b5b-181">Teste isso direcionando `w32time` para `Stop-Service`.</span><span class="sxs-lookup"><span data-stu-id="48b5b-181">Test this by piping `w32time` to `Stop-Service`.</span></span>

```powershell
'w32time' | Stop-Service
```

<span data-ttu-id="48b5b-182">Observe que, no exemplo anterior, usei aspas simples em torno da cadeia de caracteres `w32time`.</span><span class="sxs-lookup"><span data-stu-id="48b5b-182">Notice that in the previous example, I used single quotes around the string `w32time`.</span></span> <span data-ttu-id="48b5b-183">No PowerShell, você sempre deve usar aspas simples em vez de aspas duplas, a menos que o conteúdo da cadeia de caracteres entre aspas contenha uma variável que precise ser expandida para o valor real.</span><span class="sxs-lookup"><span data-stu-id="48b5b-183">In PowerShell, you should always use single quotes instead of double quotes unless the contents of the quoted string contains a variable that needs to be expanded to its actual value.</span></span> <span data-ttu-id="48b5b-184">Usando aspas simples, o PowerShell não precisa analisar o conteúdo contido entre aspas e, portanto, o código é executado um pouco mais rápido.</span><span class="sxs-lookup"><span data-stu-id="48b5b-184">By using single quotes, PowerShell doesn't have to parse the contents contained within the quotes so your code runs a little faster.</span></span>

<span data-ttu-id="48b5b-185">Crie um objeto personalizado para testar a entrada do pipeline pelo nome da propriedade para o parâmetro **Name** de `Stop-Service`.</span><span class="sxs-lookup"><span data-stu-id="48b5b-185">Create a custom object to test pipeline input by property name for the **Name** parameter of `Stop-Service`.</span></span>

```powershell
$CustomObject = [pscustomobject]@{
 Name = 'w32time'
 }
```

<span data-ttu-id="48b5b-186">O conteúdo da variável **CustomObject** é um tipo de objeto **PSCustomObject** e contém uma propriedade chamada **Name**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-186">The contents of the **CustomObject** variable is a **PSCustomObject** object type and it contains a property named **Name**.</span></span>

```powershell
$CustomObject | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Name        NoteProperty string Name=w32time
```

<span data-ttu-id="48b5b-187">Se você for colocar a variável `$CustomObject` entre aspas, o ideal será usar aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="48b5b-187">If you were to surround the `$CustomObject` variable with quotes, you want to use double quotes.</span></span>
<span data-ttu-id="48b5b-188">Caso contrário, usando aspas simples, a cadeia de caracteres literal `$CustomObject` será direcionada para `Get-Member`, em vez de para o valor contido pela variável.</span><span class="sxs-lookup"><span data-stu-id="48b5b-188">Otherwise, using single quotes, the literal string `$CustomObject` is piped to `Get-Member` instead of the value contained by the variable.</span></span>

<span data-ttu-id="48b5b-189">Embora o direcionamento do conteúdo de `$CustomObject` para o cmdlet `Stop-Service` associe-o ao parâmetro **Name**, desta vez, ele o associa **pelo nome da propriedade** em vez de **por valor**, porque o conteúdo de `$CustomObject` é um objeto que tem uma propriedade chamada **Name**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-189">Although piping the contents of `$CustomObject` to `Stop-Service` cmdlet binds to the **Name** parameter, this time it binds **by property name** instead of **by value** because the contents of `$CustomObject` is an object that has a property named **Name**.</span></span>

<span data-ttu-id="48b5b-190">Neste exemplo, crio outro objeto personalizado usando outro nome de propriedade, como **Service**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-190">In this example, I create another custom object using a different property name, such as **Service**.</span></span>

```powershell
$CustomObject = [pscustomobject]@{
  Service = 'w32time'
}
```

<span data-ttu-id="48b5b-191">Um erro é gerado ao tentar direcionar `$CustomObject` para `Stop-Service`, porque ele não produz um objeto **ServiceController** ou **String** e não tem uma propriedade chamada **Name**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-191">An error is generated when trying to pipe `$CustomObject` to `Stop-Service` because it doesn't produce a **ServiceController** or **String** object, and it doesn't have a property named **Name**.</span></span>

```powershell
$CustomObject | Stop-Service
```

```Output
Stop-Service : Cannot find any service with service name '@{Service=w32time}'.
At line:1 char:17
+ $CustomObject | Stop-Service
+
    + CategoryInfo          : ObjectNotFound: (@{Service=w32time}:String) [Stop-Service]
   , ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.S
   topServiceCommand
```

<span data-ttu-id="48b5b-192">Se a saída de um comando não for alinhada com as opções de entrada do pipeline para outro comando, `Select-Object` poderá ser usado para renomear a propriedade, de modo que as propriedades sejam alinhadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="48b5b-192">If the output of one command doesn't line up with the pipeline input options for another command, `Select-Object` can be used to rename the property so that the properties lineup correctly.</span></span>

```powershell
$CustomObject |
  Select-Object -Property @{name='Name';expression={$_.Service}} |
    Stop-Service
```

<span data-ttu-id="48b5b-193">Neste exemplo, `Select-Object` foi usado para renomear a propriedade **Service** para uma propriedade chamada **Name**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-193">In this example, `Select-Object` was used to rename the **Service** property to a property named **Name**.</span></span>

<span data-ttu-id="48b5b-194">A sintaxe desse exemplo pode parecer um pouco complicada a princípio.</span><span class="sxs-lookup"><span data-stu-id="48b5b-194">The syntax this example may seem a little complicated at first.</span></span> <span data-ttu-id="48b5b-195">O que aprendi é que você nunca aprenderá a sintaxe copiando e colando o código.</span><span class="sxs-lookup"><span data-stu-id="48b5b-195">What I have learned is that you'll never learn the syntax by copy and pasting code.</span></span> <span data-ttu-id="48b5b-196">Reserve um tempo para digitar o código.</span><span class="sxs-lookup"><span data-stu-id="48b5b-196">Take the time to type the code in.</span></span> <span data-ttu-id="48b5b-197">Após algum tempo, isso passará a ser algo natural.</span><span class="sxs-lookup"><span data-stu-id="48b5b-197">After a few times, it becomes second nature.</span></span> <span data-ttu-id="48b5b-198">Ter vários monitores é um grande benefício, pois você pode ver o código de exemplo em uma tela e digitá-lo em outro.</span><span class="sxs-lookup"><span data-stu-id="48b5b-198">Having multiple monitors is a huge benefit because you can display the example code on one screen and type it in on another one.</span></span>

<span data-ttu-id="48b5b-199">Ocasionalmente, o ideal é usar um parâmetro que não aceite a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="48b5b-199">Occasionally, you may want to use a parameter that doesn't accept pipeline input.</span></span> <span data-ttu-id="48b5b-200">O exemplo a seguir demonstra o uso da saída de um comando como a entrada de outro.</span><span class="sxs-lookup"><span data-stu-id="48b5b-200">The following example demonstrates using the output of one command as input for another.</span></span> <span data-ttu-id="48b5b-201">Primeiro, salve o nome de exibição de alguns serviços Windows em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="48b5b-201">First save the display name for a couple of Windows services into a text file.</span></span>

```powershell
'Background Intelligent Transfer Service', 'Windows Time' |
Out-File -FilePath $env:TEMP\services.txt
```

<span data-ttu-id="48b5b-202">Execute o comando que fornece a saída necessária entre parênteses como o valor do parâmetro do comando que exige a entrada.</span><span class="sxs-lookup"><span data-stu-id="48b5b-202">You can run the command that provides the needed output within parentheses as the value for the parameter of the command requiring the input.</span></span>

```powershell
Stop-Service -DisplayName (Get-Content -Path $env:TEMP\services.txt)
```

<span data-ttu-id="48b5b-203">Isso é exatamente como a ordem das operações em álgebra para aqueles que se lembram de como ela funciona.</span><span class="sxs-lookup"><span data-stu-id="48b5b-203">This is just like order of operations in Algebra for those of you who remember how it works.</span></span> <span data-ttu-id="48b5b-204">O comando entre parênteses sempre é executado antes da parte externa do comando.</span><span class="sxs-lookup"><span data-stu-id="48b5b-204">The command within parentheses always runs prior to the outer portion of the command.</span></span>

## <a name="powershellget"></a><span data-ttu-id="48b5b-205">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="48b5b-205">PowerShellGet</span></span>

<span data-ttu-id="48b5b-206">O PowerShellGet é um módulo do PowerShell que contém comandos para descoberta, instalação, publicação e atualização de módulos (e outros artefatos) do PowerShell em um repositório do NuGet.</span><span class="sxs-lookup"><span data-stu-id="48b5b-206">PowerShellGet is a PowerShell module that contains commands for discovering, installing, publishing, and updating PowerShell modules (and other artifacts) to or from a NuGet repository.</span></span> <span data-ttu-id="48b5b-207">O PowerShellGet é fornecido no PowerShell versão 5.0 e superior.</span><span class="sxs-lookup"><span data-stu-id="48b5b-207">PowerShellGet ships with PowerShell version 5.0 and higher.</span></span> <span data-ttu-id="48b5b-208">Ele está disponível como um download separado para o PowerShell versão 3.0 e superior.</span><span class="sxs-lookup"><span data-stu-id="48b5b-208">It is available as a separate download for PowerShell version 3.0 and higher.</span></span>

<span data-ttu-id="48b5b-209">A Microsoft hospeda um repositório online do NuGet chamado [Galeria do PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="48b5b-209">Microsoft hosts an online NuGet repository called the [PowerShell Gallery][].</span></span> <span data-ttu-id="48b5b-210">Embora esse repositório seja hospedado pela Microsoft, a maioria dos módulos contidos no repositório não é escrita pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="48b5b-210">Although this repository is hosted by Microsoft, the majority of the modules contained within the repository aren't written by Microsoft.</span></span> <span data-ttu-id="48b5b-211">Qualquer código obtido na Galeria do PowerShell deve ser examinado detalhadamente em um ambiente de teste isolado antes de ser considerado adequado para uso em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="48b5b-211">Any code obtain from the PowerShell Gallery should be thoroughly reviewed in an isolated test environment before being considered suitable for use in a production environment.</span></span>

<span data-ttu-id="48b5b-212">A maioria das empresas desejará hospedar o próprio repositório do NuGet particular interno, no qual poderá publicar módulos somente para uso interno, bem como módulos que ela baixou de outras fontes depois de validá-los como não sendo mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="48b5b-212">Most companies will want to host their own internal private NuGet repository where they can post their internal use only modules as well as modules that they've downloaded from other sources once they've validated them as being non-malicious.</span></span>

<span data-ttu-id="48b5b-213">Use o cmdlet `Find-Module` que faz parte do módulo PowerShellGet para localizar um módulo na Galeria do PowerShell que escrevi chamado MrToolkit.</span><span class="sxs-lookup"><span data-stu-id="48b5b-213">Use the `Find-Module` cmdlet that's part of the PowerShellGet module to find a module in the PowerShell Gallery that I wrote named MrToolkit.</span></span>

```powershell
Find-Module -Name MrToolkit
```

```Output
NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with
NuGet-based repositories. The NuGet provider must be available in 'C:\Program
Files\PackageManagement\ProviderAssemblies' or
'C:\Users\MrAdmin\AppData\Local\PackageManagement\ProviderAssemblies'. You can also
install the NuGet provider by running 'Install-PackageProvider -Name NuGet
-MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to install and import the
NuGet provider now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.1        MrToolkit                           PSGallery            Misc PowerShell Tools
```

<span data-ttu-id="48b5b-214">Na primeira vez que você usar um dos comandos do módulo PowerShellGet, precisará instalar o provedor do NuGet.</span><span class="sxs-lookup"><span data-stu-id="48b5b-214">The first time you use one of the commands from the PowerShellGet module, you'll be prompted to install the NuGet provider.</span></span>

<span data-ttu-id="48b5b-215">Para instalar o módulo MrToolkit, redirecione o comando anterior para `Install-Module`.</span><span class="sxs-lookup"><span data-stu-id="48b5b-215">To install the MrToolkit module, pipe the previous command to `Install-Module`.</span></span>

```powershell
Find-Module -Name MrToolkit | Install-Module
```

```Output
Untrusted repository
You are installing the modules from an untrusted repository. If you trust this
repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet.
Are you sure you want to install the modules from
'https://www.powershellgallery.com/api/v2/'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): y
```

<span data-ttu-id="48b5b-216">Como a Galeria do PowerShell é um repositório não confiável, ele solicita que você aprove a instalação do módulo.</span><span class="sxs-lookup"><span data-stu-id="48b5b-216">Since the PowerShell Gallery is an untrusted repository, it prompts you to approve the installation of the module.</span></span>

## <a name="finding-pipeline-input-the-easy-way"></a><span data-ttu-id="48b5b-217">Como localizar a entrada do pipeline da maneira fácil</span><span class="sxs-lookup"><span data-stu-id="48b5b-217">Finding pipeline input the easy way</span></span>

<span data-ttu-id="48b5b-218">O módulo MrToolkit contém uma função chamada `Get-MrPipelineInput`.</span><span class="sxs-lookup"><span data-stu-id="48b5b-218">The MrToolkit module contains a function named `Get-MrPipelineInput`.</span></span> <span data-ttu-id="48b5b-219">Esse cmdlet pode ser usado para determinar com facilidade quais parâmetros de um comando aceitam a entrada do pipeline, que tipo de objeto eles aceitam e se aceitam a entrada do pipeline **por valor** ou **pelo nome da propriedade**.</span><span class="sxs-lookup"><span data-stu-id="48b5b-219">This cmdlet can be used to easily determine which parameters of a command accept pipeline input, what type of object they accept, and if they accept pipeline input **by value** or **by property name**.</span></span>

```powershell
Get-MrPipelineInput -Name Stop-Service
```

```Output
ParameterName ParameterType                             ValueFromPipeline ValueFromPipelineByPropertyName
------------- -------------                             ----------------- ---------------
InputObject   System.ServiceProcess.ServiceController[]              True           False
Name          System.String[]                                        True            True
```

<span data-ttu-id="48b5b-220">Como você pode ver, as mesmas informações que determinamos anteriormente por meio da Ajuda podem ser determinadas com facilidade por meio dessa função.</span><span class="sxs-lookup"><span data-stu-id="48b5b-220">As you can see, the same information we previously determined by sifting through the help can easily be determined with this function.</span></span>

## <a name="summary"></a><span data-ttu-id="48b5b-221">Resumo</span><span class="sxs-lookup"><span data-stu-id="48b5b-221">Summary</span></span>

<span data-ttu-id="48b5b-222">Neste capítulo, você aprendeu mais sobre os comandos de uma linha do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48b5b-222">In this chapter, you've learned about PowerShell one-liners.</span></span> <span data-ttu-id="48b5b-223">Você descobriu que o número de linhas físicas nas quais um comando está não tem nada a ver com o fato de ele ser ou não um comando de uma linha do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48b5b-223">You've learned that the number of physical lines that a command is on has nothing to do with whether or not it's a PowerShell one-liner.</span></span> <span data-ttu-id="48b5b-224">Você também conheceu a filtragem à esquerda, o pipeline e o PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="48b5b-224">You've also learned about filtering left, the pipeline, and PowerShellGet.</span></span>

## <a name="review"></a><span data-ttu-id="48b5b-225">Revisão</span><span class="sxs-lookup"><span data-stu-id="48b5b-225">Review</span></span>

1. <span data-ttu-id="48b5b-226">O que é um comando de uma linha do PowerShell?</span><span class="sxs-lookup"><span data-stu-id="48b5b-226">What is a PowerShell one-liner?</span></span>
1. <span data-ttu-id="48b5b-227">Quais são alguns dos caracteres em que as quebras de linha naturais podem ocorrer no PowerShell?</span><span class="sxs-lookup"><span data-stu-id="48b5b-227">What are some of the characters where natural line breaks can occur in PowerShell?</span></span>
1. <span data-ttu-id="48b5b-228">Por que você deve realizar a filtragem à esquerda?</span><span class="sxs-lookup"><span data-stu-id="48b5b-228">Why should you filter left?</span></span>
1. <span data-ttu-id="48b5b-229">Quais são as duas maneiras pelas quais um comando do PowerShell pode aceitar a entrada do pipeline?</span><span class="sxs-lookup"><span data-stu-id="48b5b-229">What are the two ways that a PowerShell command can accept pipeline input?</span></span>
1. <span data-ttu-id="48b5b-230">Por que você não deve confiar nos comandos encontrados na Galeria do PowerShell?</span><span class="sxs-lookup"><span data-stu-id="48b5b-230">Why shouldn't you trust commands found in the PowerShell Gallery?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="48b5b-231">Leitura recomendada</span><span class="sxs-lookup"><span data-stu-id="48b5b-231">Recommended Reading</span></span>

- <span data-ttu-id="48b5b-232">[about_Pipelines][]</span><span class="sxs-lookup"><span data-stu-id="48b5b-232">[about_Pipelines][]</span></span>
- <span data-ttu-id="48b5b-233">[about_Command_Syntax][]</span><span class="sxs-lookup"><span data-stu-id="48b5b-233">[about_Command_Syntax][]</span></span>
- <span data-ttu-id="48b5b-234">[about_Parameters][]</span><span class="sxs-lookup"><span data-stu-id="48b5b-234">[about_Parameters][]</span></span>
- <span data-ttu-id="48b5b-235">[PowerShellGet: A maneira MAIS FÁCIL de descobrir, instalar e atualizar módulos do PowerShell][psget]</span><span class="sxs-lookup"><span data-stu-id="48b5b-235">[PowerShellGet: The BIG EASY way to discover, install, and update PowerShell modules][psget]</span></span>

<!-- link references-->
[about_Pipelines]: /powershell/module/microsoft.powershell.core/about/about_pipelines
[about_Command_Syntax]: /powershell/module/microsoft.powershell.core/about/about_command_syntax
[about_Parameters]: /powershell/module/microsoft.powershell.core/about/about_parameters
[psget]: https://mikefrobbins.com/2015/04/23/powershellget-the-big-easy-way-to-discover-install-and-update-powershell-modules/
[Galeria do PowerShell]: https://www.powershellgallery.com/
[PowerShell Gallery]: https://www.powershellgallery.com/
