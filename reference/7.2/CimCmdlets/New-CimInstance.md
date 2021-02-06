---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimInstance
ms.openlocfilehash: d81117ad6885d660e31f031bd8134096db91b7da
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603327"
---
# <span data-ttu-id="e4a34-102">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e4a34-102">New-CimInstance</span></span>

## <span data-ttu-id="e4a34-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e4a34-103">SYNOPSIS</span></span>
<span data-ttu-id="e4a34-104">Cria uma instância CIM.</span><span class="sxs-lookup"><span data-stu-id="e4a34-104">Creates a CIM instance.</span></span>

## <span data-ttu-id="e4a34-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e4a34-105">SYNTAX</span></span>

### <span data-ttu-id="e4a34-106">ClassNameComputerSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="e4a34-106">ClassNameComputerSet (Default)</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e4a34-107">ClassNameSessionSet</span><span class="sxs-lookup"><span data-stu-id="e4a34-107">ClassNameSessionSet</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e4a34-108">ResourceUriSessionSet</span><span class="sxs-lookup"><span data-stu-id="e4a34-108">ResourceUriSessionSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e4a34-109">ResourceUriComputerSet</span><span class="sxs-lookup"><span data-stu-id="e4a34-109">ResourceUriComputerSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e4a34-110">CimClassSessionSet</span><span class="sxs-lookup"><span data-stu-id="e4a34-110">CimClassSessionSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e4a34-111">CimClassComputerSet</span><span class="sxs-lookup"><span data-stu-id="e4a34-111">CimClassComputerSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e4a34-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e4a34-112">DESCRIPTION</span></span>

<span data-ttu-id="e4a34-113">O `New-CimInstance` cmdlet cria uma instância de uma classe CIM com base na definição de classe no computador local ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="e4a34-113">The `New-CimInstance` cmdlet creates an instance of a CIM class based on the class definition on either the local computer or a remote computer.</span></span> <span data-ttu-id="e4a34-114">Por padrão, o `New-CimInstance` cmdlet cria uma instância no computador local.</span><span class="sxs-lookup"><span data-stu-id="e4a34-114">By default, the `New-CimInstance` cmdlet creates an instance on the local computer.</span></span>

## <span data-ttu-id="e4a34-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e4a34-115">EXAMPLES</span></span>

### <span data-ttu-id="e4a34-116">Exemplo 1: criar uma instância de uma classe CIM</span><span class="sxs-lookup"><span data-stu-id="e4a34-116">Example 1: Create an instance of a CIM class</span></span>

<span data-ttu-id="e4a34-117">Este exemplo cria uma instância de uma classe CIM denominada win32_environment no namespace raiz/cimv2 no computador.</span><span class="sxs-lookup"><span data-stu-id="e4a34-117">This example creates an instance of a CIM Class named win32_environment in the root/cimv2 namespace on the computer.</span></span>

```powershell
New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";VariableValue="testvalue";UserName="domain\user"}
```

<span data-ttu-id="e4a34-118">Nenhuma validação no lado do cliente é executada se a classe não existir, se as propriedades estiverem erradas ou se o servidor rejeitar a chamada.</span><span class="sxs-lookup"><span data-stu-id="e4a34-118">No client side validation is performed if the class does not exist, the properties are wrong, or if the server rejects the call.</span></span> <span data-ttu-id="e4a34-119">Se a instância for criada com êxito, o cmdlet produzirá a instância recém-criada.</span><span class="sxs-lookup"><span data-stu-id="e4a34-119">If the instance is created successfully, the cmdlet outputs the newly created instance.</span></span>

### <span data-ttu-id="e4a34-120">Exemplo 2: criar uma instância de uma classe CIM usando um esquema de classe</span><span class="sxs-lookup"><span data-stu-id="e4a34-120">Example 2: Create an instance of a CIM class using a class schema</span></span>

<span data-ttu-id="e4a34-121">Este exemplo recupera um objeto de classe CIM e o armazena em uma variável chamada `$class` .</span><span class="sxs-lookup"><span data-stu-id="e4a34-121">This example retrieves a CIM class object and stores it in a variable named `$class`.</span></span> <span data-ttu-id="e4a34-122">O conteúdo da variável é passado para o `New-CimInstance` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e4a34-122">The contents of the variable are then passed to the `New-CimInstance` cmdlet.</span></span>

```powershell
$class = Get-CimClass -ClassName Win32_Environment
New-CimInstance -CimClass $class -Property @{Name="testvar";VariableValue="testvalue";UserName="Contoso\User1"}
```

### <span data-ttu-id="e4a34-123">Exemplo 3: criar uma instância dinâmica no cliente</span><span class="sxs-lookup"><span data-stu-id="e4a34-123">Example 3: Create a dynamic instance on the client</span></span>

<span data-ttu-id="e4a34-124">Este exemplo cria uma instância dinâmica de uma classe CIM chamada **Win32_Process** no computador cliente sem obter a instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="e4a34-124">This example creates a dynamic instance of a CIM class named **Win32_Process** on the client computer without getting the instance from the server.</span></span> <span data-ttu-id="e4a34-125">A nova instância é armazenada na variável `$a` .</span><span class="sxs-lookup"><span data-stu-id="e4a34-125">The new instance is stored in the variable `$a`.</span></span> <span data-ttu-id="e4a34-126">Essa instância dinâmica pode ser usada para executar operações se a instância com essa chave existir no servidor.</span><span class="sxs-lookup"><span data-stu-id="e4a34-126">This dynamic instance can be used to perform operations if the instance with this key exists on the server.</span></span>

```powershell
$a = New-CimInstance -ClassName Win32_Process -Property @{Handle=0} -Key Handle -ClientOnly
Get-CimInstance -CimInstance $a
Invoke-CimMethod -CimInstance $a -MethodName GetOwner
```

```Output
ProcessId Name                HandleCount WorkingSetSize VirtualSize
--------- ----                ----------- -------------- -----------
0         System Idle Process 0           8192           8192

Domain         :
ReturnValue    : 2
User           :
PSComputerName :
```

<span data-ttu-id="e4a34-127">`Get-CimInstance`Em seguida, o cmdlet recupera uma única instância específica.</span><span class="sxs-lookup"><span data-stu-id="e4a34-127">The `Get-CimInstance` cmdlet then retrieves a particular single instance.</span></span> <span data-ttu-id="e4a34-128">O `Invoke-CimMethod` cmdlet chama o método **GetOwner** na instância recuperada.</span><span class="sxs-lookup"><span data-stu-id="e4a34-128">The `Invoke-CimMethod` cmdlet calls the **GetOwner** method on the retrieved instance.</span></span>

### <span data-ttu-id="e4a34-129">Exemplo 4: criar uma instância para uma classe CIM de um namespace específico</span><span class="sxs-lookup"><span data-stu-id="e4a34-129">Example 4: Create an instance for a CIM class of a specific namespace</span></span>

<span data-ttu-id="e4a34-130">Este exemplo obtém uma instância de uma classe CIM chamada **MSFT_Something** na raiz do namespace **/em algum lugar** e a armazena em uma variável chamada `$class` .</span><span class="sxs-lookup"><span data-stu-id="e4a34-130">This example gets an instance of a CIM class named **MSFT_Something** in the namespace **root/somewhere** and stores it in a variable named `$class`.</span></span> <span data-ttu-id="e4a34-131">A variável é passada para o `New-CimInstance` cmdlet para criar uma nova instância CIM e executar validações do lado do cliente na nova instância.</span><span class="sxs-lookup"><span data-stu-id="e4a34-131">The variable is passed to the `New-CimInstance` cmdlet to create a new CIM instance and perform client side validations on the new instance.</span></span>

```powershell
$class = Get-CimClass -ClassName MSFT_Something -Namespace root/somewhere
New-CimInstance -CimClass $class -Property @{"Prop1"=1;"Prop2"="value"} -ClientOnly
```

<span data-ttu-id="e4a34-132">Neste exemplo, o uso do parâmetro **CimClass** em vez do parâmetro **ClassName** valida que **Prop1** e **Prop2** realmente existem e que as chaves estão marcadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="e4a34-132">In this example, using the **CimClass** parameter instead of the **ClassName** parameter validates that **Prop1** and **Prop2** actually exist and that the keys are marked correctly.</span></span>

<span data-ttu-id="e4a34-133">Você não pode usar o parâmetro **ComputerName** ou **CimSession** com o parâmetro **ClientOnly** .</span><span class="sxs-lookup"><span data-stu-id="e4a34-133">You cannot use the **ComputerName** or **CimSession** parameter with the **ClientOnly** parameter.</span></span>

## <span data-ttu-id="e4a34-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e4a34-134">PARAMETERS</span></span>

### <span data-ttu-id="e4a34-135">-CimClass</span><span class="sxs-lookup"><span data-stu-id="e4a34-135">-CimClass</span></span>

<span data-ttu-id="e4a34-136">Especifica um objeto de classe CIM que representa o tipo da instância.</span><span class="sxs-lookup"><span data-stu-id="e4a34-136">Specifies a CIM class object that represents the type of the instance.</span></span> <span data-ttu-id="e4a34-137">Use o `Get-CimClass` cmdlet para recuperar a declaração de classe de um computador.</span><span class="sxs-lookup"><span data-stu-id="e4a34-137">Use the `Get-CimClass` cmdlet to retrieve the class declaration from a computer.</span></span> <span data-ttu-id="e4a34-138">O uso desse parâmetro resulta em validações de esquema melhores do cliente.</span><span class="sxs-lookup"><span data-stu-id="e4a34-138">Using this parameter results in better client side schema validations.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassSessionSet, CimClassComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e4a34-139">-CimSession</span><span class="sxs-lookup"><span data-stu-id="e4a34-139">-CimSession</span></span>

<span data-ttu-id="e4a34-140">Executa o comando usando a sessão CIM especificada.</span><span class="sxs-lookup"><span data-stu-id="e4a34-140">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="e4a34-141">Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como os `New-CimSession` `Get-CimSession` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="e4a34-141">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="e4a34-142">Para obter mais informações, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="e4a34-142">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ClassNameSessionSet, ResourceUriSessionSet, CimClassSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e4a34-143">-ClassName</span><span class="sxs-lookup"><span data-stu-id="e4a34-143">-ClassName</span></span>

<span data-ttu-id="e4a34-144">Especifica o nome da classe CIM da qual a operação cria uma instância.</span><span class="sxs-lookup"><span data-stu-id="e4a34-144">Specifies the name of the CIM class of which the operation creates an instance.</span></span> <span data-ttu-id="e4a34-145">Observação: você pode usar o preenchimento com Tab para procurar a lista de classes, porque o PowerShell Obtém uma lista de classes do servidor WMI local para fornecer uma lista de nomes de classe.</span><span class="sxs-lookup"><span data-stu-id="e4a34-145">NOTE: You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4a34-146">-ClientOnly</span><span class="sxs-lookup"><span data-stu-id="e4a34-146">-ClientOnly</span></span>

<span data-ttu-id="e4a34-147">Indica que a instância é criada somente no PowerShell sem ir para o servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="e4a34-147">Indicates that the instance is only created in PowerShell without going to the CIM server.</span></span> <span data-ttu-id="e4a34-148">Você pode usar esse parâmetro para criar uma instância CIM na memória para uso em operações subsequentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4a34-148">You can use this parameter to create an in-memory CIM instance for use in subsequent PowerShell operations.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, CimClassSessionSet, CimClassComputerSet
Aliases: Local

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4a34-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="e4a34-149">-ComputerName</span></span>

<span data-ttu-id="e4a34-150">Especifica o nome do computador no qual você deseja executar a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="e4a34-150">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="e4a34-151">Você pode especificar um FQDN (nome de domínio totalmente qualificado), um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="e4a34-151">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="e4a34-152">Se você especificar esse parâmetro, o cmdlet criará uma sessão temporária para o computador especificado usando o protocolo WSMan.</span><span class="sxs-lookup"><span data-stu-id="e4a34-152">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WSMan protocol.</span></span>

<span data-ttu-id="e4a34-153">Se você não especificar esse parâmetro, o cmdlet executará a operação no computador local usando Component Object Model (COM).</span><span class="sxs-lookup"><span data-stu-id="e4a34-153">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="e4a34-154">Se várias operações estiverem sendo executadas no mesmo computador, a conexão usando uma sessão CIM fornecerá um melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="e4a34-154">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4a34-155">-Chave</span><span class="sxs-lookup"><span data-stu-id="e4a34-155">-Key</span></span>

<span data-ttu-id="e4a34-156">Especifica as propriedades que são usadas como chaves.</span><span class="sxs-lookup"><span data-stu-id="e4a34-156">Specifies the properties that are used as keys.</span></span> <span data-ttu-id="e4a34-157">**CimSession** e **ComputerName** não podem ser usados quando a **chave** é especificada.</span><span class="sxs-lookup"><span data-stu-id="e4a34-157">**CimSession** and **ComputerName** cannot be used when **Key** is specified.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4a34-158">-Namespace</span><span class="sxs-lookup"><span data-stu-id="e4a34-158">-Namespace</span></span>

<span data-ttu-id="e4a34-159">Especifica o namespace da classe para a nova instância.</span><span class="sxs-lookup"><span data-stu-id="e4a34-159">Specifies the namespace of the class for the new instance.</span></span> <span data-ttu-id="e4a34-160">O namespace padrão é **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="e4a34-160">The default namespace is **root/cimv2**.</span></span>
<span data-ttu-id="e4a34-161">Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.</span><span class="sxs-lookup"><span data-stu-id="e4a34-161">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4a34-162">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="e4a34-162">-OperationTimeoutSec</span></span>

<span data-ttu-id="e4a34-163">Especifica a quantidade de tempo que o cmdlet aguarda uma resposta do servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="e4a34-163">Specifies the amount of time that the cmdlet waits for a response from the CIM server.</span></span> <span data-ttu-id="e4a34-164">Por padrão, o valor desse parâmetro é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.</span><span class="sxs-lookup"><span data-stu-id="e4a34-164">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span> <span data-ttu-id="e4a34-165">Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão robusto de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis, pois a operação no servidor expirará antes que o cliente possa se reconectar.</span><span class="sxs-lookup"><span data-stu-id="e4a34-165">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4a34-166">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="e4a34-166">-Property</span></span>

<span data-ttu-id="e4a34-167">Especifica as propriedades da instância CIM usando uma tabela de hash (pares nome-valor).</span><span class="sxs-lookup"><span data-stu-id="e4a34-167">Specifies the properties of the CIM instance using a hash table (name-value pairs).</span></span>

<span data-ttu-id="e4a34-168">Se você especificar o parâmetro **CimClass** , o `New-CimInstance` cmdlet executará uma validação de propriedade no cliente para certificar-se de que as propriedades especificadas são consistentes com a declaração de classe no servidor.</span><span class="sxs-lookup"><span data-stu-id="e4a34-168">If you specify the **CimClass** parameter, then the `New-CimInstance` cmdlet performs a property validation on the client to make sure that the properties specified are consistent with the class declaration on the server.</span></span> <span data-ttu-id="e4a34-169">Se o parâmetro **CimClass** não for especificado, a validação da propriedade será feita no servidor.</span><span class="sxs-lookup"><span data-stu-id="e4a34-169">If the **CimClass** parameter is not specified, then the property validation is done on the server.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases: Arguments

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4a34-170">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="e4a34-170">-ResourceUri</span></span>

<span data-ttu-id="e4a34-171">Especifica o URI (Uniform Resource Identifier) do recurso da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="e4a34-171">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="e4a34-172">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="e4a34-172">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="e4a34-173">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="e4a34-173">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="e4a34-174">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e4a34-174">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="e4a34-175">Por padrão, se você não especificar esse parâmetro, o URI de recurso padrão do DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` será usado e o nome da classe será anexado a ele.</span><span class="sxs-lookup"><span data-stu-id="e4a34-175">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="e4a34-176">O **ResourceURI** só pode ser usado com sessões CIM criadas usando o protocolo WSMan ou ao especificar o parâmetro **ComputerName** , que cria uma sessão CIM usando WSMan.</span><span class="sxs-lookup"><span data-stu-id="e4a34-176">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="e4a34-177">Se você especificar esse parâmetro sem especificar o parâmetro **ComputerName** ou se especificar uma sessão CIM criada usando o protocolo DCOM, receberá um erro, pois o protocolo DCOM não oferece suporte ao parâmetro **ResourceURI** .</span><span class="sxs-lookup"><span data-stu-id="e4a34-177">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="e4a34-178">Se o parâmetro **ResourceURI** e o parâmetro **Filter** forem especificados, o parâmetro **Filter** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="e4a34-178">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4a34-179">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e4a34-179">-Confirm</span></span>

<span data-ttu-id="e4a34-180">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e4a34-180">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e4a34-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e4a34-181">-WhatIf</span></span>

<span data-ttu-id="e4a34-182">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="e4a34-182">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e4a34-183">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e4a34-183">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e4a34-184">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e4a34-184">CommonParameters</span></span>

<span data-ttu-id="e4a34-185">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e4a34-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e4a34-186">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e4a34-186">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e4a34-187">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e4a34-187">INPUTS</span></span>

### <span data-ttu-id="e4a34-188">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e4a34-188">None</span></span>

<span data-ttu-id="e4a34-189">Esse cmdlet não aceita nenhum objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="e4a34-189">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="e4a34-190">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e4a34-190">OUTPUTS</span></span>

### <span data-ttu-id="e4a34-191">System.Object</span><span class="sxs-lookup"><span data-stu-id="e4a34-191">System.Object</span></span>

<span data-ttu-id="e4a34-192">Esse cmdlet retorna um objeto que contém as informações da instância CIM.</span><span class="sxs-lookup"><span data-stu-id="e4a34-192">This cmdlet returns an object that contains the CIM instance information.</span></span>

## <span data-ttu-id="e4a34-193">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e4a34-193">NOTES</span></span>

## <span data-ttu-id="e4a34-194">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e4a34-194">RELATED LINKS</span></span>

[<span data-ttu-id="e4a34-195">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="e4a34-195">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="e4a34-196">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e4a34-196">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="e4a34-197">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e4a34-197">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="e4a34-198">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e4a34-198">Set-CimInstance</span></span>](Set-CimInstance.md)

