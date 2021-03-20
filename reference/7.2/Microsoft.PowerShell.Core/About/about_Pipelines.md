---
description: Combinando comandos em pipelines no PowerShell
Locale: en-US
ms.date: 03/18/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pipelines?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pipelines
ms.openlocfilehash: 6e3f15682caeecba6fa10166e1def7cc3d4a9eed
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104726733"
---
# <a name="about-pipelines"></a><span data-ttu-id="09feb-103">Sobre pipelines</span><span class="sxs-lookup"><span data-stu-id="09feb-103">About Pipelines</span></span>

## <a name="short-description"></a><span data-ttu-id="09feb-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="09feb-104">Short description</span></span>

<span data-ttu-id="09feb-105">Combinando comandos em pipelines no PowerShell</span><span class="sxs-lookup"><span data-stu-id="09feb-105">Combining commands into pipelines in the PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="09feb-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="09feb-106">Long description</span></span>

<span data-ttu-id="09feb-107">Um pipeline é uma série de comandos conectados por operadores de pipeline ( `|` ) (ASCII 124).</span><span class="sxs-lookup"><span data-stu-id="09feb-107">A pipeline is a series of commands connected by pipeline operators (`|`) (ASCII 124).</span></span> <span data-ttu-id="09feb-108">Cada operador de pipeline envia os resultados do comando anterior para o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="09feb-108">Each pipeline operator sends the results of the preceding command to the next command.</span></span>

<span data-ttu-id="09feb-109">A saída do primeiro comando pode ser enviada para processamento como entrada para o segundo comando.</span><span class="sxs-lookup"><span data-stu-id="09feb-109">The output of the first command can be sent for processing as input to the second command.</span></span> <span data-ttu-id="09feb-110">E essa saída pode ser enviada para outro comando.</span><span class="sxs-lookup"><span data-stu-id="09feb-110">And that output can be sent to yet another command.</span></span> <span data-ttu-id="09feb-111">O resultado é uma cadeia de comandos complexa ou um _pipeline_ composto por uma série de comandos simples.</span><span class="sxs-lookup"><span data-stu-id="09feb-111">The result is a complex command chain or _pipeline_ that is composed of a series of simple commands.</span></span>

<span data-ttu-id="09feb-112">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="09feb-112">For example,</span></span>

```powershell
Command-1 | Command-2 | Command-3
```

<span data-ttu-id="09feb-113">Neste exemplo, os objetos que `Command-1` são emitidos são enviados para `Command-2` .</span><span class="sxs-lookup"><span data-stu-id="09feb-113">In this example, the objects that `Command-1` emits are sent to `Command-2`.</span></span>
<span data-ttu-id="09feb-114">`Command-2` processa os objetos e os envia para o `Command-3` .</span><span class="sxs-lookup"><span data-stu-id="09feb-114">`Command-2` processes the objects and sends them to `Command-3`.</span></span> <span data-ttu-id="09feb-115">`Command-3` processa os objetos e os envia por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-115">`Command-3` processes the objects and send them down the pipeline.</span></span> <span data-ttu-id="09feb-116">Como não há mais comandos no pipeline, os resultados são exibidos no console.</span><span class="sxs-lookup"><span data-stu-id="09feb-116">Because there are no more commands in the pipeline, the results are displayed at the console.</span></span>

<span data-ttu-id="09feb-117">Em um pipeline, os comandos são processados na ordem da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="09feb-117">In a pipeline, the commands are processed in order from left to right.</span></span> <span data-ttu-id="09feb-118">O processamento é tratado como uma única operação e a saída é exibida à medida que é gerada.</span><span class="sxs-lookup"><span data-stu-id="09feb-118">The processing is handled as a single operation and output is displayed as it's generated.</span></span>

<span data-ttu-id="09feb-119">Veja um exemplo simples.</span><span class="sxs-lookup"><span data-stu-id="09feb-119">Here is a simple example.</span></span> <span data-ttu-id="09feb-120">O comando a seguir obtém o processo do bloco de notas e o interrompe.</span><span class="sxs-lookup"><span data-stu-id="09feb-120">The following command gets the Notepad process and then stops it.</span></span>

<span data-ttu-id="09feb-121">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="09feb-121">For example,</span></span>

```powershell
Get-Process notepad | Stop-Process
```

<span data-ttu-id="09feb-122">O primeiro comando usa o `Get-Process` cmdlet para obter um objeto que representa o processo do bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="09feb-122">The first command uses the `Get-Process` cmdlet to get an object representing the Notepad process.</span></span> <span data-ttu-id="09feb-123">Ele usa um operador de pipeline ( `|` ) para enviar o objeto de processo para o `Stop-Process` cmdlet, o que interrompe o processo do bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="09feb-123">It uses a pipeline operator (`|`) to send the process object to the `Stop-Process` cmdlet, which stops the Notepad process.</span></span> <span data-ttu-id="09feb-124">Observe que o `Stop-Process` comando não tem um parâmetro **Name** ou **ID** para especificar o processo, pois o processo especificado é enviado por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-124">Notice that the `Stop-Process` command doesn't have a **Name** or **ID** parameter to specify the process, because the specified process is submitted through the pipeline.</span></span>

<span data-ttu-id="09feb-125">Este exemplo de pipeline Obtém os arquivos de texto no diretório atual, seleciona apenas os arquivos com mais de 10.000 bytes, classifica-os por comprimento e exibe o nome e o comprimento de cada arquivo em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="09feb-125">This pipeline example gets the text files in the current directory, selects only the files that are more than 10,000 bytes long, sorts them by length, and displays the name and length of each file in a table.</span></span>

```powershell
Get-ChildItem -Path *.txt |
  Where-Object {$_.length -gt 10000} |
    Sort-Object -Property length |
      Format-Table -Property name, length
```

<span data-ttu-id="09feb-126">Esse pipeline consiste em quatro comandos na ordem especificada.</span><span class="sxs-lookup"><span data-stu-id="09feb-126">This pipeline consists of four commands in the specified order.</span></span> <span data-ttu-id="09feb-127">A ilustração a seguir mostra a saída de cada comando conforme passado para o próximo comando no pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-127">The following illustration shows the output from each command as it's passed to the next command in the pipeline.</span></span>

```
Get-ChildItem -Path *.txt
| (FileInfo objects for *.txt)
V
Where-Object {$_.length -gt 10000}
| (FileInfo objects for *.txt)
| (      Length > 10000      )
V
Sort-Object -Property Length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
V
Format-Table -Property name, length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
| (   Formatted in a table   )
V

Name                       Length
----                       ------
tmp1.txt                    82920
tmp2.txt                   114000
tmp3.txt                   114000
```

## <a name="using-pipelines"></a><span data-ttu-id="09feb-128">Usando pipelines</span><span class="sxs-lookup"><span data-stu-id="09feb-128">Using pipelines</span></span>

<span data-ttu-id="09feb-129">A maioria dos cmdlets do PowerShell foi projetada para dar suporte a pipelines.</span><span class="sxs-lookup"><span data-stu-id="09feb-129">Most PowerShell cmdlets are designed to support pipelines.</span></span> <span data-ttu-id="09feb-130">Na maioria dos casos, você pode _canalizar_ os resultados de um cmdlet **Get** para outro cmdlet do mesmo substantivo.</span><span class="sxs-lookup"><span data-stu-id="09feb-130">In most cases, you can _pipe_ the results of a **Get** cmdlet to another cmdlet of the same noun.</span></span>
<span data-ttu-id="09feb-131">Por exemplo, você pode canalizar a saída do `Get-Service` cmdlet para os `Start-Service` `Stop-Service` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="09feb-131">For example, you can pipe the output of the `Get-Service` cmdlet to the `Start-Service` or `Stop-Service` cmdlets.</span></span>

<span data-ttu-id="09feb-132">Este pipeline de exemplo inicia o serviço WMI no computador:</span><span class="sxs-lookup"><span data-stu-id="09feb-132">This example pipeline starts the WMI service on the computer:</span></span>

```powershell
Get-Service wmi | Start-Service
```

<span data-ttu-id="09feb-133">Para outro exemplo, você pode canalizar a saída de `Get-Item` ou `Get-ChildItem` dentro do provedor de registro do PowerShell para o `New-ItemProperty` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09feb-133">For another example, you can pipe the output of `Get-Item` or `Get-ChildItem` within the PowerShell registry provider to the `New-ItemProperty` cmdlet.</span></span> <span data-ttu-id="09feb-134">Este exemplo adiciona uma nova entrada de registro, **NoOfEmployees**, com um valor de **8124**, à chave do registro **MyCompany** .</span><span class="sxs-lookup"><span data-stu-id="09feb-134">This example adds a new registry entry, **NoOfEmployees**, with a value of **8124**, to the **MyCompany** registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany |
  New-ItemProperty -Name NoOfEmployees -Value 8124
```

<span data-ttu-id="09feb-135">Muitos dos cmdlets do utilitário, como `Get-Member` ,, `Where-Object` , `Sort-Object` `Group-Object` e `Measure-Object` são usados quase exclusivamente em pipelines.</span><span class="sxs-lookup"><span data-stu-id="09feb-135">Many of the utility cmdlets, such as `Get-Member`, `Where-Object`, `Sort-Object`, `Group-Object`, and `Measure-Object` are used almost exclusively in pipelines.</span></span> <span data-ttu-id="09feb-136">É possível canalizar qualquer tipo de objeto para esses cmdlets.</span><span class="sxs-lookup"><span data-stu-id="09feb-136">You can pipe any object type to these cmdlets.</span></span> <span data-ttu-id="09feb-137">Este exemplo mostra como classificar todos os processos no computador pelo número de identificadores abertos em cada processo.</span><span class="sxs-lookup"><span data-stu-id="09feb-137">This example shows how to sort all the processes on the computer by the number of open handles in each process.</span></span>

```powershell
Get-Process | Sort-Object -Property handles
```

<span data-ttu-id="09feb-138">Você pode canalizar objetos para os cmdlets de formatação, exportação e saída, como `Format-List` ,,, `Format-Table` `Export-Clixml` `Export-CSV` e `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="09feb-138">You can pipe objects to the formatting, export, and output cmdlets, such as `Format-List`, `Format-Table`, `Export-Clixml`, `Export-CSV`, and `Out-File`.</span></span>

<span data-ttu-id="09feb-139">Este exemplo mostra como usar o `Format-List` cmdlet para exibir uma lista de propriedades para um objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="09feb-139">This example shows how to use the `Format-List` cmdlet to display a list of properties for a process object.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="09feb-140">Você também pode canalizar a saída de comandos nativos para cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09feb-140">You can also pipe the output of native commands to PowerShell cmdlets.</span></span> <span data-ttu-id="09feb-141">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="09feb-141">For example:</span></span>

```powershell
PS> ipconfig.exe | Select-String -Pattern 'IPv4'

   IPv4 Address. . . . . . . . . . . : 172.24.80.1
   IPv4 Address. . . . . . . . . . . : 192.168.1.45
   IPv4 Address. . . . . . . . . . . : 100.64.108.37
```

> [!IMPORTANT]
> <span data-ttu-id="09feb-142">Os fluxos de **êxito** e de **erro** são semelhantes aos fluxos stdin e stderr de outros shells.</span><span class="sxs-lookup"><span data-stu-id="09feb-142">The **Success** and **Error** streams are similar to the stdin and stderr streams of other shells.</span></span> <span data-ttu-id="09feb-143">No entanto, stdin não está conectado ao pipeline do PowerShell para entrada.</span><span class="sxs-lookup"><span data-stu-id="09feb-143">However, stdin is not connected to the PowerShell pipeline for input.</span></span> <span data-ttu-id="09feb-144">Para obter mais informações, consulte [about_Redirection](about_Redirection.md).</span><span class="sxs-lookup"><span data-stu-id="09feb-144">For more information, see [about_Redirection](about_Redirection.md).</span></span>

<span data-ttu-id="09feb-145">Com um pouco de prática, você descobrirá que a combinação de comandos simples em pipelines poupa tempo e digitação e torna o script mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="09feb-145">With a bit of practice, you'll find that combining simple commands into pipelines saves time and typing, and makes your scripting more efficient.</span></span>

## <a name="how-pipelines-work"></a><span data-ttu-id="09feb-146">Como funcionam os pipelines</span><span class="sxs-lookup"><span data-stu-id="09feb-146">How pipelines work</span></span>

<span data-ttu-id="09feb-147">Esta seção explica como os objetos de entrada são associados a parâmetros de cmdlet e processados durante a execução do pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-147">This section explains how input objects are bound to cmdlet parameters and processed during pipeline execution.</span></span>

### <a name="accepts-pipeline-input"></a><span data-ttu-id="09feb-148">Aceita entrada de pipeline</span><span class="sxs-lookup"><span data-stu-id="09feb-148">Accepts pipeline input</span></span>

<span data-ttu-id="09feb-149">Para dar suporte ao pipeline, o cmdlet receptor deve ter um parâmetro que aceita entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-149">To support pipelining, the receiving cmdlet must have a parameter that accepts pipeline input.</span></span> <span data-ttu-id="09feb-150">Use o `Get-Help` comando com as opções **Full** ou **Parameter** para determinar quais parâmetros de um cmdlet aceitam entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-150">Use the `Get-Help` command with the **Full** or **Parameter** options to determine which parameters of a cmdlet accept pipeline input.</span></span>

<span data-ttu-id="09feb-151">Por exemplo, para determinar qual dos parâmetros do `Start-Service` cmdlet aceita entrada de pipeline, digite:</span><span class="sxs-lookup"><span data-stu-id="09feb-151">For example, to determine which of the parameters of the `Start-Service` cmdlet accepts pipeline input, type:</span></span>

```powershell
Get-Help Start-Service -Full
```

<span data-ttu-id="09feb-152">ou</span><span class="sxs-lookup"><span data-stu-id="09feb-152">or</span></span>

```powershell
Get-Help Start-Service -Parameter *
```

<span data-ttu-id="09feb-153">A ajuda para o `Start-Service` cmdlet mostra que apenas os parâmetros **InputObject** e **Name** aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-153">The help for the `Start-Service` cmdlet shows that only the **InputObject** and **Name** parameters accept pipeline input.</span></span>

```Output
-InputObject <ServiceController[]>
Specifies ServiceController objects representing the services to be started.
Enter a variable that contains the objects, or type a command or expression
that gets the objects.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByValue)
Accept wildcard characters?  false

-Name <String[]>
Specifies the service names for the service to be started.

The parameter name is optional. You can use Name or its alias, ServiceName,
or you can omit the parameter name.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByPropertyName, ByValue)
Accept wildcard characters?  false
```

<span data-ttu-id="09feb-154">Quando você envia objetos por meio do pipeline para o `Start-Service` , o PowerShell tenta associar os objetos aos parâmetros **InputObject** e **Name** .</span><span class="sxs-lookup"><span data-stu-id="09feb-154">When you send objects through the pipeline to `Start-Service`, PowerShell attempts to associate the objects with the **InputObject** and **Name** parameters.</span></span>

### <a name="methods-of-accepting-pipeline-input"></a><span data-ttu-id="09feb-155">Métodos de aceitação de entrada de pipeline</span><span class="sxs-lookup"><span data-stu-id="09feb-155">Methods of accepting pipeline input</span></span>

<span data-ttu-id="09feb-156">Os parâmetros de cmdlets podem aceitar a entrada de pipeline em uma das duas maneiras diferentes:</span><span class="sxs-lookup"><span data-stu-id="09feb-156">Cmdlets parameters can accept pipeline input in one of two different ways:</span></span>

- <span data-ttu-id="09feb-157">**ByValue**: o parâmetro aceita valores que correspondem ao tipo .net esperado ou que podem ser convertidos nesse tipo.</span><span class="sxs-lookup"><span data-stu-id="09feb-157">**ByValue**: The parameter accepts values that match the expected .NET type or that can be converted to that type.</span></span>

  <span data-ttu-id="09feb-158">Por exemplo, o parâmetro **Name** de `Start-Service` aceita entrada de pipeline por valor.</span><span class="sxs-lookup"><span data-stu-id="09feb-158">For example, the **Name** parameter of `Start-Service` accepts pipeline input by value.</span></span> <span data-ttu-id="09feb-159">Ele pode aceitar objetos String ou objetos que podem ser convertidos em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="09feb-159">It can accept string objects or objects that can be converted to strings.</span></span>

- <span data-ttu-id="09feb-160">**ByPropertyName**: o parâmetro aceita a entrada somente quando o objeto de entrada tem uma propriedade de mesmo nome que o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="09feb-160">**ByPropertyName**: The parameter accepts input only when the input object has a property of the same name as the parameter.</span></span>

  <span data-ttu-id="09feb-161">Por exemplo, o parâmetro Name de `Start-Service` pode aceitar objetos que têm uma propriedade **Name** .</span><span class="sxs-lookup"><span data-stu-id="09feb-161">For example, the Name parameter of `Start-Service` can accept objects that have a **Name** property.</span></span> <span data-ttu-id="09feb-162">Para listar as propriedades de um objeto, redirecione-o para `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="09feb-162">To list the properties of an object, pipe it to `Get-Member`.</span></span>

<span data-ttu-id="09feb-163">Alguns parâmetros podem aceitar objetos pelo valor ou nome da propriedade, facilitando a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-163">Some parameters can accept objects by both value or property name, making it easier to take input from the pipeline.</span></span>

### <a name="parameter-binding"></a><span data-ttu-id="09feb-164">Associação de parâmetro</span><span class="sxs-lookup"><span data-stu-id="09feb-164">Parameter binding</span></span>

<span data-ttu-id="09feb-165">Quando você canaliza objetos de um comando para outro, o PowerShell tenta associar os objetos de pipe com um parâmetro do cmdlet de recebimento.</span><span class="sxs-lookup"><span data-stu-id="09feb-165">When you pipe objects from one command to another command, PowerShell attempts to associate the piped objects with a parameter of the receiving cmdlet.</span></span>

<span data-ttu-id="09feb-166">O componente de associação de parâmetro do PowerShell associa os objetos de entrada a parâmetros de cmdlet de acordo com os seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="09feb-166">PowerShell's parameter binding component associates the input objects with cmdlet parameters according to the following criteria:</span></span>

- <span data-ttu-id="09feb-167">O parâmetro deve aceitar a entrada de um pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-167">The parameter must accept input from a pipeline.</span></span>
- <span data-ttu-id="09feb-168">O parâmetro deve aceitar o tipo de objeto que está sendo enviado ou um tipo que pode ser convertido para o tipo esperado.</span><span class="sxs-lookup"><span data-stu-id="09feb-168">The parameter must accept the type of object being sent or a type that can be converted to the expected type.</span></span>
- <span data-ttu-id="09feb-169">O parâmetro não foi usado no comando.</span><span class="sxs-lookup"><span data-stu-id="09feb-169">The parameter wasn't used in the command.</span></span>

<span data-ttu-id="09feb-170">Por exemplo, o `Start-Service` cmdlet tem muitos parâmetros, mas apenas dois deles, **Name** e **InputObject** aceitam entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-170">For example, the `Start-Service` cmdlet has many parameters, but only two of them, **Name** and **InputObject** accept pipeline input.</span></span> <span data-ttu-id="09feb-171">O parâmetro **Name** usa cadeias de caracteres e o parâmetro **InputObject** usa objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="09feb-171">The **Name** parameter takes strings and the **InputObject** parameter takes service objects.</span></span> <span data-ttu-id="09feb-172">Portanto, é possível redirecionar cadeias de caracteres, objetos de serviço e objetos com propriedades que podem ser convertidas em objetos de cadeia ou de serviço.</span><span class="sxs-lookup"><span data-stu-id="09feb-172">Therefore, you can pipe strings, service objects, and objects with properties that can be converted to string or service objects.</span></span>

<span data-ttu-id="09feb-173">O PowerShell gerencia a associação de parâmetro com a maior eficiência possível.</span><span class="sxs-lookup"><span data-stu-id="09feb-173">PowerShell manages parameter binding as efficiently as possible.</span></span> <span data-ttu-id="09feb-174">Você não pode sugerir ou forçar o PowerShell a se associar a um parâmetro específico.</span><span class="sxs-lookup"><span data-stu-id="09feb-174">You can't suggest or force the PowerShell to bind to a specific parameter.</span></span> <span data-ttu-id="09feb-175">O comando falhará se o PowerShell não puder associar os objetos canalizados.</span><span class="sxs-lookup"><span data-stu-id="09feb-175">The command fails if PowerShell can't bind the piped objects.</span></span>

<span data-ttu-id="09feb-176">Para obter mais informações sobre como solucionar erros de associação, consulte [investigando erros de pipeline](#investigating-pipeline-errors) mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="09feb-176">For more information about troubleshooting binding errors, see [Investigating Pipeline Errors](#investigating-pipeline-errors) later in this article.</span></span>

### <a name="one-at-a-time-processing"></a><span data-ttu-id="09feb-177">Processamento One-at-time</span><span class="sxs-lookup"><span data-stu-id="09feb-177">One-at-a-time processing</span></span>

<span data-ttu-id="09feb-178">Os objetos de tubulação a um comando são muito parecidos com o uso de um parâmetro do comando para enviar os objetos.</span><span class="sxs-lookup"><span data-stu-id="09feb-178">Piping objects to a command is much like using a parameter of the command to submit the objects.</span></span> <span data-ttu-id="09feb-179">Vejamos um exemplo de pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-179">Let's look at a pipeline example.</span></span> <span data-ttu-id="09feb-180">Neste exemplo, usamos um pipeline para exibir uma tabela de objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="09feb-180">In this example, we use a pipeline to display a table of service objects.</span></span>

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

<span data-ttu-id="09feb-181">Funcionalmente, isso é como usar o parâmetro **InputObject** de `Format-Table` para enviar a coleção de objetos.</span><span class="sxs-lookup"><span data-stu-id="09feb-181">Functionally, this is like using the **InputObject** parameter of `Format-Table` to submit the object collection.</span></span>

<span data-ttu-id="09feb-182">Por exemplo, podemos salvar a coleção de serviços em uma variável que é passada usando o parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="09feb-182">For example, we can save the collection of services to a variable that is passed using the **InputObject** parameter.</span></span>

```powershell
$services = Get-Service
Format-Table -InputObject $services -Property Name, DependentServices
```

<span data-ttu-id="09feb-183">Ou podemos inserir o comando no parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="09feb-183">Or we can embed the command in the **InputObject** parameter.</span></span>

```powershell
Format-Table -InputObject (Get-Service) -Property Name, DependentServices
```

<span data-ttu-id="09feb-184">No entanto, há uma diferença importante.</span><span class="sxs-lookup"><span data-stu-id="09feb-184">However, there's an important difference.</span></span> <span data-ttu-id="09feb-185">Quando você canaliza vários objetos para um comando, o PowerShell envia os objetos para o comando, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="09feb-185">When you pipe multiple objects to a command, PowerShell sends the objects to the command one at a time.</span></span> <span data-ttu-id="09feb-186">Quando você usa um parâmetro de comando, os objetos são enviados como um único objeto de matriz.</span><span class="sxs-lookup"><span data-stu-id="09feb-186">When you use a command parameter, the objects are sent as a single array object.</span></span> <span data-ttu-id="09feb-187">Essa diferença secundária tem consequências significativas.</span><span class="sxs-lookup"><span data-stu-id="09feb-187">This minor difference has significant consequences.</span></span>

<span data-ttu-id="09feb-188">Ao executar um pipeline, o PowerShell enumera automaticamente qualquer tipo que implemente a `IEnumerable` interface e envia os membros por meio do pipeline, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="09feb-188">When executing a pipeline, PowerShell automatically enumerates any type that implements the `IEnumerable` interface and sends the members through the pipeline one at a time.</span></span> <span data-ttu-id="09feb-189">A exceção é `[hashtable]` , que requer uma chamada para o `GetEnumerator()` método.</span><span class="sxs-lookup"><span data-stu-id="09feb-189">The exception is `[hashtable]`, which requires a call to the `GetEnumerator()` method.</span></span>

<span data-ttu-id="09feb-190">Nos exemplos a seguir, uma matriz e uma tabela de hash são canalizadas para o `Measure-Object` cmdlet para contar o número de objetos recebidos do pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-190">In the following examples, an array and a hashtable are piped to the `Measure-Object` cmdlet to count the number of objects received from the pipeline.</span></span> <span data-ttu-id="09feb-191">A matriz tem vários membros, e a tabela de hash tem vários pares de chave/valor.</span><span class="sxs-lookup"><span data-stu-id="09feb-191">The array has multiple members, and the hashtable has multiple key-value pairs.</span></span> <span data-ttu-id="09feb-192">Somente a matriz é enumerada uma de cada vez.</span><span class="sxs-lookup"><span data-stu-id="09feb-192">Only the array is enumerated one at a time.</span></span>

```powershell
@(1,2,3) | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

```powershell
@{"One"=1;"Two"=2} | Measure-Object
```

```Output
Count    : 1
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

<span data-ttu-id="09feb-193">Da mesma forma, se você canalizar vários objetos de processo do `Get-Process` cmdlet para o `Get-Member` cmdlet, o PowerShell enviará cada objeto de processo, um de cada vez, para `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="09feb-193">Similarly, if you pipe multiple process objects from the `Get-Process` cmdlet to the `Get-Member` cmdlet, PowerShell sends each process object, one at a time, to `Get-Member`.</span></span> <span data-ttu-id="09feb-194">`Get-Member` exibe a classe .NET (tipo) dos objetos de processo e suas propriedades e métodos.</span><span class="sxs-lookup"><span data-stu-id="09feb-194">`Get-Member` displays the .NET class (type) of the process objects, and their properties and methods.</span></span>

```powershell
Get-Process | Get-Member
```

```Output
TypeName: System.Diagnostics.Process

Name      MemberType     Definition
----      ----------     ----------
Handles   AliasProperty  Handles = Handlecount
Name      AliasProperty  Name = ProcessName
NPM       AliasProperty  NPM = NonpagedSystemMemorySize
...
```

> [!NOTE]
> <span data-ttu-id="09feb-195">`Get-Member` elimina duplicatas, portanto, se os objetos forem todos do mesmo tipo, ele exibirá apenas um tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="09feb-195">`Get-Member` eliminates duplicates, so if the objects are all of the same type, it only displays one object type.</span></span>

<span data-ttu-id="09feb-196">No entanto, se você usar o parâmetro **InputObject** de `Get-Member` , `Get-Member` o receberá uma matriz de objetos **System. Diagnostics. Process** como uma única unidade.</span><span class="sxs-lookup"><span data-stu-id="09feb-196">However, if you use the **InputObject** parameter of `Get-Member`, then `Get-Member` receives an array of **System.Diagnostics.Process** objects as a single unit.</span></span> <span data-ttu-id="09feb-197">Ele exibe as propriedades de uma matriz de objetos.</span><span class="sxs-lookup"><span data-stu-id="09feb-197">It displays the properties of an array of objects.</span></span> <span data-ttu-id="09feb-198">(Observe o símbolo da matriz ( `[]` ) após o nome do tipo **System. Object** .)</span><span class="sxs-lookup"><span data-stu-id="09feb-198">(Note the array symbol (`[]`) after the **System.Object** type name.)</span></span>

<span data-ttu-id="09feb-199">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="09feb-199">For example,</span></span>

```powershell
Get-Member -InputObject (Get-Process)
```

```Output
TypeName: System.Object[]

Name               MemberType    Definition
----               ----------    ----------
Count              AliasProperty Count = Length
Address            Method        System.Object& Address(Int32 )
Clone              Method        System.Object Clone()
...
```

<span data-ttu-id="09feb-200">Esse resultado pode não ser o que você pretendia.</span><span class="sxs-lookup"><span data-stu-id="09feb-200">This result might not be what you intended.</span></span> <span data-ttu-id="09feb-201">Mas, depois de entender, você pode usá-lo.</span><span class="sxs-lookup"><span data-stu-id="09feb-201">But after you understand it, you can use it.</span></span> <span data-ttu-id="09feb-202">Por exemplo, todos os objetos de matriz têm uma propriedade **Count** .</span><span class="sxs-lookup"><span data-stu-id="09feb-202">For example, all array objects have a **Count** property.</span></span> <span data-ttu-id="09feb-203">Você pode usá-lo para contar o número de processos em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="09feb-203">You can use that to count the number of processes running on the computer.</span></span>

<span data-ttu-id="09feb-204">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="09feb-204">For example,</span></span>

```powershell
(Get-Process).count
```

<span data-ttu-id="09feb-205">É importante lembrar que os objetos enviados pelo pipeline são entregues um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="09feb-205">It's important to remember that objects sent down the pipeline are delivered one at a time.</span></span>

## <a name="investigating-pipeline-errors"></a><span data-ttu-id="09feb-206">Investigando erros de pipeline</span><span class="sxs-lookup"><span data-stu-id="09feb-206">Investigating pipeline errors</span></span>

<span data-ttu-id="09feb-207">Quando o PowerShell não pode associar os objetos de pipe com um parâmetro do cmdlet receptor, o comando falha.</span><span class="sxs-lookup"><span data-stu-id="09feb-207">When PowerShell can't associate the piped objects with a parameter of the receiving cmdlet, the command fails.</span></span>

<span data-ttu-id="09feb-208">No exemplo a seguir, tentamos mover uma entrada de registro de uma chave do registro para outra.</span><span class="sxs-lookup"><span data-stu-id="09feb-208">In the following example, we try to move a registry entry from one registry key to another.</span></span> <span data-ttu-id="09feb-209">O `Get-Item` cmdlet obtém o caminho de destino, que é então canalizado para o `Move-ItemProperty` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09feb-209">The `Get-Item` cmdlet gets the destination path, which is then piped to the `Move-ItemProperty` cmdlet.</span></span> <span data-ttu-id="09feb-210">O `Move-ItemProperty` comando especifica o caminho atual e o nome da entrada do registro a ser movida.</span><span class="sxs-lookup"><span data-stu-id="09feb-210">The `Move-ItemProperty` command specifies the current path and name of the registry entry to be moved.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales |
Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
```

<span data-ttu-id="09feb-211">O comando falha e o PowerShell exibe a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="09feb-211">The command fails and PowerShell displays the following error message:</span></span>

```Output
Move-ItemProperty : The input object can't be bound to any parameters for
the command either because the command doesn't take pipeline input or the
input and its properties do not match any of the parameters that take
pipeline input.
At line:1 char:23
+ $a | Move-ItemProperty <<<<  -Path HKLM:\Software\MyCompany\design -Name p
```

<span data-ttu-id="09feb-212">Para investigar, use o `Trace-Command` cmdlet para rastrear o componente de associação de parâmetro do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09feb-212">To investigate, use the `Trace-Command` cmdlet to trace the parameter binding component of PowerShell.</span></span> <span data-ttu-id="09feb-213">O exemplo a seguir rastreia a associação de parâmetro enquanto o pipeline está em execução.</span><span class="sxs-lookup"><span data-stu-id="09feb-213">The following example traces parameter binding while the pipeline is executing.</span></span> <span data-ttu-id="09feb-214">O parâmetro **PSHost** exibe os resultados do rastreamento no console e o parâmetro **FilePath** envia os resultados do rastreamento para o `debug.txt` arquivo para referência posterior.</span><span class="sxs-lookup"><span data-stu-id="09feb-214">The **PSHost** parameter displays the trace results in the console and the **FilePath** parameter send the trace results to the `debug.txt` file for later reference.</span></span>

```powershell
Trace-Command -Name ParameterBinding -PSHost -FilePath debug.txt -Expression {
  Get-Item -Path HKLM:\Software\MyCompany\sales |
    Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
}
```

<span data-ttu-id="09feb-215">Os resultados do rastreamento são longos, mas mostram os valores que estão sendo associados ao `Get-Item` cmdlet e, em seguida, os valores nomeados que estão sendo associados ao `Move-ItemProperty` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09feb-215">The results of the trace are lengthy, but they show the values being bound to the `Get-Item` cmdlet and then the named values being bound to the `Move-ItemProperty` cmdlet.</span></span>

```Output
...
BIND NAMED cmd line args [`Move-ItemProperty`]
BIND arg [HKLM:\Software\MyCompany\design] to parameter [Path]
...
BIND arg [product] to parameter [Name]
...
BIND POSITIONAL cmd line args [`Move-ItemProperty`]
...
```

<span data-ttu-id="09feb-216">Por fim, ele mostra que a tentativa de associar o caminho ao  parâmetro de destino `Move-ItemProperty` falha.</span><span class="sxs-lookup"><span data-stu-id="09feb-216">Finally, it shows that the attempt to bind the path to the **Destination** parameter of `Move-ItemProperty` failed.</span></span>

```Output
...
BIND PIPELINE object to parameters: [`Move-ItemProperty`]
PIPELINE object TYPE = [Microsoft.Win32.RegistryKey]
RESTORING pipeline parameter's original values
Parameter [Destination] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
Parameter [Credential] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
...
```

<span data-ttu-id="09feb-217">Use o `Get-Help` cmdlet para exibir os atributos do parâmetro de **destino** .</span><span class="sxs-lookup"><span data-stu-id="09feb-217">Use the `Get-Help` cmdlet to view the attributes of the **Destination** parameter.</span></span>

```Output
Get-Help Move-ItemProperty -Parameter Destination

-Destination <String>
    Specifies the path to the destination location.

    Required?                    true
    Position?                    1
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  false
```

<span data-ttu-id="09feb-218">Os resultados mostram que o **destino** faz apenas a entrada do pipeline "por nome da propriedade".</span><span class="sxs-lookup"><span data-stu-id="09feb-218">The results show that **Destination** takes pipeline input only "by property name".</span></span> <span data-ttu-id="09feb-219">Portanto, o objeto de pipe deve ter uma propriedade chamada **Destination**.</span><span class="sxs-lookup"><span data-stu-id="09feb-219">Therefore, the piped object must have a property named **Destination**.</span></span>

<span data-ttu-id="09feb-220">Use `Get-Member` para ver as propriedades do objeto proveniente de `Get-Item` .</span><span class="sxs-lookup"><span data-stu-id="09feb-220">Use `Get-Member` to see the properties of the object coming from `Get-Item`.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales | Get-Member
```

<span data-ttu-id="09feb-221">A saída mostra que o item é um objeto **Microsoft. Win32. RegistryKey** que não tem uma propriedade de **destino** .</span><span class="sxs-lookup"><span data-stu-id="09feb-221">The output shows that the item is a **Microsoft.Win32.RegistryKey** object that doesn't have a **Destination** property.</span></span> <span data-ttu-id="09feb-222">Isso explica por que o comando falhou.</span><span class="sxs-lookup"><span data-stu-id="09feb-222">That explains why the command failed.</span></span>

<span data-ttu-id="09feb-223">O parâmetro **path** aceita a entrada de pipeline por nome ou por valor.</span><span class="sxs-lookup"><span data-stu-id="09feb-223">The **Path** parameter accepts pipeline input by name or by value.</span></span>

```Output
Get-Help Move-ItemProperty -Parameter Path

-Path <String[]>
    Specifies the path to the current location of the property. Wildcard
    characters are permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  true
```

<span data-ttu-id="09feb-224">Para corrigir o comando, devemos especificar o destino no `Move-ItemProperty` cmdlet e usar `Get-Item` para obter o **caminho** do item que desejamos mover.</span><span class="sxs-lookup"><span data-stu-id="09feb-224">To fix the command, we must specify the destination in the `Move-ItemProperty` cmdlet and use `Get-Item` to get the **Path** of the item we want to move.</span></span>

<span data-ttu-id="09feb-225">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="09feb-225">For example,</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\design |
Move-ItemProperty -Destination HKLM:\Software\MyCompany\sales -Name product
```

## <a name="intrinsic-line-continuation"></a><span data-ttu-id="09feb-226">Continuação de linha intrínseca</span><span class="sxs-lookup"><span data-stu-id="09feb-226">Intrinsic line continuation</span></span>

<span data-ttu-id="09feb-227">Como já foi discutido, um pipeline é uma série de comandos conectados por operadores de pipeline ( `|` ), geralmente gravados em uma única linha.</span><span class="sxs-lookup"><span data-stu-id="09feb-227">As already discussed, a pipeline is a series of commands connected by pipeline operators (`|`), usually written on a single line.</span></span> <span data-ttu-id="09feb-228">No entanto, para facilitar a leitura, o PowerShell permite dividir o pipeline em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="09feb-228">However, for readability, PowerShell allows you to split the pipeline across multiple lines.</span></span>
<span data-ttu-id="09feb-229">Quando um operador de pipe é o último token na linha, o analisador do PowerShell une a linha seguinte ao comando atual para continuar a construção do pipeline.</span><span class="sxs-lookup"><span data-stu-id="09feb-229">When a pipe operator is the last token on the line, the PowerShell parser joins the next line to current command to continue the construction of the pipeline.</span></span>

<span data-ttu-id="09feb-230">Por exemplo, o seguinte pipeline de linha única:</span><span class="sxs-lookup"><span data-stu-id="09feb-230">For example, the following single-line pipeline:</span></span>

```powershell
Command-1 | Command-2 | Command-3
```

<span data-ttu-id="09feb-231">pode ser escrito como:</span><span class="sxs-lookup"><span data-stu-id="09feb-231">can be written as:</span></span>

```powershell
Command-1 |
  Command-2 |
    Command-3
```

<span data-ttu-id="09feb-232">Os espaços à esquerda nas linhas subsequentes não são significativos.</span><span class="sxs-lookup"><span data-stu-id="09feb-232">The leading spaces on the subsequent lines are not significant.</span></span> <span data-ttu-id="09feb-233">O recuo melhora a legibilidade.</span><span class="sxs-lookup"><span data-stu-id="09feb-233">The indentation enhances readability.</span></span>

<span data-ttu-id="09feb-234">O PowerShell 7 adiciona suporte para a continuação de pipelines com o caractere de pipeline no início de uma linha.</span><span class="sxs-lookup"><span data-stu-id="09feb-234">PowerShell 7 adds support for continuation of pipelines with the pipeline character at the beginning of a line.</span></span> <span data-ttu-id="09feb-235">Os exemplos a seguir mostram como você pode usar essa nova funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="09feb-235">The following examples show how you could use this new functionality.</span></span>

```powershell
# Wrapping with a pipe at the beginning of a line (no backtick required)
Get-Process | Where-Object CPU | Where-Object Path
    | Get-Item | Where-Object FullName -match "AppData"
    | Sort-Object FullName -Unique

# Wrapping with a pipe on a line by itself
Get-Process | Where-Object CPU | Where-Object Path
    |
    Get-Item | Where-Object FullName -match "AppData"
    |
    Sort-Object FullName -Unique
```

> [!IMPORTANT]
> <span data-ttu-id="09feb-236">Ao trabalhar interativamente no Shell, colar o código com pipelines no início de uma linha somente ao usar <kbd>Ctrl</kbd> + <kbd>V</kbd> para colar.</span><span class="sxs-lookup"><span data-stu-id="09feb-236">When working interactively in the shell, pasting code with pipelines at the beginning of a line only when using <kbd>Ctrl</kbd>+<kbd>V</kbd> to paste.</span></span>
> <span data-ttu-id="09feb-237">Clique com o botão direito do mouse em copiar operações Insira as linhas uma de cada vez.</span><span class="sxs-lookup"><span data-stu-id="09feb-237">Right-click paste operations insert the lines one at a time.</span></span> <span data-ttu-id="09feb-238">Como a linha não termina com um caractere de pipeline, o PowerShell considera a entrada como concluída e executa essa linha como inserida.</span><span class="sxs-lookup"><span data-stu-id="09feb-238">Since the line does not end with a pipeline character, PowerShell considers the input to be complete and executes that line as entered.</span></span>

## <a name="see-also"></a><span data-ttu-id="09feb-239">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="09feb-239">See Also</span></span>

[<span data-ttu-id="09feb-240">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="09feb-240">about_PSReadLine</span></span>](../../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="09feb-241">about_Objects</span><span class="sxs-lookup"><span data-stu-id="09feb-241">about_Objects</span></span>](about_objects.md)

[<span data-ttu-id="09feb-242">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="09feb-242">about_Parameters</span></span>](about_parameters.md)

[<span data-ttu-id="09feb-243">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="09feb-243">about_Command_Syntax</span></span>](about_command_syntax.md)

[<span data-ttu-id="09feb-244">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="09feb-244">about_ForEach</span></span>](about_foreach.md)

