---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Com usar o Mecanismo Windows PowerShell 2.0
ms.openlocfilehash: c5ac92159d63e5669643908016186ed32dfb46db
ms.sourcegitcommit: 3e343f005fe76960c998ef1869a1a093d37ef349
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85216015"
---
# <a name="using-the-windows-powershell-20-engine"></a><span data-ttu-id="19be9-103">Com usar o Mecanismo Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="19be9-103">Using the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="19be9-104">O Windows PowerShell foi projetado para ser compatível com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="19be9-104">Windows PowerShell is designed to be backward compatible with previous versions.</span></span> <span data-ttu-id="19be9-105">Cmdlets, provedores, snap-ins, módulos e scripts escritos para o Windows PowerShell 2.0 são executados sem alteração em versões mais recentes do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19be9-105">Cmdlets, providers, snap-ins, modules, and scripts written for Windows PowerShell 2.0 run unchanged in newer versions Windows PowerShell.</span></span> <span data-ttu-id="19be9-106">No entanto, o Microsoft .NET Framework 4 alterou a política de ativação de runtime.</span><span class="sxs-lookup"><span data-stu-id="19be9-106">However, Microsoft .NET Framework 4 changed the runtime activation policy.</span></span>
<span data-ttu-id="19be9-107">Os programas de host do Windows PowerShell escritos para o Windows PowerShell 2.0 e compilados com o CLR (Common Language Runtime) 2.0 não podem ser executados sem modificação nas novas versões do Windows PowerShell que são compiladas com o CLR 4.0 (ou superior).</span><span class="sxs-lookup"><span data-stu-id="19be9-107">Windows PowerShell host programs written for Windows PowerShell 2.0 and compiled with Common Language Runtime (CLR) 2.0 cannot run without modification in new versions Windows PowerShell that are compiled with CLR 4.0 (or higher).</span></span>

<span data-ttu-id="19be9-108">O Mecanismo Windows PowerShell 2.0 deve ser usado somente quando um programa de script ou de host existente não pode ser executado, porque ele é incompatível com o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="19be9-108">The Windows PowerShell 2.0 Engine is intended to be used only when an existing script or host program cannot run because it is incompatible with Windows PowerShell 5.1.</span></span> <span data-ttu-id="19be9-109">Exemplos disso incluem as versões mais antigas dos módulos do SQL Server ou do Exchange.</span><span class="sxs-lookup"><span data-stu-id="19be9-109">Examples of this include older versions of Exchange or SQL Server modules.</span></span> <span data-ttu-id="19be9-110">Tais casos devem ser raros.</span><span class="sxs-lookup"><span data-stu-id="19be9-110">Such cases are expected to be rare.</span></span>

<span data-ttu-id="19be9-111">Muitos programas que exigem o Mecanismo Windows PowerShell 2.0 o inicia automaticamente.</span><span class="sxs-lookup"><span data-stu-id="19be9-111">Many programs that require the Windows PowerShell 2.0 Engine start it automatically.</span></span> <span data-ttu-id="19be9-112">Essas instruções são incluídas para as raras situações em que você precisa iniciar o mecanismo manualmente.</span><span class="sxs-lookup"><span data-stu-id="19be9-112">These instructions are included for the rare situations in which you need to start the engine manually.</span></span>

## <a name="deprecation-and-security-concerns"></a><span data-ttu-id="19be9-113">Reprovação e problemas de segurança</span><span class="sxs-lookup"><span data-stu-id="19be9-113">Deprecation and security concerns</span></span>

<span data-ttu-id="19be9-114">O Windows PowerShell 2.0 foi preterido em agosto de 2017.</span><span class="sxs-lookup"><span data-stu-id="19be9-114">Windows PowerShell 2.0 was deprecated in August, 2017.</span></span> <span data-ttu-id="19be9-115">Para obter mais informações, confira o [comunicado][] no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19be9-115">For more information, see the [announcement][] on the PowerShell blog.</span></span>

<span data-ttu-id="19be9-116">O Windows PowerShell 2.0 não tem uma quantidade significativa dos recursos de proteção e segurança adicionados às versões 3, 4 e 5.</span><span class="sxs-lookup"><span data-stu-id="19be9-116">Windows PowerShell 2.0 is missing a significant amount of the hardening and security features added in versions 3, 4, and 5.</span></span> <span data-ttu-id="19be9-117">Recomendamos expressamente que os usuários não o usem, se possível.</span><span class="sxs-lookup"><span data-stu-id="19be9-117">We highly, highly recommend that users not use it if they can help it.</span></span> <span data-ttu-id="19be9-118">Para obter mais informações, confira [Uma comparação da segurança da linguagem de script e do shell][] e [PowerShell ♥ a Equipe Azul][blueteam].</span><span class="sxs-lookup"><span data-stu-id="19be9-118">For more information, see [A Comparison of Shell and Scripting Language Security][] and [PowerShell ♥ the Blue Team][blueteam].</span></span>

## <a name="installing-and-enabling-required-programs"></a><span data-ttu-id="19be9-119">Instalar e habilitar os programas necessários</span><span class="sxs-lookup"><span data-stu-id="19be9-119">Installing and Enabling Required Programs</span></span>

<span data-ttu-id="19be9-120">Antes de iniciar o Mecanismo Windows PowerShell 2.0, habilite o Mecanismo Windows PowerShell 2.0 e o Microsoft .NET Framework 3.5 com o Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="19be9-120">Before starting the Windows PowerShell 2.0 Engine, enable the Windows PowerShell 2.0 Engine and Microsoft .NET Framework 3.5 with Service Pack 1.</span></span> <span data-ttu-id="19be9-121">Para ver as instruções, consulte [Instalar o Windows PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="19be9-121">For instructions, see [Installing Windows PowerShell][].</span></span>

<span data-ttu-id="19be9-122">Os sistemas nos quais o Windows Management Framework 3.0 ou superior está instalado têm todos os componentes necessários.</span><span class="sxs-lookup"><span data-stu-id="19be9-122">Systems on which Windows Management Framework 3.0 or higher is installed have all of the required components.</span></span> <span data-ttu-id="19be9-123">Nenhuma outra configuração é necessária.</span><span class="sxs-lookup"><span data-stu-id="19be9-123">No further configuration is necessary.</span></span> <span data-ttu-id="19be9-124">Para obter informações sobre como instalar o Windows Management Framework, confira [Instalar e configurar o WMF][].</span><span class="sxs-lookup"><span data-stu-id="19be9-124">For information about installing Windows Management Framework, see [Install and configure WMF][].</span></span>

## <a name="how-to-start-the-windows-powershell-20-engine"></a><span data-ttu-id="19be9-125">Como iniciar o Mecanismo Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="19be9-125">How to start the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="19be9-126">Ao iniciar o Windows PowerShell a versão mais recente é iniciada por padrão.</span><span class="sxs-lookup"><span data-stu-id="19be9-126">When you start Windows PowerShell the newest version starts by default.</span></span> <span data-ttu-id="19be9-127">Para iniciar o Windows PowerShell com o Mecanismo Windows PowerShell 2.0, use o parâmetro Version de `PowerShell.exe`.</span><span class="sxs-lookup"><span data-stu-id="19be9-127">To start Windows PowerShell with the Windows PowerShell 2.0 Engine, use the Version parameter of `PowerShell.exe`.</span></span> <span data-ttu-id="19be9-128">Você pode executar o comando no prompt de comando, incluindo o Windows PowerShell e Cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="19be9-128">You can run the command at any command prompt, including Windows PowerShell and Cmd.exe.</span></span>

```
PowerShell.exe -Version 2
```

## <a name="how-to-start-a-remote-session-with-the-windows-powershell-20-engine"></a><span data-ttu-id="19be9-129">Como iniciar uma sessão remota com o Mecanismo Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="19be9-129">How to start a remote session with the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="19be9-130">Para executar o Mecanismo Windows PowerShell 2.0 em uma sessão remota, crie uma configuração de sessão (também conhecida como _ponto de extremidade_) no computador remoto que carrega o Mecanismo Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="19be9-130">To run the Windows PowerShell 2.0 Engine in a remote session, create a session configuration (also known as an _endpoint_) on the remote computer that loads the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="19be9-131">A configuração da sessão é salva no computador remoto e pode ser usada por qualquer usuário autorizado para criar sessões que utilizam o Mecanismo Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="19be9-131">The session configuration is saved on the remote computer and can be used by any authorized user to create sessions that use the Windows PowerShell 2.0 Engine.</span></span>

<span data-ttu-id="19be9-132">Essa é uma tarefa avançada que normalmente é executada por um administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="19be9-132">This is an advanced task that is typically performed by a system administrator.</span></span>

<span data-ttu-id="19be9-133">O procedimento a seguir usa o parâmetro **PSVersion** do cmdlet [Register-PSSessionConfiguration][] para criar uma Mecanismo Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="19be9-133">The following procedure uses the **PSVersion** parameter of the [Register-PSSessionConfiguration][] cmdlet to create a session configuration that uses the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="19be9-134">Você também pode usar o parâmetro **PowerShellVersion** do cmdlet [New-PSSessionConfigurationFile][] para criar um arquivo de configuração de sessão para uma sessão que carrega o Mecanismo Windows PowerShell 2.0 e você pode usar o parâmetro **PSVersion** do parâmetro [Set-PSSessionConfiguration][] para alterar uma configuração de sessão para usar o Mecanismo Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="19be9-134">You can also use the **PowerShellVersion** parameter of the [New-PSSessionConfigurationFile][] cmdlet to create a session configuration file for a session that loads the Windows PowerShell 2.0 Engine and you can use the **PSVersion** parameter of the [Set-PSSessionConfiguration][] parameter to change a session configuration to use the Windows PowerShell 2.0 Engine.</span></span>

<span data-ttu-id="19be9-135">Para obter mais informações sobre como criar arquivos de configuração, confira [about_Session_Configuration_Files][].</span><span class="sxs-lookup"><span data-stu-id="19be9-135">For more information about session configuration files, see [about_Session_Configuration_Files][].</span></span>
<span data-ttu-id="19be9-136">Para obter informações sobre as configurações de sessão, incluindo instalação e segurança, confira [about_Session_Configurations][].</span><span class="sxs-lookup"><span data-stu-id="19be9-136">For information about session configurations, including setup and security, see [about_Session_Configurations][].</span></span>

### <a name="to-start-a-remote-windows-powershell-20-session"></a><span data-ttu-id="19be9-137">Para iniciar uma sessão remota do Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="19be9-137">To start a remote Windows PowerShell 2.0 session</span></span>

1. <span data-ttu-id="19be9-138">Para criar uma configuração de sessão que exige o Mecanismo Windows PowerShell 2.0, use o parâmetro **PSVersion** do cmdlet `Register-PSSessionConfiguration` com um valor igual a `2.0`.</span><span class="sxs-lookup"><span data-stu-id="19be9-138">To create a session configuration that requires the Windows PowerShell 2.0 Engine, use the **PSVersion** parameter of the `Register-PSSessionConfiguration` cmdlet with a value of `2.0`.</span></span>
   <span data-ttu-id="19be9-139">Execute este comando no computador no “lado do servidor” ou na extremidade de recebimento de uma conexão.</span><span class="sxs-lookup"><span data-stu-id="19be9-139">Run this command on the computer at the "server side" or receiving end of the connection.</span></span>

   <span data-ttu-id="19be9-140">O comando de exemplo a seguir cria a configuração de sessão PS2 no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="19be9-140">The following sample command creates the PS2 session configuration on the Server01 computer.</span></span> <span data-ttu-id="19be9-141">Para executar esse comando, inicie o Windows PowerShell com a opção **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="19be9-141">To run this command, start Windows PowerShell with the **Run as administrator** option.</span></span>

   ```powershell
   Register-PSSessionConfiguration -Name PS2 -PSVersion 2.0
   ```

1. <span data-ttu-id="19be9-142">Para criar uma sessão no computador Server01 que usa a configuração de sessão PS2, use o parâmetro **ConfigurationName** dos cmdlets que criam uma sessão remota, como o cmdlet New-PSSession.</span><span class="sxs-lookup"><span data-stu-id="19be9-142">To create a session on the Server01 computer that uses the PS2 session configuration, use the **ConfigurationName** parameter of cmdlets that create a remote session, such as the \`New-PSSession cmdlet.</span></span>

   <span data-ttu-id="19be9-143">Quando uma sessão que usa a configuração de sessão é iniciada, o Mecanismo Windows PowerShell 2.0 é automaticamente carregado na sessão.</span><span class="sxs-lookup"><span data-stu-id="19be9-143">When a session that uses the session configuration starts, the Windows PowerShell 2.0 Engine is automatically loaded into the session.</span></span>

   <span data-ttu-id="19be9-144">O comando a seguir inicia uma sessão no computador Server01 que usa a configuração de sessão PS2.</span><span class="sxs-lookup"><span data-stu-id="19be9-144">The following command starts a session on the Server01 computer that uses the PS2 session configuration.</span></span> <span data-ttu-id="19be9-145">O comando salva a sessão na variável `$s`.</span><span class="sxs-lookup"><span data-stu-id="19be9-145">The command saves the session in the `$s` variable.</span></span>

   ```powershell
   $s = New-PSSession -ComputerName Server01 -ConfigurationName PS2
   ```

## <a name="how-to-start-a-background-job-with-the-windows-powershell-20-engine"></a><span data-ttu-id="19be9-146">Como iniciar um trabalho em segundo plano com o Mecanismo Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="19be9-146">How to start a background job with the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="19be9-147">Para iniciar um trabalho em segundo plano com o Mecanismo Windows PowerShell 2.0, use o parâmetro **PSVersion** do cmdlet [Start-Job][].</span><span class="sxs-lookup"><span data-stu-id="19be9-147">To start a background job with the Windows PowerShell 2.0 Engine, use the **PSVersion** parameter of the [Start-Job][] cmdlet.</span></span>

<span data-ttu-id="19be9-148">O comando a seguir inicia um trabalho em segundo plano com o Mecanismo Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="19be9-148">The following command starts a background job with the Windows PowerShell 2.0 Engine</span></span>

```powershell
Start-Job {Get-Process} -PSVersion 2.0
```

<span data-ttu-id="19be9-149">Para obter mais informações sobre trabalhos em segundo plano, consulte [about_Jobs][].</span><span class="sxs-lookup"><span data-stu-id="19be9-149">For more information about background jobs, see [about_Jobs][].</span></span>

<!-- link references -->
[comunicado]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[announcement]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[Uma comparação da segurança da linguagem de script e do shell]: https://devblogs.microsoft.com/powershell/a-comparison-of-shell-and-scripting-language-security/
[A Comparison of Shell and Scripting Language Security]: https://devblogs.microsoft.com/powershell/a-comparison-of-shell-and-scripting-language-security/
[blueteam]: https://devblogs.microsoft.com/powershell/powershell-the-blue-team/
[Instalar o Windows PowerShell]: install/Installing-Windows-PowerShell.md
[Installing Windows PowerShell]: install/Installing-Windows-PowerShell.md
[Instalar e configurar o WMF]: wmf/setup/install-configure.md
[Install and configure WMF]: wmf/setup/install-configure.md
[Register-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration
[New-PSSessionConfigurationFile]: /powershell/module/Microsoft.PowerShell.Core/New-PSSessionConfigurationFile
[Set-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration
[about_Session_Configuration_Files]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configuration_Files
[about_Session_Configurations]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configurations
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[about_Jobs]: /powershell/module/microsoft.powershell.core/about/about_jobs
