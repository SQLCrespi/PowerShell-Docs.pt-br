---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 0e6df859a19f2281cc835b725fbc52c232042e56
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597405"
---
# <span data-ttu-id="d3c5f-102">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="d3c5f-102">Restart-Computer</span></span>

## <span data-ttu-id="d3c5f-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d3c5f-103">SYNOPSIS</span></span>
<span data-ttu-id="d3c5f-104">Reinicia o sistema operacional em computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-104">Restarts the operating system on local and remote computers.</span></span>

## <span data-ttu-id="d3c5f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d3c5f-105">SYNTAX</span></span>

### <span data-ttu-id="d3c5f-106">Padrãoset (padrão)</span><span class="sxs-lookup"><span data-stu-id="d3c5f-106">DefaultSet (Default)</span></span>

```
Restart-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential]<PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d3c5f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d3c5f-107">DESCRIPTION</span></span>

<span data-ttu-id="d3c5f-108">O `Restart-Computer` cmdlet reinicia o sistema operacional nos computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-108">The `Restart-Computer` cmdlet restarts the operating system on the local and remote computers.</span></span>

<span data-ttu-id="d3c5f-109">Você pode usar os parâmetros de `Restart-Computer` para executar as operações de reinicialização, para especificar os níveis de autenticação e as credenciais alternativas, para limitar as operações executadas ao mesmo tempo e forçar uma reinicialização imediata.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-109">You can use the parameters of `Restart-Computer` to run the restart operations, to specify the authentication levels and alternate credentials, to limit the operations that run at the same time, and to force an immediate restart.</span></span>

<span data-ttu-id="d3c5f-110">A partir do Windows PowerShell 3,0, você pode aguardar a conclusão da reinicialização antes de executar o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-110">Starting in Windows PowerShell 3.0, you can wait for the restart to complete before you run the next command.</span></span> <span data-ttu-id="d3c5f-111">Especifique um tempo limite de espera e um intervalo de consulta e aguarde a disponibilidade de serviços específicos no computador reiniciado.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-111">Specify a waiting time-out and query interval, and wait for particular services to be available on the restarted computer.</span></span> <span data-ttu-id="d3c5f-112">Esse recurso torna o uso prático `Restart-Computer` em scripts e funções.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-112">This feature makes it practical to use `Restart-Computer` in scripts and functions.</span></span>

## <span data-ttu-id="d3c5f-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d3c5f-113">EXAMPLES</span></span>

### <span data-ttu-id="d3c5f-114">Exemplo 1: reiniciar o computador local</span><span class="sxs-lookup"><span data-stu-id="d3c5f-114">Example 1: Restart the local computer</span></span>

<span data-ttu-id="d3c5f-115">`Restart-Computer` reinicia o computador local.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-115">`Restart-Computer` restarts the local computer.</span></span>

```powershell
Restart-Computer
```

### <span data-ttu-id="d3c5f-116">Exemplo 2: reiniciar vários computadores</span><span class="sxs-lookup"><span data-stu-id="d3c5f-116">Example 2: Restart multiple computers</span></span>

<span data-ttu-id="d3c5f-117">`Restart-Computer` pode reiniciar computadores remotos e locais.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-117">`Restart-Computer` can restart remote and local computers.</span></span> <span data-ttu-id="d3c5f-118">O parâmetro **ComputerName** aceita uma matriz de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-118">The **ComputerName** parameter accepts an array of computer names.</span></span>

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### <span data-ttu-id="d3c5f-119">Exemplo 3: obter nomes de computador de um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="d3c5f-119">Example 3: Get computer names from a text file</span></span>

<span data-ttu-id="d3c5f-120">`Restart-Computer` Obtém uma lista de nomes de computador de um arquivo de texto e reinicia os computadores.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-120">`Restart-Computer` gets a list of computer names from a text file and restarts the computers.</span></span> <span data-ttu-id="d3c5f-121">O parâmetro **ComputerName** não foi especificado.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-121">The **ComputerName** parameter isn't specified.</span></span> <span data-ttu-id="d3c5f-122">Mas, como é o primeiro parâmetro de posição, ele aceita os nomes de computador do arquivo de texto que são enviados pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-122">But because it's the first position parameter, it accepts the computer names from the text file that are sent down the pipeline.</span></span>

```powershell
Get-Content -Path C:\Domain01.txt | Restart-Computer
```

<span data-ttu-id="d3c5f-123">`Get-Content` usa o parâmetro **path** para obter uma lista de nomes de computador de um arquivo de texto, **Domain01.txt**.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-123">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt**.</span></span> <span data-ttu-id="d3c5f-124">Os nomes dos computadores são enviados pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-124">The computer names are sent down the pipeline.</span></span> <span data-ttu-id="d3c5f-125">`Restart-Computer` reinicia cada computador.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-125">`Restart-Computer` restarts each computer.</span></span>

### <span data-ttu-id="d3c5f-126">Exemplo 4: forçar a reinicialização de computadores listados em um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="d3c5f-126">Example 4: Force restart of computers listed in a text file</span></span>

<span data-ttu-id="d3c5f-127">Este exemplo força uma reinicialização imediata dos computadores listados no `Domain01.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-127">This example forces an immediate restart of the computers listed in the `Domain01.txt` file.</span></span> <span data-ttu-id="d3c5f-128">Os nomes de computador do arquivo de texto são armazenados em uma variável.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-128">The computer names from the text file are stored in a variable.</span></span> <span data-ttu-id="d3c5f-129">O parâmetro **Force** força uma reinicialização imediata.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-129">The **Force** parameter forces an immediate restart.</span></span>

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force
```

<span data-ttu-id="d3c5f-130">`Get-Content` usa o parâmetro **path** para obter uma lista de nomes de computador de um arquivo de texto, **Domain01.txt**.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-130">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt**.</span></span> <span data-ttu-id="d3c5f-131">Os nomes dos computadores são armazenados na variável `$Names` .</span><span class="sxs-lookup"><span data-stu-id="d3c5f-131">The computer names are stored in the variable `$Names`.</span></span> <span data-ttu-id="d3c5f-132">`Get-Credential` solicita um nome de usuário e uma senha e armazena os valores na variável `$Creds` .</span><span class="sxs-lookup"><span data-stu-id="d3c5f-132">`Get-Credential` prompts you for a username and password and stores the values in the variable `$Creds`.</span></span> <span data-ttu-id="d3c5f-133">`Restart-Computer` usa os parâmetros **ComputerName** e **Credential** com suas variáveis.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-133">`Restart-Computer` uses the **ComputerName** and **Credential** parameters with their variables.</span></span> <span data-ttu-id="d3c5f-134">O parâmetro **Force** causa uma reinicialização imediata de cada computador.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-134">The **Force** parameter causes an immediate restart of each computer.</span></span>

### <span data-ttu-id="d3c5f-135">Exemplo 6: reiniciar um computador remoto e aguardar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3c5f-135">Example 6: Restart a remote computer and wait for PowerShell</span></span>

<span data-ttu-id="d3c5f-136">`Restart-Computer` reinicia o computador remoto e aguarda até 5 minutos (300 segundos) para que o PowerShell fique disponível no computador reiniciado antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-136">`Restart-Computer` restarts the remote computer and then waits up to 5 minutes (300 seconds) for PowerShell to become available on the restarted computer before it continues.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

<span data-ttu-id="d3c5f-137">`Restart-Computer` usa o parâmetro **ComputerName** para especificar **Server01**.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-137">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01**.</span></span> <span data-ttu-id="d3c5f-138">O parâmetro **Wait** aguarda a conclusão da reinicialização.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-138">The **Wait** parameter waits for the restart to finish.</span></span> <span data-ttu-id="d3c5f-139">O **para** especifica que o PowerShell pode executar comandos no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-139">The **For** specifies that PowerShell can run commands on the remote computer.</span></span> <span data-ttu-id="d3c5f-140">O parâmetro **Timeout** especifica uma espera de cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-140">The **Timeout** parameter specifies a five-minute wait.</span></span> <span data-ttu-id="d3c5f-141">O parâmetro **Delay** consulta o computador remoto a cada dois segundos para determinar se ele foi reiniciado.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-141">The **Delay** parameter queries the remote computer every two seconds to determine whether it's restarted.</span></span>

### <span data-ttu-id="d3c5f-142">Exemplo 7: reiniciar um computador usando o WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="d3c5f-142">Example 7: Restart a computer by using WsmanAuthentication</span></span>

<span data-ttu-id="d3c5f-143">`Restart-Computer` reinicia o computador remoto usando o mecanismo **WsmanAuthentication** .</span><span class="sxs-lookup"><span data-stu-id="d3c5f-143">`Restart-Computer` restarts the remote computer using the **WsmanAuthentication** mechanism.</span></span>
<span data-ttu-id="d3c5f-144">A autenticação Kerberos determina se o usuário atual tem permissão para reiniciar o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-144">Kerberos authentication determines whether the current user has permission to restart the remote computer.</span></span> <span data-ttu-id="d3c5f-145">Para obter mais informações, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="d3c5f-145">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

```powershell
Restart-Computer -ComputerName Server01 -WsmanAuthentication Kerberos
```

<span data-ttu-id="d3c5f-146">`Restart-Computer` usa o parâmetro **ComputerName** para especificar o computador remoto, **Server01**.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-146">`Restart-Computer` uses the **ComputerName** parameter to specify the remote computer, **Server01**.</span></span>
<span data-ttu-id="d3c5f-147">O parâmetro **WsmanAuthentication** especifica o método de autenticação como **Kerberos**.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-147">The **WsmanAuthentication** parameter specifies the authentication method as **Kerberos**.</span></span>

## <span data-ttu-id="d3c5f-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d3c5f-148">PARAMETERS</span></span>

### <span data-ttu-id="d3c5f-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d3c5f-149">-ComputerName</span></span>

<span data-ttu-id="d3c5f-150">Especifica um nome de computador ou uma matriz separada por vírgulas de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-150">Specifies one computer name or a comma-separated array of computer names.</span></span> <span data-ttu-id="d3c5f-151">`Restart-Computer` aceita objetos **ComputerName** do pipeline ou das variáveis.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-151">`Restart-Computer` accepts **ComputerName** objects from the pipeline or variables.</span></span>

<span data-ttu-id="d3c5f-152">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-152">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span> <span data-ttu-id="d3c5f-153">Para especificar o computador local, digite o nome do computador, um ponto `.` ou localhost.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-153">To specify the local computer, type the computer name, a dot `.`, or localhost.</span></span>

<span data-ttu-id="d3c5f-154">Esse parâmetro não depende da comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-154">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="d3c5f-155">Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-155">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

<span data-ttu-id="d3c5f-156">Se o parâmetro **ComputerName** não for especificado, `Restart-Computer` o reiniciará o computador local.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-156">If the **ComputerName** parameter isn't specified, `Restart-Computer` restarts the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d3c5f-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="d3c5f-157">-Credential</span></span>

<span data-ttu-id="d3c5f-158">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-158">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="d3c5f-159">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-159">The default is the current user.</span></span>

<span data-ttu-id="d3c5f-160">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-160">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="d3c5f-161">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-161">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="d3c5f-162">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="d3c5f-162">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="d3c5f-163">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="d3c5f-163">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3c5f-164">-Atraso</span><span class="sxs-lookup"><span data-stu-id="d3c5f-164">-Delay</span></span>

<span data-ttu-id="d3c5f-165">Especifica a frequência de consultas, em segundos.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-165">Specifies the frequency of queries, in seconds.</span></span> <span data-ttu-id="d3c5f-166">O PowerShell consulta o serviço especificado pelo parâmetro **for** para determinar se o serviço está disponível depois que o computador é reiniciado.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-166">PowerShell queries the service specified by the **For** parameter to determine whether the service is available after the computer is restarted.</span></span>

<span data-ttu-id="d3c5f-167">Esse parâmetro é válido somente junto com os parâmetros **Wait** e **for** .</span><span class="sxs-lookup"><span data-stu-id="d3c5f-167">This parameter is valid only together with the **Wait** and **For** parameters.</span></span>

<span data-ttu-id="d3c5f-168">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-168">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d3c5f-169">Se o parâmetro **Delay** não for especificado, o `Restart-Computer` usará um atraso de cinco segundos.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-169">If the **Delay** parameter isn't specified, `Restart-Computer` uses a five second delay.</span></span>

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3c5f-170">-Para</span><span class="sxs-lookup"><span data-stu-id="d3c5f-170">-For</span></span>

<span data-ttu-id="d3c5f-171">Especifica o comportamento do PowerShell, pois ele aguarda que o serviço ou o recurso especificado se torne disponível após a reinicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-171">Specifies the behavior of PowerShell as it waits for the specified service or feature to become available after the computer restarts.</span></span> <span data-ttu-id="d3c5f-172">Esse parâmetro só é válido com o parâmetro **Wait** .</span><span class="sxs-lookup"><span data-stu-id="d3c5f-172">This parameter is only valid with the **Wait** parameter.</span></span>

<span data-ttu-id="d3c5f-173">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="d3c5f-173">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d3c5f-174">**Padrão**: aguarda a reinicialização do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-174">**Default**: Waits for PowerShell to restart.</span></span>
- <span data-ttu-id="d3c5f-175">**PowerShell**: pode executar comandos em uma sessão remota do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-175">**PowerShell**: Can run commands in a PowerShell remote session on the computer.</span></span>
- <span data-ttu-id="d3c5f-176">**WMI**: recebe uma resposta a uma consulta Win32_ComputerSystem para o computador.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-176">**WMI**: Receives a reply to a Win32_ComputerSystem query for the computer.</span></span>
- <span data-ttu-id="d3c5f-177">**WinRM**: pode estabelecer uma sessão remota para o computador usando o WS-Management.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-177">**WinRM**: Can establish a remote session to the computer by using WS-Management.</span></span>

<span data-ttu-id="d3c5f-178">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-178">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: (All)
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3c5f-179">-Force</span><span class="sxs-lookup"><span data-stu-id="d3c5f-179">-Force</span></span>

<span data-ttu-id="d3c5f-180">Força uma reinicialização imediata do computador.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-180">Forces an immediate restart of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3c5f-181">-Tempo limite</span><span class="sxs-lookup"><span data-stu-id="d3c5f-181">-Timeout</span></span>

<span data-ttu-id="d3c5f-182">Especifica a duração da espera, em segundos.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-182">Specifies the duration of the wait, in seconds.</span></span> <span data-ttu-id="d3c5f-183">Quando o tempo limite expira, o `Restart-Computer` retorna ao prompt de comando, mesmo que os computadores não sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-183">When the timeout elapses, `Restart-Computer` returns to the command prompt, even if the computers aren't restarted.</span></span>

<span data-ttu-id="d3c5f-184">O parâmetro **Timeout** só é válido com o parâmetro **Wait** .</span><span class="sxs-lookup"><span data-stu-id="d3c5f-184">The **Timeout** parameter is only valid with the **Wait** parameter.</span></span> <span data-ttu-id="d3c5f-185">O **tempo limite** substitui o período de espera indefinido do parâmetro de **espera** .</span><span class="sxs-lookup"><span data-stu-id="d3c5f-185">**Timeout** overrides the **Wait** parameter's indefinite waiting period.</span></span>

<span data-ttu-id="d3c5f-186">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-186">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3c5f-187">-Wait</span><span class="sxs-lookup"><span data-stu-id="d3c5f-187">-Wait</span></span>

<span data-ttu-id="d3c5f-188">`Restart-Computer` suprime o prompt do PowerShell e bloqueia o pipeline até que os computadores sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-188">`Restart-Computer` suppresses the PowerShell prompt and blocks the pipeline until the computers have restarted.</span></span> <span data-ttu-id="d3c5f-189">Você pode usar esse parâmetro em um script para reiniciar os computadores e continuar a processar quando a reinicialização for concluída.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-189">You can use this parameter in a script to restart computers and then continue to process when the restart is finished.</span></span>

<span data-ttu-id="d3c5f-190">O parâmetro **Wait** aguarda indefinidamente para que os computadores sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-190">The **Wait** parameter waits indefinitely for the computers to restart.</span></span> <span data-ttu-id="d3c5f-191">Você pode usar o **tempo limite** para ajustar o tempo e os parâmetros **de e de** **atraso** para aguardar que serviços específicos se tornem disponíveis nos computadores reiniciados.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-191">You can use **Timeout** to adjust the timing and the **For** and **Delay** parameters to wait for particular services to become available on the restarted computers.</span></span>

<span data-ttu-id="d3c5f-192">O parâmetro **Wait** não é válido quando você está reiniciando o computador local.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-192">The **Wait** parameter isn't valid when you're restarting the local computer.</span></span> <span data-ttu-id="d3c5f-193">Se o valor do parâmetro **ComputerName** contiver os nomes de computadores remotos e o computador local, o `Restart-Computer` gerará um erro de não finalização para **aguardar** no computador local, mas aguardará a reinicialização dos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-193">If the value of the **ComputerName** parameter contains the names of remote computers and the local computer, `Restart-Computer` generates a non-terminating error for **Wait** on the local computer, but waits for the remote computers to restart.</span></span>

<span data-ttu-id="d3c5f-194">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-194">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d3c5f-195">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="d3c5f-195">-WsmanAuthentication</span></span>

<span data-ttu-id="d3c5f-196">Especifica o mecanismo usado para autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-196">Specifies the mechanism that is used to authenticate the user credentials.</span></span> <span data-ttu-id="d3c5f-197">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-197">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d3c5f-198">Os valores aceitáveis para esse parâmetro são: **Basic**, **CredSSP**, **Default**, **Digest**, **Kerberos** e **Negotiate**.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-198">The acceptable values for this parameter are: **Basic**, **CredSSP**, **Default**, **Digest**, **Kerberos**, and **Negotiate**.</span></span>

<span data-ttu-id="d3c5f-199">Para obter mais informações, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="d3c5f-199">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="d3c5f-200">A autenticação do Credential Security Service Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-200">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="d3c5f-201">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-201">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="d3c5f-202">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-202">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3c5f-203">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d3c5f-203">-Confirm</span></span>

<span data-ttu-id="d3c5f-204">Solicita a confirmação antes de executar `Restart-Computer` .</span><span class="sxs-lookup"><span data-stu-id="d3c5f-204">Prompts you for confirmation before running `Restart-Computer`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3c5f-205">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d3c5f-205">-WhatIf</span></span>

<span data-ttu-id="d3c5f-206">Mostra o que aconteceria se o `Restart-Computer` for executado.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-206">Shows what would happen if the `Restart-Computer` runs.</span></span> <span data-ttu-id="d3c5f-207">O `Restart-Computer` cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-207">The `Restart-Computer` cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3c5f-208">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d3c5f-208">CommonParameters</span></span>

<span data-ttu-id="d3c5f-209">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-209">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d3c5f-210">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d3c5f-210">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d3c5f-211">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d3c5f-211">INPUTS</span></span>

### <span data-ttu-id="d3c5f-212">System.String</span><span class="sxs-lookup"><span data-stu-id="d3c5f-212">System.String</span></span>

<span data-ttu-id="d3c5f-213">`Restart-Computer` aceita nomes de computador do pipeline ou de variáveis.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-213">`Restart-Computer` accepts computer names from the pipeline or variables.</span></span>

## <span data-ttu-id="d3c5f-214">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d3c5f-214">OUTPUTS</span></span>

### <span data-ttu-id="d3c5f-215">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d3c5f-215">None</span></span>

<span data-ttu-id="d3c5f-216">`Restart-Computer` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-216">`Restart-Computer` doesn't generate any output.</span></span>

## <span data-ttu-id="d3c5f-217">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d3c5f-217">NOTES</span></span>

- <span data-ttu-id="d3c5f-218">No Windows, `Restart-Computer` o usa o [método Win32Shutdown](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) da classe Instrumentação de gerenciamento do Windows (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) .</span><span class="sxs-lookup"><span data-stu-id="d3c5f-218">In Windows, `Restart-Computer` uses the [Win32Shutdown method](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) of the Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) class.</span></span> <span data-ttu-id="d3c5f-219">Esse método requer que o privilégio **SeShutdownPrivilege** seja habilitado para a conta de usuário usada para reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-219">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>
- <span data-ttu-id="d3c5f-220">No Linux e Mac OS, `Restart-Computer` o usa a `/sbin/shutdown` ferramenta bash.</span><span class="sxs-lookup"><span data-stu-id="d3c5f-220">On Linux and Mac OS, `Restart-Computer` uses the `/sbin/shutdown` bash tool.</span></span>

## <span data-ttu-id="d3c5f-221">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d3c5f-221">RELATED LINKS</span></span>

[<span data-ttu-id="d3c5f-222">Sobre Gerenciamento Remoto do Windows</span><span class="sxs-lookup"><span data-stu-id="d3c5f-222">About Windows Remote Management</span></span>](/windows/desktop/WinRM/about-windows-remote-management)

[<span data-ttu-id="d3c5f-223">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="d3c5f-223">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="d3c5f-224">Protocolo WS-Management</span><span class="sxs-lookup"><span data-stu-id="d3c5f-224">WS-Management Protocol</span></span>](/windows/desktop/WinRM/ws-management-protocol)
