---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimInstance
ms.openlocfilehash: 5a23aaa59eb10ff35ecefb7365d3294cdb06f781
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596167"
---
# <span data-ttu-id="a26d2-102">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="a26d2-102">Remove-CimInstance</span></span>

## <span data-ttu-id="a26d2-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a26d2-103">SYNOPSIS</span></span>
<span data-ttu-id="a26d2-104">Remove uma instância CIM de um computador.</span><span class="sxs-lookup"><span data-stu-id="a26d2-104">Removes a CIM instance from a computer.</span></span>

## <span data-ttu-id="a26d2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a26d2-105">SYNTAX</span></span>

### <span data-ttu-id="a26d2-106">CimInstanceComputerSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="a26d2-106">CimInstanceComputerSet (Default)</span></span>

```
Remove-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a26d2-107">CimInstanceSessionSet</span><span class="sxs-lookup"><span data-stu-id="a26d2-107">CimInstanceSessionSet</span></span>

```
Remove-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a26d2-108">QuerySessionSet</span><span class="sxs-lookup"><span data-stu-id="a26d2-108">QuerySessionSet</span></span>

```
Remove-CimInstance -CimSession <CimSession[]> [[-Namespace] <String>]
 [-OperationTimeoutSec <UInt32>] [-Query] <String> [-QueryDialect <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="a26d2-109">QueryComputerSet</span><span class="sxs-lookup"><span data-stu-id="a26d2-109">QueryComputerSet</span></span>

```
Remove-CimInstance [-ComputerName <String[]>] [[-Namespace] <String>]
 [-OperationTimeoutSec <UInt32>] [-Query] <String> [-QueryDialect <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="a26d2-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a26d2-110">DESCRIPTION</span></span>

<span data-ttu-id="a26d2-111">Esse cmdlet Remove uma instância CIM de um servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="a26d2-111">This cmdlet removes a CIM instance from a CIM server.</span></span> <span data-ttu-id="a26d2-112">Você pode especificar a instância CIM a ser removida usando um objeto de instância CIM recuperado pelo `Get-CimInstance` cmdlet ou especificando uma consulta.</span><span class="sxs-lookup"><span data-stu-id="a26d2-112">You can specify the CIM instance to remove by using either a CIM instance object retrieved by the `Get-CimInstance` cmdlet, or by specifying a query.</span></span>

<span data-ttu-id="a26d2-113">Se o parâmetro **InputObject** não for especificado, o cmdlet funcionará de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="a26d2-113">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="a26d2-114">Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet funcionará no Instrumentação de gerenciamento do Windows local (WMI) usando uma sessão Component Object Model (com).</span><span class="sxs-lookup"><span data-stu-id="a26d2-114">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="a26d2-115">Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet funcionará no servidor CIM especificado pelo parâmetro **ComputerName** ou pelo parâmetro **CimSession** .</span><span class="sxs-lookup"><span data-stu-id="a26d2-115">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

## <span data-ttu-id="a26d2-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a26d2-116">EXAMPLES</span></span>

### <span data-ttu-id="a26d2-117">Exemplo 1: remover a instância CIM</span><span class="sxs-lookup"><span data-stu-id="a26d2-117">Example 1: Remove the CIM instance</span></span>

<span data-ttu-id="a26d2-118">Este exemplo usa o parâmetro de **consulta** para remover as instâncias de CIM da classe denominada **Win32_Environment** que começam com a cadeia de caracteres **testvar** .</span><span class="sxs-lookup"><span data-stu-id="a26d2-118">This example use the **Query** parameter to remove CIM instances from the class named **Win32_Environment** that start with the character string **testvar** .</span></span>

```powershell
Remove-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"'
```

### <span data-ttu-id="a26d2-119">Exemplo 2: remover a instância CIM usando o objeto de instância CIM</span><span class="sxs-lookup"><span data-stu-id="a26d2-119">Example 2: Remove the CIM instance using CIM instance object</span></span>

<span data-ttu-id="a26d2-120">Este exemplo recupera os objetos de instância CIM filtrados pelo parâmetro de **consulta** e os armazena em `$var` uma variável chamada usando o `Get-CimInstance` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a26d2-120">This example retrieves the CIM instance objects filtered by the **Query** parameter and stores them in variable named `$var` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="a26d2-121">O conteúdo da variável é passado para o `Remove-CimInstance` cmdlet, que remove as instâncias de CIM.</span><span class="sxs-lookup"><span data-stu-id="a26d2-121">The contents of the variable are then passed to the `Remove-CimInstance` cmdlet, which removes the CIM instances.</span></span>

```powershell
notepad.exe
$var = Get-CimInstance -Query 'Select * from Win32_Process where name LIKE "notepad%"'
Remove-CimInstance -InputObject $var
```

## <span data-ttu-id="a26d2-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a26d2-122">PARAMETERS</span></span>

### <span data-ttu-id="a26d2-123">-CimSession</span><span class="sxs-lookup"><span data-stu-id="a26d2-123">-CimSession</span></span>

<span data-ttu-id="a26d2-124">Executa o comando usando a sessão CIM especificada.</span><span class="sxs-lookup"><span data-stu-id="a26d2-124">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="a26d2-125">Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como os `New-CimSession` `Get-CimSession` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="a26d2-125">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="a26d2-126">Para obter mais informações, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="a26d2-126">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

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

### <span data-ttu-id="a26d2-127">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="a26d2-127">-ComputerName</span></span>

<span data-ttu-id="a26d2-128">Especifica o nome do computador no qual você deseja executar a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="a26d2-128">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="a26d2-129">Você pode especificar um nome de domínio totalmente qualificado (FQDN) ou um nome NetBIOS.</span><span class="sxs-lookup"><span data-stu-id="a26d2-129">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="a26d2-130">Se você especificar esse parâmetro, o cmdlet criará uma sessão temporária para o computador especificado usando o protocolo WsMan.</span><span class="sxs-lookup"><span data-stu-id="a26d2-130">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="a26d2-131">Se você não especificar esse parâmetro, o cmdlet executará a operação no computador local usando Component Object Model (COM).</span><span class="sxs-lookup"><span data-stu-id="a26d2-131">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="a26d2-132">Se várias operações estiverem sendo executadas no mesmo computador, a conexão usando uma sessão CIM fornecerá um melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="a26d2-132">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

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

### <span data-ttu-id="a26d2-133">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a26d2-133">-InputObject</span></span>

<span data-ttu-id="a26d2-134">Especifica um objeto de instância CIM a ser removido do servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="a26d2-134">Specifies a CIM instance object to be removed from the CIM server.</span></span> <span data-ttu-id="a26d2-135">O objeto passado para o cmdlet não é alterado, somente a instância no servidor CIM é removida.</span><span class="sxs-lookup"><span data-stu-id="a26d2-135">The object passed to the cmdlet is not changed, only the instance in the CIM server is removed.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a26d2-136">-Namespace</span><span class="sxs-lookup"><span data-stu-id="a26d2-136">-Namespace</span></span>

<span data-ttu-id="a26d2-137">Especifica o namespace para a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="a26d2-137">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="a26d2-138">O namespace padrão é **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="a26d2-138">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="a26d2-139">Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.</span><span class="sxs-lookup"><span data-stu-id="a26d2-139">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a26d2-140">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="a26d2-140">-OperationTimeoutSec</span></span>

<span data-ttu-id="a26d2-141">Especifica a quantidade de tempo que o cmdlet aguarda uma resposta do computador.</span><span class="sxs-lookup"><span data-stu-id="a26d2-141">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="a26d2-142">Por padrão, o valor desse parâmetro é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.</span><span class="sxs-lookup"><span data-stu-id="a26d2-142">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="a26d2-143">Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão robusto de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis, pois a operação no servidor expirará antes que o cliente possa se reconectar.</span><span class="sxs-lookup"><span data-stu-id="a26d2-143">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="a26d2-144">-Query</span><span class="sxs-lookup"><span data-stu-id="a26d2-144">-Query</span></span>

<span data-ttu-id="a26d2-145">Especifica uma consulta a ser executada no servidor CIM.</span><span class="sxs-lookup"><span data-stu-id="a26d2-145">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="a26d2-146">Você pode especificar o dialeto da consulta usando o parâmetro **QueryDialect** .</span><span class="sxs-lookup"><span data-stu-id="a26d2-146">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

<span data-ttu-id="a26d2-147">Se o valor especificado contiver aspas duplas ( `"` ), aspas simples ( `'` ) ou barra invertida ( `\` ), você deverá escapar desses caracteres prefixando-os com o caractere de barra invertida ( `\` ).</span><span class="sxs-lookup"><span data-stu-id="a26d2-147">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="a26d2-148">Se o valor especificado usar o operador LIKE WQL, você deverá escapar os caracteres a seguir, colocando-os entre colchetes ( `[]` ): porcentagem ( `%` ), sublinhado ( `_` ) ou colchete de abertura ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="a26d2-148">If the value specified uses the WQL LIKE operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a26d2-149">-QueryDialect</span><span class="sxs-lookup"><span data-stu-id="a26d2-149">-QueryDialect</span></span>

<span data-ttu-id="a26d2-150">Especifica a linguagem de consulta usada para o parâmetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="a26d2-150">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="a26d2-151">Os valores aceitáveis para esse parâmetro são: **WQL** ou **CQL**.</span><span class="sxs-lookup"><span data-stu-id="a26d2-151">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="a26d2-152">O valor padrão é **WQL**.</span><span class="sxs-lookup"><span data-stu-id="a26d2-152">The default value is **WQL**.</span></span>

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

### <span data-ttu-id="a26d2-153">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="a26d2-153">-ResourceUri</span></span>

<span data-ttu-id="a26d2-154">Especifica o URI (Uniform Resource Identifier) do recurso da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="a26d2-154">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="a26d2-155">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="a26d2-155">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="a26d2-156">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="a26d2-156">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="a26d2-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a26d2-157">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="a26d2-158">Por padrão, se você não especificar esse parâmetro, o URI de recurso padrão do DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` será usado e o nome da classe será anexado a ele.</span><span class="sxs-lookup"><span data-stu-id="a26d2-158">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="a26d2-159">O ResourceURI só pode ser usado com sessões CIM criadas usando o protocolo WSMan ou ao especificar o parâmetro ComputerName, que cria uma sessão CIM usando WSMan.</span><span class="sxs-lookup"><span data-stu-id="a26d2-159">ResourceURI can only be used with CIM sessions created using the WSMan protocol, or when specifying the ComputerName parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="a26d2-160">Se você especificar esse parâmetro sem especificar o parâmetro ComputerName ou se especificar uma sessão CIM criada usando o protocolo DCOM, receberá um erro, pois o protocolo DCOM não oferece suporte ao parâmetro ResourceURI.</span><span class="sxs-lookup"><span data-stu-id="a26d2-160">If you specify this parameter without specifying the ComputerName parameter, or if you specify a CIM session created using DCOM protocol, you get an error, because the DCOM protocol does not support the ResourceURI parameter.</span></span>

<span data-ttu-id="a26d2-161">Se o parâmetro **ResourceURI** e o parâmetro **Filter** forem especificados, o parâmetro **Filter** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="a26d2-161">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

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

### <span data-ttu-id="a26d2-162">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a26d2-162">-Confirm</span></span>

<span data-ttu-id="a26d2-163">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a26d2-163">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a26d2-164">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a26d2-164">-WhatIf</span></span>

<span data-ttu-id="a26d2-165">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="a26d2-165">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a26d2-166">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="a26d2-166">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a26d2-167">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a26d2-167">CommonParameters</span></span>

<span data-ttu-id="a26d2-168">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a26d2-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a26d2-169">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a26d2-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a26d2-170">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a26d2-170">INPUTS</span></span>

### <span data-ttu-id="a26d2-171">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a26d2-171">None</span></span>

<span data-ttu-id="a26d2-172">Esse cmdlet não aceita nenhum objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="a26d2-172">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="a26d2-173">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a26d2-173">OUTPUTS</span></span>

### <span data-ttu-id="a26d2-174">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a26d2-174">None</span></span>

<span data-ttu-id="a26d2-175">Esse cmdlet não produz saídas.</span><span class="sxs-lookup"><span data-stu-id="a26d2-175">This cmdlet produces no outputs.</span></span>

## <span data-ttu-id="a26d2-176">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a26d2-176">NOTES</span></span>

## <span data-ttu-id="a26d2-177">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a26d2-177">RELATED LINKS</span></span>

[<span data-ttu-id="a26d2-178">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="a26d2-178">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="a26d2-179">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="a26d2-179">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="a26d2-180">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="a26d2-180">Set-CimInstance</span></span>](Set-CimInstance.md)

