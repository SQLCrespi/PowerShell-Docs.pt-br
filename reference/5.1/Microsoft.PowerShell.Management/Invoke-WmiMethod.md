---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-wmimethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WmiMethod
ms.openlocfilehash: e9743488e86429e5cc3252162e51268a7978b79d
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "93194832"
---
# <span data-ttu-id="0fafe-103">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="0fafe-103">Invoke-WmiMethod</span></span>

## <span data-ttu-id="0fafe-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0fafe-104">SYNOPSIS</span></span>
<span data-ttu-id="0fafe-105">Chama os métodos WMI.</span><span class="sxs-lookup"><span data-stu-id="0fafe-105">Calls WMI methods.</span></span>

## <span data-ttu-id="0fafe-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0fafe-106">SYNTAX</span></span>

### <span data-ttu-id="0fafe-107">classe (padrão)</span><span class="sxs-lookup"><span data-stu-id="0fafe-107">class (Default)</span></span>

```
Invoke-WmiMethod [-Class] <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0fafe-108">objeto</span><span class="sxs-lookup"><span data-stu-id="0fafe-108">object</span></span>

```
Invoke-WmiMethod -InputObject <ManagementObject> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0fafe-109">caminho</span><span class="sxs-lookup"><span data-stu-id="0fafe-109">path</span></span>

```
Invoke-WmiMethod -Path <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0fafe-110">WQLQuery</span><span class="sxs-lookup"><span data-stu-id="0fafe-110">WQLQuery</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0fafe-111">Consulta</span><span class="sxs-lookup"><span data-stu-id="0fafe-111">query</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0fafe-112">list</span><span class="sxs-lookup"><span data-stu-id="0fafe-112">list</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0fafe-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fafe-113">DESCRIPTION</span></span>

<span data-ttu-id="0fafe-114">O `Invoke-WmiMethod` cmdlet chama os métodos de objetos Instrumentação de gerenciamento do Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="0fafe-114">The `Invoke-WmiMethod` cmdlet calls the methods of Windows Management Instrumentation (WMI) objects.</span></span>

<span data-ttu-id="0fafe-115">Novos cmdlets de modelo CIM (CIM), introduzidos no Windows PowerShell 3,0, executam as mesmas tarefas que os cmdlets do WMI.</span><span class="sxs-lookup"><span data-stu-id="0fafe-115">New Common Information Model (CIM) cmdlets, introduced in Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="0fafe-116">Os cmdlets do CIM estão em conformidade com os padrões do WSMan (WS-Management) e com o padrão CIM, que permite que os cmdlets usem as mesmas técnicas para gerenciar computadores Windows e aqueles que executam outros sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="0fafe-116">The CIM cmdlets comply with WS-Management (WSMan) standards and with the CIM standard, which enables the cmdlets to use the same techniques to manage Windows computers and those running other operating systems.</span></span> <span data-ttu-id="0fafe-117">Em vez de usar `Invoke-WmiMethod` , considere o uso [de Invoke-CimMethod](../cimcmdlets/invoke-cimmethod.md).</span><span class="sxs-lookup"><span data-stu-id="0fafe-117">Instead of using `Invoke-WmiMethod`, consider using [Invoke-CimMethod](../cimcmdlets/invoke-cimmethod.md).</span></span>

## <span data-ttu-id="0fafe-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0fafe-118">EXAMPLES</span></span>

### <span data-ttu-id="0fafe-119">Exemplo 1: listar a ordem necessária de objetos WMI</span><span class="sxs-lookup"><span data-stu-id="0fafe-119">Example 1: List the required order of WMI objects</span></span>

```powershell
([wmiclass]'Win32_Volume').GetMethodParameters('Format')
```

```Output
__GENUS           : 2
__CLASS           : __PARAMETERS
__SUPERCLASS      :
__DYNASTY         : __PARAMETERS
__RELPATH         :
__PROPERTY_COUNT  : 6
__DERIVATION      : {}
__SERVER          :
__NAMESPACE       :
__PATH            :
ClusterSize       : 0
EnableCompression : False
FileSystem        : NTFS
Label             :
QuickFormat       : False
Version           : 0
PSComputerName    :
```

<span data-ttu-id="0fafe-120">Esse comando lista a ordem dos objetos exigida.</span><span class="sxs-lookup"><span data-stu-id="0fafe-120">This command lists the required order of the objects.</span></span> <span data-ttu-id="0fafe-121">Invocar o WMI no PowerShell 3.0 difere de métodos alternativos e requer que os valores de objeto sejam inseridos em uma ordem específica.</span><span class="sxs-lookup"><span data-stu-id="0fafe-121">To invoke WMI in PowerShell 3.0 differs from alternate methods, and requires that object values are entered in a specific order.</span></span>

### <span data-ttu-id="0fafe-122">Exemplo 2: iniciar uma instância de um aplicativo</span><span class="sxs-lookup"><span data-stu-id="0fafe-122">Example 2: Start an instance of an application</span></span>

```powershell
([Wmiclass]'Win32_Process').GetMethodParameters('Create')
```

```Output
__GENUS                   : 2
__CLASS                   : __PARAMETERS
__SUPERCLASS              :
__DYNASTY                 : __PARAMETERS
__RELPATH                 :
__PROPERTY_COUNT          : 3
__DERIVATION              : {}
__SERVER                  :
__NAMESPACE               :
__PATH                    :
CommandLine               :
CurrentDirectory          :
ProcessStartupInformation :
PSComputerName            :
```

```powershell
Invoke-WmiMethod -Path win32_process -Name create -ArgumentList notepad.exe
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 2
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ProcessId        : 11312
ReturnValue      : 0
PSComputerName   :
```

<span data-ttu-id="0fafe-123">Esse comando inicia uma instância do bloco de notas chamando o `Create` método da classe **Win32_Process** .</span><span class="sxs-lookup"><span data-stu-id="0fafe-123">This command starts an instance of Notepad by calling the `Create` method of the **Win32_Process** class.</span></span>

<span data-ttu-id="0fafe-124">A propriedade **ReturnValue** é populada com um 0 e a propriedade **ProcessId** é populada com um inteiro (o próximo número de ID do processo) se o comando for concluído.</span><span class="sxs-lookup"><span data-stu-id="0fafe-124">The **ReturnValue** property is populated with a 0, and the **ProcessId** property is populated with an integer (the next process ID number) if the command is completed.</span></span>

### <span data-ttu-id="0fafe-125">Exemplo 3: renomear um arquivo</span><span class="sxs-lookup"><span data-stu-id="0fafe-125">Example 3: Rename a file</span></span>

```powershell
Invoke-WmiMethod -Path "CIM_DataFile.Name='C:\scripts\test.txt'" -Name Rename -ArgumentList "C:\scripts\test_bu.txt"
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ReturnValue      : 0
```

<span data-ttu-id="0fafe-126">Este comando renomeia um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0fafe-126">This command renames a file.</span></span> <span data-ttu-id="0fafe-127">Ele usa o parâmetro **path** para fazer referência a uma instância da classe **CIM_Datafile** .</span><span class="sxs-lookup"><span data-stu-id="0fafe-127">It uses the **Path** parameter to reference an instance of the **CIM_DataFile** class.</span></span> <span data-ttu-id="0fafe-128">Em seguida, ele aplica o método Rename àquela instância específica.</span><span class="sxs-lookup"><span data-stu-id="0fafe-128">Then, it applies the Rename method to that particular instance.</span></span>

<span data-ttu-id="0fafe-129">A propriedade **ReturnValue** será populada com um 0 se o comando for concluído.</span><span class="sxs-lookup"><span data-stu-id="0fafe-129">The **ReturnValue** property is populated with a 0 if the command is completed.</span></span>

### <span data-ttu-id="0fafe-130">Exemplo 4: passando uma matriz de valores usando `-ArgumentList`</span><span class="sxs-lookup"><span data-stu-id="0fafe-130">Example 4: Passing an array of values using `-ArgumentList`</span></span>

<span data-ttu-id="0fafe-131">Um exemplo que usa uma matriz de objetos `$binSD` seguida por um `$null` valor.</span><span class="sxs-lookup"><span data-stu-id="0fafe-131">An example using an array of objects `$binSD` followed by a `$null` value.</span></span>

```powershell
$acl = get-acl test.txt
$binSD = $acl.GetSecurityDescriptorBinaryForm()
Invoke-WmiMethod -class Win32_SecurityDescriptorHelper -Name BinarySDToSDDL -ArgumentList $binSD, $null
```

## <span data-ttu-id="0fafe-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0fafe-132">PARAMETERS</span></span>

### <span data-ttu-id="0fafe-133">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="0fafe-133">-ArgumentList</span></span>

<span data-ttu-id="0fafe-134">Especifica os parâmetros a passar para o método chamado.</span><span class="sxs-lookup"><span data-stu-id="0fafe-134">Specifies the parameters to pass to the called method.</span></span> <span data-ttu-id="0fafe-135">O valor desse parâmetro deve ser uma matriz de objetos e deve aparecer na ordem exigida pelo método chamado.</span><span class="sxs-lookup"><span data-stu-id="0fafe-135">The value of this parameter must be an array of objects, and they must appear in the order required by the called method.</span></span> <span data-ttu-id="0fafe-136">O `Invoke-CimCommand` cmdlet não tem essas limitações.</span><span class="sxs-lookup"><span data-stu-id="0fafe-136">The `Invoke-CimCommand` cmdlet does not have these limitations.</span></span>

<span data-ttu-id="0fafe-137">Para determinar a ordem na qual listar esses objetos, execute o `GetMethodParameters()` método na classe WMI, conforme ilustrado no exemplo 1, próximo ao final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="0fafe-137">To determine the order in which to list those objects, run the `GetMethodParameters()` method on the WMI class, as illustrated in Example 1, near the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0fafe-138">Se o primeiro valor é uma matriz que contém mais de um elemento, um segundo valor de $null é necessário.</span><span class="sxs-lookup"><span data-stu-id="0fafe-138">If the first value is an array that contains more than one element, a second value of $null is required.</span></span> <span data-ttu-id="0fafe-139">Caso contrário, o comando gera um erro, como "Não é possível converter o objeto do tipo 'System.Byte' para o tipo 'System. Array'.".</span><span class="sxs-lookup"><span data-stu-id="0fafe-139">Otherwise, the command generates an error, such as "Unable to cast object of type 'System.Byte' to type 'System.Array'.".</span></span> <span data-ttu-id="0fafe-140">Consulte o exemplo 4 acima.</span><span class="sxs-lookup"><span data-stu-id="0fafe-140">See example 4 above.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: class, object, path
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-141">-AsJob</span><span class="sxs-lookup"><span data-stu-id="0fafe-141">-AsJob</span></span>

<span data-ttu-id="0fafe-142">Indica que esse cmdlet executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="0fafe-142">Indicates that this cmdlet runs the command as a background job.</span></span> <span data-ttu-id="0fafe-143">Use este parâmetro para executar comandos que levam muito tempo para serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="0fafe-143">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="0fafe-144">Quando você usa o parâmetro **AsJob** , o comando retorna um objeto que representa o trabalho em segundo plano e, em seguida, exibe o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="0fafe-144">When you use the **AsJob** parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span> <span data-ttu-id="0fafe-145">É possível continuar a trabalhar na sessão enquanto o trabalho é concluído.</span><span class="sxs-lookup"><span data-stu-id="0fafe-145">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="0fafe-146">Se `Invoke-WmiMethod` é usado em um computador remoto, o trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local.</span><span class="sxs-lookup"><span data-stu-id="0fafe-146">If `Invoke-WmiMethod` is used against a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="0fafe-147">Para gerenciar o trabalho, use os cmdlets que contêm o substantivo Job (os cmdlets Job).</span><span class="sxs-lookup"><span data-stu-id="0fafe-147">To manage the job, use the cmdlets that contain the Job noun (the Job cmdlets).</span></span> <span data-ttu-id="0fafe-148">Para obter os resultados do trabalho, use o cmdlet Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="0fafe-148">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="0fafe-149">Para utilizar esse parâmetro com computadores remotos, os computadores local e remoto precisam ser configurados para acesso remoto.</span><span class="sxs-lookup"><span data-stu-id="0fafe-149">To use this parameter with remote computers, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="0fafe-150">Além disso, você deve iniciar o Windows PowerShell usando a opção Executar como administrador no Windows Vista e versões posteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="0fafe-150">Additionally, you must start Windows PowerShell by using the Run as administrator option in Windows Vista and later versions of Windows.</span></span> <span data-ttu-id="0fafe-151">Para obter mais informações, consulte about_Remote_Requirements.</span><span class="sxs-lookup"><span data-stu-id="0fafe-151">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="0fafe-152">Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte about_Jobs e about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="0fafe-152">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="0fafe-153">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="0fafe-153">-Authentication</span></span>

<span data-ttu-id="0fafe-154">Especifica o nível de autenticação a ser usado com a conexão WMI.</span><span class="sxs-lookup"><span data-stu-id="0fafe-154">Specifies the authentication level to be used with the WMI connection.</span></span> <span data-ttu-id="0fafe-155">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="0fafe-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0fafe-156">-1: inalterado</span><span class="sxs-lookup"><span data-stu-id="0fafe-156">-1: Unchanged</span></span>
- <span data-ttu-id="0fafe-157">0: padrão</span><span class="sxs-lookup"><span data-stu-id="0fafe-157">0: Default</span></span>
- <span data-ttu-id="0fafe-158">1: nenhum (nenhuma autenticação em executada.)</span><span class="sxs-lookup"><span data-stu-id="0fafe-158">1: None (No authentication in performed.)</span></span>
- <span data-ttu-id="0fafe-159">2: conectar (a autenticação é executada somente quando o cliente estabelece uma relação com o aplicativo.)</span><span class="sxs-lookup"><span data-stu-id="0fafe-159">2: Connect (Authentication is performed only when the client establishes a relationship with the application.)</span></span>
- <span data-ttu-id="0fafe-160">3: chamada (a autenticação é executada somente no início de cada chamada quando o aplicativo recebe a solicitação).</span><span class="sxs-lookup"><span data-stu-id="0fafe-160">3: Call (Authentication is performed only at the beginning of each call when the application receives the request.)</span></span>
- <span data-ttu-id="0fafe-161">4: pacote (a autenticação é executada em todos os dados que são recebidos do cliente.)</span><span class="sxs-lookup"><span data-stu-id="0fafe-161">4: Packet (Authentication is performed on all the data that is received from the client.)</span></span>
- <span data-ttu-id="0fafe-162">5: PacketIntegrity (todos os dados transferidos entre o cliente e o aplicativo são autenticados e verificados.)</span><span class="sxs-lookup"><span data-stu-id="0fafe-162">5: PacketIntegrity (All the data that is transferred between the client and the application is authenticated and verified.)</span></span>
- <span data-ttu-id="0fafe-163">6: PacketPrivacy (as propriedades dos outros níveis de autenticação são usadas e todos os dados são criptografados).</span><span class="sxs-lookup"><span data-stu-id="0fafe-163">6: PacketPrivacy (The properties of the other authentication levels are used, and all the data is encrypted.)</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-164">-Autoridade</span><span class="sxs-lookup"><span data-stu-id="0fafe-164">-Authority</span></span>

<span data-ttu-id="0fafe-165">Especifica a autoridade a ser usada para autenticar a conexão WMI.</span><span class="sxs-lookup"><span data-stu-id="0fafe-165">Specifies the authority to use to authenticate the WMI connection.</span></span> <span data-ttu-id="0fafe-166">Você pode especificar a autenticação NTLM (Windows NT LAN Manager) ou Kerberos padrão.</span><span class="sxs-lookup"><span data-stu-id="0fafe-166">You can specify standard Windows NT LAN Manager (NTLM) or Kerberos authentication.</span></span> <span data-ttu-id="0fafe-167">Para usar o NTLM, defina a configuração da autoridade como ntlmdomain: \<DomainName\>, em que \<DomainName\> identifica um nome de domínio válido do NTLM.</span><span class="sxs-lookup"><span data-stu-id="0fafe-167">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span> <span data-ttu-id="0fafe-168">Para usar o Kerberos, especifique kerberos: \<DomainName\ServerName\>.</span><span class="sxs-lookup"><span data-stu-id="0fafe-168">To use Kerberos, specify kerberos:\<DomainName\ServerName\>.</span></span> <span data-ttu-id="0fafe-169">Não é possível, ao conectar-se ao computador local, incluir a configuração da autoridade.</span><span class="sxs-lookup"><span data-stu-id="0fafe-169">You cannot include the authority setting when you connect to the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-170">-Classe</span><span class="sxs-lookup"><span data-stu-id="0fafe-170">-Class</span></span>

<span data-ttu-id="0fafe-171">Especifica a classe WMI que contém um método estático para realização de chamadas.</span><span class="sxs-lookup"><span data-stu-id="0fafe-171">Specifies the WMI class that contains a static method to call.</span></span>

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-172">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0fafe-172">-ComputerName</span></span>

<span data-ttu-id="0fafe-173">Especifica, como uma matriz de cadeia de caracteres, os computadores em que esse cmdlet executa o comando.</span><span class="sxs-lookup"><span data-stu-id="0fafe-173">Specifies, as a string array, the computers that this cmdlet runs the command on.</span></span> <span data-ttu-id="0fafe-174">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="0fafe-174">The default is the local computer.</span></span>

<span data-ttu-id="0fafe-175">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores.</span><span class="sxs-lookup"><span data-stu-id="0fafe-175">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span> <span data-ttu-id="0fafe-176">Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.</span><span class="sxs-lookup"><span data-stu-id="0fafe-176">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="0fafe-177">Esse parâmetro não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0fafe-177">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="0fafe-178">Você pode usar o parâmetro **ComputerName** , mesmo que seu computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="0fafe-178">You can use the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: class, path, WQLQuery, query, list
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-179">-Credential</span><span class="sxs-lookup"><span data-stu-id="0fafe-179">-Credential</span></span>

<span data-ttu-id="0fafe-180">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="0fafe-180">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="0fafe-181">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="0fafe-181">The default is the current user.</span></span> <span data-ttu-id="0fafe-182">Digite um nome de usuário, como `User01` , `Domain01\User01` ou `User@Contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="0fafe-182">Type a user name, such as `User01`, `Domain01\User01`, or `User@Contoso.com`.</span></span> <span data-ttu-id="0fafe-183">Ou insira um objeto **PSCredential** , como um objeto que é retornado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="0fafe-183">Or, enter a **PSCredential** object, such as an object that is returned by the Get-Credential cmdlet.</span></span> <span data-ttu-id="0fafe-184">Quando você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="0fafe-184">When you type a user name, you will be prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-185">-EnableAllPrivileges</span><span class="sxs-lookup"><span data-stu-id="0fafe-185">-EnableAllPrivileges</span></span>

<span data-ttu-id="0fafe-186">Indica que esse cmdlet habilita todos os privilégios do usuário atual antes que o comando faça a chamada WMI.</span><span class="sxs-lookup"><span data-stu-id="0fafe-186">Indicates that this cmdlet enables all the privileges of the current user before the command makes the WMI call.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-187">-Representação</span><span class="sxs-lookup"><span data-stu-id="0fafe-187">-Impersonation</span></span>

<span data-ttu-id="0fafe-188">Especifica o nível de representação a ser usado.</span><span class="sxs-lookup"><span data-stu-id="0fafe-188">Specifies the impersonation level to use.</span></span> <span data-ttu-id="0fafe-189">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="0fafe-189">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0fafe-190">0: padrão (lê o registro local para o nível de representação padrão, que geralmente é definido como "3: Impersonate".)</span><span class="sxs-lookup"><span data-stu-id="0fafe-190">0: Default (Reads the local registry for the default impersonation level, which is usually set to "3: Impersonate".)</span></span>
- <span data-ttu-id="0fafe-191">1: anônimo (oculta as credenciais do chamador).</span><span class="sxs-lookup"><span data-stu-id="0fafe-191">1: Anonymous (Hides the credentials of the caller.)</span></span>
- <span data-ttu-id="0fafe-192">2: identificar (permite que os objetos consultem as credenciais do chamador).</span><span class="sxs-lookup"><span data-stu-id="0fafe-192">2: Identify (Allows objects to query the credentials of the caller.)</span></span>
- <span data-ttu-id="0fafe-193">3: representar (permite que os objetos usem as credenciais do chamador.)</span><span class="sxs-lookup"><span data-stu-id="0fafe-193">3: Impersonate (Allows objects to use the credentials of the caller.)</span></span>
- <span data-ttu-id="0fafe-194">4: delegate (permite que os objetos permitam que outros objetos usem as credenciais do chamador.)</span><span class="sxs-lookup"><span data-stu-id="0fafe-194">4: Delegate (Allows objects to permit other objects to use the credentials of the caller.)</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-195">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0fafe-195">-InputObject</span></span>

<span data-ttu-id="0fafe-196">Especifica um objeto **ManagementObject** a ser usado como entrada.</span><span class="sxs-lookup"><span data-stu-id="0fafe-196">Specifies a **ManagementObject** object to use as input.</span></span> <span data-ttu-id="0fafe-197">Quando esse parâmetro é usado, todos os outros parâmetros, exceto os parâmetros **Flag** e **Argument** , são ignorados.</span><span class="sxs-lookup"><span data-stu-id="0fafe-197">When this parameter is used, all other parameters except the **Flag** and **Argument** parameters are ignored.</span></span>

```yaml
Type: System.Management.ManagementObject
Parameter Sets: object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-198">-Localidade</span><span class="sxs-lookup"><span data-stu-id="0fafe-198">-Locale</span></span>

<span data-ttu-id="0fafe-199">Especifica o local preferido para objetos WMI.</span><span class="sxs-lookup"><span data-stu-id="0fafe-199">Specifies the preferred locale for WMI objects.</span></span> <span data-ttu-id="0fafe-200">Especifique o valor do parâmetro **locale** como uma matriz no `MS_<LCID>` formato na ordem preferida.</span><span class="sxs-lookup"><span data-stu-id="0fafe-200">Specify the value of the **Locale** parameter as an array in the `MS_<LCID>` format in the preferred order.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-201">-Name</span><span class="sxs-lookup"><span data-stu-id="0fafe-201">-Name</span></span>

<span data-ttu-id="0fafe-202">Especifica o nome do método a ser invocado.</span><span class="sxs-lookup"><span data-stu-id="0fafe-202">Specifies the name of the method to be invoked.</span></span> <span data-ttu-id="0fafe-203">Este parâmetro é obrigatório e não pode ser nulo ou vazio.</span><span class="sxs-lookup"><span data-stu-id="0fafe-203">This parameter is mandatory and cannot be null or empty.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-204">-Namespace</span><span class="sxs-lookup"><span data-stu-id="0fafe-204">-Namespace</span></span>

<span data-ttu-id="0fafe-205">Quando usado com o parâmetro **Class** , esse parâmetro especifica o namespace do repositório WMI em que a classe WMI ou o objeto referenciado está localizado.</span><span class="sxs-lookup"><span data-stu-id="0fafe-205">When used with the **Class** parameter, this parameter specifies the WMI repository namespace where the referenced WMI class or object is located.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-206">-Path</span><span class="sxs-lookup"><span data-stu-id="0fafe-206">-Path</span></span>

<span data-ttu-id="0fafe-207">Especifica o caminho do objeto WMI de uma classe WMI, ou então especifica o caminho do objeto WMI de uma instância de uma classe WMI.</span><span class="sxs-lookup"><span data-stu-id="0fafe-207">Specifies the WMI object path of a WMI class, or specifies the WMI object path of an instance of a WMI class.</span></span> <span data-ttu-id="0fafe-208">A classe ou a instância especificada deve conter o método especificado no parâmetro **Name** .</span><span class="sxs-lookup"><span data-stu-id="0fafe-208">The class or the instance that you specify must contain the method that is specified in the **Name** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fafe-209">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0fafe-209">-ThrottleLimit</span></span>

<span data-ttu-id="0fafe-210">Especifica um valor de limitação para o número de operações WMI que podem ser executadas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="0fafe-210">Specifies a throttle value for the number of WMI operations that can be executed simultaneously.</span></span>
<span data-ttu-id="0fafe-211">Esse parâmetro é usado junto com o parâmetro **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="0fafe-211">This parameter is used together with the **AsJob** parameter.</span></span> <span data-ttu-id="0fafe-212">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="0fafe-212">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="0fafe-213">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0fafe-213">-Confirm</span></span>

<span data-ttu-id="0fafe-214">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0fafe-214">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0fafe-215">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0fafe-215">-WhatIf</span></span>

<span data-ttu-id="0fafe-216">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0fafe-216">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0fafe-217">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0fafe-217">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0fafe-218">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0fafe-218">CommonParameters</span></span>

<span data-ttu-id="0fafe-219">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0fafe-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0fafe-220">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0fafe-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0fafe-221">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0fafe-221">INPUTS</span></span>

### <span data-ttu-id="0fafe-222">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0fafe-222">None</span></span>

<span data-ttu-id="0fafe-223">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="0fafe-223">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="0fafe-224">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0fafe-224">OUTPUTS</span></span>

### <span data-ttu-id="0fafe-225">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0fafe-225">None</span></span>

<span data-ttu-id="0fafe-226">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="0fafe-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0fafe-227">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0fafe-227">NOTES</span></span>

## <span data-ttu-id="0fafe-228">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0fafe-228">RELATED LINKS</span></span>

[<span data-ttu-id="0fafe-229">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0fafe-229">Get-WSManInstance</span></span>](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[<span data-ttu-id="0fafe-230">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="0fafe-230">Invoke-WSManAction</span></span>](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[<span data-ttu-id="0fafe-231">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0fafe-231">New-WSManInstance</span></span>](../Microsoft.WsMan.Management/New-WSManInstance.md)

[<span data-ttu-id="0fafe-232">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0fafe-232">Remove-WSManInstance</span></span>](../Microsoft.WsMan.Management/Remove-WSManInstance.md)

[<span data-ttu-id="0fafe-233">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="0fafe-233">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="0fafe-234">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="0fafe-234">Remove-WmiObject</span></span>](Remove-WmiObject.md)

[<span data-ttu-id="0fafe-235">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="0fafe-235">Set-WmiInstance</span></span>](Set-WmiInstance.md)
