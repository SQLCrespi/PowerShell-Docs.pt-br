---
ms.date: 09/13/2016
ms.topic: reference
title: Criar um cmdlet sem parâmetros
description: Criar um cmdlet sem parâmetros
ms.openlocfilehash: 5df27ac4c1f6dfcc3e7596d93f8db0f97aae71c1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646542"
---
# <a name="creating-a-cmdlet-without-parameters"></a><span data-ttu-id="9c68e-103">Criar um cmdlet sem parâmetros</span><span class="sxs-lookup"><span data-stu-id="9c68e-103">Creating a Cmdlet without Parameters</span></span>

<span data-ttu-id="9c68e-104">Esta seção descreve como criar um cmdlet que recupera informações do computador local sem o uso de parâmetros e, em seguida, grava as informações no pipeline.</span><span class="sxs-lookup"><span data-stu-id="9c68e-104">This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span> <span data-ttu-id="9c68e-105">O cmdlet descrito aqui é um cmdlet Get-Proc que recupera informações sobre os processos do computador local e, em seguida, exibe essas informações na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="9c68e-105">The cmdlet described here is a Get-Proc cmdlet that retrieves information about the processes of the local computer, and then displays that information at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="9c68e-106">Lembre-se de que, ao escrever cmdlets, os assemblies de referência do Windows PowerShell® são baixados no disco (por padrão, em C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0).</span><span class="sxs-lookup"><span data-stu-id="9c68e-106">Be aware that when writing cmdlets, the Windows PowerShell® reference assemblies are downloaded onto disk (by default at C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0).</span></span> <span data-ttu-id="9c68e-107">Eles não são instalados no GAC (cache de assembly global).</span><span class="sxs-lookup"><span data-stu-id="9c68e-107">They are not installed in the Global Assembly Cache (GAC).</span></span>

## <a name="naming-the-cmdlet"></a><span data-ttu-id="9c68e-108">Nomeando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="9c68e-108">Naming the Cmdlet</span></span>

<span data-ttu-id="9c68e-109">Um nome de cmdlet consiste em um verbo que indica a ação que o cmdlet usa e um substantivo que indica os itens que o cmdlet atua.</span><span class="sxs-lookup"><span data-stu-id="9c68e-109">A cmdlet name consists of a verb that indicates the action the cmdlet takes and a noun that indicates the items that the cmdlet acts upon.</span></span> <span data-ttu-id="9c68e-110">Como esse cmdlet de Get-Proc de exemplo recupera objetos de processo, ele usa o verbo "Get", definido pela enumeração [System. Management. Automation. Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) e o substantivo "proc" para indicar que o cmdlet funciona em itens de processo.</span><span class="sxs-lookup"><span data-stu-id="9c68e-110">Because this sample Get-Proc cmdlet retrieves process objects, it uses the verb "Get", defined by the [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) enumeration, and the noun "Proc" to indicate that the cmdlet works on process items.</span></span>

<span data-ttu-id="9c68e-111">Ao nomear cmdlets, não use nenhum dos seguintes caracteres: #, () {} [] &-/\ $;: "' <> &#124; ?</span><span class="sxs-lookup"><span data-stu-id="9c68e-111">When naming cmdlets, do not use any of the following characters: # , () {} [] & - /\ $ ; : " '<> &#124; ?</span></span> <span data-ttu-id="9c68e-112">@ \` .</span><span class="sxs-lookup"><span data-stu-id="9c68e-112">@ \` .</span></span>

### <a name="choosing-a-noun"></a><span data-ttu-id="9c68e-113">Escolhendo um substantivo</span><span class="sxs-lookup"><span data-stu-id="9c68e-113">Choosing a Noun</span></span>

<span data-ttu-id="9c68e-114">Você deve escolher um substantivo específico.</span><span class="sxs-lookup"><span data-stu-id="9c68e-114">You should choose a noun that is specific.</span></span> <span data-ttu-id="9c68e-115">É melhor usar um substantivo singular prefixado com uma versão reduzida do nome do produto.</span><span class="sxs-lookup"><span data-stu-id="9c68e-115">It is best to use a singular noun prefixed with a shortened version of the product name.</span></span> <span data-ttu-id="9c68e-116">Um exemplo de nome de cmdlet desse tipo é " `Get-SQLServer` ".</span><span class="sxs-lookup"><span data-stu-id="9c68e-116">An example cmdlet name of this type is "`Get-SQLServer`".</span></span>

### <a name="choosing-a-verb"></a><span data-ttu-id="9c68e-117">Escolhendo um verbo</span><span class="sxs-lookup"><span data-stu-id="9c68e-117">Choosing a Verb</span></span>

<span data-ttu-id="9c68e-118">Você deve usar um verbo do conjunto de nomes de verbo de cmdlet aprovados.</span><span class="sxs-lookup"><span data-stu-id="9c68e-118">You should use a verb from the set of approved cmdlet verb names.</span></span> <span data-ttu-id="9c68e-119">Para obter mais informações sobre os verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="9c68e-119">For more information about the approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="9c68e-120">Definindo a classe do cmdlet</span><span class="sxs-lookup"><span data-stu-id="9c68e-120">Defining the Cmdlet Class</span></span>

<span data-ttu-id="9c68e-121">Depois de escolher um nome de cmdlet, defina uma classe .NET para implementar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c68e-121">Once you have chosen a cmdlet name, define a .NET class to implement the cmdlet.</span></span> <span data-ttu-id="9c68e-122">Aqui está a definição de classe para este exemplo de Get-Proc cmdlet:</span><span class="sxs-lookup"><span data-stu-id="9c68e-122">Here is the class definition for this sample Get-Proc cmdlet:</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

<span data-ttu-id="9c68e-123">Observe que, antes da definição de classe, o atributo [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) , com a sintaxe `[Cmdlet(verb, noun, ...)]` , é usado para identificar essa classe como um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c68e-123">Notice that previous to the class definition, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute, with the syntax `[Cmdlet(verb, noun, ...)]`, is used to identify this class as a cmdlet.</span></span> <span data-ttu-id="9c68e-124">Esse é o único atributo necessário para todos os cmdlets e permite que o tempo de execução do Windows PowerShell os chame corretamente.</span><span class="sxs-lookup"><span data-stu-id="9c68e-124">This is the only required attribute for all cmdlets, and it allows the Windows PowerShell runtime to call them correctly.</span></span> <span data-ttu-id="9c68e-125">Você pode definir palavras-chave de atributo para declarar ainda mais a classe, se necessário.</span><span class="sxs-lookup"><span data-stu-id="9c68e-125">You can set attribute keywords to further declare the class if necessary.</span></span> <span data-ttu-id="9c68e-126">Lembre-se de que a declaração de atributo para nossa classe GetProcCommand de exemplo declara apenas os nomes de substantivo e verbo para o cmdlet Get-Proc.</span><span class="sxs-lookup"><span data-stu-id="9c68e-126">Be aware that the attribute declaration for our sample GetProcCommand class declares only the noun and verb names for the Get-Proc cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="9c68e-127">Para todas as classes de atributo do Windows PowerShell, as palavras-chave que você pode definir correspondem às propriedades da classe de atributo.</span><span class="sxs-lookup"><span data-stu-id="9c68e-127">For all Windows PowerShell attribute classes, the keywords that you can set correspond to properties of the attribute class.</span></span>

<span data-ttu-id="9c68e-128">Ao nomear a classe do cmdlet, é uma prática recomendada refletir o nome do cmdlet no nome da classe.</span><span class="sxs-lookup"><span data-stu-id="9c68e-128">When naming the class of the cmdlet, it is a good practice to reflect the cmdlet name in the class name.</span></span> <span data-ttu-id="9c68e-129">Para fazer isso, use o formato "VerbNounCommand" e substitua "verbo" e "substantivo" pelo verbo e pelo substantivo usados no nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c68e-129">To do this, use the form "VerbNounCommand" and replace "Verb" and "Noun" with the verb and noun used in the cmdlet name.</span></span> <span data-ttu-id="9c68e-130">Como é mostrado na definição de classe anterior, o cmdlet de Get-Proc de exemplo define uma classe chamada GetProcCommand, que deriva da classe base [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) .</span><span class="sxs-lookup"><span data-stu-id="9c68e-130">As is shown in the previous class definition, the sample Get-Proc cmdlet defines a class called GetProcCommand, which derives from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) base class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c68e-131">Se você quiser definir um cmdlet que acesse o tempo de execução do Windows PowerShell diretamente, sua classe do .NET deverá derivar da classe base [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .</span><span class="sxs-lookup"><span data-stu-id="9c68e-131">If you want to define a cmdlet that accesses the Windows PowerShell runtime directly, your .NET class should derive from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class.</span></span> <span data-ttu-id="9c68e-132">Para obter mais informações sobre essa classe, consulte [criando um cmdlet que define conjuntos de parâmetros](./adding-parameter-sets-to-a-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="9c68e-132">For more information about this class, see [Creating a Cmdlet that Defines Parameter Sets](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9c68e-133">A classe de um cmdlet deve ser explicitamente marcada como pública.</span><span class="sxs-lookup"><span data-stu-id="9c68e-133">The class for a cmdlet must be explicitly marked as public.</span></span> <span data-ttu-id="9c68e-134">As classes que não estiverem marcadas como públicas usarão como padrão o interno e não serão encontradas pelo tempo de execução do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c68e-134">Classes that are not marked as public will default to internal and will not be found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="9c68e-135">O Windows PowerShell usa o namespace [Microsoft. PowerShell. Commands](/dotnet/api/Microsoft.PowerShell.Commands) para suas classes de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c68e-135">Windows PowerShell uses the [Microsoft.PowerShell.Commands](/dotnet/api/Microsoft.PowerShell.Commands) namespace for its cmdlet classes.</span></span> <span data-ttu-id="9c68e-136">É recomendável posicionar suas classes de cmdlet em um namespace de comandos do seu namespace de API, por exemplo, XXX. PS. Commands.</span><span class="sxs-lookup"><span data-stu-id="9c68e-136">It is recommended to place your cmdlet classes in a Commands namespace of your API namespace, for example, xxx.PS.Commands.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="9c68e-137">Substituindo um método de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="9c68e-137">Overriding an Input Processing Method</span></span>

<span data-ttu-id="9c68e-138">A classe [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) fornece três métodos principais de processamento de entrada, pelo menos um dos quais seu cmdlet deve substituir.</span><span class="sxs-lookup"><span data-stu-id="9c68e-138">The [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class provides three main input processing methods, at least one of which your cmdlet must override.</span></span> <span data-ttu-id="9c68e-139">Para obter mais informações sobre como o Windows PowerShell processa registros, consulte [como o Windows PowerShell funciona](/previous-versions//ms714658(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="9c68e-139">For more information about how Windows PowerShell processes records, see [How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85)).</span></span>

<span data-ttu-id="9c68e-140">Para todos os tipos de entrada, o tempo de execução do Windows PowerShell chama [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) para habilitar o processamento.</span><span class="sxs-lookup"><span data-stu-id="9c68e-140">For all types of input, the Windows PowerShell runtime calls [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) to enable processing.</span></span> <span data-ttu-id="9c68e-141">Se o cmdlet precisar executar algum pré-processamento ou configuração, ele poderá fazer isso substituindo esse método.</span><span class="sxs-lookup"><span data-stu-id="9c68e-141">If your cmdlet must perform some preprocessing or setup, it can do this by overriding this method.</span></span>

> [!NOTE]
> <span data-ttu-id="9c68e-142">O Windows PowerShell usa o termo "registro" para descrever o conjunto de valores de parâmetro fornecidos quando um cmdlet é chamado.</span><span class="sxs-lookup"><span data-stu-id="9c68e-142">Windows PowerShell uses the term "record" to describe the set of parameter values supplied when a cmdlet is called.</span></span>

<span data-ttu-id="9c68e-143">Se o cmdlet aceitar a entrada do pipeline, ele deverá substituir o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) e, opcionalmente, o método [System. Management. Automation. cmdlet. endprocessor](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) .</span><span class="sxs-lookup"><span data-stu-id="9c68e-143">If your cmdlet accepts pipeline input, it must override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, and optionally the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="9c68e-144">Por exemplo, um cmdlet poderá substituir os dois métodos se ele reunir todas as entradas usando [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) e, em seguida, operar na entrada como um elemento inteiro, em vez de um Element de cada vez, como o `Sort-Object` cmdlet faz.</span><span class="sxs-lookup"><span data-stu-id="9c68e-144">For example, a cmdlet might override both methods if it gathers all input using [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) and then operates on the input as a whole rather than one element at a time, as the `Sort-Object` cmdlet does.</span></span>

<span data-ttu-id="9c68e-145">Se o cmdlet não receber a entrada do pipeline, ele deverá substituir o método [System. Management. Automation. cmdlet. Endprocessor](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) .</span><span class="sxs-lookup"><span data-stu-id="9c68e-145">If your cmdlet does not take pipeline input, it should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="9c68e-146">Lembre-se de que esse método é usado frequentemente no lugar de [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) quando o cmdlet não pode operar em um elemento por vez, como é o caso de um cmdlet de classificação.</span><span class="sxs-lookup"><span data-stu-id="9c68e-146">Be aware that this method is frequently used in place of [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) when the cmdlet cannot operate on one element at a time, as is the case for a sorting cmdlet.</span></span>

<span data-ttu-id="9c68e-147">Como este cmdlet de Get-Proc de exemplo deve receber a entrada do pipeline, ele substitui o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) e usa as implementações padrão para [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) e [System. Management. Automation. cmdlet. noprocessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing).</span><span class="sxs-lookup"><span data-stu-id="9c68e-147">Because this sample Get-Proc cmdlet must receive pipeline input, it overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method and uses the default implementations for [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) and [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing).</span></span> <span data-ttu-id="9c68e-148">A substituição [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) recupera os processos e os grava na linha de comando usando o método [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) .</span><span class="sxs-lookup"><span data-stu-id="9c68e-148">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override retrieves processes and writes them to the command line using the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Get the current processes
  Process[] processes = Process.GetProcesses();

  // Write the processes to the pipeline making them available
  // to the next cmdlet. The second parameter of this call tells
  // PowerShell to enumerate the array, and send one process at a
  // time to the pipeline.
  WriteObject(processes, true);
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ Get the current processes.
    Dim processes As Process()
    processes = Process.GetProcesses()

    '/ Write the processes to the pipeline making them available
    '/ to the next cmdlet. The second parameter of this call tells
    '/ PowerShell to enumerate the array, and send one process at a
    '/ time to the pipeline.
    WriteObject(processes, True)

End Sub 'ProcessRecord
```

#### <a name="things-to-remember-about-input-processing"></a><span data-ttu-id="9c68e-149">Coisas a serem lembradas sobre o processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="9c68e-149">Things to Remember About Input Processing</span></span>

- <span data-ttu-id="9c68e-150">A fonte padrão de entrada é um objeto explícito (por exemplo, uma cadeia de caracteres) fornecido pelo usuário na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="9c68e-150">The default source for input is an explicit object (for example, a string) provided by the user on the command line.</span></span> <span data-ttu-id="9c68e-151">Para obter mais informações, consulte [criando um cmdlet para processar a entrada de linha de comando](./adding-parameters-that-process-command-line-input.md).</span><span class="sxs-lookup"><span data-stu-id="9c68e-151">For more information, see [Creating a Cmdlet to Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>

- <span data-ttu-id="9c68e-152">Um método de processamento de entrada também pode receber entrada do objeto de saída de um cmdlet upstream no pipeline.</span><span class="sxs-lookup"><span data-stu-id="9c68e-152">An input processing method can also receive input from the output object of an upstream cmdlet on the pipeline.</span></span> <span data-ttu-id="9c68e-153">Para obter mais informações, consulte [criando um cmdlet para processar a entrada do pipeline](./adding-parameters-that-process-pipeline-input.md).</span><span class="sxs-lookup"><span data-stu-id="9c68e-153">For more information, see [Creating a Cmdlet to Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="9c68e-154">Lembre-se de que o cmdlet pode receber entrada de uma combinação de fontes de linha de comando e de pipeline.</span><span class="sxs-lookup"><span data-stu-id="9c68e-154">Be aware that your cmdlet can receive input from a combination of command-line and pipeline sources.</span></span>

- <span data-ttu-id="9c68e-155">O cmdlet downstream pode não retornar por muito tempo ou não deve ser retornado.</span><span class="sxs-lookup"><span data-stu-id="9c68e-155">The downstream cmdlet might not return for a long time, or not at all.</span></span> <span data-ttu-id="9c68e-156">Por esse motivo, o método de processamento de entrada em seu cmdlet não deve manter bloqueios durante chamadas para [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), especialmente bloqueios para os quais o escopo se estende além da instância do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c68e-156">For that reason, the input processing method in your cmdlet should not hold locks during calls to [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), especially locks for which the scope extends beyond the cmdlet instance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c68e-157">Os cmdlets devem nunca chamar [System. console. WriteLine \*](/dotnet/api/System.Console.WriteLine) ou seu equivalente.</span><span class="sxs-lookup"><span data-stu-id="9c68e-157">Cmdlets should never call [System.Console.Writeline\*](/dotnet/api/System.Console.WriteLine) or its equivalent.</span></span>

- <span data-ttu-id="9c68e-158">Seu cmdlet pode ter variáveis de objeto para limpeza quando termina o processamento (por exemplo, se abrir um identificador de arquivo no método [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) e manter o identificador aberto para uso por [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)).</span><span class="sxs-lookup"><span data-stu-id="9c68e-158">Your cmdlet might have object variables to clean up when it is finished processing (for example, if it opens a file handle in the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method and keeps the handle open for use by [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)).</span></span> <span data-ttu-id="9c68e-159">É importante lembrar que o tempo de execução do Windows PowerShell nem sempre chama o método [System. Management. Automation. cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) , que deve executar a limpeza de objeto.</span><span class="sxs-lookup"><span data-stu-id="9c68e-159">It is important to remember that the Windows PowerShell runtime does not always call the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method, which should perform object cleanup.</span></span>

<span data-ttu-id="9c68e-160">Por exemplo, [System. Management. Automation. cmdlet. endprocesso](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) não poderá ser chamado se o cmdlet for cancelado no Midway ou se um erro de encerramento ocorrer em qualquer parte do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c68e-160">For example, [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) might not be called if the cmdlet is canceled midway or if a terminating error occurs in any part of the cmdlet.</span></span> <span data-ttu-id="9c68e-161">Portanto, um cmdlet que exige a limpeza de objeto deve implementar o padrão [System. IDisposable](/dotnet/api/System.IDisposable) completo, incluindo o finalizador, para que o tempo de execução possa chamar o [System. Management. Automation. cmdlet. endprocessor](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) e [System. IDisposable. Dispose \*](/dotnet/api/System.IDisposable.Dispose) no final do processamento.</span><span class="sxs-lookup"><span data-stu-id="9c68e-161">Therefore, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including the finalizer, so that the runtime can call both [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) and [System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) at the end of processing.</span></span>

## <a name="code-sample"></a><span data-ttu-id="9c68e-162">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="9c68e-162">Code Sample</span></span>

<span data-ttu-id="9c68e-163">Para obter o código de exemplo completo em C#, consulte [exemplo de GetProcessSample01](./getprocesssample01-sample.md).</span><span class="sxs-lookup"><span data-stu-id="9c68e-163">For the complete C# sample code, see [GetProcessSample01 Sample](./getprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="9c68e-164">Definindo tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="9c68e-164">Defining Object Types and Formatting</span></span>

<span data-ttu-id="9c68e-165">O Windows PowerShell passa informações entre os cmdlets usando objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="9c68e-165">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="9c68e-166">Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c68e-166">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="9c68e-167">Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="9c68e-167">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="9c68e-168">Criando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="9c68e-168">Building the Cmdlet</span></span>

<span data-ttu-id="9c68e-169">Depois de implementar um cmdlet, você deve registrá-lo com o Windows PowerShell por meio de um snap-in do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c68e-169">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="9c68e-170">Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="9c68e-170">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="9c68e-171">Testando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="9c68e-171">Testing the Cmdlet</span></span>

<span data-ttu-id="9c68e-172">Quando o cmdlet tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando-o na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="9c68e-172">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="9c68e-173">O código para nosso cmdlet de Get-Proc de exemplo é pequeno, mas ele ainda usa o tempo de execução do Windows PowerShell e um objeto .NET existente, o que é suficiente para torná-lo útil.</span><span class="sxs-lookup"><span data-stu-id="9c68e-173">The code for our sample Get-Proc cmdlet is small, but it still uses the Windows PowerShell runtime and an existing .NET object, which is enough to make it useful.</span></span> <span data-ttu-id="9c68e-174">Vamos testá-lo para entender melhor o que Get-Proc pode fazer e como sua saída pode ser usada.</span><span class="sxs-lookup"><span data-stu-id="9c68e-174">Let's test it to better understand what Get-Proc can do and how its output can be used.</span></span> <span data-ttu-id="9c68e-175">Para obter mais informações sobre como usar cmdlets na linha de comando, consulte o [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9c68e-175">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

1. <span data-ttu-id="9c68e-176">Inicie o Windows PowerShell e obtenha os processos atuais em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="9c68e-176">Start Windows PowerShell, and get the current processes running on the computer.</span></span>

    ```powershell
    get-proc
    ```

    <span data-ttu-id="9c68e-177">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="9c68e-177">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. <span data-ttu-id="9c68e-178">Atribua uma variável aos resultados do cmdlet para facilitar a manipulação.</span><span class="sxs-lookup"><span data-stu-id="9c68e-178">Assign a variable to the cmdlet results for easier manipulation.</span></span>

    ```powershell
    $p=get-proc
    ```

3. <span data-ttu-id="9c68e-179">Obter o número de processos.</span><span class="sxs-lookup"><span data-stu-id="9c68e-179">Get the number of processes.</span></span>

    ```powershell
    $p.length
    ```

    <span data-ttu-id="9c68e-180">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="9c68e-180">The following output appears.</span></span>

    ```output
    63
    ```

4. <span data-ttu-id="9c68e-181">Recuperar um processo específico.</span><span class="sxs-lookup"><span data-stu-id="9c68e-181">Retrieve a specific process.</span></span>

    ```powershell
    $p[6]
    ```

    <span data-ttu-id="9c68e-182">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="9c68e-182">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. <span data-ttu-id="9c68e-183">Obtenha a hora de início desse processo.</span><span class="sxs-lookup"><span data-stu-id="9c68e-183">Get the start time of this process.</span></span>

    ```powershell
    $p[6].starttime
    ```

    <span data-ttu-id="9c68e-184">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="9c68e-184">The following output appears.</span></span>

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. <span data-ttu-id="9c68e-185">Obtenha os processos para os quais a contagem de identificador é maior que 500 e Classifique o resultado.</span><span class="sxs-lookup"><span data-stu-id="9c68e-185">Get the processes for which the handle count is greater than 500, and sort the result.</span></span>

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    <span data-ttu-id="9c68e-186">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="9c68e-186">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. <span data-ttu-id="9c68e-187">Use o `Get-Member` cmdlet para listar as propriedades disponíveis para cada processo.</span><span class="sxs-lookup"><span data-stu-id="9c68e-187">Use the `Get-Member` cmdlet to list the properties available for each process.</span></span>

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    <span data-ttu-id="9c68e-188">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="9c68e-188">The following output appears.</span></span>

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a><span data-ttu-id="9c68e-189">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9c68e-189">See Also</span></span>

[<span data-ttu-id="9c68e-190">Criando um cmdlet para processar a entrada de linha de comando</span><span class="sxs-lookup"><span data-stu-id="9c68e-190">Creating a Cmdlet to Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="9c68e-191">Criando um cmdlet para processar a entrada do pipeline</span><span class="sxs-lookup"><span data-stu-id="9c68e-191">Creating a Cmdlet to Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="9c68e-192">Como criar um cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c68e-192">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="9c68e-193">[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="9c68e-193">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="9c68e-194">[Como funciona o Windows PowerShell](/previous-versions//ms714658(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="9c68e-194">[How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85))</span></span>

<span data-ttu-id="9c68e-195">[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="9c68e-195">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="9c68e-196">Referência do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c68e-196">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="9c68e-197">Amostras de cmdlet</span><span class="sxs-lookup"><span data-stu-id="9c68e-197">Cmdlet Samples</span></span>](./cmdlet-samples.md)
