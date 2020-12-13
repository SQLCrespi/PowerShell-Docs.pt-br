---
ms.date: 09/13/2016
ms.topic: reference
title: Adicionar aliases, expansão de curinga e ajuda a parâmetros de cmdlet
description: Adicionar aliases, expansão de curinga e ajuda a parâmetros de cmdlet
ms.openlocfilehash: f0f07796370b4613b1ca0ad17b16c6598bfa438d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660635"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a><span data-ttu-id="85a2f-103">Adicionar aliases, expansão de curinga e ajuda a parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="85a2f-103">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>

<span data-ttu-id="85a2f-104">Esta seção descreve como adicionar aliases, expansão de curinga e mensagens de ajuda aos parâmetros do cmdlet Stop-Proc (descrito em [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md)).</span><span class="sxs-lookup"><span data-stu-id="85a2f-104">This section describes how to add aliases, wildcard expansion, and Help messages to the parameters of the Stop-Proc cmdlet (described in [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md)).</span></span>

<span data-ttu-id="85a2f-105">Esse Stop-Proc cmdlet tenta parar os processos recuperados usando o cmdlet Get-Proc (descrito em [criando seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="85a2f-105">This Stop-Proc cmdlet attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="85a2f-106">Definindo o cmdlet</span><span class="sxs-lookup"><span data-stu-id="85a2f-106">Defining the Cmdlet</span></span>

<span data-ttu-id="85a2f-107">A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85a2f-107">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="85a2f-108">Como você está escrevendo um cmdlet para alterar o sistema, ele deve ser nomeado de acordo.</span><span class="sxs-lookup"><span data-stu-id="85a2f-108">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="85a2f-109">Como esse cmdlet interrompe os processos do sistema, ele usa o verbo "Stop", definido pela classe [System. Management. Automation. Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) , com o substantivo "proc" para indicar o processo.</span><span class="sxs-lookup"><span data-stu-id="85a2f-109">Because this cmdlet stops system processes, it uses the verb "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate process.</span></span> <span data-ttu-id="85a2f-110">Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="85a2f-110">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="85a2f-111">O código a seguir é a definição de classe para este Stop-Proc cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85a2f-111">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="85a2f-112">Definindo parâmetros para a modificação do sistema</span><span class="sxs-lookup"><span data-stu-id="85a2f-112">Defining Parameters for System Modification</span></span>

<span data-ttu-id="85a2f-113">Seu cmdlet precisa definir parâmetros que dão suporte a modificações do sistema e comentários do usuário.</span><span class="sxs-lookup"><span data-stu-id="85a2f-113">Your cmdlet needs to define parameters that support system modifications and user feedback.</span></span> <span data-ttu-id="85a2f-114">O cmdlet deve definir um `Name` parâmetro ou equivalente para que o cmdlet possa modificar o sistema por algum tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="85a2f-114">The cmdlet should define a `Name` parameter or equivalent so that the cmdlet will be able to modify the system by some sort of identifier.</span></span> <span data-ttu-id="85a2f-115">Além disso, o cmdlet deve definir os `Force` `PassThru` parâmetros e.</span><span class="sxs-lookup"><span data-stu-id="85a2f-115">In addition, the cmdlet should define the `Force` and `PassThru` parameters.</span></span> <span data-ttu-id="85a2f-116">Para obter mais informações sobre esses parâmetros, consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="85a2f-116">For more information about these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="defining-a-parameter-alias"></a><span data-ttu-id="85a2f-117">Definindo um alias de parâmetro</span><span class="sxs-lookup"><span data-stu-id="85a2f-117">Defining a Parameter Alias</span></span>

<span data-ttu-id="85a2f-118">Um alias de parâmetro pode ser um nome alternativo ou um nome curto bem definido de 1 letra ou de duas letras para um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85a2f-118">A parameter alias can be an alternate name or a well-defined 1-letter or 2-letter short name for a cmdlet parameter.</span></span> <span data-ttu-id="85a2f-119">Em ambos os casos, a meta de usar aliases é simplificar a entrada do usuário na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="85a2f-119">In both cases, the goal of using aliases is to simplify user entry from the command line.</span></span> <span data-ttu-id="85a2f-120">O Windows PowerShell dá suporte a aliases de parâmetro por meio do atributo [System. Management. Automation. AliasAttribute](/dotnet/api/System.Management.Automation.AliasAttribute) , que usa a sintaxe de declaração [alias ()].</span><span class="sxs-lookup"><span data-stu-id="85a2f-120">Windows PowerShell supports parameter aliases through the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, which uses the declaration syntax [Alias()].</span></span>

<span data-ttu-id="85a2f-121">O código a seguir mostra como um alias é adicionado ao `Name` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="85a2f-121">The following code shows how an alias is added to the `Name` parameter.</span></span>

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

<span data-ttu-id="85a2f-122">Além de usar o atributo [System. Management. Automation. AliasAttribute](/dotnet/api/System.Management.Automation.AliasAttribute) , o tempo de execução do Windows PowerShell executa correspondência de nome parcial, mesmo que nenhum alias seja especificado.</span><span class="sxs-lookup"><span data-stu-id="85a2f-122">In addition to using the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, the Windows PowerShell runtime performs partial name matching, even if no aliases are specified.</span></span> <span data-ttu-id="85a2f-123">Por exemplo, se o cmdlet tiver um `FileName` parâmetro e esse for o único parâmetro que começa com `F` , o usuário poderá inserir `Filename` , `Filenam` , `File` , `Fi` ou `F` e ainda reconhecer a entrada como o `FileName` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="85a2f-123">For example, if your cmdlet has a `FileName` parameter and that is the only parameter that starts with `F`, the user could enter `Filename`, `Filenam`, `File`, `Fi`, or `F` and still recognize the entry as the `FileName` parameter.</span></span>

## <a name="creating-help-for-parameters"></a><span data-ttu-id="85a2f-124">Criando ajuda para parâmetros</span><span class="sxs-lookup"><span data-stu-id="85a2f-124">Creating Help for Parameters</span></span>

<span data-ttu-id="85a2f-125">O Windows PowerShell permite que você crie ajuda para parâmetros de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85a2f-125">Windows PowerShell allows you to create Help for cmdlet parameters.</span></span> <span data-ttu-id="85a2f-126">Faça isso para qualquer parâmetro usado para modificação do sistema e comentários do usuário.</span><span class="sxs-lookup"><span data-stu-id="85a2f-126">Do this for any parameter used for system modification and user feedback.</span></span> <span data-ttu-id="85a2f-127">Para cada parâmetro para dar suporte à ajuda, você pode definir a `HelpMessage` palavra-chave Attribute na declaração de atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) .</span><span class="sxs-lookup"><span data-stu-id="85a2f-127">For each parameter to support Help, you can set the `HelpMessage` attribute keyword in the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="85a2f-128">Essa palavra-chave define o texto a ser exibido para o usuário para obter assistência no uso do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="85a2f-128">This keyword defines the text to display to the user for assistance in using the parameter.</span></span> <span data-ttu-id="85a2f-129">Você também pode definir a `HelpMessageBaseName` palavra-chave para identificar o nome de base de um recurso a ser usado para a mensagem.</span><span class="sxs-lookup"><span data-stu-id="85a2f-129">You can also set the `HelpMessageBaseName` keyword to identify the base name of a resource to use for the message.</span></span> <span data-ttu-id="85a2f-130">Se você definir essa palavra-chave, também deverá definir a `HelpMessageResourceId` palavra-chave para especificar o identificador de recurso.</span><span class="sxs-lookup"><span data-stu-id="85a2f-130">If you set this keyword, you must also set the `HelpMessageResourceId` keyword to specify the resource identifier.</span></span>

<span data-ttu-id="85a2f-131">O seguinte código desse cmdlet Stop-Proc define a `HelpMessage` palavra-chave Attribute para o `Name` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="85a2f-131">The following code from this Stop-Proc cmdlet defines the `HelpMessage` attribute keyword for the `Name` parameter.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="85a2f-132">Substituindo um método de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="85a2f-132">Overriding an Input Processing Method</span></span>

<span data-ttu-id="85a2f-133">O cmdlet deve substituir um método de processamento de entrada, com mais frequência ele será [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span><span class="sxs-lookup"><span data-stu-id="85a2f-133">Your cmdlet must override an input processing method, most often this will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="85a2f-134">Ao modificar o sistema, o cmdlet deve chamar os métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) para permitir que o usuário forneça comentários antes que uma alteração seja feita.</span><span class="sxs-lookup"><span data-stu-id="85a2f-134">When modifying the system, the cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to allow the user to provide feedback before a change is made.</span></span> <span data-ttu-id="85a2f-135">Para obter mais informações sobre esses métodos, consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="85a2f-135">For more information about these methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="supporting-wildcard-expansion"></a><span data-ttu-id="85a2f-136">Suporte à expansão de curinga</span><span class="sxs-lookup"><span data-stu-id="85a2f-136">Supporting Wildcard Expansion</span></span>

<span data-ttu-id="85a2f-137">Para permitir a seleção de vários objetos, o cmdlet pode usar as classes [System. Management. Automation. Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) e [System. Management. Automation. curingaoptions](/dotnet/api/System.Management.Automation.WildcardOptions) para fornecer suporte à expansão de curinga para a entrada de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="85a2f-137">To allow the selection of multiple objects, your cmdlet can use the [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) and [System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) classes to provide wildcard expansion support for parameter input.</span></span> <span data-ttu-id="85a2f-138">Exemplos de padrões de curinga são LSA \*, \* . txt e [a-c] \* .</span><span class="sxs-lookup"><span data-stu-id="85a2f-138">Examples of wildcard patterns are lsa\*, \*.txt, and [a-c]\*.</span></span> <span data-ttu-id="85a2f-139">Use o caractere de aspas (') como um caractere de escape quando o padrão contiver um caractere que deve ser usado literalmente.</span><span class="sxs-lookup"><span data-stu-id="85a2f-139">Use the back-quote character (\`) as an escape character when the pattern contains a character that should be used literally.</span></span>

<span data-ttu-id="85a2f-140">As expansões de curinga dos nomes de arquivo e caminho são exemplos de cenários comuns em que o cmdlet pode querer permitir suporte para entradas de caminho quando a seleção de vários objetos é necessária.</span><span class="sxs-lookup"><span data-stu-id="85a2f-140">Wildcard expansions of file and path names are examples of common scenarios where the cmdlet may want to allow support for path inputs when the selection of multiple objects is required.</span></span> <span data-ttu-id="85a2f-141">Um caso comum está no sistema de arquivos, em que um usuário deseja ver todos os arquivos que residem na pasta atual.</span><span class="sxs-lookup"><span data-stu-id="85a2f-141">A common case is in the file system, where a user wants to see all files residing in the current folder.</span></span>

<span data-ttu-id="85a2f-142">Você deve precisar de um padrão de caractere curinga personalizado somente para a implementação, raramente.</span><span class="sxs-lookup"><span data-stu-id="85a2f-142">You should need a customized wildcard pattern matching implementation only rarely.</span></span> <span data-ttu-id="85a2f-143">Nesse caso, o cmdlet deve dar suporte à especificação POSIX 1003,2, 3,13 completa para expansão de curinga ou o seguinte subconjunto simplificado:</span><span class="sxs-lookup"><span data-stu-id="85a2f-143">In this case, your cmdlet should support either the full POSIX 1003.2, 3.13 specification for wildcard expansion or the following simplified subset:</span></span>

- <span data-ttu-id="85a2f-144">**Ponto de interrogação (?).**</span><span class="sxs-lookup"><span data-stu-id="85a2f-144">**Question mark (?).**</span></span> <span data-ttu-id="85a2f-145">Corresponde a qualquer caractere no local especificado.</span><span class="sxs-lookup"><span data-stu-id="85a2f-145">Matches any character at the specified location.</span></span>

- <span data-ttu-id="85a2f-146">**Asterisco ( \* ).**</span><span class="sxs-lookup"><span data-stu-id="85a2f-146">**Asterisk (\*).**</span></span> <span data-ttu-id="85a2f-147">Corresponde a zero ou mais caracteres a partir do local especificado.</span><span class="sxs-lookup"><span data-stu-id="85a2f-147">Matches zero or more characters starting at the specified location.</span></span>

- <span data-ttu-id="85a2f-148">**Colchete de abertura ([).**</span><span class="sxs-lookup"><span data-stu-id="85a2f-148">**Open bracket ([).**</span></span> <span data-ttu-id="85a2f-149">Apresenta uma expressão de colchete de padrão que pode conter caracteres ou um intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="85a2f-149">Introduces a pattern bracket expression that can contain characters or a range of characters.</span></span> <span data-ttu-id="85a2f-150">Se um intervalo for necessário, um hífen (-) será usado para indicar o intervalo.</span><span class="sxs-lookup"><span data-stu-id="85a2f-150">If a range is required, a hyphen (-) is used to indicate the range.</span></span>

- <span data-ttu-id="85a2f-151">**Colchete de fechamento (]).**</span><span class="sxs-lookup"><span data-stu-id="85a2f-151">**Close bracket (]).**</span></span> <span data-ttu-id="85a2f-152">Termina uma expressão de colchete de padrão.</span><span class="sxs-lookup"><span data-stu-id="85a2f-152">Ends a pattern bracket expression.</span></span>

- <span data-ttu-id="85a2f-153">**Caractere de escape de aspas traseiras (').**</span><span class="sxs-lookup"><span data-stu-id="85a2f-153">**Back-quote escape character (\`).**</span></span> <span data-ttu-id="85a2f-154">Indica que o próximo caractere deve ser levado literalmente.</span><span class="sxs-lookup"><span data-stu-id="85a2f-154">Indicates that the next character should be taken literally.</span></span> <span data-ttu-id="85a2f-155">Lembre-se de que ao especificar o caractere de aspas invertidas na linha de comando (em vez de especificá-lo de forma programática), o caractere de escape de aspas traseiras deve ser especificado duas vezes.</span><span class="sxs-lookup"><span data-stu-id="85a2f-155">Be aware that when specifying the back-quote character from the command line (as opposed to specifying it programmatically), the back-quote escape character must be specified twice.</span></span>

> [!NOTE]
> <span data-ttu-id="85a2f-156">Para obter mais informações sobre padrões de curinga, consulte [suportando curingas em parâmetros de cmdlet](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="85a2f-156">For more information about wildcard patterns, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span></span>

<span data-ttu-id="85a2f-157">O código a seguir mostra como definir opções de curinga e definir o padrão curinga usado para resolver o `Name` parâmetro para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85a2f-157">The following code shows how to set wildcard options and define the wildcard pattern used for resolving the `Name` parameter for this cmdlet.</span></span>

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

<span data-ttu-id="85a2f-158">O código a seguir mostra como testar se o nome do processo corresponde ao padrão curinga definido.</span><span class="sxs-lookup"><span data-stu-id="85a2f-158">The following code shows how to test whether the process name matches the defined wildcard pattern.</span></span> <span data-ttu-id="85a2f-159">Observe que, nesse caso, se o nome do processo não corresponder ao padrão, o cmdlet continuará para obter o próximo nome do processo.</span><span class="sxs-lookup"><span data-stu-id="85a2f-159">Notice that, in this case, if the process name does not match the pattern, the cmdlet continues on to get the next process name.</span></span>

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a><span data-ttu-id="85a2f-160">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="85a2f-160">Code Sample</span></span>

<span data-ttu-id="85a2f-161">Para obter o código de exemplo completo em C#, consulte [exemplo de StopProcessSample03](./stopprocesssample03-sample.md).</span><span class="sxs-lookup"><span data-stu-id="85a2f-161">For the complete C# sample code, see [StopProcessSample03 Sample](./stopprocesssample03-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="85a2f-162">Definir tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="85a2f-162">Define Object Types and Formatting</span></span>

<span data-ttu-id="85a2f-163">O Windows PowerShell passa informações entre os cmdlets usando objetos .net.</span><span class="sxs-lookup"><span data-stu-id="85a2f-163">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="85a2f-164">Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85a2f-164">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="85a2f-165">Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="85a2f-165">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="85a2f-166">Criando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="85a2f-166">Building the Cmdlet</span></span>

<span data-ttu-id="85a2f-167">Depois de implementar um cmdlet, ele deve ser registrado com o Windows PowerShell por meio de um snap-in do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85a2f-167">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="85a2f-168">Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="85a2f-168">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="85a2f-169">Testando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="85a2f-169">Testing the Cmdlet</span></span>

<span data-ttu-id="85a2f-170">Quando o cmdlet tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando-o na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="85a2f-170">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="85a2f-171">Vamos testar o cmdlet Stop-Proc de exemplo.</span><span class="sxs-lookup"><span data-stu-id="85a2f-171">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="85a2f-172">Para obter mais informações sobre como usar cmdlets na linha de comando, consulte o [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="85a2f-172">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="85a2f-173">Inicie o Windows PowerShell e use Stop-Proc para interromper um processo usando o alias ProcessName para o `Name` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="85a2f-173">Start Windows PowerShell and use Stop-Proc to stop a process using the ProcessName alias for the `Name` parameter.</span></span>

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

    <span data-ttu-id="85a2f-174">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="85a2f-174">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="85a2f-175">Faça a seguinte entrada na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="85a2f-175">Make the following entry on the command line.</span></span> <span data-ttu-id="85a2f-176">Como o parâmetro Name é obrigatório, você será solicitado a fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="85a2f-176">Because the Name parameter is mandatory, you are prompted for it.</span></span> <span data-ttu-id="85a2f-177">Inserindo "!?"</span><span class="sxs-lookup"><span data-stu-id="85a2f-177">Entering "!?"</span></span> <span data-ttu-id="85a2f-178">Abre o texto de ajuda associado ao parâmetro.</span><span class="sxs-lookup"><span data-stu-id="85a2f-178">brings up the help text associated with the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

    <span data-ttu-id="85a2f-179">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="85a2f-179">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- <span data-ttu-id="85a2f-180">Agora, faça a seguinte entrada parar todos os processos que correspondam ao padrão de curinga "\* observação \* ".</span><span class="sxs-lookup"><span data-stu-id="85a2f-180">Now make the following entry to stop all processes that match the wildcard pattern "\*note\*".</span></span> <span data-ttu-id="85a2f-181">Você será solicitado antes de parar cada processo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="85a2f-181">You are prompted before stopping each process that matches the pattern.</span></span>

    ```powershell
    PS> stop-proc -Name *note*
    ```

    <span data-ttu-id="85a2f-182">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="85a2f-182">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

    <span data-ttu-id="85a2f-183">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="85a2f-183">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

    <span data-ttu-id="85a2f-184">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="85a2f-184">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="85a2f-185">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="85a2f-185">See Also</span></span>

[<span data-ttu-id="85a2f-186">Criar um cmdlet que modifica o sistema</span><span class="sxs-lookup"><span data-stu-id="85a2f-186">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="85a2f-187">Como criar um cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="85a2f-187">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="85a2f-188">[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="85a2f-188">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="85a2f-189">[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="85a2f-189">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="85a2f-190">Suporte a curingas em parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="85a2f-190">Supporting Wildcards in Cmdlet Parameters</span></span>](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[<span data-ttu-id="85a2f-191">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="85a2f-191">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
