---
title: Working with WMI (Trabalhar com o WMI)
description: O PowerShell teve cmdlets para trabalhar com o WMI desde o início.
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 119bb3381ee55c70340da89d1c0690d84b3e70d2
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "99597589"
---
# <a name="chapter-7---working-with-wmi"></a><span data-ttu-id="57da4-103">Capítulo 7 – Como trabalhar com o WMI</span><span class="sxs-lookup"><span data-stu-id="57da4-103">Chapter 7 - Working with WMI</span></span>

## <a name="wmi-and-cim"></a><span data-ttu-id="57da4-104">WMI e CIM</span><span class="sxs-lookup"><span data-stu-id="57da4-104">WMI and CIM</span></span>

<span data-ttu-id="57da4-105">O PowerShell é fornecido por padrão com cmdlets para trabalhar com outras tecnologias, como WMI (Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="57da4-105">PowerShell ships by default with cmdlets for working with other technologies such as Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="57da4-106">Há vários cmdlets WMI nativos que existem no PowerShell sem a necessidade de instalar nenhum software ou módulo adicional.</span><span class="sxs-lookup"><span data-stu-id="57da4-106">There are several native WMI cmdlets that exist in PowerShell without having to install any additional software or modules.</span></span>

<span data-ttu-id="57da4-107">O PowerShell teve cmdlets para trabalhar com o WMI desde o início.</span><span class="sxs-lookup"><span data-stu-id="57da4-107">PowerShell has had cmdlets for working with WMI since the beginning.</span></span> <span data-ttu-id="57da4-108">`Get-Command` pode ser usado para determinar quais cmdlets do WMI existem no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57da4-108">`Get-Command` can be used to determine what WMI cmdlets exist in PowerShell.</span></span> <span data-ttu-id="57da4-109">Os resultados a seguir são do meu computador do ambiente de laboratório do Windows 10 que está executando o PowerShell versão 5.1.</span><span class="sxs-lookup"><span data-stu-id="57da4-109">The following results are from my Windows 10 lab environment computer that is running PowerShell version 5.1.</span></span> <span data-ttu-id="57da4-110">Seus resultados podem diferir dependendo da versão do PowerShell que você está executando.</span><span class="sxs-lookup"><span data-stu-id="57da4-110">Your results may differ depending on what PowerShell version you're running.</span></span>

```powershell
Get-Command -Noun WMI*
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-WmiObject                                      3.1.0.0    Microsof...
Cmdlet          Invoke-WmiMethod                                   3.1.0.0    Microsof...
Cmdlet          Register-WmiEvent                                  3.1.0.0    Microsof...
Cmdlet          Remove-WmiObject                                   3.1.0.0    Microsof...
Cmdlet          Set-WmiInstance                                    3.1.0.0    Microsof...
```

<span data-ttu-id="57da4-111">Os cmdlets do modelo CIM (CIM) foram introduzidos na versão 3.0 do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57da4-111">Common Information Model (CIM) cmdlets were introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="57da4-112">Os cmdlets do CIM são projetados para que possam ser usados em computadores Windows e não Windows.</span><span class="sxs-lookup"><span data-stu-id="57da4-112">The CIM cmdlets are designed so they can be used on both Windows and non-Windows machines.</span></span> <span data-ttu-id="57da4-113">Os cmdlets do WMI foram preteridos, portanto, minha recomendação é usar os cmdlets do CIM, em vez dos WMI mais antigos.</span><span class="sxs-lookup"><span data-stu-id="57da4-113">The WMI cmdlets are deprecated so my recommendation is to use the CIM cmdlets instead of the older WMI ones.</span></span>

<span data-ttu-id="57da4-114">Os cmdlets CIM estão todos contidos em um módulo.</span><span class="sxs-lookup"><span data-stu-id="57da4-114">The CIM cmdlets are all contained within a module.</span></span> <span data-ttu-id="57da4-115">Para obter uma lista dos cmdlets do CIM, use `Get-Command` com o parâmetro **Module**, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="57da4-115">To obtain a list of the CIM cmdlets, use `Get-Command` with the **Module** parameter as shown in the following example.</span></span>

```powershell
Get-Command -Module CimCmdlets
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Export-BinaryMiLog                                 1.0.0.0    CimCmdlets
Cmdlet          Get-CimAssociatedInstance                          1.0.0.0    CimCmdlets
Cmdlet          Get-CimClass                                       1.0.0.0    CimCmdlets
Cmdlet          Get-CimInstance                                    1.0.0.0    CimCmdlets
Cmdlet          Get-CimSession                                     1.0.0.0    CimCmdlets
Cmdlet          Import-BinaryMiLog                                 1.0.0.0    CimCmdlets
Cmdlet          Invoke-CimMethod                                   1.0.0.0    CimCmdlets
Cmdlet          New-CimInstance                                    1.0.0.0    CimCmdlets
Cmdlet          New-CimSession                                     1.0.0.0    CimCmdlets
Cmdlet          New-CimSessionOption                               1.0.0.0    CimCmdlets
Cmdlet          Register-CimIndicationEvent                        1.0.0.0    CimCmdlets
Cmdlet          Remove-CimInstance                                 1.0.0.0    CimCmdlets
Cmdlet          Remove-CimSession                                  1.0.0.0    CimCmdlets
Cmdlet          Set-CimInstance                                    1.0.0.0    CimCmdlets
```

<span data-ttu-id="57da4-116">Os cmdlets do CIM ainda permitem que você trabalhe com o WMI, portanto, não fique confuso quando alguém fizer a instrução "Quando eu consultar o WMI com os cmdlets CIM do PowerShell…"</span><span class="sxs-lookup"><span data-stu-id="57da4-116">The CIM cmdlets still allow you to work with WMI so don't be confused when someone makes the statement "When I query WMI with the PowerShell CIM cmdlets..."</span></span>

<span data-ttu-id="57da4-117">Como mencionei anteriormente, o WMI é uma tecnologia separada do PowerShell e você está usando apenas os cmdlets do CIM para acessar o WMI.</span><span class="sxs-lookup"><span data-stu-id="57da4-117">As I previously mentioned, WMI is a separate technology from PowerShell and you're just using the CIM cmdlets for accessing WMI.</span></span> <span data-ttu-id="57da4-118">Você pode encontrar um VBScript antigo que usa linguagem WQL para consultar o WMI, como no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="57da4-118">You may find an old VBScript that uses WMI Query Language (WQL) to query WMI such as in the following example.</span></span>

```vb
strComputer = "."
Set objWMIService = GetObject("winmgmts:" _
    & "{impersonationLevel=impersonate}!\\" & strComputer & "\root\cimv2")

Set colBIOS = objWMIService.ExecQuery _
    ("Select * from Win32_BIOS")

For each objBIOS in colBIOS
    Wscript.Echo "Manufacturer: " & objBIOS.Manufacturer
    Wscript.Echo "Name: " & objBIOS.Name
    Wscript.Echo "Serial Number: " & objBIOS.SerialNumber
    Wscript.Echo "SMBIOS Version: " & objBIOS.SMBIOSBIOSVersion
    Wscript.Echo "Version: " & objBIOS.Version
Next
```

<span data-ttu-id="57da4-119">Você pode usar a consulta WQL desse VBScript e usá-la com o cmdlet `Get-CimInstance` sem nenhuma modificação.</span><span class="sxs-lookup"><span data-stu-id="57da4-119">You can take the WQL query from that VBScript and use it with the `Get-CimInstance` cmdlet without any modifications.</span></span>

```powershell
Get-CimInstance -Query 'Select * from Win32_BIOS'
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 3810-1995-1654-4615-2295-2755-89
Version           : VRTUAL - 4001628
```

<span data-ttu-id="57da4-120">Isso não é como eu normalmente consulto o WMI com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57da4-120">That's not how I typically query WMI with PowerShell.</span></span> <span data-ttu-id="57da4-121">Mas funciona e permite que você migre facilmente os VBScripts existentes para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57da4-121">But it does work and allows you to easily migrate existing VBScripts to PowerShell.</span></span> <span data-ttu-id="57da4-122">Quando começo a escrever uma única linha para consultar o WMI, uso a sintaxe a seguir.</span><span class="sxs-lookup"><span data-stu-id="57da4-122">When I start out writing a one-liner to query WMI, I use the following syntax.</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 3810-1995-1654-4615-2295-2755-89
Version           : VRTUAL - 4001628
```

<span data-ttu-id="57da4-123">Se eu quiser apenas o número de série, poderei canalizar a saída para `Select-Object` e especificar apenas a propriedade **SerialNumber**.</span><span class="sxs-lookup"><span data-stu-id="57da4-123">If I only want the serial number, I can pipe the output to `Select-Object` and specify only the **SerialNumber** property.</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS | Select-Object -Property SerialNumber
```

```Output
SerialNumber
------------
3810-1995-1654-4615-2295-2755-89
```

<span data-ttu-id="57da4-124">Por padrão, há várias propriedades que são recuperadas em segundo plano que nunca são usadas.</span><span class="sxs-lookup"><span data-stu-id="57da4-124">By default, there are several properties that are retrieved behind the scenes that are never used.</span></span>
<span data-ttu-id="57da4-125">Talvez não importe muito ao consultar o WMI no computador local.</span><span class="sxs-lookup"><span data-stu-id="57da4-125">It may not matter much when querying WMI on the local computer.</span></span> <span data-ttu-id="57da4-126">Mas, quando você começa a consultar computadores remotos, isso representa não apenas tempo de processamento adicional para retornar essas informações, mas também informações adicionais desnecessárias das quais efetuar pull pela rede.</span><span class="sxs-lookup"><span data-stu-id="57da4-126">But once you start querying remote computers, it's not only additional processing time to return that information, but also additional unnecessary information to have to pull across the network.</span></span> <span data-ttu-id="57da4-127">`Get-CimInstance` tem um parâmetro **Property** que limita as informações recuperadas.</span><span class="sxs-lookup"><span data-stu-id="57da4-127">`Get-CimInstance` has a **Property** parameter that limits the information that's retrieved.</span></span> <span data-ttu-id="57da4-128">Isso torna a consulta ao WMI mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="57da4-128">This makes the query to WMI more efficient.</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS -Property SerialNumber |
Select-Object -Property SerialNumber
```

```Output
SerialNumber
------------
3810-1995-1654-4615-2295-2755-89
```

<span data-ttu-id="57da4-129">Os resultados anteriores retornaram um objeto.</span><span class="sxs-lookup"><span data-stu-id="57da4-129">The previous results returned an object.</span></span> <span data-ttu-id="57da4-130">Para retornar uma cadeia de caracteres simples, use o parâmetro **ExpandProperty**.</span><span class="sxs-lookup"><span data-stu-id="57da4-130">To return a simple string, use the **ExpandProperty** parameter.</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS -Property SerialNumber |
Select-Object -ExpandProperty SerialNumber
```

```Output
3810-1995-1654-4615-2295-2755-89
```

<span data-ttu-id="57da4-131">Você também pode usar o estilo pontilhado de sintaxe para retornar uma cadeia de caracteres simples.</span><span class="sxs-lookup"><span data-stu-id="57da4-131">You could also use the dotted style of syntax to return a simple string.</span></span> <span data-ttu-id="57da4-132">Isso elimina a necessidade de canalizar para `Select-Object`.</span><span class="sxs-lookup"><span data-stu-id="57da4-132">This eliminates the need to pipe to `Select-Object`.</span></span>

```powershell
(Get-CimInstance -ClassName Win32_BIOS -Property SerialNumber).SerialNumber
```

```Output
3810-1995-1654-4615-2295-2755-89
```

## <a name="query-remote-computers-with-the-cim-cmdlets"></a><span data-ttu-id="57da4-133">Consultar computadores remotos com os cmdlets do CIM</span><span class="sxs-lookup"><span data-stu-id="57da4-133">Query Remote Computers with the CIM cmdlets</span></span>

<span data-ttu-id="57da4-134">Ainda estou executando o PowerShell como um administrador local que é um usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="57da4-134">I'm still running PowerShell as a local admin who is a domain user.</span></span> <span data-ttu-id="57da4-135">Quando tento consultar informações de um computador remoto usando o cmdlet `Get-CimInstance`, recebo uma mensagem de erro de acesso negado.</span><span class="sxs-lookup"><span data-stu-id="57da4-135">When I try to query information from a remote computer using the `Get-CimInstance` cmdlet, I receive an access denied error message.</span></span>

```powershell
Get-CimInstance -ComputerName dc01 -ClassName Win32_BIOS
```

```Output
Get-CimInstance : Access is denied.
At line:1 char:1
+ Get-CimInstance -ComputerName dc01 -ClassName Win32_BIOS
+ ``````````````````````````````````````````````````````~~
    + CategoryInfo          : PermissionDenied: (root\cimv2:Win32_BIOS:String) [Get-CimI
   nstance], CimException
    + FullyQualifiedErrorId : HRESULT 0x80070005,Microsoft.Management.Infrastructure.Cim
   Cmdlets.GetCimInstanceCommand
    + PSComputerName        : dc01
```

<span data-ttu-id="57da4-136">Muitas pessoas têm preocupações com a segurança quando se trata do PowerShell, mas a verdade é que você tem exatamente as mesmas permissões no PowerShell e na GUI.</span><span class="sxs-lookup"><span data-stu-id="57da4-136">Many people have security concerns when it comes to PowerShell, but the truth is you have exactly the same permissions in PowerShell as you do in the GUI.</span></span> <span data-ttu-id="57da4-137">Nem mais nem menos.</span><span class="sxs-lookup"><span data-stu-id="57da4-137">No more and no less.</span></span> <span data-ttu-id="57da4-138">O problema no exemplo anterior é que o usuário que está executando o PowerShell não tem direitos para consultar informações de WMI do servidor DC01.</span><span class="sxs-lookup"><span data-stu-id="57da4-138">The problem in the previous example is that the user running PowerShell doesn't have rights to query WMI information from the DC01 server.</span></span> <span data-ttu-id="57da4-139">Eu poderia reiniciar o PowerShell como um administrador de domínio, pois `Get-CimInstance` não tem um parâmetro **Credential**.</span><span class="sxs-lookup"><span data-stu-id="57da4-139">I could relaunch PowerShell as a domain administrator since `Get-CimInstance` doesn't have a **Credential** parameter.</span></span> <span data-ttu-id="57da4-140">Mas, confie em mim: essa não é uma boa ideia, pois tudo que eu executar do PowerShell será executado como administrador de domínio. Isso pode ser perigoso do ponto de vista da segurança, dependendo da situação.</span><span class="sxs-lookup"><span data-stu-id="57da4-140">But, trust me, that isn't a good idea because then anything that I run from PowerShell would be running as a domain admin. That could be dangerous from a security standpoint depending on the situation.</span></span>

<span data-ttu-id="57da4-141">Usando o princípio de privilégios mínimos, vou elevar a minha conta do administrador de domínio por comando usando o parâmetro **Credential**, se um comando tiver um.</span><span class="sxs-lookup"><span data-stu-id="57da4-141">Using the principle of least privilege, I elevate to my domain admin account on a per command basis using the **Credential** parameter, if a command has one.</span></span> <span data-ttu-id="57da4-142">`Get-CimInstance` não tem um parâmetro **Credential** para que a solução neste cenário seja criar uma **CimSession** primeiro.</span><span class="sxs-lookup"><span data-stu-id="57da4-142">`Get-CimInstance` doesn't have a **Credential** parameter so the solution in this scenario is to create a **CimSession** first.</span></span> <span data-ttu-id="57da4-143">Em seguida, uso a **CimSession**, em vez de um nome do computador, para consultar o WMI no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="57da4-143">Then I use the **CimSession** instead of a computer name to query WMI on the remote computer.</span></span>

```powershell
$CimSession = New-CimSession -ComputerName dc01 -Credential (Get-Credential)
```

```Output
cmdlet Get-Credential at command pipeline position 1
Supply values for the following parameters:
Credential
```

<span data-ttu-id="57da4-144">A sessão CIM foi armazenada em uma variável chamada `$CimSession`.</span><span class="sxs-lookup"><span data-stu-id="57da4-144">The CIM session was stored in a variable named `$CimSession`.</span></span> <span data-ttu-id="57da4-145">Observe que também especifiquei o cmdlet `Get-Credential` entre parênteses para que ele seja executado primeiro, solicitando credenciais alternativas antes de criar a nova sessão.</span><span class="sxs-lookup"><span data-stu-id="57da4-145">Notice that I also specified the `Get-Credential` cmdlet in parentheses so that it executes first, prompting me for alternate credentials, before creating the new session.</span></span> <span data-ttu-id="57da4-146">Mostrarei outra maneira mais eficiente de especificar credenciais alternativas posteriormente neste capítulo, mas é importante entender esse conceito básico antes de torná-lo mais complicado.</span><span class="sxs-lookup"><span data-stu-id="57da4-146">I'll show you another more efficient way to specify alternate credentials later in this chapter, but it's important to understand this basic concept before making it more complicated.</span></span>

<span data-ttu-id="57da4-147">A sessão CIM criada no exemplo anterior agora pode ser usada com o cmdlet `Get-CimInstance` para consultar as informações do BIOS do WMI no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="57da4-147">The CIM session created in the previous example can now be used with the `Get-CimInstance` cmdlet to query the BIOS information from WMI on the remote computer.</span></span>

```powershell
Get-CimInstance -CimSession $CimSession -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 0986-6980-3916-0512-6608-8243-13
Version           : VRTUAL - 4001628
PSComputerName    : dc01
```

<span data-ttu-id="57da4-148">Há vários benefícios adicionais de usar sessões CIM, em vez de apenas especificar um nome do computador.</span><span class="sxs-lookup"><span data-stu-id="57da4-148">There are several additional benefits to using CIM sessions instead of just specifying a computer name.</span></span> <span data-ttu-id="57da4-149">Ao executar várias consultas no mesmo computador, usar uma sessão CIM é mais eficiente do que usar o nome do computador para cada consulta.</span><span class="sxs-lookup"><span data-stu-id="57da4-149">When running multiple queries to the same computer, using a CIM session is more efficient than using the computer name for each query.</span></span> <span data-ttu-id="57da4-150">A criação de uma sessão CIM só configura a conexão uma vez.</span><span class="sxs-lookup"><span data-stu-id="57da4-150">Creating a CIM session only sets up the connection once.</span></span>
<span data-ttu-id="57da4-151">Em seguida, várias consultas usam essa mesma sessão para recuperar informações.</span><span class="sxs-lookup"><span data-stu-id="57da4-151">Then, multiple queries use that same session to retrieve information.</span></span> <span data-ttu-id="57da4-152">Usar o nome do computador requer que os cmdlets configurem e derrubem a conexão com cada consulta individual.</span><span class="sxs-lookup"><span data-stu-id="57da4-152">Using the computer name requires the cmdlets to set up and tear down the connection with each individual query.</span></span>

<span data-ttu-id="57da4-153">O cmdlet `Get-CimInstance` usa o protocolo WSMan por padrão, o que significa que o computador remoto precisa do PowerShell versão 3.0 ou superior para se conectar.</span><span class="sxs-lookup"><span data-stu-id="57da4-153">The `Get-CimInstance` cmdlet uses the WSMan protocol by default, which means the remote computer needs PowerShell version 3.0 or higher to connect.</span></span> <span data-ttu-id="57da4-154">Na verdade, não é a versão do PowerShell que importa, é a versão da pilha.</span><span class="sxs-lookup"><span data-stu-id="57da4-154">It's actually not the PowerShell version that matters, it's the stack version.</span></span> <span data-ttu-id="57da4-155">A versão da pilha pode ser determinada usando o cmdlet `Test-WSMan`.</span><span class="sxs-lookup"><span data-stu-id="57da4-155">The stack version can be determined using the `Test-WSMan` cmdlet.</span></span>
<span data-ttu-id="57da4-156">Ele precisa ser a versão 3.0.</span><span class="sxs-lookup"><span data-stu-id="57da4-156">It needs to be version 3.0.</span></span> <span data-ttu-id="57da4-157">Essa é a versão que você encontrará com o PowerShell versão 3.0 e superior.</span><span class="sxs-lookup"><span data-stu-id="57da4-157">That's the version you'll find with PowerShell version 3.0 and higher.</span></span>

```powershell
Test-WSMan -ComputerName dc01
```

```Output
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd
ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd
ProductVendor   : Microsoft Corporation
ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 3.0
```

<span data-ttu-id="57da4-158">Os cmdlets mais antigos do WMI usam o protocolo DCOM, que é compatível com versões mais antigas do Windows.</span><span class="sxs-lookup"><span data-stu-id="57da4-158">The older WMI cmdlets use the DCOM protocol, which is compatible with older versions of Windows.</span></span> <span data-ttu-id="57da4-159">Mas o DCOM é normalmente bloqueado pelo firewall em versões mais recentes do Windows.</span><span class="sxs-lookup"><span data-stu-id="57da4-159">But DCOM is typically blocked by the firewall on newer versions of Windows.</span></span> <span data-ttu-id="57da4-160">O cmdlet `New-CimSessionOption` permite que você crie uma conexão de protocolo DCOM para uso com `New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="57da4-160">The `New-CimSessionOption` cmdlet allows you to create a DCOM protocol connection for use with `New-CimSession`.</span></span> <span data-ttu-id="57da4-161">Isso permite que o cmdlet `Get-CimInstance` seja usado para se comunicar com versões do Windows tão antigas quanto o Windows Server 2000.</span><span class="sxs-lookup"><span data-stu-id="57da4-161">This allows the `Get-CimInstance` cmdlet to be used to communicate with versions of Windows as old as Windows Server 2000.</span></span> <span data-ttu-id="57da4-162">Isso também significa que o PowerShell não é necessário no computador remoto ao usar o cmdlet `Get-CimInstance` com uma CimSession configurada para usar o protocolo DCOM.</span><span class="sxs-lookup"><span data-stu-id="57da4-162">This also means that PowerShell is not required on the remote computer when using the `Get-CimInstance` cmdlet with a CimSession that's configured to use the DCOM protocol.</span></span>

<span data-ttu-id="57da4-163">Crie a opção de protocolo DCOM usando o cmdlet `New-CimSessionOption` e armazene-a em uma variável.</span><span class="sxs-lookup"><span data-stu-id="57da4-163">Create the DCOM protocol option using the `New-CimSessionOption` cmdlet and store it in a variable.</span></span>

```powershell
$DCOM = New-CimSessionOption -Protocol Dcom
```

<span data-ttu-id="57da4-164">Para eficiência, você pode armazenar seu administrador de domínio ou credenciais elevadas em uma variável para que você não precise inseri-las constantemente para cada comando.</span><span class="sxs-lookup"><span data-stu-id="57da4-164">For efficiency, you can store your domain administrator or elevated credentials in a variable so you don't have to constantly enter them for each command.</span></span>

```powershell
$Cred = Get-Credential
```

```Output
cmdlet Get-Credential at command pipeline position 1
Supply values for the following parameters:
Credential
```

<span data-ttu-id="57da4-165">Tenho um servidor chamado SQL03 que executa o Windows Server 2008 (não R2).</span><span class="sxs-lookup"><span data-stu-id="57da4-165">I have a server named SQL03 that runs Windows Server 2008 (non-R2).</span></span> <span data-ttu-id="57da4-166">É o sistema operacional Windows Server mais recente que não tem o PowerShell instalado por padrão.</span><span class="sxs-lookup"><span data-stu-id="57da4-166">It's the newest Windows Server operating system that doesn't have PowerShell installed by default.</span></span>

<span data-ttu-id="57da4-167">Crie uma **CimSession** para SQL03 usando o protocolo DCOM.</span><span class="sxs-lookup"><span data-stu-id="57da4-167">Create a **CimSession** to SQL03 using the DCOM protocol.</span></span>

```powershell
$CimSession = New-CimSession -ComputerName sql03 -SessionOption $DCOM -Credential $Cred
```

<span data-ttu-id="57da4-168">Observe que, no comando anterior, desta vez eu especifiquei a variável chamada `$Cred` como o valor do parâmetro **Credential**, em vez de precisar inseri-las manualmente outra vez.</span><span class="sxs-lookup"><span data-stu-id="57da4-168">Notice in the previous command, this time I specified the variable named `$Cred` as the value for the **Credential** parameter instead of having to enter them manually again.</span></span>

<span data-ttu-id="57da4-169">A saída da consulta é a mesma, não importa o protocolo subjacente que está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="57da4-169">The output of the query is the same regardless of the underlying protocol being used.</span></span>

```powershell
Get-CimInstance -CimSession $CimSession -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 7237-7483-8873-8926-7271-5004-86
Version           : VRTUAL - 4001628
PSComputerName    : sql03
```

<span data-ttu-id="57da4-170">O cmdlet `Get-CimSession` é usado para ver quais **CimSessions** estão atualmente conectadas e quais protocolos elas estão usando.</span><span class="sxs-lookup"><span data-stu-id="57da4-170">The `Get-CimSession` cmdlet is used to see what **CimSessions** are currently connected and what protocols they're using.</span></span>

```powershell
Get-CimSession
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : 80742787-e38e-41b1-a7d7-fa1369cf1402
ComputerName : dc01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : 8fcabd81-43cf-4682-bd53-ccce1e24aecb
ComputerName : sql03
Protocol     : DCOM
```

<span data-ttu-id="57da4-171">Recupere e armazene as duas **CimSessions** criadas anteriormente em uma variável chamada `$CimSession`.</span><span class="sxs-lookup"><span data-stu-id="57da4-171">Retrieve and store both of the previously created **CimSessions** in a variable named `$CimSession`.</span></span>

```powershell
$CimSession = Get-CimSession
```

<span data-ttu-id="57da4-172">Confira ambos os computadores com um comando, um usando o protocolo WSMan e o outro com DCOM.</span><span class="sxs-lookup"><span data-stu-id="57da4-172">Query both of the computers with one command, one using the WSMan protocol and the other one with DCOM.</span></span>

```powershell
Get-CimInstance -CimSession $CimSession -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 0986-6980-3916-0512-6608-8243-13
Version           : VRTUAL - 4001628
PSComputerName    : dc01

SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 7237-7483-8873-8926-7271-5004-86
Version           : VRTUAL - 4001628
PSComputerName    : sql03
```

<span data-ttu-id="57da4-173">Escrevi vários artigos de blog sobre os cmdlets do WMI e do CIM.</span><span class="sxs-lookup"><span data-stu-id="57da4-173">I've written numerous blog articles about the WMI and CIM cmdlets.</span></span> <span data-ttu-id="57da4-174">Um dos mais úteis é sobre uma função que criei para determinar automaticamente se WSMan ou DCOM deve ser usado e configurar a sessão CIM automaticamente sem precisar descobrir manualmente qual delas.</span><span class="sxs-lookup"><span data-stu-id="57da4-174">One of the most useful ones is about a function that I created to automatically determine if WSMan or DCOM should be used and set up the CIM session automatically without having to figure out which one manually.</span></span> <span data-ttu-id="57da4-175">Esse artigo de blog é intitulado [Função do PowerShell para criar CimSessions a computadores remotos com fallback para DCOM][].</span><span class="sxs-lookup"><span data-stu-id="57da4-175">That blog article is titled [PowerShell Function to Create CimSessions to Remote Computers with Fallback to Dcom][].</span></span>

<span data-ttu-id="57da4-176">Quando você terminar com as sessões CIM, deverá removê-las com o cmdlet `Remove-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="57da4-176">When you're finished with the CIM sessions, you should remove them with the `Remove-CimSession` cmdlet.</span></span> <span data-ttu-id="57da4-177">Para remover todas as sessões CIM, basta canalizar `Get-CimSession` para `Remove-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="57da4-177">To remove all CIM sessions, simply pipe `Get-CimSession` to `Remove-CimSession`.</span></span>

```powershell
Get-CimSession | Remove-CimSession
```

## <a name="summary"></a><span data-ttu-id="57da4-178">Resumo</span><span class="sxs-lookup"><span data-stu-id="57da4-178">Summary</span></span>

<span data-ttu-id="57da4-179">Neste capítulo, você aprendeu a usar o PowerShell para trabalhar com o WMI em computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="57da4-179">In this chapter, you've learned about using PowerShell to work with WMI on both local and remote computers.</span></span> <span data-ttu-id="57da4-180">Você também aprendeu a usar os cmdlets do CIM para trabalhar com computadores remotos com o protocolo WSMan ou DCOM.</span><span class="sxs-lookup"><span data-stu-id="57da4-180">You've also learned how to use the CIM cmdlets to work with remote computers with both the WSMan or DCOM protocol.</span></span>

## <a name="review"></a><span data-ttu-id="57da4-181">Revisão</span><span class="sxs-lookup"><span data-stu-id="57da4-181">Review</span></span>

1. <span data-ttu-id="57da4-182">Qual é a diferença entre os cmdlets do WMI e do CIM?</span><span class="sxs-lookup"><span data-stu-id="57da4-182">What is the difference in the WMI and CIM cmdlets?</span></span>
1. <span data-ttu-id="57da4-183">Por padrão, que protocolo o cmdlet `Get-CimInstance` usa?</span><span class="sxs-lookup"><span data-stu-id="57da4-183">By default, what protocol does the `Get-CimInstance` cmdlet use?</span></span>
1. <span data-ttu-id="57da4-184">Quais são alguns dos benefícios de usar uma sessão CIM, em vez de especificar um nome do computador com `Get-CimInstance`?</span><span class="sxs-lookup"><span data-stu-id="57da4-184">What are some of the benefits of using a CIM session instead of specifying a computer name with `Get-CimInstance`?</span></span>
1. <span data-ttu-id="57da4-185">Como especificar um protocolo alternativo diferente do padrão para uso com `Get-CimInstance`?</span><span class="sxs-lookup"><span data-stu-id="57da4-185">How do you specify an alternate protocol other than the default one for use with `Get-CimInstance`?</span></span>
1. <span data-ttu-id="57da4-186">Como fechar ou remover sessões CIM?</span><span class="sxs-lookup"><span data-stu-id="57da4-186">How do you close or remove CIM sessions?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="57da4-187">Leitura recomendada</span><span class="sxs-lookup"><span data-stu-id="57da4-187">Recommended Reading</span></span>

- <span data-ttu-id="57da4-188">[about_WMI][]</span><span class="sxs-lookup"><span data-stu-id="57da4-188">[about_WMI][]</span></span>
- <span data-ttu-id="57da4-189">[about_WMI_Cmdlets][]</span><span class="sxs-lookup"><span data-stu-id="57da4-189">[about_WMI_Cmdlets][]</span></span>
- <span data-ttu-id="57da4-190">[about_WQL][]</span><span class="sxs-lookup"><span data-stu-id="57da4-190">[about_WQL][]</span></span>
- <span data-ttu-id="57da4-191">[Módulo CimCmdlets][]</span><span class="sxs-lookup"><span data-stu-id="57da4-191">[CimCmdlets Module][]</span></span>
- <span data-ttu-id="57da4-192">[Vídeo: Como usar cmdlets CIM e sessões CIM][]</span><span class="sxs-lookup"><span data-stu-id="57da4-192">[Video: Using CIM Cmdlets and CIM Sessions][]</span></span>

<!-- link references -->
[about_WMI]: /powershell/module/microsoft.powershell.core/about/about_wmi
[about_WMI_Cmdlets]: /powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets
[about_WQL]: /powershell/module/microsoft.powershell.core/about/about_wql
[Módulo CimCmdlets]: /powershell/module/cimcmdlets/
[CimCmdlets Module]: /powershell/module/cimcmdlets/
[Vídeo: Como usar cmdlets CIM e sessões CIM]: https://mikefrobbins.com/2013/09/12/phillyposh-user-group-meeting-presentation-follow-up-powershell-second-hop-problem-with-cimsessions/
[Video: Using CIM Cmdlets and CIM Sessions]: https://mikefrobbins.com/2013/09/12/phillyposh-user-group-meeting-presentation-follow-up-powershell-second-hop-problem-with-cimsessions/
[Função do PowerShell para criar CimSessions a computadores remotos com fallback para DCOM]: https://mikefrobbins.com/2014/08/28/powershell-function-to-create-cimsessions-to-remote-computers-with-fallback-to-dcom/
[PowerShell Function to Create CimSessions to Remote Computers with Fallback to Dcom]: https://mikefrobbins.com/2014/08/28/powershell-function-to-create-cimsessions-to-remote-computers-with-fallback-to-dcom/
