---
title: Getting Started with PowerShell (Introdução ao PowerShell)
description: Em que local encontrar e como iniciar o PowerShell para novos usuários.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 0f72fb5baf5b829142b18ed774261e9b3b66291b
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438017"
---
# <a name="chapter-1---getting-started-with-powershell"></a><span data-ttu-id="46b19-103">Capítulo 1 – Introdução ao PowerShell</span><span class="sxs-lookup"><span data-stu-id="46b19-103">Chapter 1 - Getting Started with PowerShell</span></span>

<span data-ttu-id="46b19-104">Com frequência, descubro que os apresentadores em conferências e reuniões de grupo de usuários já têm o PowerShell em execução quando iniciam apresentações no nível básico.</span><span class="sxs-lookup"><span data-stu-id="46b19-104">I often find that presenters at conferences and user group meetings already have PowerShell running when they start entry-level presentations.</span></span> <span data-ttu-id="46b19-105">Este livro começa respondendo às perguntas que ouvi nessas sessões de participantes que não usavam anteriormente o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46b19-105">This book begins by answering the questions I've heard attendees who haven't previously used PowerShell ask in those sessions.</span></span>

<span data-ttu-id="46b19-106">Especificamente, este capítulo se concentra na localização e na inicialização do PowerShell e na solução de alguns dos pontos problemáticos iniciais que os novos usuários enfrentam com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46b19-106">Specifically, this chapter focuses on finding and launching PowerShell, and solving some of the initial pain points that new users experience with PowerShell.</span></span> <span data-ttu-id="46b19-107">Lembre-se de acompanhar os exemplos mostrados neste capítulo no computador do ambiente de laboratório do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="46b19-107">Be sure to follow along and walk through the examples shown in this chapter on your Windows 10 lab environment computer.</span></span>

## <a name="what-do-i-need-to-get-started-with-powershell"></a><span data-ttu-id="46b19-108">O que é necessário para começar a usar o PowerShell?</span><span class="sxs-lookup"><span data-stu-id="46b19-108">What do I need to get started with PowerShell?</span></span>

<span data-ttu-id="46b19-109">Todas as versões modernas de sistemas operacionais Windows são fornecidas com o PowerShell instalado.</span><span class="sxs-lookup"><span data-stu-id="46b19-109">All modern versions of Windows operating systems ship with PowerShell installed.</span></span> <span data-ttu-id="46b19-110">Se você estiver executando uma versão mais antiga que a 5.1, instale a última versão.</span><span class="sxs-lookup"><span data-stu-id="46b19-110">If you're running a version older than 5.1, you should install the latest version.</span></span>

- <span data-ttu-id="46b19-111">Para fazer a atualização para o Windows PowerShell 5.1, confira [Como atualizar um Windows PowerShell existente][]</span><span class="sxs-lookup"><span data-stu-id="46b19-111">To upgrade to Windows PowerShell 5.1, see [Upgrading existing Windows PowerShell][]</span></span>
- <span data-ttu-id="46b19-112">Instale a última versão do PowerShell, confira [Instalando o PowerShell][]</span><span class="sxs-lookup"><span data-stu-id="46b19-112">To install the latest version of PowerShell, see [Installing PowerShell][]</span></span>

## <a name="where-do-i-find-powershell"></a><span data-ttu-id="46b19-113">Em que local posso encontrar o PowerShell?</span><span class="sxs-lookup"><span data-stu-id="46b19-113">Where do I find PowerShell?</span></span>

<span data-ttu-id="46b19-114">A maneira mais fácil de encontrar o PowerShell no Windows 10 é digitar **PowerShell** na barra de pesquisa, conforme mostrado na Figura 1-1.</span><span class="sxs-lookup"><span data-stu-id="46b19-114">The easiest way to find PowerShell on Windows 10 is to type **PowerShell** into the search bar as shown in Figure 1-1.</span></span>

![Figura 1-1](media/figure1-1.png)

<span data-ttu-id="46b19-116">Observe que quatro atalhos diferentes para o PowerShell são mostrados na Figura 1-1.</span><span class="sxs-lookup"><span data-stu-id="46b19-116">Notice that four different shortcuts for PowerShell are shown in Figure 1-1.</span></span> <span data-ttu-id="46b19-117">O computador usado para fins de demonstração neste livro executa a versão de 64 bits do Windows 10 e, portanto, há uma versão de 64 bits do console do PowerShell e do ISE (Ambiente de Script Integrado) do PowerShell e uma versão de 32 bits de cada um, conforme indicado pelo sufixo (x86) nos atalhos.</span><span class="sxs-lookup"><span data-stu-id="46b19-117">The computer used for demonstration purposes in this book is running the 64-bit version of Windows 10 so there's a 64-bit version of the PowerShell console and the PowerShell ISE (Integrated Scripting Environment), and a 32-bit version of each one as denoted by the (x86) suffix on the shortcuts.</span></span> <span data-ttu-id="46b19-118">Se você estiver executando uma versão de 32 bits do Windows 10, terá apenas dois atalhos.</span><span class="sxs-lookup"><span data-stu-id="46b19-118">If you happen to be running a 32-bit version of Windows 10, you'll only have two shortcuts.</span></span> <span data-ttu-id="46b19-119">Esses itens não têm o sufixo (x86), mas são versões de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="46b19-119">Those items don't have the (x86) suffix, but are 32-bit versions.</span></span> <span data-ttu-id="46b19-120">Se você tem um sistema operacional de 64 bits, minha recomendação é executar a versão de 64 bits do PowerShell, a menos que você tenha um motivo específico para executar a versão de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="46b19-120">If you have a 64-bit operating system, my recommendation is to run the 64-bit version of PowerShell unless you have a specific reason for running the 32-bit version.</span></span>

<span data-ttu-id="46b19-121">Para obter informações sobre como iniciar o PowerShell em outras versões do Windows, confira [Iniciando o Windows PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="46b19-121">For information about starting PowerShell on other versions of Windows, see [Starting Windows PowerShell][].</span></span>

## <a name="how-do-i-launch-powershell"></a><span data-ttu-id="46b19-122">Como fazer para iniciar o PowerShell?</span><span class="sxs-lookup"><span data-stu-id="46b19-122">How do I launch PowerShell?</span></span>

<span data-ttu-id="46b19-123">Nos ambientes corporativos de produção aos quais dou suporte, uso três contas de usuário diferentes do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="46b19-123">In the production enterprise environments that I support, I use three different Active Directory user accounts.</span></span> <span data-ttu-id="46b19-124">Espelhei essas contas no ambiente de laboratório usado neste livro.</span><span class="sxs-lookup"><span data-stu-id="46b19-124">I've mirrored those accounts in the lab environment used in this book.</span></span> <span data-ttu-id="46b19-125">Faço logon no computador Windows 10 como um usuário de domínio que não seja um administrador local ou de domínio.</span><span class="sxs-lookup"><span data-stu-id="46b19-125">I log into the Windows 10 computer as a domain user who is not a domain or local administrator.</span></span>

<span data-ttu-id="46b19-126">Iniciei o console do PowerShell clicando no atalho "Windows PowerShell", conforme mostrado na Figura 1-1.</span><span class="sxs-lookup"><span data-stu-id="46b19-126">I've launched the PowerShell console by clicking on the "Windows PowerShell" shortcut as shown in Figure 1-1.</span></span>

![Figura 1-4](media/figure1-4.png)

<span data-ttu-id="46b19-128">Observe que a barra de título do console do PowerShell indica "Windows PowerShell", conforme mostrado na Figura 1-4.</span><span class="sxs-lookup"><span data-stu-id="46b19-128">Notice that the title bar of the PowerShell console says "Windows PowerShell" as shown in Figure 1-4.</span></span> <span data-ttu-id="46b19-129">Alguns comandos são executados corretamente, mas o PowerShell não pode participar do UAC (Controle de Acesso do Usuário).</span><span class="sxs-lookup"><span data-stu-id="46b19-129">Some commands run fine, but PowerShell can't participate in User Access Control (UAC).</span></span> <span data-ttu-id="46b19-130">Isso significa que não é possível solicitar a elevação para tarefas que exigem a aprovação de um administrador.</span><span class="sxs-lookup"><span data-stu-id="46b19-130">That means it's unable to prompt for elevation for tasks that require the approval of an administrator.</span></span>
<span data-ttu-id="46b19-131">A seguinte mensagem de erro é gerada:</span><span class="sxs-lookup"><span data-stu-id="46b19-131">The following error message is generated:</span></span>

```powershell
Get-Service -Name W32Time | Stop-Service
```

```Output
Stop-Service : Service 'Windows Time (W32Time)' cannot be stopped due to the following
error: Cannot open W32Time service on computer '.'.
At line:1 char:29
+ Get-Service -Name W32Time | Stop-Service
+
    + CategoryInfo          : CloseError: (System.ServiceProcess.ServiceController:ServiceController)
     [Stop-Service], ServiceCommandException
    + FullyQualifiedErrorId : CouldNotStopService,Microsoft.PowerShell.Commands.StopServiceCommand
```

<span data-ttu-id="46b19-132">A solução para esse problema é executar o PowerShell como um usuário de domínio que seja um administrador local.</span><span class="sxs-lookup"><span data-stu-id="46b19-132">The solution to this problem is to run PowerShell as a domain user who is a local administrator.</span></span>
<span data-ttu-id="46b19-133">É assim que a minha segunda conta de usuário de domínio está configurada.</span><span class="sxs-lookup"><span data-stu-id="46b19-133">This is how my second domain user account is configured.</span></span> <span data-ttu-id="46b19-134">Usando a entidade de privilégio mínimo, essa conta NÃO deve ser um administrador de domínio nem ter privilégios elevados no domínio.</span><span class="sxs-lookup"><span data-stu-id="46b19-134">Using the principal of least privilege, this account should NOT be a domain administrator, or have any elevated privileges in the domain.</span></span>

<span data-ttu-id="46b19-135">Feche o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46b19-135">Close PowerShell.</span></span> <span data-ttu-id="46b19-136">Reinicie o console do PowerShell, mas, desta vez, clique com o botão direito do mouse no atalho do **Windows PowerShell** e selecione **Executar como administrador**, conforme mostrado na Figura 1-5.</span><span class="sxs-lookup"><span data-stu-id="46b19-136">Relaunch the PowerShell console, except this time right-click on the **Windows PowerShell** shortcut and select **Run as administrator** as shown in Figure 1-5.</span></span>

![Figura 1-5](media/figure1-5.png)

<span data-ttu-id="46b19-138">Se você estiver conectado ao Windows como um usuário normal, precisará fornecer suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="46b19-138">If you're logged into Windows as a normal user, you'll be prompted for credentials.</span></span> <span data-ttu-id="46b19-139">Vou inserir as credenciais da minha conta de usuário que é um usuário de domínio e um administrador local, conforme mostrado na Figura 1-6.</span><span class="sxs-lookup"><span data-stu-id="46b19-139">I'll enter the credentials for my user account who is a domain user and local admin as shown in Figure 1-6.</span></span>

![Figura 1-6](media/figure1-6.png)

<span data-ttu-id="46b19-141">Depois que o PowerShell for reiniciado como administrador, a barra de título deverá indicar "Administrador: Windows PowerShell", conforme mostrado na Figura 1-7.</span><span class="sxs-lookup"><span data-stu-id="46b19-141">Once PowerShell is relaunched as an administrator, the title bar should say "Administrator: Windows PowerShell" as shown in Figure 1-7.</span></span>

![Figura 1-7](media/figure1-7.png)

<span data-ttu-id="46b19-143">Agora que o PowerShell está sendo executado com privilégios elevados como um administrador local, o UAC não será mais um problema quando um comando for executado no computador local que normalmente exigirá uma solicitação de elevação.</span><span class="sxs-lookup"><span data-stu-id="46b19-143">Now that PowerShell is being run elevated as a local administrator, UAC will no longer be a problem when a command is run on the local computer that would normally require a prompt for elevation.</span></span> <span data-ttu-id="46b19-144">Lembre-se de que qualquer comando executado nessa instância com privilégios elevados do console do PowerShell também é executado com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="46b19-144">Keep in mind though that any command run from this elevated instance of the PowerShell console, also runs elevated.</span></span>

<span data-ttu-id="46b19-145">Para simplificar a localização do PowerShell e iniciá-lo como administrador, recomendo fixá-lo na barra de tarefas e defini-lo para ser iniciado automaticamente como administrador toda vez que for executado.</span><span class="sxs-lookup"><span data-stu-id="46b19-145">To simplify finding PowerShell and launching it as an administrator, I recommend pinning it to the taskbar and setting it to automatically launch as an admin each time it's run.</span></span>

<span data-ttu-id="46b19-146">Pesquise o PowerShell novamente, mas, desta vez, clique com o botão direito do mouse nele e selecione "Fixar na barra de tarefas", conforme mostrado na Figura 1-8.</span><span class="sxs-lookup"><span data-stu-id="46b19-146">Search for PowerShell again, except this time right-click on it and select "Pin to taskbar" as shown in Figure 1-8.</span></span>

![Figura 1-8](media/figure1-8.png)

<span data-ttu-id="46b19-148">Clique com o botão direito do mouse no atalho do PowerShell que agora está fixado à barra de tarefas e selecione Propriedades, conforme mostrado na Figura 1-9.</span><span class="sxs-lookup"><span data-stu-id="46b19-148">Right-click on the PowerShell shortcut that's now pinned to the taskbar and select properties as shown in Figure 1-9.</span></span>

![Figura 1-9](media/figure1-9.png)

<span data-ttu-id="46b19-150">Clique em "Avançado", como indicado no nº 1 na Figura 1-10, marque a caixa de seleção "Executar como administrador", como indicado no nº 2 na Figura 1-10 e clique em OK duas vezes para aceitar as alterações e sair das duas caixas de diálogo.</span><span class="sxs-lookup"><span data-stu-id="46b19-150">Click on "Advanced" as denoted by #1 in Figure 1-10, then check the "Run as administrator" checkbox as denoted by #2 in Figure 1-10, and then click OK twice to accept the changes and exit out of both dialog boxes.</span></span>

![Figura 1-10](media/figure1-10.png)

<span data-ttu-id="46b19-152">Você nunca precisará se preocupar em localizar o PowerShell ou se ele está sendo executado como administrador novamente.</span><span class="sxs-lookup"><span data-stu-id="46b19-152">You'll never have to worry about finding PowerShell or whether or not it's running as an administrator again.</span></span>

<span data-ttu-id="46b19-153">A execução do PowerShell com privilégios elevados como administrador para evitar problemas com o UAC afeta apenas os comandos executados no computador local.</span><span class="sxs-lookup"><span data-stu-id="46b19-153">Running PowerShell elevated as an administrator to prevent having problems with UAC only impacts commands that are run against the local computer.</span></span> <span data-ttu-id="46b19-154">Ele não tem nenhum efeito sobre os comandos direcionados para computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="46b19-154">It has no effect on commands that target remote computers.</span></span>

## <a name="what-version-of-powershell-am-i-running"></a><span data-ttu-id="46b19-155">Qual versão do PowerShell estou executando?</span><span class="sxs-lookup"><span data-stu-id="46b19-155">What version of PowerShell am I running?</span></span>

<span data-ttu-id="46b19-156">Há várias variáveis automáticas no PowerShell que armazenam informações de estado.</span><span class="sxs-lookup"><span data-stu-id="46b19-156">There are a number of automatic variables in PowerShell that store state information.</span></span> <span data-ttu-id="46b19-157">Uma dessas variáveis é `$PSVersionTable`, que contém uma tabela de hash que pode ser usada para exibir as informações relevantes da versão do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="46b19-157">One of these variables is `$PSVersionTable`, which contains a hashtable that can be used to display the relevant PowerShell version information:</span></span>

```powershell
$PSVersionTable
```

```Output
Name                           Value
----                           -----
PSVersion                      5.1.19041.1
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
BuildVersion                   10.0.19041.1
CLRVersion                     4.0.30319.42000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

<span data-ttu-id="46b19-158">As versões mais recentes do Windows PowerShell são distribuídas como parte do WMF (Windows Management Framework).</span><span class="sxs-lookup"><span data-stu-id="46b19-158">Newer versions of Windows PowerShell are distributed as part of the Windows Management Framework (WMF).</span></span> <span data-ttu-id="46b19-159">Uma versão específica do .NET Framework é necessária, dependendo da versão do WMF.</span><span class="sxs-lookup"><span data-stu-id="46b19-159">A specific version of the .NET Framework is required depending on the WMF version.</span></span> <span data-ttu-id="46b19-160">Para fazer a atualização para o Windows PowerShell 5.1, confira [Como atualizar um Windows PowerShell existente][].</span><span class="sxs-lookup"><span data-stu-id="46b19-160">To upgrade to Windows PowerShell 5.1, see [Upgrading existing Windows PowerShell][].</span></span>

## <a name="execution-policy"></a><span data-ttu-id="46b19-161">Política de execução</span><span class="sxs-lookup"><span data-stu-id="46b19-161">Execution Policy</span></span>

<span data-ttu-id="46b19-162">Ao contrário da crença popular, a política de execução no PowerShell não é um limite de segurança.</span><span class="sxs-lookup"><span data-stu-id="46b19-162">Contrary to popular belief, the execution policy in PowerShell is not a security boundary.</span></span> <span data-ttu-id="46b19-163">Ela foi projetada para impedir que um usuário execute um script sem perceber.</span><span class="sxs-lookup"><span data-stu-id="46b19-163">It's designed to prevent a user from unknowingly running a script.</span></span> <span data-ttu-id="46b19-164">Um usuário determinado pode facilmente ignorar a política de execução no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46b19-164">A determined user can easily bypass the execution policy in PowerShell.</span></span> <span data-ttu-id="46b19-165">A Tabela 1-2 mostra a política de execução padrão para os sistemas operacionais Windows atuais.</span><span class="sxs-lookup"><span data-stu-id="46b19-165">Table 1-2 shows the default execution policy for current Windows operating systems.</span></span>

| <span data-ttu-id="46b19-166">Versão do sistema operacional do Windows</span><span class="sxs-lookup"><span data-stu-id="46b19-166">Windows Operating System Version</span></span> | <span data-ttu-id="46b19-167">Política de execução padrão</span><span class="sxs-lookup"><span data-stu-id="46b19-167">Default Execution Policy</span></span> |
| -------------------------------- | ------------------------ |
| <span data-ttu-id="46b19-168">Server 2019</span><span class="sxs-lookup"><span data-stu-id="46b19-168">Server 2019</span></span>                      | <span data-ttu-id="46b19-169">Remota assinada</span><span class="sxs-lookup"><span data-stu-id="46b19-169">Remote Signed</span></span>            |
| <span data-ttu-id="46b19-170">Server 2016</span><span class="sxs-lookup"><span data-stu-id="46b19-170">Server 2016</span></span>                      | <span data-ttu-id="46b19-171">Remota assinada</span><span class="sxs-lookup"><span data-stu-id="46b19-171">Remote Signed</span></span>            |
| <span data-ttu-id="46b19-172">Windows 10</span><span class="sxs-lookup"><span data-stu-id="46b19-172">Windows 10</span></span>                       | <span data-ttu-id="46b19-173">Restrito</span><span class="sxs-lookup"><span data-stu-id="46b19-173">Restricted</span></span>               |

<span data-ttu-id="46b19-174">Seja qual for a configuração de política de execução, qualquer comando do PowerShell pode ser executado de maneira interativa.</span><span class="sxs-lookup"><span data-stu-id="46b19-174">Regardless of the execution policy setting, any PowerShell command can be run interactively.</span></span> <span data-ttu-id="46b19-175">A política de execução afeta somente os comandos em execução em um script.</span><span class="sxs-lookup"><span data-stu-id="46b19-175">The execution policy only affects commands running in a script.</span></span> <span data-ttu-id="46b19-176">O cmdlet `Get-ExecutionPolicy` é usado para determinar qual é a configuração de política de execução atual, e o cmdlet `Set-ExecutionPolicy` é usado para alterar a política de execução.</span><span class="sxs-lookup"><span data-stu-id="46b19-176">The `Get-ExecutionPolicy` cmdlet is used to determine what the current execution policy setting is and the `Set-ExecutionPolicy` cmdlet is used to change the execution policy.</span></span> <span data-ttu-id="46b19-177">Minha recomendação é usar a política **RemoteSigned**, que exige que os scripts baixados sejam assinados por um editor confiável para serem executados.</span><span class="sxs-lookup"><span data-stu-id="46b19-177">My recommendation is to use the **RemoteSigned** policy, which requires downloaded scripts to be signed by a trusted publisher in order to be run.</span></span>

<span data-ttu-id="46b19-178">Verifique a política de execução atual:</span><span class="sxs-lookup"><span data-stu-id="46b19-178">Check the current execution policy:</span></span>

```powershell
Get-ExecutionPolicy
```

```Output
Restricted
```

<span data-ttu-id="46b19-179">Os scripts do PowerShell não poderão ser executados quando a política de execução estiver definida como **Restrita**.</span><span class="sxs-lookup"><span data-stu-id="46b19-179">PowerShell scripts can't be run at all when the execution policy is set to **Restricted**.</span></span> <span data-ttu-id="46b19-180">Essa é a configuração padrão em todos os sistemas operacionais do cliente Windows.</span><span class="sxs-lookup"><span data-stu-id="46b19-180">This is the default setting on all Windows client operating systems.</span></span> <span data-ttu-id="46b19-181">Para demonstrar o problema, salve o código a seguir como um arquivo `.ps1` chamado `Stop-TimeService.ps1`.</span><span class="sxs-lookup"><span data-stu-id="46b19-181">To demonstrate the problem, save the following code as a `.ps1` file named `Stop-TimeService.ps1`.</span></span>

```powershell
Get-Service -Name W32Time | Stop-Service -PassThru
```

<span data-ttu-id="46b19-182">Esse comando é executado de maneira interativa sem erros, desde que o PowerShell seja executado com privilégios elevados como administrador.</span><span class="sxs-lookup"><span data-stu-id="46b19-182">That command runs interactively without error as long as PowerShell is run elevated as an administrator.</span></span> <span data-ttu-id="46b19-183">Mas assim que ele é salvo como um arquivo de script e você tenta executar o script, ele gera um erro:</span><span class="sxs-lookup"><span data-stu-id="46b19-183">But as soon as it's saved as a script file and you try to execute the script, it generates an error:</span></span>

```powershell
.\Stop-TimeService.ps1
```

```Output
.\Stop-TimeService.ps1 : File C:\demo\Stop-TimeService.ps1 cannot be loaded because
running scripts is disabled on this system. For more information, see
about_Execution_Policies at http://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Stop-TimeService.ps1
+
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

<span data-ttu-id="46b19-184">Observe que o erro mostrado no conjunto de resultados anterior informa exatamente qual é o problema (a execução de scripts está desabilitada nesse sistema).</span><span class="sxs-lookup"><span data-stu-id="46b19-184">Notice that the error shown in the previous set of results tells you exactly what the problem is (running scripts is disabled on this system).</span></span> <span data-ttu-id="46b19-185">Quando você executa um comando no PowerShell que gera uma mensagem de erro, leia a mensagem de erro em vez de apenas executar novamente o comando e esperar que ele seja executado com êxito.</span><span class="sxs-lookup"><span data-stu-id="46b19-185">When you run a command in PowerShell that generates an error message, be sure to read the error message instead of just rerunning the command and hoping that it runs successfully.</span></span>

<span data-ttu-id="46b19-186">Altere a política de execução do PowerShell para remota assinada.</span><span class="sxs-lookup"><span data-stu-id="46b19-186">Change the PowerShell execution policy to remote signed.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

```Output
Execution Policy Change
The execution policy helps protect you from scripts that you do not trust. Changing the execution
policy might expose you to the security risks described in the about_Execution_Policies help topic
at http://go.microsoft.com/fwlink/?LinkID=135170. Do you want to change the execution policy?
[Y] Yes [A] Yes to All [N] No [L] No to All [S] Suspend [?] Help (default is "N"):y
```

<span data-ttu-id="46b19-187">Lembre-se de ler o aviso que é exibido ao alterar a política de execução.</span><span class="sxs-lookup"><span data-stu-id="46b19-187">Be sure to read the warning that's displayed when changing the execution policy.</span></span> <span data-ttu-id="46b19-188">Também recomendo dar uma olhada no tópico da Ajuda [about_Execution_Policies][] para verificar se você entendeu as implicações de segurança da alteração da política de execução.</span><span class="sxs-lookup"><span data-stu-id="46b19-188">I also recommend taking a look at the [about_Execution_Policies][] help topic to make sure you understand the security implications of changing the execution policy.</span></span>

<span data-ttu-id="46b19-189">Agora que a política de execução foi definida como **RemoteSigned**, o script `Stop-TimeService.ps1` é executado sem erros.</span><span class="sxs-lookup"><span data-stu-id="46b19-189">Now that the execution policy has been set to **RemoteSigned**, the `Stop-TimeService.ps1` script runs error free.</span></span>

```powershell
.\Stop-TimeService.ps1
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  W32Time            Windows Time
```

<span data-ttu-id="46b19-190">Não se esqueça de iniciar o serviço de Tempo do Windows antes de continuar, caso contrário, você poderá ter problemas imprevistos.</span><span class="sxs-lookup"><span data-stu-id="46b19-190">Be sure to start your Windows Time service before continuing otherwise you may run into unforeseen problems.</span></span>

```powershell
Start-Service -Name w32time
```

## <a name="summary"></a><span data-ttu-id="46b19-191">Resumo</span><span class="sxs-lookup"><span data-stu-id="46b19-191">Summary</span></span>

<span data-ttu-id="46b19-192">Neste capítulo, você aprendeu a localizar e iniciar o PowerShell e a criar um atalho que inicia o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="46b19-192">In this chapter, you've learned how to find and launch PowerShell, and how to create a shortcut that launches PowerShell as an administrator.</span></span> <span data-ttu-id="46b19-193">Você também aprendeu mais sobre a política de execução padrão e como alterá-la.</span><span class="sxs-lookup"><span data-stu-id="46b19-193">You've also learned about the default execution policy and how to change it.</span></span>

## <a name="review"></a><span data-ttu-id="46b19-194">Revisão</span><span class="sxs-lookup"><span data-stu-id="46b19-194">Review</span></span>

1. <span data-ttu-id="46b19-195">Como determinar qual versão do PowerShell um computador está executando?</span><span class="sxs-lookup"><span data-stu-id="46b19-195">How do you determine what PowerShell version a computer is running?</span></span>
1. <span data-ttu-id="46b19-196">Por que é importante iniciar o PowerShell com privilégios elevados como administrador?</span><span class="sxs-lookup"><span data-stu-id="46b19-196">Why is it important to launch PowerShell elevated as an administrator?</span></span>
1. <span data-ttu-id="46b19-197">Como determinar a política de execução atual do PowerShell?</span><span class="sxs-lookup"><span data-stu-id="46b19-197">How do you determine the current PowerShell execution policy?</span></span>
1. <span data-ttu-id="46b19-198">O que a política de execução padrão do PowerShell nos computadores cliente Windows impede que ocorra?</span><span class="sxs-lookup"><span data-stu-id="46b19-198">What does the default PowerShell execution policy on Windows client computers prevent from occurring?</span></span>
1. <span data-ttu-id="46b19-199">Como alterar a política de execução do PowerShell?</span><span class="sxs-lookup"><span data-stu-id="46b19-199">How do you change the PowerShell execution policy?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="46b19-200">Leitura recomendada</span><span class="sxs-lookup"><span data-stu-id="46b19-200">Recommended Reading</span></span>

<span data-ttu-id="46b19-201">Para aqueles que desejam saber mais sobre os tópicos abordados neste capítulo, recomendo a leitura dos tópicos da Ajuda do PowerShell a seguir.</span><span class="sxs-lookup"><span data-stu-id="46b19-201">For those who want to know more information about the topics covered in this chapter, I recommend reading the following PowerShell help topics.</span></span>

- <span data-ttu-id="46b19-202">[about_Automatic_Variables][]</span><span class="sxs-lookup"><span data-stu-id="46b19-202">[about_Automatic_Variables][]</span></span>
- <span data-ttu-id="46b19-203">[about_Execution_Policies][]</span><span class="sxs-lookup"><span data-stu-id="46b19-203">[about_Execution_Policies][]</span></span>

<span data-ttu-id="46b19-204">No próximo capítulo, você aprenderá mais sobre a detectabilidade de comandos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46b19-204">In the next chapter, you'll learn about the discoverability of commands in PowerShell.</span></span> <span data-ttu-id="46b19-205">Uma das coisas que será abordada é como atualizar o PowerShell para que esses tópicos da Ajuda possam ser exibidos diretamente no PowerShell, em vez de precisar exibi-los na Internet.</span><span class="sxs-lookup"><span data-stu-id="46b19-205">One of the things that will be covered is how to update PowerShell so those help topics can be viewed right from within PowerShell instead of having to view them on the internet.</span></span>

<!-- link references -->
[about_Automatic_Variables]: /powershell/module/microsoft.powershell.core/about/about_automatic_variables
[about_Execution_Policies]: /powershell//powershell/module/microsoft.powershell.core/about/about_execution_policies
[Como atualizar um Windows PowerShell existente]: /powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell
[Upgrading existing Windows PowerShell]: /powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell
[Instalando o PowerShell]: /powershell/scripting/install/installing-powershell
[Installing PowerShell]: /powershell/scripting/install/installing-powershell
[Iniciando o Windows PowerShell]: /powershell/scripting/windows-powershell/starting-windows-powershell
[Starting Windows PowerShell]: /powershell/scripting/windows-powershell/starting-windows-powershell
