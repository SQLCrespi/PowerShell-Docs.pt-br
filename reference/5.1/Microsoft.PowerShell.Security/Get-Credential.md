---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 26c4f8c8dcc1fbd56e29f55a6a8c2e6aa37a2842
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "93196635"
---
# <span data-ttu-id="429f9-103">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="429f9-103">Get-Credential</span></span>

## <span data-ttu-id="429f9-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="429f9-104">SYNOPSIS</span></span>
<span data-ttu-id="429f9-105">Obtém um objeto de credencial com base em um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="429f9-105">Gets a credential object based on a user name and password.</span></span>

## <span data-ttu-id="429f9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="429f9-106">SYNTAX</span></span>

### <span data-ttu-id="429f9-107">Credentialset (padrão)</span><span class="sxs-lookup"><span data-stu-id="429f9-107">CredentialSet (Default)</span></span>

```
Get-Credential [-Credential] <PSCredential> [<CommonParameters>]
```

### <span data-ttu-id="429f9-108">Mensagem de</span><span class="sxs-lookup"><span data-stu-id="429f9-108">MessageSet</span></span>

```
Get-Credential -Message <String> [[-UserName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="429f9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="429f9-109">DESCRIPTION</span></span>

<span data-ttu-id="429f9-110">O `Get-Credential` cmdlet cria um objeto de credencial para um nome de usuário e senha especificados.</span><span class="sxs-lookup"><span data-stu-id="429f9-110">The `Get-Credential` cmdlet creates a credential object for a specified user name and password.</span></span> <span data-ttu-id="429f9-111">É possível utilizar o objeto de credencial em operações de segurança.</span><span class="sxs-lookup"><span data-stu-id="429f9-111">You can use the credential object in security operations.</span></span>

<span data-ttu-id="429f9-112">A partir do PowerShell 3,0, você pode usar o parâmetro **Message** para especificar uma mensagem personalizada na caixa de diálogo que solicita ao usuário seu nome e senha.</span><span class="sxs-lookup"><span data-stu-id="429f9-112">Beginning in PowerShell 3.0, you can use the **Message** parameter to specify a customized message on the dialog box that prompts the user for their name and password.</span></span>

<span data-ttu-id="429f9-113">O `Get-Credential` cmdlet solicita ao usuário uma senha ou um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="429f9-113">The `Get-Credential` cmdlet prompts the user for a password or a user name and password.</span></span> <span data-ttu-id="429f9-114">Por padrão, aparecerá uma caixa de diálogo de autenticação para solicitar o usuário.</span><span class="sxs-lookup"><span data-stu-id="429f9-114">By default, an authentication dialog box appears to prompt the user.</span></span> <span data-ttu-id="429f9-115">No entanto, em alguns programas de host, como o console do PowerShell, você pode solicitar o usuário na linha de comando alterando uma entrada de registro.</span><span class="sxs-lookup"><span data-stu-id="429f9-115">However, in some host programs, such as the PowerShell console, you can prompt the user at the command line by changing a registry entry.</span></span> <span data-ttu-id="429f9-116">Para obter mais informações sobre essa entrada do registro, consulte as observações e os exemplos.</span><span class="sxs-lookup"><span data-stu-id="429f9-116">For more information about this registry entry, see the notes and examples.</span></span>

## <span data-ttu-id="429f9-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="429f9-117">EXAMPLES</span></span>

### <span data-ttu-id="429f9-118">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="429f9-118">Example 1</span></span>

```powershell
$c = Get-Credential
```

<span data-ttu-id="429f9-119">Esse comando obtém um objeto de credencial e o salva na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="429f9-119">This command gets a credential object and saves it in the `$c` variable.</span></span>

<span data-ttu-id="429f9-120">Ao digita o comando, será exibida uma caixa de diálogo solicitando um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="429f9-120">When you enter the command, a dialog box appears requesting a user name and password.</span></span> <span data-ttu-id="429f9-121">Quando você insere as informações solicitadas, o cmdlet cria um objeto **PSCredential** que representa as credenciais do usuário e salva-o na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="429f9-121">When you enter the requested information, the cmdlet creates a **PSCredential** object representing the credentials of the user and saves it in the `$c` variable.</span></span>

<span data-ttu-id="429f9-122">É possível utilizar o objeto como entrada para os cmdlets que exigem autenticação de usuário, como aqueles com um parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="429f9-122">You can use the object as input to cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span> <span data-ttu-id="429f9-123">No entanto, alguns provedores instalados com o PowerShell não oferecem suporte ao parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="429f9-123">However, some providers that are installed with PowerShell do not support the **Credential** parameter.</span></span>

### <span data-ttu-id="429f9-124">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="429f9-124">Example 2</span></span>

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

<span data-ttu-id="429f9-125">Esses comandos usam um objeto Credential que o `Get-Credential` cmdlet retorna para autenticar um usuário em um computador remoto para que eles possam usar o Instrumentação de gerenciamento do Windows (WMI) para gerenciar o computador.</span><span class="sxs-lookup"><span data-stu-id="429f9-125">These commands use a credential object that the `Get-Credential` cmdlet returns to authenticate a user on a remote computer so they can use Windows Management Instrumentation (WMI) to manage the computer.</span></span>

<span data-ttu-id="429f9-126">O primeiro comando obtém um objeto de credencial e o salva na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="429f9-126">The first command gets a credential object and saves it in the `$c` variable.</span></span> <span data-ttu-id="429f9-127">O segundo comando usa o objeto Credential em um `Get-CimInstance` comando.</span><span class="sxs-lookup"><span data-stu-id="429f9-127">The second command uses the credential object in a `Get-CimInstance` command.</span></span> <span data-ttu-id="429f9-128">Esse comando obtém informações sobre as unidades de disco no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="429f9-128">This command gets information about the disk drives on the Server01 computer.</span></span>

### <span data-ttu-id="429f9-129">Exemplo 3:</span><span class="sxs-lookup"><span data-stu-id="429f9-129">Example 3</span></span>

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

<span data-ttu-id="429f9-130">Este comando mostra como incluir um `Get-Credential` comando em um  `Get-CimInstance` comando.</span><span class="sxs-lookup"><span data-stu-id="429f9-130">This command shows how to include a `Get-Credential` command in a  `Get-CimInstance` command.</span></span>

<span data-ttu-id="429f9-131">Esse comando usa o `Get-CimInstance` cmdlet para obter informações sobre o BIOS no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="429f9-131">This command uses the `Get-CimInstance` cmdlet to get information about the BIOS on the Server01 computer.</span></span> <span data-ttu-id="429f9-132">Ele usa o parâmetro **Credential** para autenticar o usuário, Domínio01 \ Usuário01 e um `Get-Credential` comando como o valor do parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="429f9-132">It uses the **Credential** parameter to authenticate the user, Domain01\User01, and a `Get-Credential` command as the value of the **Credential** parameter.</span></span>

### <span data-ttu-id="429f9-133">Exemplo 4</span><span class="sxs-lookup"><span data-stu-id="429f9-133">Example 4</span></span>

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

<span data-ttu-id="429f9-134">Este exemplo cria uma credencial que inclui um nome de usuário sem um nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="429f9-134">This example creates a credential that includes a user name without a domain name.</span></span>

<span data-ttu-id="429f9-135">O primeiro comando obtém uma credencial com o nome de usuário User01 e a armazena na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="429f9-135">The first command gets a credential with the user name User01 and stores it in the `$c` variable.</span></span>
<span data-ttu-id="429f9-136">O segundo comando exibe o valor da propriedade **Username** do objeto de credencial resultante.</span><span class="sxs-lookup"><span data-stu-id="429f9-136">The second command displays the value of the **Username** property of the resulting credential object.</span></span>

### <span data-ttu-id="429f9-137">Exemplo 5</span><span class="sxs-lookup"><span data-stu-id="429f9-137">Example 5</span></span>

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

<span data-ttu-id="429f9-138">Este comando utiliza o método **PromptForCredential** para solicitar ao usuário seu nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="429f9-138">This command uses the **PromptForCredential** method to prompt the user for their user name and password.</span></span> <span data-ttu-id="429f9-139">O comando salva as credenciais resultantes na `$Credential` variável.</span><span class="sxs-lookup"><span data-stu-id="429f9-139">The command saves the resulting credentials in the `$Credential` variable.</span></span>

<span data-ttu-id="429f9-140">O método **PromptForCredential** é uma alternativa ao uso do `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="429f9-140">The **PromptForCredential** method is an alternative to using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="429f9-141">Ao utilizar o **PromptForCredential** , é possível especificar a legenda, mensagens e nome de usuário que aparecem na caixa de mensagem.</span><span class="sxs-lookup"><span data-stu-id="429f9-141">When you use **PromptForCredential** , you can specify the caption, messages, and user name that appear in the message box.</span></span>

<span data-ttu-id="429f9-142">Para obter mais informações, consulte a documentação do [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) no SDK.</span><span class="sxs-lookup"><span data-stu-id="429f9-142">For more information, see the [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) documentation in the SDK.</span></span>

### <span data-ttu-id="429f9-143">Exemplo 6</span><span class="sxs-lookup"><span data-stu-id="429f9-143">Example 6</span></span>

```powershell
Set-ItemProperty "HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds" -Name ConsolePrompting -Value $true
```

<span data-ttu-id="429f9-144">Este exemplo mostra como modificar o registro para que o usuário seja solicitado na linha de comando, em vez de por meio de uma caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="429f9-144">This example shows how to modify the registry so that the user is prompted at the command line, instead of by using a dialog box.</span></span>

<span data-ttu-id="429f9-145">O comando cria a entrada do registro **ConsolePrompting** e define seu valor como True.</span><span class="sxs-lookup"><span data-stu-id="429f9-145">The command creates the **ConsolePrompting** registry entry and sets its value to True.</span></span> <span data-ttu-id="429f9-146">Para executar esse comando, inicie o PowerShell com a opção "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="429f9-146">To run this command, start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="429f9-147">Para usar uma caixa de diálogo para solicitação, defina o valor de ConsolePrompting como false ($false) ou use o `Remove-ItemProperty` cmdlet para excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="429f9-147">To use a dialog box for prompting, set the value of the ConsolePrompting to false ($false) or use the `Remove-ItemProperty` cmdlet to delete it.</span></span>

<span data-ttu-id="429f9-148">A entrada do registro ConsolePrompting funciona em alguns programas de host, como o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="429f9-148">The ConsolePrompting registry entry works in some host programs, such as the PowerShell console.</span></span> <span data-ttu-id="429f9-149">Ela pode não funcionar em todos os programas de host.</span><span class="sxs-lookup"><span data-stu-id="429f9-149">It might not work in all host programs.</span></span>

### <span data-ttu-id="429f9-150">Exemplo 7</span><span class="sxs-lookup"><span data-stu-id="429f9-150">Example 7</span></span>

<span data-ttu-id="429f9-151">Este exemplo mostra como criar um objeto de credencial que seja idêntico ao objeto que `Get-Credential` retorna sem avisar o usuário.</span><span class="sxs-lookup"><span data-stu-id="429f9-151">This example shows how to create a credential object that is identical to the object that `Get-Credential` returns without prompting the user.</span></span> <span data-ttu-id="429f9-152">Este método requer uma senha de texto sem formatação, que pode violar os padrões de segurança em algumas empresas.</span><span class="sxs-lookup"><span data-stu-id="429f9-152">This method requires a plain text password, which might violate the security standards in some enterprises.</span></span>

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

<span data-ttu-id="429f9-153">O primeiro comando salva o nome da conta de usuário no `$User` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="429f9-153">The first command saves the user account name in the `$User` parameter.</span></span> <span data-ttu-id="429f9-154">O valor deve ter o formato "Domain\User" ou "ComputerName\User".</span><span class="sxs-lookup"><span data-stu-id="429f9-154">The value must have the "Domain\User" or "ComputerName\User" format.</span></span>

<span data-ttu-id="429f9-155">O segundo comando usa o `ConvertTo-SecureString` cmdlet para criar uma cadeia de caracteres segura de uma senha de texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="429f9-155">The second command uses the `ConvertTo-SecureString` cmdlet to create a secure string from a plain text password.</span></span> <span data-ttu-id="429f9-156">O comando utiliza o parâmetro **AsPlainText** para indicar que a cadeia de caracteres de texto está sem formatação e o parâmetro **Force** para confirmar que você compreende os riscos do uso de texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="429f9-156">The command uses the **AsPlainText** parameter to indicate that the string is plain text and the **Force** parameter to confirm that you understand the risks of using plain text.</span></span>

<span data-ttu-id="429f9-157">O terceiro comando usa o `New-Object` cmdlet para criar um objeto **PSCredential** com base nos valores nas `$User` `$PWord` variáveis e.</span><span class="sxs-lookup"><span data-stu-id="429f9-157">The third command uses the `New-Object` cmdlet to create a **PSCredential** object from the values in the `$User` and `$PWord` variables.</span></span>

### <span data-ttu-id="429f9-158">Exemplo 8</span><span class="sxs-lookup"><span data-stu-id="429f9-158">Example 8</span></span>

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

<span data-ttu-id="429f9-159">Esse comando usa os parâmetros de **mensagem** e **nome de usuário** do `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="429f9-159">This command uses the **Message** and **UserName** parameters of the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="429f9-160">Esse formato de comando destina-se a funções e scripts compartilhados.</span><span class="sxs-lookup"><span data-stu-id="429f9-160">This command format is designed for shared scripts and functions.</span></span> <span data-ttu-id="429f9-161">Nesse caso, a mensagem informa ao usuário porque as credenciais são necessárias e dá a eles confiança de que a solicitação é legítima.</span><span class="sxs-lookup"><span data-stu-id="429f9-161">In this case, the message tells the user why credentials are needed and gives them confidence that the request is legitimate.</span></span>

### <span data-ttu-id="429f9-162">Exemplo 9</span><span class="sxs-lookup"><span data-stu-id="429f9-162">Example 9</span></span>

```powershell
Invoke-Command -ComputerName Server01 {Get-Credential Domain01\User02}
```

```Output
PowerShell Credential Request : PowerShell Credential Request
Warning: This credential is being requested by a script or application on the SERVER01 remote computer. Enter your credentials only if you
 trust the remote computer and the application or script requesting it.

Enter your credentials.
Password for user Domain01\User02: ***************

PSComputerName     : Server01
RunspaceId         : 422bdf52-9886-4ada-ab2f-130497c6777f
PSShowComputerName : True
UserName           : Domain01\User01
Password           : System.Security.SecureString
```

<span data-ttu-id="429f9-163">Esse comando obtém uma credencial do computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="429f9-163">This command gets a credential from the Server01 remote computer.</span></span> <span data-ttu-id="429f9-164">O comando usa o `Invoke-Command` cmdlet para executar um `Get-Credential` comando no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="429f9-164">The command uses the `Invoke-Command` cmdlet to run a `Get-Credential` command on the remote computer.</span></span> <span data-ttu-id="429f9-165">A saída mostra a mensagem de segurança remota que `Get-Credential` inclui no prompt de autenticação.</span><span class="sxs-lookup"><span data-stu-id="429f9-165">The output shows the remote security message that `Get-Credential` includes in the authentication prompt.</span></span>

## <span data-ttu-id="429f9-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="429f9-166">PARAMETERS</span></span>

### <span data-ttu-id="429f9-167">-Credential</span><span class="sxs-lookup"><span data-stu-id="429f9-167">-Credential</span></span>

<span data-ttu-id="429f9-168">Especifica um nome de usuário para a credencial, como **User01** ou **Domínio01 \ Usuário01** .</span><span class="sxs-lookup"><span data-stu-id="429f9-168">Specifies a user name for the credential, such as **User01** or **Domain01\User01** .</span></span> <span data-ttu-id="429f9-169">O nome do parâmetro, `-Credential` , é opcional.</span><span class="sxs-lookup"><span data-stu-id="429f9-169">The parameter name, `-Credential`, is optional.</span></span>

<span data-ttu-id="429f9-170">Ao enviar o comando e especificar um nome de usuário, você será solicitado a fornecer uma senha.</span><span class="sxs-lookup"><span data-stu-id="429f9-170">When you submit the command and specify a user name, you're prompted for a password.</span></span> <span data-ttu-id="429f9-171">Se você omitir esse parâmetro, um nome de usuário e uma senha serão solicitados.</span><span class="sxs-lookup"><span data-stu-id="429f9-171">If you omit this parameter, you're prompted for a user name and a password.</span></span>

<span data-ttu-id="429f9-172">A partir do PowerShell 3,0, se você inserir um nome de usuário sem um domínio, `Get-Credential` o não inserirá mais uma barra invertida antes do nome.</span><span class="sxs-lookup"><span data-stu-id="429f9-172">Starting in PowerShell 3.0, if you enter a user name without a domain, `Get-Credential` no longer inserts a backslash before the name.</span></span>

<span data-ttu-id="429f9-173">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="429f9-173">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="429f9-174">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="429f9-174">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="429f9-175">-Mensagem</span><span class="sxs-lookup"><span data-stu-id="429f9-175">-Message</span></span>

<span data-ttu-id="429f9-176">Especifica uma mensagem que aparece no prompt de autenticação.</span><span class="sxs-lookup"><span data-stu-id="429f9-176">Specifies a message that appears in the authentication prompt.</span></span> <span data-ttu-id="429f9-177">Esse parâmetro é projetado para o uso em uma função ou script.</span><span class="sxs-lookup"><span data-stu-id="429f9-177">This parameter is designed for use in a function or script.</span></span> <span data-ttu-id="429f9-178">É possível utilizar a mensagem para explicar ao usuário por que você está solicitando credenciais e como elas serão utilizadas.</span><span class="sxs-lookup"><span data-stu-id="429f9-178">You can use the message to explain to the user why you are requesting credentials and how they will be used.</span></span>

<span data-ttu-id="429f9-179">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="429f9-179">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="429f9-180">-UserName</span><span class="sxs-lookup"><span data-stu-id="429f9-180">-UserName</span></span>

<span data-ttu-id="429f9-181">Especifica um nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="429f9-181">Specifies a user name.</span></span> <span data-ttu-id="429f9-182">O prompt de autenticação solicita uma senha para o nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="429f9-182">The authentication prompt requests a password for the user name.</span></span> <span data-ttu-id="429f9-183">Por padrão, o nome de usuário está em branco e o prompt de autenticação solicita um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="429f9-183">By default, the user name is blank and the authentication prompt requests both a user name and password.</span></span>

<span data-ttu-id="429f9-184">Quando o prompt de autenticação aparece em uma caixa de diálogo, o usuário pode editar o nome de usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="429f9-184">When the authentication prompt appears in a dialog box, the user can edit the specified user name.</span></span>
<span data-ttu-id="429f9-185">No entanto, o usuário não pode alterar o nome de usuário quando o prompt aparece na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="429f9-185">However, the user cannot change the user name when the prompt appears at the command line.</span></span> <span data-ttu-id="429f9-186">Ao usar esse parâmetro em uma função compartilhada ou um script, considere todas as apresentações possíveis.</span><span class="sxs-lookup"><span data-stu-id="429f9-186">When using this parameter in a shared function or script, consider all possible presentations.</span></span>

<span data-ttu-id="429f9-187">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="429f9-187">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: 1
Default value: None (blank)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="429f9-188">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="429f9-188">CommonParameters</span></span>

<span data-ttu-id="429f9-189">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="429f9-189">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="429f9-190">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="429f9-190">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="429f9-191">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="429f9-191">INPUTS</span></span>

### <span data-ttu-id="429f9-192">Nenhum</span><span class="sxs-lookup"><span data-stu-id="429f9-192">None</span></span>

<span data-ttu-id="429f9-193">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="429f9-193">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="429f9-194">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="429f9-194">OUTPUTS</span></span>

### <span data-ttu-id="429f9-195">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="429f9-195">System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="429f9-196">`Get-Credential` Retorna um objeto Credential.</span><span class="sxs-lookup"><span data-stu-id="429f9-196">`Get-Credential` returns a credential object.</span></span>

## <span data-ttu-id="429f9-197">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="429f9-197">NOTES</span></span>

<span data-ttu-id="429f9-198">Você pode usar o objeto **PSCredential** que `Get-Credential` cria em cmdlets que solicitam autenticação de usuário, como aqueles com um parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="429f9-198">You can use the **PSCredential** object that `Get-Credential` creates in cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span>

<span data-ttu-id="429f9-199">Por padrão, o prompt de autenticação aparece na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="429f9-199">By default, the authentication prompt appears in a dialog box.</span></span> <span data-ttu-id="429f9-200">Para exibir o prompt de autenticação na linha de comando, adicione a entrada do registro **ConsolePrompting** ( `HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\ConsolePrompting` ) e defina seu valor como **true** .</span><span class="sxs-lookup"><span data-stu-id="429f9-200">To display the authentication prompt at the command line, add the **ConsolePrompting** registry entry (`HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\ConsolePrompting`) and set its value to **True** .</span></span>
<span data-ttu-id="429f9-201">Se a entrada do registro **ConsolePrompting** não existir ou se o valor for False, o prompt de autenticação aparece na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="429f9-201">If the **ConsolePrompting** registry entry does not exist or if its value is False, the authentication prompt appears in a dialog box.</span></span> <span data-ttu-id="429f9-202">Para obter instruções, consulte os exemplos.</span><span class="sxs-lookup"><span data-stu-id="429f9-202">For instructions, see the examples.</span></span>

<span data-ttu-id="429f9-203">A entrada do registro **ConsolePrompting** funciona no console do PowerShell, mas não funciona em todos os programas de host.</span><span class="sxs-lookup"><span data-stu-id="429f9-203">The **ConsolePrompting** registry entry works in the PowerShell console, but it does not work in all host programs.</span></span>

<span data-ttu-id="429f9-204">Por exemplo, ele não tem nenhum efeito no ISE (ambiente de script integrado) do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="429f9-204">For example, it has no effect in the PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="429f9-205">Para obter informações sobre o efeito entrada do registro **ConsolePrompting** , consulte os tópicos de ajuda para o programa do host.</span><span class="sxs-lookup"><span data-stu-id="429f9-205">For information about the effect of the **ConsolePrompting** registry entry, see the help topics for the host program.</span></span>

<span data-ttu-id="429f9-206">O parâmetro **Credential** não tem suporte de todos os provedores instalados com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="429f9-206">The **Credential** parameter is not supported by all providers that are installed with PowerShell.</span></span>
<span data-ttu-id="429f9-207">A partir do PowerShell 3,0, ele tem suporte em cmdlets selecionados, como os `Get-Content` `New-PSDrive` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="429f9-207">Beginning in PowerShell 3.0, it is supported on select cmdlets, such as the `Get-Content` and `New-PSDrive` cmdlets.</span></span>

## <span data-ttu-id="429f9-208">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="429f9-208">RELATED LINKS</span></span>

[<span data-ttu-id="429f9-209">PromptForCredential</span><span class="sxs-lookup"><span data-stu-id="429f9-209">PromptForCredential</span></span>](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
