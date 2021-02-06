---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 01/21/2020
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/invoke-cimmethod?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CimMethod
ms.openlocfilehash: 1217e07d09213d7c0e223129207c085b9ba2d48d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597388"
---
# <span data-ttu-id="046b9-102">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="046b9-102">Invoke-CimMethod</span></span>

## <span data-ttu-id="046b9-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="046b9-103">SYNOPSIS</span></span>
<span data-ttu-id="046b9-104">Invoca um método de uma classe CIM.</span><span class="sxs-lookup"><span data-stu-id="046b9-104">Invokes a method of a CIM class.</span></span>

## <span data-ttu-id="046b9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="046b9-105">SYNTAX</span></span>

### <span data-ttu-id="046b9-106">ClassNameComputerSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="046b9-106">ClassNameComputerSet (Default)</span></span>

```
Invoke-CimMethod [-ClassName] <String> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="046b9-107">ClassNameSessionSet</span><span class="sxs-lookup"><span data-stu-id="046b9-107">ClassNameSessionSet</span></span>

```
Invoke-CimMethod [-ClassName] <String> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="046b9-108">ResourceUriComputerSet</span><span class="sxs-lookup"><span data-stu-id="046b9-108">ResourceUriComputerSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="046b9-109">CimInstanceSessionSet</span><span class="sxs-lookup"><span data-stu-id="046b9-109">CimInstanceSessionSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="046b9-110">CimInstanceComputerSet</span><span class="sxs-lookup"><span data-stu-id="046b9-110">CimInstanceComputerSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="046b9-111">ResourceUriSessionSet</span><span class="sxs-lookup"><span data-stu-id="046b9-111">ResourceUriSessionSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="046b9-112">CimClassComputerSet</span><span class="sxs-lookup"><span data-stu-id="046b9-112">CimClassComputerSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="046b9-113">CimClassSessionSet</span><span class="sxs-lookup"><span data-stu-id="046b9-113">CimClassSessionSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="046b9-114">QueryComputerSet</span><span class="sxs-lookup"><span data-stu-id="046b9-114">QueryComputerSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="046b9-115">QuerySessionSet</span><span class="sxs-lookup"><span data-stu-id="046b9-115">QuerySessionSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="046b9-116">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="046b9-116">DESCRIPTION</span></span>

<span data-ttu-id="046b9-117">O `Invoke-CimMethod` cmdlet invoca um método de uma classe CIM ou uma instância CIM usando os pares nome-valor especificados pelo parâmetro **arguments** .</span><span class="sxs-lookup"><span data-stu-id="046b9-117">The `Invoke-CimMethod` cmdlet invokes a method of a CIM class or CIM instance using the name-value pairs specified by the **Arguments** parameter.</span></span>

<span data-ttu-id="046b9-118">Se o parâmetro **InputObject** não for especificado, o cmdlet funcionará de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="046b9-118">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="046b9-119">Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet funcionará no Instrumentação de gerenciamento do Windows local (WMI) usando uma sessão Component Object Model (com).</span><span class="sxs-lookup"><span data-stu-id="046b9-119">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="046b9-120">Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet funcionará no servidor CIM especificado pelo parâmetro **ComputerName** ou pelo parâmetro **CimSession** .</span><span class="sxs-lookup"><span data-stu-id="046b9-120">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="046b9-121">Se o parâmetro **InputObject** for especificado, o cmdlet funcionará de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="046b9-121">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="046b9-122">Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet usará a sessão CIM ou o nome do computador do objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="046b9-122">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="046b9-123">Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet usa o valor do parâmetro **CimSession** ou o valor do parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="046b9-123">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the **CimSession** parameter value or **ComputerName** parameter value.</span></span> <span data-ttu-id="046b9-124">Esse não é um cenário comum.</span><span class="sxs-lookup"><span data-stu-id="046b9-124">This is not a common scenario.</span></span>

## <span data-ttu-id="046b9-125">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="046b9-125">EXAMPLES</span></span>

### <span data-ttu-id="046b9-126">Exemplo 1: invocar um método</span><span class="sxs-lookup"><span data-stu-id="046b9-126">Example 1: Invoke a method</span></span>

<span data-ttu-id="046b9-127">Este exemplo invoca o método **Terminate** da classe **Win32_Process** .</span><span class="sxs-lookup"><span data-stu-id="046b9-127">This example invokes the **Terminate** method of the **Win32_Process** class.</span></span>

```powershell
Invoke-CimMethod -Query 'select * from Win32_Process where name like "notepad%"' -MethodName "Terminate"
```

### <span data-ttu-id="046b9-128">Exemplo 2: invocar um método usando o objeto de instância CIM</span><span class="sxs-lookup"><span data-stu-id="046b9-128">Example 2: Invoke a method using CIM instance object</span></span>

<span data-ttu-id="046b9-129">Este exemplo recupera o objeto de instância CIM e o armazena em uma variável chamada `$x` usando o `Get-CimInstance` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="046b9-129">This example retrieves the CIM instance object and stores it in a variable named `$x` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="046b9-130">O conteúdo da variável é usado como **InputObject** para o `Invoke-CimMethod` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="046b9-130">The contents of the variable are then used as the **InputObject** for the `Invoke-CimMethod` cmdlet.</span></span> <span data-ttu-id="046b9-131">O método **GetOwner** é invocado para o **CimInstance**.</span><span class="sxs-lookup"><span data-stu-id="046b9-131">The **GetOwner** method is invoked for the **CimInstance**.</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Process where name like "notepad%"'
Invoke-CimMethod -InputObject $x -MethodName GetOwner
```

### <span data-ttu-id="046b9-132">Exemplo 3: invocar um método estático usando argumentos</span><span class="sxs-lookup"><span data-stu-id="046b9-132">Example 3: Invoke a static method using arguments</span></span>

<span data-ttu-id="046b9-133">Este exemplo invoca o método **Create** chamado usando o parâmetro **arguments** .</span><span class="sxs-lookup"><span data-stu-id="046b9-133">This example invokes the **Create** method named using the **Arguments** parameter.</span></span>

```powershell
Invoke-CimMethod -ClassName Win32_Process -MethodName "Create" -Arguments @{
  CommandLine = 'notepad.exe'; CurrentDirectory = "C:\windows\system32"
}
```

### <span data-ttu-id="046b9-134">Exemplo 4: validação no lado do cliente</span><span class="sxs-lookup"><span data-stu-id="046b9-134">Example 4: Client-side validation</span></span>

<span data-ttu-id="046b9-135">Este exemplo executa a validação do lado do cliente para o método **XYZ** passando um objeto **CimClass** para `Invoke-CimMethod` .</span><span class="sxs-lookup"><span data-stu-id="046b9-135">This example performs client-side validation for the **xyz** method by passing a **CimClass** object to `Invoke-CimMethod`.</span></span>

```powershell
$c = Get-CimClass -ClassName Win32_Process
Invoke-CimMethod -CimClass $c -MethodName "xyz" -Arguments @{ CommandLine = 'notepad.exe' }
```

## <span data-ttu-id="046b9-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="046b9-136">PARAMETERS</span></span>

### <span data-ttu-id="046b9-137">-Arguments</span><span class="sxs-lookup"><span data-stu-id="046b9-137">-Arguments</span></span>

<span data-ttu-id="046b9-138">Especifica os parâmetros a passar para o método chamado.</span><span class="sxs-lookup"><span data-stu-id="046b9-138">Specifies the parameters to pass to the called method.</span></span> <span data-ttu-id="046b9-139">Especifique os valores para esse parâmetro como pares de nome-valor, armazenados em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="046b9-139">Specify the values for this parameter as name-value pairs, stored in a hash table.</span></span> <span data-ttu-id="046b9-140">A ordem dos valores inseridos não é importante.</span><span class="sxs-lookup"><span data-stu-id="046b9-140">The order of the values entered isn't important.</span></span>

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

### <span data-ttu-id="046b9-141">-CimClass</span><span class="sxs-lookup"><span data-stu-id="046b9-141">-CimClass</span></span>

<span data-ttu-id="046b9-142">Especifica um objeto de classe CIM que representa uma definição de classe CIM no servidor.</span><span class="sxs-lookup"><span data-stu-id="046b9-142">Specifies a CIM class object that represents a CIM class definition on the server.</span></span> <span data-ttu-id="046b9-143">Use esse parâmetro ao invocar um método estático de uma classe.</span><span class="sxs-lookup"><span data-stu-id="046b9-143">Use this parameter when invoking a static method of a class.</span></span>

<span data-ttu-id="046b9-144">Você pode usar o `Get-CimClass` cmdlet para recuperar uma definição de classe do servidor.</span><span class="sxs-lookup"><span data-stu-id="046b9-144">You can use the `Get-CimClass` cmdlet to retrieve a class definition from the server.</span></span>

<span data-ttu-id="046b9-145">O uso desse parâmetro resulta em validações de esquema melhores do cliente.</span><span class="sxs-lookup"><span data-stu-id="046b9-145">Using this parameter results in better client side schema validations.</span></span>

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

### <span data-ttu-id="046b9-146">-CimSession</span><span class="sxs-lookup"><span data-stu-id="046b9-146">-CimSession</span></span>

<span data-ttu-id="046b9-147">Executa o comando usando a sessão CIM especificada.</span><span class="sxs-lookup"><span data-stu-id="046b9-147">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="046b9-148">Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como os `New-CimSession` `Get-CimSession` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="046b9-148">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="046b9-149">Para obter mais informações, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="046b9-149">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

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

### <span data-ttu-id="046b9-150">-ClassName</span><span class="sxs-lookup"><span data-stu-id="046b9-150">-ClassName</span></span>

<span data-ttu-id="046b9-151">Especifica o nome da classe CIM para a qual executar a operação.</span><span class="sxs-lookup"><span data-stu-id="046b9-151">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="046b9-152">Esse parâmetro é usado somente para métodos estáticos.</span><span class="sxs-lookup"><span data-stu-id="046b9-152">This parameter is only used for static methods.</span></span> <span data-ttu-id="046b9-153">Você pode usar o preenchimento com Tab para procurar a lista de classes, porque o PowerShell Obtém uma lista de classes do servidor WMI local para fornecer uma lista de nomes de classe.</span><span class="sxs-lookup"><span data-stu-id="046b9-153">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

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

### <span data-ttu-id="046b9-154">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="046b9-154">-ComputerName</span></span>

<span data-ttu-id="046b9-155">Especifica o nome do computador no qual você deseja executar a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="046b9-155">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="046b9-156">Você pode especificar um FQDN (nome de domínio totalmente qualificado), um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="046b9-156">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="046b9-157">Ao usar esse parâmetro, o cmdlet cria uma sessão temporária para o computador especificado usando o protocolo WsMan.</span><span class="sxs-lookup"><span data-stu-id="046b9-157">When using this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span> <span data-ttu-id="046b9-158">Caso contrário, o cmdlet executará a operação no computador local usando a Component Object Model (COM).</span><span class="sxs-lookup"><span data-stu-id="046b9-158">Otherwise, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="046b9-159">Conecte-se usando uma sessão CIM para melhorar o desempenho quando várias operações estiverem sendo executadas no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="046b9-159">Connect using a CIM session for better performance when multiple operations are being performed on the same computer.</span></span>

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

### <span data-ttu-id="046b9-160">-InputObject</span><span class="sxs-lookup"><span data-stu-id="046b9-160">-InputObject</span></span>

<span data-ttu-id="046b9-161">Especifica um objeto de instância CIM a ser usado como entrada para invocar um método.</span><span class="sxs-lookup"><span data-stu-id="046b9-161">Specifies a CIM instance object to use as input to invoke a method.</span></span> <span data-ttu-id="046b9-162">Esse parâmetro só pode ser usado para invocar métodos de instância.</span><span class="sxs-lookup"><span data-stu-id="046b9-162">This parameter can only be used to invoke instance methods.</span></span> <span data-ttu-id="046b9-163">Para invocar métodos estáticos de classe, use o parâmetro de **classe** ou o parâmetro **CimClass** .</span><span class="sxs-lookup"><span data-stu-id="046b9-163">To invoke class static methods, use the **Class** parameter or the **CimClass** parameter.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="046b9-164">-MethodName</span><span class="sxs-lookup"><span data-stu-id="046b9-164">-MethodName</span></span>

<span data-ttu-id="046b9-165">Especifica o nome do método CIM a ser invocado.</span><span class="sxs-lookup"><span data-stu-id="046b9-165">Specifies the name of the CIM method to invoke.</span></span> <span data-ttu-id="046b9-166">Este parâmetro é obrigatório e não pode ser nulo ou vazio.</span><span class="sxs-lookup"><span data-stu-id="046b9-166">This parameter is mandatory and cannot be null or empty.</span></span> <span data-ttu-id="046b9-167">Para invocar o método estático de uma classe CIM, use o **ClassName** ou o parâmetro **CimClass** .</span><span class="sxs-lookup"><span data-stu-id="046b9-167">To invoke static method of a CIM class use the **ClassName** or the **CimClass** parameter.</span></span>

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

### <span data-ttu-id="046b9-168">-Namespace</span><span class="sxs-lookup"><span data-stu-id="046b9-168">-Namespace</span></span>

<span data-ttu-id="046b9-169">Especifica o namespace para a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="046b9-169">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="046b9-170">O namespace padrão é **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="046b9-170">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="046b9-171">Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.</span><span class="sxs-lookup"><span data-stu-id="046b9-171">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriComputerSet, ResourceUriSessionSet, QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="046b9-172">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="046b9-172">-OperationTimeoutSec</span></span>

<span data-ttu-id="046b9-173">Especifica a quantidade de tempo que o cmdlet aguarda uma resposta do computador.</span><span class="sxs-lookup"><span data-stu-id="046b9-173">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="046b9-174">Por padrão, o valor é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.</span><span class="sxs-lookup"><span data-stu-id="046b9-174">By default, the value is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="046b9-175">Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão padrão de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis.</span><span class="sxs-lookup"><span data-stu-id="046b9-175">If the **OperationTimeoutSec** parameter is set to a value less than the default connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable.</span></span>

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

### <span data-ttu-id="046b9-176">-Query</span><span class="sxs-lookup"><span data-stu-id="046b9-176">-Query</span></span>

<span data-ttu-id="046b9-177">Especifica uma consulta a ser executada no servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="046b9-177">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="046b9-178">Um método é invocado nas instâncias recebidas como resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="046b9-178">A method is invoked on the instances received as a result of the query.</span></span> <span data-ttu-id="046b9-179">Você pode especificar o dialeto da consulta usando o parâmetro **QueryDialect** .</span><span class="sxs-lookup"><span data-stu-id="046b9-179">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

<span data-ttu-id="046b9-180">Se o valor especificado contiver aspas duplas ( `"` ), aspas simples ( `'` ) ou barra invertida ( `\` ), você deverá escapar desses caracteres prefixando-os com o caractere de barra invertida ( `\` ).</span><span class="sxs-lookup"><span data-stu-id="046b9-180">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="046b9-181">Se o valor especificado usar o operador LIKE WQL, você deverá escapar os caracteres a seguir, colocando-os entre colchetes ( `[]` ): porcentagem ( `%` ), sublinhado ( `_` ) ou colchete de abertura ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="046b9-181">If the value specified uses the WQL LIKE operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="046b9-182">-QueryDialect</span><span class="sxs-lookup"><span data-stu-id="046b9-182">-QueryDialect</span></span>

<span data-ttu-id="046b9-183">Especifica a linguagem de consulta usada para o parâmetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="046b9-183">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="046b9-184">Os valores aceitáveis para esse parâmetro são: **WQL** ou **CQL**.</span><span class="sxs-lookup"><span data-stu-id="046b9-184">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span>

<span data-ttu-id="046b9-185">O valor padrão é **WQL**.</span><span class="sxs-lookup"><span data-stu-id="046b9-185">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="046b9-186">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="046b9-186">-ResourceUri</span></span>

<span data-ttu-id="046b9-187">Especifica o URI (Uniform Resource Identifier) do recurso da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="046b9-187">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="046b9-188">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="046b9-188">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="046b9-189">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="046b9-189">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="046b9-190">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="046b9-190">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="046b9-191">Por padrão, se você não especificar esse parâmetro, o URI de recurso padrão do DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` será usado e o nome da classe será anexado a ele.</span><span class="sxs-lookup"><span data-stu-id="046b9-191">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="046b9-192">O **ResourceURI** só pode ser usado com sessões CIM criadas usando o protocolo WSMan ou ao especificar o parâmetro **ComputerName** , que cria uma sessão CIM usando WSMan.</span><span class="sxs-lookup"><span data-stu-id="046b9-192">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span>

<span data-ttu-id="046b9-193">Quando você especifica esse parâmetro sem especificar o parâmetro **ComputerName** , ou quando você especifica uma sessão CIM criada usando o protocolo DCOM, recebe um erro.</span><span class="sxs-lookup"><span data-stu-id="046b9-193">When you specify this parameter without specifying the **ComputerName** parameter, or when you specify a CIM session created using DCOM protocol, you get an error.</span></span> <span data-ttu-id="046b9-194">O protocolo DCOM não oferece suporte ao parâmetro **ResourceURI** .</span><span class="sxs-lookup"><span data-stu-id="046b9-194">The DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="046b9-195">Se o parâmetro **ResourceURI** e o parâmetro **Filter** forem especificados, o parâmetro **Filter** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="046b9-195">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="046b9-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="046b9-196">-Confirm</span></span>

<span data-ttu-id="046b9-197">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="046b9-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="046b9-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="046b9-198">-WhatIf</span></span>

<span data-ttu-id="046b9-199">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="046b9-199">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="046b9-200">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="046b9-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="046b9-201">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="046b9-201">CommonParameters</span></span>

<span data-ttu-id="046b9-202">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="046b9-202">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="046b9-203">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="046b9-203">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="046b9-204">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="046b9-204">INPUTS</span></span>

### <span data-ttu-id="046b9-205">Classe CIM</span><span class="sxs-lookup"><span data-stu-id="046b9-205">CIM class</span></span>

<span data-ttu-id="046b9-206">Esse cmdlet aceita uma classe CIM como um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="046b9-206">This cmdlet accepts a CIM class as an input object.</span></span>

### <span data-ttu-id="046b9-207">Instância CIM</span><span class="sxs-lookup"><span data-stu-id="046b9-207">CIM instance</span></span>

<span data-ttu-id="046b9-208">Esse cmdlet aceita uma instância CIM como um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="046b9-208">This cmdlet accepts a CIM instance as an input object.</span></span>

## <span data-ttu-id="046b9-209">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="046b9-209">OUTPUTS</span></span>

### <span data-ttu-id="046b9-210">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="046b9-210">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="046b9-211">Esse cmdlet retorna um objeto.</span><span class="sxs-lookup"><span data-stu-id="046b9-211">This cmdlet returns an object.</span></span>

## <span data-ttu-id="046b9-212">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="046b9-212">NOTES</span></span>

## <span data-ttu-id="046b9-213">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="046b9-213">RELATED LINKS</span></span>

[<span data-ttu-id="046b9-214">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="046b9-214">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="046b9-215">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="046b9-215">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="046b9-216">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="046b9-216">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="046b9-217">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="046b9-217">New-CimSession</span></span>](New-CimSession.md)

