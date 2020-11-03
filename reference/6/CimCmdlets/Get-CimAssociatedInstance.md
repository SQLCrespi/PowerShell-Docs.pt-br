---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimassociatedinstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimAssociatedInstance
ms.openlocfilehash: adf6c1ac6f6f9288233d530b7ea2101f4b7688e4
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194904"
---
# <span data-ttu-id="fcc48-103">Get-CimAssociatedInstance</span><span class="sxs-lookup"><span data-stu-id="fcc48-103">Get-CimAssociatedInstance</span></span>

## <span data-ttu-id="fcc48-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fcc48-104">SYNOPSIS</span></span>
<span data-ttu-id="fcc48-105">Recupera as instâncias CIM que estão conectadas a uma instância CIM específica por uma associação.</span><span class="sxs-lookup"><span data-stu-id="fcc48-105">Retrieves the CIM instances that are connected to a specific CIM instance by an association.</span></span>

## <span data-ttu-id="fcc48-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fcc48-106">SYNTAX</span></span>

### <span data-ttu-id="fcc48-107">ComputerSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="fcc48-107">ComputerSet (Default)</span></span>

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] [-ComputerName <String[]>] [-KeyOnly] [<CommonParameters>]
```

### <span data-ttu-id="fcc48-108">Sessionset</span><span class="sxs-lookup"><span data-stu-id="fcc48-108">SessionSet</span></span>

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] -CimSession <CimSession[]> [-KeyOnly] [<CommonParameters>]
```

## <span data-ttu-id="fcc48-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fcc48-109">DESCRIPTION</span></span>

<span data-ttu-id="fcc48-110">O `Get-CimAssociatedInstance` cmdlet recupera as instâncias de CIM conectadas a uma instância de CIM específica, chamada de instância de origem, por uma associação.</span><span class="sxs-lookup"><span data-stu-id="fcc48-110">The `Get-CimAssociatedInstance` cmdlet retrieves the CIM instances connected to a specific CIM instance, called the source instance, by an association.</span></span>

<span data-ttu-id="fcc48-111">Em uma associação, cada instância de CIM tem uma função nomeada e a mesma instância de CIM pode participar de uma associação em funções diferentes.</span><span class="sxs-lookup"><span data-stu-id="fcc48-111">In an association, each CIM instance has a named role and the same CIM instance can participate in an association in different roles.</span></span>

<span data-ttu-id="fcc48-112">Se o parâmetro InputObject não for especificado, o cmdlet funcionará de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="fcc48-112">If the InputObject parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="fcc48-113">Se nem o parâmetro **ComputerName** nem o parâmetro **CimSession** for especificado, esse cmdlet funcionará no Instrumentação de gerenciamento do Windows local (WMI) usando uma sessão Component Object Model (com).</span><span class="sxs-lookup"><span data-stu-id="fcc48-113">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="fcc48-114">Se o parâmetro **ComputerName** ou o parâmetro **CimSession** for especificado, esse cmdlet funcionará no servidor CIM especificado pelo parâmetro **ComputerName** ou pelo parâmetro **CimSession** .</span><span class="sxs-lookup"><span data-stu-id="fcc48-114">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

## <span data-ttu-id="fcc48-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fcc48-115">EXAMPLES</span></span>

### <span data-ttu-id="fcc48-116">Exemplo 1: obter todas as instâncias associadas de uma instância específica</span><span class="sxs-lookup"><span data-stu-id="fcc48-116">Example 1: Get all the associated instances of a specific instance</span></span>

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1]
```

<span data-ttu-id="fcc48-117">Esse conjunto de comandos recupera as instâncias da classe denominada Win32_LogicalDisk e armazena as informações em uma variável chamada `$disk` usando o `Get-CimInstance` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fcc48-117">This set of commands retrieves the instances of the class named Win32_LogicalDisk and stores the information in a variable named `$disk` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="fcc48-118">A primeira instância de disco lógico na variável é usada como o objeto de entrada para o `Get-CimAssociatedInstance` cmdlet obter todas as instâncias de CIM associadas da instância CIM especificada.</span><span class="sxs-lookup"><span data-stu-id="fcc48-118">The first logical disk instance in the variable is then used as the input object for the `Get-CimAssociatedInstance` cmdlet to get all the associated CIM instances of the specified CIM instance.</span></span>

### <span data-ttu-id="fcc48-119">Exemplo 2: obter todas as instâncias associadas de um tipo específico</span><span class="sxs-lookup"><span data-stu-id="fcc48-119">Example 2: Get all the associated instances of a specific type</span></span>

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1] -ResultClass Win32_DiskPartition
```

<span data-ttu-id="fcc48-120">Esse conjunto de comandos recupera todas as instâncias da classe **Win32_LogicalDisk** e as armazena em uma variável chamada `$disk` .</span><span class="sxs-lookup"><span data-stu-id="fcc48-120">This set of commands retrieves all the instances of the **Win32_LogicalDisk** class and stores them in a variable named `$disk`.</span></span> <span data-ttu-id="fcc48-121">A primeira instância de disco lógico na variável é usada como o objeto de entrada para o `Get-CimAssociatedInstance` cmdlet obter todas as instâncias associadas que estão associadas por meio da classe de associação especificada **Win32_DiskPartition** .</span><span class="sxs-lookup"><span data-stu-id="fcc48-121">The first logical disk instance in the variable is then used as the input object for the `Get-CimAssociatedInstance` cmdlet to get all the associated instances that are associated through the specified association class **Win32_DiskPartition** .</span></span>

### <span data-ttu-id="fcc48-122">Exemplo 3: obter todas as instâncias associadas por meio do qualificador de uma classe específica</span><span class="sxs-lookup"><span data-stu-id="fcc48-122">Example 3: Get all the associated instances through qualifier of a specific class</span></span>

```powershell
$s = Get-CimInstance -Query "Select * from Win32_Service where name like 'Winmgmt'"
Get-CimClass -ClassName *Service* -Qualifier "Association"
$c.CimClasName
```

```Output
Win32_LoadOrderGroupServiceDependencies
Win32_DependentService
Win32_SystemServices
Win32_LoadOrderGroupServiceMembers
Win32_ServiceSpecificationService
```

```powershell
Get-CimAssociatedInstance -InputObject $s -Association Win32_DependentService
```

<span data-ttu-id="fcc48-123">Esse conjunto de comandos recupera os serviços que dependem do serviço WMI e os armazena em uma variável chamada `$s` .</span><span class="sxs-lookup"><span data-stu-id="fcc48-123">This set of commands retrieves the services that depend on WMI service and stores them in a variable named `$s`.</span></span> <span data-ttu-id="fcc48-124">O nome da classe de associação para o **Win32_DependentService** é recuperado usando o `Get-CimClass` cmdlet especificando a **Associação** como o qualificador e, em seguida, é passado com $s ao `Get-CimAssociatedInstance` cmdlet para obter todas as instâncias associadas da classe de associação recuperada.</span><span class="sxs-lookup"><span data-stu-id="fcc48-124">The association class name for the **Win32_DependentService** is retrieved using the `Get-CimClass` cmdlet by specifying **Association** as the qualifier and is then passed with $s to the `Get-CimAssociatedInstance` cmdlet to get all the associated instances of the retrieved association class.</span></span>

## <span data-ttu-id="fcc48-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fcc48-125">PARAMETERS</span></span>

### <span data-ttu-id="fcc48-126">-Associação</span><span class="sxs-lookup"><span data-stu-id="fcc48-126">-Association</span></span>

<span data-ttu-id="fcc48-127">Especifica o nome da classe de associação.</span><span class="sxs-lookup"><span data-stu-id="fcc48-127">Specifies the name of the association class.</span></span> <span data-ttu-id="fcc48-128">Se você não especificar esse parâmetro, o cmdlet retornará todos os objetos de associação existentes de qualquer tipo.</span><span class="sxs-lookup"><span data-stu-id="fcc48-128">If you do not specify this parameter, the cmdlet returns all existing association objects of any type.</span></span>

<span data-ttu-id="fcc48-129">Por exemplo, se A classe A estiver associada à classe B por meio de duas associações, AB1 e AB2, esse parâmetro poderá ser usado para especificar o tipo de associação, AB1 ou AB2.</span><span class="sxs-lookup"><span data-stu-id="fcc48-129">For example, if class A is associated with class B through two associations, AB1 and AB2, then this parameter can be used to specify the type of association, either AB1 or AB2.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fcc48-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="fcc48-130">-CimSession</span></span>

<span data-ttu-id="fcc48-131">Executa o comando usando a sessão CIM especificada.</span><span class="sxs-lookup"><span data-stu-id="fcc48-131">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="fcc48-132">Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como `New-CimSession` ou `Get-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="fcc48-132">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as `New-CimSession` or `Get-CimSession`.</span></span> <span data-ttu-id="fcc48-133">Para obter mais informações, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="fcc48-133">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: SessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fcc48-134">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="fcc48-134">-ComputerName</span></span>

<span data-ttu-id="fcc48-135">Especifica o nome do computador no qual você deseja executar a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="fcc48-135">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="fcc48-136">Você pode especificar um nome de domínio totalmente qualificado (FQDN) ou um nome NetBIOS.</span><span class="sxs-lookup"><span data-stu-id="fcc48-136">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="fcc48-137">Se você especificar esse parâmetro, o cmdlet criará uma sessão temporária para o computador especificado usando o protocolo WsMan.</span><span class="sxs-lookup"><span data-stu-id="fcc48-137">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="fcc48-138">Se você não especificar esse parâmetro, o cmdlet executará a operação no computador local usando Component Object Model (COM).</span><span class="sxs-lookup"><span data-stu-id="fcc48-138">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="fcc48-139">Se várias operações estiverem sendo executadas no mesmo computador, a conexão usando uma sessão CIM fornecerá um melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="fcc48-139">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fcc48-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fcc48-140">-InputObject</span></span>

<span data-ttu-id="fcc48-141">Especifica a entrada para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fcc48-141">Specifies the input to this cmdlet.</span></span> <span data-ttu-id="fcc48-142">Você pode usar esse parâmetro ou é possível canalizar a entrada para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fcc48-142">You can use this parameter, or you can pipe the input to this cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fcc48-143">-Somente</span><span class="sxs-lookup"><span data-stu-id="fcc48-143">-KeyOnly</span></span>

<span data-ttu-id="fcc48-144">Retorna objetos com apenas as propriedades de chave populadas.</span><span class="sxs-lookup"><span data-stu-id="fcc48-144">Returns objects with only key properties populated.</span></span> <span data-ttu-id="fcc48-145">Isso reduz a quantidade de dados transferidos pela rede.</span><span class="sxs-lookup"><span data-stu-id="fcc48-145">This reduces the amount of data that is transferred over the network.</span></span>

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

### <span data-ttu-id="fcc48-146">-Namespace</span><span class="sxs-lookup"><span data-stu-id="fcc48-146">-Namespace</span></span>

<span data-ttu-id="fcc48-147">Especifica o namespace para a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="fcc48-147">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="fcc48-148">O namespace padrão é root/cimv2.</span><span class="sxs-lookup"><span data-stu-id="fcc48-148">The default namespace is root/cimv2.</span></span>

> [!NOTE]
> <span data-ttu-id="fcc48-149">Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.</span><span class="sxs-lookup"><span data-stu-id="fcc48-149">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fcc48-150">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="fcc48-150">-OperationTimeoutSec</span></span>

<span data-ttu-id="fcc48-151">Especifica a quantidade de tempo que o cmdlet aguarda uma resposta do computador.</span><span class="sxs-lookup"><span data-stu-id="fcc48-151">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="fcc48-152">Por padrão, o valor desse parâmetro é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.</span><span class="sxs-lookup"><span data-stu-id="fcc48-152">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="fcc48-153">Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão robusto de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis, pois a operação no servidor expirará antes que o cliente possa se reconectar.</span><span class="sxs-lookup"><span data-stu-id="fcc48-153">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fcc48-154">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="fcc48-154">-ResourceUri</span></span>

<span data-ttu-id="fcc48-155">Especifica o URI (Uniform Resource Identifier) do recurso da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="fcc48-155">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="fcc48-156">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="fcc48-156">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="fcc48-157">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="fcc48-157">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="fcc48-158">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fcc48-158">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="fcc48-159">Por padrão, se você não especificar esse parâmetro, o URI de recurso padrão do DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` será usado e o nome da classe será anexado a ele.</span><span class="sxs-lookup"><span data-stu-id="fcc48-159">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="fcc48-160">O **ResourceURI** só pode ser usado com sessões CIM criadas usando o protocolo WSMan ou ao especificar o parâmetro **ComputerName** , que cria uma sessão CIM usando WSMan.</span><span class="sxs-lookup"><span data-stu-id="fcc48-160">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="fcc48-161">Se você especificar esse parâmetro sem especificar o parâmetro **ComputerName** ou se especificar uma sessão CIM criada usando o protocolo DCOM, receberá um erro, pois o protocolo DCOM não oferece suporte ao parâmetro **ResourceURI** .</span><span class="sxs-lookup"><span data-stu-id="fcc48-161">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="fcc48-162">Se o parâmetro **ResourceURI** e o parâmetro **Filter** forem especificados, o parâmetro **Filter** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="fcc48-162">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fcc48-163">-ResultClassName</span><span class="sxs-lookup"><span data-stu-id="fcc48-163">-ResultClassName</span></span>

<span data-ttu-id="fcc48-164">Especifica o nome de classe das instâncias associadas.</span><span class="sxs-lookup"><span data-stu-id="fcc48-164">Specifies the class name of the associated instances.</span></span> <span data-ttu-id="fcc48-165">Uma instância CIM pode ser associada a uma ou mais instâncias CIM.</span><span class="sxs-lookup"><span data-stu-id="fcc48-165">A CIM instance can be associated with one or more CIM instances.</span></span> <span data-ttu-id="fcc48-166">Todas as instâncias de CIM associadas serão retornadas se você não especificar o nome da classe de resultado.</span><span class="sxs-lookup"><span data-stu-id="fcc48-166">All associated CIM instances are returned if you do not specify the result class name.</span></span>

<span data-ttu-id="fcc48-167">Por padrão, o valor desse parâmetro é NULL e todas as instâncias de CIM associadas são retornadas.</span><span class="sxs-lookup"><span data-stu-id="fcc48-167">By default, the value of this parameter is null, and all associated CIM instances are returned.</span></span>

<span data-ttu-id="fcc48-168">Você pode filtrar os resultados da Associação para corresponder a um nome de classe específico.</span><span class="sxs-lookup"><span data-stu-id="fcc48-168">You can filter the association results to match a specific class name.</span></span> <span data-ttu-id="fcc48-169">A filtragem ocorre no servidor.</span><span class="sxs-lookup"><span data-stu-id="fcc48-169">Filtering happens on the server.</span></span> <span data-ttu-id="fcc48-170">Se esse parâmetro não for especificado, o `Get-CIMAssociatedInstance` retornará todas as associações existentes.</span><span class="sxs-lookup"><span data-stu-id="fcc48-170">If this parameter is not specified, `Get-CIMAssociatedInstance` returns all existing associations.</span></span> <span data-ttu-id="fcc48-171">Por exemplo, se A classe A estiver associada às classes B, C e D, esse parâmetro poderá ser usado para restringir a saída a um tipo específico (B, C ou D).</span><span class="sxs-lookup"><span data-stu-id="fcc48-171">For example, if class A is associated with classes B, C and D, then this parameter can be used to restrict the output to a specific type (B, C or D).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fcc48-172">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fcc48-172">CommonParameters</span></span>

<span data-ttu-id="fcc48-173">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fcc48-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fcc48-174">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fcc48-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fcc48-175">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fcc48-175">INPUTS</span></span>

### <span data-ttu-id="fcc48-176">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fcc48-176">None</span></span>

<span data-ttu-id="fcc48-177">Esse cmdlet não aceita nenhum objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="fcc48-177">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="fcc48-178">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fcc48-178">OUTPUTS</span></span>

### <span data-ttu-id="fcc48-179">System.Object</span><span class="sxs-lookup"><span data-stu-id="fcc48-179">System.Object</span></span>

<span data-ttu-id="fcc48-180">Esse cmdlet retorna um objeto.</span><span class="sxs-lookup"><span data-stu-id="fcc48-180">This cmdlet returns an object.</span></span>

## <span data-ttu-id="fcc48-181">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fcc48-181">NOTES</span></span>

## <span data-ttu-id="fcc48-182">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fcc48-182">RELATED LINKS</span></span>

[<span data-ttu-id="fcc48-183">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="fcc48-183">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="fcc48-184">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="fcc48-184">Get-CimInstance</span></span>](get-ciminstance.md)
