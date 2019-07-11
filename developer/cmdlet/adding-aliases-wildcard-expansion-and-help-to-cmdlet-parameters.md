---
title: Adicionar Aliases, expansão de curinga e ajudar a parâmetros de Cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 931ccace-c565-4a98-8dcc-df00f86394b1
caps.latest.revision: 8
ms.openlocfilehash: bc921537062e35aa203fa3ee95d3b7211c89cb28
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67733840"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a><span data-ttu-id="5cb09-102">Adicionar aliases, expansão de curinga e ajuda a parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="5cb09-102">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>

<span data-ttu-id="5cb09-103">Esta seção descreve como adicionar aliases, expansão de curinga, e mensagens de ajuda para os parâmetros do cmdlet Stop-Proc (descrito na [criação de um Cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md)).</span><span class="sxs-lookup"><span data-stu-id="5cb09-103">This section describes how to add aliases, wildcard expansion, and Help messages to the parameters of the Stop-Proc cmdlet (described in [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md)).</span></span>

<span data-ttu-id="5cb09-104">Esse cmdlet Stop-Proc tenta interromper os processos que são recuperados usando o cmdlet Get-Proc (descrito na [criando seu primeiro Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="5cb09-104">This Stop-Proc cmdlet attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="5cb09-105">Definindo o Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5cb09-105">Defining the Cmdlet</span></span>

<span data-ttu-id="5cb09-106">A primeira etapa na criação de cmdlet sempre é o cmdlet de nomenclatura e declarar a classe .NET que implementa o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5cb09-106">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="5cb09-107">Porque você está escrevendo um cmdlet para alterar o sistema, ele deve ser nomeado adequadamente.</span><span class="sxs-lookup"><span data-stu-id="5cb09-107">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="5cb09-108">Como este cmdlet interrompe os processos do sistema, ele usa o verbo "Stop", definido pela [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) classe, com o substantivo "Processo" para indicar o processo.</span><span class="sxs-lookup"><span data-stu-id="5cb09-108">Because this cmdlet stops system processes, it uses the verb "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate process.</span></span> <span data-ttu-id="5cb09-109">Para obter mais informações sobre os verbos aprovados do cmdlet, consulte [nomes de verbos de Cmdlet](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="5cb09-109">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="5cb09-110">O código a seguir é a definição de classe para esse cmdlet Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="5cb09-110">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="5cb09-111">Definir parâmetros para modificação do sistema</span><span class="sxs-lookup"><span data-stu-id="5cb09-111">Defining Parameters for System Modification</span></span>

<span data-ttu-id="5cb09-112">O cmdlet precisa definir os parâmetros que modificações no sistema de suporte e comentários do usuário.</span><span class="sxs-lookup"><span data-stu-id="5cb09-112">Your cmdlet needs to define parameters that support system modifications and user feedback.</span></span> <span data-ttu-id="5cb09-113">O cmdlet deve definir um `Name` parâmetro ou equivalente para que o cmdlet será capaz de modificar o sistema por algum tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="5cb09-113">The cmdlet should define a `Name` parameter or equivalent so that the cmdlet will be able to modify the system by some sort of identifier.</span></span> <span data-ttu-id="5cb09-114">Além disso, o cmdlet deve definir a `Force` e `PassThru` parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5cb09-114">In addition, the cmdlet should define the `Force` and `PassThru` parameters.</span></span> <span data-ttu-id="5cb09-115">Para obter mais informações sobre esses parâmetros, consulte [criação de um Cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="5cb09-115">For more information about these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="defining-a-parameter-alias"></a><span data-ttu-id="5cb09-116">Definir um Alias de parâmetro</span><span class="sxs-lookup"><span data-stu-id="5cb09-116">Defining a Parameter Alias</span></span>

<span data-ttu-id="5cb09-117">Um alias de parâmetro pode ser um nome alternativo ou bem-definidos 1 ou 2 letras nome curto para um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5cb09-117">A parameter alias can be an alternate name or a well-defined 1-letter or 2-letter short name for a cmdlet parameter.</span></span> <span data-ttu-id="5cb09-118">Em ambos os casos, o objetivo de usar aliases é simplificar a entrada do usuário na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="5cb09-118">In both cases, the goal of using aliases is to simplify user entry from the command line.</span></span> <span data-ttu-id="5cb09-119">Windows PowerShell dá suporte a aliases de parâmetro por meio de [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) atributo, que usa a sintaxe de declaração [Alias()].</span><span class="sxs-lookup"><span data-stu-id="5cb09-119">Windows PowerShell supports parameter aliases through the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, which uses the declaration syntax [Alias()].</span></span>

<span data-ttu-id="5cb09-120">O código a seguir mostra como um alias é adicionado para o `Name` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5cb09-120">The following code shows how an alias is added to the `Name` parameter.</span></span>

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
[Alias("ProcessName")]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

<span data-ttu-id="5cb09-121">Além de usar o [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) atributo, o tempo de execução do Windows PowerShell executa a correspondência de nome parcial, mesmo se nenhum alias for especificadas.</span><span class="sxs-lookup"><span data-stu-id="5cb09-121">In addition to using the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, the Windows PowerShell runtime performs partial name matching, even if no aliases are specified.</span></span> <span data-ttu-id="5cb09-122">Por exemplo, se seu cmdlet possui um `FileName` parâmetro e que é o único parâmetro que começa com `F`, o usuário poderia digitar `Filename`, `Filenam`, `File`, `Fi`, ou `F` e ainda reconhecer a entrada, como o `FileName` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5cb09-122">For example, if your cmdlet has a `FileName` parameter and that is the only parameter that starts with `F`, the user could enter `Filename`, `Filenam`, `File`, `Fi`, or `F` and still recognize the entry as the `FileName` parameter.</span></span>

## <a name="creating-help-for-parameters"></a><span data-ttu-id="5cb09-123">Ajuda para os parâmetros de criação</span><span class="sxs-lookup"><span data-stu-id="5cb09-123">Creating Help for Parameters</span></span>

<span data-ttu-id="5cb09-124">Windows PowerShell permite que você crie a Ajuda para os parâmetros de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5cb09-124">Windows PowerShell allows you to create Help for cmdlet parameters.</span></span> <span data-ttu-id="5cb09-125">Faça isso para qualquer parâmetro usado para comentários de usuário e a modificação do sistema.</span><span class="sxs-lookup"><span data-stu-id="5cb09-125">Do this for any parameter used for system modification and user feedback.</span></span> <span data-ttu-id="5cb09-126">Para cada parâmetro dar suporte à Ajuda, você pode definir as `HelpMessage` palavra-chave de atributo o [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) declaração do atributo.</span><span class="sxs-lookup"><span data-stu-id="5cb09-126">For each parameter to support Help, you can set the `HelpMessage` attribute keyword in the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="5cb09-127">Essa palavra-chave define o texto a ser exibido ao usuário para assistência usando o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5cb09-127">This keyword defines the text to display to the user for assistance in using the parameter.</span></span> <span data-ttu-id="5cb09-128">Você também pode definir o `HelpMessageBaseName` palavra-chave para identificar o nome de base de um recurso a ser usado para a mensagem.</span><span class="sxs-lookup"><span data-stu-id="5cb09-128">You can also set the `HelpMessageBaseName` keyword to identify the base name of a resource to use for the message.</span></span> <span data-ttu-id="5cb09-129">Se você definir essa palavra-chave, você também deve definir o `HelpMessageResourceId` palavra-chave para especificar o identificador de recurso.</span><span class="sxs-lookup"><span data-stu-id="5cb09-129">If you set this keyword, you must also set the `HelpMessageResourceId` keyword to specify the resource identifier.</span></span>

<span data-ttu-id="5cb09-130">O código a seguir desse cmdlet Stop-Proc define o `HelpMessage` atributo a palavra-chave para o `Name` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5cb09-130">The following code from this Stop-Proc cmdlet defines the `HelpMessage` attribute keyword for the `Name` parameter.</span></span>

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="5cb09-131">Substituindo uma método de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="5cb09-131">Overriding an Input Processing Method</span></span>

<span data-ttu-id="5cb09-132">O cmdlet deve substituir uma método de processamento de entrada, mais frequentemente, isso será [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span><span class="sxs-lookup"><span data-stu-id="5cb09-132">Your cmdlet must override an input processing method, most often this will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="5cb09-133">Ao modificar o sistema, o cmdlet deve chamar o [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) métodos para permitir que o usuário para fornecer comentários antes que uma alteração é feita.</span><span class="sxs-lookup"><span data-stu-id="5cb09-133">When modifying the system, the cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to allow the user to provide feedback before a change is made.</span></span> <span data-ttu-id="5cb09-134">Para obter mais informações sobre esses métodos, consulte [criação de um Cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="5cb09-134">For more information about these methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="supporting-wildcard-expansion"></a><span data-ttu-id="5cb09-135">Suporte à expansão de curinga</span><span class="sxs-lookup"><span data-stu-id="5cb09-135">Supporting Wildcard Expansion</span></span>

<span data-ttu-id="5cb09-136">Para permitir que a seleção de vários objetos, o cmdlet pode usar o [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) e [System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) classes para fornecer suporte de expansão de curinga para o parâmetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="5cb09-136">To allow the selection of multiple objects, your cmdlet can use the [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) and [System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) classes to provide wildcard expansion support for parameter input.</span></span> <span data-ttu-id="5cb09-137">São exemplos de padrões de curinga de lsa \* \*. txt e [a-c]\*.</span><span class="sxs-lookup"><span data-stu-id="5cb09-137">Examples of wildcard patterns are lsa\*, \*.txt, and [a-c]\*.</span></span> <span data-ttu-id="5cb09-138">Use o caractere de acento (') como um caractere de escape quando o padrão contém um caractere que deve ser usado literalmente.</span><span class="sxs-lookup"><span data-stu-id="5cb09-138">Use the back-quote character (\`) as an escape character when the pattern contains a character that should be used literally.</span></span>

<span data-ttu-id="5cb09-139">Expansões de curinga de nomes de arquivo e caminho são exemplos de cenários comuns em que o cmdlet talvez queira permitir que o suporte para entradas de caminho quando a seleção de vários objetos é necessária.</span><span class="sxs-lookup"><span data-stu-id="5cb09-139">Wildcard expansions of file and path names are examples of common scenarios where the cmdlet may want to allow support for path inputs when the selection of multiple objects is required.</span></span> <span data-ttu-id="5cb09-140">Um caso comum é no sistema de arquivos, em que um usuário quiser ver todos os arquivos que residem na pasta atual.</span><span class="sxs-lookup"><span data-stu-id="5cb09-140">A common case is in the file system, where a user wants to see all files residing in the current folder.</span></span>

<span data-ttu-id="5cb09-141">Você precisa apenas raramente uma implementação de correspondência de padrão de curinga personalizados.</span><span class="sxs-lookup"><span data-stu-id="5cb09-141">You should need a customized wildcard pattern matching implementation only rarely.</span></span> <span data-ttu-id="5cb09-142">Nesse caso, seu cmdlet deve dar suporte a 1003.2 POSIX completa, especificação 3.13 para expansão de curinga ou o subconjunto simplificado a seguir:</span><span class="sxs-lookup"><span data-stu-id="5cb09-142">In this case, your cmdlet should support either the full POSIX 1003.2, 3.13 specification for wildcard expansion or the following simplified subset:</span></span>

- <span data-ttu-id="5cb09-143">**Ponto de interrogação (?).**</span><span class="sxs-lookup"><span data-stu-id="5cb09-143">**Question mark (?).**</span></span> <span data-ttu-id="5cb09-144">Corresponde a qualquer caractere no local especificado.</span><span class="sxs-lookup"><span data-stu-id="5cb09-144">Matches any character at the specified location.</span></span>

- <span data-ttu-id="5cb09-145">**Asterisco (\*).**</span><span class="sxs-lookup"><span data-stu-id="5cb09-145">**Asterisk (\*).**</span></span> <span data-ttu-id="5cb09-146">Corresponde a zero ou mais caracteres começando no local especificado.</span><span class="sxs-lookup"><span data-stu-id="5cb09-146">Matches zero or more characters starting at the specified location.</span></span>

- <span data-ttu-id="5cb09-147">**Colchete de abertura ([]).**</span><span class="sxs-lookup"><span data-stu-id="5cb09-147">**Open bracket ([).**</span></span> <span data-ttu-id="5cb09-148">Apresenta uma expressão entre colchetes padrão que pode conter caracteres ou um intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5cb09-148">Introduces a pattern bracket expression that can contain characters or a range of characters.</span></span> <span data-ttu-id="5cb09-149">Se um intervalo for necessário, um hífen (-) é usado para indicar o intervalo.</span><span class="sxs-lookup"><span data-stu-id="5cb09-149">If a range is required, a hyphen (-) is used to indicate the range.</span></span>

- <span data-ttu-id="5cb09-150">**Colchete de fechamento (]).**</span><span class="sxs-lookup"><span data-stu-id="5cb09-150">**Close bracket (]).**</span></span> <span data-ttu-id="5cb09-151">Termina uma expressão entre colchetes de padrão.</span><span class="sxs-lookup"><span data-stu-id="5cb09-151">Ends a pattern bracket expression.</span></span>

- <span data-ttu-id="5cb09-152">**Acento caractere de escape (').**</span><span class="sxs-lookup"><span data-stu-id="5cb09-152">**Back-quote escape character (\`).**</span></span> <span data-ttu-id="5cb09-153">Indica que o próximo caractere deve ser interpretado literalmente.</span><span class="sxs-lookup"><span data-stu-id="5cb09-153">Indicates that the next character should be taken literally.</span></span> <span data-ttu-id="5cb09-154">Lembre-se de que ao especificar o caractere de acento da linha de comando (em vez de especificá-lo por meio de programação), o caractere de escape de acento deve ser especificado duas vezes.</span><span class="sxs-lookup"><span data-stu-id="5cb09-154">Be aware that when specifying the back-quote character from the command line (as opposed to specifying it programmatically), the back-quote escape character must be specified twice.</span></span>

> [!NOTE]
> <span data-ttu-id="5cb09-155">Para obter mais informações sobre padrões de curinga, consulte [que dão suporte a curingas nos parâmetros de Cmdlet](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="5cb09-155">For more information about wildcard patterns, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span></span>

<span data-ttu-id="5cb09-156">O código a seguir mostra como definir opções de curinga e definir o padrão de curinga usado para resolver o `Name` parâmetro desse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5cb09-156">The following code shows how to set wildcard options and define the wildcard pattern used for resolving the `Name` parameter for this cmdlet.</span></span>

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

<span data-ttu-id="5cb09-157">O código a seguir mostra como testar se o nome do processo corresponde ao padrão de curinga definido.</span><span class="sxs-lookup"><span data-stu-id="5cb09-157">The following code shows how to test whether the process name matches the defined wildcard pattern.</span></span> <span data-ttu-id="5cb09-158">Observe que, nesse caso, se o nome do processo não coincide com o padrão, o cmdlet continua em obter o próximo nome de processo.</span><span class="sxs-lookup"><span data-stu-id="5cb09-158">Notice that, in this case, if the process name does not match the pattern, the cmdlet continues on to get the next process name.</span></span>

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a><span data-ttu-id="5cb09-159">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="5cb09-159">Code Sample</span></span>

<span data-ttu-id="5cb09-160">Para o completo C# exemplos de código, consulte [StopProcessSample03 amostra](./stopprocesssample03-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5cb09-160">For the complete C# sample code, see [StopProcessSample03 Sample](./stopprocesssample03-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="5cb09-161">Definir tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="5cb09-161">Define Object Types and Formatting</span></span>

<span data-ttu-id="5cb09-162">Windows PowerShell passa informações entre cmdlets usando objetos .net.</span><span class="sxs-lookup"><span data-stu-id="5cb09-162">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="5cb09-163">Consequentemente, talvez seja necessário definir seu próprio tipo de um cmdlet ou o cmdlet talvez precise estender um tipo existente fornecido pelo outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5cb09-163">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="5cb09-164">Para obter mais informações sobre como definir novos tipos ou estender os tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="5cb09-164">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="5cb09-165">Criando o Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5cb09-165">Building the Cmdlet</span></span>

<span data-ttu-id="5cb09-166">Depois de implementar um cmdlet, ele deve ser registrado com o Windows PowerShell por meio de um snap-in do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cb09-166">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="5cb09-167">Para obter mais informações sobre como registrar cmdlets, consulte [como registrar Cmdlets, provedores e aplicativos Host](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="5cb09-167">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="5cb09-168">Testando o Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5cb09-168">Testing the Cmdlet</span></span>

<span data-ttu-id="5cb09-169">Quando seu cmdlet tiver sido registrado com o Windows PowerShell, você pode testá-lo executando-o na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="5cb09-169">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="5cb09-170">Vamos testar o exemplo de cmdlet Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="5cb09-170">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="5cb09-171">Para obter mais informações sobre como usar os cmdlets da linha de comando, consulte o [Introdução ao Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5cb09-171">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="5cb09-172">Inicie o Windows PowerShell e use Proc Stop para interromper um processo usando o alias ProcessName para o `Name` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5cb09-172">Start Windows PowerShell and use Stop-Proc to stop a process using the ProcessName alias for the `Name` parameter.</span></span>

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

<span data-ttu-id="5cb09-173">A seguinte saída é exibida.</span><span class="sxs-lookup"><span data-stu-id="5cb09-173">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="5cb09-174">Verifique a entrada a seguir na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="5cb09-174">Make the following entry on the command line.</span></span> <span data-ttu-id="5cb09-175">Como o parâmetro de nome é obrigatório, você será solicitado para ele.</span><span class="sxs-lookup"><span data-stu-id="5cb09-175">Because the Name parameter is mandatory, you are prompted for it.</span></span> <span data-ttu-id="5cb09-176">Inserir "!?"</span><span class="sxs-lookup"><span data-stu-id="5cb09-176">Entering "!?"</span></span> <span data-ttu-id="5cb09-177">Exibe o texto de ajuda associado ao parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5cb09-177">brings up the help text associated with the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

<span data-ttu-id="5cb09-178">A seguinte saída é exibida.</span><span class="sxs-lookup"><span data-stu-id="5cb09-178">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- <span data-ttu-id="5cb09-179">Agora, verifique a seguinte entrada para interromper todos os processos que correspondem ao padrão de curinga "\* Observação\*".</span><span class="sxs-lookup"><span data-stu-id="5cb09-179">Now make the following entry to stop all processes that match the wildcard pattern "\*note\*".</span></span> <span data-ttu-id="5cb09-180">Você será solicitado antes de parar a cada processo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="5cb09-180">You are prompted before stopping each process that matches the pattern.</span></span>

    ```powershell
    PS> stop-proc -Name *note*
    ```

<span data-ttu-id="5cb09-181">A seguinte saída é exibida.</span><span class="sxs-lookup"><span data-stu-id="5cb09-181">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

<span data-ttu-id="5cb09-182">A seguinte saída é exibida.</span><span class="sxs-lookup"><span data-stu-id="5cb09-182">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

<span data-ttu-id="5cb09-183">A seguinte saída é exibida.</span><span class="sxs-lookup"><span data-stu-id="5cb09-183">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="5cb09-184">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5cb09-184">See Also</span></span>

[<span data-ttu-id="5cb09-185">Criar um Cmdlet que modifica o sistema</span><span class="sxs-lookup"><span data-stu-id="5cb09-185">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="5cb09-186">Como criar um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cb09-186">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="5cb09-187">[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="5cb09-187">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="5cb09-188">[Como registrar Cmdlets, provedores e aplicativos de Host](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="5cb09-188">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="5cb09-189">Suporte a curingas nos parâmetros do Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5cb09-189">Supporting Wildcards in Cmdlet Parameters</span></span>](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[<span data-ttu-id="5cb09-190">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cb09-190">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
