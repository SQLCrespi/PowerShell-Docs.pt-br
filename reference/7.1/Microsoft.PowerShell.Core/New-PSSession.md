---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSession
ms.openlocfilehash: e5dedf3d161f2687bddfbd09740812d8c5cbaa77
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93195027"
---
# <span data-ttu-id="d45d0-103">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="d45d0-103">New-PSSession</span></span>

## <span data-ttu-id="d45d0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d45d0-104">SYNOPSIS</span></span>
<span data-ttu-id="d45d0-105">Cria uma conexão persistente para um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-105">Creates a persistent connection to a local or remote computer.</span></span>

## <span data-ttu-id="d45d0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d45d0-106">SYNTAX</span></span>

### <span data-ttu-id="d45d0-107">ComputerName (padrão)</span><span class="sxs-lookup"><span data-stu-id="d45d0-107">ComputerName (Default)</span></span>

```
New-PSSession [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Name <String[]>]
 [-EnableNetworkAccess] [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="d45d0-108">Uri</span><span class="sxs-lookup"><span data-stu-id="d45d0-108">Uri</span></span>

```
New-PSSession [-Credential <PSCredential>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="d45d0-109">VMId</span><span class="sxs-lookup"><span data-stu-id="d45d0-109">VMId</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 [-VMId] <Guid[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="d45d0-110">VMName</span><span class="sxs-lookup"><span data-stu-id="d45d0-110">VMName</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 -VMName <String[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="d45d0-111">Session</span><span class="sxs-lookup"><span data-stu-id="d45d0-111">Session</span></span>

```
New-PSSession [[-Session] <PSSession[]>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="d45d0-112">ContainerId</span><span class="sxs-lookup"><span data-stu-id="d45d0-112">ContainerId</span></span>

```
New-PSSession [-Name <String[]>] [-ConfigurationName <String>] -ContainerId <String[]>
 [-RunAsAdministrator] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="d45d0-113">UseWindowsPowerShellParameterSet</span><span class="sxs-lookup"><span data-stu-id="d45d0-113">UseWindowsPowerShellParameterSet</span></span>

```
New-PSSession [-Name <String[]>] [-UseWindowsPowerShell] [<CommonParameters>]
```

### <span data-ttu-id="d45d0-114">SSHHost</span><span class="sxs-lookup"><span data-stu-id="d45d0-114">SSHHost</span></span>

```
New-PSSession [-Name <String[]>] [-Port <Int32>] [-HostName] <String[]> [-UserName <String>]
 [-KeyFilePath <String>] [-SSHTransport] [-Subsystem <String>] [<CommonParameters>]
```

### <span data-ttu-id="d45d0-115">SSHHostHashParam</span><span class="sxs-lookup"><span data-stu-id="d45d0-115">SSHHostHashParam</span></span>

```
New-PSSession [-Name <String[]>] -SSHConnection <Hashtable[]> [<CommonParameters>]
```

## <span data-ttu-id="d45d0-116">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d45d0-116">DESCRIPTION</span></span>

<span data-ttu-id="d45d0-117">O `New-PSSession` cmdlet cria uma sessão do PowerShell ( **PSSession** ) em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-117">The `New-PSSession` cmdlet creates a PowerShell session ( **PSSession** ) on a local or remote computer.</span></span> <span data-ttu-id="d45d0-118">Quando você cria uma **PSSession** , o PowerShell estabelece uma conexão persistente com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-118">When you create a **PSSession** , PowerShell establishes a persistent connection to the remote computer.</span></span>

<span data-ttu-id="d45d0-119">Use uma **PSSession** para executar vários comandos que compartilham dados, como uma função ou o valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="d45d0-119">Use a **PSSession** to run multiple commands that share data, such as a function or the value of a variable.</span></span> <span data-ttu-id="d45d0-120">Para executar comandos em uma **PSSession** , use o `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d45d0-120">To run commands in a **PSSession** , use the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="d45d0-121">Para usar a **PSSession** para interagir diretamente com um computador remoto, use o `Enter-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d45d0-121">To use the **PSSession** to interact directly with a remote computer, use the `Enter-PSSession` cmdlet.</span></span> <span data-ttu-id="d45d0-122">Para obter mais informações, consulte [about_PSSessions](about/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="d45d0-122">For more information, see [about_PSSessions](about/about_PSSessions.md).</span></span>

<span data-ttu-id="d45d0-123">Você pode executar comandos em um computador remoto sem criar uma **PSSession** usando os parâmetros **ComputerName** de `Enter-PSSession` ou `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="d45d0-123">You can run commands on a remote computer without creating a **PSSession** by using the **ComputerName** parameters of `Enter-PSSession` or `Invoke-Command`.</span></span> <span data-ttu-id="d45d0-124">Quando você usa o parâmetro **ComputerName** , o PowerShell cria uma conexão temporária que é usada para o comando e, em seguida, é fechada.</span><span class="sxs-lookup"><span data-stu-id="d45d0-124">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that is used for the command and is then closed.</span></span>

<span data-ttu-id="d45d0-125">A partir do PowerShell 6,0, você pode usar Secure Shell (SSH) para estabelecer uma conexão com o e criar uma sessão em um computador remoto, se o SSH estiver disponível no computador local e o computador remoto estiver configurado com um ponto de extremidade SSH do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d45d0-125">Starting with PowerShell 6.0 you can use Secure Shell (SSH) to establish a connection to and create a session on a remote computer, if SSH is available on the local computer and the remote computer is configured with a PowerShell SSH endpoint.</span></span> <span data-ttu-id="d45d0-126">O benefício de uma sessão remota do PowerShell baseada em SSH é que ela pode funcionar em várias plataformas (Windows, Linux e macOS).</span><span class="sxs-lookup"><span data-stu-id="d45d0-126">The benefit of an SSH based PowerShell remote session is that it can work across multiple platforms (Windows, Linux, macOS).</span></span> <span data-ttu-id="d45d0-127">Para sessões baseadas em SSH, use o parâmetro **hostname** ou **SSHConnection** definido para especificar o computador remoto e as informações de conexão relevantes.</span><span class="sxs-lookup"><span data-stu-id="d45d0-127">For SSH based sessions you use the **HostName** or **SSHConnection** parameter set to specify the remote computer and relevant connection information.</span></span> <span data-ttu-id="d45d0-128">Para obter mais informações sobre como configurar a comunicação remota do PowerShell SSH, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="d45d0-128">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

> [!NOTE]
> <span data-ttu-id="d45d0-129">Ao usar a comunicação remota do WSMan em um cliente Linux ou macOS com um ponto de extremidade HTTPS em que o certificado do servidor não é confiável (por exemplo, um certificado autoassinado).</span><span class="sxs-lookup"><span data-stu-id="d45d0-129">When using WSMan remoting from a Linux or macOS client with a HTTPS endpoint where the server certificate is not trusted (e.g., a self-signed certificate).</span></span> <span data-ttu-id="d45d0-130">Você deve fornecer um `PSSessionOption` que inclui `-SkipCACheck` e `-SkipCNCheck` para estabelecer a conexão com êxito.</span><span class="sxs-lookup"><span data-stu-id="d45d0-130">You must provide a `PSSessionOption` that includes `-SkipCACheck` and `-SkipCNCheck` to successfully establish the connection.</span></span> <span data-ttu-id="d45d0-131">Faça isso apenas se você estiver em um ambiente em que você pode ter certeza do certificado do servidor e da conexão de rede com o sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="d45d0-131">Only do this if you are in an environment where you can be certain of the server certificate and the network connection to the target system.</span></span>

## <span data-ttu-id="d45d0-132">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d45d0-132">EXAMPLES</span></span>

### <span data-ttu-id="d45d0-133">Exemplo 1: criar uma sessão no computador local</span><span class="sxs-lookup"><span data-stu-id="d45d0-133">Example 1: Create a session on the local computer</span></span>

```powershell
$s = New-PSSession
```

<span data-ttu-id="d45d0-134">Esse comando cria uma nova **PSSession** no computador local e salva a **PSSession** na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="d45d0-134">This command creates a new **PSSession** on the local computer and saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="d45d0-135">Agora você pode usar esta **PSSession** para executar comandos no computador local.</span><span class="sxs-lookup"><span data-stu-id="d45d0-135">You can now use this **PSSession** to run commands on the local computer.</span></span>

### <span data-ttu-id="d45d0-136">Exemplo 2: criar uma sessão em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="d45d0-136">Example 2: Create a session on a remote computer</span></span>

```powershell
$Server01 = New-PSSession -ComputerName Server01
```

<span data-ttu-id="d45d0-137">Esse comando cria uma nova **PSSession** no computador Server01 e salva-a na `$Server01` variável.</span><span class="sxs-lookup"><span data-stu-id="d45d0-137">This command creates a new **PSSession** on the Server01 computer and saves it in the `$Server01` variable.</span></span>

<span data-ttu-id="d45d0-138">Ao criar vários objetos **PSSession** , atribua-os a variáveis com nomes úteis.</span><span class="sxs-lookup"><span data-stu-id="d45d0-138">When creating multiple **PSSession** objects, assign them to variables with useful names.</span></span> <span data-ttu-id="d45d0-139">Isso ajudará você a gerenciar os objetos **PSSession** em comandos subsequentes.</span><span class="sxs-lookup"><span data-stu-id="d45d0-139">This will help you manage the **PSSession** objects in subsequent commands.</span></span>

### <span data-ttu-id="d45d0-140">Exemplo 3: criar sessões em vários computadores</span><span class="sxs-lookup"><span data-stu-id="d45d0-140">Example 3: Create sessions on multiple computers</span></span>

```powershell
$s1, $s2, $s3 = New-PSSession -ComputerName Server01,Server02,Server03
```

<span data-ttu-id="d45d0-141">Esse comando cria três objetos **PSSession** , um em cada um dos computadores especificados pelo parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-141">This command creates three **PSSession** objects, one on each of the computers specified by the **ComputerName** parameter.</span></span>

<span data-ttu-id="d45d0-142">O comando usa o operador de atribuição (=) para atribuir os novos objetos **PSSession** às variáveis: `$s1` , `$s2` , `$s3` .</span><span class="sxs-lookup"><span data-stu-id="d45d0-142">The command uses the assignment operator (=) to assign the new **PSSession** objects to variables: `$s1`, `$s2`, `$s3`.</span></span> <span data-ttu-id="d45d0-143">Ele atribui a **PSSession** Server01 a `$s1` , a **PSSession** Server02 `$s2` e a Server03 **PSSession** para `$s3` .</span><span class="sxs-lookup"><span data-stu-id="d45d0-143">It assigns the Server01 **PSSession** to `$s1`, the Server02 **PSSession** to `$s2`, and the Server03 **PSSession** to `$s3`.</span></span>

<span data-ttu-id="d45d0-144">Quando você atribui vários objetos a uma série de variáveis, o PowerShell atribui cada objeto a uma variável na série, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d45d0-144">When you assign multiple objects to a series of variables, PowerShell assigns each object to a variable in the series respectively.</span></span> <span data-ttu-id="d45d0-145">Se houver mais objetos que variáveis, todos os objetos restantes serão atribuídos à última variável.</span><span class="sxs-lookup"><span data-stu-id="d45d0-145">If there are more objects than variables, all remaining objects are assigned to the last variable.</span></span> <span data-ttu-id="d45d0-146">Se houver mais variáveis que objetos, as variáveis restantes ficarão vazias (nulas).</span><span class="sxs-lookup"><span data-stu-id="d45d0-146">If there are more variables than objects, the remaining variables are empty (null).</span></span>

### <span data-ttu-id="d45d0-147">Exemplo 4: criar uma sessão com uma porta especificada</span><span class="sxs-lookup"><span data-stu-id="d45d0-147">Example 4: Create a session with a specified port</span></span>

```powershell
New-PSSession -ComputerName Server01 -Port 8081 -UseSSL -ConfigurationName E12
```

<span data-ttu-id="d45d0-148">Este comando cria uma nova **PSSession** no computador Server01 que se conecta à porta do servidor 8081 e usa o protocolo SSL.</span><span class="sxs-lookup"><span data-stu-id="d45d0-148">This command creates a new **PSSession** on the Server01 computer that connects to server port 8081 and uses the SSL protocol.</span></span> <span data-ttu-id="d45d0-149">A nova **PSSession** usa uma configuração de sessão alternativa chamada E12.</span><span class="sxs-lookup"><span data-stu-id="d45d0-149">The new **PSSession** uses an alternative session configuration called E12.</span></span>

<span data-ttu-id="d45d0-150">Antes de configurar a porta, você deve configurar o ouvinte WinRM no computador remoto para escutar na porta 8081.</span><span class="sxs-lookup"><span data-stu-id="d45d0-150">Before setting the port, you must configure the WinRM listener on the remote computer to listen on port 8081.</span></span> <span data-ttu-id="d45d0-151">Para obter mais informações, consulte a descrição do parâmetro **Port** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-151">For more information, see the description of the **Port** parameter.</span></span>

### <span data-ttu-id="d45d0-152">Exemplo 5: criar uma sessão com base em uma sessão existente</span><span class="sxs-lookup"><span data-stu-id="d45d0-152">Example 5: Create a session based on an existing session</span></span>

```powershell
New-PSSession -Session $s -Credential Domain01\User01
```

<span data-ttu-id="d45d0-153">Este comando cria uma **PSSession** com as mesmas propriedades de uma **PSSession** existente.</span><span class="sxs-lookup"><span data-stu-id="d45d0-153">This command creates a **PSSession** with the same properties as an existing **PSSession** .</span></span> <span data-ttu-id="d45d0-154">Você pode usar esse formato de comando quando os recursos de uma **PSSession** existente são esgotados e uma nova **PSSession** é necessária para descarregar parte da demanda.</span><span class="sxs-lookup"><span data-stu-id="d45d0-154">You can use this command format when the resources of an existing **PSSession** are exhausted and a new **PSSession** is needed to offload some of the demand.</span></span>

<span data-ttu-id="d45d0-155">O comando usa o parâmetro **Session** de `New-PSSession` para especificar a **PSSession** salva na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="d45d0-155">The command uses the **Session** parameter of `New-PSSession` to specify the **PSSession** saved in the `$s` variable.</span></span> <span data-ttu-id="d45d0-156">Ele usa as credenciais do usuário Domain1\Admin01 para concluir o comando.</span><span class="sxs-lookup"><span data-stu-id="d45d0-156">It uses the credentials of the Domain1\Admin01 user to complete the command.</span></span>

### <span data-ttu-id="d45d0-157">Exemplo 6: criar uma sessão com um escopo global em um domínio diferente</span><span class="sxs-lookup"><span data-stu-id="d45d0-157">Example 6: Create a session with a global scope in a different domain</span></span>

```powershell
$global:s = New-PSSession -ComputerName Server1.Domain44.Corpnet.Fabrikam.com -Credential Domain01\Admin01
```

<span data-ttu-id="d45d0-158">Este exemplo mostra como criar uma **PSSession** com um escopo global em um computador em um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="d45d0-158">This example shows how to create a **PSSession** with a global scope on a computer in a different domain.</span></span>

<span data-ttu-id="d45d0-159">Por padrão, os objetos **PSSession** criados na linha de comando são criados com o escopo local e os objetos **PSSession** criados em um script têm escopo de script.</span><span class="sxs-lookup"><span data-stu-id="d45d0-159">By default, **PSSession** objects created at the command line are created with local scope and **PSSession** objects created in a script have script scope.</span></span>

<span data-ttu-id="d45d0-160">Para criar uma **PSSession** com escopo global, crie uma nova **PSSession** e, em seguida, armazene a **PSSession** em uma variável que é convertida em um escopo global.</span><span class="sxs-lookup"><span data-stu-id="d45d0-160">To create a **PSSession** with global scope, create a new **PSSession** and then store the **PSSession** in a variable that is cast to a global scope.</span></span> <span data-ttu-id="d45d0-161">Nesse caso, a `$s` variável é convertida em um escopo global.</span><span class="sxs-lookup"><span data-stu-id="d45d0-161">In this case, the `$s` variable is cast to a global scope.</span></span>

<span data-ttu-id="d45d0-162">O comando usa o parâmetro **ComputerName** para especificar o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-162">The command uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="d45d0-163">Como o computador está em um domínio diferente da conta de usuário, o nome completo do computador é especificado junto com as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="d45d0-163">Because the computer is in a different domain than the user account, the full name of the computer is specified together with the credentials of the user.</span></span>

### <span data-ttu-id="d45d0-164">Exemplo 7: criar sessões para muitos computadores</span><span class="sxs-lookup"><span data-stu-id="d45d0-164">Example 7: Create sessions for many computers</span></span>

```powershell
$rs = Get-Content C:\Test\Servers.txt | New-PSSession -ThrottleLimit 50
```

<span data-ttu-id="d45d0-165">Esse comando cria uma **PSSession** em cada um dos computadores 200 listados no arquivo Servers.txt e armazena a **PSSession** resultante na `$rs` variável.</span><span class="sxs-lookup"><span data-stu-id="d45d0-165">This command creates a **PSSession** on each of the 200 computers listed in the Servers.txt file and it stores the resulting **PSSession** in the `$rs` variable.</span></span> <span data-ttu-id="d45d0-166">Os objetos **PSSession** têm um limite de limitação de 50.</span><span class="sxs-lookup"><span data-stu-id="d45d0-166">The **PSSession** objects have a throttle limit of 50.</span></span>

<span data-ttu-id="d45d0-167">Você pode usar esse formato de comando quando os nomes dos computadores são armazenados em um banco de dados, arquivo de texto, planilha ou outro formato convertível em texto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-167">You can use this command format when the names of computers are stored in a database, spreadsheet, text file, or other text-convertible format.</span></span>

### <span data-ttu-id="d45d0-168">Exemplo 8: criar uma sessão usando um URI</span><span class="sxs-lookup"><span data-stu-id="d45d0-168">Example 8: Create a session by using a URI</span></span>

```powershell
$s = New-PSSession -URI http://Server01:91/NewSession -Credential Domain01\User01
```

<span data-ttu-id="d45d0-169">Esse comando cria uma **PSSession** no computador Server01 e a armazena na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="d45d0-169">This command creates a **PSSession** on the Server01 computer and stores it in the `$s` variable.</span></span> <span data-ttu-id="d45d0-170">Ele usa o parâmetro **URI** para especificar o protocolo de transporte, o computador remoto, a porta e uma configuração de sessão alternativa.</span><span class="sxs-lookup"><span data-stu-id="d45d0-170">It uses the **URI** parameter to specify the transport protocol, the remote computer, the port, and an alternate session configuration.</span></span> <span data-ttu-id="d45d0-171">Ele também usa o parâmetro **Credential** para especificar uma conta de usuário que tenha permissão para criar uma sessão no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-171">It also uses the **Credential** parameter to specify a user account that has permission to create a session on the remote computer.</span></span>

### <span data-ttu-id="d45d0-172">Exemplo 9: executar um trabalho em segundo plano em um conjunto de sessões</span><span class="sxs-lookup"><span data-stu-id="d45d0-172">Example 9: Run a background job in a set of sessions</span></span>

```powershell
$s = New-PSSession -ComputerName (Get-Content Servers.txt) -Credential Domain01\Admin01 -ThrottleLimit 16
Invoke-Command -Session $s -ScriptBlock {Get-Process PowerShell} -AsJob
```

<span data-ttu-id="d45d0-173">Esses comandos criam um conjunto de objetos **PSSession** e, em seguida, executam um trabalho em segundo plano em cada um dos objetos **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-173">These commands create a set of **PSSession** objects and then run a background job in each of the **PSSession** objects.</span></span>

<span data-ttu-id="d45d0-174">O primeiro comando cria uma nova **PSSession** em cada um dos computadores listados no arquivo Servers.txt.</span><span class="sxs-lookup"><span data-stu-id="d45d0-174">The first command creates a new **PSSession** on each of the computers listed in the Servers.txt file.</span></span> <span data-ttu-id="d45d0-175">Ele usa o `New-PSSession` cmdlet para criar a **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-175">It uses the `New-PSSession` cmdlet to create the **PSSession** .</span></span> <span data-ttu-id="d45d0-176">O valor do parâmetro **ComputerName** é um comando que usa o `Get-Content` cmdlet para obter a lista de nomes de computador que o arquivo Servers.txt.</span><span class="sxs-lookup"><span data-stu-id="d45d0-176">The value of the **ComputerName** parameter is a command that uses the `Get-Content` cmdlet to get the list of computer names the Servers.txt file.</span></span>

<span data-ttu-id="d45d0-177">O comando usa o parâmetro **Credential** para criar os objetos **PSSession** que têm a permissão de um administrador de domínio e ele usa o parâmetro **ThrottleLimit** para limitar o comando a 16 conexões simultâneas.</span><span class="sxs-lookup"><span data-stu-id="d45d0-177">The command uses the **Credential** parameter to create the **PSSession** objects that have the permission of a domain administrator, and it uses the **ThrottleLimit** parameter to limit the command to 16 concurrent connections.</span></span> <span data-ttu-id="d45d0-178">O comando salva os objetos **PSSession** na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="d45d0-178">The command saves the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="d45d0-179">O segundo comando usa o parâmetro **AsJob** do `Invoke-Command` cmdlet para iniciar um trabalho em segundo plano que executa um `Get-Process PowerShell` comando em cada um dos objetos **PSSession** no `$s` .</span><span class="sxs-lookup"><span data-stu-id="d45d0-179">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a background job that runs a `Get-Process PowerShell` command in each of the **PSSession** objects in `$s`.</span></span>

<span data-ttu-id="d45d0-180">Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](About/about_Jobs.md) e [about_Remote_Jobs](About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="d45d0-180">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

### <span data-ttu-id="d45d0-181">Exemplo 10: criar uma sessão para um computador usando seu URI</span><span class="sxs-lookup"><span data-stu-id="d45d0-181">Example 10: Create a session for a computer by using its URI</span></span>

```powershell
New-PSSession -ConnectionURI https://management.exchangelabs.com/Management
```

<span data-ttu-id="d45d0-182">Este comando cria objetos **PSSession** que se conectam a um computador especificado por um URI em vez de um nome de computador.</span><span class="sxs-lookup"><span data-stu-id="d45d0-182">This command creates a **PSSession** objects that connects to a computer that is specified by a URI instead of a computer name.</span></span>

### <span data-ttu-id="d45d0-183">Exemplo 11: criar uma opção de sessão</span><span class="sxs-lookup"><span data-stu-id="d45d0-183">Example 11: Create a session option</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck
New-PSSession -ConnectionUri https://management.exchangelabs.com/Management -SessionOption $so -Credential Server01\Admin01
```

<span data-ttu-id="d45d0-184">Este exemplo mostra como criar um objeto de opção de sessão e usar o parâmetro **SessionOption** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-184">This example shows how to create a session option object and use the **SessionOption** parameter.</span></span>

<span data-ttu-id="d45d0-185">O primeiro comando usa o `New-PSSessionOption` cmdlet para criar uma opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-185">The first command uses the `New-PSSessionOption` cmdlet to create a session option.</span></span> <span data-ttu-id="d45d0-186">Ele salva o objeto **SessionOption** resultante na `$so` variável.</span><span class="sxs-lookup"><span data-stu-id="d45d0-186">It saves the resulting **SessionOption** object in the `$so` variable.</span></span>

<span data-ttu-id="d45d0-187">O segundo comando usa a opção em uma nova sessão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-187">The second command uses the option in a new session.</span></span> <span data-ttu-id="d45d0-188">O comando usa o `New-PSSession` cmdlet para criar uma nova sessão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-188">The command uses the `New-PSSession` cmdlet to create a new session.</span></span> <span data-ttu-id="d45d0-189">O valor do parâmetro SessionOption é o objeto **SessionOption** na `$so` variável.</span><span class="sxs-lookup"><span data-stu-id="d45d0-189">The value of the SessionOption parameter is the **SessionOption** object in the `$so` variable.</span></span>

### <span data-ttu-id="d45d0-190">Exemplo 12: criar uma sessão usando SSH</span><span class="sxs-lookup"><span data-stu-id="d45d0-190">Example 12: Create a session using SSH</span></span>

```powershell
New-PSSession -HostName UserA@LinuxServer01
```

<span data-ttu-id="d45d0-191">Este exemplo mostra como criar uma nova **PSSession** usando Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="d45d0-191">This example shows how to create a new **PSSession** using Secure Shell (SSH).</span></span> <span data-ttu-id="d45d0-192">Se o SSH estiver configurado no computador remoto para solicitar senhas, você receberá um prompt de senha.</span><span class="sxs-lookup"><span data-stu-id="d45d0-192">If SSH is configured on the remote computer to prompt for passwords then you will get a password prompt.</span></span> <span data-ttu-id="d45d0-193">Caso contrário, você precisará usar a autenticação de usuário baseada em chave SSH.</span><span class="sxs-lookup"><span data-stu-id="d45d0-193">Otherwise you will have to use SSH key based user authentication.</span></span>

### <span data-ttu-id="d45d0-194">Exemplo 13: criar uma sessão usando SSH e especificar a porta e a chave de autenticação do usuário</span><span class="sxs-lookup"><span data-stu-id="d45d0-194">Example 13: Create a session using SSH and specify the port and user authentication key</span></span>

```powershell
New-PSSession -HostName UserA@LinuxServer01:22 -KeyFilePath c:\<path>\userAKey_rsa
```

<span data-ttu-id="d45d0-195">Este exemplo mostra como criar uma **PSSession** usando Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="d45d0-195">This example shows how to create a **PSSession** using Secure Shell (SSH).</span></span> <span data-ttu-id="d45d0-196">Ele usa o parâmetro **Port** para especificar a porta a ser usada e o parâmetro **keyFilePath** para especificar uma chave RSA usada para identificar e autenticar o usuário no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-196">It uses the **Port** parameter to specify the port to use and the **KeyFilePath** parameter to specify an RSA key used to identify and authenticate the user on the remote computer.</span></span>

### <span data-ttu-id="d45d0-197">Exemplo 14: criar várias sessões usando SSH</span><span class="sxs-lookup"><span data-stu-id="d45d0-197">Example 14: Create multiple sessions using SSH</span></span>

```powershell
$sshConnections = @{ HostName="WinServer1"; UserName="domain\userA"; KeyFilePath="c:\users\UserA\id_rsa" }, @{ HostName="UserB@LinuxServer5"; KeyFilePath="c:\UserB\<path>\id_rsa" }
New-PSSession -SSHConnection $sshConnections
```

<span data-ttu-id="d45d0-198">Este exemplo mostra como criar várias sessões usando Secure Shell (SSH) e o conjunto de parâmetros **SSHConnection** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-198">This example shows how to create multiple sessions using Secure Shell (SSH) and the **SSHConnection** parameter set.</span></span> <span data-ttu-id="d45d0-199">O parâmetro **SSHConnection** usa uma matriz de tabelas de hash que contêm informações de conexão para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-199">The **SSHConnection** parameter takes an array of hash tables that contain connection information for each session.</span></span> <span data-ttu-id="d45d0-200">Observe que este exemplo requer que os computadores remotos de destino tenham o SSH configurado para dar suporte à autenticação de usuário baseada em chave.</span><span class="sxs-lookup"><span data-stu-id="d45d0-200">Note that this example requires that the target remote computers have SSH configured to support key based user authentication.</span></span>

## <span data-ttu-id="d45d0-201">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d45d0-201">PARAMETERS</span></span>

### <span data-ttu-id="d45d0-202">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="d45d0-202">-AllowRedirection</span></span>

<span data-ttu-id="d45d0-203">Indica que esse cmdlet permite o redirecionamento dessa conexão para um Uniform Resource Identifier alternativo (URI).</span><span class="sxs-lookup"><span data-stu-id="d45d0-203">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="d45d0-204">Quando você usa o parâmetro **ConnectionURI** , o destino remoto pode retornar uma instrução para redirecionar para um URI diferente.</span><span class="sxs-lookup"><span data-stu-id="d45d0-204">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="d45d0-205">Por padrão, o PowerShell não redireciona conexões, mas você pode usar esse parâmetro para habilitá-la a redirecionar a conexão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-205">By default, PowerShell does not redirect connections, but you can use this parameter to enable it to redirect the connection.</span></span>

<span data-ttu-id="d45d0-206">É possível também limitar o número de vezes que a conexão é redirecionada alterando o valor da opção de sessão **MaximumConnectionRedirectionCount** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-206">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="d45d0-207">Use o parâmetro **MaximumRedirection** do `New-PSSessionOption` cmdlet ou defina a propriedade **MaximumConnectionRedirectionCount** da variável de preferência **$PSSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-207">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span> <span data-ttu-id="d45d0-208">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="d45d0-208">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-209">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="d45d0-209">-ApplicationName</span></span>

<span data-ttu-id="d45d0-210">Especifica o segmento de nome de aplicativo do URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-210">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="d45d0-211">Use esse parâmetro para especificar o nome do aplicativo quando não estiver usando o parâmetro **ConnectionURI** no comando.</span><span class="sxs-lookup"><span data-stu-id="d45d0-211">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="d45d0-212">O valor padrão é o valor da `$PSSessionApplicationName` variável de preferência no computador local.</span><span class="sxs-lookup"><span data-stu-id="d45d0-212">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="d45d0-213">Se esta variável de preferência não estiver definida, o valor padrão é WSMAN.</span><span class="sxs-lookup"><span data-stu-id="d45d0-213">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="d45d0-214">Esse valor é adequado para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="d45d0-214">This value is appropriate for most uses.</span></span> <span data-ttu-id="d45d0-215">Para obter mais informações, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d45d0-215">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="d45d0-216">O serviço WinRM usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-216">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="d45d0-217">O valor desse parâmetro deve corresponder ao valor da propriedade **URLPrefix** de um ouvinte no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-217">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-218">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="d45d0-218">-Authentication</span></span>

<span data-ttu-id="d45d0-219">Especifica o mecanismo usado para autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="d45d0-219">Specifies the mechanism that is used to authenticate the user's credentials.</span></span>
<span data-ttu-id="d45d0-220">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="d45d0-220">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d45d0-221">Padrão</span><span class="sxs-lookup"><span data-stu-id="d45d0-221">Default</span></span>
- <span data-ttu-id="d45d0-222">Básico</span><span class="sxs-lookup"><span data-stu-id="d45d0-222">Basic</span></span>
- <span data-ttu-id="d45d0-223">CredSSP</span><span class="sxs-lookup"><span data-stu-id="d45d0-223">Credssp</span></span>
- <span data-ttu-id="d45d0-224">Digest</span><span class="sxs-lookup"><span data-stu-id="d45d0-224">Digest</span></span>
- <span data-ttu-id="d45d0-225">Kerberos</span><span class="sxs-lookup"><span data-stu-id="d45d0-225">Kerberos</span></span>
- <span data-ttu-id="d45d0-226">Negotiate</span><span class="sxs-lookup"><span data-stu-id="d45d0-226">Negotiate</span></span>
- <span data-ttu-id="d45d0-227">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="d45d0-227">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="d45d0-228">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="d45d0-228">The default value is Default.</span></span>

<span data-ttu-id="d45d0-229">Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="d45d0-229">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="d45d0-230">A autenticação do Credential Security Support Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-230">Credential Security Support Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="d45d0-231">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="d45d0-231">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="d45d0-232">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="d45d0-232">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, Uri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-233">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="d45d0-233">-CertificateThumbprint</span></span>

<span data-ttu-id="d45d0-234">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="d45d0-234">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="d45d0-235">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="d45d0-235">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="d45d0-236">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="d45d0-236">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="d45d0-237">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="d45d0-237">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="d45d0-238">Para obter um certificado, use o `Get-Item` `Get-ChildItem` comando ou na unidade de certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="d45d0-238">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-239">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d45d0-239">-ComputerName</span></span>

<span data-ttu-id="d45d0-240">Especifica uma matriz de nomes de computadores.</span><span class="sxs-lookup"><span data-stu-id="d45d0-240">Specifies an array of names of computers.</span></span> <span data-ttu-id="d45d0-241">Esse cmdlet cria uma conexão persistente ( **PSSession** ) para o computador especificado.</span><span class="sxs-lookup"><span data-stu-id="d45d0-241">This cmdlet creates a persistent connection ( **PSSession** ) to the specified computer.</span></span> <span data-ttu-id="d45d0-242">Se você inserir vários nomes de computador, o `New-PSSession` criará vários objetos **PSSession** , um para cada computador.</span><span class="sxs-lookup"><span data-stu-id="d45d0-242">If you enter multiple computer names, `New-PSSession` creates multiple **PSSession** objects, one for each computer.</span></span> <span data-ttu-id="d45d0-243">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="d45d0-243">The default is the local computer.</span></span>

<span data-ttu-id="d45d0-244">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="d45d0-244">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span> <span data-ttu-id="d45d0-245">Para especificar o computador local, digite o nome do computador, localhost ou um ponto (.).</span><span class="sxs-lookup"><span data-stu-id="d45d0-245">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span> <span data-ttu-id="d45d0-246">Quando o computador está em um domínio diferente do usuário, é necessário o nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="d45d0-246">When the computer is in a different domain than the user, the fully qualified domain name is required.</span></span> <span data-ttu-id="d45d0-247">Também é possível canalizar um nome de computador, entre aspas, para `New-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="d45d0-247">You can also pipe a computer name, in quotation marks, to `New-PSSession`.</span></span>

<span data-ttu-id="d45d0-248">Para usar um endereço IP no valor do parâmetro **ComputerName** , o comando deve incluir o parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-248">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="d45d0-249">Além disso, o computador deve ser configurado para o transporte HTTPS ou o endereço IP do computador remoto deve ser incluído na lista WinRM TrustedHosts no computador local.</span><span class="sxs-lookup"><span data-stu-id="d45d0-249">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="d45d0-250">Para obter instruções sobre como adicionar um nome de computador à lista TrustedHosts, consulte "como adicionar um computador à lista de hosts confiáveis" em [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="d45d0-250">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="d45d0-251">Para incluir o computador local no valor do parâmetro **ComputerName** , inicie o Windows PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="d45d0-251">To include the local computer in the value of the **ComputerName** parameter, start Windows PowerShell by using the Run as administrator option.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-252">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="d45d0-252">-ConfigurationName</span></span>

<span data-ttu-id="d45d0-253">Especifica a configuração de sessão que é usada para a nova **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-253">Specifies the session configuration that is used for the new **PSSession** .</span></span>

<span data-ttu-id="d45d0-254">Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-254">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="d45d0-255">Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="d45d0-255">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="d45d0-256">A configuração da sessão para uma sessão está localizada no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-256">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="d45d0-257">Se a configuração de sessão especificada não existir no computador remoto, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="d45d0-257">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="d45d0-258">O valor padrão é o valor da `$PSSessionConfigurationName` variável de preferência no computador local.</span><span class="sxs-lookup"><span data-stu-id="d45d0-258">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="d45d0-259">Se esta variável de preferência não for definida, o padrão é Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d45d0-259">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="d45d0-260">Para obter mais informações, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d45d0-260">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri, VMId, VMName, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-261">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="d45d0-261">-ConnectionUri</span></span>

<span data-ttu-id="d45d0-262">Especifica um URI que define o ponto de extremidade de conexão para a sessão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-262">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="d45d0-263">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="d45d0-263">The URI must be fully qualified.</span></span> <span data-ttu-id="d45d0-264">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d45d0-264">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="d45d0-265">O valor padrão é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d45d0-265">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="d45d0-266">Se não especificar um **ConnectionURI** , poderá usar os parâmetros **UseSSL** , **ComputerName** , **Port** e **ApplicationName** para especificar os valores do **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-266">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="d45d0-267">Os valores válidos para o segmento Transport do URI são HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d45d0-267">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="d45d0-268">Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas de padrões: 80 para HTTP e 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d45d0-268">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="d45d0-269">Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d45d0-269">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="d45d0-270">Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.</span><span class="sxs-lookup"><span data-stu-id="d45d0-270">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: Uri
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-271">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="d45d0-271">-ContainerId</span></span>

<span data-ttu-id="d45d0-272">Especifica uma matriz de IDs de contêineres.</span><span class="sxs-lookup"><span data-stu-id="d45d0-272">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="d45d0-273">Esse cmdlet inicia uma sessão interativa com cada um dos contêineres especificados.</span><span class="sxs-lookup"><span data-stu-id="d45d0-273">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="d45d0-274">Use o `docker ps` comando para obter uma lista de IDs de contêiner.</span><span class="sxs-lookup"><span data-stu-id="d45d0-274">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="d45d0-275">Para obter mais informações, consulte a ajuda para o comando [Docker PS](https://docs.docker.com/engine/reference/commandline/ps/) .</span><span class="sxs-lookup"><span data-stu-id="d45d0-275">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-276">-Credential</span><span class="sxs-lookup"><span data-stu-id="d45d0-276">-Credential</span></span>

<span data-ttu-id="d45d0-277">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="d45d0-277">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="d45d0-278">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="d45d0-278">The default is the current user.</span></span>

<span data-ttu-id="d45d0-279">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d45d0-279">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="d45d0-280">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="d45d0-280">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="d45d0-281">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="d45d0-281">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="d45d0-282">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="d45d0-282">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-283">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="d45d0-283">-EnableNetworkAccess</span></span>

<span data-ttu-id="d45d0-284">Indica que esse cmdlet adiciona um token de segurança interativo a sessões de loopback.</span><span class="sxs-lookup"><span data-stu-id="d45d0-284">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="d45d0-285">O token interativo permite executar comandos na sessão de loopback que obtêm dados de outros computadores.</span><span class="sxs-lookup"><span data-stu-id="d45d0-285">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="d45d0-286">Por exemplo, você pode executar um comando na sessão que copia arquivos XML de um computador remoto no computador local.</span><span class="sxs-lookup"><span data-stu-id="d45d0-286">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="d45d0-287">Uma sessão de loopback é uma **PSSession** originada e termina no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="d45d0-287">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="d45d0-288">Para criar uma sessão de loopback, omita o parâmetro **ComputerName** ou defina seu valor como ponto (.), localhost ou o nome do computador local.</span><span class="sxs-lookup"><span data-stu-id="d45d0-288">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (.), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="d45d0-289">Por padrão, esse cmdlet cria sessões de loopback usando um token de rede, que pode não fornecer permissão suficiente para autenticar em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="d45d0-289">By default, this cmdlet creates loopback sessions by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="d45d0-290">O parâmetro **EnableNetworkAccess** só é eficaz em sessões de loopback.</span><span class="sxs-lookup"><span data-stu-id="d45d0-290">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="d45d0-291">Se você usar **EnableNetworkAccess** ao criar uma sessão em um computador remoto, o comando terá sucesso, mas o parâmetro será ignorado.</span><span class="sxs-lookup"><span data-stu-id="d45d0-291">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="d45d0-292">Você também pode habilitar o acesso remoto em uma sessão de loopback usando o valor CredSSP do parâmetro de **autenticação** , que delega as credenciais de sessão para outros computadores.</span><span class="sxs-lookup"><span data-stu-id="d45d0-292">You can also enable remote access in a loopback session by using the CredSSP value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="d45d0-293">Para proteger o computador contra acesso mal-intencionado, as sessões de loopback desconectadas que têm tokens interativos, que são aquelas criadas usando o parâmetro **EnableNetworkAccess** , podem ser reconectadas somente do computador no qual a sessão foi criada.</span><span class="sxs-lookup"><span data-stu-id="d45d0-293">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="d45d0-294">Sessões desconectadas que usam a autenticação CredSSP podem ser reconectadas por meio de outros computadores.</span><span class="sxs-lookup"><span data-stu-id="d45d0-294">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="d45d0-295">Para obter mais informações, consulte `Disconnect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="d45d0-295">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="d45d0-296">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d45d0-296">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri, Session
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-297">-HostName</span><span class="sxs-lookup"><span data-stu-id="d45d0-297">-HostName</span></span>

<span data-ttu-id="d45d0-298">Especifica uma matriz de nomes de computador para uma conexão baseada em Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="d45d0-298">Specifies an array of computer names for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="d45d0-299">Isso é semelhante ao parâmetro ComputerName, exceto pelo fato de que a conexão com o computador remoto é feita usando SSH em vez de WinRM do Windows.</span><span class="sxs-lookup"><span data-stu-id="d45d0-299">This is similar to the ComputerName parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span>

<span data-ttu-id="d45d0-300">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="d45d0-300">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-301">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="d45d0-301">-KeyFilePath</span></span>

<span data-ttu-id="d45d0-302">Especifica um caminho de arquivo de chave usado pelo Secure Shell (SSH) para autenticar um usuário em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-302">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="d45d0-303">O SSH permite que a autenticação do usuário seja executada por meio de chaves privadas/públicas como uma alternativa à autenticação básica de senha.</span><span class="sxs-lookup"><span data-stu-id="d45d0-303">SSH allows user authentication to be performed via private/public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="d45d0-304">Se o computador remoto estiver configurado para autenticação de chave, esse parâmetro poderá ser usado para fornecer a chave que identifica o usuário.</span><span class="sxs-lookup"><span data-stu-id="d45d0-304">If the remote computer is configured for key authentication then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="d45d0-305">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="d45d0-305">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-306">-Name</span><span class="sxs-lookup"><span data-stu-id="d45d0-306">-Name</span></span>

<span data-ttu-id="d45d0-307">Especifica um nome amigável para a **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-307">Specifies a friendly name for the **PSSession** .</span></span>

<span data-ttu-id="d45d0-308">Você pode usar o nome para se referir à **PSSession** quando usar outros cmdlets, como `Get-PSSession` e `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="d45d0-308">You can use the name to refer to the **PSSession** when you use other cmdlets, such as `Get-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="d45d0-309">Não é necessário que o nome do computador ou da sessão atual seja exclusivo.</span><span class="sxs-lookup"><span data-stu-id="d45d0-309">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-310">-Port</span><span class="sxs-lookup"><span data-stu-id="d45d0-310">-Port</span></span>

<span data-ttu-id="d45d0-311">Especifica a porta de rede no computador remoto que é usada para esta conexão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-311">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="d45d0-312">Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-312">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="d45d0-313">As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d45d0-313">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="d45d0-314">Antes de usar outra porta, você deve configurar o ouvinte do WinRM no computador remoto para escutar nessa porta.</span><span class="sxs-lookup"><span data-stu-id="d45d0-314">Before using another port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="d45d0-315">Use os seguintes comandos para configurar o ouvinte:</span><span class="sxs-lookup"><span data-stu-id="d45d0-315">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="d45d0-316">Não use o parâmetro **Port** a menos que seja necessário.</span><span class="sxs-lookup"><span data-stu-id="d45d0-316">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="d45d0-317">A configuração da porta no comando se aplica a todos os computadores ou sessões em que o comando for executado.</span><span class="sxs-lookup"><span data-stu-id="d45d0-317">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="d45d0-318">Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="d45d0-318">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-319">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d45d0-319">-RunAsAdministrator</span></span>

<span data-ttu-id="d45d0-320">Indica que a **PSSession** é executada como administrador.</span><span class="sxs-lookup"><span data-stu-id="d45d0-320">Indicates that the **PSSession** runs as administrator.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-321">-Sessão</span><span class="sxs-lookup"><span data-stu-id="d45d0-321">-Session</span></span>

<span data-ttu-id="d45d0-322">Especifica uma matriz de objetos **PSSession** que esse cmdlet usa como um modelo para a nova **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-322">Specifies an array of **PSSession** objects that this cmdlet uses as a model for the new **PSSession** .</span></span> <span data-ttu-id="d45d0-323">Esse parâmetro cria novos objetos **PSSession** que têm as mesmas propriedades que os objetos **PSSession** especificados.</span><span class="sxs-lookup"><span data-stu-id="d45d0-323">This parameter creates new **PSSession** objects that have the same properties as the specified **PSSession** objects.</span></span>

<span data-ttu-id="d45d0-324">Insira uma variável que contém os objetos **PSSession** ou um comando que cria ou obtém os objetos **PSSession** , como um `New-PSSession` comando ou `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="d45d0-324">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="d45d0-325">Os objetos **PSSession** resultantes têm o mesmo nome do computador, nome do aplicativo, URI de conexão, porta, nome de configuração, limite de limitação e valor de protocolo SSL (SSL) como os originais, mas têm um nome de exibição diferente, ID e ID de instância (GUID).</span><span class="sxs-lookup"><span data-stu-id="d45d0-325">The resulting **PSSession** objects have the same computer name, application name, connection URI, port, configuration name, throttle limit, and Secure Sockets Layer (SSL) value as the originals, but they have a different display name, ID, and instance ID (GUID).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-326">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="d45d0-326">-SessionOption</span></span>

<span data-ttu-id="d45d0-327">Especifica as opções avançadas para a sessão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-327">Specifies advanced options for the session.</span></span> <span data-ttu-id="d45d0-328">Insira um objeto **SessionOption** , como um que você cria usando o `New-PSSessionOption` cmdlet ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-328">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="d45d0-329">Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se estiver definido.</span><span class="sxs-lookup"><span data-stu-id="d45d0-329">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="d45d0-330">Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-330">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="d45d0-331">Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-331">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="d45d0-332">No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-332">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="d45d0-333">Para obter uma descrição das opções de sessão que incluem os valores padrão, consulte `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="d45d0-333">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="d45d0-334">Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d45d0-334">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="d45d0-335">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d45d0-335">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-336">-SSHConnection</span><span class="sxs-lookup"><span data-stu-id="d45d0-336">-SSHConnection</span></span>

<span data-ttu-id="d45d0-337">Esse parâmetro usa uma matriz de Hashtables em que cada Hashtable contém um ou mais parâmetros de conexão necessários para estabelecer uma conexão de Secure Shell (SSH) (nome do host, porta, nome de usuário, keyFilePath).</span><span class="sxs-lookup"><span data-stu-id="d45d0-337">This parameter takes an array of hashtables where each hashtable contains one or more connection parameters needed to establish a Secure Shell (SSH) connection (HostName, Port, UserName, KeyFilePath).</span></span>

<span data-ttu-id="d45d0-338">Os parâmetros de conexão da tabela de hash são os mesmos definidos para o conjunto de parâmetros **hostname** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-338">The hashtable connection parameters are the same as defined for the **HostName** parameter set.</span></span>

<span data-ttu-id="d45d0-339">O parâmetro **SSHConnection** é útil para criar várias sessões em que cada sessão requer informações de conexão diferentes.</span><span class="sxs-lookup"><span data-stu-id="d45d0-339">The **SSHConnection** parameter is useful for creating multiple sessions where each session requires different connection information.</span></span>

<span data-ttu-id="d45d0-340">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="d45d0-340">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SSHHostHashParam
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-341">-SSHTransport</span><span class="sxs-lookup"><span data-stu-id="d45d0-341">-SSHTransport</span></span>

<span data-ttu-id="d45d0-342">Indica que a conexão remota é estabelecida usando Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="d45d0-342">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="d45d0-343">Por padrão, o PowerShell usa o Windows WinRM para se conectar a um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-343">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="d45d0-344">Essa opção força o PowerShell a usar o parâmetro HostName definido para estabelecer uma conexão remota com base em SSH.</span><span class="sxs-lookup"><span data-stu-id="d45d0-344">This switch forces PowerShell to use the HostName parameter set for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="d45d0-345">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="d45d0-345">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-346">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="d45d0-346">-ThrottleLimit</span></span>

<span data-ttu-id="d45d0-347">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="d45d0-347">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="d45d0-348">Se você omitir esse parâmetro ou digitar o valor 0 (zero), o valor padrão, 32, será usado.</span><span class="sxs-lookup"><span data-stu-id="d45d0-348">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span>

<span data-ttu-id="d45d0-349">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="d45d0-349">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, Uri, VMId, VMName, Session, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-350">-UserName</span><span class="sxs-lookup"><span data-stu-id="d45d0-350">-UserName</span></span>

<span data-ttu-id="d45d0-351">Especifica o nome de usuário para a conta usada para criar uma sessão no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-351">Specifies the user name for the account used to create a session on the remote computer.</span></span> <span data-ttu-id="d45d0-352">O método de autenticação de usuário dependerá de como o Secure Shell (SSH) está configurado no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-352">User authentication method will depend on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="d45d0-353">Se o SSH estiver configurado para autenticação de senha básica, você será solicitado a fornecer a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="d45d0-353">If SSH is configured for basic password authentication then you will be prompted for the user password.</span></span>

<span data-ttu-id="d45d0-354">Se o SSH estiver configurado para a autenticação de usuário baseada em chave, um caminho de arquivo de chave poderá ser fornecido por meio do parâmetro keyFilePath e nenhum prompt de senha ocorrerá.</span><span class="sxs-lookup"><span data-stu-id="d45d0-354">If SSH is configured for key based user authentication then a key file path can be provided via the KeyFilePath parameter and no password prompt will occur.</span></span> <span data-ttu-id="d45d0-355">Observe que, se o arquivo de chave de usuário do cliente estiver localizado em um local de SSH conhecido, o parâmetro keyFilePath não será necessário para a autenticação baseada em chave e a autenticação do usuário ocorrerá automaticamente com base no nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="d45d0-355">Note that if the client user key file is located in an SSH known location then the KeyFilePath parameter is not needed for key based authentication, and user authentication will occur automatically based on the user name.</span></span> <span data-ttu-id="d45d0-356">Consulte a documentação do SSH sobre autenticação de usuário baseada em chave para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d45d0-356">See SSH documentation about key based user authentication for more information.</span></span>

<span data-ttu-id="d45d0-357">Esse não é um parâmetro obrigatório.</span><span class="sxs-lookup"><span data-stu-id="d45d0-357">This is not a required parameter.</span></span> <span data-ttu-id="d45d0-358">Se nenhum parâmetro UserName for especificado, o nome de usuário do logon atual será usado para a conexão.</span><span class="sxs-lookup"><span data-stu-id="d45d0-358">If no UserName parameter is specified then the current log on user name is used for the connection.</span></span>

<span data-ttu-id="d45d0-359">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="d45d0-359">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-360">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="d45d0-360">-UseSSL</span></span>

<span data-ttu-id="d45d0-361">Indica que esse cmdlet usa o protocolo SSL para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d45d0-361">Indicates that this cmdlet uses the SSL protocol to establish a connection to the remote computer.</span></span>
<span data-ttu-id="d45d0-362">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="d45d0-362">By default, SSL is not used.</span></span>

<span data-ttu-id="d45d0-363">WS-Management criptografa todo o conteúdo do PowerShell transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="d45d0-363">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="d45d0-364">O parâmetro **UseSSL** oferece uma proteção adicional que envia os dados por uma conexão HTTPS em vez de uma conexão http.</span><span class="sxs-lookup"><span data-stu-id="d45d0-364">The **UseSSL** parameter offers an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="d45d0-365">Se você usar esse parâmetro, mas o SSL não estiver disponível na porta usada para o comando, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="d45d0-365">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-366">-VMId</span><span class="sxs-lookup"><span data-stu-id="d45d0-366">-VMId</span></span>

<span data-ttu-id="d45d0-367">Especifica uma matriz de ID de máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="d45d0-367">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="d45d0-368">Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas.</span><span class="sxs-lookup"><span data-stu-id="d45d0-368">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="d45d0-369">Para ver as máquinas virtuais que estão disponíveis para você, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d45d0-369">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-370">-VMName</span><span class="sxs-lookup"><span data-stu-id="d45d0-370">-VMName</span></span>

<span data-ttu-id="d45d0-371">Especifica uma matriz de nomes de máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="d45d0-371">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="d45d0-372">Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas.</span><span class="sxs-lookup"><span data-stu-id="d45d0-372">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="d45d0-373">Para ver as máquinas virtuais que estão disponíveis para você, use o `Get-VM` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d45d0-373">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-374">-Subsistema</span><span class="sxs-lookup"><span data-stu-id="d45d0-374">-Subsystem</span></span>

<span data-ttu-id="d45d0-375">Especifica o subsistema SSH usado para a nova **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d45d0-375">Specifies the SSH subsystem used for the new **PSSession** .</span></span>

<span data-ttu-id="d45d0-376">Isso especifica o subsistema a ser usado no destino, conforme definido em sshd_config.</span><span class="sxs-lookup"><span data-stu-id="d45d0-376">This specifies the subsystem to use on the target as defined in sshd_config.</span></span>
<span data-ttu-id="d45d0-377">O subsistema inicia uma versão específica do PowerShell com parâmetros predefinidos.</span><span class="sxs-lookup"><span data-stu-id="d45d0-377">The subsystem starts a specific version of PowerShell with predefined parameters.</span></span>
<span data-ttu-id="d45d0-378">Se o subsistema especificado não existir no computador remoto, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="d45d0-378">If the specified subsystem does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="d45d0-379">Se esse parâmetro não for usado, o padrão será o subsistema ' PowerShell '.</span><span class="sxs-lookup"><span data-stu-id="d45d0-379">If this parameter is not used, the default is the 'powershell' subsystem.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-380">-UseWindowsPowerShell</span><span class="sxs-lookup"><span data-stu-id="d45d0-380">-UseWindowsPowerShell</span></span>

<span data-ttu-id="d45d0-381">{{Descrição de UseWindowsPowerShell de preenchimento}}</span><span class="sxs-lookup"><span data-stu-id="d45d0-381">{{ Fill UseWindowsPowerShell Description }}</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseWindowsPowerShellParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d45d0-382">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d45d0-382">CommonParameters</span></span>

<span data-ttu-id="d45d0-383">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d45d0-383">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d45d0-384">Para obter mais informações, confira about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d45d0-384">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d45d0-385">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d45d0-385">INPUTS</span></span>

### <span data-ttu-id="d45d0-386">System. String, System. URI, System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="d45d0-386">System.String, System.URI, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="d45d0-387">É possível canalizar uma cadeia de caracteres, um URI ou um objeto de sessão para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d45d0-387">You can pipe a string, URI, or session object to this cmdlet.</span></span>

## <span data-ttu-id="d45d0-388">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d45d0-388">OUTPUTS</span></span>

### <span data-ttu-id="d45d0-389">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="d45d0-389">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="d45d0-390">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d45d0-390">NOTES</span></span>

- <span data-ttu-id="d45d0-391">Esse cmdlet usa a infraestrutura de comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d45d0-391">This cmdlet uses the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="d45d0-392">Para usar esse cmdlet, o computador local e os computadores remotos devem ser configurados para a comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d45d0-392">To use this cmdlet, the local computer and any remote computers must be configured for PowerShell remoting.</span></span> <span data-ttu-id="d45d0-393">Para obter mais informações, consulte [about_Remote_Requirements](About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d45d0-393">For more information, see [about_Remote_Requirements](About/about_Remote_Requirements.md).</span></span>
- <span data-ttu-id="d45d0-394">Para criar uma **PSSession** no computador local, inicie o PowerShell com a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="d45d0-394">To create a **PSSession** on the local computer, start PowerShell with the Run as administrator option.</span></span>
- <span data-ttu-id="d45d0-395">Quando você terminar com a **PSSession** , use o `Remove-PSSession` cmdlet para excluir a **PSSession** e liberar seus recursos.</span><span class="sxs-lookup"><span data-stu-id="d45d0-395">When you are finished with the **PSSession** , use the `Remove-PSSession` cmdlet to delete the **PSSession** and release its resources.</span></span>
- <span data-ttu-id="d45d0-396">Os conjuntos de parâmetros **hostname** e **SSHConnection** foram incluídos a partir do PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="d45d0-396">The **HostName** and **SSHConnection** parameter sets were included starting with PowerShell 6.0.</span></span>
  <span data-ttu-id="d45d0-397">Elas foram adicionadas para fornecer comunicação remota do PowerShell com base em Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="d45d0-397">They were added to provide PowerShell remoting based on Secure Shell (SSH).</span></span> <span data-ttu-id="d45d0-398">Tanto o SSH quanto o PowerShell têm suporte em várias plataformas (Windows, Linux, macOS) e a comunicação remota do PowerShell funcionará nessas plataformas nas quais o PowerShell e o SSH estão instalados e configurados.</span><span class="sxs-lookup"><span data-stu-id="d45d0-398">Both SSH and PowerShell are supported on multiple platforms (Windows, Linux, macOS) and PowerShell remoting will work over these platforms where PowerShell and SSH are installed and configured.</span></span> <span data-ttu-id="d45d0-399">Isso é separado da somente comunicação remota do Windows anterior, que é baseada no WinRM, e que muitos dos recursos e limitações específicos do WinRM não se aplicam.</span><span class="sxs-lookup"><span data-stu-id="d45d0-399">This is separate from the previous Windows only remoting that is based on WinRM and much of the WinRM specific features and limitations do not apply.</span></span> <span data-ttu-id="d45d0-400">Por exemplo, cotas baseadas em WinRM, opções de sessão, configuração de ponto de extremidade personalizado e recursos de desconexão/reconexão não têm suporte no momento.</span><span class="sxs-lookup"><span data-stu-id="d45d0-400">For example WinRM based quotas, session options, custom endpoint configuration, and disconnect/reconnect features are currently not supported.</span></span> <span data-ttu-id="d45d0-401">Para obter mais informações sobre como configurar a comunicação remota do PowerShell SSH, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="d45d0-401">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <span data-ttu-id="d45d0-402">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d45d0-402">RELATED LINKS</span></span>

[<span data-ttu-id="d45d0-403">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="d45d0-403">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="d45d0-404">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="d45d0-404">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="d45d0-405">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="d45d0-405">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="d45d0-406">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="d45d0-406">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="d45d0-407">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="d45d0-407">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="d45d0-408">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="d45d0-408">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="d45d0-409">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="d45d0-409">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="d45d0-410">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="d45d0-410">Remove-PSSession</span></span>](Remove-PSSession.md)

