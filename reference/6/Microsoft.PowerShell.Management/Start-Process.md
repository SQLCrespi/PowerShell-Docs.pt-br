---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: a221c6126bbbf22dffb493828f759bcbd4cfe759
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2020
ms.locfileid: "93195099"
---
# <span data-ttu-id="97c14-103">Start-Process</span><span class="sxs-lookup"><span data-stu-id="97c14-103">Start-Process</span></span>

## <span data-ttu-id="97c14-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="97c14-104">SYNOPSIS</span></span>
<span data-ttu-id="97c14-105">Inicia um ou mais processos no computador local.</span><span class="sxs-lookup"><span data-stu-id="97c14-105">Starts one or more processes on the local computer.</span></span>

## <span data-ttu-id="97c14-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="97c14-106">SYNTAX</span></span>

### <span data-ttu-id="97c14-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="97c14-107">Default (Default)</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="97c14-108">UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="97c14-108">UseShellExecute</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="97c14-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="97c14-109">DESCRIPTION</span></span>

<span data-ttu-id="97c14-110">O `Start-Process` cmdlet inicia um ou mais processos no computador local.</span><span class="sxs-lookup"><span data-stu-id="97c14-110">The `Start-Process` cmdlet starts one or more processes on the local computer.</span></span> <span data-ttu-id="97c14-111">Por padrão, `Start-Process` o cria um novo processo que herda todas as variáveis de ambiente definidas no processo atual.</span><span class="sxs-lookup"><span data-stu-id="97c14-111">By default, `Start-Process` creates a new process that inherits all the environment variables that are defined in the current process.</span></span>

<span data-ttu-id="97c14-112">Para especificar o programa que é executado no processo, insira um arquivo executável ou arquivo de script, ou um arquivo que pode ser aberto usando um programa no computador.</span><span class="sxs-lookup"><span data-stu-id="97c14-112">To specify the program that runs in the process, enter an executable file or script file, or a file that can be opened by using a program on the computer.</span></span> <span data-ttu-id="97c14-113">Se você especificar um arquivo não executável, `Start-Process` o iniciará o programa associado ao arquivo, semelhante ao `Invoke-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97c14-113">If you specify a non-executable file, `Start-Process` starts the program that is associated with the file, similar to the `Invoke-Item` cmdlet.</span></span>

<span data-ttu-id="97c14-114">Você pode usar os parâmetros de `Start-Process` para especificar opções, como carregar um perfil de usuário, iniciar o processo em uma nova janela ou usar credenciais alternativas.</span><span class="sxs-lookup"><span data-stu-id="97c14-114">You can use the parameters of `Start-Process` to specify options, such as loading a user profile, starting the process in a new window, or using alternate credentials.</span></span>

## <span data-ttu-id="97c14-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="97c14-115">EXAMPLES</span></span>

### <span data-ttu-id="97c14-116">Exemplo 1: iniciar um processo que usa valores padrão</span><span class="sxs-lookup"><span data-stu-id="97c14-116">Example 1: Start a process that uses default values</span></span>

<span data-ttu-id="97c14-117">Este exemplo inicia um processo que usa o `Sort.exe` arquivo na pasta atual.</span><span class="sxs-lookup"><span data-stu-id="97c14-117">This example starts a process that uses the `Sort.exe` file in the current folder.</span></span> <span data-ttu-id="97c14-118">O comando usa todos os valores padrão, incluindo o estilo de janela padrão, a pasta de trabalho e as credenciais.</span><span class="sxs-lookup"><span data-stu-id="97c14-118">The command uses all of the default values, including the default window style, working folder, and credentials.</span></span>

```powershell
Start-Process -FilePath "sort.exe"
```

### <span data-ttu-id="97c14-119">Exemplo 2: imprimir um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="97c14-119">Example 2: Print a text file</span></span>

<span data-ttu-id="97c14-120">Este exemplo inicia um processo que imprime o `C:\PS-Test\MyFile.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="97c14-120">This example starts a process that prints the `C:\PS-Test\MyFile.txt` file.</span></span>

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### <span data-ttu-id="97c14-121">Exemplo 3: iniciar um processo para classificar itens em um novo arquivo</span><span class="sxs-lookup"><span data-stu-id="97c14-121">Example 3: Start a process to sort items to a new file</span></span>

<span data-ttu-id="97c14-122">Este exemplo inicia um processo que classifica itens no `Testsort.txt` arquivo e retorna os itens classificados nos `Sorted.txt` arquivos.</span><span class="sxs-lookup"><span data-stu-id="97c14-122">This example starts a process that sorts items in the `Testsort.txt` file and returns the sorted items in the `Sorted.txt` files.</span></span> <span data-ttu-id="97c14-123">Todos os erros são gravados no `SortError.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="97c14-123">Any errors are written to the `SortError.txt` file.</span></span>

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

<span data-ttu-id="97c14-124">O parâmetro **UseNewEnvironment** especifica que o processo é executado com suas próprias variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="97c14-124">The **UseNewEnvironment** parameter specifies that the process runs with its own environment variables.</span></span>

### <span data-ttu-id="97c14-125">Exemplo 4: iniciar um processo em uma janela maximizada</span><span class="sxs-lookup"><span data-stu-id="97c14-125">Example 4: Start a process in a maximized window</span></span>

<span data-ttu-id="97c14-126">Este exemplo inicia o `Notepad.exe` processo.</span><span class="sxs-lookup"><span data-stu-id="97c14-126">This example starts the `Notepad.exe` process.</span></span> <span data-ttu-id="97c14-127">Ele maximiza a janela e mantém a janela até que o processo seja concluído.</span><span class="sxs-lookup"><span data-stu-id="97c14-127">It maximizes the window and retains the window until the process completes.</span></span>

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### <span data-ttu-id="97c14-128">Exemplo 5: iniciar o PowerShell como administrador</span><span class="sxs-lookup"><span data-stu-id="97c14-128">Example 5: Start PowerShell as an administrator</span></span>

<span data-ttu-id="97c14-129">Este exemplo inicia o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="97c14-129">This example starts PowerShell by using the **Run as administrator** option.</span></span>

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### <span data-ttu-id="97c14-130">Exemplo 6: usando verbos diferentes para iniciar um processo</span><span class="sxs-lookup"><span data-stu-id="97c14-130">Example 6: Using different verbs to start a process</span></span>

<span data-ttu-id="97c14-131">Este exemplo mostra como localizar os verbos que podem ser usados ao iniciar um processo.</span><span class="sxs-lookup"><span data-stu-id="97c14-131">This example shows how to find the verbs that can be used when starting a process.</span></span> <span data-ttu-id="97c14-132">Os verbos disponíveis são determinados pela extensão de nome do arquivo que é executado no processo.</span><span class="sxs-lookup"><span data-stu-id="97c14-132">The available verbs are determined by the filename extension of the file that runs in the process.</span></span>

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

<span data-ttu-id="97c14-133">O exemplo usa `New-Object` para criar um objeto **System. Diagnostics. ProcessStartInfo** para **PowerShell.exe** , o arquivo que é executado no processo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97c14-133">The example uses `New-Object` to create a **System.Diagnostics.ProcessStartInfo** object for **PowerShell.exe** , the file that runs in the PowerShell process.</span></span> <span data-ttu-id="97c14-134">A propriedade **verbos** do objeto **ProcessStartInfo** mostra que você pode usar os verbos **Open** e **runas** com `PowerShell.exe` , ou com qualquer processo que execute um `.exe` arquivo.</span><span class="sxs-lookup"><span data-stu-id="97c14-134">The **Verbs** property of the **ProcessStartInfo** object shows that you can use the **Open** and **RunAs** verbs with `PowerShell.exe`, or with any process that runs a `.exe` file.</span></span>

### <span data-ttu-id="97c14-135">Exemplo 7: especificando argumentos para o processo</span><span class="sxs-lookup"><span data-stu-id="97c14-135">Example 7: Specifying arguments to the process</span></span>

<span data-ttu-id="97c14-136">Ambos os comandos iniciam o interpretador de comandos do Windows, emitindo um `dir` comando na `Program Files` pasta.</span><span class="sxs-lookup"><span data-stu-id="97c14-136">Both commands start the Windows command interpreter, issuing a `dir` command on the `Program Files` folder.</span></span> <span data-ttu-id="97c14-137">Como this FolderName contém um espaço, o valor precisa ser circundado com aspas de escape.</span><span class="sxs-lookup"><span data-stu-id="97c14-137">Because this foldername contains a space, the value needs surrounded with escaped quotes.</span></span>
<span data-ttu-id="97c14-138">Observe que o primeiro comando especifica uma cadeia de caracteres como **argumentolist** .</span><span class="sxs-lookup"><span data-stu-id="97c14-138">Note that the first command specifies a string as **ArgumentList** .</span></span> <span data-ttu-id="97c14-139">O segundo comando é uma matriz de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="97c14-139">The second command is a string array.</span></span>

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

## <span data-ttu-id="97c14-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="97c14-140">PARAMETERS</span></span>

### <span data-ttu-id="97c14-141">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="97c14-141">-ArgumentList</span></span>

<span data-ttu-id="97c14-142">Especifica os parâmetros ou valores de parâmetro a serem usados quando esse cmdlet iniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="97c14-142">Specifies parameters or parameter values to use when this cmdlet starts the process.</span></span> <span data-ttu-id="97c14-143">Os argumentos podem ser aceitos como uma única cadeia de caracteres com os argumentos separados por espaços ou como uma matriz de cadeias de caracteres separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="97c14-143">Arguments can be accepted as a single string with the arguments separated by spaces, or as an array of strings separated by commas.</span></span>

<span data-ttu-id="97c14-144">Se os parâmetros ou os valores de parâmetro contiverem um espaço, eles precisarão estar entre aspas duplas de escape.</span><span class="sxs-lookup"><span data-stu-id="97c14-144">If parameters or parameter values contain a space, they need to be surrounded with escaped double quotes.</span></span> <span data-ttu-id="97c14-145">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="97c14-145">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="97c14-146">-Credential</span></span>

<span data-ttu-id="97c14-147">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="97c14-147">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="97c14-148">Por padrão, o cmdlet usa as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="97c14-148">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="97c14-149">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97c14-149">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="97c14-150">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="97c14-150">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="97c14-151">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="97c14-151">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="97c14-152">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="97c14-152">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Default
Aliases: RunAs

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-153">-FilePath</span><span class="sxs-lookup"><span data-stu-id="97c14-153">-FilePath</span></span>

<span data-ttu-id="97c14-154">Especifica o caminho opcional e o nome do arquivo do programa que é executado no processo.</span><span class="sxs-lookup"><span data-stu-id="97c14-154">Specifies the optional path and filename of the program that runs in the process.</span></span> <span data-ttu-id="97c14-155">Insira o nome de um arquivo executável ou de um documento, como um `.txt` arquivo ou `.doc` , que está associado a um programa no computador.</span><span class="sxs-lookup"><span data-stu-id="97c14-155">Enter the name of an executable file or of a document, such as a `.txt` or `.doc` file, that is associated with a program on the computer.</span></span> <span data-ttu-id="97c14-156">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="97c14-156">This parameter is required.</span></span>

<span data-ttu-id="97c14-157">Se você especificar apenas um nome de arquivo, use o parâmetro **WorkingDirectory** para especificar o caminho.</span><span class="sxs-lookup"><span data-stu-id="97c14-157">If you specify only a filename, use the **WorkingDirectory** parameter to specify the path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-158">-LoadUserProfile</span><span class="sxs-lookup"><span data-stu-id="97c14-158">-LoadUserProfile</span></span>

<span data-ttu-id="97c14-159">Indica que esse cmdlet carrega o perfil de usuário do Windows armazenado na `HKEY_USERS` chave do registro para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="97c14-159">Indicates that this cmdlet loads the Windows user profile stored in the `HKEY_USERS` registry key for the current user.</span></span> <span data-ttu-id="97c14-160">O parâmetro não se aplica a sistemas não Windows.</span><span class="sxs-lookup"><span data-stu-id="97c14-160">The parameter does not apply for non-Windows systems.</span></span>

<span data-ttu-id="97c14-161">Esse parâmetro não afeta os perfis do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97c14-161">This parameter does not affect the PowerShell profiles.</span></span> <span data-ttu-id="97c14-162">Para obter mais informações, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="97c14-162">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: Lup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-163">-NoNewWindow</span><span class="sxs-lookup"><span data-stu-id="97c14-163">-NoNewWindow</span></span>

<span data-ttu-id="97c14-164">Inicie o novo processo na janela do console atual.</span><span class="sxs-lookup"><span data-stu-id="97c14-164">Start the new process in the current console window.</span></span> <span data-ttu-id="97c14-165">Por padrão no Windows, o PowerShell abre uma nova janela.</span><span class="sxs-lookup"><span data-stu-id="97c14-165">By default on Windows, PowerShell opens a new window.</span></span> <span data-ttu-id="97c14-166">Em sistemas não Windows, você nunca Obtém uma nova janela de terminal.</span><span class="sxs-lookup"><span data-stu-id="97c14-166">On non-Windows systems, you never get a new terminal window.</span></span>

<span data-ttu-id="97c14-167">Você não pode usar os parâmetros **NoNewWindow** e **WindowStyle** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="97c14-167">You cannot use the **NoNewWindow** and **WindowStyle** parameters in the same command.</span></span>

<span data-ttu-id="97c14-168">O parâmetro não se aplica a sistemas não Windows.</span><span class="sxs-lookup"><span data-stu-id="97c14-168">The parameter does not apply for non-Windows systems.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: nnw

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-169">-PassThru</span><span class="sxs-lookup"><span data-stu-id="97c14-169">-PassThru</span></span>

<span data-ttu-id="97c14-170">Retorna um objeto de processo para cada processo que o cmdlet iniciou.</span><span class="sxs-lookup"><span data-stu-id="97c14-170">Returns a process object for each process that the cmdlet started.</span></span> <span data-ttu-id="97c14-171">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="97c14-171">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="97c14-172">-RedirectStandardError</span><span class="sxs-lookup"><span data-stu-id="97c14-172">-RedirectStandardError</span></span>

<span data-ttu-id="97c14-173">Especifica um arquivo.</span><span class="sxs-lookup"><span data-stu-id="97c14-173">Specifies a file.</span></span> <span data-ttu-id="97c14-174">Esse cmdlet envia todos os erros gerados pelo processo para um arquivo que você especificar.</span><span class="sxs-lookup"><span data-stu-id="97c14-174">This cmdlet sends any errors generated by the process to a file that you specify.</span></span>
<span data-ttu-id="97c14-175">Insira o caminho e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="97c14-175">Enter the path and filename.</span></span> <span data-ttu-id="97c14-176">Por padrão, os erros são exibidos no console.</span><span class="sxs-lookup"><span data-stu-id="97c14-176">By default, the errors are displayed in the console.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-177">-RedirectStandardInput</span><span class="sxs-lookup"><span data-stu-id="97c14-177">-RedirectStandardInput</span></span>

<span data-ttu-id="97c14-178">Especifica um arquivo.</span><span class="sxs-lookup"><span data-stu-id="97c14-178">Specifies a file.</span></span> <span data-ttu-id="97c14-179">Esse cmdlet lê a entrada do arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="97c14-179">This cmdlet reads input from the specified file.</span></span> <span data-ttu-id="97c14-180">Insira o caminho e o nome do arquivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="97c14-180">Enter the path and filename of the input file.</span></span> <span data-ttu-id="97c14-181">Por padrão, o processo obtém sua entrada do teclado.</span><span class="sxs-lookup"><span data-stu-id="97c14-181">By default, the process gets its input from the keyboard.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-182">-RedirectStandardOutput</span><span class="sxs-lookup"><span data-stu-id="97c14-182">-RedirectStandardOutput</span></span>

<span data-ttu-id="97c14-183">Especifica um arquivo.</span><span class="sxs-lookup"><span data-stu-id="97c14-183">Specifies a file.</span></span> <span data-ttu-id="97c14-184">Esse cmdlet envia a saída gerada pelo processo para um arquivo que você especificar.</span><span class="sxs-lookup"><span data-stu-id="97c14-184">This cmdlet sends the output generated by the process to a file that you specify.</span></span>
<span data-ttu-id="97c14-185">Insira o caminho e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="97c14-185">Enter the path and filename.</span></span> <span data-ttu-id="97c14-186">Por padrão, a saída é exibida no console.</span><span class="sxs-lookup"><span data-stu-id="97c14-186">By default, the output is displayed in the console.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-187">-UseNewEnvironment</span><span class="sxs-lookup"><span data-stu-id="97c14-187">-UseNewEnvironment</span></span>

<span data-ttu-id="97c14-188">Indica que esse cmdlet usa novas variáveis de ambiente especificadas para o processo.</span><span class="sxs-lookup"><span data-stu-id="97c14-188">Indicates that this cmdlet uses new environment variables specified for the process.</span></span> <span data-ttu-id="97c14-189">Por padrão, o processo iniciado é executado com as variáveis de ambiente herdadas do processo pai.</span><span class="sxs-lookup"><span data-stu-id="97c14-189">By default, the started process runs with the environment variables inherited from the parent process.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-190">-Verbo</span><span class="sxs-lookup"><span data-stu-id="97c14-190">-Verb</span></span>

<span data-ttu-id="97c14-191">Especifica um verbo a ser usado quando esse cmdlet iniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="97c14-191">Specifies a verb to use when this cmdlet starts the process.</span></span> <span data-ttu-id="97c14-192">Os verbos disponíveis são determinados pela extensão de nome do arquivo que é executado no processo.</span><span class="sxs-lookup"><span data-stu-id="97c14-192">The verbs that are available are determined by the filename extension of the file that runs in the process.</span></span>

<span data-ttu-id="97c14-193">A tabela a seguir mostra os verbos para alguns tipos de arquivos comuns do processo.</span><span class="sxs-lookup"><span data-stu-id="97c14-193">The following table shows the verbs for some common process file types.</span></span>

| <span data-ttu-id="97c14-194">Tipo de arquivo</span><span class="sxs-lookup"><span data-stu-id="97c14-194">File type</span></span> |                <span data-ttu-id="97c14-195">Verbos</span><span class="sxs-lookup"><span data-stu-id="97c14-195">Verbs</span></span>                |
| --------- | ----------------------------------- |
| <span data-ttu-id="97c14-196">.cmd</span><span class="sxs-lookup"><span data-stu-id="97c14-196">.cmd</span></span>      | <span data-ttu-id="97c14-197">Editar, abrir, imprimir, executar como, RunAsUser</span><span class="sxs-lookup"><span data-stu-id="97c14-197">Edit, Open, Print, RunAs, RunAsUser</span></span> |
| <span data-ttu-id="97c14-198">.exe</span><span class="sxs-lookup"><span data-stu-id="97c14-198">.exe</span></span>      | <span data-ttu-id="97c14-199">Abrir, RunAs, RunAsUser</span><span class="sxs-lookup"><span data-stu-id="97c14-199">Open, RunAs, RunAsUser</span></span>              |
| <span data-ttu-id="97c14-200">.txt</span><span class="sxs-lookup"><span data-stu-id="97c14-200">.txt</span></span>      | <span data-ttu-id="97c14-201">Abrir, imprimir, imprimir em</span><span class="sxs-lookup"><span data-stu-id="97c14-201">Open, Print, PrintTo</span></span>                |
| <span data-ttu-id="97c14-202">.wav</span><span class="sxs-lookup"><span data-stu-id="97c14-202">.wav</span></span>      | <span data-ttu-id="97c14-203">Abrir, reproduzir</span><span class="sxs-lookup"><span data-stu-id="97c14-203">Open, Play</span></span>                          |

<span data-ttu-id="97c14-204">Para localizar os verbos que podem ser usados com o arquivo que é executado em um processo, use o `New-Object` cmdlet para criar um objeto **System. Diagnostics. ProcessStartInfo** para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="97c14-204">To find the verbs that can be used with the file that runs in a process, use the `New-Object` cmdlet to create a **System.Diagnostics.ProcessStartInfo** object for the file.</span></span> <span data-ttu-id="97c14-205">Os verbos disponíveis estão na propriedade **verbos** do objeto **ProcessStartInfo** .</span><span class="sxs-lookup"><span data-stu-id="97c14-205">The available verbs are in the **Verbs** property of the **ProcessStartInfo** object.</span></span> <span data-ttu-id="97c14-206">Para obter detalhes, consulte os exemplos.</span><span class="sxs-lookup"><span data-stu-id="97c14-206">For details, see the examples.</span></span>

<span data-ttu-id="97c14-207">O parâmetro não se aplica a sistemas não Windows.</span><span class="sxs-lookup"><span data-stu-id="97c14-207">The parameter does not apply for non-Windows systems.</span></span>

```yaml
Type: System.String
Parameter Sets: UseShellExecute
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-208">-Wait</span><span class="sxs-lookup"><span data-stu-id="97c14-208">-Wait</span></span>

<span data-ttu-id="97c14-209">Indica que esse cmdlet aguarda o processo especificado e seus descendentes serem concluídos antes de aceitar mais entrada.</span><span class="sxs-lookup"><span data-stu-id="97c14-209">Indicates that this cmdlet waits for the specified process and its descendants to complete before accepting more input.</span></span> <span data-ttu-id="97c14-210">Esse parâmetro suprime o prompt de comando ou retém a janela até que os processos sejam concluídos.</span><span class="sxs-lookup"><span data-stu-id="97c14-210">This parameter suppresses the command prompt or retains the window until the processes finish.</span></span>

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

### <span data-ttu-id="97c14-211">-WindowStyle</span><span class="sxs-lookup"><span data-stu-id="97c14-211">-WindowStyle</span></span>

<span data-ttu-id="97c14-212">Especifica o estado da janela que é usada para o novo processo.</span><span class="sxs-lookup"><span data-stu-id="97c14-212">Specifies the state of the window that is used for the new process.</span></span> <span data-ttu-id="97c14-213">Os valores aceitáveis para esse parâmetro são: **normal** , **oculto** , **minimizado** e **maximizado** .</span><span class="sxs-lookup"><span data-stu-id="97c14-213">The acceptable values for this parameter are: **Normal** , **Hidden** , **Minimized** , and **Maximized** .</span></span> <span data-ttu-id="97c14-214">O valor padrão é **normal** .</span><span class="sxs-lookup"><span data-stu-id="97c14-214">The default value is **Normal** .</span></span>

<span data-ttu-id="97c14-215">Você não pode usar os parâmetros **WindowStyle** e **NoNewWindow** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="97c14-215">You cannot use the **WindowStyle** and **NoNewWindow** parameters in the same command.</span></span>

<span data-ttu-id="97c14-216">O parâmetro não se aplica a sistemas não Windows.</span><span class="sxs-lookup"><span data-stu-id="97c14-216">The parameter does not apply for non-Windows systems.</span></span>

```yaml
Type: System.Diagnostics.ProcessWindowStyle
Parameter Sets: (All)
Aliases:
Accepted values: Normal, Hidden, Minimized, Maximized

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-217">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="97c14-217">-WorkingDirectory</span></span>

<span data-ttu-id="97c14-218">Especifica o local em que o novo processo deve ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="97c14-218">Specifies the location that the new process should start in.</span></span> <span data-ttu-id="97c14-219">O padrão é o local do arquivo executável ou do documento que está sendo iniciado.</span><span class="sxs-lookup"><span data-stu-id="97c14-219">The default is the location of the executable file or document being started.</span></span> <span data-ttu-id="97c14-220">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="97c14-220">Wildcards are not supported.</span></span> <span data-ttu-id="97c14-221">O nome do caminho não deve conter caracteres que seriam interpretados como curingas.</span><span class="sxs-lookup"><span data-stu-id="97c14-221">The path name must not contain characters that would be interpreted as wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-222">-Confirm</span><span class="sxs-lookup"><span data-stu-id="97c14-222">-Confirm</span></span>

<span data-ttu-id="97c14-223">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97c14-223">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-224">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="97c14-224">-WhatIf</span></span>

<span data-ttu-id="97c14-225">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="97c14-225">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="97c14-226">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="97c14-226">The cmdlet is not run.</span></span>

<span data-ttu-id="97c14-227">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="97c14-227">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97c14-228">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="97c14-228">CommonParameters</span></span>

<span data-ttu-id="97c14-229">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="97c14-229">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="97c14-230">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="97c14-230">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="97c14-231">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="97c14-231">INPUTS</span></span>

### <span data-ttu-id="97c14-232">Nenhum</span><span class="sxs-lookup"><span data-stu-id="97c14-232">None</span></span>

<span data-ttu-id="97c14-233">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97c14-233">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="97c14-234">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="97c14-234">OUTPUTS</span></span>

### <span data-ttu-id="97c14-235">Nenhum, System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="97c14-235">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="97c14-236">Esse cmdlet gera um objeto **System. Diagnostics. Process** , se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="97c14-236">This cmdlet generates a **System.Diagnostics.Process** object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="97c14-237">Caso contrário, este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="97c14-237">Otherwise, this cmdlet does not return any output.</span></span>

## <span data-ttu-id="97c14-238">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="97c14-238">NOTES</span></span>

- <span data-ttu-id="97c14-239">Esse cmdlet é implementado usando o método **Start** da classe **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="97c14-239">This cmdlet is implemented by using the **Start** method of the **System.Diagnostics.Process** class.</span></span> <span data-ttu-id="97c14-240">Para obter mais informações sobre esse método, consulte o [método Process. Start](/dotnet/api/system.diagnostics.process.start#overloads).</span><span class="sxs-lookup"><span data-stu-id="97c14-240">For more information about this method, see [Process.Start Method](/dotnet/api/system.diagnostics.process.start#overloads).</span></span>

- <span data-ttu-id="97c14-241">No Windows, quando você usa o **UseNewEnvironment** , o novo processo inicia apenas com as variáveis de ambiente padrão definidas para o escopo da **máquina** .</span><span class="sxs-lookup"><span data-stu-id="97c14-241">On Windows, when you use **UseNewEnvironment** , the new process starts only containing the default environment variables defined for the **Machine** scope.</span></span> <span data-ttu-id="97c14-242">Isso tem o lado de afetar que o `$env:USERNAME` está definido como **System** .</span><span class="sxs-lookup"><span data-stu-id="97c14-242">This has the side affect that the `$env:USERNAME` is set to **SYSTEM** .</span></span> <span data-ttu-id="97c14-243">Nenhuma das variáveis do escopo do **usuário** está incluída.</span><span class="sxs-lookup"><span data-stu-id="97c14-243">None of the variables from the **User** scope are included.</span></span>

- <span data-ttu-id="97c14-244">No Windows, o caso de uso mais comum para o `Start-Process` é usar o parâmetro **Wait** para bloquear o progresso até que o novo processo saia.</span><span class="sxs-lookup"><span data-stu-id="97c14-244">On Windows, the most common use case for `Start-Process` is to use the **Wait** parameter to block progress until the new process exits.</span></span> <span data-ttu-id="97c14-245">No sistema não Windows, raramente isso é necessário, pois o comportamento padrão para aplicativos de linha de comando é equivalente a `Start-Process -Wait` .</span><span class="sxs-lookup"><span data-stu-id="97c14-245">On non-Windows system, this is rarely needed since the default behavior for command-line applications is equivalent to `Start-Process -Wait`.</span></span>

- <span data-ttu-id="97c14-246">Ao usar `Start-Process` em sistemas não Windows, você nunca Obtém uma nova janela de terminal.</span><span class="sxs-lookup"><span data-stu-id="97c14-246">When using `Start-Process` on non-Windows systems, you never get a new terminal window.</span></span>

## <span data-ttu-id="97c14-247">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="97c14-247">RELATED LINKS</span></span>

[<span data-ttu-id="97c14-248">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="97c14-248">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="97c14-249">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="97c14-249">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="97c14-250">Get-Process</span><span class="sxs-lookup"><span data-stu-id="97c14-250">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="97c14-251">Start-Service</span><span class="sxs-lookup"><span data-stu-id="97c14-251">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="97c14-252">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="97c14-252">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="97c14-253">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="97c14-253">Wait-Process</span></span>](Wait-Process.md)
