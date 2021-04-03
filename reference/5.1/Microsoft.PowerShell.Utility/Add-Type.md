---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: e6fa1d63f2c748c590920db0cbfdf241e0646a73
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2021
ms.locfileid: "106274248"
---
# <span data-ttu-id="70bff-102">Add-Type</span><span class="sxs-lookup"><span data-stu-id="70bff-102">Add-Type</span></span>

## <span data-ttu-id="70bff-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="70bff-103">SYNOPSIS</span></span>
<span data-ttu-id="70bff-104">Adiciona uma classe de Microsoft .NET a uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-104">Adds a Microsoft .NET class to a PowerShell session.</span></span>

## <span data-ttu-id="70bff-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="70bff-105">SYNTAX</span></span>

### <span data-ttu-id="70bff-106">From (padrão)</span><span class="sxs-lookup"><span data-stu-id="70bff-106">FromSource (Default)</span></span>

```
Add-Type [-CodeDomProvider <CodeDomProvider>] [-CompilerParameters <CompilerParameters>]
 [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [<CommonParameters>]
```

### <span data-ttu-id="70bff-107">FromMember</span><span class="sxs-lookup"><span data-stu-id="70bff-107">FromMember</span></span>

```
Add-Type [-CodeDomProvider <CodeDomProvider>] [-CompilerParameters <CompilerParameters>]
 [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>] [-UsingNamespace <String[]>]
 [-Language <Language>] [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="70bff-108">FromPath</span><span class="sxs-lookup"><span data-stu-id="70bff-108">FromPath</span></span>

```
Add-Type [-CompilerParameters <CompilerParameters>] [-Path] <String[]>
 [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>]
 [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="70bff-109">FromLiteralPath</span><span class="sxs-lookup"><span data-stu-id="70bff-109">FromLiteralPath</span></span>

```
Add-Type [-CompilerParameters <CompilerParameters>] -LiteralPath <String[]>
 [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>]
 [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="70bff-110">FromAssemblyName</span><span class="sxs-lookup"><span data-stu-id="70bff-110">FromAssemblyName</span></span>

```
Add-Type -AssemblyName <String[]> [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

## <span data-ttu-id="70bff-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="70bff-111">DESCRIPTION</span></span>

<span data-ttu-id="70bff-112">O `Add-Type` cmdlet permite que você defina uma classe de estrutura de Microsoft .net na sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-112">The `Add-Type` cmdlet lets you define a Microsoft .NET Framework class in your PowerShell session.</span></span>
<span data-ttu-id="70bff-113">Em seguida, você pode instanciar objetos, usando o `New-Object` cmdlet, e usar os objetos da mesma forma que usaria qualquer objeto de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70bff-113">You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Framework object.</span></span> <span data-ttu-id="70bff-114">Se você adicionar um `Add-Type` comando ao seu perfil do PowerShell, a classe estará disponível em todas as sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-114">If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.</span></span>

<span data-ttu-id="70bff-115">Você pode especificar o tipo especificando um assembly existente ou arquivos de código-fonte, ou você pode especificar o código-fonte embutido ou salvo em uma variável.</span><span class="sxs-lookup"><span data-stu-id="70bff-115">You can specify the type by specifying an existing assembly or source code files, or you can specify the source code inline or saved in a variable.</span></span> <span data-ttu-id="70bff-116">Você pode até mesmo especificar apenas um método e `Add-Type` irá definir e gerar a classe.</span><span class="sxs-lookup"><span data-stu-id="70bff-116">You can even specify only a method and `Add-Type` will define and generate the class.</span></span> <span data-ttu-id="70bff-117">No Windows, você pode usar esse recurso para fazer chamadas de invocação de plataforma (P/Invoke) para funções não gerenciadas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-117">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span> <span data-ttu-id="70bff-118">Se você especificar o código-fonte, `Add-Type` o compilará o código-fonte especificado e gerará um assembly na memória que contenha os novos tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70bff-118">If you specify source code, `Add-Type` compiles the specified source code and generates an in-memory assembly that contains the new .NET Framework types.</span></span>

<span data-ttu-id="70bff-119">Você pode usar os parâmetros de `Add-Type` para especificar um idioma alternativo e um compilador, C# é o padrão, opções de compilador, dependências de assembly, o namespace de classe, os nomes do tipo e o assembly resultante.</span><span class="sxs-lookup"><span data-stu-id="70bff-119">You can use the parameters of `Add-Type` to specify an alternate language and compiler, C# is the default, compiler options, assembly dependencies, the class namespace, the names of the type, and the resulting assembly.</span></span>

## <span data-ttu-id="70bff-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="70bff-120">EXAMPLES</span></span>

### <span data-ttu-id="70bff-121">Exemplo 1: adicionar um tipo .NET a uma sessão</span><span class="sxs-lookup"><span data-stu-id="70bff-121">Example 1: Add a .NET type to a session</span></span>

<span data-ttu-id="70bff-122">Este exemplo adiciona a classe **BasicTest** à sessão especificando o código-fonte armazenado em uma variável.</span><span class="sxs-lookup"><span data-stu-id="70bff-122">This example adds the **BasicTest** class to the session by specifying source code that is stored in a variable.</span></span> <span data-ttu-id="70bff-123">A classe **BasicTest** é usada para adicionar inteiros, criar um objeto e multiplicar inteiros.</span><span class="sxs-lookup"><span data-stu-id="70bff-123">The **BasicTest** class is used to add integers, create an object, and multiply integers.</span></span>

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

<span data-ttu-id="70bff-124">A `$Source` variável armazena o código-fonte da classe.</span><span class="sxs-lookup"><span data-stu-id="70bff-124">The `$Source` variable stores the source code for the class.</span></span> <span data-ttu-id="70bff-125">O tipo tem um método estático chamado `Add` e um método não estático chamado `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="70bff-125">The type has a static method called `Add` and a non-static method called `Multiply`.</span></span>

<span data-ttu-id="70bff-126">O `Add-Type` cmdlet adiciona a classe à sessão.</span><span class="sxs-lookup"><span data-stu-id="70bff-126">The `Add-Type` cmdlet adds the class to the session.</span></span> <span data-ttu-id="70bff-127">Como ele está usando código-fonte embutido, o comando usa o parâmetro **TypeDefinition** para especificar o código na `$Source` variável.</span><span class="sxs-lookup"><span data-stu-id="70bff-127">Because it's using inline source code, the command uses the **TypeDefinition** parameter to specify the code in the `$Source` variable.</span></span>

<span data-ttu-id="70bff-128">O `Add` método estático da classe **BasicTest** usa os caracteres de dois-pontos duplos ( `::` ) para especificar um membro estático da classe.</span><span class="sxs-lookup"><span data-stu-id="70bff-128">The `Add` static method of the **BasicTest** class uses the double-colon characters (`::`) to specify a static member of the class.</span></span> <span data-ttu-id="70bff-129">Os inteiros são adicionados e a soma é exibida.</span><span class="sxs-lookup"><span data-stu-id="70bff-129">The integers are added and the sum is displayed.</span></span>

<span data-ttu-id="70bff-130">O `New-Object` cmdlet instancia uma instância da classe **BasicTest** .</span><span class="sxs-lookup"><span data-stu-id="70bff-130">The `New-Object` cmdlet instantiates an instance of the **BasicTest** class.</span></span> <span data-ttu-id="70bff-131">Ele salva o novo objeto na `$BasicTestObject` variável.</span><span class="sxs-lookup"><span data-stu-id="70bff-131">It saves the new object in the `$BasicTestObject` variable.</span></span>

<span data-ttu-id="70bff-132">`$BasicTestObject` usa o `Multiply` método.</span><span class="sxs-lookup"><span data-stu-id="70bff-132">`$BasicTestObject` uses the `Multiply` method.</span></span> <span data-ttu-id="70bff-133">Os inteiros são multiplicados e o produto é exibido.</span><span class="sxs-lookup"><span data-stu-id="70bff-133">The integers are multiplied and the product is displayed.</span></span>

### <span data-ttu-id="70bff-134">Exemplo 2: examinar um tipo adicionado</span><span class="sxs-lookup"><span data-stu-id="70bff-134">Example 2: Examine an added type</span></span>

<span data-ttu-id="70bff-135">Este exemplo usa o `Get-Member` cmdlet para examinar os objetos que os `Add-Type` `New-Object` cmdlets e criados no **exemplo 1**.</span><span class="sxs-lookup"><span data-stu-id="70bff-135">This example uses the `Get-Member` cmdlet to examine the objects that the `Add-Type` and `New-Object` cmdlets created in **Example 1**.</span></span>

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

<span data-ttu-id="70bff-136">O `Get-Member` cmdlet obtém o tipo e os membros da classe **BasicTest** que `Add-Type` foi adicionada à sessão.</span><span class="sxs-lookup"><span data-stu-id="70bff-136">The `Get-Member` cmdlet gets the type and members of the **BasicTest** class that `Add-Type` added to the session.</span></span> <span data-ttu-id="70bff-137">O `Get-Member` comando revela que é um objeto **System. RuntimeType** , que é derivado da classe **System. Object** .</span><span class="sxs-lookup"><span data-stu-id="70bff-137">The `Get-Member` command reveals that it's a **System.RuntimeType** object, which is derived from the **System.Object** class.</span></span>

<span data-ttu-id="70bff-138">O `Get-Member` parâmetro **static** Obtém as propriedades e os métodos estáticos da classe **BasicTest** .</span><span class="sxs-lookup"><span data-stu-id="70bff-138">The `Get-Member` **Static** parameter gets the static properties and methods of the **BasicTest** class.</span></span> <span data-ttu-id="70bff-139">A saída mostra que o `Add` método está incluído.</span><span class="sxs-lookup"><span data-stu-id="70bff-139">The output shows that the `Add` method is included.</span></span>

<span data-ttu-id="70bff-140">O `Get-Member` cmdlet obtém os membros do objeto armazenado na `$BasicTestObject` variável.</span><span class="sxs-lookup"><span data-stu-id="70bff-140">The `Get-Member` cmdlet gets the members of the object stored in the `$BasicTestObject` variable.</span></span>
<span data-ttu-id="70bff-141">`$BasicTestObject` foi criado usando o `New-Object` cmdlet com a classe **BasicTest** .</span><span class="sxs-lookup"><span data-stu-id="70bff-141">`$BasicTestObject` was created by using the `New-Object` cmdlet with the **BasicTest** class.</span></span> <span data-ttu-id="70bff-142">A saída revela que o valor da `$BasicTestObject` variável é uma instância da classe **BasicTest** e que ela inclui um membro chamado `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="70bff-142">The output reveals that the value of the `$BasicTestObject` variable is an instance of the **BasicTest** class and that it includes a member called `Multiply`.</span></span>

### <span data-ttu-id="70bff-143">Exemplo 3: adicionar tipos de um assembly</span><span class="sxs-lookup"><span data-stu-id="70bff-143">Example 3: Add types from an assembly</span></span>

<span data-ttu-id="70bff-144">Este exemplo adiciona as classes do `Accessibility.dll` assembly à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="70bff-144">This example adds the classes from the `Accessibility.dll` assembly to the current session.</span></span>

```powershell
$AccType = Add-Type -AssemblyName "accessib*" -PassThru
```

<span data-ttu-id="70bff-145">A `$AccType` variável armazena um objeto criado com o `Add-Type` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70bff-145">The `$AccType` variable stores an object created with the `Add-Type` cmdlet.</span></span> <span data-ttu-id="70bff-146">`Add-Type` usa o parâmetro **AssemblyName** para especificar o nome do assembly.</span><span class="sxs-lookup"><span data-stu-id="70bff-146">`Add-Type` uses the **AssemblyName** parameter to specify the name of the assembly.</span></span> <span data-ttu-id="70bff-147">O `*` caractere curinga asterisco () permite que você obtenha o assembly correto mesmo quando não tiver certeza do nome ou de sua grafia.</span><span class="sxs-lookup"><span data-stu-id="70bff-147">The asterisk (`*`) wildcard character allows you to get the correct assembly even when you aren't sure of the name or its spelling.</span></span> <span data-ttu-id="70bff-148">O parâmetro **PassThru** gera objetos que representam as classes que são adicionadas à sessão.</span><span class="sxs-lookup"><span data-stu-id="70bff-148">The **PassThru** parameter generates objects that represent the classes that are added to the session.</span></span>

### <span data-ttu-id="70bff-149">Exemplo 4: chamar APIs nativas do Windows</span><span class="sxs-lookup"><span data-stu-id="70bff-149">Example 4: Call native Windows APIs</span></span>

<span data-ttu-id="70bff-150">Este exemplo demonstra como chamar APIs nativas do Windows no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-150">This example demonstrates how to call native Windows APIs in PowerShell.</span></span> <span data-ttu-id="70bff-151">`Add-Type` usa o mecanismo de invocação de plataforma (P/Invoke) para chamar uma função no `User32.dll` do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-151">`Add-Type` uses the Platform Invoke (P/Invoke) mechanism to call a function in `User32.dll` from PowerShell.</span></span> <span data-ttu-id="70bff-152">Este exemplo só funciona em computadores que executam o sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="70bff-152">This example only works on computers running the Windows operating system.</span></span>

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

<span data-ttu-id="70bff-153">A `$Signature` variável armazena a assinatura C# da `ShowWindowAsync` função.</span><span class="sxs-lookup"><span data-stu-id="70bff-153">The `$Signature` variable stores the C# signature of the `ShowWindowAsync` function.</span></span> <span data-ttu-id="70bff-154">Para garantir que o método resultante estará visível em uma sessão do PowerShell, a `public` palavra-chave foi adicionada à assinatura padrão.</span><span class="sxs-lookup"><span data-stu-id="70bff-154">To ensure that the resulting method will be visible in a PowerShell session, the `public` keyword was added to the standard signature.</span></span> <span data-ttu-id="70bff-155">Para obter mais informações, consulte [função ShowWindowAsync](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span><span class="sxs-lookup"><span data-stu-id="70bff-155">For more information, see [ShowWindowAsync function](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span></span>

<span data-ttu-id="70bff-156">A `$ShowWindowAsync` variável armazena o objeto criado pelo parâmetro `Add-Type` **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="70bff-156">The `$ShowWindowAsync` variable stores the object created by the `Add-Type` **PassThru** parameter.</span></span>
<span data-ttu-id="70bff-157">O `Add-Type` cmdlet adiciona a `ShowWindowAsync` função à sessão do PowerShell como um método estático.</span><span class="sxs-lookup"><span data-stu-id="70bff-157">The `Add-Type` cmdlet adds the `ShowWindowAsync` function to the PowerShell session as a static method.</span></span> <span data-ttu-id="70bff-158">O comando usa o parâmetro **MemberDefinition** para especificar a definição de método salva na `$Signature` variável.</span><span class="sxs-lookup"><span data-stu-id="70bff-158">The command uses the **MemberDefinition** parameter to specify the method definition saved in the `$Signature` variable.</span></span> <span data-ttu-id="70bff-159">O comando usa os parâmetros **Name** e **Namespace** para especificar um nome e um namespace para a classe.</span><span class="sxs-lookup"><span data-stu-id="70bff-159">The command uses the **Name** and **Namespace** parameters to specify a name and namespace for the class.</span></span> <span data-ttu-id="70bff-160">O parâmetro **PassThru** gera um objeto que representa os tipos.</span><span class="sxs-lookup"><span data-stu-id="70bff-160">The **PassThru** parameter generates an object that represents the types.</span></span>

<span data-ttu-id="70bff-161">O novo `ShowWindowAsync` método estático é usado nos comandos para minimizar e restaurar o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-161">The new `ShowWindowAsync` static method is used in the commands to minimize and restore the PowerShell console.</span></span> <span data-ttu-id="70bff-162">O método usa dois parâmetros: o identificador de janela e um inteiro que especifica como a janela é exibida.</span><span class="sxs-lookup"><span data-stu-id="70bff-162">The method takes two parameters: the window handle, and an integer that specifies how the window is displayed.</span></span>

<span data-ttu-id="70bff-163">Para minimizar o console do PowerShell, o `ShowWindowAsync` usa o `Get-Process` cmdlet com a `$PID` variável automática para obter o processo que está hospedando a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-163">To minimize the PowerShell console, `ShowWindowAsync` uses the `Get-Process` cmdlet with the `$PID` automatic variable to get the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="70bff-164">Em seguida, ele usa a propriedade **MainWindowHandle** do processo atual e um valor de `2` , que representa o `SW_MINIMIZE` valor.</span><span class="sxs-lookup"><span data-stu-id="70bff-164">Then it uses the **MainWindowHandle** property of the current process and a value of `2`, which represents the `SW_MINIMIZE` value.</span></span>

<span data-ttu-id="70bff-165">Para restaurar a janela, o `ShowWindowAsync` usa um valor de `4` para a posição da janela, que representa o `SW_RESTORE` valor.</span><span class="sxs-lookup"><span data-stu-id="70bff-165">To restore the window, `ShowWindowAsync` uses a value of `4` for the window position, which represents the `SW_RESTORE` value.</span></span>

<span data-ttu-id="70bff-166">Para maximizar a janela, use o valor de `3` que representa `SW_MAXIMIZE` .</span><span class="sxs-lookup"><span data-stu-id="70bff-166">To maximize the window, use the value of `3` that represents `SW_MAXIMIZE`.</span></span>

### <span data-ttu-id="70bff-167">Exemplo 5: adicionar um tipo de um arquivo de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="70bff-167">Example 5: Add a type from a Visual Basic file</span></span>

<span data-ttu-id="70bff-168">Este exemplo usa o `Add-Type` cmdlet para adicionar a classe **VBFromFile** que é definida no `Hello.vb` arquivo para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="70bff-168">This example uses the `Add-Type` cmdlet to add the **VBFromFile** class that's defined in the `Hello.vb` file to the current session.</span></span> <span data-ttu-id="70bff-169">O texto do `Hello.vb` arquivo é mostrado na saída do comando.</span><span class="sxs-lookup"><span data-stu-id="70bff-169">The text of the `Hello.vb` file is shown in the command output.</span></span>

```powershell
Add-Type -Path "C:\PS-Test\Hello.vb"
[VBFromFile]::SayHello(", World")

# From Hello.vb

Public Class VBFromFile
  Public Shared Function SayHello(sourceName As String) As String
    Dim myValue As String = "Hello"
    return myValue + sourceName
  End Function
End Class
```

```Output
Hello, World
```

<span data-ttu-id="70bff-170">`Add-Type` usa o parâmetro **path** para especificar o arquivo de origem, `Hello.vb` e adiciona o tipo definido no arquivo.</span><span class="sxs-lookup"><span data-stu-id="70bff-170">`Add-Type` uses the **Path** parameter to specify the source file, `Hello.vb`, and adds the type defined in the file.</span></span> <span data-ttu-id="70bff-171">A `SayHello` função é chamada como um método estático da classe **VBFromFile** .</span><span class="sxs-lookup"><span data-stu-id="70bff-171">The `SayHello` function is called as a static method of the **VBFromFile** class.</span></span>

### <span data-ttu-id="70bff-172">Exemplo 6: adicionar uma classe com JScript.NET</span><span class="sxs-lookup"><span data-stu-id="70bff-172">Example 6: Add a class with JScript.NET</span></span>

<span data-ttu-id="70bff-173">Este exemplo usa JScript.NET para criar uma nova classe, **FRectangle**, na sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-173">This example uses JScript.NET to create a new class, **FRectangle**, in your PowerShell session.</span></span>

```powershell
Add-Type @'
 class FRectangle {
   var Length : double;
   var Height : double;
   function Perimeter() : double {
       return (Length + Height) * 2; }
   function Area() : double {
       return Length * Height;  } }
'@ -Language JScript

$rect = [FRectangle]::new()
$rect
```

```Output
Length Height
------ ------
     0      0
```

### <span data-ttu-id="70bff-174">Exemplo 7: adicionar um compilador F #</span><span class="sxs-lookup"><span data-stu-id="70bff-174">Example 7: Add an F# compiler</span></span>

<span data-ttu-id="70bff-175">Este exemplo mostra como usar o `Add-Type` cmdlet para adicionar um compilador de código F # à sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-175">This example shows how to use the `Add-Type` cmdlet to add an F# code compiler to your PowerShell session.</span></span> <span data-ttu-id="70bff-176">Para executar este exemplo no PowerShell, você deve ter o `FSharp.Compiler.CodeDom.dll` instalado com a linguagem F #.</span><span class="sxs-lookup"><span data-stu-id="70bff-176">To run this example in PowerShell, you must have the `FSharp.Compiler.CodeDom.dll` that is installed with the F# language.</span></span>

```powershell
Add-Type -Path "FSharp.Compiler.CodeDom.dll"
$Provider = New-Object Microsoft.FSharp.Compiler.CodeDom.FSharpCodeProvider
$FSharpCode = @"
let rec loop n =if n <= 0 then () else beginprint_endline (string_of_int n);loop (n-1)end
"@
$FSharpType = Add-Type -TypeDefinition $FSharpCode -CodeDomProvider $Provider -PassThru |
   Where-Object { $_.IsPublic }
$FSharpType::loop(4)
```

```Output
4
3
2
1
```

<span data-ttu-id="70bff-177">`Add-Type` usa o parâmetro **path** para especificar um assembly e obtém os tipos no assembly.</span><span class="sxs-lookup"><span data-stu-id="70bff-177">`Add-Type` uses the **Path** parameter to specify an assembly and gets the types in the assembly.</span></span>
<span data-ttu-id="70bff-178">`New-Object` Cria uma instância do provedor de código F # e salva o resultado na `$Provider` variável.</span><span class="sxs-lookup"><span data-stu-id="70bff-178">`New-Object` creates an instance of the F# code provider and saves the result in the `$Provider` variable.</span></span> <span data-ttu-id="70bff-179">A `$FSharpCode` variável salva o código F # que define o método de **loop** .</span><span class="sxs-lookup"><span data-stu-id="70bff-179">The `$FSharpCode` variable saves the F# code that defines the **Loop** method.</span></span>

<span data-ttu-id="70bff-180">A `$FSharpType` variável armazena os resultados do `Add-Type` cmdlet que salva os tipos públicos definidos em `$FSharpCode` .</span><span class="sxs-lookup"><span data-stu-id="70bff-180">The the `$FSharpType` variable stores the results of the `Add-Type` cmdlet that saves the public types defined in `$FSharpCode`.</span></span> <span data-ttu-id="70bff-181">O parâmetro **TypeDefinition** especifica o código-fonte que define os tipos.</span><span class="sxs-lookup"><span data-stu-id="70bff-181">The **TypeDefinition** parameter specifies the source code that defines the types.</span></span> <span data-ttu-id="70bff-182">O parâmetro **CodeDomProvider** especifica o compilador de código fonte.</span><span class="sxs-lookup"><span data-stu-id="70bff-182">The **CodeDomProvider** parameter specifies the source code compiler.</span></span> <span data-ttu-id="70bff-183">O parâmetro **PassThru** direciona `Add-Type` para retornar um objeto de tempo de **execução** que representa os tipos.</span><span class="sxs-lookup"><span data-stu-id="70bff-183">The **PassThru** parameter directs `Add-Type` to return a **Runtime** object that represents the types.</span></span>
<span data-ttu-id="70bff-184">Os objetos são enviados para o pipeline para o `Where-Object` cmdlet, que retorna apenas os tipos públicos.</span><span class="sxs-lookup"><span data-stu-id="70bff-184">The objects are sent down the pipeline to the `Where-Object` cmdlet, which returns only the public types.</span></span> <span data-ttu-id="70bff-185">O cmdlet **Where-Object** é usado porque o provedor F # gera tipos não públicos para dar suporte ao tipo público resultante.</span><span class="sxs-lookup"><span data-stu-id="70bff-185">The **Where-Object** cmdlet is used because the F# provider generates non-public types to support the resulting public type.</span></span>

<span data-ttu-id="70bff-186">O método loop é chamado como um método estático do tipo armazenado na `$FSharpType` variável.</span><span class="sxs-lookup"><span data-stu-id="70bff-186">The Loop method is called as a static method of the type stored in the `$FSharpType` variable.</span></span>

## <span data-ttu-id="70bff-187">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="70bff-187">PARAMETERS</span></span>

### <span data-ttu-id="70bff-188">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="70bff-188">-AssemblyName</span></span>

<span data-ttu-id="70bff-189">Especifica o nome de um assembly que inclui os tipos.</span><span class="sxs-lookup"><span data-stu-id="70bff-189">Specifies the name of an assembly that includes the types.</span></span> <span data-ttu-id="70bff-190">`Add-Type` usa os tipos do assembly especificado.</span><span class="sxs-lookup"><span data-stu-id="70bff-190">`Add-Type` takes the types from the specified assembly.</span></span> <span data-ttu-id="70bff-191">Esse parâmetro é necessário quando você está criando tipos com base em um nome de assembly.</span><span class="sxs-lookup"><span data-stu-id="70bff-191">This parameter is required when you're creating types based on an assembly name.</span></span>

<span data-ttu-id="70bff-192">Insira o nome completo ou simples, também conhecido como o nome parcial, de um assembly.</span><span class="sxs-lookup"><span data-stu-id="70bff-192">Enter the full or simple name, also known as the partial name, of an assembly.</span></span> <span data-ttu-id="70bff-193">Caracteres curinga são permitidos no nome do assembly.</span><span class="sxs-lookup"><span data-stu-id="70bff-193">Wildcard characters are permitted in the assembly name.</span></span> <span data-ttu-id="70bff-194">Se você inserir um nome simples ou parcial, `Add-Type` o o resolverá para o nome completo e, em seguida, usará o nome completo para carregar o assembly.</span><span class="sxs-lookup"><span data-stu-id="70bff-194">If you enter a simple or partial name, `Add-Type` resolves it to the full name, and then uses the full name to load the assembly.</span></span>

<span data-ttu-id="70bff-195">Esse parâmetro não aceita um caminho ou um nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="70bff-195">This parameter doesn't accept a path or a file name.</span></span> <span data-ttu-id="70bff-196">Para inserir o caminho para o arquivo DLL (biblioteca de vínculo dinâmico) do assembly, use o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="70bff-196">To enter the path to the assembly dynamic-link library (DLL) file, use the **Path** parameter.</span></span>

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

### <span data-ttu-id="70bff-197">-CodeDomProvider</span><span class="sxs-lookup"><span data-stu-id="70bff-197">-CodeDomProvider</span></span>

<span data-ttu-id="70bff-198">Especifica um compilador ou gerador de código.</span><span class="sxs-lookup"><span data-stu-id="70bff-198">Specifies a code generator or compiler.</span></span> <span data-ttu-id="70bff-199">`Add-Type` usa o compilador especificado para compilar o código-fonte.</span><span class="sxs-lookup"><span data-stu-id="70bff-199">`Add-Type` uses the specified compiler to compile the source code.</span></span> <span data-ttu-id="70bff-200">O padrão é o compilador C#.</span><span class="sxs-lookup"><span data-stu-id="70bff-200">The default is the C# compiler.</span></span> <span data-ttu-id="70bff-201">Use esse parâmetro se você estiver usando um idioma que não pode ser especificado usando o parâmetro **Language** .</span><span class="sxs-lookup"><span data-stu-id="70bff-201">Use this parameter if you're using a language that can't be specified by using the **Language** parameter.</span></span> <span data-ttu-id="70bff-202">O **CodeDomProvider** que você especificar deve ser capaz de gerar assemblies do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="70bff-202">The **CodeDomProvider** that you specify must be able to generate assemblies from source code.</span></span>

```yaml
Type: System.CodeDom.Compiler.CodeDomProvider
Parameter Sets: FromSource, FromMember
Aliases: Provider

Required: False
Position: Named
Default value: C# compiler
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70bff-203">-Compiladorparameters</span><span class="sxs-lookup"><span data-stu-id="70bff-203">-CompilerParameters</span></span>

<span data-ttu-id="70bff-204">Especifica as opções para o compilador de código fonte.</span><span class="sxs-lookup"><span data-stu-id="70bff-204">Specifies the options for the source code compiler.</span></span> <span data-ttu-id="70bff-205">Essas opções são enviadas sem revisão para o compilador.</span><span class="sxs-lookup"><span data-stu-id="70bff-205">These options are sent to the compiler without revision.</span></span>

<span data-ttu-id="70bff-206">Esse parâmetro permite que você direcione o compilador para gerar um arquivo executável, inserir recursos ou definir opções de linha de comando, como a `/unsafe` opção.</span><span class="sxs-lookup"><span data-stu-id="70bff-206">This parameter allows you to direct the compiler to generate an executable file, embed resources, or set command-line options, such as the `/unsafe` option.</span></span> <span data-ttu-id="70bff-207">Esse parâmetro implementa a classe **CompilerParameters** , **System. CodeDom. compilador. CompilerParameters**.</span><span class="sxs-lookup"><span data-stu-id="70bff-207">This parameter implements the **CompilerParameters** class, **System.CodeDom.Compiler.CompilerParameters**.</span></span>

<span data-ttu-id="70bff-208">Você não pode usar os parâmetros **CompilerParameters** e **ReferencedAssemblies** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="70bff-208">You can't use the **CompilerParameters** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.CodeDom.Compiler.CompilerParameters
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: CP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70bff-209">-IgnoreWarnings</span><span class="sxs-lookup"><span data-stu-id="70bff-209">-IgnoreWarnings</span></span>

<span data-ttu-id="70bff-210">Ignora os avisos do compilador.</span><span class="sxs-lookup"><span data-stu-id="70bff-210">Ignores compiler warnings.</span></span> <span data-ttu-id="70bff-211">Use esse parâmetro para evitar o `Add-Type` tratamento de avisos do compilador como erros.</span><span class="sxs-lookup"><span data-stu-id="70bff-211">Use this parameter to prevent `Add-Type` from handling compiler warnings as errors.</span></span>

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

### <span data-ttu-id="70bff-212">-Idioma</span><span class="sxs-lookup"><span data-stu-id="70bff-212">-Language</span></span>

<span data-ttu-id="70bff-213">Especifica a linguagem usada no código-fonte.</span><span class="sxs-lookup"><span data-stu-id="70bff-213">Specifies the language that is used in the source code.</span></span> <span data-ttu-id="70bff-214">O `Add-Type` cmdlet usa o valor desse parâmetro para selecionar o **CodeDomProvider** apropriado.</span><span class="sxs-lookup"><span data-stu-id="70bff-214">The `Add-Type` cmdlet uses the value of this parameter to select the appropriate **CodeDomProvider**.</span></span> <span data-ttu-id="70bff-215">CSharp é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="70bff-215">CSharp is the default value.</span></span> <span data-ttu-id="70bff-216">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="70bff-216">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="70bff-217">CSharp</span><span class="sxs-lookup"><span data-stu-id="70bff-217">CSharp</span></span>
- <span data-ttu-id="70bff-218">CSharpVersion2</span><span class="sxs-lookup"><span data-stu-id="70bff-218">CSharpVersion2</span></span>
- <span data-ttu-id="70bff-219">CSharpVersion3</span><span class="sxs-lookup"><span data-stu-id="70bff-219">CSharpVersion3</span></span>
- <span data-ttu-id="70bff-220">JScript</span><span class="sxs-lookup"><span data-stu-id="70bff-220">JScript</span></span>
- <span data-ttu-id="70bff-221">VisualBasic</span><span class="sxs-lookup"><span data-stu-id="70bff-221">VisualBasic</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp, CSharpVersion2, CSharpVersion3, JScript, VisualBasic

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70bff-222">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="70bff-222">-LiteralPath</span></span>

<span data-ttu-id="70bff-223">Especifica o caminho para arquivos de código fonte ou arquivos DLL de assembly que contêm os tipos.</span><span class="sxs-lookup"><span data-stu-id="70bff-223">Specifies the path to source code files or assembly DLL files that contain the types.</span></span> <span data-ttu-id="70bff-224">Ao contrário do **caminho**, o valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="70bff-224">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="70bff-225">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="70bff-225">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="70bff-226">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="70bff-226">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="70bff-227">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="70bff-227">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70bff-228">-MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="70bff-228">-MemberDefinition</span></span>

<span data-ttu-id="70bff-229">Especifica novas propriedades ou métodos para a classe.</span><span class="sxs-lookup"><span data-stu-id="70bff-229">Specifies new properties or methods for the class.</span></span> <span data-ttu-id="70bff-230">`Add-Type` gera o código de modelo necessário para dar suporte às propriedades ou aos métodos.</span><span class="sxs-lookup"><span data-stu-id="70bff-230">`Add-Type` generates the template code that is required to support the properties or methods.</span></span>

<span data-ttu-id="70bff-231">No Windows, você pode usar esse recurso para fazer chamadas de invocação de plataforma (P/Invoke) para funções não gerenciadas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-231">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span>

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

### <span data-ttu-id="70bff-232">-Name</span><span class="sxs-lookup"><span data-stu-id="70bff-232">-Name</span></span>

<span data-ttu-id="70bff-233">Especifica o nome da classe a ser criada.</span><span class="sxs-lookup"><span data-stu-id="70bff-233">Specifies the name of the class to create.</span></span> <span data-ttu-id="70bff-234">Esse parâmetro é necessário ao gerar um tipo por meio de uma definição de membro.</span><span class="sxs-lookup"><span data-stu-id="70bff-234">This parameter is required when generating a type from a member definition.</span></span>

<span data-ttu-id="70bff-235">O nome do tipo e o namespace devem ser exclusivos dentro de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="70bff-235">The type name and namespace must be unique within a session.</span></span> <span data-ttu-id="70bff-236">Você não pode descarregar um tipo ou alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="70bff-236">You can't unload a type or change it.</span></span>
<span data-ttu-id="70bff-237">Para alterar o código de um tipo, você deve alterar o nome ou iniciar uma nova sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-237">To change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="70bff-238">Caso contrário, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="70bff-238">Otherwise, the command fails.</span></span>

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

### <span data-ttu-id="70bff-239">-Namespace</span><span class="sxs-lookup"><span data-stu-id="70bff-239">-Namespace</span></span>

<span data-ttu-id="70bff-240">Especifica um namespace para o tipo.</span><span class="sxs-lookup"><span data-stu-id="70bff-240">Specifies a namespace for the type.</span></span>

<span data-ttu-id="70bff-241">Se esse parâmetro não estiver incluído no comando, o tipo será criado no namespace **Microsoft. PowerShell. Commands. AddType. AutoGeneratedTypes** .</span><span class="sxs-lookup"><span data-stu-id="70bff-241">If this parameter isn't included in the command, the type is created in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace.</span></span> <span data-ttu-id="70bff-242">Se o parâmetro for incluído no comando com um valor de cadeia de caracteres vazio ou um valor de `$Null` , o tipo será gerado no namespace global.</span><span class="sxs-lookup"><span data-stu-id="70bff-242">If the parameter is included in the command with an empty string value or a value of `$Null`, the type is generated in the global namespace.</span></span>

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

### <span data-ttu-id="70bff-243">-OutputAssembly</span><span class="sxs-lookup"><span data-stu-id="70bff-243">-OutputAssembly</span></span>

<span data-ttu-id="70bff-244">Gera um arquivo DLL para o assembly com o nome especificado no local.</span><span class="sxs-lookup"><span data-stu-id="70bff-244">Generates a DLL file for the assembly with the specified name in the location.</span></span> <span data-ttu-id="70bff-245">Insira um caminho opcional e um nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="70bff-245">Enter an optional path and file name.</span></span> <span data-ttu-id="70bff-246">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="70bff-246">Wildcard characters are permitted.</span></span> <span data-ttu-id="70bff-247">Por padrão, `Add-Type` o gera o assembly somente na memória.</span><span class="sxs-lookup"><span data-stu-id="70bff-247">By default, `Add-Type` generates the assembly only in memory.</span></span>

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

### <span data-ttu-id="70bff-248">-OutputType</span><span class="sxs-lookup"><span data-stu-id="70bff-248">-OutputType</span></span>

<span data-ttu-id="70bff-249">Especifica o tipo de saída do assembly de saída.</span><span class="sxs-lookup"><span data-stu-id="70bff-249">Specifies the output type of the output assembly.</span></span> <span data-ttu-id="70bff-250">Por padrão, nenhum tipo de saída é especificado.</span><span class="sxs-lookup"><span data-stu-id="70bff-250">By default, no output type is specified.</span></span> <span data-ttu-id="70bff-251">Este parâmetro é válido somente quando um assembly de saída é especificado no comando.</span><span class="sxs-lookup"><span data-stu-id="70bff-251">This parameter is valid only when an output assembly is specified in the command.</span></span> <span data-ttu-id="70bff-252">Para obter mais informações sobre os valores, consulte [Enumeração OutputAssemblyType](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span><span class="sxs-lookup"><span data-stu-id="70bff-252">For more information about the values, see [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span></span>

<span data-ttu-id="70bff-253">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="70bff-253">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="70bff-254">ConsoleApplication</span><span class="sxs-lookup"><span data-stu-id="70bff-254">ConsoleApplication</span></span>
- <span data-ttu-id="70bff-255">Biblioteca</span><span class="sxs-lookup"><span data-stu-id="70bff-255">Library</span></span>
- <span data-ttu-id="70bff-256">WindowsApplication</span><span class="sxs-lookup"><span data-stu-id="70bff-256">WindowsApplication</span></span>

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

### <span data-ttu-id="70bff-257">-PassThru</span><span class="sxs-lookup"><span data-stu-id="70bff-257">-PassThru</span></span>

<span data-ttu-id="70bff-258">Retorna um objeto **System.Runtime** que representa os tipos adicionados.</span><span class="sxs-lookup"><span data-stu-id="70bff-258">Returns a **System.Runtime** object that represents the types that were added.</span></span> <span data-ttu-id="70bff-259">Por padrão, esse cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="70bff-259">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="70bff-260">-Path</span><span class="sxs-lookup"><span data-stu-id="70bff-260">-Path</span></span>

<span data-ttu-id="70bff-261">Especifica o caminho para arquivos de código fonte ou arquivos DLL de assembly que contêm os tipos.</span><span class="sxs-lookup"><span data-stu-id="70bff-261">Specifies the path to source code files or assembly DLL files that contain the types.</span></span>

<span data-ttu-id="70bff-262">Se você enviar arquivos de código-fonte, `Add-Type` o compilará o código nos arquivos e criará um assembly na memória dos tipos.</span><span class="sxs-lookup"><span data-stu-id="70bff-262">If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly of the types.</span></span> <span data-ttu-id="70bff-263">A extensão de nome de arquivo especificada no valor de **path** determina o compilador que o `Add-Type` usa.</span><span class="sxs-lookup"><span data-stu-id="70bff-263">The file name extension specified in the value of **Path** determines the compiler that `Add-Type` uses.</span></span>

<span data-ttu-id="70bff-264">Se você enviar um arquivo de assembly, `Add-Type` o usará os tipos do assembly.</span><span class="sxs-lookup"><span data-stu-id="70bff-264">If you submit an assembly file, `Add-Type` takes the types from the assembly.</span></span> <span data-ttu-id="70bff-265">Para especificar um assembly na memória ou o cache de assembly global, use o parâmetro **AssemblyName**.</span><span class="sxs-lookup"><span data-stu-id="70bff-265">To specify an in-memory assembly or the global assembly cache, use the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="70bff-266">-ReferencedAssemblies</span><span class="sxs-lookup"><span data-stu-id="70bff-266">-ReferencedAssemblies</span></span>

<span data-ttu-id="70bff-267">Especifica os assemblies dos quais depende o tipo.</span><span class="sxs-lookup"><span data-stu-id="70bff-267">Specifies the assemblies upon which the type depends.</span></span> <span data-ttu-id="70bff-268">Por padrão, o `Add-Type` faz referência a `System.dll` e `System.Management.Automation.dll` .</span><span class="sxs-lookup"><span data-stu-id="70bff-268">By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`.</span></span> <span data-ttu-id="70bff-269">Os assemblies que você especificar usando esse parâmetro são referenciados além os assemblies padrão.</span><span class="sxs-lookup"><span data-stu-id="70bff-269">The assemblies that you specify by using this parameter are referenced in addition to the default assemblies.</span></span>

<span data-ttu-id="70bff-270">Você não pode usar os parâmetros **CompilerParameters** e **ReferencedAssemblies** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="70bff-270">You can't use the **CompilerParameters** and **ReferencedAssemblies** parameters in the same command.</span></span>

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

### <span data-ttu-id="70bff-271">-TypeDefinition</span><span class="sxs-lookup"><span data-stu-id="70bff-271">-TypeDefinition</span></span>

<span data-ttu-id="70bff-272">Especifica o código-fonte que contém as definições de tipo.</span><span class="sxs-lookup"><span data-stu-id="70bff-272">Specifies the source code that contains the type definitions.</span></span> <span data-ttu-id="70bff-273">Insira o código-fonte em uma cadeia de caracteres ou cadeia de caracteres here, ou insira uma variável que contenha o código-fonte.</span><span class="sxs-lookup"><span data-stu-id="70bff-273">Enter the source code in a string or here-string, or enter a variable that contains the source code.</span></span> <span data-ttu-id="70bff-274">Para obter mais informações sobre as cadeias de caracteres aqui, consulte [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="70bff-274">For more information about here-strings, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span></span>

<span data-ttu-id="70bff-275">Inclua uma declaração de namespace em sua definição de tipo.</span><span class="sxs-lookup"><span data-stu-id="70bff-275">Include a namespace declaration in your type definition.</span></span> <span data-ttu-id="70bff-276">Se você omitir a declaração de namespace, seu tipo pode ter o mesmo nome que outro tipo ou o atalho para outro tipo, causando uma substituição não intencional.</span><span class="sxs-lookup"><span data-stu-id="70bff-276">If you omit the namespace declaration, your type might have the same name as another type or the shortcut for another type, causing an unintentional overwrite.</span></span> <span data-ttu-id="70bff-277">Por exemplo, se você definir um tipo chamado **exceção**, os scripts que usam **exceção** como o atalho para **System. Exception** falharão.</span><span class="sxs-lookup"><span data-stu-id="70bff-277">For example, if you define a type called **Exception**, scripts that use **Exception** as the shortcut for **System.Exception** will fail.</span></span>

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

### <span data-ttu-id="70bff-278">-UsingNamespace</span><span class="sxs-lookup"><span data-stu-id="70bff-278">-UsingNamespace</span></span>

<span data-ttu-id="70bff-279">Especifica outros namespaces que são necessários para a classe.</span><span class="sxs-lookup"><span data-stu-id="70bff-279">Specifies other namespaces that are required for the class.</span></span> <span data-ttu-id="70bff-280">Isso é muito parecido com a palavra-chave C#, `Using` .</span><span class="sxs-lookup"><span data-stu-id="70bff-280">This is much like the C# keyword, `Using`.</span></span>

<span data-ttu-id="70bff-281">Por padrão, `Add-Type` o faz referência ao namespace do **sistema** .</span><span class="sxs-lookup"><span data-stu-id="70bff-281">By default, `Add-Type` references the **System** namespace.</span></span> <span data-ttu-id="70bff-282">Quando o parâmetro **MemberDefinition** é usado, `Add-Type` o também faz referência ao namespace **System. Runtime. InteropServices** por padrão.</span><span class="sxs-lookup"><span data-stu-id="70bff-282">When the **MemberDefinition** parameter is used, `Add-Type` also references the **System.Runtime.InteropServices** namespace by default.</span></span> <span data-ttu-id="70bff-283">Os namespaces que você adiciona usando o parâmetro **UsingNamespace** são mencionados além dos namespaces padrão.</span><span class="sxs-lookup"><span data-stu-id="70bff-283">The namespaces that you add by using the **UsingNamespace** parameter are referenced in addition to the default namespaces.</span></span>

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

### <span data-ttu-id="70bff-284">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="70bff-284">CommonParameters</span></span>

<span data-ttu-id="70bff-285">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="70bff-285">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="70bff-286">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="70bff-286">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="70bff-287">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="70bff-287">INPUTS</span></span>

### <span data-ttu-id="70bff-288">Nenhum</span><span class="sxs-lookup"><span data-stu-id="70bff-288">None</span></span>

<span data-ttu-id="70bff-289">Você não pode enviar objetos pelo pipeline para o `Add-Type` .</span><span class="sxs-lookup"><span data-stu-id="70bff-289">You can't send objects down the pipeline to `Add-Type`.</span></span>

## <span data-ttu-id="70bff-290">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="70bff-290">OUTPUTS</span></span>

### <span data-ttu-id="70bff-291">Nenhum ou System. Type</span><span class="sxs-lookup"><span data-stu-id="70bff-291">None or System.Type</span></span>

<span data-ttu-id="70bff-292">Quando você usa o parâmetro **PassThru** , `Add-Type` retorna um objeto **System. Type** que representa o novo tipo.</span><span class="sxs-lookup"><span data-stu-id="70bff-292">When you use the **PassThru** parameter, `Add-Type` returns a **System.Type** object that represents the new type.</span></span> <span data-ttu-id="70bff-293">Caso contrário, esse cmdlet não gerará nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="70bff-293">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="70bff-294">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="70bff-294">NOTES</span></span>

<span data-ttu-id="70bff-295">Os tipos que você adiciona existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="70bff-295">The types that you add exist only in the current session.</span></span> <span data-ttu-id="70bff-296">Para usar os tipos em todas as sessões, adicione-as ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-296">To use the types in all sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="70bff-297">Para obter mais informações sobre o perfil, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="70bff-297">For more information about the profile, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="70bff-298">Os nomes de tipo e namespaces devem ser exclusivos em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="70bff-298">Type names and namespaces must be unique within a session.</span></span> <span data-ttu-id="70bff-299">Você não pode descarregar um tipo ou alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="70bff-299">You can't unload a type or change it.</span></span> <span data-ttu-id="70bff-300">Se você precisar alterar o código para um tipo, deverá alterar o nome ou iniciar uma nova sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70bff-300">If you need to change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="70bff-301">Caso contrário, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="70bff-301">Otherwise, the command fails.</span></span>

<span data-ttu-id="70bff-302">A classe **CodeDomProvider** para algumas linguagens, como IronPython e J#, não gera saída.</span><span class="sxs-lookup"><span data-stu-id="70bff-302">The **CodeDomProvider** class for some languages, such as IronPython and J#, doesn't generate output.</span></span> <span data-ttu-id="70bff-303">Como resultado, os tipos escritos nesses idiomas não podem ser usados com o `Add-Type` .</span><span class="sxs-lookup"><span data-stu-id="70bff-303">As a result, types written in these languages can't be used with `Add-Type`.</span></span>

<span data-ttu-id="70bff-304">Esse cmdlet se baseia na [classe CodeDomProvider](/dotnet/api/system.codedom.compiler.codedomprovider)Framework Microsoft .net.</span><span class="sxs-lookup"><span data-stu-id="70bff-304">This cmdlet is based on the Microsoft .NET Framework [CodeDomProvider Class](/dotnet/api/system.codedom.compiler.codedomprovider).</span></span>

## <span data-ttu-id="70bff-305">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="70bff-305">RELATED LINKS</span></span>

[<span data-ttu-id="70bff-306">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="70bff-306">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_profiles.md)

[<span data-ttu-id="70bff-307">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="70bff-307">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="70bff-308">Add-Member</span><span class="sxs-lookup"><span data-stu-id="70bff-308">Add-Member</span></span>](Add-Member.md)

[<span data-ttu-id="70bff-309">New-Object</span><span class="sxs-lookup"><span data-stu-id="70bff-309">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="70bff-310">OutputAssemblyType</span><span class="sxs-lookup"><span data-stu-id="70bff-310">OutputAssemblyType</span></span>](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[<span data-ttu-id="70bff-311">Invocação de plataforma (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="70bff-311">Platform Invoke (P/Invoke)</span></span>](/dotnet/standard/native-interop/pinvoke)

[<span data-ttu-id="70bff-312">Where-Object</span><span class="sxs-lookup"><span data-stu-id="70bff-312">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
