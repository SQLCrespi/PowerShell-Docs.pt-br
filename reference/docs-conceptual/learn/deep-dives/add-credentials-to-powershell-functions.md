---
title: Adicionar suporte a Credential às funções do PowerShell
description: Como adicionar parâmetros de credencial a seus scripts, funções e cmdlets do PowerShell.
ms.date: 10/29/2020
ms.custom: contributor-JoshDuffney
ms.openlocfilehash: 3e4a3f41ccbca1cf97f2e96fd60f22d89be7bc5a
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354619"
---
# <a name="add-credential-support-to-powershell-functions"></a><span data-ttu-id="89bc9-103">Adicionar suporte a Credential às funções do PowerShell</span><span class="sxs-lookup"><span data-stu-id="89bc9-103">Add Credential support to PowerShell functions</span></span>

> [!NOTE]
> <span data-ttu-id="89bc9-104">A [versão original][] deste artigo foi publicada no blog escrito por [@joshduffney][].</span><span class="sxs-lookup"><span data-stu-id="89bc9-104">The [original version][] of this article appeared on the blog written by [@joshduffney][].</span></span> <span data-ttu-id="89bc9-105">Este artigo foi editado para inclusão neste site.</span><span class="sxs-lookup"><span data-stu-id="89bc9-105">This article has been edited for inclusion on this site.</span></span> <span data-ttu-id="89bc9-106">A equipe do PowerShell agradece a Josh por compartilhar este conteúdo conosco.</span><span class="sxs-lookup"><span data-stu-id="89bc9-106">The PowerShell team thanks Josh for sharing this content with us.</span></span> <span data-ttu-id="89bc9-107">Confira o blog dele em [duffney.io][].</span><span class="sxs-lookup"><span data-stu-id="89bc9-107">Please check out his blog at [duffney.io][].</span></span>

<span data-ttu-id="89bc9-108">Este artigo mostra como adicionar parâmetros de credencial às funções do PowerShell e por que é conveniente fazer isso.</span><span class="sxs-lookup"><span data-stu-id="89bc9-108">This article shows you how to add credential parameters to PowerShell functions and why you'd want to.</span></span> <span data-ttu-id="89bc9-109">Um parâmetro de credencial permite que você execute a função ou cmdlet como um usuário diferente.</span><span class="sxs-lookup"><span data-stu-id="89bc9-109">A credential parameter is to allow you to run the function or cmdlet as a different user.</span></span> <span data-ttu-id="89bc9-110">Ele é comumente usado para executar a função ou cmdlet como uma conta de usuário com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="89bc9-110">The most common use is to run the function or cmdlet as an elevated user account.</span></span>

<span data-ttu-id="89bc9-111">Por exemplo, o cmdlet `New-ADUser` tem um parâmetro **Credential** , para o qual você pode fornecer credenciais de administrador de domínio a fim de criar uma conta em um domínio.</span><span class="sxs-lookup"><span data-stu-id="89bc9-111">For example, the cmdlet `New-ADUser` has a **Credential** parameter, which you could provide domain admin credentials to create an account in a domain.</span></span> <span data-ttu-id="89bc9-112">Supondo que sua conta normal que está executando a sessão do PowerShell ainda não tenha esse acesso.</span><span class="sxs-lookup"><span data-stu-id="89bc9-112">Assuming your normal account running the PowerShell session doesn't have that access already.</span></span>

## <a name="creating-credential-object"></a><span data-ttu-id="89bc9-113">Criar um objeto de credencial</span><span class="sxs-lookup"><span data-stu-id="89bc9-113">Creating credential object</span></span>

<span data-ttu-id="89bc9-114">O objeto [PSCredential][] representa um conjunto de credenciais de segurança, como nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="89bc9-114">The [PSCredential][] object represents a set of security credentials such as a user name and password.</span></span> <span data-ttu-id="89bc9-115">O objeto pode ser passado como um parâmetro para uma função executada como a conta de usuário nesse objeto de credencial.</span><span class="sxs-lookup"><span data-stu-id="89bc9-115">The object can be passed as a parameter to a function that runs as the user account in that credential object.</span></span> <span data-ttu-id="89bc9-116">Há algumas maneiras de criar um objeto de credencial.</span><span class="sxs-lookup"><span data-stu-id="89bc9-116">There are a few ways that you can create a credential object.</span></span> <span data-ttu-id="89bc9-117">A primeira maneira é usar o cmdlet do PowerShell `Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-117">The first way to create a credential object is to use the PowerShell cmdlet `Get-Credential`.</span></span> <span data-ttu-id="89bc9-118">Quando você faz a execução sem parâmetros, é solicitado um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="89bc9-118">When you run without parameters, it prompts you for a username and password.</span></span> <span data-ttu-id="89bc9-119">Ou é possível chamar o cmdlet com alguns parâmetros opcionais.</span><span class="sxs-lookup"><span data-stu-id="89bc9-119">Or you can call the cmdlet with some optional parameters.</span></span>

<span data-ttu-id="89bc9-120">Para especificar o nome de domínio e nome de usuário com antecedência, você pode usar os parâmetros **Credential** ou **UserName**.</span><span class="sxs-lookup"><span data-stu-id="89bc9-120">To specify the domain name and username ahead of time you can use either the **Credential** or **UserName** parameters.</span></span> <span data-ttu-id="89bc9-121">Ao usar o parâmetro **UserName** , você também deve fornecer um valor de **Message**.</span><span class="sxs-lookup"><span data-stu-id="89bc9-121">When you use the **UserName** parameter, you're also required to provide a **Message** value.</span></span> <span data-ttu-id="89bc9-122">O código a seguir demonstra o uso do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="89bc9-122">The code below demonstrates using the cmdlet.</span></span> <span data-ttu-id="89bc9-123">Você também pode armazenar o objeto de credencial em uma variável para poder usar a credencial várias vezes.</span><span class="sxs-lookup"><span data-stu-id="89bc9-123">You can also store the credential object in a variable so that you can use the credential multiple times.</span></span> <span data-ttu-id="89bc9-124">No exemplo abaixo, o objeto de credencial é armazenado na variável `$Cred`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-124">In the example below, the credential object is stored in the variable `$Cred`.</span></span>

```powershell
$Cred = Get-Credential
$Cred = Get-Credential -Credential domain\user
$Cred = Get-Credential -UserName domain\user -Message 'Enter Password'
```

<span data-ttu-id="89bc9-125">Às vezes, não será possível usar o método interativo de criação de objetos de credencial mostrado no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="89bc9-125">Sometimes, you can't use the interactive method of creating credential objects shown in the previous example.</span></span> <span data-ttu-id="89bc9-126">A maioria das ferramentas de automação requer um método não interativo.</span><span class="sxs-lookup"><span data-stu-id="89bc9-126">Most automation tools require a non-interactive method.</span></span> <span data-ttu-id="89bc9-127">Para criar uma credencial sem interação do usuário, crie uma cadeia de caracteres segura que contenha a senha.</span><span class="sxs-lookup"><span data-stu-id="89bc9-127">To create a credential without user interaction, create a secure string containing the password.</span></span> <span data-ttu-id="89bc9-128">Depois, passe a cadeia de caracteres segura e o nome de usuário para o método `System.Management.Automation.PSCredential()`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-128">Then pass the secure string and user name to the `System.Management.Automation.PSCredential()` method.</span></span>

<span data-ttu-id="89bc9-129">Use o seguinte comando para criar uma cadeia de caracteres segura que contém a senha:</span><span class="sxs-lookup"><span data-stu-id="89bc9-129">Use the following command to create a secure string containing the password:</span></span>

```powershell
ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
```

<span data-ttu-id="89bc9-130">Tanto o parâmetro **AsPlainText** quanto o **Force** são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="89bc9-130">Both the **AsPlainText** and **Force** parameters are required.</span></span> <span data-ttu-id="89bc9-131">Sem esses parâmetros, você recebe uma mensagem avisando que não deve passar texto sem formatação para uma cadeia de caracteres segura.</span><span class="sxs-lookup"><span data-stu-id="89bc9-131">Without those parameters, you receive a message warning that you shouldn't pass plain text into a secure string.</span></span> <span data-ttu-id="89bc9-132">O PowerShell retorna esse aviso porque a senha de texto sem formatação é registrada em vários logs.</span><span class="sxs-lookup"><span data-stu-id="89bc9-132">PowerShell returns this warning because the plain text password gets recorded in various logs.</span></span> <span data-ttu-id="89bc9-133">Depois de criar uma cadeia de caracteres segura, você precisa passá-la para o método `PSCredential()` a fim de criar o objeto de credencial.</span><span class="sxs-lookup"><span data-stu-id="89bc9-133">Once you have a secure string created, you need to pass it to the `PSCredential()` method to create the credential object.</span></span> <span data-ttu-id="89bc9-134">No exemplo a seguir, a variável `$password` contém a cadeia de caractere segura e `$Cred` contém o objeto de credencial.</span><span class="sxs-lookup"><span data-stu-id="89bc9-134">In the following example, the variable `$password` contains the secure string `$Cred` contains the credential object.</span></span>

```powershell
$password = ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("username", $password)
```

<span data-ttu-id="89bc9-135">Agora que você sabe como criar objetos de credencial, pode adicionar parâmetros de credencial às funções do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89bc9-135">Now that you know how to create credential objects, you can add credential parameters to your PowerShell functions.</span></span>

## <a name="adding-a-credential-parameter"></a><span data-ttu-id="89bc9-136">Adicionar um parâmetro de credencial</span><span class="sxs-lookup"><span data-stu-id="89bc9-136">Adding a Credential Parameter</span></span>

<span data-ttu-id="89bc9-137">Assim como qualquer outro parâmetro, comece adicionando-o ao bloco `param` de sua função.</span><span class="sxs-lookup"><span data-stu-id="89bc9-137">Just like any other parameter, you start off by adding it in the `param` block of your function.</span></span>
<span data-ttu-id="89bc9-138">Recomendamos nomear o parâmetro como `$Credential` porque é isso que os cmdlets existentes do PowerShell usam.</span><span class="sxs-lookup"><span data-stu-id="89bc9-138">It's recommended that you name the parameter `$Credential` because that's what existing PowerShell cmdlets use.</span></span> <span data-ttu-id="89bc9-139">O tipo do parâmetro deve ser `[System.Management.Automation.PSCredential]`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-139">The type of the parameter should be `[System.Management.Automation.PSCredential]`.</span></span>

<span data-ttu-id="89bc9-140">O exemplo a seguir mostra o bloco de parâmetro para uma função chamada `Get-Something`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-140">The following example shows the parameter block for a function called `Get-Something`.</span></span> <span data-ttu-id="89bc9-141">Ela tem dois parâmetros: `$Name` e `$Credential`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-141">It has two parameters: `$Name` and `$Credential`.</span></span>

```powershell
function Get-Something {
    param(
        $Name,
        [System.Management.Automation.PSCredential]$Credential
    )
```

<span data-ttu-id="89bc9-142">O código nesse exemplo é suficiente para ter um parâmetro de credencial funcional. no entanto, você pode adicionar alguns elementos para torná-lo mais robusto.</span><span class="sxs-lookup"><span data-stu-id="89bc9-142">The code in this example is enough to have a working credential parameter, however there are a few things you can add to make it more robust.</span></span>

- <span data-ttu-id="89bc9-143">Adicione o atributo de validação `[ValidateNotNull()]` para verificar se o valor está sendo passado para **Credential**.</span><span class="sxs-lookup"><span data-stu-id="89bc9-143">Add the `[ValidateNotNull()]` validation attribute to check that the value being passed to **Credential**.</span></span> <span data-ttu-id="89bc9-144">Se o valor do parâmetro for nulo, esse atributo impedirá que a função seja executada com credenciais inválidas.</span><span class="sxs-lookup"><span data-stu-id="89bc9-144">If the parameter value is null, this attribute prevents the function from executing with invalid credentials.</span></span>

- <span data-ttu-id="89bc9-145">Adicione `[System.Management.Automation.Credential()]`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-145">Add `[System.Management.Automation.Credential()]`.</span></span> <span data-ttu-id="89bc9-146">Isso permite que você passe um nome de usuário como uma cadeia de caracteres e tenha um prompt interativo para a senha.</span><span class="sxs-lookup"><span data-stu-id="89bc9-146">This allows you to pass in a username as a string and have an interactive prompt for the password.</span></span>

- <span data-ttu-id="89bc9-147">Defina um valor padrão do parâmetro `$Credential` para `[System.Management.Automation.PSCredential]::Empty`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-147">Set a default value for the `$Credential` parameter to `[System.Management.Automation.PSCredential]::Empty`.</span></span> <span data-ttu-id="89bc9-148">Sua função você pode estar passando esse objeto `$Credential` para os cmdlets do PowerShell existentes.</span><span class="sxs-lookup"><span data-stu-id="89bc9-148">Your function you might be passing this `$Credential` object to existing PowerShell cmdlets.</span></span> <span data-ttu-id="89bc9-149">Fornecer um valor nulo ao cmdlet chamado dentro de sua função causa um erro.</span><span class="sxs-lookup"><span data-stu-id="89bc9-149">Providing a null value to the cmdlet called inside your function causes an error.</span></span> <span data-ttu-id="89bc9-150">Para evitar isso, forneça um objeto de credencial vazio.</span><span class="sxs-lookup"><span data-stu-id="89bc9-150">Providing an empty credential object avoids this error.</span></span>

> [!TIP]
> <span data-ttu-id="89bc9-151">Alguns cmdlets que aceitam um parâmetro de credencial não dão suporte a `[System.Management.Automation.PSCredential]::Empty` como deveriam.</span><span class="sxs-lookup"><span data-stu-id="89bc9-151">Some cmdlets that accept a credential parameter do not support `[System.Management.Automation.PSCredential]::Empty` as they should.</span></span> <span data-ttu-id="89bc9-152">Confira a seção [Lidar com cmdlets herdados](#dealing-with-legacy-cmdlets) para obter uma solução alternativa.</span><span class="sxs-lookup"><span data-stu-id="89bc9-152">See the [Dealing with Legacy Cmdlets](#dealing-with-legacy-cmdlets) section for a workaround.</span></span>

## <a name="using-credential-parameters"></a><span data-ttu-id="89bc9-153">Usar parâmetros de credencial</span><span class="sxs-lookup"><span data-stu-id="89bc9-153">Using credential parameters</span></span>

<span data-ttu-id="89bc9-154">O exemplo a seguir demonstra como usar parâmetros de credencial.</span><span class="sxs-lookup"><span data-stu-id="89bc9-154">The following example demonstrates how to use credential parameters.</span></span> <span data-ttu-id="89bc9-155">Este exemplo mostra uma função chamada `Set-RemoteRegistryValue`, extraída do [The Pester Book][].</span><span class="sxs-lookup"><span data-stu-id="89bc9-155">This example shows a function called `Set-RemoteRegistryValue`, which is out of [The Pester Book][].</span></span> <span data-ttu-id="89bc9-156">Essa função define o parâmetro de credencial usando as técnicas descritas na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="89bc9-156">This function defines the credential parameter using the techniques describe in the previous section.</span></span> <span data-ttu-id="89bc9-157">A função chama `Invoke-Command` usando a variável `$Credential` criada por ela.</span><span class="sxs-lookup"><span data-stu-id="89bc9-157">The function calls `Invoke-Command` using the `$Credential` variable created by the function.</span></span> <span data-ttu-id="89bc9-158">Isso permite que você altere o usuário que está executando `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-158">This allows you to change the user who's running `Invoke-Command`.</span></span> <span data-ttu-id="89bc9-159">Como o valor padrão de `$Credential` é uma credencial vazia, a função pode ser executada sem o fornecimento de credenciais.</span><span class="sxs-lookup"><span data-stu-id="89bc9-159">Because the default value of `$Credential` is an empty credential, the function can run without providing credentials.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )
        $null = Invoke-Command -ComputerName $ComputerName -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } -Credential $Credential
}
```

<span data-ttu-id="89bc9-160">As seções a seguir mostram métodos diferentes de fornecimento de credenciais para `Set-RemoteRegistryValue`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-160">The following sections show different methods of providing credentials to `Set-RemoteRegistryValue`.</span></span>

### <a name="prompting-for-credentials"></a><span data-ttu-id="89bc9-161">Solicitar credenciais</span><span class="sxs-lookup"><span data-stu-id="89bc9-161">Prompting for credentials</span></span>

<span data-ttu-id="89bc9-162">Usar `Get-Credential` entre parênteses `()` durante o tempo de execução faz com que `Get-credential` seja executado primeiro.</span><span class="sxs-lookup"><span data-stu-id="89bc9-162">Using `Get-Credential` in parentheses `()` at run time causes the `Get-credential` to run first.</span></span> <span data-ttu-id="89bc9-163">Você será solicitado a informar um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="89bc9-163">You are prompted for a username and password.</span></span> <span data-ttu-id="89bc9-164">Você pode usar os parâmetros **Credential** ou **UserName** de `Get-credential` para preencher previamente o nome de usuário e o domínio.</span><span class="sxs-lookup"><span data-stu-id="89bc9-164">You could use the **Credential** or **UserName** parameters of `Get-credential` to pre-populate the username and domain.</span></span> <span data-ttu-id="89bc9-165">O exemplo a seguir usa uma técnica chamada nivelamento a fim de passar parâmetros para a função `Set-RemoteRegistryValue`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-165">The following example uses a technique called splatting to pass parameters to the `Set-RemoteRegistryValue` function.</span></span> <span data-ttu-id="89bc9-166">Para saber mais sobre o nivelamento, confira o artigo [Sobre o nivelamento][].</span><span class="sxs-lookup"><span data-stu-id="89bc9-166">For more information about splatting, check out the [about_Splatting][] article.</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential (Get-Credential)
```

![Obter uma credencial em tempo de execução](./media/add-credentials-to-powershell-functions/GetCredAtRunTime.gif)

<span data-ttu-id="89bc9-168">Usar o `(Get-Credential)` parece complicado.</span><span class="sxs-lookup"><span data-stu-id="89bc9-168">Using `(Get-Credential)` seems cumbersome.</span></span> <span data-ttu-id="89bc9-169">Normalmente, quando você usa o parâmetro **Credential** com apenas um nome de usuário, o cmdlet solicita a senha automaticamente.</span><span class="sxs-lookup"><span data-stu-id="89bc9-169">Normally, when you use the **Credential** parameter with only a username, the cmdlet automatically prompts for the password.</span></span> <span data-ttu-id="89bc9-170">O atributo `[System.Management.Automation.Credential()]` habilita esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="89bc9-170">The `[System.Management.Automation.Credential()]` attribute enables this behavior.</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential duffney
```

![Solicita credenciais](./media/add-credentials-to-powershell-functions/GetCredsPrompt.gif)

> [!NOTE]
> <span data-ttu-id="89bc9-172">Para definir o valor de registro mostrado, esses exemplos presumem que você possui os recursos do **Servidor da Web** do Windows instalados.</span><span class="sxs-lookup"><span data-stu-id="89bc9-172">To set the registry value shown, these examples assume you have the **Web Server** features of Windows installed.</span></span> <span data-ttu-id="89bc9-173">Execute `Install-WindowsFeature Web-Server` e `Install-WindowsFeature web-mgmt-tools`, se necessário.</span><span class="sxs-lookup"><span data-stu-id="89bc9-173">Run `Install-WindowsFeature Web-Server` and `Install-WindowsFeature web-mgmt-tools` if required.</span></span>

### <a name="provide-credentials-in-a-variable"></a><span data-ttu-id="89bc9-174">Fornecer credenciais em uma variável</span><span class="sxs-lookup"><span data-stu-id="89bc9-174">Provide credentials in a variable</span></span>

<span data-ttu-id="89bc9-175">Você também pode preencher uma variável de credencial com antecedência e passá-la para o parâmetro **Credential** da função `Set-RemoteRegistryValue`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-175">You can also populate a credential variable ahead of time and pass it to the **Credential** parameter of `Set-RemoteRegistryValue` function.</span></span> <span data-ttu-id="89bc9-176">Use esse método com ferramentas de CI/CD (integração contínua/implantação contínua), como Jenkins, TeamCity e Octopus Deploy.</span><span class="sxs-lookup"><span data-stu-id="89bc9-176">Use this method with Continuous Integration / Continuous Deployment (CI/CD) tools such as Jenkins, TeamCity, and Octopus Deploy.</span></span> <span data-ttu-id="89bc9-177">Para obter um exemplo de uso do Jenkins, confira a postagem no blog de Hodge [Automatizar com Jenkins e PowerShell no Windows – Parte 2][].</span><span class="sxs-lookup"><span data-stu-id="89bc9-177">For an example using Jenkins, check out Hodge's blog post [Automating with Jenkins and PowerShell on Windows - Part 2][].</span></span>

<span data-ttu-id="89bc9-178">Este exemplo usa o método .NET para criar o objeto de credencial e uma cadeia de caracteres segura para passar a senha.</span><span class="sxs-lookup"><span data-stu-id="89bc9-178">This example uses the .NET method to create the credential object and a secure string to pass in the password.</span></span>

```powershell
$password = ConvertTo-SecureString "P@ssw0rd" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("duffney", $password)

$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential $Cred
```

<span data-ttu-id="89bc9-179">Nesse exemplo, a cadeia de caracteres segura é criada usando uma senha com texto não criptografado.</span><span class="sxs-lookup"><span data-stu-id="89bc9-179">For this example, the secure string is created using a clear text password.</span></span> <span data-ttu-id="89bc9-180">Todas as ferramentas de CI/CD mencionadas anteriormente têm um método seguro de fornecimento de senha em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="89bc9-180">All of the previously mentioned CI/CD have a secure method of providing that password at run time.</span></span> <span data-ttu-id="89bc9-181">Ao utilizá-las, substitua a senha de texto sem formatação pela variável definida na ferramenta de CI/CD que você usa.</span><span class="sxs-lookup"><span data-stu-id="89bc9-181">When using those tools, replace the plain text password with the variable defined within the CI/CD tool you use.</span></span>

### <a name="run-without-credentials"></a><span data-ttu-id="89bc9-182">Executar sem credenciais</span><span class="sxs-lookup"><span data-stu-id="89bc9-182">Run without credentials</span></span>

<span data-ttu-id="89bc9-183">Como o `$Credential` usa como padrão um objeto de credencial vazio, você pode executar o comando sem credenciais, conforme mostrado no seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="89bc9-183">Since `$Credential` defaults to an empty credential object, you can run the command without credentials, as shown in this example:</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams
```

## <a name="dealing-with-legacy-cmdlets"></a><span data-ttu-id="89bc9-184">Lidar com cmdlets herdados</span><span class="sxs-lookup"><span data-stu-id="89bc9-184">Dealing with legacy cmdlets</span></span>

<span data-ttu-id="89bc9-185">Nem todos os cmdlets dão suporte a objetos de credencial ou permitem credenciais vazias.</span><span class="sxs-lookup"><span data-stu-id="89bc9-185">Not all cmdlets support credential objects or allow empty credentials.</span></span> <span data-ttu-id="89bc9-186">Em vez disso, o cmdlet prefere usar os parâmetros de nome de usuário e senha como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="89bc9-186">Instead, the cmdlet wants username and password parameters as strings.</span></span> <span data-ttu-id="89bc9-187">Para solucionar essa limitação, há algumas alternativas.</span><span class="sxs-lookup"><span data-stu-id="89bc9-187">There are a few ways to work around this limitation.</span></span>

### <a name="using-if-else-to-handle-empty-credentials"></a><span data-ttu-id="89bc9-188">Usar if-else para lidar com credenciais vazias</span><span class="sxs-lookup"><span data-stu-id="89bc9-188">Using if-else to handle empty credentials</span></span>

<span data-ttu-id="89bc9-189">Neste cenário, o cmdlet que você deseja executar não aceita um objeto de credencial vazio.</span><span class="sxs-lookup"><span data-stu-id="89bc9-189">In this scenario, the cmdlet you want to run doesn't accept an empty credential object.</span></span> <span data-ttu-id="89bc9-190">Este exemplo adicionará o parâmetro **Credential** a `Invoke-Command` somente se ele não estiver vazio.</span><span class="sxs-lookup"><span data-stu-id="89bc9-190">This example adds the **Credential** parameter to `Invoke-Command` only if it's not empty.</span></span> <span data-ttu-id="89bc9-191">Caso contrário, executará o `Invoke-Command` sem o parâmetro **Credential**.</span><span class="sxs-lookup"><span data-stu-id="89bc9-191">Otherwise, it runs the `Invoke-Command` without the **Credential** parameter.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

    if($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
        Invoke-Command -ComputerName:$ComputerName -Credential:$Credential  {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    } else {
        Invoke-Command -ComputerName:$ComputerName {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    }
}
```

### <a name="using-splatting-to-handle-empty-credentials"></a><span data-ttu-id="89bc9-192">Usar nivelamento para lidar com credenciais vazias</span><span class="sxs-lookup"><span data-stu-id="89bc9-192">Using splatting to handle empty credentials</span></span>

<span data-ttu-id="89bc9-193">Este exemplo usa o nivelamento de parâmetro para chamar o cmdlet herdado.</span><span class="sxs-lookup"><span data-stu-id="89bc9-193">This example uses parameter splatting to call the legacy cmdlet.</span></span> <span data-ttu-id="89bc9-194">O objeto `$Credential` é adicionado condicionalmente à tabela de hash de nivelamento e evita a necessidade de repetir o bloco de script `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-194">The `$Credential` object is conditionally added to the hash table for splatting and avoids the need to repeat the `Invoke-Command` script block.</span></span> <span data-ttu-id="89bc9-195">Para saber mais sobre o nivelamento dentro de funções, confira a postagem no blog [Nivelar parâmetros dentro de funções avançadas][].</span><span class="sxs-lookup"><span data-stu-id="89bc9-195">To learn more about splatting inside functions, see the [Splatting Parameters Inside Advanced Functions][] blog post.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $Splat = @{
            ComputerName = $ComputerName
        }

        if ($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
            $Splat['Credential'] = $Credential
        }

        $null = Invoke-Command -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } @splat
}
```

### <a name="working-with-string-passwords"></a><span data-ttu-id="89bc9-196">Trabalhar com cadeias de caracteres como senha</span><span class="sxs-lookup"><span data-stu-id="89bc9-196">Working with string passwords</span></span>

<span data-ttu-id="89bc9-197">O cmdlet `Invoke-Sqlcmd` é um dos que aceitam uma cadeia de caracteres como senha.</span><span class="sxs-lookup"><span data-stu-id="89bc9-197">The `Invoke-Sqlcmd` cmdlet is an example of a cmdlet that accepts a string as a password.</span></span>
<span data-ttu-id="89bc9-198">O `Invoke-Sqlcmd` permite executar instruções SQL simples de inserção, atualização e exclusão.</span><span class="sxs-lookup"><span data-stu-id="89bc9-198">`Invoke-Sqlcmd` allows you to run simple SQL insert, update, and delete statements.</span></span> <span data-ttu-id="89bc9-199">O `Invoke-Sqlcmd` requer um nome de usuário e senha com texto não criptografado, em vez de um objeto de credencial mais seguro.</span><span class="sxs-lookup"><span data-stu-id="89bc9-199">`Invoke-Sqlcmd` requires a clear-text username and password rather than a more secure credential object.</span></span> <span data-ttu-id="89bc9-200">Este exemplo mostra como extrair o nome de usuário e a senha de um objeto de credencial.</span><span class="sxs-lookup"><span data-stu-id="89bc9-200">This example shows how to extract the username and password from a credential object.</span></span>

<span data-ttu-id="89bc9-201">A função `Get-AllSQLDatabases` neste exemplo chama o cmdlet `Invoke-Sqlcmd` a fim de consultar um servidor SQL para todos os seus bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="89bc9-201">The `Get-AllSQLDatabases` function in this example calls the `Invoke-Sqlcmd` cmdlet to query a SQL server for all its databases.</span></span> <span data-ttu-id="89bc9-202">A função define um parâmetro **Credential** com o mesmo atributo usado nos exemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="89bc9-202">The function defines a **Credential** parameter with the same attribute used in the previous examples.</span></span> <span data-ttu-id="89bc9-203">Como o nome de usuário e a senha existem na variável `$Credential`, você pode extrair esses valores para usar com `Invoke-Sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-203">Since the username and password exist within the `$Credential` variable, you can extract those values for use with `Invoke-Sqlcmd`.</span></span>

<span data-ttu-id="89bc9-204">O nome de usuário está disponível na propriedade **UserName** da variável `$Credential`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-204">The user name is available from the **UserName** property of the `$Credential` variable.</span></span> <span data-ttu-id="89bc9-205">Para obter a senha, você deve usar o método `GetNetworkCredential()` do objeto `$Credential`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-205">To obtain the password, you have to use the `GetNetworkCredential()` method of the `$Credential` object.</span></span> <span data-ttu-id="89bc9-206">Os valores são extraídos em variáveis que são adicionadas a uma tabela de hash usada para nivelamento dos parâmetros para `Invoke-Sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="89bc9-206">The values are extracted into variables that are added to a hash table used for splatting parameters to `Invoke-Sqlcmd`.</span></span>

```powershell
function Get-AllSQLDatabases {
    param(
        $SQLServer,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $UserName = $Credential.UserName
        $Password = $Credential.GetNetworkCredential().Password

        $splat = @{
            UserName = $UserName
            Password = $Password
            ServerInstance = 'SQLServer'
            Query = "Select * from Sys.Databases"
        }

        Invoke-Sqlcmd @splat
}

$credSplat = @{
    TypeName = 'System.Management.Automation.PSCredential'
    ArgumentList = 'duffney',('P@ssw0rd' | ConvertTo-SecureString -AsPlainText -Force)
}
$Credential= New-Object @credSplat
ConvertTo-SecureString -AsPlainText -Force)

Get-AllSQLDatabases -SQLServer SQL01 -Credential $Credential
```

## <a name="continued-learning-credential-management"></a><span data-ttu-id="89bc9-207">Gerenciamento de credencial de aprendizagem contínua</span><span class="sxs-lookup"><span data-stu-id="89bc9-207">Continued learning credential management</span></span>

<span data-ttu-id="89bc9-208">Criar e armazenar objetos de credenciais com segurança pode ser difícil.</span><span class="sxs-lookup"><span data-stu-id="89bc9-208">Creating and storing credential objects securely can be difficult.</span></span> <span data-ttu-id="89bc9-209">Os recursos a seguir podem ajudar você a manter suas credenciais do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89bc9-209">The following resources can help you maintain PowerShell credentials.</span></span>

- <span data-ttu-id="89bc9-210">[BetterCredentials][]</span><span class="sxs-lookup"><span data-stu-id="89bc9-210">[BetterCredentials][]</span></span>
- <span data-ttu-id="89bc9-211">[Cofre da Chave do Azure][]</span><span class="sxs-lookup"><span data-stu-id="89bc9-211">[Azure Key Vault][]</span></span>
- <span data-ttu-id="89bc9-212">[Projeto de Cofre][]</span><span class="sxs-lookup"><span data-stu-id="89bc9-212">[Vault Project][]</span></span>
- <span data-ttu-id="89bc9-213">[Módulo SecretManagement][]</span><span class="sxs-lookup"><span data-stu-id="89bc9-213">[SecretManagement module][]</span></span>

<!-- link references -->
[versão original]: https://duffney.io/addcredentialstopowershellfunctions/
[original version]: https://duffney.io/addcredentialstopowershellfunctions/
[@joshduffney]: https://twitter.com/joshduffney
[duffney.io]: https://duffney.io/posts/
[BetterCredentials]: https://www.powershellgallery.com/packages/BetterCredentials/
[Cofre da Chave do Azure]: https://azure.microsoft.com/services/key-vault/
[Azure Key Vault]: https://azure.microsoft.com/services/key-vault/
[Projeto de Cofre]: https://www.vaultproject.io/
[Vault Project]: https://www.vaultproject.io/
[Nivelar parâmetros dentro de funções avançadas]: https://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[Splatting Parameters Inside Advanced Functions]: https://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[Automatizar com Jenkins e PowerShell no Windows – Parte 2]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[Automating with Jenkins and PowerShell on Windows - Part 2]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[PSCredential]: /dotnet/api/system.management.automation.pscredential
[The Pester Book]: https://leanpub.com/the-pester-book
[about_Splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[Módulo SecretManagement]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
[SecretManagement module]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
