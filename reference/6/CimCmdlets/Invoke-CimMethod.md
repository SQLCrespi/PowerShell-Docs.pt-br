---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 01/21/2020
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/invoke-cimmethod?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CimMethod
ms.openlocfilehash: 2f6e7bac8cd460b9eb9fa74d9e1aa931d33108d1
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194865"
---
# <span data-ttu-id="678b3-103">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="678b3-103">Invoke-CimMethod</span></span>

## <span data-ttu-id="678b3-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="678b3-104">SYNOPSIS</span></span>
<span data-ttu-id="678b3-105">Invoca um método de uma classe CIM.</span><span class="sxs-lookup"><span data-stu-id="678b3-105">Invokes a method of a CIM class.</span></span>

## <span data-ttu-id="678b3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="678b3-106">SYNTAX</span></span>

### <span data-ttu-id="678b3-107">ClassNameComputerSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="678b3-107">ClassNameComputerSet (Default)</span></span>

```
Invoke-CimMethod [-ClassName] <String> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="678b3-108">ClassNameSessionSet</span><span class="sxs-lookup"><span data-stu-id="678b3-108">ClassNameSessionSet</span></span>

```
Invoke-CimMethod [-ClassName] <String> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="678b3-109">ResourceUriComputerSet</span><span class="sxs-lookup"><span data-stu-id="678b3-109">ResourceUriComputerSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="678b3-110">CimInstanceSessionSet</span><span class="sxs-lookup"><span data-stu-id="678b3-110">CimInstanceSessionSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="678b3-111">CimInstanceComputerSet</span><span class="sxs-lookup"><span data-stu-id="678b3-111">CimInstanceComputerSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="678b3-112">ResourceUriSessionSet</span><span class="sxs-lookup"><span data-stu-id="678b3-112">ResourceUriSessionSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="678b3-113">CimClassComputerSet</span><span class="sxs-lookup"><span data-stu-id="678b3-113">CimClassComputerSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="678b3-114">CimClassSessionSet</span><span class="sxs-lookup"><span data-stu-id="678b3-114">CimClassSessionSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="678b3-115">QueryComputerSet</span><span class="sxs-lookup"><span data-stu-id="678b3-115">QueryComputerSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="678b3-116">QuerySessionSet</span><span class="sxs-lookup"><span data-stu-id="678b3-116">QuerySessionSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="678b3-117">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="678b3-117">DESCRIPTION</span></span>

<span data-ttu-id="678b3-118">O `Invoke-CimMethod` cmdlet invoca um método de uma classe CIM ou uma instância CIM usando os pares nome-valor especificados pelo parâmetro **arguments** .</span><span class="sxs-lookup"><span data-stu-id="678b3-118">The `Invoke-CimMethod` cmdlet invokes a method of a CIM class or CIM instance using the name-value pairs specified by the **Arguments** parameter.</span></span>

<span data-ttu-id="678b3-119">Se o parâmetro **InputObject** não for especificado, o cmdlet funcionará de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="678b3-119">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="678b3-120">Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet funcionará no Instrumentação de gerenciamento do Windows local (WMI) usando uma sessão Component Object Model (com).</span><span class="sxs-lookup"><span data-stu-id="678b3-120">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="678b3-121">Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet funcionará no servidor CIM especificado pelo parâmetro **ComputerName** ou pelo parâmetro **CimSession** .</span><span class="sxs-lookup"><span data-stu-id="678b3-121">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="678b3-122">Se o parâmetro **InputObject** for especificado, o cmdlet funcionará de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="678b3-122">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="678b3-123">Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet usará a sessão CIM ou o nome do computador do objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="678b3-123">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="678b3-124">Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet usa o valor do parâmetro **CimSession** ou o valor do parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="678b3-124">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the **CimSession** parameter value or **ComputerName** parameter value.</span></span> <span data-ttu-id="678b3-125">Esse não é um cenário comum.</span><span class="sxs-lookup"><span data-stu-id="678b3-125">This is not a common scenario.</span></span>

## <span data-ttu-id="678b3-126">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="678b3-126">EXAMPLES</span></span>

### <span data-ttu-id="678b3-127">Exemplo 1: invocar um método</span><span class="sxs-lookup"><span data-stu-id="678b3-127">Example 1: Invoke a method</span></span>

<span data-ttu-id="678b3-128">Este exemplo invoca o método **Terminate** da classe **Win32_Process** .</span><span class="sxs-lookup"><span data-stu-id="678b3-128">This example invokes the **Terminate** method of the **Win32_Process** class.</span></span>

```powershell
Invoke-CimMethod -Query 'select * from Win32_Process where name like "notepad%"' -MethodName "Terminate"
```

### <span data-ttu-id="678b3-129">Exemplo 2: invocar um método usando o objeto de instância CIM</span><span class="sxs-lookup"><span data-stu-id="678b3-129">Example 2: Invoke a method using CIM instance object</span></span>

<span data-ttu-id="678b3-130">Este exemplo recupera o objeto de instância CIM e o armazena em uma variável chamada `$x` usando o `Get-CimInstance` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="678b3-130">This example retrieves the CIM instance object and stores it in a variable named `$x` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="678b3-131">O conteúdo da variável é usado como **InputObject** para o `Invoke-CimMethod` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="678b3-131">The contents of the variable are then used as the **InputObject** for the `Invoke-CimMethod` cmdlet.</span></span> <span data-ttu-id="678b3-132">O método **GetOwner** é invocado para o **CimInstance** .</span><span class="sxs-lookup"><span data-stu-id="678b3-132">The **GetOwner** method is invoked for the **CimInstance** .</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Process where name like "notepad%"'
Invoke-CimMethod -InputObject $x -MethodName GetOwner
```

### <span data-ttu-id="678b3-133">Exemplo 3: invocar um método estático usando argumentos</span><span class="sxs-lookup"><span data-stu-id="678b3-133">Example 3: Invoke a static method using arguments</span></span>

<span data-ttu-id="678b3-134">Este exemplo invoca o método **Create** chamado usando o parâmetro **arguments** .</span><span class="sxs-lookup"><span data-stu-id="678b3-134">This example invokes the **Create** method named using the **Arguments** parameter.</span></span>

```powershell
Invoke-CimMethod -ClassName Win32_Process -MethodName "Create" -Arguments @{
  CommandLine = 'notepad.exe'; CurrentDirectory = "C:\windows\system32"
}
```

### <span data-ttu-id="678b3-135">Exemplo 4: validação no lado do cliente</span><span class="sxs-lookup"><span data-stu-id="678b3-135">Example 4: Client-side validation</span></span>

<span data-ttu-id="678b3-136">Este exemplo executa a validação do lado do cliente para o método **XYZ** passando um objeto **CimClass** para `Invoke-CimMethod` .</span><span class="sxs-lookup"><span data-stu-id="678b3-136">This example performs client-side validation for the **xyz** method by passing a **CimClass** object to `Invoke-CimMethod`.</span></span>

```powershell
$c = Get-CimClass -ClassName Win32_Process
Invoke-CimMethod -CimClass $c -MethodName "xyz" -Arguments @{ CommandLine = 'notepad.exe' }
```

## <span data-ttu-id="678b3-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="678b3-137">PARAMETERS</span></span>

### <span data-ttu-id="678b3-138">-Arguments</span><span class="sxs-lookup"><span data-stu-id="678b3-138">-Arguments</span></span>

<span data-ttu-id="678b3-139">Especifica os parâmetros a passar para o método chamado.</span><span class="sxs-lookup"><span data-stu-id="678b3-139">Specifies the parameters to pass to the called method.</span></span> <span data-ttu-id="678b3-140">Especifique os valores para esse parâmetro como pares de nome-valor, armazenados em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="678b3-140">Specify the values for this parameter as name-value pairs, stored in a hash table.</span></span> <span data-ttu-id="678b3-141">A ordem dos valores inseridos não é importante.</span><span class="sxs-lookup"><span data-stu-id="678b3-141">The order of the values entered isn't important.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="678b3-142">-CimClass</span><span class="sxs-lookup"><span data-stu-id="678b3-142">-CimClass</span></span>

<span data-ttu-id="678b3-143">Especifica um objeto de classe CIM que representa uma definição de classe CIM no servidor.</span><span class="sxs-lookup"><span data-stu-id="678b3-143">Specifies a CIM class object that represents a CIM class definition on the server.</span></span> <span data-ttu-id="678b3-144">Use esse parâmetro ao invocar um método estático de uma classe.</span><span class="sxs-lookup"><span data-stu-id="678b3-144">Use this parameter when invoking a static method of a class.</span></span>

<span data-ttu-id="678b3-145">Você pode usar o `Get-CimClass` cmdlet para recuperar uma definição de classe do servidor.</span><span class="sxs-lookup"><span data-stu-id="678b3-145">You can use the `Get-CimClass` cmdlet to retrieve a class definition from the server.</span></span>

<span data-ttu-id="678b3-146">O uso desse parâmetro resulta em validações de esquema melhores do cliente.</span><span class="sxs-lookup"><span data-stu-id="678b3-146">Using this parameter results in better client side schema validations.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassComputerSet, CimClassSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="678b3-147">-CimSession</span><span class="sxs-lookup"><span data-stu-id="678b3-147">-CimSession</span></span>

<span data-ttu-id="678b3-148">Executa o comando usando a sessão CIM especificada.</span><span class="sxs-lookup"><span data-stu-id="678b3-148">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="678b3-149">Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como os `New-CimSession` `Get-CimSession` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="678b3-149">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="678b3-150">Para obter mais informações, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="678b3-150">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ClassNameSessionSet, CimInstanceSessionSet, CimClassSessionSet, QuerySessionSet, ResourceUriSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="678b3-151">-ClassName</span><span class="sxs-lookup"><span data-stu-id="678b3-151">-ClassName</span></span>

<span data-ttu-id="678b3-152">Especifica o nome da classe CIM para a qual executar a operação.</span><span class="sxs-lookup"><span data-stu-id="678b3-152">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="678b3-153">Esse parâmetro é usado somente para métodos estáticos.</span><span class="sxs-lookup"><span data-stu-id="678b3-153">This parameter is only used for static methods.</span></span> <span data-ttu-id="678b3-154">Você pode usar o preenchimento com Tab para procurar a lista de classes, porque o PowerShell Obtém uma lista de classes do servidor WMI local para fornecer uma lista de nomes de classe.</span><span class="sxs-lookup"><span data-stu-id="678b3-154">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases: Class

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="678b3-155">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="678b3-155">-ComputerName</span></span>

<span data-ttu-id="678b3-156">Especifica o nome do computador no qual você deseja executar a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="678b3-156">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="678b3-157">Você pode especificar um FQDN (nome de domínio totalmente qualificado), um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="678b3-157">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="678b3-158">Ao usar esse parâmetro, o cmdlet cria uma sessão temporária para o computador especificado usando o protocolo WsMan.</span><span class="sxs-lookup"><span data-stu-id="678b3-158">When using this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span> <span data-ttu-id="678b3-159">Caso contrário, o cmdlet executará a operação no computador local usando a Component Object Model (COM).</span><span class="sxs-lookup"><span data-stu-id="678b3-159">Otherwise, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="678b3-160">Conecte-se usando uma sessão CIM para melhorar o desempenho quando várias operações estiverem sendo executadas no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="678b3-160">Connect using a CIM session for better performance when multiple operations are being performed on the same computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet, CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="678b3-161">-InputObject</span><span class="sxs-lookup"><span data-stu-id="678b3-161">-InputObject</span></span>

<span data-ttu-id="678b3-162">Especifica um objeto de instância CIM a ser usado como entrada para invocar um método.</span><span class="sxs-lookup"><span data-stu-id="678b3-162">Specifies a CIM instance object to use as input to invoke a method.</span></span> <span data-ttu-id="678b3-163">Esse parâmetro só pode ser usado para invocar métodos de instância.</span><span class="sxs-lookup"><span data-stu-id="678b3-163">This parameter can only be used to invoke instance methods.</span></span> <span data-ttu-id="678b3-164">Para invocar métodos estáticos de classe, use o parâmetro de **classe** ou o parâmetro **CimClass** .</span><span class="sxs-lookup"><span data-stu-id="678b3-164">To invoke class static methods, use the **Class** parameter or the **CimClass** parameter.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceSessionSet, CimInstanceComputerSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="678b3-165">-MethodName</span><span class="sxs-lookup"><span data-stu-id="678b3-165">-MethodName</span></span>

<span data-ttu-id="678b3-166">Especifica o nome do método CIM a ser invocado.</span><span class="sxs-lookup"><span data-stu-id="678b3-166">Specifies the name of the CIM method to invoke.</span></span> <span data-ttu-id="678b3-167">Este parâmetro é obrigatório e não pode ser nulo ou vazio.</span><span class="sxs-lookup"><span data-stu-id="678b3-167">This parameter is mandatory and cannot be null or empty.</span></span> <span data-ttu-id="678b3-168">Para invocar o método estático de uma classe CIM, use o **ClassName** ou o parâmetro **CimClass** .</span><span class="sxs-lookup"><span data-stu-id="678b3-168">To invoke static method of a CIM class use the **ClassName** or the **CimClass** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="678b3-169">-Namespace</span><span class="sxs-lookup"><span data-stu-id="678b3-169">-Namespace</span></span>

<span data-ttu-id="678b3-170">Especifica o namespace para a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="678b3-170">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="678b3-171">O namespace padrão é **root/cimv2** .</span><span class="sxs-lookup"><span data-stu-id="678b3-171">The default namespace is **root/cimv2** .</span></span> <span data-ttu-id="678b3-172">Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.</span><span class="sxs-lookup"><span data-stu-id="678b3-172">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriComputerSet, ResourceUriSessionSet, QueryComputerSet, QuerySessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="678b3-173">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="678b3-173">-OperationTimeoutSec</span></span>

<span data-ttu-id="678b3-174">Especifica a quantidade de tempo que o cmdlet aguarda uma resposta do computador.</span><span class="sxs-lookup"><span data-stu-id="678b3-174">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="678b3-175">Por padrão, o valor é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.</span><span class="sxs-lookup"><span data-stu-id="678b3-175">By default, the value is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="678b3-176">Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão padrão de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis.</span><span class="sxs-lookup"><span data-stu-id="678b3-176">If the **OperationTimeoutSec** parameter is set to a value less than the default connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable.</span></span>

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

### <span data-ttu-id="678b3-177">-Query</span><span class="sxs-lookup"><span data-stu-id="678b3-177">-Query</span></span>

<span data-ttu-id="678b3-178">Especifica uma consulta a ser executada no servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="678b3-178">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="678b3-179">Um método é invocado nas instâncias recebidas como resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="678b3-179">A method is invoked on the instances received as a result of the query.</span></span> <span data-ttu-id="678b3-180">Você pode especificar o dialeto da consulta usando o parâmetro **QueryDialect** .</span><span class="sxs-lookup"><span data-stu-id="678b3-180">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

<span data-ttu-id="678b3-181">Se o valor especificado contiver aspas duplas ( `"` ), aspas simples ( `'` ) ou barra invertida ( `\` ), você deverá escapar desses caracteres prefixando-os com o caractere de barra invertida ( `\` ).</span><span class="sxs-lookup"><span data-stu-id="678b3-181">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="678b3-182">Se o valor especificado usar o operador LIKE WQL, você deverá escapar os caracteres a seguir, colocando-os entre colchetes ( `[]` ): porcentagem ( `%` ), sublinhado ( `_` ) ou colchete de abertura ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="678b3-182">If the value specified uses the WQL LIKE operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QueryComputerSet, QuerySessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="678b3-183">-QueryDialect</span><span class="sxs-lookup"><span data-stu-id="678b3-183">-QueryDialect</span></span>

<span data-ttu-id="678b3-184">Especifica a linguagem de consulta usada para o parâmetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="678b3-184">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="678b3-185">Os valores aceitáveis para esse parâmetro são: **WQL** ou **CQL** .</span><span class="sxs-lookup"><span data-stu-id="678b3-185">The acceptable values for this parameter are: **WQL** or **CQL** .</span></span>

<span data-ttu-id="678b3-186">O valor padrão é **WQL** .</span><span class="sxs-lookup"><span data-stu-id="678b3-186">The default value is **WQL** .</span></span>

```yaml
Type: System.String
Parameter Sets: QueryComputerSet, QuerySessionSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="678b3-187">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="678b3-187">-ResourceUri</span></span>

<span data-ttu-id="678b3-188">Especifica o URI (Uniform Resource Identifier) do recurso da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="678b3-188">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="678b3-189">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="678b3-189">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="678b3-190">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="678b3-190">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="678b3-191">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="678b3-191">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="678b3-192">Por padrão, se você não especificar esse parâmetro, o URI de recurso padrão do DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` será usado e o nome da classe será anexado a ele.</span><span class="sxs-lookup"><span data-stu-id="678b3-192">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="678b3-193">O **ResourceURI** só pode ser usado com sessões CIM criadas usando o protocolo WSMan ou ao especificar o parâmetro **ComputerName** , que cria uma sessão CIM usando WSMan.</span><span class="sxs-lookup"><span data-stu-id="678b3-193">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span>

<span data-ttu-id="678b3-194">Quando você especifica esse parâmetro sem especificar o parâmetro **ComputerName** , ou quando você especifica uma sessão CIM criada usando o protocolo DCOM, recebe um erro.</span><span class="sxs-lookup"><span data-stu-id="678b3-194">When you specify this parameter without specifying the **ComputerName** parameter, or when you specify a CIM session created using DCOM protocol, you get an error.</span></span> <span data-ttu-id="678b3-195">O protocolo DCOM não oferece suporte ao parâmetro **ResourceURI** .</span><span class="sxs-lookup"><span data-stu-id="678b3-195">The DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="678b3-196">Se o parâmetro **ResourceURI** e o parâmetro **Filter** forem especificados, o parâmetro **Filter** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="678b3-196">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet, CimInstanceSessionSet, CimInstanceComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="678b3-197">-Confirm</span><span class="sxs-lookup"><span data-stu-id="678b3-197">-Confirm</span></span>

<span data-ttu-id="678b3-198">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="678b3-198">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="678b3-199">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="678b3-199">-WhatIf</span></span>

<span data-ttu-id="678b3-200">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="678b3-200">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="678b3-201">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="678b3-201">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="678b3-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="678b3-202">CommonParameters</span></span>

<span data-ttu-id="678b3-203">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="678b3-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="678b3-204">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="678b3-204">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="678b3-205">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="678b3-205">INPUTS</span></span>

### <span data-ttu-id="678b3-206">Classe CIM</span><span class="sxs-lookup"><span data-stu-id="678b3-206">CIM class</span></span>

<span data-ttu-id="678b3-207">Esse cmdlet aceita uma classe CIM como um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="678b3-207">This cmdlet accepts a CIM class as an input object.</span></span>

### <span data-ttu-id="678b3-208">Instância CIM</span><span class="sxs-lookup"><span data-stu-id="678b3-208">CIM instance</span></span>

<span data-ttu-id="678b3-209">Esse cmdlet aceita uma instância CIM como um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="678b3-209">This cmdlet accepts a CIM instance as an input object.</span></span>

## <span data-ttu-id="678b3-210">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="678b3-210">OUTPUTS</span></span>

### <span data-ttu-id="678b3-211">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="678b3-211">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="678b3-212">Esse cmdlet retorna um objeto.</span><span class="sxs-lookup"><span data-stu-id="678b3-212">This cmdlet returns an object.</span></span>

## <span data-ttu-id="678b3-213">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="678b3-213">NOTES</span></span>

## <span data-ttu-id="678b3-214">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="678b3-214">RELATED LINKS</span></span>

[<span data-ttu-id="678b3-215">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="678b3-215">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="678b3-216">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="678b3-216">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="678b3-217">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="678b3-217">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="678b3-218">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="678b3-218">New-CimSession</span></span>](New-CimSession.md)
