---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-ciminstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimInstance
ms.openlocfilehash: d6eab5d6fcf1c4d983f2502465d76ad5df1db9dd
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194863"
---
# <span data-ttu-id="9e453-103">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="9e453-103">New-CimInstance</span></span>

## <span data-ttu-id="9e453-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9e453-104">SYNOPSIS</span></span>
<span data-ttu-id="9e453-105">Cria uma instância CIM.</span><span class="sxs-lookup"><span data-stu-id="9e453-105">Creates a CIM instance.</span></span>

## <span data-ttu-id="9e453-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9e453-106">SYNTAX</span></span>

### <span data-ttu-id="9e453-107">ClassNameComputerSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="9e453-107">ClassNameComputerSet (Default)</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9e453-108">ClassNameSessionSet</span><span class="sxs-lookup"><span data-stu-id="9e453-108">ClassNameSessionSet</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9e453-109">ResourceUriSessionSet</span><span class="sxs-lookup"><span data-stu-id="9e453-109">ResourceUriSessionSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9e453-110">ResourceUriComputerSet</span><span class="sxs-lookup"><span data-stu-id="9e453-110">ResourceUriComputerSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9e453-111">CimClassSessionSet</span><span class="sxs-lookup"><span data-stu-id="9e453-111">CimClassSessionSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9e453-112">CimClassComputerSet</span><span class="sxs-lookup"><span data-stu-id="9e453-112">CimClassComputerSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9e453-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9e453-113">DESCRIPTION</span></span>

<span data-ttu-id="9e453-114">O `New-CimInstance` cmdlet cria uma instância de uma classe CIM com base na definição de classe no computador local ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9e453-114">The `New-CimInstance` cmdlet creates an instance of a CIM class based on the class definition on either the local computer or a remote computer.</span></span> <span data-ttu-id="9e453-115">Por padrão, o `New-CimInstance` cmdlet cria uma instância no computador local.</span><span class="sxs-lookup"><span data-stu-id="9e453-115">By default, the `New-CimInstance` cmdlet creates an instance on the local computer.</span></span>

## <span data-ttu-id="9e453-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9e453-116">EXAMPLES</span></span>

### <span data-ttu-id="9e453-117">Exemplo 1: criar uma instância de uma classe CIM</span><span class="sxs-lookup"><span data-stu-id="9e453-117">Example 1: Create an instance of a CIM class</span></span>

<span data-ttu-id="9e453-118">Este exemplo cria uma instância de uma classe CIM denominada win32_environment no namespace raiz/cimv2 no computador.</span><span class="sxs-lookup"><span data-stu-id="9e453-118">This example creates an instance of a CIM Class named win32_environment in the root/cimv2 namespace on the computer.</span></span>

```powershell
New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";VariableValue="testvalue";UserName="domain\user"}
```

<span data-ttu-id="9e453-119">Nenhuma validação no lado do cliente é executada se a classe não existir, se as propriedades estiverem erradas ou se o servidor rejeitar a chamada.</span><span class="sxs-lookup"><span data-stu-id="9e453-119">No client side validation is performed if the class does not exist, the properties are wrong, or if the server rejects the call.</span></span> <span data-ttu-id="9e453-120">Se a instância for criada com êxito, o cmdlet produzirá a instância recém-criada.</span><span class="sxs-lookup"><span data-stu-id="9e453-120">If the instance is created successfully, the cmdlet outputs the newly created instance.</span></span>

### <span data-ttu-id="9e453-121">Exemplo 2: criar uma instância de uma classe CIM usando um esquema de classe</span><span class="sxs-lookup"><span data-stu-id="9e453-121">Example 2: Create an instance of a CIM class using a class schema</span></span>

<span data-ttu-id="9e453-122">Este exemplo recupera um objeto de classe CIM e o armazena em uma variável chamada `$class` .</span><span class="sxs-lookup"><span data-stu-id="9e453-122">This example retrieves a CIM class object and stores it in a variable named `$class`.</span></span> <span data-ttu-id="9e453-123">O conteúdo da variável é passado para o `New-CimInstance` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e453-123">The contents of the variable are then passed to the `New-CimInstance` cmdlet.</span></span>

```powershell
$class = Get-CimClass -ClassName Win32_Environment
New-CimInstance -CimClass $class -Property @{Name="testvar";VariableValue="testvalue";UserName="Contoso\User1"}
```

### <span data-ttu-id="9e453-124">Exemplo 3: criar uma instância dinâmica no cliente</span><span class="sxs-lookup"><span data-stu-id="9e453-124">Example 3: Create a dynamic instance on the client</span></span>

<span data-ttu-id="9e453-125">Este exemplo cria uma instância dinâmica de uma classe CIM chamada **Win32_Process** no computador cliente sem obter a instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="9e453-125">This example creates a dynamic instance of a CIM class named **Win32_Process** on the client computer without getting the instance from the server.</span></span> <span data-ttu-id="9e453-126">A nova instância é armazenada na variável `$a` .</span><span class="sxs-lookup"><span data-stu-id="9e453-126">The new instance is stored in the variable `$a`.</span></span> <span data-ttu-id="9e453-127">Essa instância dinâmica pode ser usada para executar operações se a instância com essa chave existir no servidor.</span><span class="sxs-lookup"><span data-stu-id="9e453-127">This dynamic instance can be used to perform operations if the instance with this key exists on the server.</span></span>

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

<span data-ttu-id="9e453-128">`Get-CimInstance`Em seguida, o cmdlet recupera uma única instância específica.</span><span class="sxs-lookup"><span data-stu-id="9e453-128">The `Get-CimInstance` cmdlet then retrieves a particular single instance.</span></span> <span data-ttu-id="9e453-129">O `Invoke-CimMethod` cmdlet chama o método **GetOwner** na instância recuperada.</span><span class="sxs-lookup"><span data-stu-id="9e453-129">The `Invoke-CimMethod` cmdlet calls the **GetOwner** method on the retrieved instance.</span></span>

### <span data-ttu-id="9e453-130">Exemplo 4: criar uma instância para uma classe CIM de um namespace específico</span><span class="sxs-lookup"><span data-stu-id="9e453-130">Example 4: Create an instance for a CIM class of a specific namespace</span></span>

<span data-ttu-id="9e453-131">Este exemplo obtém uma instância de uma classe CIM chamada **MSFT_Something** na raiz do namespace **/em algum lugar** e a armazena em uma variável chamada `$class` .</span><span class="sxs-lookup"><span data-stu-id="9e453-131">This example gets an instance of a CIM class named **MSFT_Something** in the namespace **root/somewhere** and stores it in a variable named `$class`.</span></span> <span data-ttu-id="9e453-132">A variável é passada para o `New-CimInstance` cmdlet para criar uma nova instância CIM e executar validações do lado do cliente na nova instância.</span><span class="sxs-lookup"><span data-stu-id="9e453-132">The variable is passed to the `New-CimInstance` cmdlet to create a new CIM instance and perform client side validations on the new instance.</span></span>

```powershell
$class = Get-CimClass -ClassName MSFT_Something -Namespace root/somewhere
New-CimInstance -CimClass $class -Property @{"Prop1"=1;"Prop2"="value"} -ClientOnly
```

<span data-ttu-id="9e453-133">Neste exemplo, o uso do parâmetro **CimClass** em vez do parâmetro **ClassName** valida que **Prop1** e **Prop2** realmente existem e que as chaves estão marcadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="9e453-133">In this example, using the **CimClass** parameter instead of the **ClassName** parameter validates that **Prop1** and **Prop2** actually exist and that the keys are marked correctly.</span></span>

<span data-ttu-id="9e453-134">Você não pode usar o parâmetro **ComputerName** ou **CimSession** com o parâmetro **ClientOnly** .</span><span class="sxs-lookup"><span data-stu-id="9e453-134">You cannot use the **ComputerName** or **CimSession** parameter with the **ClientOnly** parameter.</span></span>

## <span data-ttu-id="9e453-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9e453-135">PARAMETERS</span></span>

### <span data-ttu-id="9e453-136">-CimClass</span><span class="sxs-lookup"><span data-stu-id="9e453-136">-CimClass</span></span>

<span data-ttu-id="9e453-137">Especifica um objeto de classe CIM que representa o tipo da instância.</span><span class="sxs-lookup"><span data-stu-id="9e453-137">Specifies a CIM class object that represents the type of the instance.</span></span> <span data-ttu-id="9e453-138">Use o `Get-CimClass` cmdlet para recuperar a declaração de classe de um computador.</span><span class="sxs-lookup"><span data-stu-id="9e453-138">Use the `Get-CimClass` cmdlet to retrieve the class declaration from a computer.</span></span> <span data-ttu-id="9e453-139">O uso desse parâmetro resulta em validações de esquema melhores do cliente.</span><span class="sxs-lookup"><span data-stu-id="9e453-139">Using this parameter results in better client side schema validations.</span></span>

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

### <span data-ttu-id="9e453-140">-CimSession</span><span class="sxs-lookup"><span data-stu-id="9e453-140">-CimSession</span></span>

<span data-ttu-id="9e453-141">Executa o comando usando a sessão CIM especificada.</span><span class="sxs-lookup"><span data-stu-id="9e453-141">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="9e453-142">Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como os `New-CimSession` `Get-CimSession` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="9e453-142">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="9e453-143">Para obter mais informações, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="9e453-143">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

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

### <span data-ttu-id="9e453-144">-ClassName</span><span class="sxs-lookup"><span data-stu-id="9e453-144">-ClassName</span></span>

<span data-ttu-id="9e453-145">Especifica o nome da classe CIM da qual a operação cria uma instância.</span><span class="sxs-lookup"><span data-stu-id="9e453-145">Specifies the name of the CIM class of which the operation creates an instance.</span></span> <span data-ttu-id="9e453-146">Observação: você pode usar o preenchimento com Tab para procurar a lista de classes, porque o PowerShell Obtém uma lista de classes do servidor WMI local para fornecer uma lista de nomes de classe.</span><span class="sxs-lookup"><span data-stu-id="9e453-146">NOTE: You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

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

### <span data-ttu-id="9e453-147">-ClientOnly</span><span class="sxs-lookup"><span data-stu-id="9e453-147">-ClientOnly</span></span>

<span data-ttu-id="9e453-148">Indica que a instância é criada somente no PowerShell sem ir para o servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="9e453-148">Indicates that the instance is only created in PowerShell without going to the CIM server.</span></span> <span data-ttu-id="9e453-149">Você pode usar esse parâmetro para criar uma instância CIM na memória para uso em operações subsequentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e453-149">You can use this parameter to create an in-memory CIM instance for use in subsequent PowerShell operations.</span></span>

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

### <span data-ttu-id="9e453-150">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9e453-150">-ComputerName</span></span>

<span data-ttu-id="9e453-151">Especifica o nome do computador no qual você deseja executar a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="9e453-151">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="9e453-152">Você pode especificar um FQDN (nome de domínio totalmente qualificado), um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="9e453-152">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="9e453-153">Se você especificar esse parâmetro, o cmdlet criará uma sessão temporária para o computador especificado usando o protocolo WSMan.</span><span class="sxs-lookup"><span data-stu-id="9e453-153">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WSMan protocol.</span></span>

<span data-ttu-id="9e453-154">Se você não especificar esse parâmetro, o cmdlet executará a operação no computador local usando Component Object Model (COM).</span><span class="sxs-lookup"><span data-stu-id="9e453-154">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="9e453-155">Se várias operações estiverem sendo executadas no mesmo computador, a conexão usando uma sessão CIM fornecerá um melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="9e453-155">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

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

### <span data-ttu-id="9e453-156">-Chave</span><span class="sxs-lookup"><span data-stu-id="9e453-156">-Key</span></span>

<span data-ttu-id="9e453-157">Especifica as propriedades que são usadas como chaves.</span><span class="sxs-lookup"><span data-stu-id="9e453-157">Specifies the properties that are used as keys.</span></span> <span data-ttu-id="9e453-158">**CimSession** e **ComputerName** não podem ser usados quando a **chave** é especificada.</span><span class="sxs-lookup"><span data-stu-id="9e453-158">**CimSession** and **ComputerName** cannot be used when **Key** is specified.</span></span>

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

### <span data-ttu-id="9e453-159">-Namespace</span><span class="sxs-lookup"><span data-stu-id="9e453-159">-Namespace</span></span>

<span data-ttu-id="9e453-160">Especifica o namespace da classe para a nova instância.</span><span class="sxs-lookup"><span data-stu-id="9e453-160">Specifies the namespace of the class for the new instance.</span></span> <span data-ttu-id="9e453-161">O namespace padrão é **root/cimv2** .</span><span class="sxs-lookup"><span data-stu-id="9e453-161">The default namespace is **root/cimv2** .</span></span>
<span data-ttu-id="9e453-162">Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.</span><span class="sxs-lookup"><span data-stu-id="9e453-162">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

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

### <span data-ttu-id="9e453-163">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="9e453-163">-OperationTimeoutSec</span></span>

<span data-ttu-id="9e453-164">Especifica a quantidade de tempo que o cmdlet aguarda uma resposta do servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="9e453-164">Specifies the amount of time that the cmdlet waits for a response from the CIM server.</span></span> <span data-ttu-id="9e453-165">Por padrão, o valor desse parâmetro é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.</span><span class="sxs-lookup"><span data-stu-id="9e453-165">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span> <span data-ttu-id="9e453-166">Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão robusto de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis, pois a operação no servidor expirará antes que o cliente possa se reconectar.</span><span class="sxs-lookup"><span data-stu-id="9e453-166">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="9e453-167">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="9e453-167">-Property</span></span>

<span data-ttu-id="9e453-168">Especifica as propriedades da instância CIM usando uma tabela de hash (pares nome-valor).</span><span class="sxs-lookup"><span data-stu-id="9e453-168">Specifies the properties of the CIM instance using a hash table (name-value pairs).</span></span>

<span data-ttu-id="9e453-169">Se você especificar o parâmetro **CimClass** , o `New-CimInstance` cmdlet executará uma validação de propriedade no cliente para certificar-se de que as propriedades especificadas são consistentes com a declaração de classe no servidor.</span><span class="sxs-lookup"><span data-stu-id="9e453-169">If you specify the **CimClass** parameter, then the `New-CimInstance` cmdlet performs a property validation on the client to make sure that the properties specified are consistent with the class declaration on the server.</span></span> <span data-ttu-id="9e453-170">Se o parâmetro **CimClass** não for especificado, a validação da propriedade será feita no servidor.</span><span class="sxs-lookup"><span data-stu-id="9e453-170">If the **CimClass** parameter is not specified, then the property validation is done on the server.</span></span>

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

### <span data-ttu-id="9e453-171">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="9e453-171">-ResourceUri</span></span>

<span data-ttu-id="9e453-172">Especifica o URI (Uniform Resource Identifier) do recurso da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="9e453-172">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="9e453-173">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="9e453-173">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="9e453-174">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="9e453-174">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="9e453-175">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9e453-175">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="9e453-176">Por padrão, se você não especificar esse parâmetro, o URI de recurso padrão do DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` será usado e o nome da classe será anexado a ele.</span><span class="sxs-lookup"><span data-stu-id="9e453-176">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="9e453-177">O **ResourceURI** só pode ser usado com sessões CIM criadas usando o protocolo WSMan ou ao especificar o parâmetro **ComputerName** , que cria uma sessão CIM usando WSMan.</span><span class="sxs-lookup"><span data-stu-id="9e453-177">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="9e453-178">Se você especificar esse parâmetro sem especificar o parâmetro **ComputerName** ou se especificar uma sessão CIM criada usando o protocolo DCOM, receberá um erro, pois o protocolo DCOM não oferece suporte ao parâmetro **ResourceURI** .</span><span class="sxs-lookup"><span data-stu-id="9e453-178">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="9e453-179">Se o parâmetro **ResourceURI** e o parâmetro **Filter** forem especificados, o parâmetro **Filter** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="9e453-179">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

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

### <span data-ttu-id="9e453-180">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9e453-180">-Confirm</span></span>

<span data-ttu-id="9e453-181">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e453-181">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9e453-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9e453-182">-WhatIf</span></span>

<span data-ttu-id="9e453-183">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="9e453-183">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9e453-184">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="9e453-184">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9e453-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9e453-185">CommonParameters</span></span>

<span data-ttu-id="9e453-186">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9e453-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9e453-187">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9e453-187">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9e453-188">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9e453-188">INPUTS</span></span>

### <span data-ttu-id="9e453-189">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9e453-189">None</span></span>

<span data-ttu-id="9e453-190">Esse cmdlet não aceita nenhum objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="9e453-190">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="9e453-191">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9e453-191">OUTPUTS</span></span>

### <span data-ttu-id="9e453-192">System.Object</span><span class="sxs-lookup"><span data-stu-id="9e453-192">System.Object</span></span>

<span data-ttu-id="9e453-193">Esse cmdlet retorna um objeto que contém as informações da instância CIM.</span><span class="sxs-lookup"><span data-stu-id="9e453-193">This cmdlet returns an object that contains the CIM instance information.</span></span>

## <span data-ttu-id="9e453-194">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9e453-194">NOTES</span></span>

## <span data-ttu-id="9e453-195">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9e453-195">RELATED LINKS</span></span>

[<span data-ttu-id="9e453-196">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="9e453-196">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="9e453-197">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="9e453-197">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="9e453-198">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="9e453-198">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="9e453-199">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="9e453-199">Set-CimInstance</span></span>](Set-CimInstance.md)
