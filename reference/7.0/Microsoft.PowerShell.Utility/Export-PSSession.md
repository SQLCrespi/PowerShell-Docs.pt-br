---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-PSSession
ms.openlocfilehash: 4ea76140cb126216204bebd5c9c87ed9c1ad2339
ms.sourcegitcommit: d95a7255f6775b2973aa9473611185a5583881ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "106555246"
---
# <span data-ttu-id="16f2b-103">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="16f2b-103">Export-PSSession</span></span>

## <span data-ttu-id="16f2b-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="16f2b-104">Synopsis</span></span>

<span data-ttu-id="16f2b-105">Exporta comandos de outra sessão e salva-os em um módulo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16f2b-105">Exports commands from another session and saves them in a PowerShell module.</span></span>

## <span data-ttu-id="16f2b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="16f2b-106">Syntax</span></span>

### <span data-ttu-id="16f2b-107">Todos</span><span class="sxs-lookup"><span data-stu-id="16f2b-107">All</span></span>

```
Export-PSSession [-OutputModule] <String> [-Force] [-Encoding <Encoding>]
 [[-CommandName] <String[]>] [-AllowClobber] [-ArgumentList <Object[]>]
 [-CommandType <CommandTypes>] [-Module <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-FormatTypeName] <String[]>] [-Certificate <X509Certificate2>] [-Session] <PSSession>
 [<CommonParameters>]
```

## <span data-ttu-id="16f2b-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="16f2b-108">Description</span></span>

<span data-ttu-id="16f2b-109">O `Export-PSSession` cmdlet obtém cmdlets, funções, aliases e outros tipos de comando de outra sessão do PowerShell (PSSession) em um computador local ou remoto e os salva em um módulo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16f2b-109">The `Export-PSSession` cmdlet gets cmdlets, functions, aliases, and other command types from another PowerShell session (PSSession) on a local or remote computer and saves them in a PowerShell module.</span></span> <span data-ttu-id="16f2b-110">Para adicionar os comandos do módulo à sessão atual, use o `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="16f2b-110">To add the commands from the module to the current session, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="16f2b-111">Ao contrário de `Import-PSSession` , que importa os comandos de outra PSSession para a sessão atual, `Export-PSSession` o salva os comandos em um módulo.</span><span class="sxs-lookup"><span data-stu-id="16f2b-111">Unlike `Import-PSSession`, which imports commands from another PSSession into the current session, `Export-PSSession` saves the commands in a module.</span></span> <span data-ttu-id="16f2b-112">Os comandos não são importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-112">The commands are not imported into the current session.</span></span>

<span data-ttu-id="16f2b-113">Para exportar comandos, use o `New-PSSession` cmdlet para criar uma PSSession que tenha os comandos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="16f2b-113">To export commands, use the `New-PSSession` cmdlet to create a PSSession that has the commands that you want to export.</span></span> <span data-ttu-id="16f2b-114">Em seguida, use o `Export-PSSession` cmdlet para exportar os comandos.</span><span class="sxs-lookup"><span data-stu-id="16f2b-114">Then use the `Export-PSSession` cmdlet to export the commands.</span></span>

<span data-ttu-id="16f2b-115">Para evitar conflitos de nome de comando, o padrão para `Export-PSSession` é exportar todos os comandos, exceto os comandos existentes na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-115">To prevent command name conflicts, the default for `Export-PSSession` is to export all commands, except for commands that exist in the current session.</span></span> <span data-ttu-id="16f2b-116">Você pode usar o parâmetro **CommandName** para especificar os comandos a serem exportados.</span><span class="sxs-lookup"><span data-stu-id="16f2b-116">You can use the **CommandName** parameter to specify the commands to export.</span></span>

<span data-ttu-id="16f2b-117">O `Export-PSSession` cmdlet usa o recurso de comunicação remota implícita do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16f2b-117">The `Export-PSSession` cmdlet uses the implicit remoting feature of PowerShell.</span></span> <span data-ttu-id="16f2b-118">Quando você importa comandos para a sessão atual, eles são executados implicitamente na sessão original ou em uma sessão semelhante no computador de origem.</span><span class="sxs-lookup"><span data-stu-id="16f2b-118">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

## <span data-ttu-id="16f2b-119">Exemplos</span><span class="sxs-lookup"><span data-stu-id="16f2b-119">Examples</span></span>

### <span data-ttu-id="16f2b-120">Exemplo 1: exportar comandos de uma PSSession</span><span class="sxs-lookup"><span data-stu-id="16f2b-120">Example 1: Export commands from a PSSession</span></span>

<span data-ttu-id="16f2b-121">Este exemplo cria uma nova PSSession do computador local para o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="16f2b-121">This example creates a new PSSession from the local computer to the Server01 computer.</span></span> <span data-ttu-id="16f2b-122">Todos os comandos, exceto aqueles que existem na sessão atual, são exportados para o módulo chamado Server01 no computador local.</span><span class="sxs-lookup"><span data-stu-id="16f2b-122">All of the commands, except those that exist in the current session, are exported to the module named Server01 on the local computer.</span></span> <span data-ttu-id="16f2b-123">A exportação inclui os dados de formatação para os comandos.</span><span class="sxs-lookup"><span data-stu-id="16f2b-123">The export includes the formatting data for the commands.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Export-PSSession -Session $S -OutputModule Server01
```

<span data-ttu-id="16f2b-124">O `New-PSSession` comando cria uma PSSession no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="16f2b-124">The `New-PSSession` command creates a PSSession on the Server01 computer.</span></span> <span data-ttu-id="16f2b-125">A PSSession é armazenada na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="16f2b-125">The PSSession is stored in the `$S` variable.</span></span> <span data-ttu-id="16f2b-126">O `Export-PSSession` comando exporta os `$S` comandos da variável e os dados de formatação para o módulo Server01.</span><span class="sxs-lookup"><span data-stu-id="16f2b-126">The `Export-PSSession` command exports the `$S` variable's commands and formatting data into the Server01 module.</span></span>

### <span data-ttu-id="16f2b-127">Exemplo 2: exportar os comandos Get e Set</span><span class="sxs-lookup"><span data-stu-id="16f2b-127">Example 2: Export the Get and Set commands</span></span>

<span data-ttu-id="16f2b-128">Este exemplo exporta todos os `Get` comandos e `Set` de um servidor.</span><span class="sxs-lookup"><span data-stu-id="16f2b-128">This example exports all of the `Get` and `Set` commands from a server.</span></span>

```powershell
$S = New-PSSession -ConnectionUri https://exchange.microsoft.com/mailbox -Credential exchangeadmin01@hotmail.com -Authentication Negotiate
Export-PSSession -Session $S -Module exch* -CommandName Get-*, Set-* -FormatTypeName * -OutputModule $PSHOME\Modules\Exchange -Encoding ASCII
```

<span data-ttu-id="16f2b-129">Esses comandos exportam os `Get` `Set` comandos e de um snap-in do Microsoft Exchange Server em um computador remoto para um módulo do Exchange no `$PSHOME\Modules` diretório no computador local.</span><span class="sxs-lookup"><span data-stu-id="16f2b-129">These commands export the `Get` and `Set` commands from a Microsoft Exchange Server snap-in on a remote computer to an Exchange module in the `$PSHOME\Modules` directory on the local computer.</span></span>
<span data-ttu-id="16f2b-130">Colocar o módulo no `$PSHOME\Modules` diretório o torna acessível a todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="16f2b-130">Placing the module in the `$PSHOME\Modules` directory makes it accessible to all users of the computer.</span></span>

### <span data-ttu-id="16f2b-131">Exemplo 3: exportar comandos de um computador remoto</span><span class="sxs-lookup"><span data-stu-id="16f2b-131">Example 3: Export commands from a remote computer</span></span>

<span data-ttu-id="16f2b-132">Este exemplo exporta os cmdlets de uma PSSession em um computador remoto e os salva em um módulo no computador local.</span><span class="sxs-lookup"><span data-stu-id="16f2b-132">This example exports cmdlets from a PSSession on a remote computer and saves them in a module on the local computer.</span></span> <span data-ttu-id="16f2b-133">Os cmdlets do módulo são adicionados à sessão atual para que possam ser usados.</span><span class="sxs-lookup"><span data-stu-id="16f2b-133">The cmdlets from the module are added to the current session so that they can be used.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01 -Credential Server01\User01
Export-PSSession -Session $S -OutputModule TestCmdlets -Type Cmdlet -CommandName *test* -FormatTypeName *
Remove-PSSession $S
Import-Module TestCmdlets
Get-Help Test*
Test-Files
```

<span data-ttu-id="16f2b-134">O `New-PSSession` comando cria uma PSSession no computador Server01 e salva-a na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="16f2b-134">The `New-PSSession` command creates a PSSession on the Server01 computer and saves it in the `$S` variable.</span></span> <span data-ttu-id="16f2b-135">O `Export-PSSession` comando exporta os cmdlets cujos nomes começam com teste de PSSession em `$S` para o módulo TestCmdlets no computador local.</span><span class="sxs-lookup"><span data-stu-id="16f2b-135">The `Export-PSSession` command exports the cmdlets whose names begin with Test from the PSSession in `$S` to the TestCmdlets module on the local computer.</span></span>

<span data-ttu-id="16f2b-136">O `Remove-PSSession` cmdlet exclui a PSSession in `$S` da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-136">The `Remove-PSSession` cmdlet deletes the PSSession in `$S` from the current session.</span></span> <span data-ttu-id="16f2b-137">Esse comando mostra que a PSSession não precisa estar ativa para usar os comandos que foram importados da sessão.</span><span class="sxs-lookup"><span data-stu-id="16f2b-137">This command shows that the PSSession need not be active to use the commands that were imported from the session.</span></span> <span data-ttu-id="16f2b-138">O `Import-Module` cmdlet adiciona os cmdlets no módulo TestCmdlets à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-138">The `Import-Module` cmdlet adds the cmdlets in the TestCmdlets module to the current session.</span></span> <span data-ttu-id="16f2b-139">O comando pode ser executado em qualquer sessão a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="16f2b-139">The command can be run in any session at any time.</span></span>

<span data-ttu-id="16f2b-140">O `Get-Help` cmdlet obtém ajuda para os cmdlets cujos nomes começam com Test.</span><span class="sxs-lookup"><span data-stu-id="16f2b-140">The `Get-Help` cmdlet gets help for cmdlets whose names begin with Test.</span></span> <span data-ttu-id="16f2b-141">Depois que os comandos em um módulo são adicionados à sessão atual, você pode usar os `Get-Help` `Get-Command` cmdlets e para saber mais sobre os comandos importados.</span><span class="sxs-lookup"><span data-stu-id="16f2b-141">After the commands in a module are added to the current session, you can use the `Get-Help` and `Get-Command` cmdlets to learn about the imported commands.</span></span> <span data-ttu-id="16f2b-142">O `Test-Files` cmdlet foi exportado do computador Server01 e adicionado à sessão.</span><span class="sxs-lookup"><span data-stu-id="16f2b-142">The `Test-Files` cmdlet was exported from the Server01 computer and added to the session.</span></span> <span data-ttu-id="16f2b-143">O `Test-Files` cmdlet é executado em uma sessão remota no computador do qual o comando foi importado.</span><span class="sxs-lookup"><span data-stu-id="16f2b-143">The `Test-Files` cmdlet runs in a remote session on the computer from which the command was imported.</span></span> <span data-ttu-id="16f2b-144">O PowerShell cria uma sessão de informações armazenadas no módulo TestCmdlets.</span><span class="sxs-lookup"><span data-stu-id="16f2b-144">PowerShell creates a session from information that is stored in the TestCmdlets module.</span></span>

### <span data-ttu-id="16f2b-145">Exemplo 4: exportar e sobrescrição comandos na sessão atual</span><span class="sxs-lookup"><span data-stu-id="16f2b-145">Example 4: Export and clobber commands in the current session</span></span>

<span data-ttu-id="16f2b-146">Este exemplo exporta comandos que são armazenados em uma variável na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-146">This example exports commands that are stored in a variable into the current session.</span></span>

```powershell
Export-PSSession -Session $S -AllowClobber -OutputModule AllCommands
```

<span data-ttu-id="16f2b-147">Esse `Export-PSSession` comando exporta todos os comandos e todos os dados de formatação da PSSession na `$S` variável para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-147">This `Export-PSSession` command exports all commands and all formatting data from the PSSession in the `$S` variable into the current session.</span></span> <span data-ttu-id="16f2b-148">O parâmetro **AllowClobber** inclui comandos com os mesmos nomes dos comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-148">The **AllowClobber** parameter includes commands with the same names as commands in the current session.</span></span>

### <span data-ttu-id="16f2b-149">Exemplo 5: exportar comandos de uma PSSession fechada</span><span class="sxs-lookup"><span data-stu-id="16f2b-149">Example 5: Export commands from a closed PSSession</span></span>

<span data-ttu-id="16f2b-150">Este exemplo mostra como executar os comandos exportados com opções especiais quando a PSSession que criou os comandos exportados é fechada.</span><span class="sxs-lookup"><span data-stu-id="16f2b-150">This example shows how to run the exported commands with special options when the PSSession that created the exported commands is closed.</span></span>

<span data-ttu-id="16f2b-151">Se a sessão remota original for fechada quando um módulo for importado, o módulo usará qualquer sessão remota aberta que se conectar ao computador de origem.</span><span class="sxs-lookup"><span data-stu-id="16f2b-151">If the original remote session is closed when a module is imported, the module will use any open remote session that connects to the originating computer.</span></span> <span data-ttu-id="16f2b-152">Se não houver nenhuma sessão atual para o computador de origem, o módulo restabelecerá uma sessão.</span><span class="sxs-lookup"><span data-stu-id="16f2b-152">If there is no current session to the originating computer, the module will reestablish a session.</span></span>

<span data-ttu-id="16f2b-153">Para executar comandos exportados com opções especiais em uma sessão remota, você deve criar uma sessão remota com essas opções antes de importar o módulo.</span><span class="sxs-lookup"><span data-stu-id="16f2b-153">To run exported commands with special options in a remote session, you must create a remote session with those options before you import the module.</span></span> <span data-ttu-id="16f2b-154">Use o `New-PSSession` cmdlet com o parâmetro **SessionOption**</span><span class="sxs-lookup"><span data-stu-id="16f2b-154">Use the `New-PSSession` cmdlet with the **SessionOption** parameter</span></span>

```powershell
$Options = New-PSSessionOption -NoMachineProfile
$S = New-PSSession -ComputerName Server01 -SessionOption $Options
Export-PSSession -Session $S -OutputModule Server01
Remove-PSSession $S
New-PSSession -ComputerName Server01 -SessionOption $Options
Import-Module Server01
```

<span data-ttu-id="16f2b-155">O `New-PSSessionOption` cmdlet cria um objeto **PSSessionOption** e salva o objeto na `$Options` variável.</span><span class="sxs-lookup"><span data-stu-id="16f2b-155">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object, and it saves the object in the `$Options` variable.</span></span> <span data-ttu-id="16f2b-156">O `New-PSSession` comando cria uma PSSession no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="16f2b-156">The `New-PSSession` command creates a PSSession on the Server01 computer.</span></span>
<span data-ttu-id="16f2b-157">O parâmetro **SessionOption** usa o objeto armazenado em `$Options` .</span><span class="sxs-lookup"><span data-stu-id="16f2b-157">The **SessionOption** parameter uses the object stored in `$Options`.</span></span> <span data-ttu-id="16f2b-158">A sessão é armazenada na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="16f2b-158">The session is stored in the `$S` variable.</span></span>

<span data-ttu-id="16f2b-159">O `Export-PSSession` cmdlet exporta os comandos de PSSession `$S` para o módulo Server01.</span><span class="sxs-lookup"><span data-stu-id="16f2b-159">The `Export-PSSession` cmdlet exports commands from the PSSession in `$S` to the Server01 module.</span></span>
<span data-ttu-id="16f2b-160">O `Remove-PSSession` cmdlet exclui a PSSession na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="16f2b-160">The `Remove-PSSession` cmdlet deletes the PSSession in the `$S` variable.</span></span>

<span data-ttu-id="16f2b-161">O `New-PSSession` cmdlet cria uma nova PSSession que se conecta ao computador Server01.</span><span class="sxs-lookup"><span data-stu-id="16f2b-161">The `New-PSSession` cmdlet creates a new PSSession that connects to the Server01 computer.</span></span> <span data-ttu-id="16f2b-162">O parâmetro **SessionOption** usa o objeto armazenado em `$Options` .</span><span class="sxs-lookup"><span data-stu-id="16f2b-162">The **SessionOption** parameter uses the object stored in `$Options`.</span></span> <span data-ttu-id="16f2b-163">O `Import-Module` cmdlet importa os comandos do módulo Server01.</span><span class="sxs-lookup"><span data-stu-id="16f2b-163">The `Import-Module` cmdlet imports the commands from the Server01 module.</span></span> <span data-ttu-id="16f2b-164">Os comandos no módulo são executados na PSSession no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="16f2b-164">The commands in the module are run in the PSSession on the Server01 computer.</span></span>

## <span data-ttu-id="16f2b-165">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="16f2b-165">Parameters</span></span>

### <span data-ttu-id="16f2b-166">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="16f2b-166">-AllowClobber</span></span>

<span data-ttu-id="16f2b-167">Exporta os comandos especificados, mesmo se tiverem os mesmos nomes de comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-167">Exports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="16f2b-168">Se você exportar um comando com o mesmo nome de um comando na sessão atual, o comando exportado ocultará ou substituirá os comandos originais.</span><span class="sxs-lookup"><span data-stu-id="16f2b-168">If you export a command with the same name as a command in the current session, the exported command hides or replaces the original commands.</span></span> <span data-ttu-id="16f2b-169">Para obter mais informações, confira [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="16f2b-169">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="16f2b-170">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="16f2b-170">-ArgumentList</span></span>

<span data-ttu-id="16f2b-171">Exporta a variante do comando resultante ao usar os argumentos especificados (valores de parâmetro).</span><span class="sxs-lookup"><span data-stu-id="16f2b-171">Exports the variant of the command that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="16f2b-172">Por exemplo, para exportar a variante do `Get-Item` comando no certificado (CERT:) na PSSession em `$S` , digite `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .</span><span class="sxs-lookup"><span data-stu-id="16f2b-172">For example, to export the variant of the `Get-Item` command in the certificate (Cert:) drive in the PSSession in `$S`, type `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="16f2b-173">-Certificado</span><span class="sxs-lookup"><span data-stu-id="16f2b-173">-Certificate</span></span>

<span data-ttu-id="16f2b-174">Especifica o certificado do cliente que é usado para assinar os arquivos de formato (\* .Format.ps1XML) ou arquivos de módulo de script (. psm1) no módulo que o `Export-PSSession` cria.</span><span class="sxs-lookup"><span data-stu-id="16f2b-174">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the module that `Export-PSSession` creates.</span></span> <span data-ttu-id="16f2b-175">Insira uma variável que contém um certificado, comando ou expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="16f2b-175">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="16f2b-176">Para localizar um certificado, use o `Get-PfxCertificate` cmdlet ou use o `Get-ChildItem` cmdlet no certificado (CERT:) Dirigir.</span><span class="sxs-lookup"><span data-stu-id="16f2b-176">To find a certificate, use the `Get-PfxCertificate` cmdlet or use the `Get-ChildItem` cmdlet in the Certificate (Cert:) drive.</span></span> <span data-ttu-id="16f2b-177">Se o certificado não for válido ou não tiver autoridade suficiente, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="16f2b-177">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="16f2b-178">-CommandName</span><span class="sxs-lookup"><span data-stu-id="16f2b-178">-CommandName</span></span>

<span data-ttu-id="16f2b-179">Exporta somente os comandos com os nomes especificados ou padrões de nome.</span><span class="sxs-lookup"><span data-stu-id="16f2b-179">Exports only the commands with the specified names or name patterns.</span></span> <span data-ttu-id="16f2b-180">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="16f2b-180">Wildcards are permitted.</span></span> <span data-ttu-id="16f2b-181">Use **CommandName** ou seu alias, **Name**.</span><span class="sxs-lookup"><span data-stu-id="16f2b-181">Use **CommandName** or its alias, **Name**.</span></span>

<span data-ttu-id="16f2b-182">Por padrão, `Export-PSSession` o exporta todos os comandos da PSSession, exceto os comandos que têm os mesmos nomes que os comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-182">By default, `Export-PSSession` exports all commands from the PSSession except for commands that have the same names as commands in the current session.</span></span> <span data-ttu-id="16f2b-183">Isso impede que os comandos sejam ocultados ou substituídos por comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-183">This prevents commands from being hidden or replaced by commands in the current session.</span></span> <span data-ttu-id="16f2b-184">Para exportar todos os comandos, mesmo aqueles que ocultam ou substituem outros comandos, use o parâmetro **AllowClobber** .</span><span class="sxs-lookup"><span data-stu-id="16f2b-184">To export all commands, even those that hide or replace other commands, use the **AllowClobber** parameter.</span></span>

<span data-ttu-id="16f2b-185">Se você usar o parâmetro **CommandName** , os arquivos de formatação para os comandos não serão exportados, a menos que você use o parâmetro **FormatTypeName** .</span><span class="sxs-lookup"><span data-stu-id="16f2b-185">If you use the **CommandName** parameter, the formatting files for the commands are not exported unless you use the **FormatTypeName** parameter.</span></span> <span data-ttu-id="16f2b-186">Da mesma forma, se você usar o parâmetro **FormatTypeName** , nenhum comando será exportado a menos que você use o parâmetro **CommandName** .</span><span class="sxs-lookup"><span data-stu-id="16f2b-186">Similarly, if you use the **FormatTypeName** parameter, no commands are exported unless you use the **CommandName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="16f2b-187">-CommandType</span><span class="sxs-lookup"><span data-stu-id="16f2b-187">-CommandType</span></span>

<span data-ttu-id="16f2b-188">Exporta somente os tipos especificados de objetos de comando.</span><span class="sxs-lookup"><span data-stu-id="16f2b-188">Exports only the specified types of command objects.</span></span> <span data-ttu-id="16f2b-189">Use o **CommandType** ou seu alias, **Type**.</span><span class="sxs-lookup"><span data-stu-id="16f2b-189">Use **CommandType** or its alias, **Type**.</span></span>

<span data-ttu-id="16f2b-190">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="16f2b-190">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="16f2b-191">`Alias`: Todos os aliases do PowerShell na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-191">`Alias`: All PowerShell aliases in the current session.</span></span>
- <span data-ttu-id="16f2b-192">`All`: Todos os tipos de comando.</span><span class="sxs-lookup"><span data-stu-id="16f2b-192">`All`: All command types.</span></span> <span data-ttu-id="16f2b-193">É o equivalente de `Get-Command -Name *` .</span><span class="sxs-lookup"><span data-stu-id="16f2b-193">It is the equivalent of `Get-Command -Name *`.</span></span>
- <span data-ttu-id="16f2b-194">`Application`: Todos os arquivos que não sejam arquivos do PowerShell em caminhos listados na variável de ambiente Path ( `$env:path` ), incluindo arquivos. txt,. exe e. dll.</span><span class="sxs-lookup"><span data-stu-id="16f2b-194">`Application`: All files other than PowerShell files in paths listed in the Path environment variable (`$env:path`), including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="16f2b-195">`Cmdlet`: Os cmdlets na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-195">`Cmdlet`: The cmdlets in the current session.</span></span> <span data-ttu-id="16f2b-196">É o padrão.</span><span class="sxs-lookup"><span data-stu-id="16f2b-196">Cmdlet is the default.</span></span>
- <span data-ttu-id="16f2b-197">`Configuration`: Uma configuração do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16f2b-197">`Configuration`: A PowerShell configuration.</span></span> <span data-ttu-id="16f2b-198">Para obter mais informações, consulte [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="16f2b-198">For more information, see [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span></span>
- <span data-ttu-id="16f2b-199">`ExternalScript`: Todos os arquivos. ps1 nos caminhos listados na variável de ambiente Path ( `$env:path` ).</span><span class="sxs-lookup"><span data-stu-id="16f2b-199">`ExternalScript`: All .ps1 files in the paths listed in the Path environment variable (`$env:path`).</span></span>
- <span data-ttu-id="16f2b-200">`Filter` e `Function` : todas as funções do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16f2b-200">`Filter` and `Function`: All PowerShell functions.</span></span>
- <span data-ttu-id="16f2b-201">`Script` Blocos de script na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="16f2b-201">`Script` Script blocks in the current session.</span></span>
- <span data-ttu-id="16f2b-202">`Workflow` Um fluxo de trabalho do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16f2b-202">`Workflow` A PowerShell workflow.</span></span> <span data-ttu-id="16f2b-203">Para obter mais informações, consulte [about_Workflows](/powershell/module/PSWorkflow/About/about_Workflows).</span><span class="sxs-lookup"><span data-stu-id="16f2b-203">For more information, see [about_Workflows](/powershell/module/PSWorkflow/About/about_Workflows).</span></span>

<span data-ttu-id="16f2b-204">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="16f2b-204">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="16f2b-205">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="16f2b-205">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="16f2b-206">Os valores podem ser passados para o parâmetro **CommandType** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="16f2b-206">The values can be passed to the **CommandType** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="16f2b-207">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="16f2b-207">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="16f2b-208">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="16f2b-208">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, All, Application, Cmdlet, Configuration, ExternalScript, Filter, Function, Script, Workflow

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="16f2b-209">-Codificação</span><span class="sxs-lookup"><span data-stu-id="16f2b-209">-Encoding</span></span>

<span data-ttu-id="16f2b-210">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="16f2b-210">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="16f2b-211">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="16f2b-211">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="16f2b-212">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="16f2b-212">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="16f2b-213">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="16f2b-213">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="16f2b-214">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="16f2b-214">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="16f2b-215">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="16f2b-215">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="16f2b-216">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="16f2b-216">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="16f2b-217">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="16f2b-217">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="16f2b-218">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="16f2b-218">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="16f2b-219">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="16f2b-219">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="16f2b-220">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="16f2b-220">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="16f2b-221">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="16f2b-221">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="16f2b-222">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="16f2b-222">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="16f2b-223">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="16f2b-223">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="16f2b-224">-Force</span><span class="sxs-lookup"><span data-stu-id="16f2b-224">-Force</span></span>

<span data-ttu-id="16f2b-225">Substitui um ou mais arquivos de saída existentes, mesmo se o arquivo tem o atributo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="16f2b-225">Overwrites one or more existing output files, even if the file has the read-only attribute.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="16f2b-226">-FormatTypeName</span><span class="sxs-lookup"><span data-stu-id="16f2b-226">-FormatTypeName</span></span>

<span data-ttu-id="16f2b-227">Exporta instruções de formatação para os tipos especificados do Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="16f2b-227">Exports formatting instructions only for the specified Microsoft .NET Framework types.</span></span> <span data-ttu-id="16f2b-228">Insira os nomes de tipo.</span><span class="sxs-lookup"><span data-stu-id="16f2b-228">Enter the type names.</span></span> <span data-ttu-id="16f2b-229">Por padrão, o `Export-PSSession` exporta as instruções de formatação para todos os tipos de .NET Framework que não estão no namespace **System. Management. Automation** .</span><span class="sxs-lookup"><span data-stu-id="16f2b-229">By default, `Export-PSSession` exports formatting instructions for all .NET Framework types that are not in the **System.Management.Automation** namespace.</span></span>

<span data-ttu-id="16f2b-230">O valor desse parâmetro deve ser o nome de um tipo que é retornado por um `Get-FormatData` comando na sessão da qual os comandos estão sendo importados.</span><span class="sxs-lookup"><span data-stu-id="16f2b-230">The value of this parameter must be the name of a type that is returned by a `Get-FormatData` command in the session from which the commands are being imported.</span></span> <span data-ttu-id="16f2b-231">Para obter todos os dados de formatação na sessão remota, digite `*` .</span><span class="sxs-lookup"><span data-stu-id="16f2b-231">To get all of the formatting data in the remote session, type `*`.</span></span>

<span data-ttu-id="16f2b-232">Se você usar o parâmetro **FormatTypeName** , nenhum comando será exportado a menos que você use o parâmetro **CommandName** .</span><span class="sxs-lookup"><span data-stu-id="16f2b-232">If you use the **FormatTypeName** parameter, no commands are exported unless you use the **CommandName** parameter.</span></span>

<span data-ttu-id="16f2b-233">Se você usar o parâmetro **CommandName** , os arquivos de formatação para os comandos não serão exportados, a menos que você use o parâmetro **FormatTypeName** .</span><span class="sxs-lookup"><span data-stu-id="16f2b-233">If you use the **CommandName** parameter, the formatting files for the commands are not exported unless you use the **FormatTypeName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="16f2b-234">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="16f2b-234">-FullyQualifiedModule</span></span>

<span data-ttu-id="16f2b-235">Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** .</span><span class="sxs-lookup"><span data-stu-id="16f2b-235">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span> <span data-ttu-id="16f2b-236">Consulte a seção comentários do [Construtor ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="16f2b-236">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="16f2b-237">Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado em um destes formatos:</span><span class="sxs-lookup"><span data-stu-id="16f2b-237">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="16f2b-238">**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.</span><span class="sxs-lookup"><span data-stu-id="16f2b-238">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="16f2b-239">Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** .</span><span class="sxs-lookup"><span data-stu-id="16f2b-239">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="16f2b-240">os dois parâmetros são mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="16f2b-240">the two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="16f2b-241">-Módulo</span><span class="sxs-lookup"><span data-stu-id="16f2b-241">-Module</span></span>

<span data-ttu-id="16f2b-242">Exporta somente os comandos nos módulos e snap-ins especificados do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16f2b-242">Exports only the commands in the specified PowerShell snap-ins and modules.</span></span> <span data-ttu-id="16f2b-243">Digite os nomes de módulos e snap-ins.</span><span class="sxs-lookup"><span data-stu-id="16f2b-243">Enter the snap-in and module names.</span></span> <span data-ttu-id="16f2b-244">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="16f2b-244">Wildcards are not permitted.</span></span>

<span data-ttu-id="16f2b-245">Para obter mais informações, consulte `Import-Module` e [about_Pssnapins](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1).</span><span class="sxs-lookup"><span data-stu-id="16f2b-245">For more information, see `Import-Module` and [about_PSSnapins](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="16f2b-246">-OutputModule</span><span class="sxs-lookup"><span data-stu-id="16f2b-246">-OutputModule</span></span>

<span data-ttu-id="16f2b-247">Especifica um caminho opcional e um nome para o módulo criado pelo `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="16f2b-247">Specifies an optional path and name for the module created by `Export-PSSession`.</span></span> <span data-ttu-id="16f2b-248">O caminho padrão é `$home\Documents\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="16f2b-248">The default path is `$home\Documents\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="16f2b-249">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="16f2b-249">This parameter is required.</span></span>

<span data-ttu-id="16f2b-250">Se o subdiretório do módulo ou qualquer um dos arquivos que o `Export-PSSession` cria já existir, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="16f2b-250">If the module subdirectory or any of the files that `Export-PSSession` creates already exist, the command fails.</span></span> <span data-ttu-id="16f2b-251">Para substituir os arquivos existentes, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="16f2b-251">To overwrite existing files, use the **Force** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, ModuleName

Required: True
Position: 1
Default value: $home\Documents\WindowsPowerShell\Modules
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="16f2b-252">-Sessão</span><span class="sxs-lookup"><span data-stu-id="16f2b-252">-Session</span></span>

<span data-ttu-id="16f2b-253">Especifica a PSSession da qual os comandos são exportados.</span><span class="sxs-lookup"><span data-stu-id="16f2b-253">Specifies the PSSession from which the commands are exported.</span></span> <span data-ttu-id="16f2b-254">Insira uma variável que contém um objeto de sessão ou um comando que obtém um objeto de sessão, como um `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="16f2b-254">Enter a variable that contains a session object or a command that gets a session object, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="16f2b-255">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="16f2b-255">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="16f2b-256">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="16f2b-256">CommonParameters</span></span>

<span data-ttu-id="16f2b-257">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="16f2b-257">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="16f2b-258">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="16f2b-258">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="16f2b-259">Entradas</span><span class="sxs-lookup"><span data-stu-id="16f2b-259">Inputs</span></span>

### <span data-ttu-id="16f2b-260">Nenhum</span><span class="sxs-lookup"><span data-stu-id="16f2b-260">None</span></span>

<span data-ttu-id="16f2b-261">Não é possível canalizar objetos para `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="16f2b-261">You cannot pipe objects to `Export-PSSession`.</span></span>

## <span data-ttu-id="16f2b-262">Saídas</span><span class="sxs-lookup"><span data-stu-id="16f2b-262">Outputs</span></span>

### <span data-ttu-id="16f2b-263">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="16f2b-263">System.IO.FileInfo</span></span>

<span data-ttu-id="16f2b-264">`Export-PSSession` Retorna uma lista de arquivos que compõem o módulo que ele criou.</span><span class="sxs-lookup"><span data-stu-id="16f2b-264">`Export-PSSession` returns a list of files that comprise the module that it created.</span></span>

## <span data-ttu-id="16f2b-265">Observações</span><span class="sxs-lookup"><span data-stu-id="16f2b-265">Notes</span></span>

<span data-ttu-id="16f2b-266">`Export-PSSession` depende da infraestrutura de comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16f2b-266">`Export-PSSession` relies on the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="16f2b-267">Para usar esse cmdlet, o computador deve ser configurado para comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="16f2b-267">To use this cmdlet, the computer must be configured for remoting.</span></span> <span data-ttu-id="16f2b-268">Para obter mais informações, consulte [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16f2b-268">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="16f2b-269">Você não pode usar `Export-PSSession` o para exportar um provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16f2b-269">You cannot use `Export-PSSession` to export a PowerShell provider.</span></span>

<span data-ttu-id="16f2b-270">Os comandos exportados são executados implicitamente na PSSession da qual foram exportados.</span><span class="sxs-lookup"><span data-stu-id="16f2b-270">Exported commands run implicitly in the PSSession from which they were exported.</span></span> <span data-ttu-id="16f2b-271">Os detalhes da execução de comandos remotamente são tratados inteiramente pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16f2b-271">The details of running the commands remotely are handled entirely by PowerShell.</span></span> <span data-ttu-id="16f2b-272">Você pode executar os comandos exportados exatamente como você executaria comandos locais.</span><span class="sxs-lookup"><span data-stu-id="16f2b-272">You can run the exported commands just as you would run local commands.</span></span>

<span data-ttu-id="16f2b-273">`Export-ModuleMember` captura e salva informações sobre a PSSession no módulo que ela exporta.</span><span class="sxs-lookup"><span data-stu-id="16f2b-273">`Export-ModuleMember` captures and saves information about the PSSession in the module that it exports.</span></span> <span data-ttu-id="16f2b-274">Se a PSSession da qual os comandos foram exportados for fechada quando você importar o módulo e não houver nenhuma PSSession ativa para o mesmo computador, os comandos no módulo tentarão recriar a PSSession.</span><span class="sxs-lookup"><span data-stu-id="16f2b-274">If the PSSession from which the commands were exported is closed when you import the module, and there are no active PSSessions to the same computer, the commands in the module attempt to recreate the PSSession.</span></span> <span data-ttu-id="16f2b-275">Se as tentativas de recriar a PSSession falharem, os comandos exportados não serão executados.</span><span class="sxs-lookup"><span data-stu-id="16f2b-275">If attempts to recreate the PSSession fail, the exported commands will not run.</span></span>

<span data-ttu-id="16f2b-276">As informações de sessão que o `Export-ModuleMember` captura e salva no módulo não incluem opções de sessão, como aquelas que você especificar na variável de `$PSSessionOption` preferência ou usando o parâmetro **SessionOption** dos `New-PSSession` `Enter-PSSession` cmdlets,, ou `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="16f2b-276">The session information that `Export-ModuleMember` captures and saves in the module does not include session options, such as those that you specify in the `$PSSessionOption` preference variable or by using the **SessionOption** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span> <span data-ttu-id="16f2b-277">Se a PSSession original for fechada quando você importar o módulo, o módulo usará outra PSSession no mesmo computador, se disponível.</span><span class="sxs-lookup"><span data-stu-id="16f2b-277">If the original PSSession is closed when you import the module, the module will use another PSSession to the same computer, if one is available.</span></span> <span data-ttu-id="16f2b-278">Para habilitar os comandos importados para serem executados em uma sessão configurada corretamente, crie uma PSSession com as opções que você deseja antes de importar o módulo.</span><span class="sxs-lookup"><span data-stu-id="16f2b-278">To enable the imported commands to run in a correctly configured session, create a PSSession with the options that you want before you import the module.</span></span>

<span data-ttu-id="16f2b-279">Para localizar os comandos a serem exportados, `Export-PSSession` o usa o `Invoke-Command` cmdlet para executar um `Get-Command` comando na PSSession.</span><span class="sxs-lookup"><span data-stu-id="16f2b-279">To find the commands to export, `Export-PSSession` uses the `Invoke-Command` cmdlet to run a `Get-Command` command in the PSSession.</span></span> <span data-ttu-id="16f2b-280">Para obter e salvar dados de formatação para os comandos, ele usa `Get-FormatData` os `Export-FormatData` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="16f2b-280">To get and save formatting data for the commands, it uses the `Get-FormatData` and `Export-FormatData` cmdlets.</span></span> <span data-ttu-id="16f2b-281">Você pode ver mensagens de erro de `Invoke-Command` , `Get-Command` , `Get-FormatData` e `Export-FormatData` quando você executa um `Export-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="16f2b-281">You might see error messages from `Invoke-Command`, `Get-Command`, `Get-FormatData`, and `Export-FormatData` when you run an `Export-PSSession` command.</span></span> <span data-ttu-id="16f2b-282">Além disso, `Export-PSSession` o não pode exportar comandos de uma sessão que não inclua os `Get-Command` `Get-FormatData` cmdlets,, `Select-Object` e `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="16f2b-282">Also, `Export-PSSession` cannot export commands from a session that does not include the `Get-Command`, `Get-FormatData`, `Select-Object`, and `Get-Help` cmdlets.</span></span>

<span data-ttu-id="16f2b-283">`Export-PSSession` usa o `Write-Progress` cmdlet para exibir o progresso do comando.</span><span class="sxs-lookup"><span data-stu-id="16f2b-283">`Export-PSSession` uses the `Write-Progress` cmdlet to display the progress of the command.</span></span> <span data-ttu-id="16f2b-284">Você pode ver a barra de progresso enquanto o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="16f2b-284">You might see the progress bar while the command is running.</span></span>

<span data-ttu-id="16f2b-285">Comandos exportados têm as mesmas limitações que outros comandos remotos, inclusive a incapacidade de iniciar um programa com uma interface de usuário, como o Bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="16f2b-285">Exported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>

<span data-ttu-id="16f2b-286">Como os perfis do PowerShell não são executados em PSSessions, os comandos que um perfil adiciona a uma sessão não estão disponíveis para o `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="16f2b-286">Because PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to `Export-PSSession`.</span></span> <span data-ttu-id="16f2b-287">Para exportar comandos de um perfil, use um `Invoke-Command` comando para executar o perfil na PSSession manualmente antes de exportar os comandos.</span><span class="sxs-lookup"><span data-stu-id="16f2b-287">To export commands from a profile, use an `Invoke-Command` command to run the profile in the PSSession manually before exporting commands.</span></span>

<span data-ttu-id="16f2b-288">O módulo que o `Export-PSSession` cria pode incluir um arquivo de formatação, mesmo que o comando não importe dados de formatação.</span><span class="sxs-lookup"><span data-stu-id="16f2b-288">The module that `Export-PSSession` creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="16f2b-289">Se o comando não importar dados de formatação, quaisquer arquivos de formatação criados não conterão dados de formatação.</span><span class="sxs-lookup"><span data-stu-id="16f2b-289">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>

## <span data-ttu-id="16f2b-290">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="16f2b-290">Related Links</span></span>

[<span data-ttu-id="16f2b-291">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="16f2b-291">about_Command_Precedence</span></span>](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)

[<span data-ttu-id="16f2b-292">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="16f2b-292">about_PSSessions</span></span>](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[<span data-ttu-id="16f2b-293">about_PSSnapins</span><span class="sxs-lookup"><span data-stu-id="16f2b-293">about_PSSnapins</span></span>](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1)

[<span data-ttu-id="16f2b-294">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="16f2b-294">about_Remote_Requirements</span></span>](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)

[<span data-ttu-id="16f2b-295">Import-Module</span><span class="sxs-lookup"><span data-stu-id="16f2b-295">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="16f2b-296">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="16f2b-296">Import-PSSession</span></span>](Import-PSSession.md)

[<span data-ttu-id="16f2b-297">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="16f2b-297">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="16f2b-298">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="16f2b-298">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="16f2b-299">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="16f2b-299">New-PSSessionOption</span></span>](../Microsoft.PowerShell.Core/New-PSSessionOption.md)

[<span data-ttu-id="16f2b-300">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="16f2b-300">Remove-PSSession</span></span>](../Microsoft.PowerShell.Core/Remove-PSSession.md)
