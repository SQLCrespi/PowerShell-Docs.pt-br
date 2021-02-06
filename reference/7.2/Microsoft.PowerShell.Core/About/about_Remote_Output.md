---
description: Descreve como interpretar e formatar a saída de comandos remotos.
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_output?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Output
ms.openlocfilehash: 476afc62089795d22002ece05c7ce2bf53994237
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597596"
---
# <a name="about-remote-output"></a><span data-ttu-id="63ae4-103">Sobre a saída remota</span><span class="sxs-lookup"><span data-stu-id="63ae4-103">About Remote Output</span></span>

## <a name="short-description"></a><span data-ttu-id="63ae4-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="63ae4-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="63ae4-105">Descreve como interpretar e formatar a saída de comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="63ae4-105">Describes how to interpret and format the output of remote commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="63ae4-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="63ae4-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="63ae4-107">A saída de um comando que foi executado em um computador remoto pode parecer com a saída do mesmo comando executada em um computador local, mas há algumas diferenças significativas.</span><span class="sxs-lookup"><span data-stu-id="63ae4-107">The output of a command that was run on a remote computer might look like output of the same command run on a local computer, but there are some significant differences.</span></span>

<span data-ttu-id="63ae4-108">Este tópico explica como interpretar, Formatar e exibir a saída de comandos que são executados em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="63ae4-108">This topic explains how to interpret, format, and display the output of commands that are run on remote computers.</span></span>

## <a name="displaying-the-computer-name"></a><span data-ttu-id="63ae4-109">EXIBINDO O NOME DO COMPUTADOR</span><span class="sxs-lookup"><span data-stu-id="63ae4-109">DISPLAYING THE COMPUTER NAME</span></span>

<span data-ttu-id="63ae4-110">Quando você usa o cmdlet Invoke-Command para executar um comando em um computador remoto, o comando retorna um objeto que inclui o nome do computador que gerou os dados.</span><span class="sxs-lookup"><span data-stu-id="63ae4-110">When you use the Invoke-Command cmdlet to run a command on a remote computer, the command returns an object that includes the name of the computer that generated the data.</span></span> <span data-ttu-id="63ae4-111">O nome do computador remoto é armazenado na propriedade PSComputerName.</span><span class="sxs-lookup"><span data-stu-id="63ae4-111">The remote computer name is stored in the PSComputerName property.</span></span>

<span data-ttu-id="63ae4-112">Para muitos comandos, o PSComputerName é exibido por padrão.</span><span class="sxs-lookup"><span data-stu-id="63ae4-112">For many commands, the PSComputerName is displayed by default.</span></span> <span data-ttu-id="63ae4-113">Por exemplo, o comando a seguir executa um comando Get-Culture em dois computadores remotos, Server01 e Server02.</span><span class="sxs-lookup"><span data-stu-id="63ae4-113">For example, the following command runs a Get-Culture command on two remote computers, Server01 and Server02.</span></span> <span data-ttu-id="63ae4-114">A saída, que aparece abaixo, inclui os nomes dos computadores remotos nos quais o comando foi executado.</span><span class="sxs-lookup"><span data-stu-id="63ae4-114">The output, which appears below, includes the names of the remote computers on which the command ran.</span></span>

```powershell
C:\PS> invoke-command -script {get-culture} -comp Server01, Server02

LCID  Name    DisplayName                PSComputerName
----  ----    -----------                --------------
1033  en-US   English (United States)    Server01
1033  es-AR   Spanish (Argentina)        Server02
```

<span data-ttu-id="63ae4-115">Você pode usar o parâmetro HideComputerName de Invoke-Command para ocultar a propriedade PSComputerName.</span><span class="sxs-lookup"><span data-stu-id="63ae4-115">You can use the HideComputerName parameter of Invoke-Command to hide the PSComputerName property.</span></span> <span data-ttu-id="63ae4-116">Esse parâmetro é projetado para comandos que coletam dados de apenas um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="63ae4-116">This parameter is designed for commands that collect data from only one remote computer.</span></span>

<span data-ttu-id="63ae4-117">O comando a seguir executa um comando Get-Culture no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="63ae4-117">The following command runs a Get-Culture command on the Server01 remote computer.</span></span> <span data-ttu-id="63ae4-118">Ele usa o parâmetro HideComputerName para ocultar a propriedade PSComputerName e as propriedades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="63ae4-118">It uses the HideComputerName parameter to hide the PSComputerName property and related properties.</span></span>

```powershell
C:\PS> invoke-command -scr {get-culture} -comp Server01 -HideComputerName

LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

<span data-ttu-id="63ae4-119">Você também pode exibir a propriedade PSComputerName se ela não for exibida por padrão.</span><span class="sxs-lookup"><span data-stu-id="63ae4-119">You can also display the PSComputerName property if it is not displayed by default.</span></span>

<span data-ttu-id="63ae4-120">Por exemplo, os comandos a seguir usam o cmdlet Format-Table para adicionar a propriedade PSComputerName à saída de um comando de Get-Date remoto.</span><span class="sxs-lookup"><span data-stu-id="63ae4-120">For example, the following commands use the Format-Table cmdlet to add the PSComputerName property to the output of a remote Get-Date command.</span></span>

```powershell
$dates = invoke-command -script {get-date} -computername Server01, Server02
$dates | format-table DateTime, PSComputerName -auto

DateTime                            PSComputerName
--------                            --------------
Monday, July 21, 2008 7:16:58 PM    Server01
Monday, July 21, 2008 7:16:58 PM    Server02
```

## <a name="displaying-the-machinename-property"></a><span data-ttu-id="63ae4-121">EXIBINDO A PROPRIEDADE MACHINENAME</span><span class="sxs-lookup"><span data-stu-id="63ae4-121">DISPLAYING THE MACHINENAME PROPERTY</span></span>

<span data-ttu-id="63ae4-122">Vários cmdlets, incluindo Get-Process, Get-Service e Get-EventLog, têm um parâmetro ComputerName que obtém os objetos em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="63ae4-122">Several cmdlets, including Get-Process, Get-Service, and Get-EventLog, have a ComputerName parameter that gets the objects on a remote computer.</span></span>
<span data-ttu-id="63ae4-123">Esses cmdlets não usam a comunicação remota do PowerShell para que você possa usá-los mesmo em computadores que não estão configurados para comunicação remota no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63ae4-123">These cmdlets do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting in Windows PowerShell.</span></span>

<span data-ttu-id="63ae4-124">Os objetos que esses cmdlets retornam armazenam o nome do computador remoto na propriedade MachineName.</span><span class="sxs-lookup"><span data-stu-id="63ae4-124">The objects that these cmdlets return store the name of the remote computer in the MachineName property.</span></span> <span data-ttu-id="63ae4-125">(Esses objetos não têm uma propriedade PSComputerName.)</span><span class="sxs-lookup"><span data-stu-id="63ae4-125">(These objects do not have a PSComputerName property.)</span></span>

<span data-ttu-id="63ae4-126">Por exemplo, esse comando obtém o processo do PowerShell nos computadores remotos Server01 e Server02.</span><span class="sxs-lookup"><span data-stu-id="63ae4-126">For example, this command gets the PowerShell process on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="63ae4-127">A exibição padrão não inclui a propriedade MachineName.</span><span class="sxs-lookup"><span data-stu-id="63ae4-127">The default display does not include the MachineName property.</span></span>

```powershell
C:\PS> get-process PowerShell -computername server01, server02

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
920      38    97524     114504   575     9.66   2648 PowerShell
194       6    24256      32384   142            3020 PowerShell
352      27    63472      63520   577     3.84   4796 PowerShell
```

<span data-ttu-id="63ae4-128">Você pode usar o cmdlet Format-Table para exibir a propriedade MachineName dos objetos de processo.</span><span class="sxs-lookup"><span data-stu-id="63ae4-128">You can use the Format-Table cmdlet to display the MachineName property of the process objects.</span></span>

<span data-ttu-id="63ae4-129">Por exemplo, o comando a seguir salva os processos na variável $p e, em seguida, usa um operador de pipeline (|) para enviar os processos em $p para o comando Format-Table.</span><span class="sxs-lookup"><span data-stu-id="63ae4-129">For example, the following command saves the processes in the $p variable and then uses a pipeline operator (|) to send the processes in $p to the Format-Table command.</span></span> <span data-ttu-id="63ae4-130">O comando usa o parâmetro Property de Format-Table para incluir a propriedade MachineName na exibição.</span><span class="sxs-lookup"><span data-stu-id="63ae4-130">The command uses the Property parameter of Format-Table to include the MachineName property in the display.</span></span>

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02
C:\PS> $P | format-table -property ID, ProcessName, MachineName -auto

Id ProcessName MachineName
-- ----------- -----------
2648 PowerShell  Server02
3020 PowerShell  Server01
4796 PowerShell  Server02
```

<span data-ttu-id="63ae4-131">O comando mais complexo a seguir adiciona a propriedade MachineName à exibição do processo padrão.</span><span class="sxs-lookup"><span data-stu-id="63ae4-131">The following more complex command adds the MachineName property to the default process display.</span></span> <span data-ttu-id="63ae4-132">Ele usa tabelas de hash para especificar propriedades calculadas.</span><span class="sxs-lookup"><span data-stu-id="63ae4-132">It uses hash tables to specify calculated properties.</span></span> <span data-ttu-id="63ae4-133">Felizmente, você não precisa entender isso para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="63ae4-133">Fortunately, you do not have to understand it to use it.</span></span>

<span data-ttu-id="63ae4-134">(Observe que o acento grave ['] é o caractere de continuação.)</span><span class="sxs-lookup"><span data-stu-id="63ae4-134">(Note that the backtick [\`] is the continuation character.)</span></span>

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02

C:\PS> $p | format-table -property Handles, `
@{Label="NPM(K)";Expression={int}}, `
@{Label="PM(K)";Expression={int}}, `
@{Label="WS(K)";Expression={int}}, `
@{Label="VM(M)";Expression={int}}, `
@{Label="CPU(s)";Expression={if ($.CPU -ne $()){ $.CPU.ToString("N")}}}, `
Id, ProcessName, MachineName -auto

Handles NPM(K) PM(K)  WS(K) VM(M) CPU(s)   Id ProcessName MachineName
------- ------ -----  ----- ----- ------   -- ----------- -----------
920     38 97560 114532   576        2648 PowerShell  Server02
192      6 24132  32028   140        3020 PowerShell  Server01
438     26 48436  59132   565        4796 PowerShell  Server02

```

## <a name="deserialized-objects"></a><span data-ttu-id="63ae4-135">OBJETOS DESSERIALIZADOS</span><span class="sxs-lookup"><span data-stu-id="63ae4-135">DESERIALIZED OBJECTS</span></span>

<span data-ttu-id="63ae4-136">Quando você executa comandos remotos que geram saída, a saída do comando é transmitida pela rede de volta para o computador local.</span><span class="sxs-lookup"><span data-stu-id="63ae4-136">When you run remote commands that generate output, the command output is transmitted across the network back to the local computer.</span></span>

<span data-ttu-id="63ae4-137">Como a maioria dos objetos do Live Microsoft .NET Framework (como os objetos retornados pelos cmdlets do PowerShell) não pode ser transmitida pela rede, os objetos dinâmicos são "serializados".</span><span class="sxs-lookup"><span data-stu-id="63ae4-137">Because most live Microsoft .NET Framework objects (such as the objects that PowerShell cmdlets return) cannot be transmitted over the network, the live objects are "serialized".</span></span> <span data-ttu-id="63ae4-138">Em outras palavras, os objetos dinâmicos são convertidos em representações XML do objeto e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="63ae4-138">In other words, the live objects are converted into XML representations of the object and its properties.</span></span> <span data-ttu-id="63ae4-139">Em seguida, o objeto serializado baseado em XML é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="63ae4-139">Then, the XML-based serialized object is transmitted across the network.</span></span>

<span data-ttu-id="63ae4-140">No computador local, o PowerShell recebe o objeto serializado baseado em XML e o "desserializa" convertendo o objeto baseado em XML em um objeto de .NET Framework padrão.</span><span class="sxs-lookup"><span data-stu-id="63ae4-140">On the local computer, PowerShell receives the XML-based serialized object and "deserializes" it by converting the XML-based object into a standard .NET Framework object.</span></span>

<span data-ttu-id="63ae4-141">No entanto, o objeto desserializado não é um objeto dinâmico.</span><span class="sxs-lookup"><span data-stu-id="63ae4-141">However, the deserialized object is not a live object.</span></span> <span data-ttu-id="63ae4-142">É um instantâneo do objeto no momento em que ele foi serializado e inclui propriedades, mas nenhum método.</span><span class="sxs-lookup"><span data-stu-id="63ae4-142">It is a snapshot of the object at the time that it was serialized, and it includes properties but no methods.</span></span> <span data-ttu-id="63ae4-143">Você pode usar e gerenciar esses objetos no PowerShell, incluindo passá-los em pipelines, exibir as propriedades selecionadas e formatá-los.</span><span class="sxs-lookup"><span data-stu-id="63ae4-143">You can use and manage these objects in PowerShell, including passing them in pipelines, displaying selected properties, and formatting them.</span></span>

<span data-ttu-id="63ae4-144">A maioria dos objetos desserializados são automaticamente formatados para exibição por entradas no Types.ps1XML ou Format.ps1arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="63ae4-144">Most deserialized objects are automatically formatted for display by entries in the Types.ps1xml or Format.ps1xml files.</span></span> <span data-ttu-id="63ae4-145">No entanto, o computador local pode não ter arquivos de formatação para todos os objetos desserializados que foram gerados em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="63ae4-145">However, the local computer might not have formatting files for all of the deserialized objects that were generated on a remote computer.</span></span> <span data-ttu-id="63ae4-146">Quando os objetos não são formatados, todas as propriedades de cada objeto aparecem no console do em uma lista de streaming.</span><span class="sxs-lookup"><span data-stu-id="63ae4-146">When objects are not formatted, all of the properties of each object appear in the console in a streaming list.</span></span>

<span data-ttu-id="63ae4-147">Quando os objetos não são formatados automaticamente, você pode usar os cmdlets de formatação, como Format-Table ou Format-List, para formatar e exibir as propriedades selecionadas.</span><span class="sxs-lookup"><span data-stu-id="63ae4-147">When objects are not formatted automatically, you can use the formatting cmdlets, such as Format-Table or Format-List, to format and display selected properties.</span></span> <span data-ttu-id="63ae4-148">Ou, você pode usar o cmdlet Out-GridView para exibir os objetos em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="63ae4-148">Or, you can use the Out-GridView cmdlet to display the objects in a table.</span></span>

<span data-ttu-id="63ae4-149">Além disso, se você executar um comando em um computador remoto que usa cmdlets que não tem em seu computador local, os objetos que o comando retorna podem não estar formatados corretamente porque você não tem os arquivos de formatação para esses objetos em seu computador.</span><span class="sxs-lookup"><span data-stu-id="63ae4-149">Also, if you run a command on a remote computer that uses cmdlets that you do not have on your local computer, the objects that the command returns might not be formatted properly because you do not have the formatting files for those objects on your computer.</span></span> <span data-ttu-id="63ae4-150">Para obter dados de formatação de outro computador, use os cmdlets Get-FormatData e Export-FormatData.</span><span class="sxs-lookup"><span data-stu-id="63ae4-150">To get formatting data from another computer, use the Get-FormatData and Export-FormatData cmdlets.</span></span>

<span data-ttu-id="63ae4-151">Alguns tipos de objeto, como objetos DirectoryInfo e GUIDs, são convertidos de volta em objetos dinâmicos quando eles são recebidos.</span><span class="sxs-lookup"><span data-stu-id="63ae4-151">Some object types, such as DirectoryInfo objects and GUIDs, are converted back into live objects when they are received.</span></span> <span data-ttu-id="63ae4-152">Esses objetos não precisam de tratamento ou formatação especial.</span><span class="sxs-lookup"><span data-stu-id="63ae4-152">These objects do not need any special handling or formatting.</span></span>

## <a name="ordering-the-results"></a><span data-ttu-id="63ae4-153">ORDENANDO OS RESULTADOS</span><span class="sxs-lookup"><span data-stu-id="63ae4-153">ORDERING THE RESULTS</span></span>

<span data-ttu-id="63ae4-154">A ordem dos nomes de computador no parâmetro ComputerName de cmdlets determina a ordem na qual o PowerShell se conecta aos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="63ae4-154">The order of the computer names in the ComputerName parameter of cmdlets determines the order in which PowerShell connects to the remote computers.</span></span> <span data-ttu-id="63ae4-155">No entanto, os resultados aparecem na ordem em que o computador local os recebe, o que pode ser uma ordem diferente.</span><span class="sxs-lookup"><span data-stu-id="63ae4-155">However, the results appear in the order in which the local computer receives them, which might be a different order.</span></span>

<span data-ttu-id="63ae4-156">Para alterar a ordem dos resultados, use o cmdlet Sort-Object.</span><span class="sxs-lookup"><span data-stu-id="63ae4-156">To change the order of the results, use the Sort-Object cmdlet.</span></span> <span data-ttu-id="63ae4-157">Você pode classificar na propriedade PSComputerName ou MachineName.</span><span class="sxs-lookup"><span data-stu-id="63ae4-157">You can sort on the PSComputerName or MachineName property.</span></span> <span data-ttu-id="63ae4-158">Você também pode classificar outra Propriedade do objeto para que os resultados de diferentes computadores sejam intercalados.</span><span class="sxs-lookup"><span data-stu-id="63ae4-158">You can also sort on another property of the object so that the results from different computers are interspersed.</span></span>

## <a name="see-also"></a><span data-ttu-id="63ae4-159">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="63ae4-159">SEE ALSO</span></span>

[<span data-ttu-id="63ae4-160">about_Remote</span><span class="sxs-lookup"><span data-stu-id="63ae4-160">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="63ae4-161">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="63ae4-161">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="63ae4-162">Format-Table</span><span class="sxs-lookup"><span data-stu-id="63ae4-162">Format-Table</span></span>](xref:Microsoft.PowerShell.Utility.Format-Table)

[<span data-ttu-id="63ae4-163">Get-Process</span><span class="sxs-lookup"><span data-stu-id="63ae4-163">Get-Process</span></span>](xref:Microsoft.PowerShell.Management.Get-Process)

[<span data-ttu-id="63ae4-164">Get-Service</span><span class="sxs-lookup"><span data-stu-id="63ae4-164">Get-Service</span></span>](xref:Microsoft.PowerShell.Management.Get-Service)

[<span data-ttu-id="63ae4-165">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="63ae4-165">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="63ae4-166">Select-Object</span><span class="sxs-lookup"><span data-stu-id="63ae4-166">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

