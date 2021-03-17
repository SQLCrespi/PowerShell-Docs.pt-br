---
description: Descreve como usar métodos para executar ações em objetos no PowerShell.
Locale: en-US
ms.date: 03/15/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_methods?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Methods
ms.openlocfilehash: 9c94de53bf320074c5b8aed1d1670fdd53d6b105
ms.sourcegitcommit: 15f759ca68d17acecab46b52250298d4f2037c4d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2021
ms.locfileid: "103575603"
---
# <a name="about-methods"></a><span data-ttu-id="1ddf5-103">Sobre métodos</span><span class="sxs-lookup"><span data-stu-id="1ddf5-103">About methods</span></span>

## <a name="short-description"></a><span data-ttu-id="1ddf5-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="1ddf5-104">Short description</span></span>
<span data-ttu-id="1ddf5-105">Descreve como usar métodos para executar ações em objetos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-105">Describes how to use methods to perform actions on objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="1ddf5-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="1ddf5-106">Long description</span></span>

<span data-ttu-id="1ddf5-107">O PowerShell usa objetos para representar os itens em armazenamentos de dados ou o estado do computador.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-107">PowerShell uses objects to represent the items in data stores or the state of the computer.</span></span> <span data-ttu-id="1ddf5-108">Por exemplo, os objetos FileInfo representam os arquivos em unidades do sistema de arquivos e os objetos ProcessInfo representam os processos no computador.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-108">For example, FileInfo objects represent the files in file system drives and ProcessInfo objects represent the processes on the computer.</span></span>

<span data-ttu-id="1ddf5-109">Os objetos têm propriedades, que armazenam dados sobre o objeto e métodos que permitem alterar o objeto.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-109">Objects have properties, which store data about the object, and methods that let you change the object.</span></span>

<span data-ttu-id="1ddf5-110">Um "método" é um conjunto de instruções que especificam uma ação que você pode executar no objeto.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-110">A "method" is a set of instructions that specify an action you can perform on the object.</span></span> <span data-ttu-id="1ddf5-111">Por exemplo, o `FileInfo` objeto inclui o `CopyTo` método que copia o arquivo que o `FileInfo` objeto representa.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-111">For example, the `FileInfo` object includes the `CopyTo` method that copies the file that the `FileInfo` object represents.</span></span>

<span data-ttu-id="1ddf5-112">Para obter os métodos de qualquer objeto, use o `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-112">To get the methods of any object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="1ddf5-113">Use sua propriedade **MemberType** com um valor de "Method".</span><span class="sxs-lookup"><span data-stu-id="1ddf5-113">Use its **MemberType** property with a value of "Method".</span></span> <span data-ttu-id="1ddf5-114">O comando a seguir obtém os métodos de objetos de processo.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-114">The following command gets the methods of process objects.</span></span>

```powershell
Get-Process | Get-Member -MemberType Method
```

```Output
TypeName: System.Diagnostics.Process

Name                      MemberType Definition
----                      ---------- ----------
BeginErrorReadLine        Method     System.Void BeginErrorReadLine()
BeginOutputReadLine       Method     System.Void BeginOutputReadLine()
...
Kill                      Method     System.Void Kill()
Refresh                   Method     System.Void Refresh()
Start                     Method     bool Start()
ToString                  Method     string ToString()
WaitForExit               Method     bool WaitForExit(int milliseconds), ...
WaitForInputIdle          Method     bool WaitForInputIdle(int millisecon...
```

<span data-ttu-id="1ddf5-115">Para executar ou "invocar" um método de um objeto, digite um ponto (.), o nome do método e um conjunto de parênteses "()".</span><span class="sxs-lookup"><span data-stu-id="1ddf5-115">To perform or "invoke" a method of an object, type a dot (.), the method name, and a set of parentheses "()".</span></span> <span data-ttu-id="1ddf5-116">Se o método tiver argumentos, coloque os valores de argumento dentro dos parênteses.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-116">If the method has arguments, place the argument values inside the parentheses.</span></span> <span data-ttu-id="1ddf5-117">Os parênteses são necessários para cada chamada de método, mesmo quando não há argumentos.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-117">The parentheses are required for every method call, even when there are no arguments.</span></span> <span data-ttu-id="1ddf5-118">Se o método usar vários argumentos, eles deverão ser separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-118">If the method takes multiple arguments, they should be separated by commas.</span></span>

<span data-ttu-id="1ddf5-119">Por exemplo, o comando a seguir invoca o método Kill de processos para encerrar o processo do bloco de notas no computador.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-119">For example, the following command invokes the Kill method of processes to end the Notepad process on the computer.</span></span>

```powershell
$notepad = Get-Process notepad
$notepad.Kill()
```

<span data-ttu-id="1ddf5-120">Este exemplo pode ser reduzido com a combinação das instruções acima.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-120">This example can be shortened by combining the above statements.</span></span>

```powershell
(Get-Process Notepad).Kill()
```

<span data-ttu-id="1ddf5-121">O `Get-Process` comando é colocado entre parênteses para garantir que ele seja executado antes que o método Kill seja invocado.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-121">The `Get-Process` command is enclosed in parentheses to ensure that it runs before the Kill method is invoked.</span></span> <span data-ttu-id="1ddf5-122">O `Kill` método é invocado no objeto retornado `Process` .</span><span class="sxs-lookup"><span data-stu-id="1ddf5-122">The `Kill` method is then invoked on the returned `Process` object.</span></span>

<span data-ttu-id="1ddf5-123">Outro método muito útil é o `Replace` método de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-123">Another very useful method is the `Replace` method of strings.</span></span> <span data-ttu-id="1ddf5-124">O `Replace` método substitui o texto em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-124">The `Replace` method, replaces text within a string.</span></span> <span data-ttu-id="1ddf5-125">No exemplo a seguir, o ponto (.) pode ser colocado imediatamente após a aspa de término da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-125">In the example below, the dot (.) can be placed immediately after the end quote of the string.</span></span>

```powershell
'this is rocket science'.Replace('rocket', 'rock')
```

```Output
this is rock science
```

<span data-ttu-id="1ddf5-126">Conforme mostrado nos exemplos anteriores, você pode invocar um método em um objeto que você obtém usando um comando, um objeto em uma variável ou qualquer coisa que resulte em um objeto (como uma cadeia de caracteres entre aspas).</span><span class="sxs-lookup"><span data-stu-id="1ddf5-126">As shown in the previous examples, you can invoke a method on an object that you get by using a command, an object in a variable, or anything that results in an object (like a string in quotes).</span></span>

<span data-ttu-id="1ddf5-127">A partir do PowerShell 4,0, a invocação de método usando nomes de métodos dinâmicos é suportada.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-127">Starting in PowerShell 4.0, method invocation by using dynamic method names is supported.</span></span>

## <a name="learning-about-methods"></a><span data-ttu-id="1ddf5-128">Aprendendo sobre métodos</span><span class="sxs-lookup"><span data-stu-id="1ddf5-128">Learning about methods</span></span>

<span data-ttu-id="1ddf5-129">Para localizar definições dos métodos de um objeto, acesse o tópico da ajuda para o tipo de objeto e procure sua página de métodos.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-129">To find definitions of the methods of an object, go to help topic for the object type and look for its methods page.</span></span> <span data-ttu-id="1ddf5-130">Por exemplo, a página a seguir descreve os métodos de Process Objects [System. Diagnostics. Process](/dotnet/api/system.diagnostics.process#methods).</span><span class="sxs-lookup"><span data-stu-id="1ddf5-130">For example, the following page describes the methods of process objects [System.Diagnostics.Process](/dotnet/api/system.diagnostics.process#methods).</span></span>

<span data-ttu-id="1ddf5-131">Para determinar os argumentos de um método, examine a definição do método, que é como o diagrama de sintaxe de um cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-131">To determine the arguments of a method, review the method definition, which is like the syntax diagram of a PowerShell cmdlet.</span></span>

<span data-ttu-id="1ddf5-132">Uma definição de método pode ter uma ou mais assinaturas de método, que são como os conjuntos de parâmetros de cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-132">A method definition might have one or more method signatures, which are like the parameter sets of PowerShell cmdlets.</span></span> <span data-ttu-id="1ddf5-133">As assinaturas mostram todos os formatos válidos de comandos para invocar o método.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-133">The signatures show all of the valid formats of commands to invoke the method.</span></span>

<span data-ttu-id="1ddf5-134">Por exemplo, o `CopyTo` método da `FileInfo` classe contém as duas assinaturas de método a seguir:</span><span class="sxs-lookup"><span data-stu-id="1ddf5-134">For example, the `CopyTo` method of the `FileInfo` class contains the following two method signatures:</span></span>

```
    CopyTo(String destFileName)
    CopyTo(String destFileName, Boolean overwrite)
```

<span data-ttu-id="1ddf5-135">A primeira assinatura do método usa o nome do arquivo de destino (e um caminho).</span><span class="sxs-lookup"><span data-stu-id="1ddf5-135">The first method signature takes the destination file name (and a path).</span></span> <span data-ttu-id="1ddf5-136">O exemplo a seguir usa o primeiro `CopyTo` método para copiar o `Final.txt` arquivo para o `C:\Bin` diretório.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-136">The following example uses the first `CopyTo` method to copy the `Final.txt` file to the `C:\Bin` directory.</span></span>

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt")
```

> [!NOTE]
> <span data-ttu-id="1ddf5-137">Ao contrário do modo de _argumento_ do PowerShell, os métodos de objeto são executados no modo de _expressão_ , que é uma passagem para o .NET Framework no qual o PowerShell se baseia.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-137">Unlike PowerShell's _argument_ mode, object methods execute in _expression_ mode, which is a pass-through to the .NET framework that PowerShell is built on.</span></span> <span data-ttu-id="1ddf5-138">No modo de _expressão_ , argumentos **bareword** (cadeias de caracteres sem aspas) não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-138">In _expression_ mode **bareword** arguments (unquoted strings) are not allowed.</span></span> <span data-ttu-id="1ddf5-139">Você pode ver essa diferença ao usar um caminho como um parâmetro, versus o caminho como um argumento.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-139">You can see this difference when using a the path as a parameter, versus the path as an argument.</span></span> <span data-ttu-id="1ddf5-140">Você pode ler mais sobre os modos de análise no [about_Parsing](about_Parsing.md)</span><span class="sxs-lookup"><span data-stu-id="1ddf5-140">You can read more about parsing modes in [about_Parsing](about_Parsing.md)</span></span>

<span data-ttu-id="1ddf5-141">A assinatura do segundo método usa um nome de arquivo de destino e um valor booliano que determina se o arquivo de destino deve ser substituído, caso ele já exista.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-141">The second method signature takes a destination file name and a Boolean value that determines whether the destination file should be overwritten, if it already exists.</span></span>

<span data-ttu-id="1ddf5-142">O exemplo a seguir usa o segundo `CopyTo` método para copiar o `Final.txt` arquivo para o `C:\Bin` diretório e substituir os arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-142">The following example uses the second `CopyTo` method to copy the `Final.txt` file to the `C:\Bin` directory, and to overwrite existing files.</span></span>

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt", $true)
```

## <a name="methods-of-scalar-objects-and-collections"></a><span data-ttu-id="1ddf5-143">Métodos de coleções e objetos escalares</span><span class="sxs-lookup"><span data-stu-id="1ddf5-143">Methods of Scalar objects and Collections</span></span>

<span data-ttu-id="1ddf5-144">Os métodos de um objeto ("escalar") de um tipo específico geralmente são diferentes dos métodos de uma coleção de objetos do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-144">The methods of one ("scalar") object of a particular type are often different from the methods of a collection of objects of the same type.</span></span>

<span data-ttu-id="1ddf5-145">Por exemplo, cada processo tem um `Kill` método, mas uma coleção de processos não tem um método Kill.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-145">For example, every process has a `Kill` method, but a collection of processes does not have a Kill method.</span></span>

<span data-ttu-id="1ddf5-146">A partir do PowerShell 3,0, o PowerShell tenta evitar erros de script que resultam de diferentes métodos de coleções e objetos escalares.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-146">Beginning in PowerShell 3.0, PowerShell tries to prevent scripting errors that result from the differing methods of scalar objects and collections.</span></span>

<span data-ttu-id="1ddf5-147">Se você enviar uma coleção, mas solicitar um método que existe somente em objetos únicos ("escalares"), o PowerShell invocará o método em cada objeto na coleção.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-147">If you submit a collection, but request a method that exists only on single ("scalar") objects, PowerShell invokes the method on every object in the collection.</span></span>

<span data-ttu-id="1ddf5-148">Se o método existir nos objetos individuais e na coleção, somente o método da coleção será invocado.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-148">If the method exists on the individual objects and on the collection, only the collection's method is invoked.</span></span>

<span data-ttu-id="1ddf5-149">Esse recurso também funciona em Propriedades de coleções e objetos escalares.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-149">This feature also works on properties of scalar objects and collections.</span></span> <span data-ttu-id="1ddf5-150">Para obter mais informações, consulte [about_Properties](about_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="1ddf5-150">For more information, see [about_Properties](about_Properties.md).</span></span>

### <a name="examples"></a><span data-ttu-id="1ddf5-151">Exemplos</span><span class="sxs-lookup"><span data-stu-id="1ddf5-151">Examples</span></span>

<span data-ttu-id="1ddf5-152">O exemplo a seguir executa o método **Kill** de objetos de processo individuais em uma coleção de objetos.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-152">The following example runs the **Kill** method of individual process objects in a collection of objects.</span></span>

<span data-ttu-id="1ddf5-153">O primeiro comando inicia três instâncias do processo do bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-153">The first command starts three instances of the Notepad process.</span></span> <span data-ttu-id="1ddf5-154">`Get-Process` Obtém todas as três instâncias do processo do bloco de notas e as salva na `$p` variável.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-154">`Get-Process` gets all three instance of the Notepad process and saves them in the `$p` variable.</span></span>

```powershell
Notepad; Notepad; Notepad
$p = Get-Process Notepad
$p.Count
```

```Output
3
```

<span data-ttu-id="1ddf5-155">O comando a seguir executa o método **Kill** em todos os três processos na `$p` variável.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-155">The next command runs the **Kill** method on all three processes in the `$p` variable.</span></span> <span data-ttu-id="1ddf5-156">Esse comando funciona mesmo que uma coleção de processos não tenha um `Kill` método.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-156">This command works even though a collection of processes does not have a `Kill` method.</span></span>

```powershell
$p.Kill()
Get-Process Notepad
```

<span data-ttu-id="1ddf5-157">O `Get-Process` comando confirma que o `Kill` método funcionou.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-157">The `Get-Process` command confirms that the `Kill` method worked.</span></span>

```Output
Get-Process : Cannot find a process with the name "notepad". Verify the proc
ess name and call the cmdlet again.
At line:1 char:12
+ Get-Process <<<<  notepad
    + CategoryInfo          : ObjectNotFound: (notepad:String) [Get-Process]
, ProcessCommandException
    + FullyQualifiedErrorId : NoProcessFoundForGivenName,Microsoft.PowerShel
l.Commands.GetProcessCommand
```

<span data-ttu-id="1ddf5-158">Este exemplo é funcionalmente equivalente a usar o `Foreach-Object` cmdlet para executar o método em cada objeto na coleção.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-158">This example is functionally equivalent to using the `Foreach-Object` cmdlet to run the method on each object in the collection.</span></span>

```powershell
$p | ForEach-Object {$_.Kill()}
```

### <a name="foreach-and-where-methods"></a><span data-ttu-id="1ddf5-159">Métodos ForEach e where</span><span class="sxs-lookup"><span data-stu-id="1ddf5-159">ForEach and Where methods</span></span>

<span data-ttu-id="1ddf5-160">A partir do PowerShell 4,0, há suporte para a filtragem de coleção usando uma sintaxe de método.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-160">Beginning in PowerShell 4.0, collection filtering using a method syntax is supported.</span></span> <span data-ttu-id="1ddf5-161">Isso permite o uso de dois novos métodos ao lidar com coleções `ForEach` e `Where` .</span><span class="sxs-lookup"><span data-stu-id="1ddf5-161">This allows use of two new methods when dealing with collections `ForEach` and `Where`.</span></span>

<span data-ttu-id="1ddf5-162">Leia mais sobre esses métodos em [about_arrays](about_arrays.md)</span><span class="sxs-lookup"><span data-stu-id="1ddf5-162">You can read more about these methods in [about_arrays](about_arrays.md)</span></span>

## <a name="calling-a-specific-method-when-multiple-overloads-exist"></a><span data-ttu-id="1ddf5-163">Chamando um método específico quando há várias sobrecargas</span><span class="sxs-lookup"><span data-stu-id="1ddf5-163">Calling a specific method when multiple overloads exist</span></span>

<span data-ttu-id="1ddf5-164">Considere o cenário a seguir ao chamar métodos .NET.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-164">Consider the following scenario when calling .NET methods.</span></span> <span data-ttu-id="1ddf5-165">Se um método usa um objeto, mas tem uma sobrecarga por meio de uma interface usando um tipo mais específico, o PowerShell escolhe o método que aceita o objeto, a menos que você o converta explicitamente nessa interface.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-165">If a method takes an object but has an overload via an interface taking a more specific type, PowerShell chooses the method that accepts the object unless you explicitly cast it to that interface.</span></span>

```powershell
Add-Type -TypeDefinition @'

   // Interface
   public interface IFoo {
     string Bar(int p);
   }

   // Type that implements the interface
   public class Foo : IFoo {

   // Direct member method named 'Bar'
   public string Bar(object p) { return $"object: {p}"; }

   // *Explicit* implementation of IFoo's 'Bar' method().
   string IFoo.Bar(int p) {
       return $"int: {p}";
   }

}
'@
```

<span data-ttu-id="1ddf5-166">Neste exemplo, a sobrecarga menos específica `object` do método **bar** foi escolhida.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-166">In this example the less specific `object` overload of the **Bar** method was chosen.</span></span>

```powershell
[Foo]::new().Bar(1)
```

```Output
object: 1
```

<span data-ttu-id="1ddf5-167">Neste exemplo, vamos converter o método para a interface **IFoo** para selecionar a sobrecarga mais específica do método **bar** .</span><span class="sxs-lookup"><span data-stu-id="1ddf5-167">In this example we cast the method to the interface **IFoo** to select the more specific overload of the **Bar** method.</span></span>

```powershell
([IFoo] [Foo]::new()).Bar(1)
```

```Output
int: 1
```

## <a name="using-net-methods-that-take-filesystem-paths"></a><span data-ttu-id="1ddf5-168">Usando métodos .NET que usam caminhos do sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="1ddf5-168">Using .NET methods that take filesystem paths</span></span>

<span data-ttu-id="1ddf5-169">O PowerShell dá suporte a vários Runspaces por processo.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-169">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="1ddf5-170">Cada runspace tem seu próprio _diretório atual_.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-170">Each runspace has its own _current directory_.</span></span> <span data-ttu-id="1ddf5-171">Isso não é o mesmo que o diretório de trabalho do processo atual: `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="1ddf5-171">This is not the same as the working directory of the current process: `[System.Environment]::CurrentDirectory`.</span></span>

<span data-ttu-id="1ddf5-172">Os métodos do .NET usam o diretório de trabalho do processo.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-172">.NET methods use the process working directory.</span></span> <span data-ttu-id="1ddf5-173">Os cmdlets do PowerShell usam o local do runspace.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-173">PowerShell cmdlets use the Runspace location.</span></span> <span data-ttu-id="1ddf5-174">Além disso, os métodos .NET só funcionam com caminhos de sistema de arquivos nativos, não com objetos de caminho do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-174">Also, .NET methods only work with native filesystem paths, not PowerShell Path objects.</span></span> <span data-ttu-id="1ddf5-175">Para usar caminhos do PowerShell com métodos .NET, você deve resolver o caminho para um caminho nativo do sistema de arquivos antes de passá-lo para o método .NET.</span><span class="sxs-lookup"><span data-stu-id="1ddf5-175">To use PowerShell paths with .NET methods, you must resolve the path to a filesystem-native path before passing it to the .NET method.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ddf5-176">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1ddf5-176">See Also</span></span>

[<span data-ttu-id="1ddf5-177">about_Objects</span><span class="sxs-lookup"><span data-stu-id="1ddf5-177">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="1ddf5-178">about_Properties</span><span class="sxs-lookup"><span data-stu-id="1ddf5-178">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="1ddf5-179">Get-Member</span><span class="sxs-lookup"><span data-stu-id="1ddf5-179">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)
