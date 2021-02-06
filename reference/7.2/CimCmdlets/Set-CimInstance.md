---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/set-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CimInstance
ms.openlocfilehash: 041ef2d5b5541c250b98003099fe58018df155c2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596575"
---
# <span data-ttu-id="96751-102">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="96751-102">Set-CimInstance</span></span>

## <span data-ttu-id="96751-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="96751-103">SYNOPSIS</span></span>
<span data-ttu-id="96751-104">Modifica uma instância CIM em um servidor CIM chamando o método ModifyInstance da classe CIM.</span><span class="sxs-lookup"><span data-stu-id="96751-104">Modifies a CIM instance on a CIM server by calling the ModifyInstance method of the CIM class.</span></span>

## <span data-ttu-id="96751-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="96751-105">SYNTAX</span></span>

### <span data-ttu-id="96751-106">CimInstanceComputerSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="96751-106">CimInstanceComputerSet (Default)</span></span>

```
Set-CimInstance [-ComputerName <String[]>] [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="96751-107">CimInstanceSessionSet</span><span class="sxs-lookup"><span data-stu-id="96751-107">CimInstanceSessionSet</span></span>

```
Set-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="96751-108">QuerySessionSet</span><span class="sxs-lookup"><span data-stu-id="96751-108">QuerySessionSet</span></span>

```
Set-CimInstance -CimSession <CimSession[]> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="96751-109">QueryComputerSet</span><span class="sxs-lookup"><span data-stu-id="96751-109">QueryComputerSet</span></span>

```
Set-CimInstance [-ComputerName <String[]>] [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="96751-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="96751-110">DESCRIPTION</span></span>

<span data-ttu-id="96751-111">Esse cmdlet modifica uma instância CIM em um servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="96751-111">This cmdlet modifies a CIM instance on a CIM server.</span></span>

<span data-ttu-id="96751-112">Se o parâmetro **InputObject** não for especificado, o cmdlet funcionará de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="96751-112">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="96751-113">Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet funcionará no Instrumentação de gerenciamento do Windows local (WMI) usando uma sessão Component Object Model (com).</span><span class="sxs-lookup"><span data-stu-id="96751-113">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="96751-114">Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet funcionará no servidor CIM especificado pelo parâmetro **ComputerName** ou pelo parâmetro **CimSession** .</span><span class="sxs-lookup"><span data-stu-id="96751-114">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="96751-115">Se o parâmetro **InputObject** for especificado, o cmdlet funcionará de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="96751-115">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="96751-116">Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet usará a sessão CIM ou o nome do computador do objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="96751-116">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="96751-117">Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet usa o valor do parâmetro **CimSession** ou o valor do parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="96751-117">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the **CimSession** parameter value or **ComputerName** parameter value.</span></span> <span data-ttu-id="96751-118">Isso não é muito comum.</span><span class="sxs-lookup"><span data-stu-id="96751-118">This is not very common.</span></span>

## <span data-ttu-id="96751-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="96751-119">EXAMPLES</span></span>

### <span data-ttu-id="96751-120">Exemplo 1: definir a instância de CIM</span><span class="sxs-lookup"><span data-stu-id="96751-120">Example 1: Set the CIM instance</span></span>

<span data-ttu-id="96751-121">Este exemplo define o valor da propriedade **VariableValue** como **ABCD** usando o parâmetro de **consulta** .</span><span class="sxs-lookup"><span data-stu-id="96751-121">This example sets the value of the **VariableValue** property to **abcd** using the **Query** parameter.</span></span> <span data-ttu-id="96751-122">Você pode modificar instâncias que correspondem a uma consulta WQL (linguagem de consulta Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="96751-122">You can modify instances matching a Windows Management Instrumentation Query Language (WQL) query.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"}
```

### <span data-ttu-id="96751-123">Exemplo 2: definir a propriedade de instância CIM usando pipeline</span><span class="sxs-lookup"><span data-stu-id="96751-123">Example 2: Set the CIM instance property using pipeline</span></span>

<span data-ttu-id="96751-124">Este exemplo recupera o objeto de instância CIM filtrado pelo parâmetro de **consulta** usando o `Get-CimInstance` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="96751-124">This example retrieves the CIM instance object filtered by the **Query** parameter using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="96751-125">O `Set-CimInstance` cmdlet modifica o valor da propriedade **VariableValue** como **ABCD**.</span><span class="sxs-lookup"><span data-stu-id="96751-125">The `Set-CimInstance` cmdlet modifies the value of **VariableValue** property to **abcd**.</span></span>

```powershell
Get-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' |
  Set-CimInstance -Property @{VariableValue="abcd"}
```

### <span data-ttu-id="96751-126">Exemplo 3: definir a propriedade de instância CIM usando o objeto de entrada</span><span class="sxs-lookup"><span data-stu-id="96751-126">Example 3: Set the CIM instance property using input object</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where Name="testvar"'
Set-CimInstance -InputObject $x -Property @{VariableValue="somevalue"} -PassThru
```

<span data-ttu-id="96751-127">Este exemplo recupera os objetos de instância CIM filtrados pelo parâmetro de consulta em para uma variável `$x` usando `Get-CimInstance` e, em seguida, passa o conteúdo da variável para o `Set-CimInstance` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="96751-127">This example retrieves the CIM instance objects filtered by the Query parameter in to a variable `$x` using `Get-CimInstance`, and then passes the contents of the variable to the `Set-CimInstance` cmdlet.</span></span> <span data-ttu-id="96751-128">`Set-CimInstance` em seguida, modifica a propriedade **VariableValue** para **someValue**.</span><span class="sxs-lookup"><span data-stu-id="96751-128">`Set-CimInstance` then modifies the **VariableValue** property to **somevalue**.</span></span> <span data-ttu-id="96751-129">Como o parâmetro **PassThru** é usado, este exemplo retorna um objeto de instância CIM modificado.</span><span class="sxs-lookup"><span data-stu-id="96751-129">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

### <span data-ttu-id="96751-130">Exemplo 4: definir a propriedade de instância CIM</span><span class="sxs-lookup"><span data-stu-id="96751-130">Example 4: Set the CIM instance property</span></span>

<span data-ttu-id="96751-131">Este exemplo recupera o objeto de instância CIM que é especificado no parâmetro de **consulta** em uma variável `$x` usando o `Get-CimInstance` cmdlet e altera o valor da propriedade **VariableValue** do objeto a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="96751-131">This example retrieves the CIM instance object that is specified in the **Query** parameter into a variable `$x` using the `Get-CimInstance` cmdlet, and changes the **VariableValue** property value of the object to change.</span></span> <span data-ttu-id="96751-132">O objeto de instância CIM é salvo usando o `Set-CimInstance` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="96751-132">The CIM instance object is then saved using the `Set-CimInstance` cmdlet.</span></span>
<span data-ttu-id="96751-133">Como o parâmetro **PassThru** é usado, este exemplo retorna um objeto de instância CIM modificado.</span><span class="sxs-lookup"><span data-stu-id="96751-133">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where name="testvar"'
$x.VariableValue = "Change"
Set-CimInstance -CimInstance $x -PassThru
```

### <span data-ttu-id="96751-134">Exemplo 5: mostrar a lista de instâncias de CIM a serem modificadas usando WhatIf</span><span class="sxs-lookup"><span data-stu-id="96751-134">Example 5: Show the list of CIM instances to modify using WhatIf</span></span>

<span data-ttu-id="96751-135">Este exemplo usa o parâmetro comum **WhatIf** para especificar que a modificação não deve ser feita, mas apenas saída o que aconteceria se fosse feito.</span><span class="sxs-lookup"><span data-stu-id="96751-135">This example uses the common parameter **WhatIf** to specify that the modification should not be done, but only output what would happen if it were done.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -WhatIf
```

### <span data-ttu-id="96751-136">Exemplo 6: definir a instância de CIM após a confirmação do usuário</span><span class="sxs-lookup"><span data-stu-id="96751-136">Example 6: Set the CIM instance after confirmation from the user</span></span>

<span data-ttu-id="96751-137">Este exemplo usa o parâmetro comum **Confirm** para especificar que a modificação deve ser feita somente após a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="96751-137">This example uses the common parameter **Confirm** to specify that the modification should be done only after confirmation from the user.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -Confirm
```

### <span data-ttu-id="96751-138">Exemplo 7: definir a instância de CIM criada</span><span class="sxs-lookup"><span data-stu-id="96751-138">Example 7: Set the created CIM instance</span></span>

<span data-ttu-id="96751-139">Este exemplo cria uma instância CIM com as propriedades especificadas usando o `New-CimInstance` cmdlet e recupera seu conteúdo em uma variável `$x` .</span><span class="sxs-lookup"><span data-stu-id="96751-139">This example creates a CIM instance with the specified properties using the `New-CimInstance` cmdlet, and retrieves its contents in to a variable `$x`.</span></span> <span data-ttu-id="96751-140">Em seguida, a variável é passada para o `Set-CimInstance` cmdlet, que modifica o valor da propriedade **VariableValue** para **someValue**.</span><span class="sxs-lookup"><span data-stu-id="96751-140">The variable is then passed to the `Set-CimInstance` cmdlet, which modifies the value of **VariableValue** property to **somevalue**.</span></span>
<span data-ttu-id="96751-141">Como o parâmetro **PassThru** é usado, este exemplo retorna um objeto de instância CIM modificado.</span><span class="sxs-lookup"><span data-stu-id="96751-141">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

```powershell
$x = New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";UserName="domain\user"} -Keys Name,UserName -ClientOnly
Set-CimInstance -CimInstance $x -Property @{VariableValue="somevalue"} -PassThru
```

## <span data-ttu-id="96751-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="96751-142">PARAMETERS</span></span>

### <span data-ttu-id="96751-143">-CimSession</span><span class="sxs-lookup"><span data-stu-id="96751-143">-CimSession</span></span>

<span data-ttu-id="96751-144">Executa os cmdlets em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="96751-144">Runs the cmdlets on a remote computer.</span></span> <span data-ttu-id="96751-145">Insira um nome de computador ou um objeto de sessão, como a saída de `New-CimSession` um `Get-CimSession` cmdlet ou.</span><span class="sxs-lookup"><span data-stu-id="96751-145">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimInstanceSessionSet, QuerySessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="96751-146">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="96751-146">-ComputerName</span></span>

<span data-ttu-id="96751-147">Especifica o nome do computador no qual você deseja executar a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="96751-147">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="96751-148">Você pode especificar um nome de domínio totalmente qualificado (FQDN) ou um nome NetBIOS.</span><span class="sxs-lookup"><span data-stu-id="96751-148">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="96751-149">Se você não especificar esse parâmetro, o cmdlet executará a operação no computador local usando Component Object Model (COM).</span><span class="sxs-lookup"><span data-stu-id="96751-149">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="96751-150">Se você especificar esse parâmetro, o cmdlet criará uma sessão temporária para o computador especificado usando o protocolo WsMan.</span><span class="sxs-lookup"><span data-stu-id="96751-150">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="96751-151">Se várias operações estiverem sendo executadas no mesmo computador, a conexão usando uma sessão CIM fornecerá um melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="96751-151">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96751-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="96751-152">-InputObject</span></span>

<span data-ttu-id="96751-153">Especifica um objeto de instância CIM a ser usado como entrada.</span><span class="sxs-lookup"><span data-stu-id="96751-153">Specifies a CIM instance object to use as input.</span></span>

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

### <span data-ttu-id="96751-154">-Namespace</span><span class="sxs-lookup"><span data-stu-id="96751-154">-Namespace</span></span>

<span data-ttu-id="96751-155">Especifica o namespace para a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="96751-155">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="96751-156">O namespace padrão é root/cimv2.</span><span class="sxs-lookup"><span data-stu-id="96751-156">The default namespace is root/cimv2.</span></span> <span data-ttu-id="96751-157">Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.</span><span class="sxs-lookup"><span data-stu-id="96751-157">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="96751-158">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="96751-158">-OperationTimeoutSec</span></span>

<span data-ttu-id="96751-159">Especifica a quantidade de tempo que o cmdlet aguarda uma resposta do computador.</span><span class="sxs-lookup"><span data-stu-id="96751-159">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="96751-160">Por padrão, o valor desse parâmetro é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.</span><span class="sxs-lookup"><span data-stu-id="96751-160">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="96751-161">Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão robusto de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis, pois a operação no servidor expirará antes que o cliente possa se reconectar.</span><span class="sxs-lookup"><span data-stu-id="96751-161">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="96751-162">-PassThru</span><span class="sxs-lookup"><span data-stu-id="96751-162">-PassThru</span></span>

<span data-ttu-id="96751-163">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="96751-163">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="96751-164">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="96751-164">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="96751-165">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="96751-165">-Property</span></span>

<span data-ttu-id="96751-166">Especifica as propriedades da instância CIM como uma tabela de hash (usando pares de nome-valor).</span><span class="sxs-lookup"><span data-stu-id="96751-166">Specifies the properties of the CIM instance as a hash table (using name-value pairs).</span></span> <span data-ttu-id="96751-167">Somente as propriedades especificadas usando esse parâmetro são alteradas.</span><span class="sxs-lookup"><span data-stu-id="96751-167">Only the properties specified using this parameter are changed.</span></span> <span data-ttu-id="96751-168">Outras propriedades da instância CIM não são alteradas.</span><span class="sxs-lookup"><span data-stu-id="96751-168">Other properties of the CIM instance are not changed.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet, QuerySessionSet, QueryComputerSet
Aliases: Arguments

Required: True (QuerySessionSet, QueryComputerSet), False (CimInstanceComputerSet, CimInstanceSessionSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="96751-169">-Query</span><span class="sxs-lookup"><span data-stu-id="96751-169">-Query</span></span>

<span data-ttu-id="96751-170">Especifica uma consulta a ser executada no servidor CIM para recuperar as instâncias de CIM nas quais o cmdlet será executado.</span><span class="sxs-lookup"><span data-stu-id="96751-170">Specifies a query to run on the CIM server to retrieve CIM instances on which to run the cmdlet.</span></span> <span data-ttu-id="96751-171">Você pode especificar o dialeto da consulta usando o parâmetro QueryDialect.</span><span class="sxs-lookup"><span data-stu-id="96751-171">You can specify the query dialect using the QueryDialect parameter.</span></span>

<span data-ttu-id="96751-172">Se o valor especificado contiver aspas duplas ( `"` ), aspas simples ( `'` ) ou barra invertida ( `\` ), você deverá escapar desses caracteres prefixando-os com o caractere de barra invertida ( `\` ).</span><span class="sxs-lookup"><span data-stu-id="96751-172">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="96751-173">Se o valor especificado usar o operador **like** WQL, você deverá escapar os caracteres a seguir, colocando-os entre colchetes ( `[]` ): porcentagem ( `%` ), sublinhado ( `_` ) ou colchete de abertura ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="96751-173">If the value specified uses the WQL **LIKE** operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="96751-174">-QueryDialect</span><span class="sxs-lookup"><span data-stu-id="96751-174">-QueryDialect</span></span>

<span data-ttu-id="96751-175">Especifica a linguagem de consulta usada para o parâmetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="96751-175">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="96751-176">Os valores aceitáveis para esse parâmetro são: **WQL** ou **CQL**.</span><span class="sxs-lookup"><span data-stu-id="96751-176">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="96751-177">O valor padrão é **WQL**.</span><span class="sxs-lookup"><span data-stu-id="96751-177">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="96751-178">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="96751-178">-ResourceUri</span></span>

<span data-ttu-id="96751-179">Especifica o URI (Uniform Resource Identifier) do recurso da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="96751-179">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="96751-180">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="96751-180">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="96751-181">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="96751-181">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="96751-182">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="96751-182">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="96751-183">Por padrão, se você não especificar esse parâmetro, o URI de recurso padrão do DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` será usado e o nome da classe será anexado a ele.</span><span class="sxs-lookup"><span data-stu-id="96751-183">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="96751-184">O ResourceURI só pode ser usado com sessões CIM criadas usando o protocolo WSMan ou ao especificar o parâmetro ComputerName, que cria uma sessão CIM usando WSMan.</span><span class="sxs-lookup"><span data-stu-id="96751-184">ResourceURI can only be used with CIM sessions created using the WSMan protocol, or when specifying the ComputerName parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="96751-185">Se você especificar esse parâmetro sem especificar o parâmetro ComputerName ou se especificar uma sessão CIM criada usando o protocolo DCOM, receberá um erro, pois o protocolo DCOM não oferece suporte ao parâmetro ResourceURI.</span><span class="sxs-lookup"><span data-stu-id="96751-185">If you specify this parameter without specifying the ComputerName parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the ResourceURI parameter.</span></span>

<span data-ttu-id="96751-186">Se o parâmetro **ResourceURI** e o parâmetro **Filter** forem especificados, o parâmetro **Filter** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="96751-186">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="96751-187">-Confirm</span><span class="sxs-lookup"><span data-stu-id="96751-187">-Confirm</span></span>

<span data-ttu-id="96751-188">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="96751-188">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="96751-189">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="96751-189">-WhatIf</span></span>

<span data-ttu-id="96751-190">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="96751-190">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="96751-191">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="96751-191">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="96751-192">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="96751-192">CommonParameters</span></span>

<span data-ttu-id="96751-193">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="96751-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="96751-194">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="96751-194">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="96751-195">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="96751-195">INPUTS</span></span>

### <span data-ttu-id="96751-196">Microsoft. Management. Infrastructure. CimInstance</span><span class="sxs-lookup"><span data-stu-id="96751-196">Microsoft.Management.Infrastructure.CimInstance</span></span>

## <span data-ttu-id="96751-197">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="96751-197">OUTPUTS</span></span>

### <span data-ttu-id="96751-198">Microsoft. Management. Infrastructure. CimInstance</span><span class="sxs-lookup"><span data-stu-id="96751-198">Microsoft.Management.Infrastructure.CimInstance</span></span>

<span data-ttu-id="96751-199">Quando o parâmetro **PassThru** é especificado, esse cmdlet retorna um objeto de instância CIM modificado.</span><span class="sxs-lookup"><span data-stu-id="96751-199">When the **Passthru** parameter is specified, this cmdlet returns a modified CIM instance object.</span></span>

## <span data-ttu-id="96751-200">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="96751-200">NOTES</span></span>

## <span data-ttu-id="96751-201">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="96751-201">RELATED LINKS</span></span>

[<span data-ttu-id="96751-202">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="96751-202">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="96751-203">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="96751-203">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="96751-204">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="96751-204">Remove-CimInstance</span></span>](remove-ciminstance.md)

