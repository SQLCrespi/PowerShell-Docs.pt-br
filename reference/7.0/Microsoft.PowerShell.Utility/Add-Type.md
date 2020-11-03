---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: cbf211f4ae5262255a74fa7fb97d2493202d71fa
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "93195308"
---
# <span data-ttu-id="ff445-103">Add-Type</span><span class="sxs-lookup"><span data-stu-id="ff445-103">Add-Type</span></span>

## <span data-ttu-id="ff445-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ff445-104">SYNOPSIS</span></span>
<span data-ttu-id="ff445-105">Adiciona uma classe de núcleo Microsoft .NET a uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-105">Adds a Microsoft .NET Core class to a PowerShell session.</span></span>

## <span data-ttu-id="ff445-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ff445-106">SYNTAX</span></span>

### <span data-ttu-id="ff445-107">From (padrão)</span><span class="sxs-lookup"><span data-stu-id="ff445-107">FromSource (Default)</span></span>

```
Add-Type [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="ff445-108">FromMember</span><span class="sxs-lookup"><span data-stu-id="ff445-108">FromMember</span></span>

```
Add-Type [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>]
 [-UsingNamespace <String[]>] [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="ff445-109">FromPath</span><span class="sxs-lookup"><span data-stu-id="ff445-109">FromPath</span></span>

```
Add-Type [-Path] <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="ff445-110">FromLiteralPath</span><span class="sxs-lookup"><span data-stu-id="ff445-110">FromLiteralPath</span></span>

```
Add-Type -LiteralPath <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="ff445-111">FromAssemblyName</span><span class="sxs-lookup"><span data-stu-id="ff445-111">FromAssemblyName</span></span>

```
Add-Type -AssemblyName <String[]> [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="ff445-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ff445-112">DESCRIPTION</span></span>

<span data-ttu-id="ff445-113">O `Add-Type` cmdlet permite que você defina uma classe de Microsoft .NET Core na sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-113">The `Add-Type` cmdlet lets you define a Microsoft .NET Core class in your PowerShell session.</span></span> <span data-ttu-id="ff445-114">Em seguida, você pode instanciar objetos usando o `New-Object` cmdlet e usar os objetos da mesma forma que usaria qualquer objeto .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ff445-114">You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Core object.</span></span> <span data-ttu-id="ff445-115">Se você adicionar um `Add-Type` comando ao seu perfil do PowerShell, a classe estará disponível em todas as sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-115">If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.</span></span>

<span data-ttu-id="ff445-116">Você pode especificar o tipo especificando um assembly existente ou arquivos de código-fonte, ou você pode especificar o código-fonte embutido ou salvo em uma variável.</span><span class="sxs-lookup"><span data-stu-id="ff445-116">You can specify the type by specifying an existing assembly or source code files, or you can specify the source code inline or saved in a variable.</span></span> <span data-ttu-id="ff445-117">Você pode até mesmo especificar apenas um método e `Add-Type` define e gera a classe.</span><span class="sxs-lookup"><span data-stu-id="ff445-117">You can even specify only a method and `Add-Type` defines and generates the class.</span></span> <span data-ttu-id="ff445-118">No Windows, você pode usar esse recurso para fazer chamadas de invocação de plataforma (P/Invoke) para funções não gerenciadas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-118">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span> <span data-ttu-id="ff445-119">Se você especificar o código-fonte, `Add-Type` o compilará o código-fonte especificado e gerará um assembly na memória que contenha os novos tipos .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ff445-119">If you specify source code, `Add-Type` compiles the specified source code and generates an in-memory assembly that contains the new .NET Core types.</span></span>

<span data-ttu-id="ff445-120">Você pode usar os parâmetros de `Add-Type` para especificar um idioma alternativo e um compilador, C# é o padrão, opções de compilador, dependências de assembly, o namespace de classe, os nomes do tipo e o assembly resultante.</span><span class="sxs-lookup"><span data-stu-id="ff445-120">You can use the parameters of `Add-Type` to specify an alternate language and compiler, C# is the default, compiler options, assembly dependencies, the class namespace, the names of the type, and the resulting assembly.</span></span>

<span data-ttu-id="ff445-121">A partir do PowerShell 7, `Add-Type` o não compilará um tipo se já existir um tipo com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="ff445-121">Beginning in PowerShell 7, `Add-Type` does not compile a type if a type with the same name already exists.</span></span> <span data-ttu-id="ff445-122">Além disso, `Add-Type` o procura assemblies em uma `ref` pasta sob a pasta que contém `pwsh.dll` .</span><span class="sxs-lookup"><span data-stu-id="ff445-122">Also, `Add-Type` looks for assemblies in a `ref` folder under the folder that contains `pwsh.dll`.</span></span>

## <span data-ttu-id="ff445-123">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ff445-123">EXAMPLES</span></span>

### <span data-ttu-id="ff445-124">Exemplo 1: adicionar um tipo .NET a uma sessão</span><span class="sxs-lookup"><span data-stu-id="ff445-124">Example 1: Add a .NET type to a session</span></span>

<span data-ttu-id="ff445-125">Este exemplo adiciona a classe **BasicTest** à sessão especificando o código-fonte armazenado em uma variável.</span><span class="sxs-lookup"><span data-stu-id="ff445-125">This example adds the **BasicTest** class to the session by specifying source code that is stored in a variable.</span></span> <span data-ttu-id="ff445-126">A classe **BasicTest** é usada para adicionar inteiros, criar um objeto e multiplicar inteiros.</span><span class="sxs-lookup"><span data-stu-id="ff445-126">The **BasicTest** class is used to add integers, create an object, and multiply integers.</span></span>

```powershell
$Source = @"
public class BasicTest
{
  public static int Add(int a, int b)
    {
        return (a + b);
    }
  public int Multiply(int a, int b)
    {
    return (a * b);
    }
}
"@

Add-Type -TypeDefinition $Source
[BasicTest]::Add(4, 3)
$BasicTestObject = New-Object BasicTest
$BasicTestObject.Multiply(5, 2)
```

<span data-ttu-id="ff445-127">A `$Source` variável armazena o código-fonte da classe.</span><span class="sxs-lookup"><span data-stu-id="ff445-127">The `$Source` variable stores the source code for the class.</span></span> <span data-ttu-id="ff445-128">O tipo tem um método estático chamado `Add` e um método não estático chamado `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="ff445-128">The type has a static method called `Add` and a non-static method called `Multiply`.</span></span>

<span data-ttu-id="ff445-129">O `Add-Type` cmdlet adiciona a classe à sessão.</span><span class="sxs-lookup"><span data-stu-id="ff445-129">The `Add-Type` cmdlet adds the class to the session.</span></span> <span data-ttu-id="ff445-130">Como ele está usando código-fonte embutido, o comando usa o parâmetro **TypeDefinition** para especificar o código na `$Source` variável.</span><span class="sxs-lookup"><span data-stu-id="ff445-130">Because it's using inline source code, the command uses the **TypeDefinition** parameter to specify the code in the `$Source` variable.</span></span>

<span data-ttu-id="ff445-131">O `Add` método estático da classe **BasicTest** usa os caracteres de dois-pontos duplos ( `::` ) para especificar um membro estático da classe.</span><span class="sxs-lookup"><span data-stu-id="ff445-131">The `Add` static method of the **BasicTest** class uses the double-colon characters (`::`) to specify a static member of the class.</span></span> <span data-ttu-id="ff445-132">Os inteiros são adicionados e a soma é exibida.</span><span class="sxs-lookup"><span data-stu-id="ff445-132">The integers are added and the sum is displayed.</span></span>

<span data-ttu-id="ff445-133">O `New-Object` cmdlet instancia uma instância da classe **BasicTest** .</span><span class="sxs-lookup"><span data-stu-id="ff445-133">The `New-Object` cmdlet instantiates an instance of the **BasicTest** class.</span></span> <span data-ttu-id="ff445-134">Ele salva o novo objeto na `$BasicTestObject` variável.</span><span class="sxs-lookup"><span data-stu-id="ff445-134">It saves the new object in the `$BasicTestObject` variable.</span></span>

<span data-ttu-id="ff445-135">`$BasicTestObject` usa o `Multiply` método.</span><span class="sxs-lookup"><span data-stu-id="ff445-135">`$BasicTestObject` uses the `Multiply` method.</span></span> <span data-ttu-id="ff445-136">Os inteiros são multiplicados e o produto é exibido.</span><span class="sxs-lookup"><span data-stu-id="ff445-136">The integers are multiplied and the product is displayed.</span></span>

### <span data-ttu-id="ff445-137">Exemplo 2: examinar um tipo adicionado</span><span class="sxs-lookup"><span data-stu-id="ff445-137">Example 2: Examine an added type</span></span>

<span data-ttu-id="ff445-138">Este exemplo usa o `Get-Member` cmdlet para examinar os objetos que os `Add-Type` `New-Object` cmdlets e criados no **exemplo 1** .</span><span class="sxs-lookup"><span data-stu-id="ff445-138">This example uses the `Get-Member` cmdlet to examine the objects that the `Add-Type` and `New-Object` cmdlets created in **Example 1** .</span></span>

```powershell
[BasicTest] | Get-Member
```

```Output
   TypeName: System.RuntimeType

Name                 MemberType Definition
----                 ---------- ----------
AsType               Method     type AsType()
Clone                Method     System.Object Clone(), System.Object ICloneable.Clone()
Equals               Method     bool Equals(System.Object obj), bool Equals(type o)
FindInterfaces       Method     type[] FindInterfaces(System.Reflection.TypeFilter filter...
...
```

```powershell
[BasicTest] | Get-Member -Static
```

```Output
  TypeName: BasicTest

Name            MemberType Definition
----            ---------- ----------
Add             Method     static int Add(int a, int b)
Equals          Method     static bool Equals(System.Object objA, System.Object objB)
new             Method     BasicTest new()
ReferenceEquals Method     static bool ReferenceEquals(System.Object objA, System.Object objB)
```

```powershell
$BasicTestObject | Get-Member
```

```Output
   TypeName: BasicTest

Name        MemberType Definition
----        ---------- ----------
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
Multiply    Method     int Multiply(int a, int b)
ToString    Method     string ToString()
```

<span data-ttu-id="ff445-139">O `Get-Member` cmdlet obtém o tipo e os membros da classe **BasicTest** que `Add-Type` foi adicionada à sessão.</span><span class="sxs-lookup"><span data-stu-id="ff445-139">The `Get-Member` cmdlet gets the type and members of the **BasicTest** class that `Add-Type` added to the session.</span></span> <span data-ttu-id="ff445-140">O `Get-Member` comando revela que é um objeto **System. RuntimeType** , que é derivado da classe **System. Object** .</span><span class="sxs-lookup"><span data-stu-id="ff445-140">The `Get-Member` command reveals that it's a **System.RuntimeType** object, which is derived from the **System.Object** class.</span></span>

<span data-ttu-id="ff445-141">O `Get-Member` parâmetro **static** Obtém as propriedades e os métodos estáticos da classe **BasicTest** .</span><span class="sxs-lookup"><span data-stu-id="ff445-141">The `Get-Member` **Static** parameter gets the static properties and methods of the **BasicTest** class.</span></span> <span data-ttu-id="ff445-142">A saída mostra que o `Add` método está incluído.</span><span class="sxs-lookup"><span data-stu-id="ff445-142">The output shows that the `Add` method is included.</span></span>

<span data-ttu-id="ff445-143">O `Get-Member` cmdlet obtém os membros do objeto armazenado na `$BasicTestObject` variável.</span><span class="sxs-lookup"><span data-stu-id="ff445-143">The `Get-Member` cmdlet gets the members of the object stored in the `$BasicTestObject` variable.</span></span>
<span data-ttu-id="ff445-144">`$BasicTestObject` foi criado usando o `New-Object` cmdlet com a classe **BasicTest** .</span><span class="sxs-lookup"><span data-stu-id="ff445-144">`$BasicTestObject` was created by using the `New-Object` cmdlet with the **BasicTest** class.</span></span> <span data-ttu-id="ff445-145">A saída revela que o valor da `$BasicTestObject` variável é uma instância da classe **BasicTest** e que ela inclui um membro chamado `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="ff445-145">The output reveals that the value of the `$BasicTestObject` variable is an instance of the **BasicTest** class and that it includes a member called `Multiply`.</span></span>

### <span data-ttu-id="ff445-146">Exemplo 3: adicionar tipos de um assembly</span><span class="sxs-lookup"><span data-stu-id="ff445-146">Example 3: Add types from an assembly</span></span>

<span data-ttu-id="ff445-147">Este exemplo adiciona as classes do `NJsonSchema.dll` assembly à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ff445-147">This example adds the classes from the `NJsonSchema.dll` assembly to the current session.</span></span>

```powershell
Set-Location -Path $PSHOME
$AccType = Add-Type -AssemblyName *jsonschema* -PassThru
```

<span data-ttu-id="ff445-148">`Set-Location` usa o parâmetro **path** para especificar a `$PSHOME` variável.</span><span class="sxs-lookup"><span data-stu-id="ff445-148">`Set-Location` uses the **Path** parameter to specify the `$PSHOME` variable.</span></span> <span data-ttu-id="ff445-149">A variável faz referência ao diretório de instalação do PowerShell onde o arquivo DLL está localizado.</span><span class="sxs-lookup"><span data-stu-id="ff445-149">The variable references the PowerShell installation directory where the DLL file is located.</span></span>

<span data-ttu-id="ff445-150">A `$AccType` variável armazena um objeto criado com o `Add-Type` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ff445-150">The `$AccType` variable stores an object created with the `Add-Type` cmdlet.</span></span> <span data-ttu-id="ff445-151">`Add-Type` usa o parâmetro **AssemblyName** para especificar o nome do assembly.</span><span class="sxs-lookup"><span data-stu-id="ff445-151">`Add-Type` uses the **AssemblyName** parameter to specify the name of the assembly.</span></span> <span data-ttu-id="ff445-152">O `*` caractere curinga asterisco () permite que você obtenha o assembly correto mesmo quando não tiver certeza do nome ou de sua grafia.</span><span class="sxs-lookup"><span data-stu-id="ff445-152">The asterisk (`*`) wildcard character allows you to get the correct assembly even when you aren't sure of the name or its spelling.</span></span> <span data-ttu-id="ff445-153">O parâmetro **PassThru** gera objetos que representam as classes que são adicionadas à sessão.</span><span class="sxs-lookup"><span data-stu-id="ff445-153">The **PassThru** parameter generates objects that represent the classes that are added to the session.</span></span>

### <span data-ttu-id="ff445-154">Exemplo 4: chamar APIs nativas do Windows</span><span class="sxs-lookup"><span data-stu-id="ff445-154">Example 4: Call native Windows APIs</span></span>

<span data-ttu-id="ff445-155">Este exemplo demonstra como chamar APIs nativas do Windows no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-155">This example demonstrates how to call native Windows APIs in PowerShell.</span></span> <span data-ttu-id="ff445-156">`Add-Type` usa o mecanismo de invocação de plataforma (P/Invoke) para chamar uma função no `User32.dll` do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-156">`Add-Type` uses the Platform Invoke (P/Invoke) mechanism to call a function in `User32.dll` from PowerShell.</span></span> <span data-ttu-id="ff445-157">Este exemplo só funciona em computadores que executam o sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="ff445-157">This example only works on computers running the Windows operating system.</span></span>

```powershell
$Signature = @"
[DllImport("user32.dll")]public static extern bool ShowWindowAsync(IntPtr hWnd, int nCmdShow);
"@

$ShowWindowAsync = Add-Type -MemberDefinition $Signature -Name "Win32ShowWindowAsync" -Namespace Win32Functions -PassThru

# Minimize the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $pid).MainWindowHandle, 2)

# Restore the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $Pid).MainWindowHandle, 4)
```

<span data-ttu-id="ff445-158">A `$Signature` variável armazena a assinatura C# da `ShowWindowAsync` função.</span><span class="sxs-lookup"><span data-stu-id="ff445-158">The `$Signature` variable stores the C# signature of the `ShowWindowAsync` function.</span></span> <span data-ttu-id="ff445-159">Para garantir que o método resultante seja visível em uma sessão do PowerShell, a `public` palavra-chave foi adicionada à assinatura padrão.</span><span class="sxs-lookup"><span data-stu-id="ff445-159">To ensure that the resulting method is visible in a PowerShell session, the `public` keyword was added to the standard signature.</span></span> <span data-ttu-id="ff445-160">Para obter mais informações, consulte [função ShowWindowAsync](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span><span class="sxs-lookup"><span data-stu-id="ff445-160">For more information, see [ShowWindowAsync function](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span></span>

<span data-ttu-id="ff445-161">A `$ShowWindowAsync` variável armazena o objeto criado pelo parâmetro `Add-Type` **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="ff445-161">The `$ShowWindowAsync` variable stores the object created by the `Add-Type` **PassThru** parameter.</span></span>
<span data-ttu-id="ff445-162">O `Add-Type` cmdlet adiciona a `ShowWindowAsync` função à sessão do PowerShell como um método estático.</span><span class="sxs-lookup"><span data-stu-id="ff445-162">The `Add-Type` cmdlet adds the `ShowWindowAsync` function to the PowerShell session as a static method.</span></span> <span data-ttu-id="ff445-163">O comando usa o parâmetro **MemberDefinition** para especificar a definição de método salva na `$Signature` variável.</span><span class="sxs-lookup"><span data-stu-id="ff445-163">The command uses the **MemberDefinition** parameter to specify the method definition saved in the `$Signature` variable.</span></span> <span data-ttu-id="ff445-164">O comando usa os parâmetros **Name** e **Namespace** para especificar um nome e um namespace para a classe.</span><span class="sxs-lookup"><span data-stu-id="ff445-164">The command uses the **Name** and **Namespace** parameters to specify a name and namespace for the class.</span></span> <span data-ttu-id="ff445-165">O parâmetro **PassThru** gera um objeto que representa os tipos.</span><span class="sxs-lookup"><span data-stu-id="ff445-165">The **PassThru** parameter generates an object that represents the types.</span></span>

<span data-ttu-id="ff445-166">O novo `ShowWindowAsync` método estático é usado nos comandos para minimizar e restaurar o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-166">The new `ShowWindowAsync` static method is used in the commands to minimize and restore the PowerShell console.</span></span> <span data-ttu-id="ff445-167">O método usa dois parâmetros: o identificador de janela e um inteiro que especifica como a janela é exibida.</span><span class="sxs-lookup"><span data-stu-id="ff445-167">The method takes two parameters: the window handle, and an integer that specifies how the window is displayed.</span></span>

<span data-ttu-id="ff445-168">Para minimizar o console do PowerShell, o `ShowWindowAsync` usa o `Get-Process` cmdlet com a `$PID` variável automática para obter o processo que está hospedando a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-168">To minimize the PowerShell console, `ShowWindowAsync` uses the `Get-Process` cmdlet with the `$PID` automatic variable to get the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="ff445-169">Em seguida, ele usa a propriedade **MainWindowHandle** do processo atual e um valor de `2` , que representa o `SW_MINIMIZE` valor.</span><span class="sxs-lookup"><span data-stu-id="ff445-169">Then it uses the **MainWindowHandle** property of the current process and a value of `2`, which represents the `SW_MINIMIZE` value.</span></span>

<span data-ttu-id="ff445-170">Para restaurar a janela, o `ShowWindowAsync` usa um valor de `4` para a posição da janela, que representa o `SW_RESTORE` valor.</span><span class="sxs-lookup"><span data-stu-id="ff445-170">To restore the window, `ShowWindowAsync` uses a value of `4` for the window position, which represents the `SW_RESTORE` value.</span></span>

<span data-ttu-id="ff445-171">Para maximizar a janela, use o valor de `3` que representa `SW_MAXIMIZE` .</span><span class="sxs-lookup"><span data-stu-id="ff445-171">To maximize the window, use the value of `3` that represents `SW_MAXIMIZE`.</span></span>

## <span data-ttu-id="ff445-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ff445-172">PARAMETERS</span></span>

### <span data-ttu-id="ff445-173">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="ff445-173">-AssemblyName</span></span>

<span data-ttu-id="ff445-174">Especifica o nome de um assembly que inclui os tipos.</span><span class="sxs-lookup"><span data-stu-id="ff445-174">Specifies the name of an assembly that includes the types.</span></span> <span data-ttu-id="ff445-175">`Add-Type` usa os tipos do assembly especificado.</span><span class="sxs-lookup"><span data-stu-id="ff445-175">`Add-Type` takes the types from the specified assembly.</span></span> <span data-ttu-id="ff445-176">Esse parâmetro é necessário quando você está criando tipos com base em um nome de assembly.</span><span class="sxs-lookup"><span data-stu-id="ff445-176">This parameter is required when you're creating types based on an assembly name.</span></span>

<span data-ttu-id="ff445-177">Insira o nome completo ou simples, também conhecido como o nome parcial, de um assembly.</span><span class="sxs-lookup"><span data-stu-id="ff445-177">Enter the full or simple name, also known as the partial name, of an assembly.</span></span> <span data-ttu-id="ff445-178">Caracteres curinga são permitidos no nome do assembly.</span><span class="sxs-lookup"><span data-stu-id="ff445-178">Wildcard characters are permitted in the assembly name.</span></span> <span data-ttu-id="ff445-179">Se você inserir um nome simples ou parcial, `Add-Type` o o resolverá para o nome completo e, em seguida, usará o nome completo para carregar o assembly.</span><span class="sxs-lookup"><span data-stu-id="ff445-179">If you enter a simple or partial name, `Add-Type` resolves it to the full name, and then uses the full name to load the assembly.</span></span>

<span data-ttu-id="ff445-180">Esse parâmetro não aceita um caminho ou um nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ff445-180">This parameter doesn't accept a path or a filename.</span></span> <span data-ttu-id="ff445-181">Para inserir o caminho para o arquivo DLL (biblioteca de vínculo dinâmico) do assembly, use o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="ff445-181">To enter the path to the assembly dynamic-link library (DLL) file, use the **Path** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromAssemblyName
Aliases: AN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ff445-182">-Compiladoroptions</span><span class="sxs-lookup"><span data-stu-id="ff445-182">-CompilerOptions</span></span>

<span data-ttu-id="ff445-183">Especifica as opções para o compilador de código fonte.</span><span class="sxs-lookup"><span data-stu-id="ff445-183">Specifies the options for the source code compiler.</span></span> <span data-ttu-id="ff445-184">Essas opções são enviadas sem revisão para o compilador.</span><span class="sxs-lookup"><span data-stu-id="ff445-184">These options are sent to the compiler without revision.</span></span>

<span data-ttu-id="ff445-185">Esse parâmetro permite que você direcione o compilador para gerar um arquivo executável, inserir recursos ou definir opções de linha de comando, como a `/unsafe` opção.</span><span class="sxs-lookup"><span data-stu-id="ff445-185">This parameter allows you to direct the compiler to generate an executable file, embed resources, or set command-line options, such as the `/unsafe` option.</span></span>

<span data-ttu-id="ff445-186">Você não pode usar os parâmetros **CompilerOptions** e **ReferencedAssemblies** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="ff445-186">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-187">-IgnoreWarnings</span><span class="sxs-lookup"><span data-stu-id="ff445-187">-IgnoreWarnings</span></span>

<span data-ttu-id="ff445-188">Ignora os avisos do compilador.</span><span class="sxs-lookup"><span data-stu-id="ff445-188">Ignores compiler warnings.</span></span> <span data-ttu-id="ff445-189">Use esse parâmetro para evitar o `Add-Type` tratamento de avisos do compilador como erros.</span><span class="sxs-lookup"><span data-stu-id="ff445-189">Use this parameter to prevent `Add-Type` from handling compiler warnings as errors.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-190">-Idioma</span><span class="sxs-lookup"><span data-stu-id="ff445-190">-Language</span></span>

<span data-ttu-id="ff445-191">Especifica a linguagem usada no código-fonte.</span><span class="sxs-lookup"><span data-stu-id="ff445-191">Specifies the language that is used in the source code.</span></span> <span data-ttu-id="ff445-192">O valor aceitável para esse parâmetro é **Csharp** .</span><span class="sxs-lookup"><span data-stu-id="ff445-192">The acceptable value for this parameter is **CSharp** .</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-193">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ff445-193">-LiteralPath</span></span>

<span data-ttu-id="ff445-194">Especifica o caminho para arquivos de código fonte ou arquivos DLL de assembly que contêm os tipos.</span><span class="sxs-lookup"><span data-stu-id="ff445-194">Specifies the path to source code files or assembly DLL files that contain the types.</span></span> <span data-ttu-id="ff445-195">Ao contrário do **caminho** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="ff445-195">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="ff445-196">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="ff445-196">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="ff445-197">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="ff445-197">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ff445-198">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="ff445-198">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-199">-MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="ff445-199">-MemberDefinition</span></span>

<span data-ttu-id="ff445-200">Especifica novas propriedades ou métodos para a classe.</span><span class="sxs-lookup"><span data-stu-id="ff445-200">Specifies new properties or methods for the class.</span></span> <span data-ttu-id="ff445-201">`Add-Type` gera o código de modelo necessário para dar suporte às propriedades ou aos métodos.</span><span class="sxs-lookup"><span data-stu-id="ff445-201">`Add-Type` generates the template code that is required to support the properties or methods.</span></span>

<span data-ttu-id="ff445-202">No Windows, você pode usar esse recurso para fazer chamadas de invocação de plataforma (P/Invoke) para funções não gerenciadas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-202">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-203">-Name</span><span class="sxs-lookup"><span data-stu-id="ff445-203">-Name</span></span>

<span data-ttu-id="ff445-204">Especifica o nome da classe a ser criada.</span><span class="sxs-lookup"><span data-stu-id="ff445-204">Specifies the name of the class to create.</span></span> <span data-ttu-id="ff445-205">Esse parâmetro é necessário ao gerar um tipo por meio de uma definição de membro.</span><span class="sxs-lookup"><span data-stu-id="ff445-205">This parameter is required when generating a type from a member definition.</span></span>

<span data-ttu-id="ff445-206">O nome do tipo e o namespace devem ser exclusivos dentro de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ff445-206">The type name and namespace must be unique within a session.</span></span> <span data-ttu-id="ff445-207">Você não pode descarregar um tipo ou alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="ff445-207">You can't unload a type or change it.</span></span>
<span data-ttu-id="ff445-208">Para alterar o código de um tipo, você deve alterar o nome ou iniciar uma nova sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-208">To change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="ff445-209">Caso contrário, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="ff445-209">Otherwise, the command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-210">-Namespace</span><span class="sxs-lookup"><span data-stu-id="ff445-210">-Namespace</span></span>

<span data-ttu-id="ff445-211">Especifica um namespace para o tipo.</span><span class="sxs-lookup"><span data-stu-id="ff445-211">Specifies a namespace for the type.</span></span>

<span data-ttu-id="ff445-212">Se esse parâmetro não estiver incluído no comando, o tipo será criado no namespace **Microsoft. PowerShell. Commands. AddType. AutoGeneratedTypes** .</span><span class="sxs-lookup"><span data-stu-id="ff445-212">If this parameter isn't included in the command, the type is created in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace.</span></span> <span data-ttu-id="ff445-213">Se o parâmetro for incluído no comando com um valor de cadeia de caracteres vazio ou um valor de `$Null` , o tipo será gerado no namespace global.</span><span class="sxs-lookup"><span data-stu-id="ff445-213">If the parameter is included in the command with an empty string value or a value of `$Null`, the type is generated in the global namespace.</span></span>

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-214">-OutputAssembly</span><span class="sxs-lookup"><span data-stu-id="ff445-214">-OutputAssembly</span></span>

<span data-ttu-id="ff445-215">Gera um arquivo DLL para o assembly com o nome especificado no local.</span><span class="sxs-lookup"><span data-stu-id="ff445-215">Generates a DLL file for the assembly with the specified name in the location.</span></span> <span data-ttu-id="ff445-216">Insira um caminho e um nome de arquivo opcionais.</span><span class="sxs-lookup"><span data-stu-id="ff445-216">Enter an optional path and filename.</span></span> <span data-ttu-id="ff445-217">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="ff445-217">Wildcard characters are permitted.</span></span> <span data-ttu-id="ff445-218">Por padrão, `Add-Type` o gera o assembly somente na memória.</span><span class="sxs-lookup"><span data-stu-id="ff445-218">By default, `Add-Type` generates the assembly only in memory.</span></span>

```yaml
Type: System.String
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ff445-219">-OutputType</span><span class="sxs-lookup"><span data-stu-id="ff445-219">-OutputType</span></span>

<span data-ttu-id="ff445-220">Especifica o tipo de saída do assembly de saída.</span><span class="sxs-lookup"><span data-stu-id="ff445-220">Specifies the output type of the output assembly.</span></span> <span data-ttu-id="ff445-221">Por padrão, nenhum tipo de saída é especificado.</span><span class="sxs-lookup"><span data-stu-id="ff445-221">By default, no output type is specified.</span></span> <span data-ttu-id="ff445-222">Este parâmetro é válido somente quando um assembly de saída é especificado no comando.</span><span class="sxs-lookup"><span data-stu-id="ff445-222">This parameter is valid only when an output assembly is specified in the command.</span></span> <span data-ttu-id="ff445-223">Para obter mais informações sobre os valores, consulte [Enumeração OutputAssemblyType](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span><span class="sxs-lookup"><span data-stu-id="ff445-223">For more information about the values, see [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span></span>

<span data-ttu-id="ff445-224">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="ff445-224">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="ff445-225">ConsoleApplication</span><span class="sxs-lookup"><span data-stu-id="ff445-225">ConsoleApplication</span></span>
- <span data-ttu-id="ff445-226">Biblioteca</span><span class="sxs-lookup"><span data-stu-id="ff445-226">Library</span></span>
- <span data-ttu-id="ff445-227">WindowsApplication</span><span class="sxs-lookup"><span data-stu-id="ff445-227">WindowsApplication</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff445-228">Os `ConsoleApplication` `WindowsApplication` valores e não produzem a saída de trabalho e não devem ser usados.</span><span class="sxs-lookup"><span data-stu-id="ff445-228">The `ConsoleApplication` and `WindowsApplication` values don't produce working output and should not be used.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutputAssemblyType
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OT
Accepted values: ConsoleApplication, Library, WindowsApplication

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-229">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ff445-229">-PassThru</span></span>

<span data-ttu-id="ff445-230">Retorna um objeto **System.Runtime** que representa os tipos adicionados.</span><span class="sxs-lookup"><span data-stu-id="ff445-230">Returns a **System.Runtime** object that represents the types that were added.</span></span> <span data-ttu-id="ff445-231">Por padrão, esse cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="ff445-231">By default, this cmdlet doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-232">-Path</span><span class="sxs-lookup"><span data-stu-id="ff445-232">-Path</span></span>

<span data-ttu-id="ff445-233">Especifica o caminho para arquivos de código fonte ou arquivos DLL de assembly que contêm os tipos.</span><span class="sxs-lookup"><span data-stu-id="ff445-233">Specifies the path to source code files or assembly DLL files that contain the types.</span></span>

<span data-ttu-id="ff445-234">Se você enviar arquivos de código-fonte, `Add-Type` o compilará o código nos arquivos e criará um assembly na memória dos tipos.</span><span class="sxs-lookup"><span data-stu-id="ff445-234">If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly of the types.</span></span> <span data-ttu-id="ff445-235">A extensão de arquivo especificada no valor de **path** determina o compilador que o `Add-Type` usa.</span><span class="sxs-lookup"><span data-stu-id="ff445-235">The file extension specified in the value of **Path** determines the compiler that `Add-Type` uses.</span></span>

<span data-ttu-id="ff445-236">Se você enviar um arquivo de assembly, `Add-Type` o usará os tipos do assembly.</span><span class="sxs-lookup"><span data-stu-id="ff445-236">If you submit an assembly file, `Add-Type` takes the types from the assembly.</span></span> <span data-ttu-id="ff445-237">Para especificar um assembly na memória ou o cache de assembly global, use o parâmetro **AssemblyName** .</span><span class="sxs-lookup"><span data-stu-id="ff445-237">To specify an in-memory assembly or the global assembly cache, use the **AssemblyName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-238">-ReferencedAssemblies</span><span class="sxs-lookup"><span data-stu-id="ff445-238">-ReferencedAssemblies</span></span>

<span data-ttu-id="ff445-239">Especifica os assemblies dos quais depende o tipo.</span><span class="sxs-lookup"><span data-stu-id="ff445-239">Specifies the assemblies upon which the type depends.</span></span> <span data-ttu-id="ff445-240">Por padrão, o `Add-Type` faz referência a `System.dll` e `System.Management.Automation.dll` .</span><span class="sxs-lookup"><span data-stu-id="ff445-240">By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`.</span></span> <span data-ttu-id="ff445-241">Os assemblies que você especificar usando esse parâmetro são referenciados além os assemblies padrão.</span><span class="sxs-lookup"><span data-stu-id="ff445-241">The assemblies that you specify by using this parameter are referenced in addition to the default assemblies.</span></span>

<span data-ttu-id="ff445-242">A partir do PowerShell 6, o **ReferencedAssemblies** não inclui os assemblies do .NET padrão.</span><span class="sxs-lookup"><span data-stu-id="ff445-242">Beginning in PowerShell 6, **ReferencedAssemblies** doesn't include the default .NET assemblies.</span></span> <span data-ttu-id="ff445-243">Você deve incluir uma referência específica a eles no valor passado para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="ff445-243">You must include a specific reference to them in the value passed to this parameter.</span></span>

<span data-ttu-id="ff445-244">Você não pode usar os parâmetros **CompilerOptions** e **ReferencedAssemblies** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="ff445-244">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: RA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-245">-TypeDefinition</span><span class="sxs-lookup"><span data-stu-id="ff445-245">-TypeDefinition</span></span>

<span data-ttu-id="ff445-246">Especifica o código-fonte que contém as definições de tipo.</span><span class="sxs-lookup"><span data-stu-id="ff445-246">Specifies the source code that contains the type definitions.</span></span> <span data-ttu-id="ff445-247">Insira o código-fonte em uma cadeia de caracteres ou cadeia de caracteres here, ou insira uma variável que contenha o código-fonte.</span><span class="sxs-lookup"><span data-stu-id="ff445-247">Enter the source code in a string or here-string, or enter a variable that contains the source code.</span></span> <span data-ttu-id="ff445-248">Para obter mais informações sobre as cadeias de caracteres aqui, consulte [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="ff445-248">For more information about here-strings, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span></span>

<span data-ttu-id="ff445-249">Inclua uma declaração de namespace em sua definição de tipo.</span><span class="sxs-lookup"><span data-stu-id="ff445-249">Include a namespace declaration in your type definition.</span></span> <span data-ttu-id="ff445-250">Se você omitir a declaração de namespace, seu tipo pode ter o mesmo nome que outro tipo ou o atalho para outro tipo, causando uma substituição não intencional.</span><span class="sxs-lookup"><span data-stu-id="ff445-250">If you omit the namespace declaration, your type might have the same name as another type or the shortcut for another type, causing an unintentional overwrite.</span></span> <span data-ttu-id="ff445-251">Por exemplo, se você definir um tipo chamado **exceção** , os scripts que usam **exceção** como o atalho para **System. Exception** falharão.</span><span class="sxs-lookup"><span data-stu-id="ff445-251">For example, if you define a type called **Exception** , scripts that use **Exception** as the shortcut for **System.Exception** will fail.</span></span>

```yaml
Type: System.String
Parameter Sets: FromSource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-252">-UsingNamespace</span><span class="sxs-lookup"><span data-stu-id="ff445-252">-UsingNamespace</span></span>

<span data-ttu-id="ff445-253">Especifica outros namespaces que são necessários para a classe.</span><span class="sxs-lookup"><span data-stu-id="ff445-253">Specifies other namespaces that are required for the class.</span></span> <span data-ttu-id="ff445-254">Isso é muito parecido com a palavra-chave C#, `Using` .</span><span class="sxs-lookup"><span data-stu-id="ff445-254">This is much like the C# keyword, `Using`.</span></span>

<span data-ttu-id="ff445-255">Por padrão, `Add-Type` o faz referência ao namespace do **sistema** .</span><span class="sxs-lookup"><span data-stu-id="ff445-255">By default, `Add-Type` references the **System** namespace.</span></span> <span data-ttu-id="ff445-256">Quando o parâmetro **MemberDefinition** é usado, `Add-Type` o também faz referência ao namespace **System. Runtime. InteropServices** por padrão.</span><span class="sxs-lookup"><span data-stu-id="ff445-256">When the **MemberDefinition** parameter is used, `Add-Type` also references the **System.Runtime.InteropServices** namespace by default.</span></span> <span data-ttu-id="ff445-257">Os namespaces que você adiciona usando o parâmetro **UsingNamespace** são mencionados além dos namespaces padrão.</span><span class="sxs-lookup"><span data-stu-id="ff445-257">The namespaces that you add by using the **UsingNamespace** parameter are referenced in addition to the default namespaces.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases: Using

Required: False
Position: Named
Default value: System namespace
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff445-258">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ff445-258">CommonParameters</span></span>

<span data-ttu-id="ff445-259">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ff445-259">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ff445-260">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ff445-260">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ff445-261">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ff445-261">INPUTS</span></span>

### <span data-ttu-id="ff445-262">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ff445-262">None</span></span>

<span data-ttu-id="ff445-263">Você não pode enviar objetos pelo pipeline para o `Add-Type` .</span><span class="sxs-lookup"><span data-stu-id="ff445-263">You can't send objects down the pipeline to `Add-Type`.</span></span>

## <span data-ttu-id="ff445-264">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ff445-264">OUTPUTS</span></span>

### <span data-ttu-id="ff445-265">Nenhum ou System. Type</span><span class="sxs-lookup"><span data-stu-id="ff445-265">None or System.Type</span></span>

<span data-ttu-id="ff445-266">Quando você usa o parâmetro **PassThru** , `Add-Type` retorna um objeto **System. Type** que representa o novo tipo.</span><span class="sxs-lookup"><span data-stu-id="ff445-266">When you use the **PassThru** parameter, `Add-Type` returns a **System.Type** object that represents the new type.</span></span> <span data-ttu-id="ff445-267">Caso contrário, esse cmdlet não gerará nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="ff445-267">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="ff445-268">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ff445-268">NOTES</span></span>

<span data-ttu-id="ff445-269">Os tipos que você adiciona existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ff445-269">The types that you add exist only in the current session.</span></span> <span data-ttu-id="ff445-270">Para usar os tipos em todas as sessões, adicione-as ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-270">To use the types in all sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="ff445-271">Para obter mais informações sobre o perfil, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ff445-271">For more information about the profile, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="ff445-272">Os nomes de tipo e namespaces devem ser exclusivos em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ff445-272">Type names and namespaces must be unique within a session.</span></span> <span data-ttu-id="ff445-273">Você não pode descarregar um tipo ou alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="ff445-273">You can't unload a type or change it.</span></span> <span data-ttu-id="ff445-274">Se você precisar alterar o código para um tipo, deverá alterar o nome ou iniciar uma nova sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-274">If you need to change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="ff445-275">Caso contrário, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="ff445-275">Otherwise, the command fails.</span></span>

<span data-ttu-id="ff445-276">No Windows PowerShell (versão 5,1 e inferior), você precisa usar o `Add-Type` para qualquer coisa que ainda não esteja carregada.</span><span class="sxs-lookup"><span data-stu-id="ff445-276">In Windows PowerShell (version 5.1 and below), you need to use `Add-Type` for anything that isn't already loaded.</span></span> <span data-ttu-id="ff445-277">Normalmente, isso se aplica a assemblies encontrados no GAC (cache de assembly global).</span><span class="sxs-lookup"><span data-stu-id="ff445-277">Most commonly, this applies to assemblies found in the Global Assembly Cache (GAC).</span></span>
<span data-ttu-id="ff445-278">No PowerShell 6 e superior, não há nenhum GAC, portanto, o PowerShell instala seus próprios assemblies no `$PSHome` .</span><span class="sxs-lookup"><span data-stu-id="ff445-278">In PowerShell 6 and higher, there is no GAC, so PowerShell installs its own assemblies in `$PSHome`.</span></span>
<span data-ttu-id="ff445-279">Esses assemblies são carregados automaticamente na solicitação, portanto, não é necessário usá `Add-Type` -los para carregá-los.</span><span class="sxs-lookup"><span data-stu-id="ff445-279">These assemblies are automatically loaded on request, so there's no need to use `Add-Type` to load them.</span></span> <span data-ttu-id="ff445-280">No entanto, o uso `Add-Type` do ainda é permitido para permitir que os scripts sejam implicitamente compatíveis com qualquer versão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff445-280">However, using `Add-Type` is still permitted to allow scripts to be implicitly compatible with any version of PowerShell.</span></span>

<span data-ttu-id="ff445-281">Os assemblies no GAC podem ser carregados pelo nome do tipo, em vez de por caminho.</span><span class="sxs-lookup"><span data-stu-id="ff445-281">Assemblies in the GAC can be loaded by type name, rather than by path.</span></span> <span data-ttu-id="ff445-282">O carregamento de assemblies de um caminho arbitrário requer `Add-Type` , pois esses assemblies não podem ser carregados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ff445-282">Loading assemblies from an arbitrary path requires `Add-Type`, since those assemblies cannot not be loaded automatically.</span></span>

## <span data-ttu-id="ff445-283">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ff445-283">RELATED LINKS</span></span>

[<span data-ttu-id="ff445-284">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="ff445-284">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_profiles.md)

[<span data-ttu-id="ff445-285">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="ff445-285">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="ff445-286">Add-Member</span><span class="sxs-lookup"><span data-stu-id="ff445-286">Add-Member</span></span>](Add-Member.md)

[<span data-ttu-id="ff445-287">New-Object</span><span class="sxs-lookup"><span data-stu-id="ff445-287">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="ff445-288">OutputAssemblyType</span><span class="sxs-lookup"><span data-stu-id="ff445-288">OutputAssemblyType</span></span>](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[<span data-ttu-id="ff445-289">Invocação de plataforma (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="ff445-289">Platform Invoke (P/Invoke)</span></span>](/dotnet/standard/native-interop/pinvoke)

[<span data-ttu-id="ff445-290">Where-Object</span><span class="sxs-lookup"><span data-stu-id="ff445-290">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
