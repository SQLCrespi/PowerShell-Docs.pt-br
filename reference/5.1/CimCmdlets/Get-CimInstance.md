---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/21/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-ciminstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimInstance
ms.openlocfilehash: 468b0e62925774fb838263b9bd9aea6a74151b5f
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194861"
---
# <span data-ttu-id="b9cbb-103">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="b9cbb-103">Get-CimInstance</span></span>

## <span data-ttu-id="b9cbb-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b9cbb-104">SYNOPSIS</span></span>
<span data-ttu-id="b9cbb-105">Obtém as instâncias CIM de uma classe de um servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-105">Gets the CIM instances of a class from a CIM server.</span></span>

## <span data-ttu-id="b9cbb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b9cbb-106">SYNTAX</span></span>

### <span data-ttu-id="b9cbb-107">ClassNameComputerSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="b9cbb-107">ClassNameComputerSet (Default)</span></span>

```
Get-CimInstance [-ClassName] <String> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="b9cbb-108">ResourceUriSessionSet</span><span class="sxs-lookup"><span data-stu-id="b9cbb-108">ResourceUriSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> -ResourceUri <Uri> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="b9cbb-109">QuerySessionSet</span><span class="sxs-lookup"><span data-stu-id="b9cbb-109">QuerySessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

### <span data-ttu-id="b9cbb-110">ClassNameSessionSet</span><span class="sxs-lookup"><span data-stu-id="b9cbb-110">ClassNameSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ClassName] <String> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="b9cbb-111">CimInstanceSessionSet</span><span class="sxs-lookup"><span data-stu-id="b9cbb-111">CimInstanceSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### <span data-ttu-id="b9cbb-112">CimInstanceComputerSet</span><span class="sxs-lookup"><span data-stu-id="b9cbb-112">CimInstanceComputerSet</span></span>

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### <span data-ttu-id="b9cbb-113">ResourceUriComputerSet</span><span class="sxs-lookup"><span data-stu-id="b9cbb-113">ResourceUriComputerSet</span></span>

```
Get-CimInstance -ResourceUri <Uri> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="b9cbb-114">QueryComputerSet</span><span class="sxs-lookup"><span data-stu-id="b9cbb-114">QueryComputerSet</span></span>

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

## <span data-ttu-id="b9cbb-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9cbb-115">DESCRIPTION</span></span>

<span data-ttu-id="b9cbb-116">O `Get-CimInstance` cmdlet obtém as instâncias CIM de uma classe de um servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-116">The `Get-CimInstance` cmdlet gets the CIM instances of a class from a CIM server.</span></span> <span data-ttu-id="b9cbb-117">Você pode especificar o nome da classe ou uma consulta para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-117">You can specify either the class name or a query for this cmdlet.</span></span> <span data-ttu-id="b9cbb-118">Esse cmdlet retorna um ou mais objetos de instância CIM que representam um instantâneo das instâncias de CIM presentes no servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-118">This cmdlet returns one or more CIM instance objects representing a snapshot of the CIM instances present on the CIM server.</span></span>

<span data-ttu-id="b9cbb-119">Se o parâmetro **InputObject** não for especificado, o cmdlet funcionará de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="b9cbb-119">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="b9cbb-120">Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet funcionará no Instrumentação de gerenciamento do Windows local (WMI) usando uma sessão Component Object Model (com).</span><span class="sxs-lookup"><span data-stu-id="b9cbb-120">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="b9cbb-121">Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet funcionará no servidor CIM especificado pelo parâmetro **ComputerName** ou pelo parâmetro **CimSession** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-121">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="b9cbb-122">Se o parâmetro **InputObject** for especificado, o cmdlet funcionará de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="b9cbb-122">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="b9cbb-123">Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet usará a sessão CIM ou o nome do computador do objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-123">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="b9cbb-124">Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet usa o valor do parâmetro CimSession ou o valor do parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-124">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the CimSession parameter value or **ComputerName** parameter value.</span></span>

## <span data-ttu-id="b9cbb-125">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b9cbb-125">EXAMPLES</span></span>

### <span data-ttu-id="b9cbb-126">Exemplo 1: obter as instâncias de CIM de uma classe especificada</span><span class="sxs-lookup"><span data-stu-id="b9cbb-126">Example 1: Get the CIM instances of a specified class</span></span>

<span data-ttu-id="b9cbb-127">Este exemplo recupera as instâncias de CIM de uma classe chamada **Win32_Process** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-127">This example retrieves the CIM instances of a class named **Win32_Process** .</span></span>

```powershell
Get-CimInstance -ClassName Win32_Process
```

### <span data-ttu-id="b9cbb-128">Exemplo 2: obter uma lista de namespaces de um servidor WMI</span><span class="sxs-lookup"><span data-stu-id="b9cbb-128">Example 2: Get a list of namespaces from a WMI server</span></span>

<span data-ttu-id="b9cbb-129">Este exemplo recupera uma lista de namespaces no namespace **raiz** em um servidor WMI.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-129">This example retrieves a list of namespaces under the **Root** namespace on a WMI server.</span></span>

```powershell
Get-CimInstance -Namespace root -ClassName __Namespace
```

### <span data-ttu-id="b9cbb-130">Exemplo 3: obter instâncias de uma classe filtrada usando uma consulta</span><span class="sxs-lookup"><span data-stu-id="b9cbb-130">Example 3: Get instances of a class filtered by using a query</span></span>

<span data-ttu-id="b9cbb-131">Este exemplo recupera todas as instâncias de CIM que começam com a letra **P** de uma classe chamada **Win32_Process** usando a consulta especificada por um parâmetro de **consulta** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-131">This example retrieves all the CIM instances that start with the letter **P** of a class named **Win32_Process** using the query specified by a **Query** parameter.</span></span>

```powershell
Get-CimInstance -Query "SELECT * from Win32_Process WHERE name LIKE 'P%'"
```

### <span data-ttu-id="b9cbb-132">Exemplo 4: obter instâncias de uma classe filtrada usando um nome de classe e uma expressão de filtro</span><span class="sxs-lookup"><span data-stu-id="b9cbb-132">Example 4: Get instances of a class filtered by using a class name and a filter expression</span></span>

<span data-ttu-id="b9cbb-133">Este exemplo recupera todas as instâncias CIM que começam com a letra **P** de uma classe chamada **Win32_Process** usando o parâmetro Filter.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-133">This example retrieves all the CIM instances that start with the letter **P** of a class named **Win32_Process** using the Filter parameter.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Process -Filter "Name like 'P%'"
```

### <span data-ttu-id="b9cbb-134">Exemplo 5: obter as instâncias de CIM com apenas as propriedades de chave preenchidas</span><span class="sxs-lookup"><span data-stu-id="b9cbb-134">Example 5: Get the CIM instances with only key properties filled in</span></span>

<span data-ttu-id="b9cbb-135">Este exemplo cria uma nova instância CIM na memória para uma classe chamada **Win32_Process** com a propriedade de chave `@{ "Handle"=0 }` e a armazena em uma variável chamada `$x` .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-135">This example creates a new CIM instance in memory for a class named **Win32_Process** with the key property `@{ "Handle"=0 }` and stores it in a variable named `$x`.</span></span> <span data-ttu-id="b9cbb-136">A variável é passada como uma instância CIM para o `Get-CimInstance` cmdlet para obter uma instância específica.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-136">The variable is passed as a CIM instance to the `Get-CimInstance` cmdlet to get a particular instance.</span></span>

```powershell
$x = New-CimInstance -ClassName Win32_Process -Namespace root\cimv2 -Property @{ "Handle"=0 } -Key Handle -ClientOnly
Get-CimInstance -CimInstance $x
```

### <span data-ttu-id="b9cbb-137">Exemplo 6: recuperar instâncias de CIM e reutilizá-las</span><span class="sxs-lookup"><span data-stu-id="b9cbb-137">Example 6: Retrieve CIM instances and reuse them</span></span>

<span data-ttu-id="b9cbb-138">Este exemplo obtém as instâncias de CIM de uma classe chamada **Win32_Process** e as armazena nas variáveis `$x` e `$y` .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-138">This example gets the CIM instances of a class named **Win32_Process** and stores them in the variables `$x` and `$y`.</span></span> <span data-ttu-id="b9cbb-139">Em seguida, a variável `$x` é formatada em uma tabela que contém apenas as propriedades **Name** e **KernelModeTime** , a tabela definida como **AutoSize** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-139">The variable `$x` is then formatted in a table containing only the **Name** and **KernelModeTime** properties, the table set to **AutoSize** .</span></span>

```powershell
$x,$y = Get-CimInstance -ClassName Win32_Process
$x | Format-Table -Property Name,KernelModeTime -AutoSize
```

```Output
Name                 KernelModeTime
----                 --------------
System Idle Process 157238797968750
```

### <span data-ttu-id="b9cbb-140">Exemplo 7: obter instâncias de CIM do computador remoto</span><span class="sxs-lookup"><span data-stu-id="b9cbb-140">Example 7: Get CIM instances from remote computer</span></span>

<span data-ttu-id="b9cbb-141">Este exemplo recupera as instâncias de CIM de uma classe chamada **Win32_ComputerSystem** dos computadores remotos chamados **Server01** e **Server02** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-141">This example retrieves the CIM instances of a class named **Win32_ComputerSystem** from the remote computers named **Server01** and **Server02** .</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -ComputerName Server01,Server02
```

### <span data-ttu-id="b9cbb-142">Exemplo 8: obtendo apenas as propriedades de chave, em vez de todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="b9cbb-142">Example 8: Getting only the key properties, instead of all properties</span></span>

<span data-ttu-id="b9cbb-143">Este exemplo recupera apenas as propriedades de chave, o que reduz o tamanho do objeto e do tráfego de rede.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-143">This example retrieves only the key properties, which reduces the size of the object and network traffic.</span></span>

```powershell
$x = Get-CimInstance -Class Win32_Process -KeyOnly
$x | Invoke-CimMethod -MethodName GetOwner
```

### <span data-ttu-id="b9cbb-144">Exemplo 9: obtendo apenas um subconjunto de propriedades, em vez de todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="b9cbb-144">Example 9: Getting only a subset of properties, instead of all properties</span></span>

<span data-ttu-id="b9cbb-145">Este exemplo recupera apenas um subconjunto de propriedades, o que reduz o tamanho do objeto e do tráfego de rede.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-145">This example retrieves only a subset of properties, which reduces the size of the object and network traffic.</span></span>

```powershell
Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x = Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x | Invoke-CimMethod -MethodName GetOwner
```

<span data-ttu-id="b9cbb-146">A instância recuperada com o parâmetro **Property** pode ser usada para executar outras operações CIM, por exemplo, `Set-CimInstance` ou `Invoke-CimMethod` .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-146">The instance retrieved with the **Property** parameter can be used to perform other CIM operations, for example `Set-CimInstance` or `Invoke-CimMethod`.</span></span>

### <span data-ttu-id="b9cbb-147">Exemplo 10: obter a instância CIM usando a sessão CIM</span><span class="sxs-lookup"><span data-stu-id="b9cbb-147">Example 10: Get the CIM instance using CIM session</span></span>

<span data-ttu-id="b9cbb-148">Este exemplo cria uma sessão CIM nos computadores chamados **Server01** e **Server02** usando o `New-CimSession` cmdlet e armazena as informações da sessão em uma variável chamada `$s` .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-148">This example creates a CIM session on the computers named **Server01** and **Server02** using the `New-CimSession` cmdlet and stores the session information in a variable named `$s`.</span></span> <span data-ttu-id="b9cbb-149">O conteúdo da variável é passado para o `Get-CimInstance` usando o parâmetro **CimSession** para obter as instâncias de CIM da classe denominada **Win32_ComputerSystem** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-149">The contents of the variable are then passed to `Get-CimInstance` by using the **CimSession** parameter, to get the CIM instances of the class named **Win32_ComputerSystem** .</span></span>

```powershell
$s = New-CimSession -ComputerName Server01,Server02
Get-CimInstance -ClassName Win32_ComputerSystem -CimSession $s
```

## <span data-ttu-id="b9cbb-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b9cbb-150">PARAMETERS</span></span>

### <span data-ttu-id="b9cbb-151">-CimSession</span><span class="sxs-lookup"><span data-stu-id="b9cbb-151">-CimSession</span></span>

<span data-ttu-id="b9cbb-152">Especifica a sessão CIM a ser usada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-152">Specifies the CIM session to use for this cmdlet.</span></span> <span data-ttu-id="b9cbb-153">Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como os `New-CimSession` `Get-CimSession` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-153">Enter a variable that contains the CIM session or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="b9cbb-154">Para obter mais informações, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="b9cbb-154">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, CimInstanceSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b9cbb-155">-ClassName</span><span class="sxs-lookup"><span data-stu-id="b9cbb-155">-ClassName</span></span>

<span data-ttu-id="b9cbb-156">Especifica o nome da classe CIM para a qual recuperar as instâncias de CIM.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-156">Specifies the name of the CIM class for which to retrieve the CIM instances.</span></span> <span data-ttu-id="b9cbb-157">Você pode usar o preenchimento com Tab para procurar a lista de classes, porque o PowerShell Obtém uma lista de classes do servidor WMI local para fornecer uma lista de nomes de classe.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-157">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

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

### <span data-ttu-id="b9cbb-158">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b9cbb-158">-ComputerName</span></span>

<span data-ttu-id="b9cbb-159">Especifica o computador no qual você deseja executar a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-159">Specifies computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="b9cbb-160">Você pode especificar um FQDN (nome de domínio totalmente qualificado), um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-160">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="b9cbb-161">Se você não especificar esse parâmetro, o cmdlet executará a operação no computador local usando Component Object Model (COM).</span><span class="sxs-lookup"><span data-stu-id="b9cbb-161">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="b9cbb-162">Se você especificar esse parâmetro, o cmdlet criará uma sessão temporária para o computador especificado usando o protocolo WsMan.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-162">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="b9cbb-163">Se várias operações estiverem sendo executadas no mesmo computador, conecte-se usando uma sessão CIM para melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-163">If multiple operations are being performed on the same computer, connect using a CIM session for better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, CimInstanceComputerSet, ResourceUriComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b9cbb-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="b9cbb-164">-Filter</span></span>

<span data-ttu-id="b9cbb-165">Especifica uma cláusula WHERE para usar como um filtro.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-165">Specifies a where clause to use as a filter.</span></span> <span data-ttu-id="b9cbb-166">Especifique a cláusula na linguagem de consulta **WQL** ou **CQL** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-166">Specify the clause in either the **WQL** or the **CQL** query language.</span></span> <span data-ttu-id="b9cbb-167">Não inclua a `WHERE` palavra-chave no valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-167">Do not include the `WHERE` keyword in the value of the parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b9cbb-168">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b9cbb-168">-InputObject</span></span>

<span data-ttu-id="b9cbb-169">Especifica um objeto de instância CIM a ser usado como entrada.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-169">Specifies a CIM instance object to use as input.</span></span>

<span data-ttu-id="b9cbb-170">Se você já estiver trabalhando com um objeto de instância CIM, poderá usar esse parâmetro para passar o objeto de instância CIM a fim de obter o instantâneo mais recente do servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-170">If you are already working with a CIM instance object, you can use this parameter to pass the CIM instance object in order to get the latest snapshot from the CIM server.</span></span> <span data-ttu-id="b9cbb-171">Quando você passa um objeto de instância CIM como uma entrada, `Get-CimInstance` o retorna o objeto do servidor usando uma operação obter CIM, em vez de uma operação de enumerar ou de consulta.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-171">When you pass a CIM instance object as an input, `Get-CimInstance` returns the object from server using a get CIM operation, instead of an enumerate or query operation.</span></span> <span data-ttu-id="b9cbb-172">O uso de uma operação get CIM é mais eficiente do que recuperar todas as instâncias e, em seguida, filtrá-las.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-172">Using a get CIM operation is more efficient than retrieving all instances and then filtering them.</span></span>

<span data-ttu-id="b9cbb-173">Se a classe CIM não implementar a operação get, a especificação do parâmetro **InputObject** retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-173">If the CIM class does not implement the get operation, then specifying the **InputObject** parameter returns an error.</span></span>

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

### <span data-ttu-id="b9cbb-174">-Somente</span><span class="sxs-lookup"><span data-stu-id="b9cbb-174">-KeyOnly</span></span>

<span data-ttu-id="b9cbb-175">Indica que somente objetos com as propriedades de chave populadas são retornados.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-175">Indicates that only objects with key properties populated are returned.</span></span> <span data-ttu-id="b9cbb-176">A especificação do parâmetro **keyonly** reduz a quantidade de dados transferidos pela rede.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-176">Specifying the **KeyOnly** parameter reduces the amount of data transferred over the network.</span></span>

<span data-ttu-id="b9cbb-177">Use o parâmetro **keyonly** para retornar apenas uma pequena parte do objeto, que pode ser usada para outras operações, como os `Set-CimInstance` `Get-CimAssociatedInstance` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-177">Use the **KeyOnly** parameter to return only a small portion of the object, which can be used for other operations, such as the `Set-CimInstance` or `Get-CimAssociatedInstance` cmdlets.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b9cbb-178">-Namespace</span><span class="sxs-lookup"><span data-stu-id="b9cbb-178">-Namespace</span></span>

<span data-ttu-id="b9cbb-179">Especifica o namespace da classe CIM.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-179">Specifies the namespace of CIM class.</span></span>

<span data-ttu-id="b9cbb-180">O namespace padrão é **root/cimv2** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-180">The default namespace is **root/cimv2** .</span></span> <span data-ttu-id="b9cbb-181">Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-181">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b9cbb-182">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="b9cbb-182">-OperationTimeoutSec</span></span>

<span data-ttu-id="b9cbb-183">Especifica a quantidade de tempo que o cmdlet aguarda uma resposta do computador.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-183">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="b9cbb-184">Por padrão, o valor desse parâmetro é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-184">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="b9cbb-185">Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão robusto de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis, pois a operação no servidor expirará antes que o cliente possa se reconectar.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-185">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="b9cbb-186">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="b9cbb-186">-Property</span></span>

<span data-ttu-id="b9cbb-187">Especifica um conjunto de propriedades de instância a serem recuperadas.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-187">Specifies a set of instance properties to retrieve.</span></span> <span data-ttu-id="b9cbb-188">Use esse parâmetro quando precisar reduzir o tamanho do objeto retornado, seja na memória ou pela rede.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-188">Use this parameter when you need to reduce the size of the object returned, either in memory or over the network.</span></span> <span data-ttu-id="b9cbb-189">O objeto retornado também contém as propriedades de chave, mesmo que você não as liste usando o parâmetro **Property** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-189">The object returned also contains the key properties even if you have not listed them using the **Property** parameter.</span></span> <span data-ttu-id="b9cbb-190">Outras propriedades da classe estão presentes, mas não são populadas.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-190">Other properties of the class are present but they are not populated.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases: SelectProperties

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b9cbb-191">-Query</span><span class="sxs-lookup"><span data-stu-id="b9cbb-191">-Query</span></span>

<span data-ttu-id="b9cbb-192">Especifica uma consulta a ser executada no servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-192">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="b9cbb-193">Se o valor especificado contiver aspas duplas `"` , aspas simples `'` ou uma barra invertida `\` , você deverá escapar desses caracteres prefixando-os com o caractere de barra invertida.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-193">If the value specified contains double quotes `"`, single quotes `'`, or a backslash `\`, you must escape those characters by prefixing them with the backslash character.</span></span> <span data-ttu-id="b9cbb-194">Se o valor especificado usar o operador **like** WQL, você deverá escapar os caracteres a seguir, colocando-os entre colchetes `[]` : percentual `%` , sublinhado `_` ou colchete de abertura `[` .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-194">If the value specified uses the WQL **LIKE** operator, then you must escape the following characters by enclosing them in square brackets `[]`: percent `%`, underscore `_`, or opening square bracket `[`.</span></span>

<span data-ttu-id="b9cbb-195">Você não pode usar uma consulta de metadados para recuperar uma lista de classes ou uma consulta de evento.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-195">You cannot use a metadata query to retrieve a list of classes or an event query.</span></span> <span data-ttu-id="b9cbb-196">Para recuperar uma lista de classes, use o `Get-CimClass` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-196">To retrieve a list of classes, use the `Get-CimClass` cmdlet.</span></span> <span data-ttu-id="b9cbb-197">Para recuperar uma consulta de evento, use o `Register-CimIndicationEvent` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-197">To retrieve an event query, use the `Register-CimIndicationEvent` cmdlet.</span></span>

<span data-ttu-id="b9cbb-198">Você pode especificar o dialeto da consulta usando o parâmetro **QueryDialect** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-198">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

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

### <span data-ttu-id="b9cbb-199">-QueryDialect</span><span class="sxs-lookup"><span data-stu-id="b9cbb-199">-QueryDialect</span></span>

<span data-ttu-id="b9cbb-200">Especifica a linguagem de consulta usada para o parâmetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-200">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="b9cbb-201">Os valores aceitáveis para esse parâmetro são: **WQL** ou **CQL** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-201">The acceptable values for this parameter are: **WQL** or **CQL** .</span></span> <span data-ttu-id="b9cbb-202">O valor padrão é **WQL** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-202">The default value is **WQL** .</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, QuerySessionSet, ClassNameSessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b9cbb-203">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="b9cbb-203">-ResourceUri</span></span>

<span data-ttu-id="b9cbb-204">Especifica o URI (Uniform Resource Identifier) do recurso da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-204">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="b9cbb-205">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-205">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="b9cbb-206">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-206">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="b9cbb-207">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b9cbb-207">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="b9cbb-208">Por padrão, se você não especificar esse parâmetro, o URI de recurso padrão do DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` será usado e o nome da classe será anexado a ele.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-208">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="b9cbb-209">O **ResourceURI** só pode ser usado com sessões CIM criadas usando o protocolo WSMan ou ao especificar o parâmetro **ComputerName** , que cria uma sessão CIM usando WSMan.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-209">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="b9cbb-210">Se você especificar esse parâmetro sem especificar o parâmetro **ComputerName** ou se especificar uma sessão CIM criada usando o protocolo DCOM, receberá um erro, pois o protocolo DCOM não oferece suporte ao parâmetro **ResourceURI** .</span><span class="sxs-lookup"><span data-stu-id="b9cbb-210">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="b9cbb-211">Se o parâmetro **ResourceURI** e o parâmetro **Filter** forem especificados, o parâmetro **Filter** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-211">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet, QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b9cbb-212">-Superficial</span><span class="sxs-lookup"><span data-stu-id="b9cbb-212">-Shallow</span></span>

<span data-ttu-id="b9cbb-213">Indica que as instâncias de uma classe são retornadas sem incluir as instâncias de quaisquer classes filhas.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-213">Indicates that the instances of a class are returned without including the instances of any child classes.</span></span> <span data-ttu-id="b9cbb-214">Por padrão, o cmdlet retorna as instâncias de uma classe e suas classes filhas.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-214">By default, the cmdlet returns the instances of a class and its child classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b9cbb-215">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b9cbb-215">CommonParameters</span></span>

<span data-ttu-id="b9cbb-216">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-216">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b9cbb-217">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b9cbb-217">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b9cbb-218">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b9cbb-218">INPUTS</span></span>

### <span data-ttu-id="b9cbb-219">Microsoft. Management. Infrastructure. CimInstance</span><span class="sxs-lookup"><span data-stu-id="b9cbb-219">Microsoft.Management.Infrastructure.CimInstance</span></span>

<span data-ttu-id="b9cbb-220">Esse cmdlet aceita um objeto de entrada especificado com o parâmetro InputObject.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-220">This cmdlet accepts an input objects specified with the InputObject parameter.</span></span>

## <span data-ttu-id="b9cbb-221">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b9cbb-221">OUTPUTS</span></span>

### <span data-ttu-id="b9cbb-222">Microsoft. Management. Infrastructure. CimInstance</span><span class="sxs-lookup"><span data-stu-id="b9cbb-222">Microsoft.Management.Infrastructure.CimInstance</span></span>

<span data-ttu-id="b9cbb-223">Esse cmdlet retorna um ou mais objetos de instância CIM que representam um instantâneo das instâncias de CIM no servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="b9cbb-223">This cmdlet returns one or more CIM instance objects representing a snapshot of the CIM instances on the CIM server.</span></span>

## <span data-ttu-id="b9cbb-224">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b9cbb-224">NOTES</span></span>

## <span data-ttu-id="b9cbb-225">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b9cbb-225">RELATED LINKS</span></span>

[<span data-ttu-id="b9cbb-226">Format-Table</span><span class="sxs-lookup"><span data-stu-id="b9cbb-226">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="b9cbb-227">Get-CimAssociatedInstance</span><span class="sxs-lookup"><span data-stu-id="b9cbb-227">Get-CimAssociatedInstance</span></span>](Get-CimAssociatedInstance.md)

[<span data-ttu-id="b9cbb-228">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="b9cbb-228">Get-CimClass</span></span>](Get-CimClass.md)

[<span data-ttu-id="b9cbb-229">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="b9cbb-229">Invoke-CimMethod</span></span>](invoke-cimmethod.md)

[<span data-ttu-id="b9cbb-230">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="b9cbb-230">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="b9cbb-231">Register-CimIndicationEvent</span><span class="sxs-lookup"><span data-stu-id="b9cbb-231">Register-CimIndicationEvent</span></span>](Register-CimIndicationEvent.md)

[<span data-ttu-id="b9cbb-232">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="b9cbb-232">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="b9cbb-233">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="b9cbb-233">Set-CimInstance</span></span>](Set-CimInstance.md)
