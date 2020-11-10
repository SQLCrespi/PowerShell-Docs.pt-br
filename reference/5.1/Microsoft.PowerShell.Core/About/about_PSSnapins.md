---
description: Descreve os snap-ins do Windows PowerShell e mostra como usá-los e gerenciá-los.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSnapins
ms.openlocfilehash: 494b3275e4fe8a3aacdc358317950542962957cf
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388885"
---
# <a name="about-pssnapins"></a><span data-ttu-id="6df93-104">Sobre os PSSnapins</span><span class="sxs-lookup"><span data-stu-id="6df93-104">About PSSnapins</span></span>

## <a name="short-description"></a><span data-ttu-id="6df93-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="6df93-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="6df93-106">Descreve os snap-ins do Windows PowerShell e mostra como usá-los e gerenciá-los.</span><span class="sxs-lookup"><span data-stu-id="6df93-106">Describes  Windows PowerShell snap-ins and shows how to use and manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="6df93-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="6df93-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="6df93-108">Um snap-in do Windows PowerShell é um assembly Microsoft .NET Framework que contém os provedores do Windows PowerShell e \/ ou cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6df93-108">A Windows PowerShell snap-in is a Microsoft .NET Framework assembly that contains Windows PowerShell providers and\/or cmdlets.</span></span> <span data-ttu-id="6df93-109">O Windows PowerShell inclui um conjunto de snap-ins básicos, mas você pode estender o poder e o valor do Windows PowerShell adicionando snap-ins que contêm provedores e cmdlets que você cria ou obtém de outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="6df93-109">Windows PowerShell includes a set of basic snap-ins, but you can extend the power and value of Windows PowerShell by adding snap-ins that contain providers and cmdlets that you create or get from others.</span></span>

<span data-ttu-id="6df93-110">Quando você adiciona um snap-in, os cmdlets e provedores que ele contém estão imediatamente disponíveis para uso na sessão atual, mas a alteração afeta apenas a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6df93-110">When you add a snap-in, the cmdlets and providers that it contains are immediately available for use in the current session, but the change affects only the current session.</span></span>

<span data-ttu-id="6df93-111">Para adicionar o snap-in a todas as sessões futuras, salve-o em seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6df93-111">To add the snap-in to all future sessions, save it in your Windows PowerShell profile.</span></span> <span data-ttu-id="6df93-112">Você também pode usar o cmdlet Export-Console para salvar os nomes de snap-in em um arquivo de console e, em seguida, usá-lo em sessões futuras.</span><span class="sxs-lookup"><span data-stu-id="6df93-112">You can also use the Export-Console cmdlet to save the snap-in names to a console file and then use it in future sessions.</span></span> <span data-ttu-id="6df93-113">Você pode até mesmo salvar vários arquivos de console, cada um com um conjunto diferente de snap-ins.</span><span class="sxs-lookup"><span data-stu-id="6df93-113">You can even save multiple console files, each with a different set of snap-ins.</span></span>

<span data-ttu-id="6df93-114">Observação: os snap-ins (PSSnapins) do Windows PowerShell estão disponíveis para uso no Windows PowerShell 3,0 e no Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="6df93-114">NOTE: Windows PowerShell snap-ins (PSSnapins) are available for use in Windows PowerShell 3.0 and Windows PowerShell 2.0.</span></span> <span data-ttu-id="6df93-115">Eles podem ser alterados ou indisponíveis nas versões subsequentes.</span><span class="sxs-lookup"><span data-stu-id="6df93-115">They might be altered or unavailable in subsequent versions.</span></span> <span data-ttu-id="6df93-116">Para compactar provedores e cmdlets do Windows PowerShell, use módulos.</span><span class="sxs-lookup"><span data-stu-id="6df93-116">To package Windows PowerShell cmdlets and providers, use modules.</span></span> <span data-ttu-id="6df93-117">Para obter informações sobre como criar módulos e converter snap-ins em módulos, consulte [escrevendo um módulo do Windows PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span><span class="sxs-lookup"><span data-stu-id="6df93-117">For information about creating modules and converting snap-ins to modules, see [Writing a Windows PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

### <a name="finding-snap-ins"></a><span data-ttu-id="6df93-118">LOCALIZANDO SNAP-INS</span><span class="sxs-lookup"><span data-stu-id="6df93-118">FINDING SNAP-INS</span></span>

<span data-ttu-id="6df93-119">Para obter uma lista dos snap-ins do Windows PowerShell em seu computador, digite:</span><span class="sxs-lookup"><span data-stu-id="6df93-119">To get a list of the  Windows PowerShell snap-ins on your computer, type:</span></span>

```powershell
Get-PSSnapin
```

<span data-ttu-id="6df93-120">Para obter o snap-in para cada provedor do Windows PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="6df93-120">To get the snap-in for each  Windows PowerShell provider, type:</span></span>

```powershell
Get-PSProvider | Format-List name, pssnapin
```

<span data-ttu-id="6df93-121">Para obter uma lista dos cmdlets em um snap-in do Windows PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="6df93-121">To get a list of the cmdlets in a  Windows PowerShell snap-in, type:</span></span>

```powershell
Get-Command -Module <snap-in_name>
```

### <a name="installing-a-snap-in"></a><span data-ttu-id="6df93-122">INSTALANDO UM SNAP-IN</span><span class="sxs-lookup"><span data-stu-id="6df93-122">INSTALLING A SNAP-IN</span></span>

<span data-ttu-id="6df93-123">Os snap-ins internos são registrados no sistema e adicionados à sessão padrão quando você inicia o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6df93-123">The built-in snap-ins are registered in the system and added to the default session when you start Windows PowerShell.</span></span> <span data-ttu-id="6df93-124">No entanto, você precisa registrar snap-ins que você cria ou obtém de outros e, em seguida, adicionar os snap-ins à sua sessão.</span><span class="sxs-lookup"><span data-stu-id="6df93-124">However, you have to register snap-ins that you create or obtain from others and then add the snap-ins to your session.</span></span>

### <a name="registering-a-snap-in"></a><span data-ttu-id="6df93-125">REGISTRANDO UM SNAP-IN</span><span class="sxs-lookup"><span data-stu-id="6df93-125">REGISTERING A SNAP-IN</span></span>

<span data-ttu-id="6df93-126">Um snap-in do Windows PowerShell é um programa escrito em uma linguagem .NET Framework que é compilada em um arquivo. dll.</span><span class="sxs-lookup"><span data-stu-id="6df93-126">A Windows PowerShell snap-in is a program written in a .NET Framework language that is compiled into a .dll file.</span></span> <span data-ttu-id="6df93-127">Para usar os provedores e os cmdlets em um snap-in, você deve primeiro registrar o snap-in (adicioná-lo ao registro).</span><span class="sxs-lookup"><span data-stu-id="6df93-127">To use the providers and cmdlets in a snap-in, you must first register the snap-in (add it to the registry).</span></span>

<span data-ttu-id="6df93-128">A maioria dos snap-ins inclui um programa de instalação (um arquivo. exe ou. msi) que registra o arquivo. dll para você.</span><span class="sxs-lookup"><span data-stu-id="6df93-128">Most snap-ins include an installation program (an .exe or .msi file) that registers the .dll file for you.</span></span> <span data-ttu-id="6df93-129">No entanto, se você receber um snap-in como um arquivo. dll, poderá registrá-lo em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="6df93-129">However, if you receive a snap-in as a .dll file, you can register it on your system.</span></span> <span data-ttu-id="6df93-130">Para obter mais informações, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="6df93-130">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

<span data-ttu-id="6df93-131">Para obter todos os snap-ins registrados no seu sistema ou para verificar se um snap-in está registrado, digite:</span><span class="sxs-lookup"><span data-stu-id="6df93-131">To get all the registered snap-ins on your system or to verify that a snap-in is registered, type:</span></span>

```powershell
Get-PSSnapin -registered
```

### <a name="adding-the-snap-in-to-the-current-session"></a><span data-ttu-id="6df93-132">ADICIONANDO O SNAP-IN À SESSÃO ATUAL</span><span class="sxs-lookup"><span data-stu-id="6df93-132">ADDING THE SNAP-IN TO THE CURRENT SESSION</span></span>

<span data-ttu-id="6df93-133">Para adicionar um snap-in registrado à sessão atual, use o cmdlet Add-PsSnapin.</span><span class="sxs-lookup"><span data-stu-id="6df93-133">To add a registered snap-in to the current session, use the Add-PsSnapin cmdlet.</span></span> <span data-ttu-id="6df93-134">Por exemplo, para adicionar o snap-in Microsoft SQL Server à sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="6df93-134">For example, to add the Microsoft SQL Server snap-in to the session, type:</span></span>

```powershell
Add-PSSnapin sql
```

<span data-ttu-id="6df93-135">Depois que o comando for concluído, os provedores e os cmdlets no snap-in estarão disponíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="6df93-135">After the command is completed, the providers and cmdlets in the snap-in are available in the session.</span></span> <span data-ttu-id="6df93-136">No entanto, eles estão disponíveis apenas na sessão atual, a menos que você os salve.</span><span class="sxs-lookup"><span data-stu-id="6df93-136">However, they are available only in the current session unless you save them.</span></span>

### <a name="saving-the-snap-ins"></a><span data-ttu-id="6df93-137">SALVANDO OS SNAP-INS</span><span class="sxs-lookup"><span data-stu-id="6df93-137">SAVING THE SNAP-INS</span></span>

<span data-ttu-id="6df93-138">Para usar um snap-in em sessões futuras do Windows PowerShell, adicione o comando Add-PsSnapin ao seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6df93-138">To use a snap-in in future Windows PowerShell sessions, add the Add-PsSnapin command to your Windows PowerShell profile.</span></span> <span data-ttu-id="6df93-139">Ou então, exporte os nomes de snap-in para um arquivo de console.</span><span class="sxs-lookup"><span data-stu-id="6df93-139">Or, export the snap-in names to a console file.</span></span>

<span data-ttu-id="6df93-140">Se você adicionar o comando Add-PSSnapin ao seu perfil, ele estará disponível em todas as sessões futuras do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6df93-140">If you add the Add-PSSnapin command to your profile, it is available in all future Windows PowerShell sessions.</span></span> <span data-ttu-id="6df93-141">Se você exportar os nomes dos snap-ins em sua sessão, poderá usar o arquivo de exportação somente quando precisar dos snap-ins.</span><span class="sxs-lookup"><span data-stu-id="6df93-141">If you export the names of the snap-ins in your session, you can use the export file only when you need the snap-ins.</span></span>

<span data-ttu-id="6df93-142">Para adicionar o comando Add-PsSnapin ao seu perfil do Windows PowerShell, abra seu perfil, Cole ou digite o comando e, em seguida, salve o perfil.</span><span class="sxs-lookup"><span data-stu-id="6df93-142">To add the Add-PsSnapin command to your Windows PowerShell profile, open your profile, paste or type the command, and then save the profile.</span></span> <span data-ttu-id="6df93-143">Para obter mais informações, consulte about_Profiles.</span><span class="sxs-lookup"><span data-stu-id="6df93-143">For more information, see about_Profiles.</span></span>

<span data-ttu-id="6df93-144">Para salvar os snap-ins de uma sessão no arquivo de console (. psc1), use o cmdlet Export-Console.</span><span class="sxs-lookup"><span data-stu-id="6df93-144">To save the snap-ins from a session in console file (.psc1), use the Export-Console cmdlet.</span></span> <span data-ttu-id="6df93-145">Por exemplo, para salvar os snap-ins na configuração de sessão atual para o arquivo NewConsole. psc1 no diretório atual, digite:</span><span class="sxs-lookup"><span data-stu-id="6df93-145">For example, to save the snap-ins in the current session configuration to the NewConsole.psc1 file in the current directory, type:</span></span>

```powershell
Export-Console NewConsole
```

<span data-ttu-id="6df93-146">Para obter mais informações, consulte Export-Console.</span><span class="sxs-lookup"><span data-stu-id="6df93-146">For more information, see Export-Console.</span></span>

### <a name="opening-windows-powershell-with-a-console-file"></a><span data-ttu-id="6df93-147">ABRINDO O WINDOWS POWERSHELL COM UM ARQUIVO DE CONSOLE</span><span class="sxs-lookup"><span data-stu-id="6df93-147">OPENING WINDOWS POWERSHELL WITH A CONSOLE FILE</span></span>

<span data-ttu-id="6df93-148">Para usar um arquivo de console que inclui o snap-in, inicie o Windows PowerShell (PowerShell.exe) no prompt de comando no Cmd.exe ou em outra sessão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6df93-148">To use a console file that includes the snap-in, start Windows PowerShell (PowerShell.exe) from the command prompt in Cmd.exe or in another Windows PowerShell session.</span></span> <span data-ttu-id="6df93-149">Use o parâmetro PsConsoleFile para especificar o arquivo de console que inclui o snap-in do.</span><span class="sxs-lookup"><span data-stu-id="6df93-149">Use the PsConsoleFile parameter to specify the console file that includes the snap-in.</span></span> <span data-ttu-id="6df93-150">Por exemplo, o comando a seguir inicia o Windows PowerShell com o arquivo de console NewConsole. psc1:</span><span class="sxs-lookup"><span data-stu-id="6df93-150">For example, the following command starts Windows PowerShell with the NewConsole.psc1 console file:</span></span>

```powershell
PowerShell.exe -psconsolefile NewConsole.psc1
```

<span data-ttu-id="6df93-151">Os provedores e cmdlets no snap-in agora estão disponíveis para uso na sessão.</span><span class="sxs-lookup"><span data-stu-id="6df93-151">The providers and cmdlets in the snapin are now available for use in the session.</span></span>

### <a name="removing-a-snap-in"></a><span data-ttu-id="6df93-152">REMOVENDO UM SNAP-IN</span><span class="sxs-lookup"><span data-stu-id="6df93-152">REMOVING A SNAP-IN</span></span>

<span data-ttu-id="6df93-153">Para remover um snap-in do Windows PowerShell da sessão atual, use o cmdlet Remove-PsSnapin.</span><span class="sxs-lookup"><span data-stu-id="6df93-153">To remove a Windows PowerShell snap-in from the current session, use the Remove-PsSnapin cmdlet.</span></span> <span data-ttu-id="6df93-154">Por exemplo, para remover o snap-in SQL Server da sessão atual, digite:</span><span class="sxs-lookup"><span data-stu-id="6df93-154">For example, to remove the SQL Server snap-in from the current session, type:</span></span>

```powershell
Remove-PSSnapin sql
```

<span data-ttu-id="6df93-155">Esse cmdlet Remove o snap-in da sessão.</span><span class="sxs-lookup"><span data-stu-id="6df93-155">This cmdlet removes the snap-in from the session.</span></span> <span data-ttu-id="6df93-156">O snap-in ainda está carregado, mas os provedores e os cmdlets aos quais ele dá suporte não estão mais disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6df93-156">The snap-in is still loaded, but the providers and cmdlets that it supports are no longer available.</span></span>

### <a name="built-in-commands"></a><span data-ttu-id="6df93-157">COMANDOS INTERNOS</span><span class="sxs-lookup"><span data-stu-id="6df93-157">BUILT-IN COMMANDS</span></span>

<span data-ttu-id="6df93-158">No Windows PowerShell 2,0 e em programas de host de estilo mais antigo no Windows PowerShell 3,0 e posteriores, os comandos internos instalados com o Windows PowerShell são empacotados em snap-ins que são adicionados automaticamente a todas as sessões do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6df93-158">In Windows PowerShell 2.0 and in older-style host programs in Windows PowerShell 3.0 and later, the built-in commands that are installed with Windows PowerShell are packaged in snap-ins that are added automatically to every Windows PowerShell session.</span></span>

<span data-ttu-id="6df93-159">A partir do Windows PowerShell 3,0, em programas de host de estilo mais recente, aqueles que iniciam sessões usando o método InitialSessionState. CreateDefault2 – os comandos internos são empacotados em módulos.</span><span class="sxs-lookup"><span data-stu-id="6df93-159">Beginning in Windows PowerShell 3.0, in newer-style host programs -- those that start sessions by using the InitialSessionState.CreateDefault2 method -- the built-in commands are packaged in modules.</span></span> <span data-ttu-id="6df93-160">A exceção é Microsoft. PowerShell. Core, que sempre aparece como um snap-in.</span><span class="sxs-lookup"><span data-stu-id="6df93-160">The exception is Microsoft.PowerShell.Core, which always appears as a snap-in.</span></span> <span data-ttu-id="6df93-161">O snap-in principal está incluído em cada sessão por padrão.</span><span class="sxs-lookup"><span data-stu-id="6df93-161">The Core snap-in is included in every session by default.</span></span> <span data-ttu-id="6df93-162">Os módulos internos são carregados automaticamente no primeiro uso.</span><span class="sxs-lookup"><span data-stu-id="6df93-162">The built-in modules are loaded automatically on first-use.</span></span>

<span data-ttu-id="6df93-163">Observação: as sessões remotas, incluindo as sessões iniciadas usando o cmdlet New-PSSession, são sessões de estilo mais antigas nas quais os comandos internos são empacotados em snap-ins.</span><span class="sxs-lookup"><span data-stu-id="6df93-163">NOTE: Remote sessions, including sessions that are started by using the New-PSSession cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="6df93-164">Os seguintes snap-ins (ou módulos) são instalados com o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6df93-164">The following snap-ins (or modules) are installed with Windows PowerShell.</span></span>

- <span data-ttu-id="6df93-165">Microsoft. PowerShell. Core-contém provedores e cmdlets usados para gerenciar os recursos básicos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6df93-165">Microsoft.PowerShell.Core - Contains providers and cmdlets used to manage the basic features of Windows PowerShell.</span></span> <span data-ttu-id="6df93-166">Ele inclui o sistema de arquivos, o registro, o alias, o ambiente, a função e os provedores de variáveis e os cmdlets básicos, como Get-Help, Get-Command e Get-History.</span><span class="sxs-lookup"><span data-stu-id="6df93-166">It includes the FileSystem, Registry, Alias, Environment, Function, and Variable providers and basic cmdlets like Get-Help, Get-Command, and Get-History.</span></span>

- <span data-ttu-id="6df93-167">Microsoft. PowerShell. host-contém cmdlets usados pelo host do Windows PowerShell, como Start-Transcript e Stop-transcrição.</span><span class="sxs-lookup"><span data-stu-id="6df93-167">Microsoft.PowerShell.Host - Contains cmdlets used by the Windows PowerShell host, such as Start-Transcript and Stop-Transcript.</span></span>

- <span data-ttu-id="6df93-168">Microsoft. PowerShell. Management-contém cmdlets como Get-Service e Get-ChildItem que são usados para gerenciar recursos baseados no Windows.</span><span class="sxs-lookup"><span data-stu-id="6df93-168">Microsoft.PowerShell.Management - Contains cmdlets such as Get-Service and Get-ChildItem that are used to manage Windows-based features.</span></span>

- <span data-ttu-id="6df93-169">Microsoft. PowerShell. Security-contém o provedor de certificados e os cmdlets usados para gerenciar a segurança do Windows PowerShell, como Get-ACL, Get-AuthenticodeSignature e ConvertTo-SecureString.</span><span class="sxs-lookup"><span data-stu-id="6df93-169">Microsoft.PowerShell.Security - Contains the Certificate provider and cmdlets used to manage Windows PowerShell security, such as Get-Acl, Get-AuthenticodeSignature, and ConvertTo-SecureString.</span></span>

- <span data-ttu-id="6df93-170">Microsoft. PowerShell. Utility-contém cmdlets usados para manipular objetos e dados, como Get-Member, write-host e Format-List.</span><span class="sxs-lookup"><span data-stu-id="6df93-170">Microsoft.PowerShell.Utility - Contains cmdlets used to manipulate objects and data, such as Get-Member, Write-Host, and Format-List.</span></span>

- <span data-ttu-id="6df93-171">Microsoft. WSMan. Management-contém o provedor WSMan e os cmdlets que gerenciam o Serviço Gerenciamento Remoto do Windows, como Connect-WSMan e Enable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="6df93-171">Microsoft.WSMan.Management - Contains the WSMan provider and cmdlets that manage the Windows Remote Management service, such as Connect-WSMan and Enable-WSManCredSSP.</span></span>

## <a name="logging-snap-in-events"></a><span data-ttu-id="6df93-172">REGISTRANDO EVENTOS DE SNAP-IN</span><span class="sxs-lookup"><span data-stu-id="6df93-172">LOGGING SNAP-IN EVENTS</span></span>

<span data-ttu-id="6df93-173">A partir do Windows PowerShell 3,0, você pode registrar eventos de execução para os cmdlets em módulos do Windows PowerShell e snap-ins definindo a propriedade LogPipelineExecutionDetails de módulos e snap-ins como TRUE.</span><span class="sxs-lookup"><span data-stu-id="6df93-173">Beginning in Windows PowerShell 3.0, you can record execution events for the cmdlets in Windows PowerShell modules and snap-ins by setting the LogPipelineExecutionDetails property of modules and snap-ins to TRUE.</span></span> <span data-ttu-id="6df93-174">Para obter mais informações, consulte [about_EventLogs](about_EventLogs.md).</span><span class="sxs-lookup"><span data-stu-id="6df93-174">For more information, see [about_EventLogs](about_EventLogs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6df93-175">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="6df93-175">SEE ALSO</span></span>

[<span data-ttu-id="6df93-176">Add-PsSnapin</span><span class="sxs-lookup"><span data-stu-id="6df93-176">Add-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Add-PSSnapin)

[<span data-ttu-id="6df93-177">Get-PsSnapin</span><span class="sxs-lookup"><span data-stu-id="6df93-177">Get-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSnapin)

[<span data-ttu-id="6df93-178">Remove-PsSnapin</span><span class="sxs-lookup"><span data-stu-id="6df93-178">Remove-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Remove-PSSnapin)

[<span data-ttu-id="6df93-179">Export-Console</span><span class="sxs-lookup"><span data-stu-id="6df93-179">Export-Console</span></span>](xref:Microsoft.PowerShell.Core.Export-Console)

[<span data-ttu-id="6df93-180">Get-Command</span><span class="sxs-lookup"><span data-stu-id="6df93-180">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="6df93-181">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="6df93-181">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="6df93-182">about_Modules</span><span class="sxs-lookup"><span data-stu-id="6df93-182">about_Modules</span></span>](about_Modules.md)

## <a name="keywords"></a><span data-ttu-id="6df93-183">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6df93-183">KEYWORDS</span></span>

<span data-ttu-id="6df93-184">about_Snapins, about_Snap_ins, about_Snap-ins</span><span class="sxs-lookup"><span data-stu-id="6df93-184">about_Snapins, about_Snap_ins, about_Snap-ins</span></span>
