---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 5630c4d09a2806eb117d005466d4925c1740d3a7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598006"
---
# <span data-ttu-id="0e7d5-102">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="0e7d5-102">Get-Credential</span></span>

## <span data-ttu-id="0e7d5-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0e7d5-103">SYNOPSIS</span></span>
<span data-ttu-id="0e7d5-104">Obtém um objeto de credencial com base em um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-104">Gets a credential object based on a user name and password.</span></span>

## <span data-ttu-id="0e7d5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e7d5-105">SYNTAX</span></span>

### <span data-ttu-id="0e7d5-106">Credentialset (padrão)</span><span class="sxs-lookup"><span data-stu-id="0e7d5-106">CredentialSet (Default)</span></span>

```
Get-Credential [[-Credential] <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="0e7d5-107">Mensagem de</span><span class="sxs-lookup"><span data-stu-id="0e7d5-107">MessageSet</span></span>

```
Get-Credential [-Message <String>] [[-UserName] <String>] [-Title <String>] [<CommonParameters>]
```

## <span data-ttu-id="0e7d5-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0e7d5-108">DESCRIPTION</span></span>

<span data-ttu-id="0e7d5-109">O `Get-Credential` cmdlet cria um objeto de credencial para um nome de usuário e senha especificados.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-109">The `Get-Credential` cmdlet creates a credential object for a specified user name and password.</span></span> <span data-ttu-id="0e7d5-110">É possível utilizar o objeto de credencial em operações de segurança.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-110">You can use the credential object in security operations.</span></span>

<span data-ttu-id="0e7d5-111">O `Get-Credential` cmdlet solicita ao usuário uma senha ou um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-111">The `Get-Credential` cmdlet prompts the user for a password or a user name and password.</span></span> <span data-ttu-id="0e7d5-112">Você pode usar o parâmetro **Message** para especificar uma mensagem personalizada no prompt de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-112">You can use the **Message** parameter to specify a customized message in the command line prompt.</span></span>

## <span data-ttu-id="0e7d5-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0e7d5-113">EXAMPLES</span></span>

### <span data-ttu-id="0e7d5-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="0e7d5-114">Example 1</span></span>

```powershell
$c = Get-Credential
```

<span data-ttu-id="0e7d5-115">Esse comando obtém um objeto de credencial e o salva na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-115">This command gets a credential object and saves it in the `$c` variable.</span></span>

<span data-ttu-id="0e7d5-116">Quando você inserir o comando, um nome de usuário e uma senha serão solicitados.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-116">When you enter the command, you are prompted for a user name and password.</span></span> <span data-ttu-id="0e7d5-117">Quando você insere as informações solicitadas, o cmdlet cria um objeto **PSCredential** que representa as credenciais do usuário e salva-o na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-117">When you enter the requested information, the cmdlet creates a **PSCredential** object representing the credentials of the user and saves it in the `$c` variable.</span></span>

<span data-ttu-id="0e7d5-118">É possível utilizar o objeto como entrada para os cmdlets que exigem autenticação de usuário, como aqueles com um parâmetro **Credential**.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-118">You can use the object as input to cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span> <span data-ttu-id="0e7d5-119">No entanto, alguns provedores instalados com o PowerShell não oferecem suporte ao parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="0e7d5-119">However, some providers that are installed with PowerShell do not support the **Credential** parameter.</span></span>

### <span data-ttu-id="0e7d5-120">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="0e7d5-120">Example 2</span></span>

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

<span data-ttu-id="0e7d5-121">Esses comandos usam um objeto Credential que o `Get-Credential` cmdlet retorna para autenticar um usuário em um computador remoto para que eles possam usar o Instrumentação de gerenciamento do Windows (WMI) para gerenciar o computador.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-121">These commands use a credential object that the `Get-Credential` cmdlet returns to authenticate a user on a remote computer so they can use Windows Management Instrumentation (WMI) to manage the computer.</span></span>

<span data-ttu-id="0e7d5-122">O primeiro comando obtém um objeto de credencial e o salva na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-122">The first command gets a credential object and saves it in the `$c` variable.</span></span> <span data-ttu-id="0e7d5-123">O segundo comando usa o objeto Credential em um `Get-CimInstance` comando.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-123">The second command uses the credential object in a `Get-CimInstance` command.</span></span> <span data-ttu-id="0e7d5-124">Esse comando obtém informações sobre as unidades de disco no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-124">This command gets information about the disk drives on the Server01 computer.</span></span>

### <span data-ttu-id="0e7d5-125">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="0e7d5-125">Example 3</span></span>

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

<span data-ttu-id="0e7d5-126">Este comando mostra como incluir um `Get-Credential` comando em um  `Get-CimInstance` comando.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-126">This command shows how to include a `Get-Credential` command in a  `Get-CimInstance` command.</span></span>

<span data-ttu-id="0e7d5-127">Esse comando usa o `Get-CimInstance` cmdlet para obter informações sobre o BIOS no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-127">This command uses the `Get-CimInstance` cmdlet to get information about the BIOS on the Server01 computer.</span></span> <span data-ttu-id="0e7d5-128">Ele usa o parâmetro **Credential** para autenticar o usuário, Domínio01 \ Usuário01 e um `Get-Credential` comando como o valor do parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="0e7d5-128">It uses the **Credential** parameter to authenticate the user, Domain01\User01, and a `Get-Credential` command as the value of the **Credential** parameter.</span></span>

### <span data-ttu-id="0e7d5-129">Exemplo 4</span><span class="sxs-lookup"><span data-stu-id="0e7d5-129">Example 4</span></span>

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

<span data-ttu-id="0e7d5-130">Este exemplo cria uma credencial que inclui um nome de usuário sem um nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-130">This example creates a credential that includes a user name without a domain name.</span></span>

<span data-ttu-id="0e7d5-131">O primeiro comando obtém uma credencial com o nome de usuário User01 e a armazena na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-131">The first command gets a credential with the user name User01 and stores it in the `$c` variable.</span></span>
<span data-ttu-id="0e7d5-132">O segundo comando exibe o valor da propriedade **Username** do objeto de credencial resultante.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-132">The second command displays the value of the **Username** property of the resulting credential object.</span></span>

### <span data-ttu-id="0e7d5-133">Exemplo 5</span><span class="sxs-lookup"><span data-stu-id="0e7d5-133">Example 5</span></span>

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

<span data-ttu-id="0e7d5-134">Este comando utiliza o método **PromptForCredential** para solicitar ao usuário seu nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-134">This command uses the **PromptForCredential** method to prompt the user for their user name and password.</span></span> <span data-ttu-id="0e7d5-135">O comando salva as credenciais resultantes na `$Credential` variável.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-135">The command saves the resulting credentials in the `$Credential` variable.</span></span>

<span data-ttu-id="0e7d5-136">O método **PromptForCredential** é uma alternativa ao uso do `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-136">The **PromptForCredential** method is an alternative to using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0e7d5-137">Ao usar o **PromptForCredential**, você pode especificar a legenda, as mensagens e o nome de usuário que aparecem no prompt.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-137">When you use **PromptForCredential**, you can specify the caption, messages, and user name that appear in the prompt.</span></span>

<span data-ttu-id="0e7d5-138">Para obter mais informações, consulte a documentação do [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) no SDK.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-138">For more information, see the [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) documentation in the SDK.</span></span>

### <span data-ttu-id="0e7d5-139">Exemplo 6</span><span class="sxs-lookup"><span data-stu-id="0e7d5-139">Example 6</span></span>

<span data-ttu-id="0e7d5-140">Este exemplo mostra como criar um objeto de credencial que seja idêntico ao objeto que `Get-Credential` retorna sem avisar o usuário.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-140">This example shows how to create a credential object that is identical to the object that `Get-Credential` returns without prompting the user.</span></span> <span data-ttu-id="0e7d5-141">Este método requer uma senha de texto sem formatação, que pode violar os padrões de segurança em algumas empresas.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-141">This method requires a plain text password, which might violate the security standards in some enterprises.</span></span>

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

<span data-ttu-id="0e7d5-142">O primeiro comando salva o nome da conta de usuário no `$User` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-142">The first command saves the user account name in the `$User` parameter.</span></span> <span data-ttu-id="0e7d5-143">O valor deve ter o formato "Domain\User" ou "ComputerName\User".</span><span class="sxs-lookup"><span data-stu-id="0e7d5-143">The value must have the "Domain\User" or "ComputerName\User" format.</span></span>

<span data-ttu-id="0e7d5-144">O segundo comando usa o `ConvertTo-SecureString` cmdlet para criar uma cadeia de caracteres segura de uma senha de texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-144">The second command uses the `ConvertTo-SecureString` cmdlet to create a secure string from a plain text password.</span></span> <span data-ttu-id="0e7d5-145">O comando utiliza o parâmetro **AsPlainText** para indicar que a cadeia de caracteres de texto está sem formatação e o parâmetro **Force** para confirmar que você compreende os riscos do uso de texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-145">The command uses the **AsPlainText** parameter to indicate that the string is plain text and the **Force** parameter to confirm that you understand the risks of using plain text.</span></span>

<span data-ttu-id="0e7d5-146">O terceiro comando usa o `New-Object` cmdlet para criar um objeto **PSCredential** com base nos valores nas `$User` `$PWord` variáveis e.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-146">The third command uses the `New-Object` cmdlet to create a **PSCredential** object from the values in the `$User` and `$PWord` variables.</span></span>

### <span data-ttu-id="0e7d5-147">Exemplo 7</span><span class="sxs-lookup"><span data-stu-id="0e7d5-147">Example 7</span></span>

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

<span data-ttu-id="0e7d5-148">Esse comando usa os parâmetros de **mensagem** e **nome de usuário** do `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-148">This command uses the **Message** and **UserName** parameters of the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0e7d5-149">Esse formato de comando destina-se a funções e scripts compartilhados.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-149">This command format is designed for shared scripts and functions.</span></span> <span data-ttu-id="0e7d5-150">Nesse caso, a mensagem informa ao usuário porque as credenciais são necessárias e dá a eles confiança de que a solicitação é legítima.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-150">In this case, the message tells the user why credentials are needed and gives them confidence that the request is legitimate.</span></span>

### <span data-ttu-id="0e7d5-151">Exemplo 8</span><span class="sxs-lookup"><span data-stu-id="0e7d5-151">Example 8</span></span>

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

<span data-ttu-id="0e7d5-152">Esse comando obtém uma credencial do computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-152">This command gets a credential from the Server01 remote computer.</span></span> <span data-ttu-id="0e7d5-153">O comando usa o `Invoke-Command` cmdlet para executar um `Get-Credential` comando no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-153">The command uses the `Invoke-Command` cmdlet to run a `Get-Credential` command on the remote computer.</span></span> <span data-ttu-id="0e7d5-154">A saída mostra a mensagem de segurança remota que `Get-Credential` inclui no prompt de autenticação.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-154">The output shows the remote security message that `Get-Credential` includes in the authentication prompt.</span></span>

## <span data-ttu-id="0e7d5-155">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e7d5-155">PARAMETERS</span></span>

### <span data-ttu-id="0e7d5-156">-Credential</span><span class="sxs-lookup"><span data-stu-id="0e7d5-156">-Credential</span></span>

<span data-ttu-id="0e7d5-157">Especifica um nome de usuário para a credencial, como **User01** ou **Domínio01 \ Usuário01**.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-157">Specifies a user name for the credential, such as **User01** or **Domain01\User01**.</span></span> <span data-ttu-id="0e7d5-158">O nome do parâmetro, `-Credential` , é opcional.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-158">The parameter name, `-Credential`, is optional.</span></span>

<span data-ttu-id="0e7d5-159">Ao enviar o comando e especificar um nome de usuário, você será solicitado a fornecer uma senha.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-159">When you submit the command and specify a user name, you're prompted for a password.</span></span> <span data-ttu-id="0e7d5-160">Se você omitir esse parâmetro, um nome de usuário e uma senha serão solicitados.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-160">If you omit this parameter, you're prompted for a user name and a password.</span></span>

<span data-ttu-id="0e7d5-161">A partir do PowerShell 3,0, se você inserir um nome de usuário sem um domínio, `Get-Credential` o não inserirá mais uma barra invertida antes do nome.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-161">Starting in PowerShell 3.0, if you enter a user name without a domain, `Get-Credential` no longer inserts a backslash before the name.</span></span>

<span data-ttu-id="0e7d5-162">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="0e7d5-162">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="0e7d5-163">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="0e7d5-163">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e7d5-164">-Mensagem</span><span class="sxs-lookup"><span data-stu-id="0e7d5-164">-Message</span></span>

<span data-ttu-id="0e7d5-165">Especifica uma mensagem que aparece no prompt de autenticação.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-165">Specifies a message that appears in the authentication prompt.</span></span> <span data-ttu-id="0e7d5-166">Esse parâmetro é projetado para o uso em uma função ou script.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-166">This parameter is designed for use in a function or script.</span></span> <span data-ttu-id="0e7d5-167">É possível utilizar a mensagem para explicar ao usuário por que você está solicitando credenciais e como elas serão utilizadas.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-167">You can use the message to explain to the user why you are requesting credentials and how they will be used.</span></span>

<span data-ttu-id="0e7d5-168">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-168">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e7d5-169">-Title</span><span class="sxs-lookup"><span data-stu-id="0e7d5-169">-Title</span></span>

<span data-ttu-id="0e7d5-170">Define o texto da linha de título para o prompt de autenticação no console do.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-170">Sets the text of the title line for the authentication prompt in the console.</span></span>

<span data-ttu-id="0e7d5-171">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-171">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e7d5-172">-UserName</span><span class="sxs-lookup"><span data-stu-id="0e7d5-172">-UserName</span></span>

<span data-ttu-id="0e7d5-173">Especifica um nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-173">Specifies a user name.</span></span> <span data-ttu-id="0e7d5-174">O prompt de autenticação solicita uma senha para o nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-174">The authentication prompt requests a password for the user name.</span></span> <span data-ttu-id="0e7d5-175">Por padrão, o nome de usuário está em branco e o prompt de autenticação solicita um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-175">By default, the user name is blank and the authentication prompt requests both a user name and password.</span></span>

<span data-ttu-id="0e7d5-176">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-176">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0e7d5-177">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0e7d5-177">CommonParameters</span></span>

<span data-ttu-id="0e7d5-178">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-178">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e7d5-179">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0e7d5-179">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e7d5-180">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0e7d5-180">INPUTS</span></span>

### <span data-ttu-id="0e7d5-181">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0e7d5-181">None</span></span>

<span data-ttu-id="0e7d5-182">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-182">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="0e7d5-183">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0e7d5-183">OUTPUTS</span></span>

### <span data-ttu-id="0e7d5-184">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="0e7d5-184">System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="0e7d5-185">`Get-Credential` Retorna um objeto Credential.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-185">`Get-Credential` returns a credential object.</span></span>

## <span data-ttu-id="0e7d5-186">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0e7d5-186">NOTES</span></span>

<span data-ttu-id="0e7d5-187">Você pode usar o objeto **PSCredential** que `Get-Credential` cria em cmdlets que solicitam autenticação de usuário, como aqueles com um parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="0e7d5-187">You can use the **PSCredential** object that `Get-Credential` creates in cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span>

<span data-ttu-id="0e7d5-188">O parâmetro **Credential** não tem suporte de todos os provedores instalados com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-188">The **Credential** parameter is not supported by all providers that are installed with PowerShell.</span></span>
<span data-ttu-id="0e7d5-189">A partir do PowerShell 3,0, ele tem suporte em cmdlets selecionados, como os `Get-Content` `New-PSDrive` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="0e7d5-189">Beginning in PowerShell 3.0, it is supported on select cmdlets, such as the `Get-Content` and `New-PSDrive` cmdlets.</span></span>

## <span data-ttu-id="0e7d5-190">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0e7d5-190">RELATED LINKS</span></span>

[<span data-ttu-id="0e7d5-191">PromptForCredential</span><span class="sxs-lookup"><span data-stu-id="0e7d5-191">PromptForCredential</span></span>](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
