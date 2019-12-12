---
title: Adicionando parâmetros que processam a entrada de linha de comando | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmer's Guide], parameters
- Get-Proc cmdlet [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], command line input
- command line input [PowerShell Programmer's Guide]
- parameters [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], creating
ms.assetid: da0b32f8-7b51-440e-a061-3177b5759e0e
caps.latest.revision: 9
ms.openlocfilehash: 7db93af33717dc4802ed915793f6cd570cfb48f6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364625"
---
# <a name="adding-parameters-that-process-command-line-input"></a><span data-ttu-id="fabe1-102">Adicionar parâmetros que processam a entrada de linha de comando</span><span class="sxs-lookup"><span data-stu-id="fabe1-102">Adding Parameters That Process Command-Line Input</span></span>

<span data-ttu-id="fabe1-103">Uma fonte de entrada para um cmdlet é a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="fabe1-103">One source of input for a cmdlet is the command line.</span></span> <span data-ttu-id="fabe1-104">Este tópico descreve como adicionar um parâmetro ao cmdlet **Get-proc** (descrito em [criando seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md)) para que o cmdlet possa processar a entrada do computador local com base em objetos explícitos passados para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fabe1-104">This topic describes how to add a parameter to the **Get-Proc** cmdlet (which is described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process input from the local computer based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="fabe1-105">O cmdlet **Get-proc** descrito aqui recupera processos com base em seus nomes e, em seguida, exibe informações sobre os processos em um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="fabe1-105">The **Get-Proc** cmdlet described here retrieves processes based on their names, and then displays information about the processes at a command prompt.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="fabe1-106">Definindo a classe do cmdlet</span><span class="sxs-lookup"><span data-stu-id="fabe1-106">Defining the Cmdlet Class</span></span>

<span data-ttu-id="fabe1-107">A primeira etapa na criação de cmdlet é a nomenclatura de cmdlets e a declaração da classe .NET Framework que implementa o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fabe1-107">The first step in cmdlet creation is cmdlet naming and the declaration of the .NET Framework class that implements the cmdlet.</span></span> <span data-ttu-id="fabe1-108">Esse cmdlet recupera informações de processo, portanto, o nome do verbo escolhido aqui é "Get".</span><span class="sxs-lookup"><span data-stu-id="fabe1-108">This cmdlet retrieves process information, so the verb name chosen here is "Get."</span></span> <span data-ttu-id="fabe1-109">(Quase qualquer tipo de cmdlet capaz de recuperar informações pode processar a entrada de linha de comando.) Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="fabe1-109">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="fabe1-110">Aqui está a declaração de classe para o cmdlet **Get-proc** .</span><span class="sxs-lookup"><span data-stu-id="fabe1-110">Here's the class declaration for the **Get-Proc** cmdlet.</span></span> <span data-ttu-id="fabe1-111">Detalhes sobre essa definição são fornecidos na [criação do seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="fabe1-111">Details about this definition are provided in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="declaring-parameters"></a><span data-ttu-id="fabe1-112">Declarando parâmetros</span><span class="sxs-lookup"><span data-stu-id="fabe1-112">Declaring Parameters</span></span>

<span data-ttu-id="fabe1-113">Um parâmetro de cmdlet permite que o usuário forneça entrada para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fabe1-113">A cmdlet parameter enables the user to provide input to the cmdlet.</span></span> <span data-ttu-id="fabe1-114">No exemplo a seguir, **Get-proc** e `Get-Member` são os nomes dos cmdlets de pipeline e `MemberType` é um parâmetro para o cmdlet `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="fabe1-114">In the following example, **Get-Proc** and `Get-Member` are the names of pipelined cmdlets, and `MemberType` is a parameter for the `Get-Member` cmdlet.</span></span> <span data-ttu-id="fabe1-115">O parâmetro tem o argumento "Property".</span><span class="sxs-lookup"><span data-stu-id="fabe1-115">The parameter has the argument "property."</span></span>

<span data-ttu-id="fabe1-116">**PS > Get-proc; Propriedade `get-member`-MemberType**</span><span class="sxs-lookup"><span data-stu-id="fabe1-116">**PS> get-proc ; `get-member` -membertype property**</span></span>

<span data-ttu-id="fabe1-117">Para declarar parâmetros para um cmdlet, é preciso primeiro definir as propriedades que representam os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="fabe1-117">To declare parameters for a cmdlet, you must first define the properties that represent the parameters.</span></span> <span data-ttu-id="fabe1-118">No cmdlet **Get-proc** , o único parâmetro é `Name`, que nesse caso representa o nome do objeto de processo de .NET Framework a ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="fabe1-118">In the **Get-Proc** cmdlet, the only parameter is `Name`, which in this case represents the name of the .NET Framework process object to retrieve.</span></span> <span data-ttu-id="fabe1-119">Portanto, a classe cmdlet define uma propriedade do tipo cadeia de caracteres para aceitar uma matriz de nomes.</span><span class="sxs-lookup"><span data-stu-id="fabe1-119">Therefore, the cmdlet class defines a property of type string to accept an array of names.</span></span>

<span data-ttu-id="fabe1-120">Aqui está a declaração de parâmetro para o parâmetro `Name` do cmdlet **Get-proc** .</span><span class="sxs-lookup"><span data-stu-id="fabe1-120">Here's the parameter declaration for the `Name` parameter of the **Get-Proc** cmdlet.</span></span>

```csharp
/// <summary>
/// Specify the cmdlet Name parameter.
/// </summary>
  [Parameter(Position = 0)]
  [ValidateNotNullOrEmpty]
  public string[] Name
  {
    get { return processNames; }
    set { processNames = value; }
  }
  private string[] processNames;

  #endregion Parameters
```

```vb
<Parameter(Position:=0), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

<span data-ttu-id="fabe1-121">Para informar ao tempo de execução do Windows PowerShell que essa propriedade é o parâmetro `Name`, um atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) é adicionado à definição de propriedade.</span><span class="sxs-lookup"><span data-stu-id="fabe1-121">To inform the Windows PowerShell runtime that this property is the `Name` parameter, a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute is added to the property definition.</span></span> <span data-ttu-id="fabe1-122">A sintaxe básica para declarar esse atributo é `[Parameter()]`.</span><span class="sxs-lookup"><span data-stu-id="fabe1-122">The basic syntax for declaring this attribute is `[Parameter()]`.</span></span>

> [!NOTE]
> <span data-ttu-id="fabe1-123">Um parâmetro deve ser explicitamente marcado como público.</span><span class="sxs-lookup"><span data-stu-id="fabe1-123">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="fabe1-124">Parâmetros que não são marcados como padrão público para interno e não são encontrados pelo tempo de execução do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fabe1-124">Parameters that are not marked as public default to internal and are not found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="fabe1-125">Esse cmdlet usa uma matriz de cadeias de caracteres para o parâmetro `Name`.</span><span class="sxs-lookup"><span data-stu-id="fabe1-125">This cmdlet uses an array of strings for the `Name` parameter.</span></span> <span data-ttu-id="fabe1-126">Se possível, o cmdlet também deve definir um parâmetro como uma matriz, pois isso permite que o cmdlet aceite mais de um item.</span><span class="sxs-lookup"><span data-stu-id="fabe1-126">If possible, your cmdlet should also define a parameter as an array, because this allows the cmdlet to accept more than one item.</span></span>

#### <a name="things-to-remember-about-parameter-definitions"></a><span data-ttu-id="fabe1-127">Coisas a serem lembradas sobre definições de parâmetros</span><span class="sxs-lookup"><span data-stu-id="fabe1-127">Things to Remember About Parameter Definitions</span></span>

- <span data-ttu-id="fabe1-128">Os nomes de parâmetro e tipos de dados predefinidos do Windows PowerShell devem ser reutilizados o máximo possível para garantir que o cmdlet seja compatível com os cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fabe1-128">Predefined Windows PowerShell parameter names and data types should be reused as much as possible to ensure that your cmdlet is compatible with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="fabe1-129">Por exemplo, se todos os cmdlets usarem o nome de parâmetro `Id` predefinido para identificar um recurso, o usuário entenderá facilmente o significado do parâmetro, independentemente do cmdlet que estiver usando.</span><span class="sxs-lookup"><span data-stu-id="fabe1-129">For example, if all cmdlets use the predefined `Id` parameter name to identify a resource, user will easily understand the meaning of the parameter, regardless of what cmdlet they are using.</span></span> <span data-ttu-id="fabe1-130">Basicamente, os nomes de parâmetro seguem as mesmas regras que as usadas para nomes de variáveis no Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="fabe1-130">Basically, parameter names follow the same rules as those used for variable names in the common language runtime (CLR).</span></span> <span data-ttu-id="fabe1-131">Para obter mais informações sobre a nomenclatura de parâmetros, consulte [nomes de parâmetro de cmdlet](https://msdn.microsoft.com/en-us/c4500737-0a05-4d01-911b-394424c65bfb).</span><span class="sxs-lookup"><span data-stu-id="fabe1-131">For more information about parameter naming, see [Cmdlet Parameter Names](https://msdn.microsoft.com/en-us/c4500737-0a05-4d01-911b-394424c65bfb).</span></span>

- <span data-ttu-id="fabe1-132">O Windows PowerShell reserva alguns nomes de parâmetro para fornecer uma experiência de usuário consistente.</span><span class="sxs-lookup"><span data-stu-id="fabe1-132">Windows PowerShell reserves a few parameter names to provide a consistent user experience.</span></span> <span data-ttu-id="fabe1-133">Não use esses nomes de parâmetro: `WhatIf`, `Confirm`, `Verbose`, `Debug`, `Warn`, `ErrorAction`, `ErrorVariable`, `OutVariable`e `OutBuffer`.</span><span class="sxs-lookup"><span data-stu-id="fabe1-133">Do not use these parameter names: `WhatIf`, `Confirm`, `Verbose`, `Debug`, `Warn`, `ErrorAction`, `ErrorVariable`, `OutVariable`, and `OutBuffer`.</span></span> <span data-ttu-id="fabe1-134">Além disso, os aliases a seguir para esses nomes de parâmetro são reservados: `vb`, `db`, `ea`, `ev`, `ov`e `ob`.</span><span class="sxs-lookup"><span data-stu-id="fabe1-134">Additionally, the following aliases for these parameter names are reserved: `vb`, `db`, `ea`, `ev`, `ov`, and `ob`.</span></span>

- <span data-ttu-id="fabe1-135">`Name` é um nome de parâmetro simples e comum, recomendado para uso em seus cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fabe1-135">`Name` is a simple and common parameter name, recommended for use in your cmdlets.</span></span> <span data-ttu-id="fabe1-136">É melhor escolher um nome de parâmetro como este de um nome complexo que seja exclusivo para um cmdlet específico e difícil de lembrar.</span><span class="sxs-lookup"><span data-stu-id="fabe1-136">It is better to choose a parameter name like this than a complex name that is unique to a specific cmdlet and hard to remember.</span></span>

- <span data-ttu-id="fabe1-137">Os parâmetros não diferenciam maiúsculas de minúsculas no Windows PowerShell, embora por padrão o Shell preserve o caso.</span><span class="sxs-lookup"><span data-stu-id="fabe1-137">Parameters are case-insensitive in Windows PowerShell, although by default the shell preserves case.</span></span> <span data-ttu-id="fabe1-138">Diferenciar maiúsculas de minúsculas dos argumentos depende da operação do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fabe1-138">Case-sensitivity of the arguments depends on the operation of the cmdlet.</span></span> <span data-ttu-id="fabe1-139">Os argumentos são passados para um parâmetro conforme especificado na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="fabe1-139">Arguments are passed to a parameter as specified at the command line.</span></span>

- <span data-ttu-id="fabe1-140">Para obter exemplos de outras declarações de parâmetro, consulte [parâmetros de cmdlet](./cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="fabe1-140">For examples of other parameter declarations, see [Cmdlet Parameters](./cmdlet-parameters.md).</span></span>

## <a name="declaring-parameters-as-positional-or-named"></a><span data-ttu-id="fabe1-141">Declarando parâmetros como posicionais ou nomeados</span><span class="sxs-lookup"><span data-stu-id="fabe1-141">Declaring Parameters as Positional or Named</span></span>

<span data-ttu-id="fabe1-142">Um cmdlet deve definir cada parâmetro como um parâmetro posicional ou nomeado.</span><span class="sxs-lookup"><span data-stu-id="fabe1-142">A cmdlet must set each parameter as either a positional or named parameter.</span></span> <span data-ttu-id="fabe1-143">Os dois tipos de parâmetros aceitam argumentos únicos, vários argumentos separados por vírgulas e configurações boolianas.</span><span class="sxs-lookup"><span data-stu-id="fabe1-143">Both kinds of parameters accept single arguments, multiple arguments separated by commas, and Boolean settings.</span></span> <span data-ttu-id="fabe1-144">Um parâmetro booliano, também chamado de *switch*, trata apenas das configurações boolianas.</span><span class="sxs-lookup"><span data-stu-id="fabe1-144">A Boolean parameter, also called a *switch*, handles only Boolean settings.</span></span> <span data-ttu-id="fabe1-145">A opção é usada para determinar a presença do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fabe1-145">The switch is used to determine the presence of the parameter.</span></span> <span data-ttu-id="fabe1-146">O padrão recomendado é `false`.</span><span class="sxs-lookup"><span data-stu-id="fabe1-146">The recommended default is `false`.</span></span>

<span data-ttu-id="fabe1-147">O cmdlet **Get-proc** de exemplo define o parâmetro `Name` como um parâmetro posicional com a posição 0.</span><span class="sxs-lookup"><span data-stu-id="fabe1-147">The sample **Get-Proc** cmdlet defines the `Name` parameter as a positional parameter with position 0.</span></span> <span data-ttu-id="fabe1-148">Isso significa que o primeiro argumento que o usuário insere na linha de comando é inserido automaticamente para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fabe1-148">This means that the first argument the user enters on the command line is automatically inserted for this parameter.</span></span> <span data-ttu-id="fabe1-149">Se você quiser definir um parâmetro nomeado, para o qual o usuário deve especificar o nome do parâmetro na linha de comando, deixe a palavra-chave `Position` fora da declaração de atributo.</span><span class="sxs-lookup"><span data-stu-id="fabe1-149">If you want to define a named parameter, for which the user must specify the parameter name from the command line, leave the `Position` keyword out of the attribute declaration.</span></span>

> [!NOTE]
> <span data-ttu-id="fabe1-150">A menos que os parâmetros devam ser nomeados, recomendamos que você crie os parâmetros mais usados posicionais para que os usuários não precisem digitar o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fabe1-150">Unless parameters must be named, we recommend that you make the most-used parameters positional so that users will not have to type the parameter name.</span></span>

## <a name="declaring-parameters-as-mandatory-or-optional"></a><span data-ttu-id="fabe1-151">Declarando parâmetros como obrigatórios ou opcionais</span><span class="sxs-lookup"><span data-stu-id="fabe1-151">Declaring Parameters as Mandatory or Optional</span></span>

<span data-ttu-id="fabe1-152">Um cmdlet deve definir cada parâmetro como um parâmetro opcional ou obrigatório.</span><span class="sxs-lookup"><span data-stu-id="fabe1-152">A cmdlet must set each parameter as either an optional or a mandatory parameter.</span></span> <span data-ttu-id="fabe1-153">No cmdlet **Get-proc** de exemplo, o parâmetro `Name` é definido como opcional porque a palavra-chave `Mandatory` não está definida na declaração de atributo.</span><span class="sxs-lookup"><span data-stu-id="fabe1-153">In the sample **Get-Proc** cmdlet, the `Name` parameter is defined as optional because the `Mandatory` keyword is not set in the attribute declaration.</span></span>

## <a name="supporting-parameter-validation"></a><span data-ttu-id="fabe1-154">Validação de parâmetro de suporte</span><span class="sxs-lookup"><span data-stu-id="fabe1-154">Supporting Parameter Validation</span></span>

<span data-ttu-id="fabe1-155">O cmdlet **Get-proc** de exemplo adiciona um atributo de validação de entrada, [System. Management. Automation. Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute), ao parâmetro `Name` para habilitar a validação de que a entrada não é `null` nem vazia.</span><span class="sxs-lookup"><span data-stu-id="fabe1-155">The sample **Get-Proc** cmdlet adds an input validation attribute, [System.Management.Automation.Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute), to the `Name` parameter to enable validation that the input is neither `null` nor empty.</span></span> <span data-ttu-id="fabe1-156">Esse atributo é um dos vários atributos de validação fornecidos pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fabe1-156">This attribute is one of several validation attributes provided by Windows PowerShell.</span></span> <span data-ttu-id="fabe1-157">Para obter exemplos de outros atributos de validação, consulte [validando a entrada de parâmetro](./validating-parameter-input.md).</span><span class="sxs-lookup"><span data-stu-id="fabe1-157">For examples of other validation attributes, see [Validating Parameter Input](./validating-parameter-input.md).</span></span>

```
[Parameter(Position = 0)]
[ValidateNotNullOrEmpty]
public string[] Name
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="fabe1-158">Substituindo um método de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="fabe1-158">Overriding an Input Processing Method</span></span>

<span data-ttu-id="fabe1-159">Se o cmdlet for manipular a entrada de linha de comando, ele deverá substituir os métodos de processamento de entrada apropriados.</span><span class="sxs-lookup"><span data-stu-id="fabe1-159">If your cmdlet is to handle command-line input, it must override the appropriate input processing methods.</span></span> <span data-ttu-id="fabe1-160">Os métodos básicos de processamento de entrada são introduzidos na [criação do seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="fabe1-160">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="fabe1-161">O cmdlet **Get-proc** substitui o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) para manipular a entrada de parâmetro `Name` fornecida pelo usuário ou um script.</span><span class="sxs-lookup"><span data-stu-id="fabe1-161">The **Get-Proc** cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="fabe1-162">Esse método obtém os processos para cada nome de processo solicitado ou todos os processos, se nenhum nome for fornecido.</span><span class="sxs-lookup"><span data-stu-id="fabe1-162">This method gets the processes for each requested process name, or all for processes if no name is provided.</span></span> <span data-ttu-id="fabe1-163">Observe que em [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), a chamada para [System. Management. Automation. cmdlet. WriteObject% 28System. Object% 2CSystem. booliano %29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) é o mecanismo de saída para enviar objetos de saída para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="fabe1-163">Notice that in [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="fabe1-164">O segundo parâmetro dessa chamada, `enumerateCollection`, é definido como `true` para informar o tempo de execução do Windows PowerShell para enumerar a matriz de saída de objetos de processo e gravar um processo por vez na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="fabe1-164">The second parameter of this call, `enumerateCollection`, is set to `true` to inform the Windows PowerShell runtime to enumerate the output array of process objects and write one process at a time to the command line.</span></span>

```csharp
protected override void ProcessRecord()
{
  // If no process names are passed to the cmdlet, get all processes.
  if (processNames == null)
  {
    // Write the processes to the pipeline making them available
    // to the next cmdlet. The second argument of this call tells
    // PowerShell to enumerate the array, and send one process at a
    // time to the pipeline.
    WriteObject(Process.GetProcesses(), true);
  }
  else
  {
    // If process names are passed to the cmdlet, get and write
    // the associated processes.
    foreach (string name in processNames)
    {
      WriteObject(Process.GetProcessesByName(name), true);
    }
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        Dim processes As Process()
        processes = Process.GetProcesses()
    End If

    '/ If process names are specified, write the processes to the
    '/ pipeline to display them or make them available to the next cmdlet.

    For Each name As String In processNames
        '/ The second parameter of this call tells PowerShell to enumerate the
        '/ array, and send one process at a time to the pipeline.
        WriteObject(Process.GetProcessesByName(name), True)
    Next

End Sub 'ProcessRecord
```

## <a name="code-sample"></a><span data-ttu-id="fabe1-165">Exemplo de Código</span><span class="sxs-lookup"><span data-stu-id="fabe1-165">Code Sample</span></span>

<span data-ttu-id="fabe1-166">Para obter o C# código de exemplo completo, consulte [exemplo de GetProcessSample02](./getprocesssample02-sample.md).</span><span class="sxs-lookup"><span data-stu-id="fabe1-166">For the complete C# sample code, see [GetProcessSample02 Sample](./getprocesssample02-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="fabe1-167">Definindo tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="fabe1-167">Defining Object Types and Formatting</span></span>

<span data-ttu-id="fabe1-168">O Windows PowerShell passa informações entre os cmdlets usando .NET Framework objetos.</span><span class="sxs-lookup"><span data-stu-id="fabe1-168">Windows PowerShell passes information between cmdlets by using .NET Framework objects.</span></span> <span data-ttu-id="fabe1-169">Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou um cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fabe1-169">Consequently, a cmdlet might need to define its own type, or a cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="fabe1-170">Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span><span class="sxs-lookup"><span data-stu-id="fabe1-170">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="fabe1-171">Criando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="fabe1-171">Building the Cmdlet</span></span>

<span data-ttu-id="fabe1-172">Depois de implementar um cmdlet, você deve registrá-lo com o Windows PowerShell usando um snap-in do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fabe1-172">After you implement a cmdlet, you must register it with Windows PowerShell by using a Windows PowerShell snap-in.</span></span> <span data-ttu-id="fabe1-173">Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span><span class="sxs-lookup"><span data-stu-id="fabe1-173">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="fabe1-174">Testando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="fabe1-174">Testing the Cmdlet</span></span>

<span data-ttu-id="fabe1-175">Quando o cmdlet estiver registrado no Windows PowerShell, você poderá testá-lo executando-o na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="fabe1-175">When your cmdlet is registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="fabe1-176">Aqui estão duas maneiras de testar o código para o cmdlet de exemplo.</span><span class="sxs-lookup"><span data-stu-id="fabe1-176">Here are two ways to test the code for the sample cmdlet.</span></span> <span data-ttu-id="fabe1-177">Para obter mais informações sobre como usar cmdlets na linha de comando, consulte [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="fabe1-177">For more information about using cmdlets from the command line, see [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="fabe1-178">No prompt do Windows PowerShell, use o comando a seguir para listar o processo do Internet Explorer, denominado "iexplore".</span><span class="sxs-lookup"><span data-stu-id="fabe1-178">At the Windows PowerShell prompt, use the following command to list the Internet Explorer process, which is named "IEXPLORE."</span></span>

    ```powershell
    PS> get-proc -name iexplore
    ```

<span data-ttu-id="fabe1-179">A seguinte saída aparece.</span><span class="sxs-lookup"><span data-stu-id="fabe1-179">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
    -------  ------  -----   -----  -----   ------ --   -----------
        354      11  10036   18992    85   0.67   3284   iexplore
    ```

- <span data-ttu-id="fabe1-180">Para listar os processos do Internet Explorer, Outlook e bloco de notas denominados "iexplore", "OUTLOOK," e "bloco de notas", use o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="fabe1-180">To list the Internet Explorer, Outlook, and Notepad processes named "IEXPLORE," "OUTLOOK," and "NOTEPAD," use the following command.</span></span> <span data-ttu-id="fabe1-181">Se houver vários processos, todos eles serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="fabe1-181">If there are multiple processes, all of them are displayed.</span></span>

    ```powershell
    PS> get-proc -name iexplore, outlook, notepad
    ```

<span data-ttu-id="fabe1-182">A seguinte saída aparece.</span><span class="sxs-lookup"><span data-stu-id="fabe1-182">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
    -------  ------  -----   -----  -----  ------   --    -----------
        732      21  24696    5000    138   2.25  2288   iexplore
        715      19  20556   14116    136   1.78  3860   iexplore
       3917      62  74096   58112    468 191.56  1848   OUTLOOK
         39       2   1024    3280     30   0.09  1444   notepad
         39       2   1024     356     30   0.08  3396   notepad
    ```

## <a name="see-also"></a><span data-ttu-id="fabe1-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fabe1-183">See Also</span></span>

[<span data-ttu-id="fabe1-184">Adicionando parâmetros que processam a entrada do pipeline</span><span class="sxs-lookup"><span data-stu-id="fabe1-184">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="fabe1-185">Criando seu primeiro cmdlet</span><span class="sxs-lookup"><span data-stu-id="fabe1-185">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="fabe1-186">Estendendo tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="fabe1-186">Extending Object Types and Formatting</span></span>](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="fabe1-187">Como registrar cmdlets, provedores e aplicativos host</span><span class="sxs-lookup"><span data-stu-id="fabe1-187">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="fabe1-188">Referência do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fabe1-188">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="fabe1-189">Exemplos de cmdlet</span><span class="sxs-lookup"><span data-stu-id="fabe1-189">Cmdlet Samples</span></span>](./cmdlet-samples.md)
