---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimclass?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimClass
ms.openlocfilehash: 551ac39084ff7bf1729618d09cfa521cb6858242
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194348"
---
# <span data-ttu-id="7ea28-103">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="7ea28-103">Get-CimClass</span></span>

## <span data-ttu-id="7ea28-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7ea28-104">SYNOPSIS</span></span>
<span data-ttu-id="7ea28-105">Obtém uma lista de classes CIM em um namespace específico.</span><span class="sxs-lookup"><span data-stu-id="7ea28-105">Gets a list of CIM classes in a specific namespace.</span></span>

## <span data-ttu-id="7ea28-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7ea28-106">SYNTAX</span></span>

### <span data-ttu-id="7ea28-107">ComputerSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="7ea28-107">ComputerSet (Default)</span></span>

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

### <span data-ttu-id="7ea28-108">Sessionset</span><span class="sxs-lookup"><span data-stu-id="7ea28-108">SessionSet</span></span>

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

## <span data-ttu-id="7ea28-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7ea28-109">DESCRIPTION</span></span>

<span data-ttu-id="7ea28-110">O `Get-CimClass` cmdlet recupera uma lista de classes CIM em um namespace específico.</span><span class="sxs-lookup"><span data-stu-id="7ea28-110">The `Get-CimClass` cmdlet retrieves a list of CIM classes in a specific namespace.</span></span> <span data-ttu-id="7ea28-111">Se não houver nenhum nome de classe fornecido, o cmdlet retornará todas as classes no namespace.</span><span class="sxs-lookup"><span data-stu-id="7ea28-111">If there is no class name supplied, then the cmdlet returns all the classes in the namespace.</span></span> <span data-ttu-id="7ea28-112">Ao contrário de uma instância CIM, as classes CIM não contêm a sessão CIM ou o nome do computador do qual elas são recuperadas.</span><span class="sxs-lookup"><span data-stu-id="7ea28-112">Unlike a CIM instance, CIM classes do not contain the CIM session or computer name from which they are retrieved.</span></span>

## <span data-ttu-id="7ea28-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7ea28-113">EXAMPLES</span></span>

### <span data-ttu-id="7ea28-114">Exemplo 1: obter todas as definições de classe</span><span class="sxs-lookup"><span data-stu-id="7ea28-114">Example 1: Get all the class definitions</span></span>

<span data-ttu-id="7ea28-115">Este exemplo obtém todas as definições de classe sob o namespace **root/cimv2** .</span><span class="sxs-lookup"><span data-stu-id="7ea28-115">This example gets all the class definitions under the namespace **root/cimv2** .</span></span>

```powershell
Get-CimClass
```

### <span data-ttu-id="7ea28-116">Exemplo 2: obter as classes com um nome específico</span><span class="sxs-lookup"><span data-stu-id="7ea28-116">Example 2: Get the classes with a specific name</span></span>

<span data-ttu-id="7ea28-117">Este exemplo obtém as classes que contêm a palavra de **disco** em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="7ea28-117">This example gets the classes that contain the word **disk** in their names.</span></span>

```powershell
Get-CimClass -ClassName *disk*
```

### <span data-ttu-id="7ea28-118">Exemplo 3: obter as classes com um nome de método específico</span><span class="sxs-lookup"><span data-stu-id="7ea28-118">Example 3: Get the classes with a specific method name</span></span>

<span data-ttu-id="7ea28-119">Este exemplo obtém as classes que começam com o nome **Win32** e têm um nome de método que começa com **Term** .</span><span class="sxs-lookup"><span data-stu-id="7ea28-119">This example gets the classes that start with the name **Win32** and have a method name that starts with **Term** .</span></span>

```powershell
Get-CimClass -ClassName Win32* -MethodName Term*
```

### <span data-ttu-id="7ea28-120">Exemplo 4: obter as classes com um nome de propriedade específico</span><span class="sxs-lookup"><span data-stu-id="7ea28-120">Example 4: Get the classes with a specific property name</span></span>

<span data-ttu-id="7ea28-121">Este exemplo obtém as classes que começam com o nome **Win32** e têm uma propriedade chamada **Handle** .</span><span class="sxs-lookup"><span data-stu-id="7ea28-121">This example gets the classes that start with the name **Win32** and have a property named **Handle** .</span></span>

```powershell
Get-CimClass -ClassName Win32* -PropertyName Handle
```

### <span data-ttu-id="7ea28-122">Exemplo 5: obter as classes com um nome de qualificador específico</span><span class="sxs-lookup"><span data-stu-id="7ea28-122">Example 5: Get the classes with a specific qualifier name</span></span>

<span data-ttu-id="7ea28-123">Este exemplo obtém as classes que iniciam com o nome **Win32** , contêm a palavra **disco** em seus nomes e têm a **Associação** de qualificador especificada.</span><span class="sxs-lookup"><span data-stu-id="7ea28-123">This example gets the classes that start with the name **Win32** , contain the word **Disk** in their names and have the specified qualifier **Association** .</span></span>

```powershell
Get-CimClass -ClassName Win32*Disk* -QualifierName Association
```

### <span data-ttu-id="7ea28-124">Exemplo 6: obter as definições de classe de um namespace específico</span><span class="sxs-lookup"><span data-stu-id="7ea28-124">Example 6: Get the class definitions from a specific namespace</span></span>

<span data-ttu-id="7ea28-125">Este exemplo obtém as definições de classe que contêm a palavra **net** em seus nomes a partir da **raiz/standardCimv2** do namespace especificado.</span><span class="sxs-lookup"><span data-stu-id="7ea28-125">This example gets the class definitions that contain the word **Net** in their names from the specified namespace **root/standardCimv2** .</span></span>

```powershell
Get-CimClass -Namespace root/standardCimv2 -ClassName *Net*
```

### <span data-ttu-id="7ea28-126">Exemplo 7: obter as definições de classe de um servidor remoto</span><span class="sxs-lookup"><span data-stu-id="7ea28-126">Example 7: Get the class definitions from a remote server</span></span>

<span data-ttu-id="7ea28-127">Este exemplo obtém as definições de classe que contêm o **disco** do Word em seus nomes dos servidores remotos especificados **Server01** e **Server02** .</span><span class="sxs-lookup"><span data-stu-id="7ea28-127">This example gets the class definitions that contain the word **disk** in their names from the specified remote servers **Server01** and **Server02** .</span></span>

```powershell
Get-CimClass -ClassName *disk* -ComputerName Server01, Server02
```

### <span data-ttu-id="7ea28-128">Exemplo 8: obter as classes usando uma sessão CIM</span><span class="sxs-lookup"><span data-stu-id="7ea28-128">Example 8: Get the classes by using a CIM session</span></span>

```powershell
$s = New-CimSession -ComputerName Server01, Server02
Get-CimClass -ClassName *disk* -CimSession $s
```

<span data-ttu-id="7ea28-129">Esse conjunto de comandos cria uma sessão com vários computadores e o armazena em uma variável `$s` usando o `New-CimSession` cmdlet e, em seguida, obtém as classes usando o `Get-CimClass` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7ea28-129">This set of commands creates a session with multiple computers and stores it into a variable `$s` using the `New-CimSession` cmdlet, and then gets the classes using the `Get-CimClass` cmdlet.</span></span>

## <span data-ttu-id="7ea28-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7ea28-130">PARAMETERS</span></span>

### <span data-ttu-id="7ea28-131">-CimSession</span><span class="sxs-lookup"><span data-stu-id="7ea28-131">-CimSession</span></span>

<span data-ttu-id="7ea28-132">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="7ea28-132">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="7ea28-133">Insira um nome de computador ou um objeto de sessão, como a saída de `New-CimSession` um `Get-CimSession` cmdlet ou.</span><span class="sxs-lookup"><span data-stu-id="7ea28-133">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span> <span data-ttu-id="7ea28-134">O padrão é a sessão atual do computador local.</span><span class="sxs-lookup"><span data-stu-id="7ea28-134">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="7ea28-135">-ClassName</span><span class="sxs-lookup"><span data-stu-id="7ea28-135">-ClassName</span></span>

<span data-ttu-id="7ea28-136">Especifica o nome da classe CIM para a qual executar a operação.</span><span class="sxs-lookup"><span data-stu-id="7ea28-136">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="7ea28-137">Você pode usar o preenchimento com Tab para procurar a lista de classes, porque o PowerShell Obtém uma lista de classes do servidor WMI local para fornecer uma lista de nomes de classe.</span><span class="sxs-lookup"><span data-stu-id="7ea28-137">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="7ea28-138">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="7ea28-138">-ComputerName</span></span>

<span data-ttu-id="7ea28-139">Especifica o computador no qual você deseja executar a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="7ea28-139">Specifies the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="7ea28-140">Você pode especificar um nome de domínio totalmente qualificado (FQDN) um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="7ea28-140">You can specify a fully qualified domain name (FQDN) a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="7ea28-141">Se você especificar esse parâmetro, o cmdlet criará uma sessão temporária para o computador especificado usando o protocolo WsMan.</span><span class="sxs-lookup"><span data-stu-id="7ea28-141">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="7ea28-142">Se você não especificar esse parâmetro, o cmdlet executará a operação no computador local usando Component Object Model (COM).</span><span class="sxs-lookup"><span data-stu-id="7ea28-142">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="7ea28-143">Se várias operações estiverem sendo executadas no mesmo computador, o uso de uma sessão CIM fornecerá um melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="7ea28-143">If multiple operations are being performed on the same computer, using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7ea28-144">-MethodName</span><span class="sxs-lookup"><span data-stu-id="7ea28-144">-MethodName</span></span>

<span data-ttu-id="7ea28-145">Localiza as classes que têm um método correspondente a esse nome.</span><span class="sxs-lookup"><span data-stu-id="7ea28-145">Finds the classes that have a method matching this name.</span></span> <span data-ttu-id="7ea28-146">Você pode usar caracteres curinga com esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7ea28-146">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="7ea28-147">-Namespace</span><span class="sxs-lookup"><span data-stu-id="7ea28-147">-Namespace</span></span>

<span data-ttu-id="7ea28-148">Especifica o namespace para a operação CIM.</span><span class="sxs-lookup"><span data-stu-id="7ea28-148">Specifies the namespace for CIM operation.</span></span> <span data-ttu-id="7ea28-149">O namespace padrão é **root/cimv2** .</span><span class="sxs-lookup"><span data-stu-id="7ea28-149">The default namespace is **root/cimv2** .</span></span> <span data-ttu-id="7ea28-150">Você pode usar o preenchimento com Tab para navegar na lista de namespaces, pois o PowerShell Obtém uma lista de namespaces do servidor WMI local para fornecer a lista de namespaces.</span><span class="sxs-lookup"><span data-stu-id="7ea28-150">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

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

### <span data-ttu-id="7ea28-151">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="7ea28-151">-OperationTimeoutSec</span></span>

<span data-ttu-id="7ea28-152">Especifica a quantidade de tempo que o cmdlet aguarda uma resposta do computador.</span><span class="sxs-lookup"><span data-stu-id="7ea28-152">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="7ea28-153">Por padrão, o valor desse parâmetro é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.</span><span class="sxs-lookup"><span data-stu-id="7ea28-153">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="7ea28-154">Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão robusto de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis, pois a operação no servidor expirará antes que o cliente possa se reconectar.</span><span class="sxs-lookup"><span data-stu-id="7ea28-154">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="7ea28-155">-PropertyName</span><span class="sxs-lookup"><span data-stu-id="7ea28-155">-PropertyName</span></span>

<span data-ttu-id="7ea28-156">Localiza as classes que têm uma propriedade correspondente a esse nome.</span><span class="sxs-lookup"><span data-stu-id="7ea28-156">Finds the classes which have a property matching this name.</span></span> <span data-ttu-id="7ea28-157">Você pode usar caracteres curinga com esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7ea28-157">You can use wildcard characters with this parameter.</span></span>

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

### <span data-ttu-id="7ea28-158">-Qualifiername</span><span class="sxs-lookup"><span data-stu-id="7ea28-158">-QualifierName</span></span>

<span data-ttu-id="7ea28-159">Filtra as classes por nome de qualificador de nível de classe.</span><span class="sxs-lookup"><span data-stu-id="7ea28-159">Filters the classes by class level qualifier name.</span></span> <span data-ttu-id="7ea28-160">Você pode usar caracteres curinga com esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7ea28-160">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="7ea28-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7ea28-161">CommonParameters</span></span>

<span data-ttu-id="7ea28-162">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7ea28-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7ea28-163">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7ea28-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7ea28-164">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7ea28-164">INPUTS</span></span>

### <span data-ttu-id="7ea28-165">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7ea28-165">None</span></span>

<span data-ttu-id="7ea28-166">Esse cmdlet não aceita nenhum objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="7ea28-166">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="7ea28-167">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7ea28-167">OUTPUTS</span></span>

### <span data-ttu-id="7ea28-168">Microsoft. Management. Infrastructure. CimClass</span><span class="sxs-lookup"><span data-stu-id="7ea28-168">Microsoft.Management.Infrastructure.CimClass</span></span>

<span data-ttu-id="7ea28-169">Esse cmdlet retorna um objeto de classe CIM.</span><span class="sxs-lookup"><span data-stu-id="7ea28-169">This cmdlet returns a CIM class object.</span></span>

## <span data-ttu-id="7ea28-170">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7ea28-170">NOTES</span></span>

## <span data-ttu-id="7ea28-171">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7ea28-171">RELATED LINKS</span></span>

[<span data-ttu-id="7ea28-172">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="7ea28-172">New-CimSession</span></span>](New-CimSession.md)
