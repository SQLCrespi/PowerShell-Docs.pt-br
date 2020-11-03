---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-typedata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-TypeData
ms.openlocfilehash: eb7bafff1af34ef34a1b67c1fbe8f9e2db0ca7ad
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193721"
---
# <span data-ttu-id="5e9f7-103">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="5e9f7-103">Update-TypeData</span></span>

## <span data-ttu-id="5e9f7-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="5e9f7-104">Synopsis</span></span>
<span data-ttu-id="5e9f7-105">Atualiza os dados de tipo estendido na sessão.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-105">Updates the extended type data in the session.</span></span>

## <span data-ttu-id="5e9f7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e9f7-106">Syntax</span></span>

### <span data-ttu-id="5e9f7-107">Fileset (padrão)</span><span class="sxs-lookup"><span data-stu-id="5e9f7-107">FileSet (Default)</span></span>

```
Update-TypeData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="5e9f7-108">DynamicTypeSet</span><span class="sxs-lookup"><span data-stu-id="5e9f7-108">DynamicTypeSet</span></span>

```
Update-TypeData [-MemberType <PSMemberTypes>] [-MemberName <String>] [-Value <Object>]
 [-SecondValue <Object>] [-TypeConverter <Type>] [-TypeAdapter <Type>]
 [-SerializationMethod <String>] [-TargetTypeForDeserialization <Type>]
 [-SerializationDepth <Int32>] [-DefaultDisplayProperty <String>]
 [-InheritPropertySerializationSet <Nullable`1>] [-StringSerializationSource <String>]
 [-DefaultDisplayPropertySet <String[]>] [-DefaultKeyPropertySet <String[]>]
 [-PropertySerializationSet <String[]>] -TypeName <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="5e9f7-109">TypeDataSet</span><span class="sxs-lookup"><span data-stu-id="5e9f7-109">TypeDataSet</span></span>

```
Update-TypeData [-Force] [-TypeData] <TypeData[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5e9f7-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="5e9f7-110">Description</span></span>

<span data-ttu-id="5e9f7-111">O `Update-TypeData` cmdlet atualiza os dados de tipo estendido na sessão recarregando os `Types.ps1xml` arquivos na memória e adicionando novos dados de tipo estendido.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-111">The `Update-TypeData` cmdlet updates the extended type data in the session by reloading the `Types.ps1xml` files into memory and adding new extended type data.</span></span>

<span data-ttu-id="5e9f7-112">Por padrão, o PowerShell carrega dados de tipo estendido conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-112">By default, PowerShell loads extended type data as it is needed.</span></span> <span data-ttu-id="5e9f7-113">Sem parâmetros, `Update-TypeData` o recarrega todos os `Types.ps1xml` arquivos que ele carregou na sessão, incluindo os arquivos de tipo que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-113">Without parameters, `Update-TypeData` reloads all of the `Types.ps1xml` files that it has loaded in the session, including any type files that you added.</span></span> <span data-ttu-id="5e9f7-114">Você pode usar os parâmetros de `Update-TypeData` para adicionar novos arquivos de tipo e adicionar e substituir dados de tipo estendido.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-114">You can use the parameters of `Update-TypeData` to add new type files and add and replace extended type data.</span></span>

<span data-ttu-id="5e9f7-115">O `Update-TypeData` cmdlet pode ser usado para pré-carregar todos os dados de tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-115">The `Update-TypeData` cmdlet can be used to preload all type data.</span></span> <span data-ttu-id="5e9f7-116">Esse recurso é particularmente útil quando você estiver desenvolvendo tipos e desejar carregar esses novos tipos para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-116">This feature is particularly useful when you are developing types and want to load those new types for testing purposes.</span></span>

<span data-ttu-id="5e9f7-117">A partir do Windows PowerShell 3,0, você pode usar `Update-TypeData` para adicionar e substituir dados de tipo estendido na sessão sem usar um `Types.ps1xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-117">Beginning in Windows PowerShell 3.0, you can use `Update-TypeData` to add and replace extended type data in the session without using a `Types.ps1xml` file.</span></span> <span data-ttu-id="5e9f7-118">Dados de tipo adicionados dinamicamente, ou seja, sem um arquivo, são adicionados somente à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-118">Type data that is added dynamically, that is, without a file, is added only to the current session.</span></span> <span data-ttu-id="5e9f7-119">Para adicionar os dados de tipo a todas as sessões, adicione um `Update-TypeData` comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-119">To add the type data to all sessions, add an `Update-TypeData` command to your PowerShell profile.</span></span> <span data-ttu-id="5e9f7-120">Para obter mais informações, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5e9f7-120">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="5e9f7-121">Além disso, a partir do Windows PowerShell 3,0, você pode usar o `Get-TypeData` cmdlet para obter os tipos estendidos na sessão atual e o `Remove-TypeData` cmdlet para excluir tipos estendidos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-121">Also, beginning in Windows PowerShell 3.0, you can use the `Get-TypeData` cmdlet to get the extended types in the current session and the `Remove-TypeData` cmdlet to delete extended types from the current session.</span></span>

<span data-ttu-id="5e9f7-122">As exceções que ocorrem em Propriedades ou a adição de propriedades a um `Update-TypeData` comando não relatam erros.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-122">Exceptions that occur in properties, or from adding properties to an `Update-TypeData` command, do not report errors.</span></span> <span data-ttu-id="5e9f7-123">Isso é para suprimir exceções que podem ocorrer em muitos tipos comuns durante a formatação e a saída.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-123">This is to suppress exceptions that would occur in many common types during formatting and outputting.</span></span> <span data-ttu-id="5e9f7-124">Se você estiver obtendo propriedades do .NET, poderá contornar a supressão de exceções usando a sintaxe do método, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="5e9f7-124">If you are getting .NET properties, you can work around the suppression of exceptions by using method syntax instead, as shown in the following example:</span></span>

`"hello".get_Length()`

<span data-ttu-id="5e9f7-125">Observe que a sintaxe do método só pode ser usada com as propriedades do .NET.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-125">Note that method syntax can only be used with .NET properties.</span></span> <span data-ttu-id="5e9f7-126">As propriedades que são adicionadas executando o `Update-TypeData` cmdlet não podem usar a sintaxe do método.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-126">Properties that are added by running the `Update-TypeData` cmdlet cannot use method syntax.</span></span>

<span data-ttu-id="5e9f7-127">Para obter mais informações sobre os `Types.ps1xml` arquivos no PowerShell, consulte [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="5e9f7-127">For more information about the `Types.ps1xml` files in PowerShell, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

## <span data-ttu-id="5e9f7-128">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5e9f7-128">Examples</span></span>

### <span data-ttu-id="5e9f7-129">Exemplo 1: atualizar tipos estendidos</span><span class="sxs-lookup"><span data-stu-id="5e9f7-129">Example 1: Update extended types</span></span>

```powershell
Update-TypeData
```

<span data-ttu-id="5e9f7-130">Esse comando atualiza a configuração de tipo estendido dos `Types.ps1xml` arquivos que já foram usados na sessão.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-130">This command updates the extended type configuration from the `Types.ps1xml` files that have already been used in the session.</span></span>

### <span data-ttu-id="5e9f7-131">Exemplo 2: atualizar tipos várias vezes</span><span class="sxs-lookup"><span data-stu-id="5e9f7-131">Example 2: Update types multiple times</span></span>

<span data-ttu-id="5e9f7-132">Este exemplo mostra como atualizar os tipos em um arquivo de tipo várias vezes na mesma sessão.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-132">This example shows how to update the types in a type file multiple times in the same session.</span></span>

<span data-ttu-id="5e9f7-133">O primeiro comando atualiza a configuração de tipo estendido dos `Types.ps1xml` arquivos, processando os `TypesA.types.ps1xml` `TypesB.types.ps1xml` arquivos e primeiro.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-133">The first command updates the extended type configuration from the `Types.ps1xml` files, processing the `TypesA.types.ps1xml` and `TypesB.types.ps1xml` files first.</span></span>

<span data-ttu-id="5e9f7-134">O segundo comando mostra como atualizar `TypesA.types.ps1xml` novamente, como você pode fazer se adicionou ou alterou um tipo no arquivo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-134">The second command shows how to update the `TypesA.types.ps1xml` again, such as you might do if you added or changed a type in the file.</span></span> <span data-ttu-id="5e9f7-135">Você pode repetir o comando anterior para o `TypesA.types.ps1xml` arquivo ou executar um `Update-TypeData` comando sem parâmetros, pois `TypesA.types.ps1xml` já está na lista de arquivos de tipo da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-135">You can either repeat the previous command for the `TypesA.types.ps1xml` file, or run an `Update-TypeData` command without parameters, because `TypesA.types.ps1xml` is already in the type file list for the current session.</span></span>

```powershell
Update-TypeData -PrependPath TypesA.types.ps1xml, TypesB.types.ps1xml
Update-TypeData -PrependPath TypesA.types.ps1xml
```

### <span data-ttu-id="5e9f7-136">Exemplo 3: adicionar uma propriedade de script a objetos DateTime</span><span class="sxs-lookup"><span data-stu-id="5e9f7-136">Example 3: Add a script property to DateTime objects</span></span>

<span data-ttu-id="5e9f7-137">Este exemplo usa `Update-TypeData` para adicionar a propriedade de script **Quarter** aos objetos **System. DateTime** na sessão atual, como os retornados pelo `Get-Date` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-137">This example uses `Update-TypeData` to add the **Quarter** script property to **System.DateTime** objects in the current session, such as those returned by the `Get-Date` cmdlet.</span></span>

```powershell
Update-TypeData -TypeName "System.DateTime" -MemberType ScriptProperty -MemberName "Quarter" -Value {
  if ($this.Month -in @(1,2,3)) {"Q1"}
  elseif ($this.Month -in @(4,5,6)) {"Q2"}
  elseif ($this.Month -in @(7,8,9)) {"Q3"}
  else {"Q4"}
}
(Get-Date).Quarter
```

```Output
Q1
```

<span data-ttu-id="5e9f7-138">O `Update-TypeData` comando usa o parâmetro **TypeName** para especificar **o tipo System. DateTime** , o parâmetro **MemberName** para especificar um nome para a nova propriedade, a propriedade **MemberType** para especificar o tipo **ScriptProperty** e o parâmetro **Value** para especificar o script que determina o trimestre anual.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-138">The `Update-TypeData` command uses the **TypeName** parameter to specify **the System.DateTime** type, the **MemberName** parameter to specify a name for the new property, the **MemberType** property to specify the **ScriptProperty** type, and the **Value** parameter to specify the script that determines the annual quarter.</span></span>

<span data-ttu-id="5e9f7-139">O valor da propriedade **Value** é um script que calcula o trimestre atual.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-139">The value of the **Value** property is a script that calculates the current annual quarter.</span></span> <span data-ttu-id="5e9f7-140">O bloco de script usa a `$this` variável automática para representar a instância atual do objeto e o operador in para determinar se o valor de mês aparece em cada matriz de inteiros.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-140">The script block uses the `$this` automatic variable to represent the current instance of the object and the In operator to determine whether the month value appears in each integer array.</span></span> <span data-ttu-id="5e9f7-141">Para obter mais informações sobre o `-in` operador, consulte [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="5e9f7-141">For more information about the `-in` operator, see [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md).</span></span>

<span data-ttu-id="5e9f7-142">O segundo comando obtém a nova propriedade Quarter da data atual.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-142">The second command gets the new Quarter property of the current date.</span></span>

### <span data-ttu-id="5e9f7-143">Exemplo 4: atualizar um tipo que é exibido em listas por padrão</span><span class="sxs-lookup"><span data-stu-id="5e9f7-143">Example 4: Update a type that displays in lists by default</span></span>

<span data-ttu-id="5e9f7-144">Este exemplo mostra como definir as propriedades de um tipo que é exibido em listas por padrão, ou seja, quando nenhuma propriedade é especificada.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-144">This example shows how to set the properties of a type that displays in lists by default, that is, when no properties are specified.</span></span> <span data-ttu-id="5e9f7-145">Como os dados de tipo não são especificados em um `Types.ps1xml` arquivo, ele só entra em vigor na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-145">Because the type data is not specified in a `Types.ps1xml` file, it is effective only in the current session.</span></span>

```powershell
Update-TypeData -TypeName "System.DateTime" -DefaultDisplayPropertySet "DateTime, DayOfYear, Quarter"
Get-Date | Format-List
```

```Output
Thursday, March 15, 2012 12:00:00 AM
DayOfYear : 75
Quarter   : Q1
```

<span data-ttu-id="5e9f7-146">O primeiro comando usa o `Update-TypeData` cmdlet para definir as propriedades de lista padrão para o tipo **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-146">The first command uses the `Update-TypeData` cmdlet to set the default list properties for the **System.DateTime** type.</span></span> <span data-ttu-id="5e9f7-147">O comando usa o parâmetro **TypeName** para especificar o tipo e o parâmetro **DefaultDisplayPropertySet** para especificar as propriedades padrão para uma lista.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-147">The command uses the **TypeName** parameter to specify the type and the **DefaultDisplayPropertySet** parameter to specify the default properties for a list.</span></span> <span data-ttu-id="5e9f7-148">As propriedades selecionadas incluem a nova propriedade de script de **trimestre** que foi adicionada em um exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-148">The selected properties include the new **Quarter** script property that was added in a previous example.</span></span>

<span data-ttu-id="5e9f7-149">O segundo comando usa o `Get-Date` cmdlet para obter um objeto **System. DateTime** que representa a data atual.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-149">The second command uses the `Get-Date` cmdlet to get a **System.DateTime** object that represents the current date.</span></span> <span data-ttu-id="5e9f7-150">O comando usa um operador de pipeline ( `|` ) para enviar o objeto **DateTime** para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-150">The command uses a pipeline operator (`|`) to send the **DateTime** object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="5e9f7-151">Como o `Format-List` comando não especifica as propriedades a serem exibidas na lista, o PowerShell usa os valores padrão que foram estabelecidos pelo `Update-TypeData` comando.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-151">Because the `Format-List` command does not specify the properties to display in the list, PowerShell uses the default values that were established by the `Update-TypeData` command.</span></span>

### <span data-ttu-id="5e9f7-152">Exemplo 5: atualizar dados de tipo para um objeto de pipe</span><span class="sxs-lookup"><span data-stu-id="5e9f7-152">Example 5: Update type data for a piped object</span></span>

```powershell
Get-Module | Update-TypeData -MemberType ScriptProperty -MemberName "SupportsUpdatableHelp" -Value {
  if ($this.HelpInfoUri) {$True} else {$False}
}
Get-Module -ListAvailable | Format-Table Name, SupportsUpdatableHelp
```

```Output
Name                             SupportsUpdatableHelp
----                             ---------------------
Microsoft.PowerShell.Diagnostics                  True
Microsoft.PowerShell.Host                         True
Microsoft.PowerShell.Management                   True
Microsoft.PowerShell.Security                     True
Microsoft.PowerShell.Utility                      True
Microsoft.WSMan.Management                        True
PSDiagnostics                                    False
PSScheduledJob                                    True
PSWorkflow                                        True
ServerManager                                     True
TroubleshootingPack                              False
```

<span data-ttu-id="5e9f7-153">Este exemplo demonstra que, quando você canaliza um objeto para `Update-TypeData` , `Update-TypeData` adiciona dados de tipo estendido para o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-153">This example demonstrates that when you pipe an object to `Update-TypeData`, `Update-TypeData` adds extended type data for the object type.</span></span>

<span data-ttu-id="5e9f7-154">Essa técnica é mais rápida do que usar o `Get-Member` cmdlet ou o `Get-Type` método para obter o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-154">This technique is quicker than using the `Get-Member` cmdlet or the `Get-Type` method to get the object type.</span></span> <span data-ttu-id="5e9f7-155">No entanto, se você canalizar uma coleção de objetos para `Update-TypeData` , ele atualizará os dados de tipo do primeiro tipo de objeto e, em seguida, retornará um erro para todos os outros objetos na coleção, pois o membro já está definido no tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-155">However, if you pipe a collection of objects to `Update-TypeData`, it updates the type data of the first object type and then returns an error for all other objects in the collection because the member is already defined on the type.</span></span>

<span data-ttu-id="5e9f7-156">O primeiro comando usa o `Get-Module` cmdlet para obter o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-156">The first command uses the `Get-Module` cmdlet to get the PSScheduledJob module.</span></span> <span data-ttu-id="5e9f7-157">O comando canaliza o objeto de módulo para o `Update-TypeData` cmdlet, que atualiza os dados de tipo para o tipo **System. Management. Automation. PSModuleInfo** e os tipos derivados dele, como o tipo ModuleInfoGrouping que `Get-Module` retorna quando você usa o parâmetro **listAvailable** no comando.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-157">The command pipes the module object to the `Update-TypeData` cmdlet, which updates the type data for the **System.Management.Automation.PSModuleInfo** type and the types derived from it, such as the ModuleInfoGrouping type that `Get-Module` returns when you use the **ListAvailable** parameter in the command.</span></span>

<span data-ttu-id="5e9f7-158">Os `Update-TypeData` comandos adicionam a propriedade de script **SupportsUpdatableHelp** a todos os módulos importados.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-158">The `Update-TypeData` commands adds the **SupportsUpdatableHelp** script property to all imported modules.</span></span> <span data-ttu-id="5e9f7-159">O valor do parâmetro **Value** é um script que retorna `$True` se a propriedade **HelpInfoUri** do módulo for populada e `$False` , de outra forma,.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-159">The value of the **Value** parameter is a script that returns `$True` if the **HelpInfoUri** property of the module is populated and `$False` otherwise.</span></span>

<span data-ttu-id="5e9f7-160">O segundo comando canaliza os objetos de módulo do `Get-Module` para o `Format-Table` cmdlet, que exibe as propriedades **Name** e **SupportsUpdatableHelp** de todos os módulos em uma lista.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-160">The second command pipes the module objects from `Get-Module` to the `Format-Table` cmdlet, which displays the **Name** and **SupportsUpdatableHelp** properties of all modules in a list.</span></span>

## <span data-ttu-id="5e9f7-161">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5e9f7-161">Parameters</span></span>

### <span data-ttu-id="5e9f7-162">-AppendPath</span><span class="sxs-lookup"><span data-stu-id="5e9f7-162">-AppendPath</span></span>

<span data-ttu-id="5e9f7-163">Especifica o caminho para arquivos opcionais `.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-163">Specifies the path to optional `.ps1xml` files.</span></span> <span data-ttu-id="5e9f7-164">Os arquivos especificados são carregados na ordem em que estão listados depois que os arquivos internos são carregados.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-164">The specified files are loaded in the order that they are listed after the built-in files are loaded.</span></span> <span data-ttu-id="5e9f7-165">Também é possível canalizar um valor de **AppendPath** para `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-165">You can also pipe an **AppendPath** value to `Update-TypeData`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-166">-DefaultDisplayProperty</span><span class="sxs-lookup"><span data-stu-id="5e9f7-166">-DefaultDisplayProperty</span></span>

<span data-ttu-id="5e9f7-167">Especifica a propriedade do tipo que é exibido pelo `Format-Wide` cmdlet quando nenhuma outra propriedade é especificada.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-167">Specifies the property of the type that is displayed by the `Format-Wide` cmdlet when no other properties are specified.</span></span>

<span data-ttu-id="5e9f7-168">Digite o nome de uma propriedade estendida ou padrão do tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-168">Type the name of a standard or extended property of the type.</span></span> <span data-ttu-id="5e9f7-169">O valor desse parâmetro pode ser o nome de um tipo que é adicionado no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-169">The value of this parameter can be the name of a type that is added in the same command.</span></span>

<span data-ttu-id="5e9f7-170">Esse valor só é eficaz quando não há exibições amplas definidas para o tipo em um `Format.ps1xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-170">This value is effective only when there are no wide views defined for the type in a `Format.ps1xml` file.</span></span>

<span data-ttu-id="5e9f7-171">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-171">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-172">-DefaultDisplayPropertySet</span><span class="sxs-lookup"><span data-stu-id="5e9f7-172">-DefaultDisplayPropertySet</span></span>

<span data-ttu-id="5e9f7-173">Especifica uma ou mais propriedades do tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-173">Specifies one or more properties of the type.</span></span> <span data-ttu-id="5e9f7-174">Essas propriedades são exibidas pelo `Format-List` cmdlet quando nenhuma outra propriedade é especificada.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-174">These properties are displayed by the `Format-List` cmdlet when no other properties are specified.</span></span>

<span data-ttu-id="5e9f7-175">Digite os nomes das propriedades estendidas ou padrão do tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-175">Type the names of standard or extended properties of the type.</span></span> <span data-ttu-id="5e9f7-176">O valor desse parâmetro pode ser os nomes de tipos que são adicionados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-176">The value of this parameter can be the names of types that are added in the same command.</span></span>

<span data-ttu-id="5e9f7-177">Esse valor só é eficaz quando não há exibições de lista definidas para o tipo em um `Format.ps1xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-177">This value is effective only when there are no list views defined for the type in a `Format.ps1xml` file.</span></span>

<span data-ttu-id="5e9f7-178">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-178">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-179">-DefaultKeyPropertySet</span><span class="sxs-lookup"><span data-stu-id="5e9f7-179">-DefaultKeyPropertySet</span></span>

<span data-ttu-id="5e9f7-180">Especifica uma ou mais propriedades do tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-180">Specifies one or more properties of the type.</span></span> <span data-ttu-id="5e9f7-181">Essas propriedades são usadas pelos `Group-Object` `Sort-Object` cmdlets e quando nenhuma outra propriedade é especificada.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-181">These properties are used by the `Group-Object` and `Sort-Object` cmdlets when no other properties are specified.</span></span>

<span data-ttu-id="5e9f7-182">Digite os nomes das propriedades estendidas ou padrão do tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-182">Type the names of standard or extended properties of the type.</span></span> <span data-ttu-id="5e9f7-183">O valor desse parâmetro pode ser os nomes de tipos que são adicionados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-183">The value of this parameter can be the names of types that are added in the same command.</span></span>

<span data-ttu-id="5e9f7-184">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-184">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-185">-Force</span><span class="sxs-lookup"><span data-stu-id="5e9f7-185">-Force</span></span>

<span data-ttu-id="5e9f7-186">Indica que o cmdlet usa os dados de tipo especificados, mesmo que os dados de tipo já tenham sido especificados para esse tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-186">Indicates that the cmdlet uses the specified type data, even if type data has already been specified for that type.</span></span>

<span data-ttu-id="5e9f7-187">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-187">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DynamicTypeSet, TypeDataSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-188">-InheritPropertySerializationSet</span><span class="sxs-lookup"><span data-stu-id="5e9f7-188">-InheritPropertySerializationSet</span></span>

<span data-ttu-id="5e9f7-189">Indica se o conjunto de propriedades que são serializadas é herdado.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-189">Indicates whether the set of properties that are serialized is inherited.</span></span> <span data-ttu-id="5e9f7-190">O valor padrão é `$Null`.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-190">The default value is `$Null`.</span></span> <span data-ttu-id="5e9f7-191">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="5e9f7-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5e9f7-192">`$True`.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-192">`$True`.</span></span> <span data-ttu-id="5e9f7-193">O conjunto de propriedades é herdado.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-193">The property set is inherited.</span></span>
- <span data-ttu-id="5e9f7-194">`$False`.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-194">`$False`.</span></span> <span data-ttu-id="5e9f7-195">O conjunto de propriedades não é herdado.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-195">The property set is not inherited.</span></span>
- <span data-ttu-id="5e9f7-196">`$Null`.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-196">`$Null`.</span></span> <span data-ttu-id="5e9f7-197">A herança não está definida.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-197">Inheritance is not defined.</span></span>

<span data-ttu-id="5e9f7-198">Esse parâmetro é válido somente quando o valor do parâmetro **o** é `SpecificProperties` .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-198">This parameter is valid only when the value of the **SerializationMethod** parameter is `SpecificProperties`.</span></span> <span data-ttu-id="5e9f7-199">Quando o valor desse parâmetro é `$False` , o parâmetro **PropertySerializationSet** é necessário.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-199">When the value of this parameter is `$False`, the **PropertySerializationSet** parameter is required.</span></span>

<span data-ttu-id="5e9f7-200">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-200">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-201">-MemberName</span><span class="sxs-lookup"><span data-stu-id="5e9f7-201">-MemberName</span></span>

<span data-ttu-id="5e9f7-202">Especifica o nome de uma propriedade ou método.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-202">Specifies the name of a property or method.</span></span>

<span data-ttu-id="5e9f7-203">Use este parâmetro com os parâmetros **TypeName** , **MemberType** , **Value** e **SecondValue** para adicionar ou alterar uma propriedade ou método de um tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-203">Use this parameter with the **TypeName** , **MemberType** , **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="5e9f7-204">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-205">-MemberType</span><span class="sxs-lookup"><span data-stu-id="5e9f7-205">-MemberType</span></span>

<span data-ttu-id="5e9f7-206">Especifica o tipo do membro para adicionar ou alterar.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-206">Specifies the type of the member to add or change.</span></span>

<span data-ttu-id="5e9f7-207">Use este parâmetro com os parâmetros **TypeName** , **MemberType** , **Value** e **SecondValue** para adicionar ou alterar uma propriedade ou método de um tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-207">Use this parameter with the **TypeName** , **MemberType** , **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span> <span data-ttu-id="5e9f7-208">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="5e9f7-208">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5e9f7-209">AliasProperty</span><span class="sxs-lookup"><span data-stu-id="5e9f7-209">AliasProperty</span></span>
- <span data-ttu-id="5e9f7-210">CodeMethod</span><span class="sxs-lookup"><span data-stu-id="5e9f7-210">CodeMethod</span></span>
- <span data-ttu-id="5e9f7-211">CodeProperty</span><span class="sxs-lookup"><span data-stu-id="5e9f7-211">CodeProperty</span></span>
- <span data-ttu-id="5e9f7-212">NoteProperty</span><span class="sxs-lookup"><span data-stu-id="5e9f7-212">Noteproperty</span></span>
- <span data-ttu-id="5e9f7-213">ScriptMethod</span><span class="sxs-lookup"><span data-stu-id="5e9f7-213">ScriptMethod</span></span>
- <span data-ttu-id="5e9f7-214">ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="5e9f7-214">ScriptProperty</span></span>

<span data-ttu-id="5e9f7-215">Para obter informações sobre esses valores, consulte [Enumeração PSMemberTypes](/dotnet/api/system.management.automation.psmembertypes).</span><span class="sxs-lookup"><span data-stu-id="5e9f7-215">For information about these values, see [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes).</span></span>

<span data-ttu-id="5e9f7-216">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-216">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: DynamicTypeSet
Aliases:
Accepted values: NoteProperty, AliasProperty, ScriptProperty, CodeProperty, ScriptMethod, CodeMethod

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-217">-PrependPath</span><span class="sxs-lookup"><span data-stu-id="5e9f7-217">-PrependPath</span></span>

<span data-ttu-id="5e9f7-218">Especifica o caminho para os arquivos opcionais `.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-218">Specifies the path to the optional `.ps1xml` files.</span></span> <span data-ttu-id="5e9f7-219">Os arquivos especificados são carregados na ordem em que estão listados antes que os arquivos internos são carregados.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-219">The specified files are loaded in the order that they are listed before the built-in files are loaded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-220">-PropertySerializationSet</span><span class="sxs-lookup"><span data-stu-id="5e9f7-220">-PropertySerializationSet</span></span>

<span data-ttu-id="5e9f7-221">Especifica os nomes das propriedades serializadas.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-221">Specifies the names of properties that are serialized.</span></span> <span data-ttu-id="5e9f7-222">Use esse parâmetro quando o valor do parâmetro **SerializationMethod** for **SpecificProperties** .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-222">Use this parameter when the value of the **SerializationMethod** parameter is **SpecificProperties** .</span></span>

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-223">-Segundovalue</span><span class="sxs-lookup"><span data-stu-id="5e9f7-223">-SecondValue</span></span>

<span data-ttu-id="5e9f7-224">Especifica valores adicionais para os membros **AliasProperty** , **ScriptProperty** , **CodeProperty** ou **CodeMethod** .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-224">Specifies additional values for **AliasProperty** , **ScriptProperty** , **CodeProperty** , or **CodeMethod** members.</span></span>

<span data-ttu-id="5e9f7-225">Use esse parâmetro com os parâmetros **TypeName** , **MemberType** , **Value** e **SecondValue** para adicionar ou alterar uma propriedade ou um método de um tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-225">Use this parameter with the **TypeName** , **MemberType** , **Value** , and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="5e9f7-226">Quando o valor do parâmetro **MemberType** é `AliasProperty` , o valor do parâmetro **segundovalue** deve ser um tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-226">When the value of the **MemberType** parameter is `AliasProperty`, the value of the **SecondValue** parameter must be a data type.</span></span> <span data-ttu-id="5e9f7-227">O PowerShell converte (isto é, conversões) do valor da propriedade alias para o tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-227">PowerShell converts (that is, casts) the value of the alias property to the specified type.</span></span> <span data-ttu-id="5e9f7-228">Por exemplo, se você adicionar uma propriedade de alias que forneça um nome alternativo para uma propriedade de cadeia de caracteres, também poderá especificar um **segundovalue** de **System. Int32** para converter o valor de cadeia de caracteres com alias em um inteiro.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-228">For example, if you add an alias property that provides an alternate name for a string property, you can also specify a **SecondValue** of **System.Int32** to convert the aliased string value to an integer.</span></span>

<span data-ttu-id="5e9f7-229">Quando o valor do parâmetro **MemberType** é `ScriptProperty` , você pode usar o parâmetro **segundovalue** para especificar um bloco de script adicional.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-229">When the value of the **MemberType** parameter is `ScriptProperty`, you can use the **SecondValue** parameter to specify an additional script block.</span></span> <span data-ttu-id="5e9f7-230">O bloco de script no valor do parâmetro **Value** obtém o valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-230">The script block in the value of the **Value** parameter gets the value of a variable.</span></span> <span data-ttu-id="5e9f7-231">O bloco de script no valor do parâmetro **SecondValue** define o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-231">The script block in the value of the **SecondValue** parameter set the value of the variable.</span></span>

<span data-ttu-id="5e9f7-232">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-232">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-233">-SerializationDepth</span><span class="sxs-lookup"><span data-stu-id="5e9f7-233">-SerializationDepth</span></span>

<span data-ttu-id="5e9f7-234">Especifica quantos níveis de objetos de tipo são serializados como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-234">Specifies how many levels of type objects are serialized as strings.</span></span> <span data-ttu-id="5e9f7-235">O valor padrão `1` serializa o objeto e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-235">The default value `1` serializes the object and its properties.</span></span> <span data-ttu-id="5e9f7-236">Um valor `0` serializa o objeto, mas não suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-236">A value of `0` serializes the object, but not its properties.</span></span> <span data-ttu-id="5e9f7-237">Um valor `2` serializa o objeto, suas propriedades e todos os objetos em valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-237">A value of `2` serializes the object, its properties, and any objects in property values.</span></span>

<span data-ttu-id="5e9f7-238">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-238">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-239">-O</span><span class="sxs-lookup"><span data-stu-id="5e9f7-239">-SerializationMethod</span></span>

<span data-ttu-id="5e9f7-240">Especifica um método de serialização para o tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-240">Specifies a serialization method for the type.</span></span> <span data-ttu-id="5e9f7-241">Um método de serialização determina quais propriedades do tipo são serializadas e a técnica usada para serializá-las.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-241">A serialization method determines which properties of the type are serialized and the technique that is used to serialize them.</span></span> <span data-ttu-id="5e9f7-242">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="5e9f7-242">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5e9f7-243">`AllPublicProperties`.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-243">`AllPublicProperties`.</span></span> <span data-ttu-id="5e9f7-244">Serialize todas as propriedades públicas do tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-244">Serialize all public properties of the type.</span></span> <span data-ttu-id="5e9f7-245">Você pode usar o parâmetro **SerializationDepth** para determinar se as propriedades filho são serializadas.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-245">You can use the **SerializationDepth** parameter to determine whether child properties are serialized.</span></span>
- <span data-ttu-id="5e9f7-246">`String`.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-246">`String`.</span></span> <span data-ttu-id="5e9f7-247">Serialize o tipo como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-247">Serialize the type as a string.</span></span> <span data-ttu-id="5e9f7-248">Você pode usar o **StringSerializationSource** para especificar uma propriedade do tipo a ser usado como o resultado da serialização.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-248">You can use the **StringSerializationSource** to specify a property of the type to use as the serialization result.</span></span> <span data-ttu-id="5e9f7-249">Caso contrário, o tipo é serializado usando o método **ToString** do objeto.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-249">Otherwise, the type is serialized by using the **ToString** method of the object.</span></span>
- <span data-ttu-id="5e9f7-250">`SpecificProperties`.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-250">`SpecificProperties`.</span></span> <span data-ttu-id="5e9f7-251">Serialize apenas as propriedades especificadas deste tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-251">Serialize only the specified properties of this type.</span></span> <span data-ttu-id="5e9f7-252">Use o parâmetro **PropertySerializationSet** para especificar as propriedades do tipo serializado.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-252">Use the **PropertySerializationSet** parameter to specify the properties of the type that are serialized.</span></span>
  <span data-ttu-id="5e9f7-253">Você também pode usar o parâmetro **InheritPropertySerializationSet** para determinar se o conjunto de propriedades é herdado e o parâmetro **SerializationDepth** para determinar se as propriedades filho são serializadas.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-253">You can also use the **InheritPropertySerializationSet** parameter to determine whether the property set is inherited and the **SerializationDepth** parameter to determine whether child properties are serialized.</span></span>

<span data-ttu-id="5e9f7-254">No PowerShell, os métodos de serialização são armazenados em objetos internos **PSStandardMembers** .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-254">In PowerShell, serialization methods are stored in **PSStandardMembers** internal objects.</span></span>

<span data-ttu-id="5e9f7-255">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-255">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-256">-StringSerializationSource</span><span class="sxs-lookup"><span data-stu-id="5e9f7-256">-StringSerializationSource</span></span>

<span data-ttu-id="5e9f7-257">Especifica o nome de uma propriedade do tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-257">Specifies the name of a property of the type.</span></span> <span data-ttu-id="5e9f7-258">O valor da propriedade especificada é usado como o resultado da serialização.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-258">The value of specified property is used as the serialization result.</span></span> <span data-ttu-id="5e9f7-259">Esse parâmetro é válido somente quando o valor do parâmetro **o** é String.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-259">This parameter is valid only when the value of the **SerializationMethod** parameter is String.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-260">-TargetTypeForDeserialization</span><span class="sxs-lookup"><span data-stu-id="5e9f7-260">-TargetTypeForDeserialization</span></span>

<span data-ttu-id="5e9f7-261">Especifica o tipo ao qual objeto desse tipo é convertido quando desserializado.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-261">Specifies the type to which object of this type are converted when they are deserialized.</span></span>

<span data-ttu-id="5e9f7-262">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-262">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-263">-TypeAdapter</span><span class="sxs-lookup"><span data-stu-id="5e9f7-263">-TypeAdapter</span></span>

<span data-ttu-id="5e9f7-264">Especifica o tipo de um adaptador de tipo, como **Microsoft. PowerShell. CIM. CimInstanceAdapter** .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-264">Specifies the type of a type adapter, such as **Microsoft.PowerShell.Cim.CimInstanceAdapter** .</span></span> <span data-ttu-id="5e9f7-265">Um adaptador de tipo permite que o PowerShell obtenha os membros de um tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-265">A type adapter enables PowerShell to get the members of a type.</span></span>

<span data-ttu-id="5e9f7-266">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-266">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-267">-TypeConverter</span><span class="sxs-lookup"><span data-stu-id="5e9f7-267">-TypeConverter</span></span>

<span data-ttu-id="5e9f7-268">Especifica um conversor de tipos para converter valores entre tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-268">Specifies a type converter to convert values between different types.</span></span> <span data-ttu-id="5e9f7-269">Se for definido um conversor de tipo para um tipo, uma instância do conversor de tipo é usada para a conversão.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-269">If a type converter is defined for a type, an instance of the type converter is used for the conversion.</span></span>

<span data-ttu-id="5e9f7-270">Insira um **System.Type** valor derivado das classes **System.ComponentModel.TypeConverter** ou **System.Management.Automation.PSTypeConverter** .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-270">Enter a **System.Type** value that is derived from the **System.ComponentModel.TypeConverter** or **System.Management.Automation.PSTypeConverter** classes.</span></span>

<span data-ttu-id="5e9f7-271">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-272">-TypeData</span><span class="sxs-lookup"><span data-stu-id="5e9f7-272">-TypeData</span></span>

<span data-ttu-id="5e9f7-273">Especifica uma matriz do tipo de dados que esse cmdlet adiciona à sessão.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-273">Specifies an array of type data that this cmdlet adds to the session.</span></span> <span data-ttu-id="5e9f7-274">Insira uma variável que contém um objeto **TypeData** ou um comando que obtém um objeto **TypeData** , como um `Get-TypeData` comando.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-274">Enter a variable that contains a **TypeData** object or a command that gets a **TypeData** object, such as a `Get-TypeData` command.</span></span> <span data-ttu-id="5e9f7-275">Também é possível canalizar um objeto **TypeData** para `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-275">You can also pipe a **TypeData** object to `Update-TypeData`.</span></span>

<span data-ttu-id="5e9f7-276">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-276">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.TypeData[]
Parameter Sets: TypeDataSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-277">-TypeName</span><span class="sxs-lookup"><span data-stu-id="5e9f7-277">-TypeName</span></span>

<span data-ttu-id="5e9f7-278">Especifica o nome do tipo a ser estendido.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-278">Specifies the name of the type to extend.</span></span>

<span data-ttu-id="5e9f7-279">Para tipos no namespace **System** , insira o nome abreviado.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-279">For types in the **System** namespace, enter the short name.</span></span> <span data-ttu-id="5e9f7-280">Caso contrário, é necessário o nome completo do tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-280">Otherwise, the full type name is required.</span></span> <span data-ttu-id="5e9f7-281">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-281">Wildcards are not supported.</span></span>

<span data-ttu-id="5e9f7-282">Você pode canalizar nomes de tipo para `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-282">You can pipe type names to `Update-TypeData`.</span></span> <span data-ttu-id="5e9f7-283">Quando você canaliza um objeto para `Update-TypeData` , `Update-TypeData` Obtém o nome do tipo do objeto e digita os dados para o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-283">When you pipe an object to `Update-TypeData`, `Update-TypeData` gets the type name of the object and type data to the object type.</span></span>

<span data-ttu-id="5e9f7-284">Use esse parâmetro com os parâmetros **MemberName** , **MemberType** , **Value** e **SecondValue** para adicionar ou alterar uma propriedade ou um método de um tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-284">Use this parameter with the **MemberName** , **MemberType** , **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="5e9f7-285">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-285">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-286">-Value</span><span class="sxs-lookup"><span data-stu-id="5e9f7-286">-Value</span></span>

<span data-ttu-id="5e9f7-287">Especifica o valor da propriedade ou método.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-287">Specifies the value of the property or method.</span></span>

<span data-ttu-id="5e9f7-288">Se você adicionar um `AliasProperty` membro,, `CodeProperty` `ScriptProperty` ou `CodeMethod` , você poderá usar o parâmetro **segundovalue** para adicionar informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-288">If you add an `AliasProperty`, `CodeProperty`, `ScriptProperty`, or `CodeMethod` member, you can use the **SecondValue** parameter to add additional information.</span></span>

<span data-ttu-id="5e9f7-289">Use esse parâmetro com os parâmetros **MemberName** , **MemberType** , **Value** e **SecondValue** para adicionar ou alterar uma propriedade ou um método de um tipo.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-289">Use this parameter with the **MemberName** , **MemberType** , **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="5e9f7-290">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-290">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-291">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5e9f7-291">-Confirm</span></span>

<span data-ttu-id="5e9f7-292">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-292">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-293">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5e9f7-293">-WhatIf</span></span>

<span data-ttu-id="5e9f7-294">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-294">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5e9f7-295">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-295">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9f7-296">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5e9f7-296">CommonParameters</span></span>

<span data-ttu-id="5e9f7-297">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-297">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5e9f7-298">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5e9f7-298">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5e9f7-299">Entradas</span><span class="sxs-lookup"><span data-stu-id="5e9f7-299">Inputs</span></span>

### <span data-ttu-id="5e9f7-300">System.String</span><span class="sxs-lookup"><span data-stu-id="5e9f7-300">System.String</span></span>

<span data-ttu-id="5e9f7-301">É possível canalizar uma cadeia de caracteres que contém os valores dos parâmetros **AppendPath** , **TypeName** ou **TypeData** para `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="5e9f7-301">You can pipe a string that contains the values of the **AppendPath** , **TypeName** , or **TypeData** parameters to `Update-TypeData`.</span></span>

## <span data-ttu-id="5e9f7-302">Saídas</span><span class="sxs-lookup"><span data-stu-id="5e9f7-302">Outputs</span></span>

### <span data-ttu-id="5e9f7-303">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5e9f7-303">None</span></span>

<span data-ttu-id="5e9f7-304">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="5e9f7-304">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="5e9f7-305">Observações</span><span class="sxs-lookup"><span data-stu-id="5e9f7-305">Notes</span></span>

## <span data-ttu-id="5e9f7-306">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="5e9f7-306">Related links</span></span>

[<span data-ttu-id="5e9f7-307">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="5e9f7-307">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="5e9f7-308">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="5e9f7-308">Get-TypeData</span></span>](Get-TypeData.md)

[<span data-ttu-id="5e9f7-309">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="5e9f7-309">Remove-TypeData</span></span>](Remove-TypeData.md)
