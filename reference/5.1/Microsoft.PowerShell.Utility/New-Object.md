---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Object
ms.openlocfilehash: a21fadd58ba566edfc6e484d753b53548f2b519b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193768"
---
# <span data-ttu-id="311b7-103">New-Object</span><span class="sxs-lookup"><span data-stu-id="311b7-103">New-Object</span></span>

## <span data-ttu-id="311b7-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="311b7-104">SYNOPSIS</span></span>
<span data-ttu-id="311b7-105">Cria uma instância de um objeto Microsoft .NET Framework ou COM.</span><span class="sxs-lookup"><span data-stu-id="311b7-105">Creates an instance of a Microsoft .NET Framework or COM object.</span></span>

## <span data-ttu-id="311b7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="311b7-106">SYNTAX</span></span>

### <span data-ttu-id="311b7-107">NET (padrão)</span><span class="sxs-lookup"><span data-stu-id="311b7-107">Net (Default)</span></span>

```
New-Object [-TypeName] <String> [[-ArgumentList] <Object[]>] [-Property <IDictionary>] [<CommonParameters>]
```

### <span data-ttu-id="311b7-108">Interfaces</span><span class="sxs-lookup"><span data-stu-id="311b7-108">Com</span></span>

```
New-Object [-ComObject] <String> [-Strict] [-Property <IDictionary>] [<CommonParameters>]
```

## <span data-ttu-id="311b7-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="311b7-109">DESCRIPTION</span></span>

<span data-ttu-id="311b7-110">O `New-Object` cmdlet cria uma instância de um objeto .NET Framework ou com.</span><span class="sxs-lookup"><span data-stu-id="311b7-110">The `New-Object` cmdlet creates an instance of a .NET Framework or COM object.</span></span>

<span data-ttu-id="311b7-111">Você pode especificar o tipo de uma classe do .NET Framework ou um ProgID de um objeto COM.</span><span class="sxs-lookup"><span data-stu-id="311b7-111">You can specify either the type of a .NET Framework class or a ProgID of a COM object.</span></span> <span data-ttu-id="311b7-112">Por padrão, você digita o nome totalmente qualificado de uma classe do .NET Framework e o cmdlet retorna uma referência a uma instância dessa classe.</span><span class="sxs-lookup"><span data-stu-id="311b7-112">By default, you type the fully qualified name of a .NET Framework class and the cmdlet returns a reference to an instance of that class.</span></span> <span data-ttu-id="311b7-113">Para criar uma instância de um objeto COM, use o parâmetro **ComObject** e especifique o ProgID do objeto como seu valor.</span><span class="sxs-lookup"><span data-stu-id="311b7-113">To create an instance of a COM object, use the **ComObject** parameter and specify the ProgID of the object as its value.</span></span>

## <span data-ttu-id="311b7-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="311b7-114">EXAMPLES</span></span>

### <span data-ttu-id="311b7-115">Exemplo 1: criar um objeto System. Version</span><span class="sxs-lookup"><span data-stu-id="311b7-115">Example 1: Create a System.Version object</span></span>

<span data-ttu-id="311b7-116">Este exemplo cria um objeto **System. Version** usando a cadeia de caracteres "1.2.3.4" como o construtor.</span><span class="sxs-lookup"><span data-stu-id="311b7-116">This example creates a **System.Version** object using the "1.2.3.4" string as the constructor.</span></span>

```powershell
New-Object -TypeName System.Version -ArgumentList "1.2.3.4"
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
1      2      3      4
```

### <span data-ttu-id="311b7-117">Exemplo 2: criar um objeto COM do Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="311b7-117">Example 2: Create an Internet Explorer COM object</span></span>

<span data-ttu-id="311b7-118">Este exemplo cria duas instâncias do objeto COM que representa o aplicativo do Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="311b7-118">This example creates two instances of the COM object that represents the Internet Explorer application.</span></span> <span data-ttu-id="311b7-119">A primeira instância usa a tabela de hash de parâmetro de **Propriedade** para chamar o método **Navigate2** e definir a propriedade **Visible** do objeto como `$True` para tornar o aplicativo visível.</span><span class="sxs-lookup"><span data-stu-id="311b7-119">The first instance uses the **Property** parameter hash table to call the **Navigate2** method and set the **Visible** property of the object to `$True` to make the application visible.</span></span>
<span data-ttu-id="311b7-120">A segunda instância obtém os mesmos resultados com comandos individuais.</span><span class="sxs-lookup"><span data-stu-id="311b7-120">The second instance gets the same results with individual commands.</span></span>

```powershell
$IE1 = New-Object -COMObject InternetExplorer.Application -Property @{Navigate2="www.microsoft.com"; Visible = $True}

# The following command gets the same results as the example above.
$IE2 = New-Object -COMObject InternetExplorer.Application`
$IE2.Navigate2("www.microsoft.com")`
$IE2.Visible = $True`
```

### <span data-ttu-id="311b7-121">Exemplo 3: usar o parâmetro estrito para gerar um erro de não finalização</span><span class="sxs-lookup"><span data-stu-id="311b7-121">Example 3: Use the Strict parameter to generate a non-terminating error</span></span>

<span data-ttu-id="311b7-122">Este exemplo demonstra que a adição do parâmetro **estrito** faz com que o `New-Object` cmdlet gere um erro de não finalização quando o objeto com usa um assembly de interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="311b7-122">This example demonstrates that adding the **Strict** parameter causes the `New-Object` cmdlet to generate a non-terminating error when the COM object uses an interop assembly.</span></span>

```powershell
$A = New-Object -COMObject Word.Application -Strict -Property @{Visible = $True}
```

```Output
New-Object : The object written to the pipeline is an instance of the type
"Microsoft.Office.Interop.Word.ApplicationClass" from the component's primary interop assembly. If
this type exposes different members than the IDispatch members, scripts written to work with this
object might not work if the primary interop assembly is not installed.

At line:1 char:14
+ $A = New-Object  <<<< -COM Word.Application -Strict; $a.visible=$true
```

### <span data-ttu-id="311b7-123">Exemplo 4: criar um objeto COM para gerenciar o Windows Desktop</span><span class="sxs-lookup"><span data-stu-id="311b7-123">Example 4: Create a COM object to manage Windows desktop</span></span>

<span data-ttu-id="311b7-124">Este exemplo mostra como criar e usar um objeto COM para gerenciar sua área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="311b7-124">This example shows how to create and use a COM object to manage your Windows desktop.</span></span>

<span data-ttu-id="311b7-125">O primeiro comando usa o parâmetro **ComObject** do `New-Object` cmdlet para criar um objeto com com o **shell. Application** ProgID.</span><span class="sxs-lookup"><span data-stu-id="311b7-125">The first command uses the **ComObject** parameter of the `New-Object` cmdlet to create a COM object with the **Shell.Application** ProgID.</span></span> <span data-ttu-id="311b7-126">Ele armazena o objeto resultante na `$ObjShell` variável.</span><span class="sxs-lookup"><span data-stu-id="311b7-126">It stores the resulting object in the `$ObjShell` variable.</span></span> <span data-ttu-id="311b7-127">O segundo comando canaliza a `$ObjShell` variável para o `Get-Member` cmdlet, que exibe as propriedades e os métodos do objeto com.</span><span class="sxs-lookup"><span data-stu-id="311b7-127">The second command pipes the `$ObjShell` variable to the `Get-Member` cmdlet, which displays the properties and methods of the COM object.</span></span> <span data-ttu-id="311b7-128">Entre os métodos está o método **ToggleDesktop** .</span><span class="sxs-lookup"><span data-stu-id="311b7-128">Among the methods is the **ToggleDesktop** method.</span></span> <span data-ttu-id="311b7-129">O terceiro comando chama o método **ToggleDesktop** do objeto para minimizar as janelas abertas na sua área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="311b7-129">The third command calls the **ToggleDesktop** method of the object to minimize the open windows on your desktop.</span></span>

```powershell
$Objshell = New-Object -COMObject "Shell.Application"
$objshell | Get-Member
$objshell.ToggleDesktop()
```

```Output
   TypeName: System.__ComObject#{866738b9-6cf2-4de8-8767-f794ebe74f4e}

Name                 MemberType Definition
----                 ---------- ----------
AddToRecent          Method     void AddToRecent (Variant, string)
BrowseForFolder      Method     Folder BrowseForFolder (int, string, int, Variant)
CanStartStopService  Method     Variant CanStartStopService (string)
CascadeWindows       Method     void CascadeWindows ()
ControlPanelItem     Method     void ControlPanelItem (string)
EjectPC              Method     void EjectPC ()
Explore              Method     void Explore (Variant)
ExplorerPolicy       Method     Variant ExplorerPolicy (string)
FileRun              Method     void FileRun ()
FindComputer         Method     void FindComputer ()
FindFiles            Method     void FindFiles ()
FindPrinter          Method     void FindPrinter (string, string, string)
GetSetting           Method     bool GetSetting (int)
GetSystemInformation Method     Variant GetSystemInformation (string)
Help                 Method     void Help ()
IsRestricted         Method     int IsRestricted (string, string)
IsServiceRunning     Method     Variant IsServiceRunning (string)
MinimizeAll          Method     void MinimizeAll ()
NameSpace            Method     Folder NameSpace (Variant)
Open                 Method     void Open (Variant)
RefreshMenu          Method     void RefreshMenu ()
ServiceStart         Method     Variant ServiceStart (string, Variant)
ServiceStop          Method     Variant ServiceStop (string, Variant)
SetTime              Method     void SetTime ()
ShellExecute         Method     void ShellExecute (string, Variant, Variant, Variant, Variant)
ShowBrowserBar       Method     Variant ShowBrowserBar (string, Variant)
ShutdownWindows      Method     void ShutdownWindows ()
Suspend              Method     void Suspend ()
TileHorizontally     Method     void TileHorizontally ()
TileVertically       Method     void TileVertically ()
ToggleDesktop        Method     void ToggleDesktop ()
TrayProperties       Method     void TrayProperties ()
UndoMinimizeALL      Method     void UndoMinimizeALL ()
Windows              Method     IDispatch Windows ()
WindowsSecurity      Method     void WindowsSecurity ()
WindowSwitcher       Method     void WindowSwitcher ()
Application          Property   IDispatch Application () {get}
Parent               Property   IDispatch Parent () {get}
```

### <span data-ttu-id="311b7-130">Exemplo 5: passar vários argumentos para um construtor</span><span class="sxs-lookup"><span data-stu-id="311b7-130">Example 5: Pass multiple arguments to a constructor</span></span>

<span data-ttu-id="311b7-131">Este exemplo mostra como criar um objeto com um construtor que usa vários parâmetros.</span><span class="sxs-lookup"><span data-stu-id="311b7-131">This example shows how to create an object with a constructor that takes multiple parameters.</span></span> <span data-ttu-id="311b7-132">Os parâmetros devem ser colocados em uma matriz ao usar o parâmetro **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="311b7-132">The parameters must be put in an array when using **ArgumentList** parameter.</span></span>

```powershell
$array = @('One', 'Two', 'Three')
$parameters = @{
    TypeName = 'System.Collections.Generic.HashSet[string]'
    ArgumentList = ([string[]]$array, [System.StringComparer]::OrdinalIgnoreCase)
}
$set = New-Object @parameters
```

<span data-ttu-id="311b7-133">O PowerShell associa cada membro da matriz a um parâmetro do construtor.</span><span class="sxs-lookup"><span data-stu-id="311b7-133">PowerShell binds each member of the array to a parameter of the constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="311b7-134">Este exemplo usa o parâmetro nivelamento para facilitar a leitura.</span><span class="sxs-lookup"><span data-stu-id="311b7-134">This example uses parameter splatting for readability.</span></span> <span data-ttu-id="311b7-135">Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="311b7-135">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

### <span data-ttu-id="311b7-136">Exemplo 6: chamando um construtor que usa uma matriz como um único parâmetro</span><span class="sxs-lookup"><span data-stu-id="311b7-136">Example 6: Calling a constructor that takes an array as a single parameter</span></span>

<span data-ttu-id="311b7-137">Este exemplo mostra como criar um objeto com um construtor que usa um parâmetro que é uma matriz ou coleção.</span><span class="sxs-lookup"><span data-stu-id="311b7-137">This example shows how to create an object with a constructor that takes a parameter that is an array or collection.</span></span> <span data-ttu-id="311b7-138">O parâmetro de matriz deve ser colocado em um encapsulamento dentro de outra matriz.</span><span class="sxs-lookup"><span data-stu-id="311b7-138">The array parameter must be put in wrapped inside another array.</span></span>

```powershell
$array = @('One', 'Two', 'Three')
# This command throws an exception.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList $array
# This command succeeds.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList (,[string[]]$array)
$set
```

```Output
New-Object : Cannot find an overload for "HashSet`1" and the argument count: "3".
At line:1 char:8
+ $set = New-Object -TypeName 'System.Collections.Generic.HashSet[strin ...
+        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidOperation: (:) [New-Object], MethodException
+ FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Commands.NewObjectCommand

One
Two
Three
```

<span data-ttu-id="311b7-139">A primeira tentativa de criar o objeto neste exemplo falha.</span><span class="sxs-lookup"><span data-stu-id="311b7-139">The first attempt to create the object in this example fails.</span></span> <span data-ttu-id="311b7-140">O PowerShell tentou associar os três membros de `$array` aos parâmetros do Construtor, mas o construtor não ocupa três parâmetros.</span><span class="sxs-lookup"><span data-stu-id="311b7-140">PowerShell attempted to bind the three members of `$array` to parameters of the constructor but the constructor does not take three parameter.</span></span> <span data-ttu-id="311b7-141">O encapsulamento `$array` em outra matriz impede que o PowerShell tente associar os três membros de `$array` aos parâmetros do construtor.</span><span class="sxs-lookup"><span data-stu-id="311b7-141">Wrapping `$array` in another array prevents PowerShell from attempting to bind the three members of `$array` to parameters of the constructor.</span></span>

## <span data-ttu-id="311b7-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="311b7-142">PARAMETERS</span></span>

### <span data-ttu-id="311b7-143">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="311b7-143">-ArgumentList</span></span>

<span data-ttu-id="311b7-144">Especifica uma matriz de argumentos a serem passados para o construtor da classe .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="311b7-144">Specifies an array of arguments to pass to the constructor of the .NET Framework class.</span></span> <span data-ttu-id="311b7-145">Se o construtor usa um único parâmetro que é uma matriz, você deve encapsular esse parâmetro dentro de outra matriz.</span><span class="sxs-lookup"><span data-stu-id="311b7-145">If the constructor takes a single parameter that is an array, you must wrap that parameter inside another array.</span></span> <span data-ttu-id="311b7-146">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="311b7-146">For example:</span></span>

`$cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate -ArgumentList (,$bytes)`

<span data-ttu-id="311b7-147">Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="311b7-147">For more information about the behavior of **ArgumentList** , see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="311b7-148">O alias para **ArgumentList** é **Args** .</span><span class="sxs-lookup"><span data-stu-id="311b7-148">The alias for **ArgumentList** is **Args** .</span></span>

```yaml
Type: System.Object[]
Parameter Sets: Net
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="311b7-149">-ComObject</span><span class="sxs-lookup"><span data-stu-id="311b7-149">-ComObject</span></span>

<span data-ttu-id="311b7-150">Especifica o identificador programático (ProgID) do objeto COM.</span><span class="sxs-lookup"><span data-stu-id="311b7-150">Specifies the programmatic identifier (ProgID) of the COM object.</span></span>

```yaml
Type: System.String
Parameter Sets: Com
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="311b7-151">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="311b7-151">-Property</span></span>

<span data-ttu-id="311b7-152">Define valores de propriedade e invoca métodos do novo objeto.</span><span class="sxs-lookup"><span data-stu-id="311b7-152">Sets property values and invokes methods of the new object.</span></span>

<span data-ttu-id="311b7-153">Insira uma tabela de hash na qual as chaves são os nomes das propriedades ou métodos e os valores são valores de propriedade ou argumentos de método.</span><span class="sxs-lookup"><span data-stu-id="311b7-153">Enter a hash table in which the keys are the names of properties or methods and the values are property values or method arguments.</span></span> <span data-ttu-id="311b7-154">`New-Object` cria o objeto e define cada valor de propriedade e invoca cada método na ordem em que eles aparecem na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="311b7-154">`New-Object` creates the object and sets each property value and invokes each method in the order that they appear in the hash table.</span></span>

<span data-ttu-id="311b7-155">Se o novo objeto for derivado da classe **PSObject** e você especificar uma propriedade que não exista no objeto, `New-Object` o adicionará a propriedade especificada ao objeto como uma NoteProperty.</span><span class="sxs-lookup"><span data-stu-id="311b7-155">If the new object is derived from the **PSObject** class, and you specify a property that does not exist on the object, `New-Object` adds the specified property to the object as a NoteProperty.</span></span> <span data-ttu-id="311b7-156">Se o objeto não for um **PSObject** , o comando gerará um erro de não finalização.</span><span class="sxs-lookup"><span data-stu-id="311b7-156">If the object is not a **PSObject** , the command generates a non-terminating error.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="311b7-157">-Estrito</span><span class="sxs-lookup"><span data-stu-id="311b7-157">-Strict</span></span>

<span data-ttu-id="311b7-158">Indica que o cmdlet gera um erro de não finalização quando um objeto COM que você tenta criar usa um assembly de interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="311b7-158">Indicates that the cmdlet generates a non-terminating error when a COM object that you attempt to create uses an interop assembly.</span></span> <span data-ttu-id="311b7-159">Esse recurso distingue objetos reais de objetos do .NET Framework com COM callable wrappers.</span><span class="sxs-lookup"><span data-stu-id="311b7-159">This feature distinguishes actual COM objects from .NET Framework objects with COM-callable wrappers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Com
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="311b7-160">-TypeName</span><span class="sxs-lookup"><span data-stu-id="311b7-160">-TypeName</span></span>

<span data-ttu-id="311b7-161">Especifica o nome totalmente qualificado da classe do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="311b7-161">Specifies the fully qualified name of the .NET Framework class.</span></span> <span data-ttu-id="311b7-162">Você não pode especificar o parâmetro **TypeName** e o parâmetro **ComObject** .</span><span class="sxs-lookup"><span data-stu-id="311b7-162">You cannot specify both the **TypeName** parameter and the **ComObject** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: Net
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="311b7-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="311b7-163">CommonParameters</span></span>

<span data-ttu-id="311b7-164">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="311b7-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="311b7-165">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="311b7-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="311b7-166">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="311b7-166">INPUTS</span></span>

### <span data-ttu-id="311b7-167">Nenhum</span><span class="sxs-lookup"><span data-stu-id="311b7-167">None</span></span>

<span data-ttu-id="311b7-168">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="311b7-168">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="311b7-169">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="311b7-169">OUTPUTS</span></span>

### <span data-ttu-id="311b7-170">Objeto</span><span class="sxs-lookup"><span data-stu-id="311b7-170">Object</span></span>

<span data-ttu-id="311b7-171">`New-Object` Retorna o objeto que é criado.</span><span class="sxs-lookup"><span data-stu-id="311b7-171">`New-Object` returns the object that is created.</span></span>

## <span data-ttu-id="311b7-172">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="311b7-172">NOTES</span></span>

- <span data-ttu-id="311b7-173">`New-Object` fornece a funcionalidade mais comumente usada da função do VBScript CreateObject.</span><span class="sxs-lookup"><span data-stu-id="311b7-173">`New-Object` provides the most commonly-used functionality of the VBScript CreateObject function.</span></span> <span data-ttu-id="311b7-174">Uma instrução como `Set objShell = CreateObject("Shell.Application")` no VBScript pode ser convertida em `$objShell = New-Object -COMObject "Shell.Application"` no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="311b7-174">A statement like `Set objShell = CreateObject("Shell.Application")` in VBScript can be translated to `$objShell = New-Object -COMObject "Shell.Application"` in PowerShell.</span></span>
- <span data-ttu-id="311b7-175">`New-Object` expande sobre a funcionalidade disponível no ambiente do Windows Script Host, facilitando o trabalho com .NET Framework objetos da linha de comando e em scripts.</span><span class="sxs-lookup"><span data-stu-id="311b7-175">`New-Object` expands upon the functionality available in the Windows Script Host environment by making it easy to work with .NET Framework objects from the command line and within scripts.</span></span>

## <span data-ttu-id="311b7-176">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="311b7-176">RELATED LINKS</span></span>

[<span data-ttu-id="311b7-177">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="311b7-177">about_Object_Creation</span></span>](../Microsoft.PowerShell.Core/About/about_Object_Creation.md)

[<span data-ttu-id="311b7-178">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="311b7-178">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="311b7-179">Group-Object</span><span class="sxs-lookup"><span data-stu-id="311b7-179">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="311b7-180">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="311b7-180">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="311b7-181">Select-Object</span><span class="sxs-lookup"><span data-stu-id="311b7-181">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="311b7-182">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="311b7-182">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="311b7-183">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="311b7-183">Tee-Object</span></span>](Tee-Object.md)
