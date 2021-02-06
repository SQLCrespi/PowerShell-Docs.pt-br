---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionOption
ms.openlocfilehash: d07942797bad3666a263e017fa8372e672936041
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595988"
---
# <span data-ttu-id="62a7d-102">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="62a7d-102">New-PSSessionOption</span></span>

## <span data-ttu-id="62a7d-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="62a7d-103">SYNOPSIS</span></span>
<span data-ttu-id="62a7d-104">Cria um objeto que contém opções avançadas para uma PSSession.</span><span class="sxs-lookup"><span data-stu-id="62a7d-104">Creates an object that contains advanced options for a PSSession.</span></span>

## <span data-ttu-id="62a7d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="62a7d-105">SYNTAX</span></span>

```
New-PSSessionOption [-MaximumRedirection <Int32>] [-NoCompression] [-NoMachineProfile] [-Culture <CultureInfo>]
 [-UICulture <CultureInfo>] [-MaximumReceivedDataSizePerCommand <Int32>] [-MaximumReceivedObjectSize <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-MaxConnectionRetryCount <Int32>]
 [-ApplicationArguments <PSPrimitiveDictionary>] [-OpenTimeout <Int32>] [-CancelTimeout <Int32>]
 [-IdleTimeout <Int32>] [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <AuthenticationMechanism>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [-IncludePortInSPN] [<CommonParameters>]
```

## <span data-ttu-id="62a7d-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="62a7d-106">DESCRIPTION</span></span>

<span data-ttu-id="62a7d-107">O `New-PSSessionOption` cmdlet cria um objeto que contém opções avançadas para uma sessão gerenciada pelo usuário (**PSSession**).</span><span class="sxs-lookup"><span data-stu-id="62a7d-107">The `New-PSSessionOption` cmdlet creates an object that contains advanced options for a user-managed session (**PSSession**).</span></span> <span data-ttu-id="62a7d-108">Você pode usar o objeto como o valor do parâmetro **SessionOption** de cmdlets que criam uma **PSSession**, como `New-PSSession` , `Enter-PSSession` e `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="62a7d-108">You can use the object as the value of the **SessionOption** parameter of cmdlets that create a **PSSession**, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

<span data-ttu-id="62a7d-109">Sem parâmetros, `New-PSSessionOption` o gera um objeto que contém os valores padrão para todas as opções.</span><span class="sxs-lookup"><span data-stu-id="62a7d-109">Without parameters, `New-PSSessionOption` generates an object that contains the default values for all of the options.</span></span> <span data-ttu-id="62a7d-110">Como todas as propriedades podem ser editadas, é possível usar o objeto resultante como um modelo e criar objetos de opção padrão para a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="62a7d-110">Because all of the properties can be edited, you can use the resulting object as a template, and create standard option objects for your enterprise.</span></span>

<span data-ttu-id="62a7d-111">Você também pode salvar um objeto de opção de sessão na `$PSSessionOption` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="62a7d-111">You can also save a session option object in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="62a7d-112">Os valores desta variável estabelecem novos valores padrão para as opções da sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-112">The values of this variable establish new default values for the session options.</span></span> <span data-ttu-id="62a7d-113">Eles tornam-se efetivos quando nenhuma opção de sessão está definida e têm precedência sobre as opções definidas na configuração da sessão, mas você pode substituí-los especificando opções de sessão ou um objeto de opção de sessão em um cmdlet que cria uma sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-113">They effective when no session options are set for the session and they take precedence over options set in the session configuration, but you can override them by specifying session options or a session option object in a cmdlet that creates a session.</span></span> <span data-ttu-id="62a7d-114">Para obter mais informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="62a7d-114">For more information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="62a7d-115">Quando você usa um objeto de opção de sessão em um cmdlet que cria uma sessão, os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na variável de preferência $PSSessionOption e na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-115">When you use a session option object in a cmdlet that creates a session, the session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span> <span data-ttu-id="62a7d-116">No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-116">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span> <span data-ttu-id="62a7d-117">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="62a7d-117">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="62a7d-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="62a7d-118">EXAMPLES</span></span>

### <span data-ttu-id="62a7d-119">Exemplo 1: criar uma opção de sessão padrão</span><span class="sxs-lookup"><span data-stu-id="62a7d-119">Example 1: Create a default session option</span></span>

<span data-ttu-id="62a7d-120">Este comando cria um objeto de opção de sessão que tem todos os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-120">This command creates a session option object that has all of the default values.</span></span>

```powershell
New-PSSessionOption
```

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

### <span data-ttu-id="62a7d-121">Exemplo 2: configurar uma sessão usando um objeto de opção de sessão</span><span class="sxs-lookup"><span data-stu-id="62a7d-121">Example 2: Configure a session by using a session option object</span></span>

<span data-ttu-id="62a7d-122">Este exemplo mostra como usar um objeto de opção de sessão para configurar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-122">This example shows how to use a session option object to configure a session.</span></span>

```powershell
$pso = New-PSSessionOption -Culture "fr-fr" -MaximumReceivedObjectSize 10MB
New-PSSession -ComputerName Server01 -SessionOption $pso
```

<span data-ttu-id="62a7d-123">O primeiro comando cria um novo objeto de opção de sessão e o salva no valor da `$pso` variável.</span><span class="sxs-lookup"><span data-stu-id="62a7d-123">The first command creates a new session option object and saves it in the value of the `$pso` variable.</span></span> <span data-ttu-id="62a7d-124">O segundo comando usa o `New-PSSession` cmdlet para criar uma sessão no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="62a7d-124">The second command uses the `New-PSSession` cmdlet to create a session on the Server01 remote computer.</span></span> <span data-ttu-id="62a7d-125">O comando usa o objeto de opção de sessão no valor da `$pso` variável como o valor do parâmetro **SessionOption** do comando.</span><span class="sxs-lookup"><span data-stu-id="62a7d-125">The command uses the session option object in the value of the `$pso` variable as the value of the **SessionOption** parameter of the command.</span></span>

### <span data-ttu-id="62a7d-126">Exemplo 3: iniciar uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="62a7d-126">Example 3: Start an interactive session</span></span>

<span data-ttu-id="62a7d-127">Esse comando usa o `Enter-PSSession` cmdlet para iniciar uma sessão interativa com o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="62a7d-127">This command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

```powershell
Enter-PSSession -ComputerName Server01 -SessionOption (New-PSSessionOption -NoEncryption -NoCompression)
```

<span data-ttu-id="62a7d-128">O valor do parâmetro **SessionOption** é um `New-PSSessionOption` comando que tem os parâmetros **NoEncryption** e **NoCompression** .</span><span class="sxs-lookup"><span data-stu-id="62a7d-128">The value of the **SessionOption** parameter is a `New-PSSessionOption` command that has the **NoEncryption** and **NoCompression** parameters.</span></span>

<span data-ttu-id="62a7d-129">O `New-PSSessionOption` comando é colocado entre parênteses para garantir que ele seja executado antes do `Enter-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="62a7d-129">The `New-PSSessionOption` command is enclosed in parentheses to make sure that it runs before the `Enter-PSSession` command.</span></span>

### <span data-ttu-id="62a7d-130">Exemplo 4: modificar um objeto de opção de sessão</span><span class="sxs-lookup"><span data-stu-id="62a7d-130">Example 4: Modify a session option object</span></span>

<span data-ttu-id="62a7d-131">Este exemplo demonstra que você pode modificar o objeto de opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-131">This example demonstrates that you can modify the session option object.</span></span> <span data-ttu-id="62a7d-132">Todas as propriedades têm valores de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="62a7d-132">All properties have read/write values.</span></span>

```powershell
$a = New-PSSessionOption
$a.OpenTimeout
```

```Output
Days              : 0
Hours             : 0
Minutes           : 3
Seconds           : 0
Milliseconds      : 0
Ticks             : 1800000000
TotalDays         : 0.00208333333333333
TotalHours        : 0.05
TotalMinutes      : 3
TotalSeconds      : 180
TotalMilliseconds : 180000
```

```powershell
$a.UICulture = (Get-UICulture)
$a.OpenTimeout = (New-Timespan -Minutes 4)
$a.MaximumConnectionRedirectionCount = 1
$a
```

```Output
MaximumConnectionRedirectionCount : 1
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         : en-US
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:04:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

<span data-ttu-id="62a7d-133">Use esse método para criar um objeto de sessão padrão para sua empresa e, em seguida, criar versões personalizadas desse objeto para usos específicos.</span><span class="sxs-lookup"><span data-stu-id="62a7d-133">Use this method to create a standard session object for your enterprise, and then create customized versions of it for particular uses.</span></span>

### <span data-ttu-id="62a7d-134">Exemplo 5: criar uma variável de preferência</span><span class="sxs-lookup"><span data-stu-id="62a7d-134">Example 5: Create a preference variable</span></span>

<span data-ttu-id="62a7d-135">Este comando cria uma `$PSSessionOption` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="62a7d-135">This command creates a `$PSSessionOption` preference variable.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -OpenTimeOut 120000
```

<span data-ttu-id="62a7d-136">Quando a `$PSSessionOption` variável de preferência ocorre na sessão, ela estabelece valores padrão para as opções nas sessões criadas usando os `New-PSSession` `Enter-PSSession` `Invoke-Command` cmdlets, e.</span><span class="sxs-lookup"><span data-stu-id="62a7d-136">When the `$PSSessionOption` preference variable occurs in the session, it establishes default values for options in the sessions that are created by using the `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="62a7d-137">Para disponibilizar a `$PSSessionOption` variável em todas as sessões, adicione-a à sua sessão do PowerShell e ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62a7d-137">To make the `$PSSessionOption` variable available in all sessions, add it to your PowerShell session and to your PowerShell profile.</span></span>

<span data-ttu-id="62a7d-138">Para obter mais informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="62a7d-138">For more information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="62a7d-139">Para obter mais informações sobre perfis, consulte [about_Profiles](About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="62a7d-139">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

### <span data-ttu-id="62a7d-140">Exemplo 6: atender aos requisitos para uma configuração de sessão remota</span><span class="sxs-lookup"><span data-stu-id="62a7d-140">Example 6: Fulfill the requirements for a remote session configuration</span></span>

<span data-ttu-id="62a7d-141">Este exemplo mostra como usar um objeto **SessionOption** para atender os requisitos para a configuração de uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="62a7d-141">This example shows how to use a **SessionOption** object to fulfill the requirements for a remote session configuration.</span></span>

```powershell
$skipCN = New-PSSessionOption -SkipCNCheck
New-PSSession -ComputerName 171.09.21.207 -UseSSL -Credential Domain01\User01 -SessionOption $SkipCN
```

<span data-ttu-id="62a7d-142">O primeiro comando usa o `New-PSSessionOption` cmdlet para criar um objeto de opção de sessão que tem a propriedade **SkipCNCheck** .</span><span class="sxs-lookup"><span data-stu-id="62a7d-142">The first command uses the `New-PSSessionOption` cmdlet to create a session option object that has the **SkipCNCheck** property.</span></span> <span data-ttu-id="62a7d-143">O comando salva o objeto de sessão resultante na `$skipCN` variável.</span><span class="sxs-lookup"><span data-stu-id="62a7d-143">The command saves the resulting session object in the `$skipCN` variable.</span></span>

<span data-ttu-id="62a7d-144">O segundo comando usa o `New-PSSession` cmdlet para criar uma nova sessão em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="62a7d-144">The second command uses the `New-PSSession` cmdlet to create a new session on a remote computer.</span></span> <span data-ttu-id="62a7d-145">A `$skipCN` variável de verificação é usada no valor do parâmetro **SessionOption** .</span><span class="sxs-lookup"><span data-stu-id="62a7d-145">The `$skipCN` check variable is used in the value of the **SessionOption** parameter.</span></span>

<span data-ttu-id="62a7d-146">Como o computador é identificado por seu endereço IP, o valor do parâmetro **ComputerName** não corresponde a nenhum dos nomes comuns no certificado usado para protocolo SSL (SSL).</span><span class="sxs-lookup"><span data-stu-id="62a7d-146">Because the computer is identified by its IP address, the value of the **ComputerName** parameter does not match any of the common names in the certificate that is used for Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="62a7d-147">Como resultado, a opção **SkipCNCheck** é obrigatória.</span><span class="sxs-lookup"><span data-stu-id="62a7d-147">As a result, the **SkipCNCheck** option is required.</span></span>

### <span data-ttu-id="62a7d-148">Exemplo 7: tornar argumentos disponíveis para uma sessão remota</span><span class="sxs-lookup"><span data-stu-id="62a7d-148">Example 7: Make arguments available to a remote session</span></span>

<span data-ttu-id="62a7d-149">Este exemplo mostra como usar o parâmetro **ApplicationArguments** do `New-PSSessionOption` cmdlet para disponibilizar dados adicionais para a sessão remota.</span><span class="sxs-lookup"><span data-stu-id="62a7d-149">This example shows how to use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet to make additional data available to the remote session.</span></span>

```powershell
$team = @{Team="IT"; Use="Testing"}
$TeamOption = New-PSSessionOption -ApplicationArguments $team
$s = New-PSSession -ComputerName Server01 -SessionOption $TeamOption
Invoke-Command -Session $s {$PSSenderInfo.ApplicationArguments}
```

```Output
Name                 Value
----                 -----
Team                 IT
Use                  Testing
PSVersionTable       {CLRVersion, BuildVersion, PSVersion, WSManStackVersion...}
```

```powershell
Invoke-Command -Session $s {
  if ($PSSenderInfo.ApplicationArguments.Use -ne "Testing") {
    .\logFiles.ps1
  }
  else {
    "Just testing."
  }
}
```

```Output
Just testing.
```

<span data-ttu-id="62a7d-150">O primeiro comando cria uma tabela de hash com duas chaves, **equipe** e **uso**.</span><span class="sxs-lookup"><span data-stu-id="62a7d-150">The first command creates a hash table with two keys, **Team** and **Use**.</span></span> <span data-ttu-id="62a7d-151">O comando salva a tabela de hash na `$team` variável.</span><span class="sxs-lookup"><span data-stu-id="62a7d-151">The command saves the hash table in the `$team` variable.</span></span> <span data-ttu-id="62a7d-152">Para obter informações sobre tabelas de hash, confira [about_Hash_Tables](about/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="62a7d-152">For more information about hash tables, see [about_Hash_Tables](about/about_Hash_Tables.md).</span></span>

<span data-ttu-id="62a7d-153">Em seguida, o `New-PSSessionOption` cmdlet, usando o parâmetro **ApplicationArguments** , cria um objeto de opção de sessão salvo na `$team` variável.</span><span class="sxs-lookup"><span data-stu-id="62a7d-153">Next, the `New-PSSessionOption` cmdlet, using the **ApplicationArguments** parameter, creates a session option object saved in the `$team` variable.</span></span> <span data-ttu-id="62a7d-154">Quando `New-PSSessionOption` o cria o objeto de opção de sessão, ele converte automaticamente a tabela de hash no valor do parâmetro **ApplicationArguments** em um dicionário primitivo para que os dados possam ser transmitidos de forma confiável para a sessão remota.</span><span class="sxs-lookup"><span data-stu-id="62a7d-154">When `New-PSSessionOption` creates the session option object, it automatically converts the hash table in the value of the **ApplicationArguments** parameter to a primitive dictionary so the data can be reliably transmitted to the remote session.</span></span>

<span data-ttu-id="62a7d-155">O `New-PSSession` cmdlet inicia uma sessão no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="62a7d-155">The `New-PSSession` cmdlet starts a session on the Server01 computer.</span></span> <span data-ttu-id="62a7d-156">Ele usa o parâmetro **SessionOption** para incluir as opções na `$teamOption` variável.</span><span class="sxs-lookup"><span data-stu-id="62a7d-156">It uses the **SessionOption** parameter to include the options in the `$teamOption` variable.</span></span>

<span data-ttu-id="62a7d-157">O `Invoke-Command` cmdlet demonstra que os dados na `$team` variável estão disponíveis para comandos na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="62a7d-157">The `Invoke-Command` cmdlet demonstrates that the data in the `$team` variable is available to commands in the remote session.</span></span> <span data-ttu-id="62a7d-158">Os dados são exibidos na propriedade **ApplicationArguments** da `$PSSenderInfo` variável automática.</span><span class="sxs-lookup"><span data-stu-id="62a7d-158">The data appears in the **ApplicationArguments** property of the `$PSSenderInfo` automatic variable.</span></span>

<span data-ttu-id="62a7d-159">O final `Invoke-Command` mostra como os dados podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="62a7d-159">The final `Invoke-Command` shows how the data might be used.</span></span>

## <span data-ttu-id="62a7d-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="62a7d-160">PARAMETERS</span></span>

### <span data-ttu-id="62a7d-161">-ApplicationArguments</span><span class="sxs-lookup"><span data-stu-id="62a7d-161">-ApplicationArguments</span></span>

<span data-ttu-id="62a7d-162">Especifica um dicionário primitivo que é enviado à sessão remota.</span><span class="sxs-lookup"><span data-stu-id="62a7d-162">Specifies a primitive dictionary that is sent to the remote session.</span></span> <span data-ttu-id="62a7d-163">Os comandos e scripts na sessão remota, incluindo os scripts de inicialização na configuração da sessão, podem encontrar esse dicionário na propriedade **ApplicationArguments** da `$PSSenderInfo` variável automática.</span><span class="sxs-lookup"><span data-stu-id="62a7d-163">Commands and scripts in the remote session, including startup scripts in the session configuration, can find this dictionary in the **ApplicationArguments** property of the `$PSSenderInfo` automatic variable.</span></span> <span data-ttu-id="62a7d-164">Você pode usar este parâmetro para enviar dados à sessão remota.</span><span class="sxs-lookup"><span data-stu-id="62a7d-164">You can use this parameter to send data to the remote session.</span></span>

<span data-ttu-id="62a7d-165">Para obter mais informações, consulte [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md)e [about_Automatic_Variables](about/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="62a7d-165">For more information, see [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md), and [about_Automatic_Variables](about/about_Automatic_Variables.md).</span></span>

```yaml
Type: System.Management.Automation.PSPrimitiveDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-166">-CancelTimeout</span><span class="sxs-lookup"><span data-stu-id="62a7d-166">-CancelTimeout</span></span>

<span data-ttu-id="62a7d-167">Determina por quanto tempo o PowerShell aguarda uma operação de cancelamento (CTRL + C) para concluir antes de terminá-la.</span><span class="sxs-lookup"><span data-stu-id="62a7d-167">Determines how long PowerShell waits for a cancel operation (CTRL+C) to finish before ending it.</span></span>
<span data-ttu-id="62a7d-168">Insira um valor em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="62a7d-168">Enter a value in milliseconds.</span></span>

<span data-ttu-id="62a7d-169">O valor padrão é 60.000 (um minuto).</span><span class="sxs-lookup"><span data-stu-id="62a7d-169">The default value is 60000 (one minute).</span></span> <span data-ttu-id="62a7d-170">Um valor de 0 (zero) significa que não há tempo limite; o comando continua indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="62a7d-170">A value of 0 (zero) means no time-out; the command continues indefinitely.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: CancelTimeoutMSec

Required: False
Position: Named
Default value: 60000
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-171">-Culture</span><span class="sxs-lookup"><span data-stu-id="62a7d-171">-Culture</span></span>

<span data-ttu-id="62a7d-172">Especifica a cultura a ser usada para a sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-172">Specifies the culture to use for the session.</span></span> <span data-ttu-id="62a7d-173">Insira um nome de cultura no `<languagecode2>-<country/regioncode2>` formato (como `ja-JP` ), uma variável que contém um objeto **CultureInfo** ou um comando que obtém um objeto **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="62a7d-173">Enter a culture name in `<languagecode2>-<country/regioncode2>` format (like `ja-JP`), a variable that contains a **CultureInfo** object, or a command that gets a **CultureInfo** object.</span></span>

<span data-ttu-id="62a7d-174">O valor padrão é `$Null` , e a cultura definida no sistema operacional é usada na sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-174">The default value is `$Null`, and the culture that is set in the operating system is used in the session.</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-175">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="62a7d-175">-IdleTimeout</span></span>

<span data-ttu-id="62a7d-176">Determina por quanto tempo a sessão permanecerá aberta se o computador remoto não receber nenhuma comunicação do computador local.</span><span class="sxs-lookup"><span data-stu-id="62a7d-176">Determines how long the session stays open if the remote computer does not receive any communication from the local computer.</span></span> <span data-ttu-id="62a7d-177">Isso inclui o sinal de pulsação.</span><span class="sxs-lookup"><span data-stu-id="62a7d-177">This includes the heartbeat signal.</span></span> <span data-ttu-id="62a7d-178">Quando o intervalo expira, a sessão é fechada.</span><span class="sxs-lookup"><span data-stu-id="62a7d-178">When the interval expires, the session closes.</span></span>

<span data-ttu-id="62a7d-179">O valor de tempo limite ocioso é de importância significativa se você pretende desconectar e reconectar-se a uma sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-179">The idle time-out value is of significant importance if you intend to disconnect and reconnect to a session.</span></span> <span data-ttu-id="62a7d-180">Você poderá reconectar-se somente se a sessão não tiver expirado.</span><span class="sxs-lookup"><span data-stu-id="62a7d-180">You can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="62a7d-181">Insira um valor em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="62a7d-181">Enter a value in milliseconds.</span></span> <span data-ttu-id="62a7d-182">O valor mínimo é 60000 (1 minuto).</span><span class="sxs-lookup"><span data-stu-id="62a7d-182">The minimum value is 60000 (1 minute).</span></span> <span data-ttu-id="62a7d-183">O máximo é o valor da propriedade **MaxIdleTimeoutms** da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-183">The maximum is the value of the **MaxIdleTimeoutms** property of the session configuration.</span></span> <span data-ttu-id="62a7d-184">O valor padrão,-1, não define um tempo limite ocioso.</span><span class="sxs-lookup"><span data-stu-id="62a7d-184">The default value, -1, does not set an idle time-out.</span></span>

<span data-ttu-id="62a7d-185">A sessão usa o tempo limite ocioso definido nas opções de sessão, se houver.</span><span class="sxs-lookup"><span data-stu-id="62a7d-185">The session uses the idle time-out that is set in the session options, if any.</span></span> <span data-ttu-id="62a7d-186">Se nenhum for definido (-1), a sessão usará o valor da propriedade **IdleTimeoutMs** da configuração de sessão ou o valor de tempo limite do shell do WSMan ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ), o que for mais curto.</span><span class="sxs-lookup"><span data-stu-id="62a7d-186">If none is set (-1), the session uses the value of the **IdleTimeoutMs** property of the session configuration or the WSMan shell time-out value (`WSMan:\<ComputerName>\Shell\IdleTimeout`), whichever is shortest.</span></span>

<span data-ttu-id="62a7d-187">Se o tempo limite de ociosidade definido nas opções da sessão excede o valor da propriedade **MaxIdleTimeoutMs** da configuração da sessão, o comando para criar uma sessão falha.</span><span class="sxs-lookup"><span data-stu-id="62a7d-187">If the idle timeout set in the session options exceeds the value of the **MaxIdleTimeoutMs** property of the session configuration, the command to create a session fails.</span></span>

<span data-ttu-id="62a7d-188">O valor de **IdleTimeoutMs** da configuração de sessão padrão do **Microsoft. PowerShell** é de 7,2 milhões milissegundos (2 horas).</span><span class="sxs-lookup"><span data-stu-id="62a7d-188">The **IdleTimeoutMs** value of the default **Microsoft.PowerShell** session configuration is 7200000 milliseconds (2 hours).</span></span> <span data-ttu-id="62a7d-189">Seu valor de **MaxIdleTimeoutMs** é de 2147483647 milissegundos ( \> 24 dias).</span><span class="sxs-lookup"><span data-stu-id="62a7d-189">Its **MaxIdleTimeoutMs** value is 2147483647 milliseconds (\>24 days).</span></span> <span data-ttu-id="62a7d-190">O valor padrão do tempo limite de ociosidade do shell do WSMan ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ) é de 7,2 milhões milissegundos (2 horas).</span><span class="sxs-lookup"><span data-stu-id="62a7d-190">The default value of the WSMan shell idle time-out (`WSMan:\<ComputerName>\Shell\IdleTimeout`) is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="62a7d-191">O valor de tempo limite ocioso de uma sessão também pode ser alterado ao desconectar-se de uma sessão ou reconectar-se a uma sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-191">The idle time-out value of a session can also be changed when disconnecting from a session or reconnecting to a session.</span></span> <span data-ttu-id="62a7d-192">Para obter mais informações, consulte `Disconnect-PSSession` e `Connect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="62a7d-192">For more information, see `Disconnect-PSSession` and `Connect-PSSession`.</span></span>

<span data-ttu-id="62a7d-193">No Windows PowerShell 2.0, o valor padrão do parâmetro **IdleTimeout** é 240.000 milissegundos (4 minutos).</span><span class="sxs-lookup"><span data-stu-id="62a7d-193">In Windows PowerShell 2.0, the default value of the **IdleTimeout** parameter is 240000 (4 minutes).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: IdleTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-194">-IncludePortInSPN</span><span class="sxs-lookup"><span data-stu-id="62a7d-194">-IncludePortInSPN</span></span>

<span data-ttu-id="62a7d-195">Inclui o número da porta no nome da entidade de serviço (SPN) usado para autenticação Kerberos, por exemplo, `HTTP://<ComputerName>:5985` .</span><span class="sxs-lookup"><span data-stu-id="62a7d-195">Includes the port number in the Service Principal Name (SPN) used for Kerberos authentication, for example, `HTTP://<ComputerName>:5985`.</span></span> <span data-ttu-id="62a7d-196">Esta opção permite que um cliente que usa um SPN não padrão faça a autenticação em um computador remoto que usa autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="62a7d-196">This option allows a client that uses a non-default SPN to authenticate against a remote computer that uses Kerberos authentication.</span></span>

<span data-ttu-id="62a7d-197">A opção é projetada para empresas nas quais vários serviços que oferecem suporte à autenticação Kerberos estão sendo executados em diferentes contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="62a7d-197">The option is designed for enterprises where multiple services that support Kerberos authentication are running under different user accounts.</span></span> <span data-ttu-id="62a7d-198">Por exemplo, um aplicativo IIS que permite a autenticação Kerberos pode exigir que o SPN padrão seja registrado para uma conta de usuário diferente da conta do computador.</span><span class="sxs-lookup"><span data-stu-id="62a7d-198">For example, an IIS application that allows for Kerberos authentication can require the default SPN to be registered to a user account that differs from the computer account.</span></span> <span data-ttu-id="62a7d-199">Nesses casos, a comunicação remota do PowerShell não pode usar o Kerberos para autenticar porque requer um SPN registrado na conta do computador.</span><span class="sxs-lookup"><span data-stu-id="62a7d-199">In such cases, PowerShell remoting cannot use Kerberos to authenticate because it requires an SPN that is registered to the computer account.</span></span> <span data-ttu-id="62a7d-200">Para resolver esse problema, os administradores podem criar diferentes SPNs, como usando **Setspn.exe**, que são registrados em contas de usuário diferentes e podem distinguir entre eles, incluindo o número da porta no SPN.</span><span class="sxs-lookup"><span data-stu-id="62a7d-200">To resolve this problem, administrators can create different SPNs, such as by using **Setspn.exe**, that are registered to different user accounts and can distinguish between them by including the port number in the SPN.</span></span>

<span data-ttu-id="62a7d-201">Para obter mais informações, consulte [visão geral do SetSPN](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="62a7d-201">For more information, see [Setspn Overview](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).</span></span>

<span data-ttu-id="62a7d-202">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="62a7d-202">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="62a7d-203">-MaxConnectionRetryCount</span><span class="sxs-lookup"><span data-stu-id="62a7d-203">-MaxConnectionRetryCount</span></span>

<span data-ttu-id="62a7d-204">Especifica o número de vezes que o PowerShell tentará estabelecer uma conexão com um computador de destino se a tentativa atual falhar devido a problemas de rede.</span><span class="sxs-lookup"><span data-stu-id="62a7d-204">Specifies the number of times that PowerShell attempts to make a connection to a target machine if the current attempt fails due to network issues.</span></span> <span data-ttu-id="62a7d-205">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="62a7d-205">The default value is 5.</span></span>

<span data-ttu-id="62a7d-206">Esse parâmetro foi adicionado para o PowerShell versão 5,0.</span><span class="sxs-lookup"><span data-stu-id="62a7d-206">This parameter was added for PowerShell version 5.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-207">-MaximumReceivedDataSizePerCommand</span><span class="sxs-lookup"><span data-stu-id="62a7d-207">-MaximumReceivedDataSizePerCommand</span></span>

<span data-ttu-id="62a7d-208">Especifica o número máximo de bytes que o computador local pode receber do computador remoto em um único comando.</span><span class="sxs-lookup"><span data-stu-id="62a7d-208">Specifies the maximum number of bytes that the local computer can receive from the remote computer in a single command.</span></span> <span data-ttu-id="62a7d-209">Insira um valor em bytes.</span><span class="sxs-lookup"><span data-stu-id="62a7d-209">Enter a value in bytes.</span></span> <span data-ttu-id="62a7d-210">Por padrão, não há limite de tamanho de dados.</span><span class="sxs-lookup"><span data-stu-id="62a7d-210">By default, there is no data size limit.</span></span>

<span data-ttu-id="62a7d-211">Esta opção foi criada para proteger os recursos no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="62a7d-211">This option is designed to protect the resources on the client computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-212">-MaximumReceivedObjectSize</span><span class="sxs-lookup"><span data-stu-id="62a7d-212">-MaximumReceivedObjectSize</span></span>

<span data-ttu-id="62a7d-213">Especifica o tamanho máximo de um objeto que o computador local pode receber do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="62a7d-213">Specifies the maximum size of an object that the local computer can receive from the remote computer.</span></span> <span data-ttu-id="62a7d-214">Esta opção foi criada para proteger os recursos no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="62a7d-214">This option is designed to protect the resources on the client computer.</span></span> <span data-ttu-id="62a7d-215">Insira um valor em bytes.</span><span class="sxs-lookup"><span data-stu-id="62a7d-215">Enter a value in bytes.</span></span>

<span data-ttu-id="62a7d-216">No Windows PowerShell 2.0, se você omite esse parâmetro, não há limite para tamanho do objeto.</span><span class="sxs-lookup"><span data-stu-id="62a7d-216">In Windows PowerShell 2.0, if you omit this parameter, there is no object size limit.</span></span> <span data-ttu-id="62a7d-217">A partir do Windows PowerShell 3.0, se você omite esse parâmetro, o valor padrão é 200 MB.</span><span class="sxs-lookup"><span data-stu-id="62a7d-217">Beginning in Windows PowerShell 3.0, if you omit this parameter, the default value is 200 MB.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 200 MB
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-218">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="62a7d-218">-MaximumRedirection</span></span>

<span data-ttu-id="62a7d-219">Determina quantas vezes o PowerShell redireciona uma conexão para um Uniform Resource Identifier alternativo (URI) antes de a conexão falhar.</span><span class="sxs-lookup"><span data-stu-id="62a7d-219">Determines how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="62a7d-220">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="62a7d-220">The default value is 5.</span></span> <span data-ttu-id="62a7d-221">Um valor de 0 (zero) impede qualquer redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="62a7d-221">A value of 0 (zero) prevents all redirection.</span></span>

<span data-ttu-id="62a7d-222">Essa opção é usada na sessão somente quando o parâmetro **AllowRedirection** é usado no comando que cria a sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-222">This option is used in the session only when the **AllowRedirection** parameter is used in the command that creates the session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-223">-NoCompression</span><span class="sxs-lookup"><span data-stu-id="62a7d-223">-NoCompression</span></span>

<span data-ttu-id="62a7d-224">Desativa a compactação de pacotes na sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-224">Turns off packet compression in the session.</span></span> <span data-ttu-id="62a7d-225">A compactação utiliza mais ciclos do processador, mas torna a transmissão mais rápida.</span><span class="sxs-lookup"><span data-stu-id="62a7d-225">Compression uses more processor cycles, but it makes transmission faster.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-226">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="62a7d-226">-NoEncryption</span></span>

<span data-ttu-id="62a7d-227">Desativa a criptografia de dados.</span><span class="sxs-lookup"><span data-stu-id="62a7d-227">Turns off data encryption.</span></span>

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

### <span data-ttu-id="62a7d-228">-NoMachineProfile</span><span class="sxs-lookup"><span data-stu-id="62a7d-228">-NoMachineProfile</span></span>

<span data-ttu-id="62a7d-229">Impede o carregamento de perfil de usuário do Windows do usuário em questão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-229">Prevents loading the user's Windows user profile.</span></span> <span data-ttu-id="62a7d-230">Como resultado a sessão pode ser criada mais rapidamente, mas as configurações de registro específicas do usuário, itens como variáveis de ambiente e certificados, não estarão disponíveis nessa sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-230">As a result, the session might be created faster, but user-specific registry settings, items such as environment variables, and certificates are not available in the session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-231">-OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="62a7d-231">-OpenTimeout</span></span>

<span data-ttu-id="62a7d-232">Determina por quanto tempo o computador cliente aguarda para que a conexão da sessão seja estabelecida.</span><span class="sxs-lookup"><span data-stu-id="62a7d-232">Determines how long the client computer waits for the session connection to be established.</span></span> <span data-ttu-id="62a7d-233">Quando o intervalo expira, o comando para estabelecer a conexão falha.</span><span class="sxs-lookup"><span data-stu-id="62a7d-233">When the interval expires, the command to establish the connection fails.</span></span> <span data-ttu-id="62a7d-234">Insira um valor em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="62a7d-234">Enter a value in milliseconds.</span></span>

<span data-ttu-id="62a7d-235">O valor padrão é 180.000 (3 minutos).</span><span class="sxs-lookup"><span data-stu-id="62a7d-235">The default value is 180000 (3 minutes).</span></span> <span data-ttu-id="62a7d-236">Um valor de 0 (zero) significa que não há tempo limite; o comando continua indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="62a7d-236">A value of 0 (zero) means no time-out; the command continues indefinitely.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OpenTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-237">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="62a7d-237">-OperationTimeout</span></span>

<span data-ttu-id="62a7d-238">Determina o tempo máximo pelo qual qualquer operação na sessão pode ser executada.</span><span class="sxs-lookup"><span data-stu-id="62a7d-238">Determines the maximum time that any operation in the session can run.</span></span> <span data-ttu-id="62a7d-239">Quando o intervalo expira, a operação falha.</span><span class="sxs-lookup"><span data-stu-id="62a7d-239">When the interval expires, the operation fails.</span></span> <span data-ttu-id="62a7d-240">Insira um valor em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="62a7d-240">Enter a value in milliseconds.</span></span>

<span data-ttu-id="62a7d-241">O valor padrão é 180.000 (3 minutos).</span><span class="sxs-lookup"><span data-stu-id="62a7d-241">The default value is 180000 (3 minutes).</span></span> <span data-ttu-id="62a7d-242">Um valor de 0 (zero) significa que não há tempo limite; a operação continua indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="62a7d-242">A value of 0 (zero) means no time-out; the operation continues indefinitely.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-243">-OutputBufferingMode</span><span class="sxs-lookup"><span data-stu-id="62a7d-243">-OutputBufferingMode</span></span>

<span data-ttu-id="62a7d-244">Determina como a saída do comando é gerenciada em sessões desconectadas quando o buffer de saída fica cheio.</span><span class="sxs-lookup"><span data-stu-id="62a7d-244">Determines how command output is managed in disconnected sessions when the output buffer becomes full.</span></span>

<span data-ttu-id="62a7d-245">Se a o modo de buffering de saída não está definido na sessão ou na configuração da sessão, o valor padrão é **Block**.</span><span class="sxs-lookup"><span data-stu-id="62a7d-245">If the output buffering mode is not set in the session or in the session configuration, the default value is **Block**.</span></span> <span data-ttu-id="62a7d-246">Os usuários também podem alterar o modo de buffering de saída ao desconectarem-se da sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-246">Users can also change the output buffering mode when disconnecting the session.</span></span>

<span data-ttu-id="62a7d-247">Se você omitir esse parâmetro, o valor de **OutputBufferingMode** do objeto de opção de sessão será None.</span><span class="sxs-lookup"><span data-stu-id="62a7d-247">If you omit this parameter, the value of the **OutputBufferingMode** of the session option object is None.</span></span> <span data-ttu-id="62a7d-248">Um valor de **Block** ou **Drop** substitui a opção de transporte do modo de buffering de saída, definida na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-248">A value of **Block** or **Drop** overrides the output buffering mode transport option set in the session configuration.</span></span> <span data-ttu-id="62a7d-249">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="62a7d-249">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="62a7d-250">Bloquear.</span><span class="sxs-lookup"><span data-stu-id="62a7d-250">Block.</span></span> <span data-ttu-id="62a7d-251">Quando o buffer de saída está cheio, a execução é suspensa até que o buffer esteja limpo.</span><span class="sxs-lookup"><span data-stu-id="62a7d-251">When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="62a7d-252">Drop.</span><span class="sxs-lookup"><span data-stu-id="62a7d-252">Drop.</span></span> <span data-ttu-id="62a7d-253">Quando o buffer de saída está cheio, a execução continua.</span><span class="sxs-lookup"><span data-stu-id="62a7d-253">When the output buffer is full, execution continues.</span></span> <span data-ttu-id="62a7d-254">Conforme uma nova saída é salva, a saída mais antiga é descartada.</span><span class="sxs-lookup"><span data-stu-id="62a7d-254">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="62a7d-255">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="62a7d-255">None.</span></span> <span data-ttu-id="62a7d-256">Nenhum modo de buffering de saída é especificado.</span><span class="sxs-lookup"><span data-stu-id="62a7d-256">No output buffering mode is specified.</span></span>

<span data-ttu-id="62a7d-257">Para obter mais informações sobre a opção de transporte do modo de buffer de saída, consulte `New-PSTransportOption` .</span><span class="sxs-lookup"><span data-stu-id="62a7d-257">For more information about the output buffering mode transport option, see `New-PSTransportOption`.</span></span>

<span data-ttu-id="62a7d-258">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="62a7d-258">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-259">-ProxyAccessType</span><span class="sxs-lookup"><span data-stu-id="62a7d-259">-ProxyAccessType</span></span>

<span data-ttu-id="62a7d-260">Determina qual mecanismo é usado para resolver o nome do host.</span><span class="sxs-lookup"><span data-stu-id="62a7d-260">Determines which mechanism is used to resolve the host name.</span></span> <span data-ttu-id="62a7d-261">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="62a7d-261">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="62a7d-262">IEConfig</span><span class="sxs-lookup"><span data-stu-id="62a7d-262">IEConfig</span></span>
- <span data-ttu-id="62a7d-263">WinHttpConfig</span><span class="sxs-lookup"><span data-stu-id="62a7d-263">WinHttpConfig</span></span>
- <span data-ttu-id="62a7d-264">AutoDetect</span><span class="sxs-lookup"><span data-stu-id="62a7d-264">AutoDetect</span></span>
- <span data-ttu-id="62a7d-265">NoProxyServer</span><span class="sxs-lookup"><span data-stu-id="62a7d-265">NoProxyServer</span></span>
- <span data-ttu-id="62a7d-266">Nenhum</span><span class="sxs-lookup"><span data-stu-id="62a7d-266">None</span></span>

<span data-ttu-id="62a7d-267">O valor padrão é Nenhum.</span><span class="sxs-lookup"><span data-stu-id="62a7d-267">The default value is None.</span></span>

<span data-ttu-id="62a7d-268">Para obter informações sobre os valores desse parâmetro, consulte [Enumeração ProxyAccessType](/dotnet/api/system.management.automation.remoting.proxyaccesstype).</span><span class="sxs-lookup"><span data-stu-id="62a7d-268">For information about the values of this parameter, see [ProxyAccessType Enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype).</span></span>

```yaml
Type: System.Management.Automation.Remoting.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: None, IEConfig, WinHttpConfig, AutoDetect, NoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-269">-ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="62a7d-269">-ProxyAuthentication</span></span>

<span data-ttu-id="62a7d-270">Especifica o método de autenticação que é usado para resolução de proxy.</span><span class="sxs-lookup"><span data-stu-id="62a7d-270">Specifies the authentication method that is used for proxy resolution.</span></span> <span data-ttu-id="62a7d-271">Os valores aceitáveis para esse parâmetro são: **Basic**, **Digest** e **Negotiate**.</span><span class="sxs-lookup"><span data-stu-id="62a7d-271">The acceptable values for this parameter are: **Basic**, **Digest**, and **Negotiate**.</span></span> <span data-ttu-id="62a7d-272">O valor padrão é **Negotiate**.</span><span class="sxs-lookup"><span data-stu-id="62a7d-272">The default value is **Negotiate**.</span></span>

<span data-ttu-id="62a7d-273">Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="62a7d-273">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-274">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="62a7d-274">-ProxyCredential</span></span>

<span data-ttu-id="62a7d-275">Especifica as credenciais a usar para autenticação de proxy.</span><span class="sxs-lookup"><span data-stu-id="62a7d-275">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="62a7d-276">Insira uma variável que contém um objeto **PSCredential** ou um comando que obtém um objeto **PSCredential** , como um `Get-Credential` comando.</span><span class="sxs-lookup"><span data-stu-id="62a7d-276">Enter a variable that contains a **PSCredential** object or a command that gets a **PSCredential** object, such as a `Get-Credential` command.</span></span> <span data-ttu-id="62a7d-277">Se esta opção não for definida, nenhuma credencial será especificada.</span><span class="sxs-lookup"><span data-stu-id="62a7d-277">If this option is not set, no credentials are specified.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-278">-SkipCACheck</span><span class="sxs-lookup"><span data-stu-id="62a7d-278">-SkipCACheck</span></span>

<span data-ttu-id="62a7d-279">Especifica que quando ele se conecta via HTTPS, o cliente não valida se o certificado do servidor está assinado por uma autoridade de certificação (CA) confiável.</span><span class="sxs-lookup"><span data-stu-id="62a7d-279">Specifies that when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="62a7d-280">Use esta opção somente quando o computador remoto for considerado confiável pelo uso de outro mecanismo, como por exemplo quando o computador remoto é parte de uma rede fisicamente segura e isolada, ou quando o computador remoto está listado como um host confiável em uma configuração de WinRM.</span><span class="sxs-lookup"><span data-stu-id="62a7d-280">Use this option only when the remote computer is trusted by using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-281">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="62a7d-281">-SkipCNCheck</span></span>

<span data-ttu-id="62a7d-282">Especifica que o nome comum do certificado (CN) do servidor não precisa corresponder ao nome do host do servidor.</span><span class="sxs-lookup"><span data-stu-id="62a7d-282">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span> <span data-ttu-id="62a7d-283">Esta opção é usada somente em operações remotas que usam o protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="62a7d-283">This option is used only in remote operations that use the HTTPS protocol.</span></span>

<span data-ttu-id="62a7d-284">Use esta opção somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="62a7d-284">Use this option only for trusted computers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-285">-SkipRevocationCheck</span><span class="sxs-lookup"><span data-stu-id="62a7d-285">-SkipRevocationCheck</span></span>

<span data-ttu-id="62a7d-286">Não valida o status de revogação do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="62a7d-286">Does not validate the revocation status of the server certificate.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-287">-UICulture</span><span class="sxs-lookup"><span data-stu-id="62a7d-287">-UICulture</span></span>

<span data-ttu-id="62a7d-288">Especifica a cultura da interface de usuário a ser usada para a sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-288">Specifies the UI culture to use for the session.</span></span>

<span data-ttu-id="62a7d-289">Os valores válidos incluem:</span><span class="sxs-lookup"><span data-stu-id="62a7d-289">Valid values include:</span></span>

- <span data-ttu-id="62a7d-290">Um nome de cultura no `<languagecode2>-<country/regioncode2>` formato, como `ja-JP`</span><span class="sxs-lookup"><span data-stu-id="62a7d-290">A culture name in `<languagecode2>-<country/regioncode2>` format, such as `ja-JP`</span></span>
- <span data-ttu-id="62a7d-291">Uma variável que contém um objeto **CultureInfo**</span><span class="sxs-lookup"><span data-stu-id="62a7d-291">A variable that contains a **CultureInfo** object</span></span>
- <span data-ttu-id="62a7d-292">Um comando que obtém um objeto **CultureInfo** , como `Get-Culture`</span><span class="sxs-lookup"><span data-stu-id="62a7d-292">A command that gets a **CultureInfo** object, such as `Get-Culture`</span></span>

<span data-ttu-id="62a7d-293">O valor padrão é `$null` , e a cultura da interface do usuário que é definida no sistema operacional quando a sessão é criada é usada na sessão.</span><span class="sxs-lookup"><span data-stu-id="62a7d-293">The default value is `$null`, and the UI culture that is set in the operating system when the session is created is used in the session.</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62a7d-294">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="62a7d-294">-UseUTF16</span></span>

<span data-ttu-id="62a7d-295">Indica que esse cmdlet codifica a solicitação no formato UTF16 em vez do formato UTF8.</span><span class="sxs-lookup"><span data-stu-id="62a7d-295">Indicates that this cmdlet encodes the request in UTF16 format instead of UTF8 format.</span></span>

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

### <span data-ttu-id="62a7d-296">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="62a7d-296">CommonParameters</span></span>

<span data-ttu-id="62a7d-297">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="62a7d-297">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="62a7d-298">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="62a7d-298">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="62a7d-299">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="62a7d-299">INPUTS</span></span>

### <span data-ttu-id="62a7d-300">Nenhum</span><span class="sxs-lookup"><span data-stu-id="62a7d-300">None</span></span>

<span data-ttu-id="62a7d-301">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="62a7d-301">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="62a7d-302">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="62a7d-302">OUTPUTS</span></span>

### <span data-ttu-id="62a7d-303">System. Management. Automation. Remoting. PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="62a7d-303">System.Management.Automation.Remoting.PSSessionOption</span></span>

## <span data-ttu-id="62a7d-304">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="62a7d-304">NOTES</span></span>

<span data-ttu-id="62a7d-305">Se o parâmetro **SessionOption** não for usado em um comando para criar uma **PSSession**, as opções de sessão serão determinadas pelos valores de propriedade da `$PSSessionOption` variável de preferência, se ela estiver definida.</span><span class="sxs-lookup"><span data-stu-id="62a7d-305">If the **SessionOption** parameter is not used in a command to create a **PSSession**, the session options are determined by the property values of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="62a7d-306">Para obter mais informações sobre a `$PSSessionOption` variável, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="62a7d-306">For more information about the `$PSSessionOption` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="62a7d-307">As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções.</span><span class="sxs-lookup"><span data-stu-id="62a7d-307">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="62a7d-308">Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="62a7d-308">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="62a7d-309">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="62a7d-309">RELATED LINKS</span></span>

[<span data-ttu-id="62a7d-310">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="62a7d-310">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="62a7d-311">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="62a7d-311">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="62a7d-312">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="62a7d-312">New-PSSession</span></span>](New-PSSession.md)
