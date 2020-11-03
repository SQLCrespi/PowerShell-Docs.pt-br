---
description: Descreve a linguagem WQL, que pode ser usada para obter objetos WMI no Windows PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wql?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WQL
ms.openlocfilehash: c6fd523864d419fb400b7041e92ec8f0733724b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196131"
---
# <a name="about-wql"></a><span data-ttu-id="12cb2-104">Sobre o WQL</span><span class="sxs-lookup"><span data-stu-id="12cb2-104">About WQL</span></span>

## <a name="short-description"></a><span data-ttu-id="12cb2-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="12cb2-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="12cb2-106">Descreve a linguagem WQL, que pode ser usada para obter objetos WMI no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12cb2-106">Describes WMI Query Language (WQL), which can be used to get WMI objects in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="12cb2-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="12cb2-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="12cb2-108">WQL é a linguagem de consulta Instrumentação de Gerenciamento do Windows (WMI), que é a linguagem usada para obter informações do WMI.</span><span class="sxs-lookup"><span data-stu-id="12cb2-108">WQL is the Windows Management Instrumentation (WMI) query language, which is the language used to get information from WMI.</span></span>

<span data-ttu-id="12cb2-109">Não é necessário usar o WQL para executar uma consulta WMI no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12cb2-109">You are not required to use WQL to perform a WMI query in Windows PowerShell.</span></span>
<span data-ttu-id="12cb2-110">Em vez disso, você pode usar os parâmetros dos cmdlets Get-WmiObject ou Get-CimInstance.</span><span class="sxs-lookup"><span data-stu-id="12cb2-110">Instead, you can use the parameters of the Get-WmiObject or Get-CimInstance cmdlets.</span></span> <span data-ttu-id="12cb2-111">As consultas WQL são um pouco mais rápidas do que os comandos de Get-WmiObject padrão e o desempenho aprimorado é evidente quando os comandos são executados em centenas de sistemas.</span><span class="sxs-lookup"><span data-stu-id="12cb2-111">WQL queries are somewhat faster than standard Get-WmiObject commands and the improved performance is evident when the commands run on hundreds of systems.</span></span> <span data-ttu-id="12cb2-112">No entanto, certifique-se de que o tempo gasto para escrever uma consulta WQL bem-sucedida não supere a melhoria do desempenho.</span><span class="sxs-lookup"><span data-stu-id="12cb2-112">However, be sure that the time you spend to write a successful WQL query doesn't outweigh the performance improvement.</span></span>

<span data-ttu-id="12cb2-113">As instruções WQL básicas que você precisa usar WQL são selecionar, onde e de.</span><span class="sxs-lookup"><span data-stu-id="12cb2-113">The basic WQL statements you need to use WQL are Select, Where, and From.</span></span>

## <a name="when-to-use-wql"></a><span data-ttu-id="12cb2-114">QUANDO USAR WQL</span><span class="sxs-lookup"><span data-stu-id="12cb2-114">WHEN TO USE WQL</span></span>

<span data-ttu-id="12cb2-115">Ao trabalhar com o WMI e, especialmente com a WQL, não se esqueça de que você também está usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12cb2-115">When working with WMI, and especially with WQL, do not forget that you are also using Windows PowerShell.</span></span> <span data-ttu-id="12cb2-116">Geralmente, se uma consulta WQL não funcionar conforme o esperado, será mais fácil usar um comando padrão do Windows PowerShell do que Depurar a consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="12cb2-116">Often, if a WQL query does not work as expected, it's easier to use a standard Windows PowerShell command than to debug the WQL query.</span></span>

<span data-ttu-id="12cb2-117">A menos que você esteja retornando grandes quantidades de dados de sistemas remotos com largura de banda restrita, raramente é produtivo gastar horas tentando aperfeiçoar uma consulta WQL complicada e complicadas quando há um cmdlet do Windows perfeitamente aceitável que faz a mesma coisa, se for um pouco mais lento.</span><span class="sxs-lookup"><span data-stu-id="12cb2-117">Unless you are returning massive amounts of data from across bandwidth-constrained remote systems, it is rarely productive to spend hours trying to perfect a complicated and convoluted WQL query when there is a perfectly acceptable Windows cmdlet that does the same thing, if a bit more slowly.</span></span>

## <a name="using-the-select-statement"></a><span data-ttu-id="12cb2-118">USANDO A INSTRUÇÃO SELECT</span><span class="sxs-lookup"><span data-stu-id="12cb2-118">USING THE SELECT STATEMENT</span></span>

<span data-ttu-id="12cb2-119">Uma consulta WMI típica começa com uma instrução SELECT que obtém todas as propriedades ou propriedades específicas de uma classe WMI.</span><span class="sxs-lookup"><span data-stu-id="12cb2-119">A typical WMI query begins with a Select statement that gets all properties or particular properties of a WMI class.</span></span> <span data-ttu-id="12cb2-120">Para selecionar todas as propriedades de uma classe WMI, use um asterisco ( \* ).</span><span class="sxs-lookup"><span data-stu-id="12cb2-120">To select all properties of a WMI class, use an asterisk (\*).</span></span> <span data-ttu-id="12cb2-121">A palavra-chave from especifica a classe WMI.</span><span class="sxs-lookup"><span data-stu-id="12cb2-121">The From keyword specifies the WMI class.</span></span>

<span data-ttu-id="12cb2-122">Uma instrução SELECT tem o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="12cb2-122">A Select statement has the following format:</span></span>

```
Select <property> from <WMI-class>
```

<span data-ttu-id="12cb2-123">Por exemplo, a instrução SELECT a seguir seleciona todas as propriedades (\*) das instâncias da classe WMI Win32_Bios.</span><span class="sxs-lookup"><span data-stu-id="12cb2-123">For example, the following Select statement selects all properties (\*) from the instances of the Win32_Bios WMI class.</span></span>

```
Select * from Win32_Bios
```

<span data-ttu-id="12cb2-124">Para selecionar uma propriedade específica de uma classe WMI, coloque o nome da propriedade entre as palavras-chave SELECT e from.</span><span class="sxs-lookup"><span data-stu-id="12cb2-124">To select a particular property of a WMI class, place the property name between the Select and From keywords.</span></span>

<span data-ttu-id="12cb2-125">A consulta a seguir seleciona apenas o nome do BIOS da classe Win32_Bios WMI.</span><span class="sxs-lookup"><span data-stu-id="12cb2-125">The following query selects only the name of the BIOS from the Win32_Bios WMI class.</span></span> <span data-ttu-id="12cb2-126">O comando salva a consulta na variável $queryName.</span><span class="sxs-lookup"><span data-stu-id="12cb2-126">The command saves the query in the $queryName variable.</span></span>

```
Select Name from Win32_Bios
```

<span data-ttu-id="12cb2-127">Para selecionar mais de uma propriedade, use vírgulas para separar os nomes de propriedade.</span><span class="sxs-lookup"><span data-stu-id="12cb2-127">To select more than one property, use commas to separate the property names.</span></span>
<span data-ttu-id="12cb2-128">A consulta WMI a seguir seleciona o nome e a versão da classe Win32_Bios WMI.</span><span class="sxs-lookup"><span data-stu-id="12cb2-128">The following WMI query selects the name and the version of the Win32_Bios WMI class.</span></span> <span data-ttu-id="12cb2-129">O comando salva a consulta na variável $queryNameVersion.</span><span class="sxs-lookup"><span data-stu-id="12cb2-129">The command saves the query in the $queryNameVersion variable.</span></span>

```
Select name, version from Win32_Bios
```

## <a name="using-the-wql-query"></a><span data-ttu-id="12cb2-130">USANDO A CONSULTA WQL</span><span class="sxs-lookup"><span data-stu-id="12cb2-130">USING THE WQL QUERY</span></span>

<span data-ttu-id="12cb2-131">Há três maneiras de usar a consulta WQL no comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12cb2-131">There are three ways to use WQL query in Windows PowerShell command.</span></span>

- <span data-ttu-id="12cb2-132">Usar o cmdlet Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="12cb2-132">Use the Get-WmiObject cmdlet</span></span>
- <span data-ttu-id="12cb2-133">Usar o cmdlet Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="12cb2-133">Use the Get-CimInstance cmdlet</span></span>
- <span data-ttu-id="12cb2-134">Use o acelerador de tipo [WMISEARCHER].</span><span class="sxs-lookup"><span data-stu-id="12cb2-134">Use the [wmisearcher] type accelerator.</span></span>

## <a name="using-the-get-wmiobject-cmdlet"></a><span data-ttu-id="12cb2-135">USANDO O CMDLET GET-WMIOBJECT</span><span class="sxs-lookup"><span data-stu-id="12cb2-135">USING THE GET-WMIOBJECT CMDLET</span></span>

<span data-ttu-id="12cb2-136">A maneira mais básica de usar a consulta WQL é colocá-la entre aspas (como uma cadeia de caracteres) e, em seguida, usar a cadeia de caracteres de consulta como o valor do parâmetro de consulta do cmdlet Get-WmiObject, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="12cb2-136">The most basic way to use the WQL query is to enclose it in quotation marks (as a string) and then use the query string as the value of the Query parameter of the Get-WmiObject cmdlet, as shown in the following example.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="12cb2-137">Você também pode salvar a instrução WQL em uma variável e, em seguida, usar a variável como o valor do parâmetro de consulta, conforme mostrado no comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="12cb2-137">You can also save the WQL statement in a variable and then use the variable as the value of the Query parameter, as shown in the following command.</span></span>

```powershell
$query = "Select * from Win32_Bios"
Get-WmiObject -Query $query
```

<span data-ttu-id="12cb2-138">Você pode usar qualquer um dos formatos com qualquer instrução WQL.</span><span class="sxs-lookup"><span data-stu-id="12cb2-138">You can use either format with any WQL statement.</span></span> <span data-ttu-id="12cb2-139">O comando a seguir usa a consulta na variável $queryName para obter apenas as propriedades Name e Version do BIOS do sistema.</span><span class="sxs-lookup"><span data-stu-id="12cb2-139">The following command uses the query in the $queryName variable to get only the name and version properties of the system BIOS.</span></span>

```powershell
$queryNameVersion = "Select Name, Version from Win32_Bios"
Get-WmiObject -Query $queryNameVersion
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

<span data-ttu-id="12cb2-140">Lembre-se de que você pode usar os parâmetros do cmdlet Get-WmiObject para obter o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="12cb2-140">Remember that you can use the parameters of the Get-WmiObject cmdlet to get the same result.</span></span> <span data-ttu-id="12cb2-141">Por exemplo, o comando a seguir também obtém os valores das propriedades Name e Version de instâncias da classe WMI Win32_Bios.</span><span class="sxs-lookup"><span data-stu-id="12cb2-141">For example, the following command also gets the values of the Name and Version properties of instances of the Win32_Bios WMI class.</span></span>

```powershell
Get-WmiObject -Class Win32_Bios -Property Name, Version
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

## <a name="using-the-get-ciminstance-cmdlet"></a><span data-ttu-id="12cb2-142">USANDO O CMDLET GET-CIMINSTANCE</span><span class="sxs-lookup"><span data-stu-id="12cb2-142">USING THE GET-CIMINSTANCE CMDLET</span></span>

<span data-ttu-id="12cb2-143">A partir do Windows PowerShell 3,0, você pode usar o cmdlet Get-CimInstance para executar consultas WQL.</span><span class="sxs-lookup"><span data-stu-id="12cb2-143">Beginning in Windows PowerShell 3.0, you can use the Get-CimInstance cmdlet to run WQL queries.</span></span>

<span data-ttu-id="12cb2-144">Get-CimInstance Obtém instâncias de classes compatíveis com CIM, incluindo classes WMI.</span><span class="sxs-lookup"><span data-stu-id="12cb2-144">Get-CimInstance gets instances of CIM-compliant classes, including WMI classes.</span></span> <span data-ttu-id="12cb2-145">Os cmdlets do CIM, introduzidos no Windows PowerShell 3,0, executam as mesmas tarefas que os cmdlets do WMI.</span><span class="sxs-lookup"><span data-stu-id="12cb2-145">The CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="12cb2-146">Os cmdlets do CIM estão em conformidade com os padrões do WSMan (WS-Management) e com o padrão modelo CIM (CIM), que permite que os cmdlets usem as mesmas técnicas para gerenciar computadores Windows e computadores que executam outros sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="12cb2-146">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard, which enables the cmdlets to use the same techniques to manage Windows computers and computers that are running other operating systems.</span></span>

<span data-ttu-id="12cb2-147">O comando a seguir usa o cmdlet Get-CimInstance para executar uma consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="12cb2-147">The following command uses the Get-CimInstance cmdlet to run a WQL query.</span></span>

<span data-ttu-id="12cb2-148">Qualquer consulta WQL que possa ser usada com Get-WmiObject também pode ser usada com Get-CimInstance.</span><span class="sxs-lookup"><span data-stu-id="12cb2-148">Any WQL query that can be used with Get-WmiObject can also be used with Get-CimInstance.</span></span>

```powershell
Get-CimInstance -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="12cb2-149">Get-CimInstance retorna um objeto CimInstance, em vez de ManagementObject que Get-WmiObject retorna, mas os objetos são bastante semelhantes.</span><span class="sxs-lookup"><span data-stu-id="12cb2-149">Get-CimInstance returns a CimInstance object, instead of the ManagementObject that Get-WmiObject returns, but the objects are quite similar.</span></span>

```
(Get-CimInstance -Query "Select * from Win32_Bios").GetType().FullName
Microsoft.Management.Infrastructure.CimInstance
(Get-WmiObject -Query "Select * from Win32_Bios").GetType().FullName
System.Management.ManagementObject
```

## <a name="using-the-wmisearcher-type-accelerator"></a><span data-ttu-id="12cb2-150">USANDO o ACELERAdor de tipo [WMISEARCHER]</span><span class="sxs-lookup"><span data-stu-id="12cb2-150">USING THE [wmisearcher] TYPE ACCELERATOR</span></span>

<span data-ttu-id="12cb2-151">O acelerador de tipo [WMISEARCHER] cria um objeto ManagementObjectSearcher a partir de uma cadeia de caracteres de instrução WQL.</span><span class="sxs-lookup"><span data-stu-id="12cb2-151">The [wmisearcher] type accelerator creates a ManagementObjectSearcher object from a WQL statement string.</span></span> <span data-ttu-id="12cb2-152">O objeto ManagementObjectSearcher tem muitas propriedades e métodos, mas o método mais básico é o método Get, que invoca a consulta WMI especificada e retorna os objetos resultantes.</span><span class="sxs-lookup"><span data-stu-id="12cb2-152">The ManagementObjectSearcher object has many properties and methods, but the most basic method is the Get method, which invokes the specified WMI query and returns the resulting objects.</span></span>

<span data-ttu-id="12cb2-153">Usando o [WMISEARCHER], você obterá acesso fácil à classe de .NET Framework do ManagementObjectSearcher.</span><span class="sxs-lookup"><span data-stu-id="12cb2-153">By using the [wmisearcher], you gain easy access to the ManagementObjectSearcher .NET Framework class.</span></span> <span data-ttu-id="12cb2-154">Isso permite consultar o WMI e configurar a maneira como a consulta é realizada.</span><span class="sxs-lookup"><span data-stu-id="12cb2-154">This lets you query WMI and to configure the way the query is conducted.</span></span>

<span data-ttu-id="12cb2-155">Para usar o acelerador de tipo [WMISEARCHER]:</span><span class="sxs-lookup"><span data-stu-id="12cb2-155">To use the [wmisearcher] type accelerator:</span></span>

1. <span data-ttu-id="12cb2-156">Converta a cadeia de caracteres WQL em um objeto ManagementObjectSearcher.</span><span class="sxs-lookup"><span data-stu-id="12cb2-156">Cast the  WQL string into a ManagementObjectSearcher object.</span></span>
2. <span data-ttu-id="12cb2-157">Chame o método Get do objeto ManagementObjectSearcher.</span><span class="sxs-lookup"><span data-stu-id="12cb2-157">Call the Get method of the ManagementObjectSearcher object.</span></span>

<span data-ttu-id="12cb2-158">Por exemplo, o comando a seguir converte a consulta "selecionar tudo", salva o resultado na variável $bios e, em seguida, chama o método Get do objeto ManagementObjectSearcher na variável $bios.</span><span class="sxs-lookup"><span data-stu-id="12cb2-158">For example, the following command casts the "select all" query, saves the result in the $bios variable, and then calls the Get method of the ManagementObjectSearcher object in the $bios variable.</span></span>

```powershell
$bios = [wmisearcher]"Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="12cb2-159">Observação: somente as propriedades de objeto selecionadas são exibidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="12cb2-159">NOTE: Only selected object properties are displayed by default.</span></span> <span data-ttu-id="12cb2-160">Essas propriedades são definidas no arquivo XML Types.ps1.</span><span class="sxs-lookup"><span data-stu-id="12cb2-160">These properties are defined in the Types.ps1xml file.</span></span>

<span data-ttu-id="12cb2-161">Você pode usar o acelerador de tipo [WMISEARCHER] para converter a consulta ou a variável.</span><span class="sxs-lookup"><span data-stu-id="12cb2-161">You can use the [wmisearcher] type accelerator to cast the query or the variable.</span></span> <span data-ttu-id="12cb2-162">No exemplo a seguir, o acelerador de tipo [WMISEARCHER] é usado para converter a variável.</span><span class="sxs-lookup"><span data-stu-id="12cb2-162">In the following example, the [wmisearcher] type accelerator is used to cast the variable.</span></span> <span data-ttu-id="12cb2-163">O resultado é o mesmo.</span><span class="sxs-lookup"><span data-stu-id="12cb2-163">The result is the same.</span></span>

```powershell
[wmisearcher]$bios = "Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="12cb2-164">Quando você usa o acelerador de tipo [WMISEARCHER], ele altera a cadeia de caracteres de consulta em um objeto ManagementObjectSearcher, conforme mostrado nos comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="12cb2-164">When you use the [wmisearcher] type accelerator, it changes the query string into a ManagementObjectSearcher object, as shown in the following commands.</span></span>

```
$a = "Select * from Win32_Bios"
$a.GetType().FullName
System.String

$a = [wmisearcher]"Select * from Win32_Bios"
$a.GetType().FullName
System.Management.ManagementObjectSearcher
```

<span data-ttu-id="12cb2-165">Esse formato de comando funciona em qualquer consulta.</span><span class="sxs-lookup"><span data-stu-id="12cb2-165">This command format works on any query.</span></span> <span data-ttu-id="12cb2-166">O comando a seguir obtém o valor da propriedade Name da classe WMI Win32_Bios.</span><span class="sxs-lookup"><span data-stu-id="12cb2-166">The following command gets the value of the Name property of the Win32_Bios WMI class.</span></span>

```powershell
$biosname = [wmisearcher]"Select Name from Win32_Bios"
$biosname.Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

<span data-ttu-id="12cb2-167">Você pode executar essa operação em um único comando, embora o comando seja um pouco mais difícil de interpretar.</span><span class="sxs-lookup"><span data-stu-id="12cb2-167">You can perform this operation in a single command, although the command is a bit more difficult to interpret.</span></span>

<span data-ttu-id="12cb2-168">Nesse formato, você usa o acelerador de tipo [WMISEARCHER] para converter a cadeia de caracteres de consulta WQL em um ManagementObjectSearcher e, em seguida, chamar o método Get no objeto, tudo em um único comando.</span><span class="sxs-lookup"><span data-stu-id="12cb2-168">In this format, you use the [wmisearcher] type accelerator to cast the WQL query string to a ManagementObjectSearcher, and then call the Get method on the object -- all in a single command.</span></span> <span data-ttu-id="12cb2-169">Os parênteses () que envolvem a cadeia de caracteres convertida direcionam o Windows PowerShell para converter a cadeia de caracteres antes de chamar o método.</span><span class="sxs-lookup"><span data-stu-id="12cb2-169">The parentheses () that enclose the casted string direct Windows PowerShell to cast the string before calling the method.</span></span>

```powershell
([wmisearcher]"Select name from Win32_Bios").Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

## <a name="using-the-basic-wql-where-statement"></a><span data-ttu-id="12cb2-170">USANDO A INSTRUÇÃO WHERE BÁSICA DO WQL</span><span class="sxs-lookup"><span data-stu-id="12cb2-170">USING THE BASIC WQL WHERE STATEMENT</span></span>

<span data-ttu-id="12cb2-171">Uma instrução WHERE estabelece condições para os dados retornados por uma instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="12cb2-171">A Where statement establishes conditions for the data that a Select statement returns.</span></span>

<span data-ttu-id="12cb2-172">A instrução WHERE tem o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="12cb2-172">The Where statement has the following format:</span></span>

```
where <property> <operator> <value>
```

<span data-ttu-id="12cb2-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="12cb2-173">For example:</span></span>

```
where Name = 'Notepad.exe'
```

<span data-ttu-id="12cb2-174">A instrução WHERE é usada com a instrução SELECT, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="12cb2-174">The Where statement is used with the Select statement, as shown in the following example.</span></span>

```
Select * from Win32_Process where Name = 'Notepad.exe'
```

<span data-ttu-id="12cb2-175">Ao usar a instrução WHERE, o nome da propriedade e o valor devem ser precisos.</span><span class="sxs-lookup"><span data-stu-id="12cb2-175">When using the Where statement, the property name and value must be accurate.</span></span>

<span data-ttu-id="12cb2-176">Por exemplo, o comando a seguir obtém os processos do bloco de notas no computador local.</span><span class="sxs-lookup"><span data-stu-id="12cb2-176">For example, the following command gets the Notepad processes on the local computer.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad.exe'"
```

<span data-ttu-id="12cb2-177">No entanto, o comando a seguir falhará, porque o nome do processo inclui a extensão de nome de arquivo ". exe".</span><span class="sxs-lookup"><span data-stu-id="12cb2-177">However, the following command fails, because the process name includes the ".exe" file name extension.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad'"
```

## <a name="where-statement-comparison-operators"></a><span data-ttu-id="12cb2-178">OPERADORES DE COMPARAÇÃO DE INSTRUÇÕES WHERE</span><span class="sxs-lookup"><span data-stu-id="12cb2-178">WHERE STATEMENT COMPARISON OPERATORS</span></span>

<span data-ttu-id="12cb2-179">Os operadores a seguir são válidos em uma instrução WHERE do WQL.</span><span class="sxs-lookup"><span data-stu-id="12cb2-179">The following operators are valid in a WQL Where statement.</span></span>

```
Operator    Description
-----------------------
=           Equal
!=          Not equal
<>          Not equal
<           Less than
>           Greater than
<=          Less than or equal
>=          Greater than or equal
LIKE        Wildcard match
IS          Evaluates null
ISNOT       Evaluates not null
ISA         Evaluates a member of a WMI class
```

<span data-ttu-id="12cb2-180">Há outros operadores, mas são aqueles usados para fazer comparações.</span><span class="sxs-lookup"><span data-stu-id="12cb2-180">There are other operators, but these are the ones used for making comparisons.</span></span>

<span data-ttu-id="12cb2-181">Por exemplo, a consulta a seguir seleciona o nome e as propriedades de prioridade dos processos na classe Win32_Process em que a prioridade do processo é maior ou igual a 11.</span><span class="sxs-lookup"><span data-stu-id="12cb2-181">For example, the following query selects the Name and Priority properties from processes in the Win32_Process class where the process priority is greater than or equal to 11.</span></span> <span data-ttu-id="12cb2-182">O cmdlet Get-WmiObject executa a consulta.</span><span class="sxs-lookup"><span data-stu-id="12cb2-182">The Get-WmiObject cmdlet runs the query.</span></span>

```powershell
$highPriority = "Select Name, Priority from Win32_Process " +
  "where Priority >= 11"
Get-WmiObject -Query $highPriority
```

## <a name="using-the-wql-operators-in-the-filter-parameter"></a><span data-ttu-id="12cb2-183">USANDO OS OPERADORES WQL NO PARÂMETRO FILTER</span><span class="sxs-lookup"><span data-stu-id="12cb2-183">USING THE WQL OPERATORS IN THE FILTER PARAMETER</span></span>

<span data-ttu-id="12cb2-184">Os operadores WQL também podem ser usados no valor do parâmetro de filtro dos cmdlets Get-WmiObject ou Get-CimInstance, bem como no valor dos parâmetros de consulta desses cmdlets.</span><span class="sxs-lookup"><span data-stu-id="12cb2-184">The WQL operators can also be used in the value of the Filter parameter of the Get-WmiObject or Get-CimInstance cmdlets, as well as in the value of the Query parameters of these cmdlets.</span></span>

<span data-ttu-id="12cb2-185">Por exemplo, o comando a seguir obtém as propriedades Name e ProcessID dos últimos cinco processos que têm valores de ProcessID maiores que 1004.</span><span class="sxs-lookup"><span data-stu-id="12cb2-185">For example, the following command gets the Name and ProcessID properties of the last five processes that have ProcessID values greater than 1004.</span></span> <span data-ttu-id="12cb2-186">O comando usa o parâmetro Filter para especificar a condição ProcessID.</span><span class="sxs-lookup"><span data-stu-id="12cb2-186">The command uses the Filter parameter to specify the ProcessID condition.</span></span>

```powershell
Get-WmiObject -Class Win32_Process `
-Property Name, ProcessID -Filter "ProcessID >= 1004" |
Sort ProcessID | Select Name, ProcessID -Last 5
```

```output
Name                                 ProcessID
----                                 ---------
SROSVC.exe                                4220
WINWORD.EXE                               4664
TscHelp.exe                               4744
SnagIt32.exe                              4748
WmiPrvSE.exe                              5056
```

## <a name="using-the-like-operator"></a><span data-ttu-id="12cb2-187">USANDO O OPERADOR LIKE</span><span class="sxs-lookup"><span data-stu-id="12cb2-187">USING THE LIKE OPERATOR</span></span>

<span data-ttu-id="12cb2-188">O operador Like permite que você use caracteres curinga para filtrar os resultados de uma consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="12cb2-188">The Like operator lets you use wildcard characters to filter the results of a WQL query.</span></span>

```
Like Operator  Description
--------------------------------------------------
[]             Character in a range [a-f] or a set
               of characters [abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

^              Character not in a range [^a-f] or
               not in a set [^abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

%              A string of zero or more characters

_              One character.
(underscore)   NOTE: To use a literal underscore
               in a query string, enclose it in
               square brackets [_].
```

<span data-ttu-id="12cb2-189">Quando o operador Like é usado sem nenhum caractere curinga ou operador de intervalo, ele se comporta como o operador de igualdade (=) e retorna objetos somente quando eles são uma correspondência exata para o padrão.</span><span class="sxs-lookup"><span data-stu-id="12cb2-189">When the Like operator is used without any wildcard characters or range operators, it behaves like the equality operator (=) and returns objects only when they are an exact match for the pattern.</span></span>

<span data-ttu-id="12cb2-190">Você pode combinar a operação de intervalo com o caractere curinga percentual para criar filtros simples, mas poderosos.</span><span class="sxs-lookup"><span data-stu-id="12cb2-190">You can combine the range operation with the percent wildcard character to create simple, yet powerful filters.</span></span>

### <a name="like-operator-examples"></a><span data-ttu-id="12cb2-191">EXEMPLOS DE OPERADOR LIKE</span><span class="sxs-lookup"><span data-stu-id="12cb2-191">LIKE OPERATOR EXAMPLES</span></span>

#### <a name="example-1-range"></a><span data-ttu-id="12cb2-192">EXEMPLO 1: [ \<range> ]</span><span class="sxs-lookup"><span data-stu-id="12cb2-192">EXAMPLE 1: [\<range>]</span></span>

<span data-ttu-id="12cb2-193">Os comandos a seguir iniciam o bloco de notas e, em seguida, pesquisam uma instância da classe Win32_Process que tem um nome que começa com uma letra entre "H" e "N" (não diferencia maiúsculas de minúsculas).</span><span class="sxs-lookup"><span data-stu-id="12cb2-193">The following commands start Notepad and then search for an instance of the Win32_Process class that has a name that starts with a letter between "H" and "N" (case-insensitive).</span></span>

<span data-ttu-id="12cb2-194">A consulta deve retornar qualquer processo de Hotpad.exe por meio de Notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="12cb2-194">The query should return any process from Hotpad.exe through Notepad.exe.</span></span>

```powershell
Notepad   # Starts Notepad
$query = "Select * from win32_Process where Name LIKE '[H-N]otepad.exe'"
Get-WmiObject -Query $query | Select Name, ProcessID
```

```output
Name                                ProcessID
----                                ---------
notepad.exe                              1740
```

#### <a name="example-2-range-and-"></a><span data-ttu-id="12cb2-195">EXEMPLO 2: [ \<range> ] e%</span><span class="sxs-lookup"><span data-stu-id="12cb2-195">EXAMPLE 2: [\<range>] and %</span></span>

<span data-ttu-id="12cb2-196">Os comandos a seguir selecionam todos os processos que têm um nome que começa com uma letra entre A e P (não diferencia maiúsculas de minúsculas) seguidos por zero ou mais letras em qualquer combinação.</span><span class="sxs-lookup"><span data-stu-id="12cb2-196">The following commands select all process that have a name that begins with a letter between A and P (case-insensitive) followed by zero or more letters in any combination.</span></span>

<span data-ttu-id="12cb2-197">O cmdlet Get-WmiObject executa a consulta, o cmdlet Select-Object Obtém as propriedades Name e ProcessID, e o cmdlet Sort-Object classifica os resultados em ordem alfabética por nome.</span><span class="sxs-lookup"><span data-stu-id="12cb2-197">The Get-WmiObject cmdlet runs the query, the Select-Object cmdlet gets the Name and ProcessID properties, and the Sort-Object cmdlet sorts the results in alphabetical order by name.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE '[A-P]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-3-not-in-range-"></a><span data-ttu-id="12cb2-198">EXEMPLO 3: não está no intervalo (^)</span><span class="sxs-lookup"><span data-stu-id="12cb2-198">EXAMPLE 3: Not in Range (^)</span></span>

<span data-ttu-id="12cb2-199">O comando a seguir obtém os processos cujos nomes não começam com nenhuma das seguintes letras: A, S, W, P, R, C, U, N</span><span class="sxs-lookup"><span data-stu-id="12cb2-199">The following command gets processes whose names do not begin with any of the following letters: A, S, W, P, R, C, U, N</span></span>

<span data-ttu-id="12cb2-200">e seguido zero ou mais letras.</span><span class="sxs-lookup"><span data-stu-id="12cb2-200">and followed zero or more letters.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE '[^ASWPRCUN]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-4-any-characters----or-none-"></a><span data-ttu-id="12cb2-201">EXEMPLO 4: quaisquer caracteres-ou nenhum (%)</span><span class="sxs-lookup"><span data-stu-id="12cb2-201">EXAMPLE 4: Any characters -- or none (%)</span></span>

<span data-ttu-id="12cb2-202">Os comandos a seguir obtêm processos que têm nomes que começam com "Calc".</span><span class="sxs-lookup"><span data-stu-id="12cb2-202">The following commands get processes that have names that begin with "calc".</span></span>
<span data-ttu-id="12cb2-203">O símbolo% em WQL é equivalente ao símbolo de asterisco ( \* ) em expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="12cb2-203">The % symbol in WQL is equivalent to the asterisk (\*) symbol in regular expressions.</span></span>

```powershell
$query = "Select * from win32_Process where Name LIKE 'calc%'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                               ProcessID
----                               ---------
calc.exe                                4424
```

#### <a name="example-5-one-character-_"></a><span data-ttu-id="12cb2-204">EXEMPLO 5: um caractere (_)</span><span class="sxs-lookup"><span data-stu-id="12cb2-204">EXAMPLE 5: One character (_)</span></span>

<span data-ttu-id="12cb2-205">Os comandos a seguir obtêm processos com nomes que têm o seguinte padrão, "c_lc.exe", em que o caractere de sublinhado representa um caractere.</span><span class="sxs-lookup"><span data-stu-id="12cb2-205">The following commands get processes that have names that have the following pattern, "c_lc.exe" where the underscore character represents any one character.</span></span> <span data-ttu-id="12cb2-206">Esse padrão corresponde a qualquer nome de calc.exe por meio de czlc.exe, ou c9lc.exe, mas não corresponde a nomes nos quais "c" e "l" são separados por mais de um caractere.</span><span class="sxs-lookup"><span data-stu-id="12cb2-206">This pattern matches any name from calc.exe through czlc.exe, or c9lc.exe, but does not match names in which the "c" and "l" are separated by more than one character.</span></span>

```powershell
$query = "Select * from Win32_Process where Name LIKE 'c_lc.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                                 ProcessID
----                                 ---------
calc.exe                                  4424
```

#### <a name="example-6-exact-match"></a><span data-ttu-id="12cb2-207">EXEMPLO 6: correspondência exata</span><span class="sxs-lookup"><span data-stu-id="12cb2-207">EXAMPLE 6: Exact match</span></span>

<span data-ttu-id="12cb2-208">Os comandos a seguir obtêm processos chamados WLIDSVC.exe.</span><span class="sxs-lookup"><span data-stu-id="12cb2-208">The following commands get processes named WLIDSVC.exe.</span></span> <span data-ttu-id="12cb2-209">Embora a consulta use a palavra-chave like, ela requer uma correspondência exata, pois o valor não inclui nenhum caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="12cb2-209">Even though the query uses the Like keyword, it requires an exact match, because the value does not include any wildcard characters.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE 'WLIDSVC.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```powershell

```output
Name                                 ProcessID
----                                 ---------
WLIDSVC.exe                                84
```

## <a name="using-the-or-operator"></a><span data-ttu-id="12cb2-210">USANDO O OPERADOR OR</span><span class="sxs-lookup"><span data-stu-id="12cb2-210">USING THE OR OPERATOR</span></span>

<span data-ttu-id="12cb2-211">Para especificar várias condições independentes, use a palavra-chave ou.</span><span class="sxs-lookup"><span data-stu-id="12cb2-211">To specify multiple independent conditions, use the Or keyword.</span></span> <span data-ttu-id="12cb2-212">A palavra-chave ou é exibida na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="12cb2-212">The Or keyword appears in the Where clause.</span></span> <span data-ttu-id="12cb2-213">Ele executa uma operação inclusiva ou em duas (ou mais) condições e retorna itens que atendem a qualquer uma das condições.</span><span class="sxs-lookup"><span data-stu-id="12cb2-213">It performs an inclusive OR operation on two (or more) conditions and returns items that meet any of the conditions.</span></span>

<span data-ttu-id="12cb2-214">O operador or tem o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="12cb2-214">The Or operator has the following format:</span></span>

```
Where <property> <operator> <value> or <property> <operator> <value> ...
```

<span data-ttu-id="12cb2-215">Por exemplo, os comandos a seguir obtêm todas as instâncias da classe Win32_Process WMI, mas as retornarão somente se o nome do processo for winword.exe ou excel.exe.</span><span class="sxs-lookup"><span data-stu-id="12cb2-215">For example, the following commands get all instances of the Win32_Process WMI class but returns them only if the process name is winword.exe or excel.exe.</span></span>

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe'"
Get-WmiObject -Query $q
```

<span data-ttu-id="12cb2-216">A instrução or pode ser usada com mais de duas condições.</span><span class="sxs-lookup"><span data-stu-id="12cb2-216">The Or statement can be used with more than two conditions.</span></span> <span data-ttu-id="12cb2-217">Na consulta a seguir, a instrução or Obtém Winword.exe, Excel.exe ou Powershell.exe.</span><span class="sxs-lookup"><span data-stu-id="12cb2-217">In the following query, the Or statement gets Winword.exe, Excel.exe, or Powershell.exe.</span></span>

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe' or Name='powershell.exe'"
```

## <a name="using-the-and-operator"></a><span data-ttu-id="12cb2-218">USANDO O OPERADOR AND</span><span class="sxs-lookup"><span data-stu-id="12cb2-218">USING THE AND OPERATOR</span></span>

<span data-ttu-id="12cb2-219">Para especificar várias condições relacionadas, use a palavra-chave and.</span><span class="sxs-lookup"><span data-stu-id="12cb2-219">To specify multiple related conditions, use the And keyword.</span></span> <span data-ttu-id="12cb2-220">A palavra-chave and é exibida na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="12cb2-220">The And keyword appears in the Where clause.</span></span> <span data-ttu-id="12cb2-221">Ele retorna os itens que atendem a todas as condições.</span><span class="sxs-lookup"><span data-stu-id="12cb2-221">It returns items that meet all of the conditions.</span></span>

<span data-ttu-id="12cb2-222">O operador and tem o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="12cb2-222">The And operator has the following format:</span></span>

```
Where <property> <operator> <value> and <property> <operator> <value> ...
```

<span data-ttu-id="12cb2-223">Por exemplo, os comandos a seguir obtêm processos que têm um nome de "Winword.exe" e a ID de processo de 6512.</span><span class="sxs-lookup"><span data-stu-id="12cb2-223">For example, the following commands get processes that have a name of "Winword.exe" and the process ID of 6512.</span></span>

<span data-ttu-id="12cb2-224">Observe que os comandos usam o cmdlet Get-CimInstance.</span><span class="sxs-lookup"><span data-stu-id="12cb2-224">Note that the commands use the Get-CimInstance cmdlet.</span></span>

```powershell
$q = "Select * from Win32_Process where Name = 'winword.exe' " +
  "and ProcessID =6512"
Get-CimInstance -Query $q
```

```output
ProcessId   Name             HandleCount      WorkingSetSize   VirtualSize
---------   ----             -----------      --------------   -----------
# 6512      WINWORD.EXE      768              117170176        633028608
```

<span data-ttu-id="12cb2-225">Todos os operadores, incluindo os operadores like, são válidos com os operadores or e e.</span><span class="sxs-lookup"><span data-stu-id="12cb2-225">All operators, including the Like operators are valid with the Or and And operators.</span></span> <span data-ttu-id="12cb2-226">Além disso, você pode combinar os operadores or e and em uma única consulta com parênteses que informam ao Windows PowerShell quais cláusulas processar primeiro.</span><span class="sxs-lookup"><span data-stu-id="12cb2-226">And, you can combine the Or and And operators in a single query with parentheses that tell Windows PowerShell which clauses to process first.</span></span>

<span data-ttu-id="12cb2-227">Esse comando usa o caractere de continuação do Windows PowerShell (') dividir o comando em duas linhas.</span><span class="sxs-lookup"><span data-stu-id="12cb2-227">This command uses the Windows PowerShell continuation character (\`) divide the command into two lines.</span></span>

```powershell
$q = "Select * from Win32_Process `
where (Name = 'winword.exe' or Name = 'excel.exe') and HandleCount > 700"
Get-CimInstance -Query $q
```

```output
ProcessId    Name             HandleCount      WorkingSetSize   VirtualSize
---------    ----             -----------      --------------   -----------
     6512    WINWORD.EXE      797              117268480        634425344
     9610    EXCEL.EXE        727               38858752        323227648
```

## <a name="searching-for-null-values"></a><span data-ttu-id="12cb2-228">PESQUISANDO VALORES NULOS</span><span class="sxs-lookup"><span data-stu-id="12cb2-228">SEARCHING FOR NULL VALUES</span></span>

<span data-ttu-id="12cb2-229">Pesquisar valores nulos no WMI é desafiador, pois pode levar a resultados imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="12cb2-229">Searching for null values in WMI is challenging, because it can lead to unpredictable results.</span></span> <span data-ttu-id="12cb2-230">NULL não é zero e não é equivalente ou a uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="12cb2-230">Null is not zero and it is not equivalent or to an empty string.</span></span> <span data-ttu-id="12cb2-231">Algumas propriedades de classe WMI são inicializadas e outras não, portanto, uma pesquisa por NULL pode não funcionar para todas as propriedades.</span><span class="sxs-lookup"><span data-stu-id="12cb2-231">Some WMI class properties are initialized and others are not, so a search for null might not work for all properties.</span></span>

<span data-ttu-id="12cb2-232">Para pesquisar valores nulos, use o operador is com um valor de "NULL".</span><span class="sxs-lookup"><span data-stu-id="12cb2-232">To search for null values, use the Is operator with a value of "null".</span></span>

<span data-ttu-id="12cb2-233">Por exemplo, os comandos a seguir obtêm processos que têm um valor nulo para a propriedade IntallDate.</span><span class="sxs-lookup"><span data-stu-id="12cb2-233">For example, the following commands get processes that have a null value for the IntallDate property.</span></span> <span data-ttu-id="12cb2-234">Os comandos retornam muitos processos.</span><span class="sxs-lookup"><span data-stu-id="12cb2-234">The commands return many processes.</span></span>

```powershell
$q = "Select * from Win32_Process where InstallDate is null"
Get-WmiObject -Query $q
```

<span data-ttu-id="12cb2-235">Por outro lado, o comando a seguir obtém as contas de usuário que têm um valor nulo para a propriedade Description.</span><span class="sxs-lookup"><span data-stu-id="12cb2-235">In contrast, the following command, gets user accounts that have a null value for the Description property.</span></span> <span data-ttu-id="12cb2-236">Esse comando não retorna nenhuma conta de usuário, embora a maioria das contas de usuário não tenha nenhum valor para a propriedade Description.</span><span class="sxs-lookup"><span data-stu-id="12cb2-236">This command does not return any user accounts, even though most user accounts do not have any value for the Description property.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Description is null"
Get-WmiObject -Query $q
```

<span data-ttu-id="12cb2-237">Para localizar as contas de usuário que não têm valor para a propriedade Description, use o operador de igualdade para obter uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="12cb2-237">To find the user accounts that have no value for the Description property, use the equality operator to get an empty string.</span></span> <span data-ttu-id="12cb2-238">Para representar a cadeia de caracteres vazia, use duas aspas simples consecutivas.</span><span class="sxs-lookup"><span data-stu-id="12cb2-238">To represent the empty string, use two consecutive single quotation marks.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Description = '' "
```

## <a name="using-true-or-false"></a><span data-ttu-id="12cb2-239">USANDO TRUE OU FALSE</span><span class="sxs-lookup"><span data-stu-id="12cb2-239">USING TRUE OR FALSE</span></span>

<span data-ttu-id="12cb2-240">Para obter valores Boolianos nas propriedades de objetos WMI, use true e false.</span><span class="sxs-lookup"><span data-stu-id="12cb2-240">To get Boolean values in the properties of WMI objects, use True and False.</span></span>
<span data-ttu-id="12cb2-241">Eles não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="12cb2-241">They are not case sensitive.</span></span>

<span data-ttu-id="12cb2-242">A consulta WQL a seguir retorna apenas contas de usuário local de um computador ingressado no domínio.</span><span class="sxs-lookup"><span data-stu-id="12cb2-242">The following WQL query returns only local user accounts from a domain joined computer.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = True"
Get-CimInstance -Query $q
```

<span data-ttu-id="12cb2-243">Para localizar contas de domínio, use um valor de false, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="12cb2-243">To find domain accounts, use a value of False, as shown in the following example.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = False"
Get-CimInstance -Query $q
```

## <a name="using-the-escape-character"></a><span data-ttu-id="12cb2-244">USANDO O CARACTERE DE ESCAPE</span><span class="sxs-lookup"><span data-stu-id="12cb2-244">USING THE ESCAPE CHARACTER</span></span>

<span data-ttu-id="12cb2-245">O WQL usa a barra invertida ( \) como seu caractere de escape.</span><span class="sxs-lookup"><span data-stu-id="12cb2-245">WQL uses the backslash (\) as its escape character.</span></span> <span data-ttu-id="12cb2-246">Isso é diferente do Windows PowerShell, que usa o caractere de acento grave (').</span><span class="sxs-lookup"><span data-stu-id="12cb2-246">This is different from Windows PowerShell, which uses the backtick character (\`).</span></span>

<span data-ttu-id="12cb2-247">As aspas e os caracteres usados para aspas, geralmente precisam ser precedidos para que não sejam interpretados erroneamente.</span><span class="sxs-lookup"><span data-stu-id="12cb2-247">Quotation marks, and the characters used for quotation marks, often need to be escaped so that they are not misinterpreted.</span></span>

<span data-ttu-id="12cb2-248">Para localizar um usuário cujo nome inclui uma aspa simples, use uma barra invertida para escapar a aspa simples, conforme mostrado no comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="12cb2-248">To find a user whose name includes a single quotation mark, use a backslash to escape the single quotation mark, as shown in the following command.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Name = 'Tim O\'Brian'"
Get-CimInstance -Query $q
```

```output
Name             Caption          AccountType      SID              Domain
----             -------          -----------      ---              ------
Tim O'Brian      FABRIKAM\TimO    512              S-1-5-21-1457... FABRIKAM
```

<span data-ttu-id="12cb2-249">Em alguns casos, a barra invertida também precisa ter escape.</span><span class="sxs-lookup"><span data-stu-id="12cb2-249">In some case, the backslash also needs to be escaped.</span></span> <span data-ttu-id="12cb2-250">Por exemplo, os comandos a seguir geram um erro de consulta inválido devido à barra invertida no valor da legenda.</span><span class="sxs-lookup"><span data-stu-id="12cb2-250">For example, the following commands generate an Invalid Query error due to the backslash in the Caption value.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\TimO'"
Get-CimInstance -Query $q
```

```output
Get-CimInstance : Invalid query
At line:1 char:1
+ Get-CimInstance -Query $q
+ ~~~~~~~~~~~
  + CategoryInfo          : InvalidArgument: (:) [Get-CimInstance], CimExcep
  + FullyQualifiedErrorId : HRESULT 0x80041017,Microsoft.Management.Infrastr
```

<span data-ttu-id="12cb2-251">Para escapar a barra invertida, use um segundo caractere de barra invertida, conforme mostrado no comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="12cb2-251">To escape the backslash, use a second backslash character, as shown in the following command.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\\TimO'"
Get-CimInstance -Query $q
```

## <a name="see-also"></a><span data-ttu-id="12cb2-252">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="12cb2-252">SEE ALSO</span></span>

[<span data-ttu-id="12cb2-253">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="12cb2-253">about_Special_Characters</span></span>](about_Special_Characters.md)

[<span data-ttu-id="12cb2-254">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="12cb2-254">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="12cb2-255">about_WMI</span><span class="sxs-lookup"><span data-stu-id="12cb2-255">about_WMI</span></span>](about_WMI.md)

[<span data-ttu-id="12cb2-256">about_WMI_Cmdlets</span><span class="sxs-lookup"><span data-stu-id="12cb2-256">about_WMI_Cmdlets</span></span>](about_WMI_Cmdlets.md)
