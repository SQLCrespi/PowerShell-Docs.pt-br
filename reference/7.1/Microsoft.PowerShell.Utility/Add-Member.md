---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 4/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-member?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Member
ms.openlocfilehash: 1c07d79af1516becff86a0706906fa6ddfe03ab8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194799"
---
# <span data-ttu-id="09f99-103">Add-Member</span><span class="sxs-lookup"><span data-stu-id="09f99-103">Add-Member</span></span>

## <span data-ttu-id="09f99-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="09f99-104">SYNOPSIS</span></span>
<span data-ttu-id="09f99-105">Adiciona propriedades e métodos personalizados a uma instância de um objeto do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09f99-105">Adds custom properties and methods to an instance of a PowerShell object.</span></span>

## <span data-ttu-id="09f99-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="09f99-106">SYNTAX</span></span>

### <span data-ttu-id="09f99-107">TypeNameset (padrão)</span><span class="sxs-lookup"><span data-stu-id="09f99-107">TypeNameSet (Default)</span></span>

```
Add-Member -InputObject <PSObject> -TypeName <String> [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="09f99-108">NotePropertyMultiMemberSet</span><span class="sxs-lookup"><span data-stu-id="09f99-108">NotePropertyMultiMemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru]
 [-NotePropertyMembers] <IDictionary> [<CommonParameters>]
```

### <span data-ttu-id="09f99-109">NotePropertySingleMemberSet</span><span class="sxs-lookup"><span data-stu-id="09f99-109">NotePropertySingleMemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru] [-NotePropertyName] <String>
 [-NotePropertyValue] <Object> [<CommonParameters>]
```

### <span data-ttu-id="09f99-110">MemberSet</span><span class="sxs-lookup"><span data-stu-id="09f99-110">MemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-MemberType] <PSMemberTypes> [-Name] <String> [[-Value] <Object>]
 [[-SecondValue] <Object>] [-TypeName <String>] [-Force] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="09f99-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="09f99-111">DESCRIPTION</span></span>

<span data-ttu-id="09f99-112">O `Add-Member` cmdlet permite que você adicione Membros (Propriedades e métodos) a uma instância de um objeto do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09f99-112">The `Add-Member` cmdlet lets you add members (properties and methods) to an instance of a PowerShell object.</span></span> <span data-ttu-id="09f99-113">Por exemplo, você pode adicionar um membro NoteProperty que contém uma descrição do objeto ou um membro **ScriptMethod** que executa um script para alterar o objeto.</span><span class="sxs-lookup"><span data-stu-id="09f99-113">For instance, you can add a NoteProperty member that contains a description of the object or a **ScriptMethod** member that runs a script to change the object.</span></span>

<span data-ttu-id="09f99-114">Para usar `Add-Member` , redirecione o objeto para `Add-Member` ou use o parâmetro **InputObject** para especificar o objeto.</span><span class="sxs-lookup"><span data-stu-id="09f99-114">To use `Add-Member`, pipe the object to `Add-Member`, or use the **InputObject** parameter to specify the object.</span></span>

<span data-ttu-id="09f99-115">O parâmetro **MemberType** indica o tipo de membro que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="09f99-115">The **MemberType** parameter indicates the type of member that you want to add.</span></span> <span data-ttu-id="09f99-116">O parâmetro **Name** atribui um nome ao novo membro e o parâmetro **Value** define o valor do membro.</span><span class="sxs-lookup"><span data-stu-id="09f99-116">The **Name** parameter assigns a name to the new member, and the **Value** parameter sets the value of the member.</span></span>

<span data-ttu-id="09f99-117">As propriedades e métodos que você adiciona são acrescentados apenas à instância específica do objeto especificado por você.</span><span class="sxs-lookup"><span data-stu-id="09f99-117">The properties and methods that you add are added only to the particular instance of the object that you specify.</span></span> <span data-ttu-id="09f99-118">`Add-Member` Não altera o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="09f99-118">`Add-Member` does not change the object type.</span></span> <span data-ttu-id="09f99-119">Para criar um novo tipo de objeto, use o `Add-Type` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09f99-119">To create a new object type, use the `Add-Type` cmdlet.</span></span>

<span data-ttu-id="09f99-120">Você também pode usar o `Export-Clixml` cmdlet para salvar a instância do objeto, incluindo os membros adicionais, em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="09f99-120">You can also use the `Export-Clixml` cmdlet to save the instance of the object, including the additional members, in a file.</span></span> <span data-ttu-id="09f99-121">Em seguida, você pode usar o `Import-Clixml` cmdlet para recriar a instância do objeto a partir das informações armazenadas no arquivo exportado.</span><span class="sxs-lookup"><span data-stu-id="09f99-121">Then you can use the `Import-Clixml` cmdlet to re-create the instance of the object from the information that is stored in the exported file.</span></span>

<span data-ttu-id="09f99-122">A partir do Windows PowerShell 3,0, `Add-Member` há novos recursos que facilitam a adição de propriedades de anotação a objetos.</span><span class="sxs-lookup"><span data-stu-id="09f99-122">Beginning in Windows PowerShell 3.0, `Add-Member` has new features that make it easier to add note properties to objects.</span></span>
<span data-ttu-id="09f99-123">Você pode usar os parâmetros **NotePropertyName** e **NotePropertyValue** para definir uma propriedade de anotação ou usar o parâmetro **NotePropertyMembers** , que usa uma tabela de hash de valores e nomes de propriedades de anotação.</span><span class="sxs-lookup"><span data-stu-id="09f99-123">You can use the **NotePropertyName** and **NotePropertyValue** parameters to define a note property or use the **NotePropertyMembers** parameter, which takes a hash table of note property names and values.</span></span>

<span data-ttu-id="09f99-124">Além disso, a partir do Windows PowerShell 3.0, o parâmetro **PassThru** , que gera um objeto de saída, é necessário com menos frequência.</span><span class="sxs-lookup"><span data-stu-id="09f99-124">Also, beginning in Windows PowerShell 3.0, the **PassThru** parameter, which generates an output object, is needed less frequently.</span></span> <span data-ttu-id="09f99-125">`Add-Member` Agora adiciona os novos membros diretamente ao objeto de entrada de mais tipos.</span><span class="sxs-lookup"><span data-stu-id="09f99-125">`Add-Member` now adds the new members directly to the input object of more types.</span></span> <span data-ttu-id="09f99-126">Para obter mais informações, consulte a descrição do parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="09f99-126">For more information, see the **PassThru** parameter description.</span></span>

## <span data-ttu-id="09f99-127">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="09f99-127">EXAMPLES</span></span>

### <span data-ttu-id="09f99-128">Exemplo 1: adicionar uma propriedade de observação a um PSObject</span><span class="sxs-lookup"><span data-stu-id="09f99-128">Example 1: Add a note property to a PSObject</span></span>

<span data-ttu-id="09f99-129">O exemplo a seguir adiciona uma propriedade de observação de **status** com um valor de "Done" para o objeto **FileInfo** que representa o `Test.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="09f99-129">The following example adds a **Status** note property with a value of "Done" to the **FileInfo** object that represents the `Test.txt` file.</span></span>

<span data-ttu-id="09f99-130">O primeiro comando usa o `Get-ChildItem` cmdlet para obter um objeto **FileInfo** que representa o `Test.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="09f99-130">The first command uses the `Get-ChildItem` cmdlet to get a **FileInfo** object representing the `Test.txt` file.</span></span> <span data-ttu-id="09f99-131">Ele o salva na `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="09f99-131">It saves it in the `$a` variable.</span></span>

<span data-ttu-id="09f99-132">O segundo comando adiciona a propriedade Note ao objeto em `$a` .</span><span class="sxs-lookup"><span data-stu-id="09f99-132">The second command adds the note property to the object in `$a`.</span></span>

<span data-ttu-id="09f99-133">O terceiro comando usa a notação de ponto para obter o valor da propriedade **status** do objeto no `$a` .</span><span class="sxs-lookup"><span data-stu-id="09f99-133">The third command uses dot notation to get the value of the **Status** property of the object in `$a`.</span></span> <span data-ttu-id="09f99-134">Como mostra a saída, o valor é "Done".</span><span class="sxs-lookup"><span data-stu-id="09f99-134">As the output shows, the value is "Done".</span></span>

```powershell
$A = Get-ChildItem c:\ps-test\test.txt
$A | Add-Member -NotePropertyName Status -NotePropertyValue Done
$A.Status
```

```Output
Done
```

### <span data-ttu-id="09f99-135">Exemplo 2: adicionar uma propriedade de alias a um PSObject</span><span class="sxs-lookup"><span data-stu-id="09f99-135">Example 2: Add an alias property to a PSObject</span></span>

<span data-ttu-id="09f99-136">O exemplo a seguir adiciona uma propriedade de alias de **tamanho** ao objeto que representa o `Test.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="09f99-136">The following example adds a **Size** alias property to the object that represents the `Test.txt` file.</span></span> <span data-ttu-id="09f99-137">A nova propriedade é um alias para a propriedade **Length** .</span><span class="sxs-lookup"><span data-stu-id="09f99-137">The new property is an alias for the **Length** property.</span></span>

<span data-ttu-id="09f99-138">O primeiro comando usa o `Get-ChildItem` cmdlet para obter o `Test.txt` objeto **FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="09f99-138">The first command uses the `Get-ChildItem` cmdlet to get the `Test.txt` **FileInfo** object.</span></span>

<span data-ttu-id="09f99-139">O segundo comando adiciona a propriedade de alias de **tamanho** .</span><span class="sxs-lookup"><span data-stu-id="09f99-139">The second command adds the **Size** alias property.</span></span>
<span data-ttu-id="09f99-140">O terceiro comando usa a notação de ponto para obter o valor da nova propriedade **size** .</span><span class="sxs-lookup"><span data-stu-id="09f99-140">The third command uses dot notation to get the value of the new **Size** property.</span></span>

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$A | Add-Member -MemberType AliasProperty -Name Size -Value Length
$A.Size
```

```Output
2394
```

### <span data-ttu-id="09f99-141">Exemplo 3: adicionar uma propriedade de observação StringUse a uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="09f99-141">Example 3: Add a StringUse note property to a string</span></span>

<span data-ttu-id="09f99-142">Este exemplo adiciona a propriedade **StringUse** note a uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="09f99-142">This example adds the **StringUse** note property to a string.</span></span>
<span data-ttu-id="09f99-143">Como `Add-Member` o não pode adicionar tipos a objetos de entrada de **cadeia de caracteres** , você pode especificar o parâmetro **PassThru** para gerar um objeto de saída.</span><span class="sxs-lookup"><span data-stu-id="09f99-143">Because `Add-Member` cannot add types to **String** input objects, you can specify the **PassThru** parameter to generate an output object.</span></span> <span data-ttu-id="09f99-144">O último comando no exemplo exibe a nova propriedade.</span><span class="sxs-lookup"><span data-stu-id="09f99-144">The last command in the example displays the new property.</span></span>

<span data-ttu-id="09f99-145">Este exemplo usa o parâmetro **NotePropertyMembers** .</span><span class="sxs-lookup"><span data-stu-id="09f99-145">This example uses the **NotePropertyMembers** parameter.</span></span> <span data-ttu-id="09f99-146">O valor do parâmetro **NotePropertyMembers** é uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="09f99-146">The value of the **NotePropertyMembers** parameter is a hash table.</span></span> <span data-ttu-id="09f99-147">A chave é o nome da propriedade de observação, **StringUse** , e o valor é o valor da propriedade Note, **Display** .</span><span class="sxs-lookup"><span data-stu-id="09f99-147">The key is the note property name, **StringUse** , and the value is the note property value, **Display** .</span></span>

```powershell
$A = "A string"
$A = $A | Add-Member -NotePropertyMembers @{StringUse="Display"} -PassThru
$A.StringUse
```

```Output
Display
```

### <span data-ttu-id="09f99-148">Exemplo 4: adicionar um método de script a um objeto FileInfo</span><span class="sxs-lookup"><span data-stu-id="09f99-148">Example 4: Add a script method to a FileInfo object</span></span>

<span data-ttu-id="09f99-149">Este exemplo adiciona o método de script **SizeInMB** a um objeto **FileInfo** que calcula o tamanho do arquivo para o megabyte mais próximo.</span><span class="sxs-lookup"><span data-stu-id="09f99-149">This example adds the **SizeInMB** script method to a **FileInfo** object which calculates the file size to the nearest MegaByte.</span></span> <span data-ttu-id="09f99-150">O segundo comando cria um **scriptblock** que usa o método estático **round** do `[math]` tipo para arredondar o tamanho do arquivo para a segunda casa decimal.</span><span class="sxs-lookup"><span data-stu-id="09f99-150">The second command creates a **ScriptBlock** that uses the **Round** static method from the `[math]` type to round the file size to the second decimal place.</span></span>

<span data-ttu-id="09f99-151">O parâmetro **Value** também usa a `$This` variável automática, que representa o objeto atual.</span><span class="sxs-lookup"><span data-stu-id="09f99-151">The **Value** parameter also uses the `$This` automatic variable, which represents the current object.</span></span> <span data-ttu-id="09f99-152">A `$This` variável é válida somente em blocos de script que definem novas propriedades e métodos.</span><span class="sxs-lookup"><span data-stu-id="09f99-152">The `$This` variable is valid only in script blocks that define new properties and methods.</span></span>

<span data-ttu-id="09f99-153">O último comando usa a notação de ponto para chamar o novo método de script **SizeInMB** no objeto na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="09f99-153">The last command uses dot notation to call the new **SizeInMB** script method on the object in the `$A` variable.</span></span>

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$S = {[math]::Round(($this.Length / 1MB), 2)}
$A | Add-Member -MemberType ScriptMethod -Name "SizeInMB" -Value $S
$A.SizeInMB()
```

```Output
0.43
```

### <span data-ttu-id="09f99-154">Exemplo 5: copiar todas as propriedades de um objeto para outro</span><span class="sxs-lookup"><span data-stu-id="09f99-154">Example 5: Copy all properties of an object to another</span></span>

<span data-ttu-id="09f99-155">Esta função copia todas as propriedades de um objeto em outro objeto.</span><span class="sxs-lookup"><span data-stu-id="09f99-155">This function copies all of the properties of one object to another object.</span></span>

<span data-ttu-id="09f99-156">O `foreach` loop usa o `Get-Member` cmdlet para obter cada uma das propriedades do objeto **from** .</span><span class="sxs-lookup"><span data-stu-id="09f99-156">The `foreach` loop uses the `Get-Member` cmdlet to get each of the properties of the **From** object.</span></span> <span data-ttu-id="09f99-157">Os comandos dentro do `foreach` loop são executados em série em cada uma das propriedades.</span><span class="sxs-lookup"><span data-stu-id="09f99-157">The commands within the `foreach` loop are performed in series on each of the properties.</span></span>

<span data-ttu-id="09f99-158">O `Add-Member` comando adiciona a propriedade do objeto **de** ao objeto **to** como uma **NoteProperty** .</span><span class="sxs-lookup"><span data-stu-id="09f99-158">The `Add-Member` command adds the property of the **From** object to the **To** object as a **NoteProperty** .</span></span> <span data-ttu-id="09f99-159">O valor é copiado usando o parâmetro **Value** .</span><span class="sxs-lookup"><span data-stu-id="09f99-159">The value is copied using the **Value** parameter.</span></span> <span data-ttu-id="09f99-160">Ele usa o parâmetro **Force** para adicionar membros com o mesmo nome de membro.</span><span class="sxs-lookup"><span data-stu-id="09f99-160">It uses the **Force** parameter to add members with the same member name.</span></span>

```powershell
function Copy-Property ($From, $To)
{
    $properties = Get-Member -InputObject $From -MemberType Property
    foreach ($p in $properties)
    {
        $To | Add-Member -MemberType NoteProperty -Name $p.Name -Value $From.$($p.Name) -Force
    }
}
```

### <span data-ttu-id="09f99-161">Exemplo 6: criar um objeto personalizado</span><span class="sxs-lookup"><span data-stu-id="09f99-161">Example 6: Create a custom object</span></span>

<span data-ttu-id="09f99-162">Este exemplo cria um objeto personalizado de **ativo** .</span><span class="sxs-lookup"><span data-stu-id="09f99-162">This example creates an **Asset** custom object.</span></span>

<span data-ttu-id="09f99-163">O `New-Object` cmdlet cria um **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="09f99-163">The `New-Object` cmdlet creates a **PSObject** .</span></span> <span data-ttu-id="09f99-164">O exemplo salva o **PSObject** na `$Asset` variável.</span><span class="sxs-lookup"><span data-stu-id="09f99-164">The example saves the **PSObject** in the `$Asset` variable.</span></span>

<span data-ttu-id="09f99-165">O segundo comando usa o `[ordered]` acelerador de tipo para criar um dicionário ordenado de nomes e valores.</span><span class="sxs-lookup"><span data-stu-id="09f99-165">The second command uses the `[ordered]` type accelerator to create an ordered dictionary of names and values.</span></span> <span data-ttu-id="09f99-166">O comando salva o resultado na `$D` variável.</span><span class="sxs-lookup"><span data-stu-id="09f99-166">The command saves the result in the `$D` variable.</span></span>

<span data-ttu-id="09f99-167">O terceiro comando usa o parâmetro **NotePropertyMembers** do `Add-Member` cmdlet para adicionar o dicionário na `$D` variável ao **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="09f99-167">The third command uses the **NotePropertyMembers** parameter of the `Add-Member` cmdlet to add the dictionary in the `$D` variable to the **PSObject** .</span></span>
<span data-ttu-id="09f99-168">A propriedade **TypeName** atribui um novo nome, **ativo** , ao **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="09f99-168">The **TypeName** property assigns a new name, **Asset** , to the **PSObject** .</span></span>

<span data-ttu-id="09f99-169">O último comando canaliza o novo objeto **Asset** para o `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09f99-169">The last command pipes the new **Asset** object to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="09f99-170">A saída mostra que o objeto tem um nome de tipo de **ativo** e as propriedades de observação que definimos no dicionário ordenado.</span><span class="sxs-lookup"><span data-stu-id="09f99-170">The output shows that the object has a type name of **Asset** and the note properties that we defined in the ordered dictionary.</span></span>

```powershell
$Asset = New-Object -TypeName PSObject
$d = [ordered]@{Name="Server30";System="Server Core";PSVersion="4.0"}
$Asset | Add-Member -NotePropertyMembers $d -TypeName Asset
$Asset | Get-Member
```

```Output
   TypeName: Asset

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Name        NoteProperty System.String Name=Server30
PSVersion   NoteProperty System.String PSVersion=4.0
System      NoteProperty System.String System=Server Core
```

## <span data-ttu-id="09f99-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="09f99-171">PARAMETERS</span></span>

### <span data-ttu-id="09f99-172">-Force</span><span class="sxs-lookup"><span data-stu-id="09f99-172">-Force</span></span>

<span data-ttu-id="09f99-173">Indica que esse cmdlet adiciona um novo membro até mesmo o objeto tem um membro personalizado com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="09f99-173">Indicates that this cmdlet adds a new member even the object has a custom member with the same name.</span></span>
<span data-ttu-id="09f99-174">Você não pode usar o parâmetro **Force** para substituir um membro padrão de um tipo.</span><span class="sxs-lookup"><span data-stu-id="09f99-174">You cannot use the **Force** parameter to replace a standard member of a type.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MemberSet, NotePropertySingleMemberSet, NotePropertyMultiMemberSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="09f99-175">-InputObject</span><span class="sxs-lookup"><span data-stu-id="09f99-175">-InputObject</span></span>

<span data-ttu-id="09f99-176">Especifica o objeto ao qual o novo membro é adicionado.</span><span class="sxs-lookup"><span data-stu-id="09f99-176">Specifies the object to which the new member is added.</span></span>
<span data-ttu-id="09f99-177">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="09f99-177">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="09f99-178">-MemberType</span><span class="sxs-lookup"><span data-stu-id="09f99-178">-MemberType</span></span>

<span data-ttu-id="09f99-179">Especifica o tipo do membro a ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="09f99-179">Specifies the type of the member to add.</span></span>
<span data-ttu-id="09f99-180">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="09f99-180">This parameter is required.</span></span>
<span data-ttu-id="09f99-181">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="09f99-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="09f99-182">NoteProperty</span><span class="sxs-lookup"><span data-stu-id="09f99-182">NoteProperty</span></span>
- <span data-ttu-id="09f99-183">AliasProperty</span><span class="sxs-lookup"><span data-stu-id="09f99-183">AliasProperty</span></span>
- <span data-ttu-id="09f99-184">ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="09f99-184">ScriptProperty</span></span>
- <span data-ttu-id="09f99-185">CodeProperty</span><span class="sxs-lookup"><span data-stu-id="09f99-185">CodeProperty</span></span>
- <span data-ttu-id="09f99-186">ScriptMethod</span><span class="sxs-lookup"><span data-stu-id="09f99-186">ScriptMethod</span></span>
- <span data-ttu-id="09f99-187">CodeMethod</span><span class="sxs-lookup"><span data-stu-id="09f99-187">CodeMethod</span></span>

<span data-ttu-id="09f99-188">Para obter informações sobre esses valores, consulte [Enumeração PSMemberTypes](/dotnet/api/system.management.automation.psmembertypes) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="09f99-188">For information about these values, see [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes) in the MSDN library.</span></span>

<span data-ttu-id="09f99-189">Nem todos os objetos têm todos os tipos de membros.</span><span class="sxs-lookup"><span data-stu-id="09f99-189">Not all objects have every type of member.</span></span>
<span data-ttu-id="09f99-190">Se você especificar um tipo de membro que o objeto não tem, o PowerShell retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="09f99-190">If you specify a member type that the object does not have, PowerShell returns an error.</span></span>

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: MemberSet
Aliases: Type
Accepted values: AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, Event, Dynamic, All

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="09f99-191">-Name</span><span class="sxs-lookup"><span data-stu-id="09f99-191">-Name</span></span>

<span data-ttu-id="09f99-192">Especifica o nome do membro que este cmdlet adiciona.</span><span class="sxs-lookup"><span data-stu-id="09f99-192">Specifies the name of the member that this cmdlet adds.</span></span>

```yaml
Type: System.String
Parameter Sets: MemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="09f99-193">-NotePropertyMembers</span><span class="sxs-lookup"><span data-stu-id="09f99-193">-NotePropertyMembers</span></span>

<span data-ttu-id="09f99-194">Especifica uma tabela de hash ou dicionário ordenado de valores e nomes de propriedade de observação.</span><span class="sxs-lookup"><span data-stu-id="09f99-194">Specifies a hash table or ordered dictionary of note property names and values.</span></span>
<span data-ttu-id="09f99-195">Digite uma tabela de hash ou dicionário no qual as chaves são os nomes de propriedade de observação e os valores são valores de propriedade de observação.</span><span class="sxs-lookup"><span data-stu-id="09f99-195">Type a hash table or dictionary in which the keys are note property names and the values are note property values.</span></span>

<span data-ttu-id="09f99-196">Para obter mais informações sobre tabelas de hash e dicionários ordenados no PowerShell, consulte [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="09f99-196">For more information about hash tables and ordered dictionaries in PowerShell, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

<span data-ttu-id="09f99-197">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="09f99-197">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: NotePropertyMultiMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="09f99-198">-NotePropertyName</span><span class="sxs-lookup"><span data-stu-id="09f99-198">-NotePropertyName</span></span>

<span data-ttu-id="09f99-199">Especifica o nome da propriedade de observação.</span><span class="sxs-lookup"><span data-stu-id="09f99-199">Specifies the note property name.</span></span>

<span data-ttu-id="09f99-200">Use este parâmetro com o parâmetro **NotePropertyValue** .</span><span class="sxs-lookup"><span data-stu-id="09f99-200">Use this parameter with the **NotePropertyValue** parameter.</span></span>
<span data-ttu-id="09f99-201">Esse parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="09f99-201">This parameter is optional.</span></span>

<span data-ttu-id="09f99-202">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="09f99-202">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="09f99-203">-NotePropertyValue</span><span class="sxs-lookup"><span data-stu-id="09f99-203">-NotePropertyValue</span></span>

<span data-ttu-id="09f99-204">Especifica o valor da propriedade de observação.</span><span class="sxs-lookup"><span data-stu-id="09f99-204">Specifies the note property value.</span></span>

<span data-ttu-id="09f99-205">Use esse parâmetro com o parâmetro **NotePropertyName** .</span><span class="sxs-lookup"><span data-stu-id="09f99-205">Use this parameter with the **NotePropertyName** parameter.</span></span>
<span data-ttu-id="09f99-206">Esse parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="09f99-206">This parameter is optional.</span></span>

<span data-ttu-id="09f99-207">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="09f99-207">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="09f99-208">-PassThru</span><span class="sxs-lookup"><span data-stu-id="09f99-208">-PassThru</span></span>

<span data-ttu-id="09f99-209">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="09f99-209">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="09f99-210">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="09f99-210">By default, this cmdlet does not generate any output.</span></span>

<span data-ttu-id="09f99-211">Para a maioria dos objetos, `Add-Member` o adiciona os novos membros ao objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="09f99-211">For most objects, `Add-Member` adds the new members to the input object.</span></span>
<span data-ttu-id="09f99-212">No entanto, quando o objeto de entrada é uma cadeia de caracteres, o `Add-Member` não pode adicionar o membro ao objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="09f99-212">However, when the input object is a string, `Add-Member` cannot add the member to the input object.</span></span>
<span data-ttu-id="09f99-213">Para estes objetos, use o parâmetro **PassThru** para criar um objeto de saída.</span><span class="sxs-lookup"><span data-stu-id="09f99-213">For these objects, use the **PassThru** parameter to create an output object.</span></span>

<span data-ttu-id="09f99-214">No Windows PowerShell 2,0, `Add-Member` adicionamos membros somente ao wrapper do **PSObject** de objetos, não ao objeto.</span><span class="sxs-lookup"><span data-stu-id="09f99-214">In Windows PowerShell 2.0, `Add-Member` added members only to the **PSObject** wrapper of objects, not to the object.</span></span>
<span data-ttu-id="09f99-215">Use o parâmetro **PassThru** para criar um objeto de saída para qualquer objeto que tenha um wrapper de **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="09f99-215">Use the **PassThru** parameter to create an output object for any object that has a **PSObject** wrapper.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="09f99-216">-Segundovalue</span><span class="sxs-lookup"><span data-stu-id="09f99-216">-SecondValue</span></span>

<span data-ttu-id="09f99-217">Especifica informações opcionais adicionais sobre membros **AliasProperty** , **ScriptProperty** , **CodeProperty** ou **CodeMethod** .</span><span class="sxs-lookup"><span data-stu-id="09f99-217">Specifies optional additional information about **AliasProperty** , **ScriptProperty** , **CodeProperty** , or **CodeMethod** members.</span></span>

<span data-ttu-id="09f99-218">Se usado ao adicionar um **AliasProperty** , esse parâmetro deve ser um tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="09f99-218">If used when adding an **AliasProperty** , this parameter must be a data type.</span></span>
<span data-ttu-id="09f99-219">Uma conversão para o tipo de dados especificado é adicionada ao valor de **AliasProperty** .</span><span class="sxs-lookup"><span data-stu-id="09f99-219">A conversion to the specified data type is added to the value of the **AliasProperty** .</span></span>

<span data-ttu-id="09f99-220">Por exemplo, se você adicionar um **AliasProperty** que forneça um nome alternativo para uma propriedade de cadeia de caracteres, você também poderá especificar um parâmetro de **segundovalue** de **System. Int32** para indicar que o valor dessa propriedade de cadeia de caracteres deve ser convertido em um inteiro quando acessado usando o **AliasProperty** correspondente.</span><span class="sxs-lookup"><span data-stu-id="09f99-220">For example, if you add an **AliasProperty** that provides an alternate name for a string property, you can also specify a **SecondValue** parameter of **System.Int32** to indicate that the value of that string property should be converted to an integer when accessed by using the corresponding **AliasProperty** .</span></span>

<span data-ttu-id="09f99-221">Você pode usar o parâmetro **segundovalue** para especificar um **scriptblock** adicional ao adicionar um membro **ScriptProperty** .</span><span class="sxs-lookup"><span data-stu-id="09f99-221">You can use the **SecondValue** parameter to specify an additional **ScriptBlock** when adding a **ScriptProperty** member.</span></span> <span data-ttu-id="09f99-222">O primeiro **scriptblock** , especificado no parâmetro **Value** , é usado para obter o valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="09f99-222">The first **ScriptBlock** , specified in the **Value** parameter, is used to get the value of a variable.</span></span> <span data-ttu-id="09f99-223">O segundo **scriptblock** , especificado no parâmetro **SecondValue** , é usado para definir o valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="09f99-223">The second **ScriptBlock** , specified in the **SecondValue** parameter, is used to set the value of a variable.</span></span>

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="09f99-224">-Value</span><span class="sxs-lookup"><span data-stu-id="09f99-224">-Value</span></span>

<span data-ttu-id="09f99-225">Especifica o valor inicial do membro adicionado.</span><span class="sxs-lookup"><span data-stu-id="09f99-225">Specifies the initial value of the added member.</span></span>
<span data-ttu-id="09f99-226">Se você adicionar um membro **AliasProperty** , **CodeProperty** , **ScriptProperty** ou **CodeMethod** , poderá fornecer informações adicionais opcionais usando o parâmetro **SecondValue** .</span><span class="sxs-lookup"><span data-stu-id="09f99-226">If you add an **AliasProperty** , **CodeProperty** , **ScriptProperty** or **CodeMethod** member, you can supply optional, additional information by using the **SecondValue** parameter.</span></span>

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="09f99-227">-TypeName</span><span class="sxs-lookup"><span data-stu-id="09f99-227">-TypeName</span></span>

<span data-ttu-id="09f99-228">Especifica um nome para o tipo.</span><span class="sxs-lookup"><span data-stu-id="09f99-228">Specifies a name for the type.</span></span>

<span data-ttu-id="09f99-229">Quando o tipo é uma classe no namespace **System** ou um tipo que tem um acelerador de tipo, você pode inserir o nome curto do tipo.</span><span class="sxs-lookup"><span data-stu-id="09f99-229">When the type is a class in the **System** namespace or a type that has a type accelerator, you can enter the short name of the type.</span></span> <span data-ttu-id="09f99-230">Caso contrário, é necessário o nome completo do tipo.</span><span class="sxs-lookup"><span data-stu-id="09f99-230">Otherwise, the full type name is required.</span></span>
<span data-ttu-id="09f99-231">Esse parâmetro é efetivo somente quando **InputObject** é um **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="09f99-231">This parameter is effective only when the **InputObject** is a **PSObject** .</span></span>

<span data-ttu-id="09f99-232">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="09f99-232">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: TypeNameSet, NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet
Aliases:

Required: True (TypeNameSet), False (NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="09f99-233">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="09f99-233">CommonParameters</span></span>

<span data-ttu-id="09f99-234">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="09f99-234">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="09f99-235">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="09f99-235">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="09f99-236">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="09f99-236">INPUTS</span></span>

### <span data-ttu-id="09f99-237">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="09f99-237">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="09f99-238">É possível canalizar qualquer tipo de objeto para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09f99-238">You can pipe any object type to this cmdlet.</span></span>

## <span data-ttu-id="09f99-239">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="09f99-239">OUTPUTS</span></span>

### <span data-ttu-id="09f99-240">Nenhum ou System. Object</span><span class="sxs-lookup"><span data-stu-id="09f99-240">None or System.Object</span></span>

<span data-ttu-id="09f99-241">Quando você usa o parâmetro **PassThru** , esse cmdlet retorna o objeto recém estendido.</span><span class="sxs-lookup"><span data-stu-id="09f99-241">When you use the **PassThru** parameter, this cmdlet returns the newly-extended object.</span></span>
<span data-ttu-id="09f99-242">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="09f99-242">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="09f99-243">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="09f99-243">NOTES</span></span>

<span data-ttu-id="09f99-244">Você pode adicionar membros somente a objetos **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="09f99-244">You can add members only to **PSObject** objects.</span></span> <span data-ttu-id="09f99-245">Para determinar se um objeto é um objeto **PSObject** , use o `-is` operador.</span><span class="sxs-lookup"><span data-stu-id="09f99-245">To determine whether an object is a **PSObject** object, use the `-is` operator.</span></span>

<span data-ttu-id="09f99-246">Por exemplo, para testar um objeto armazenado na `$obj` variável, digite `$obj -is [PSObject]` .</span><span class="sxs-lookup"><span data-stu-id="09f99-246">For instance, to test an object stored in the `$obj` variable, type `$obj -is [PSObject]`.</span></span>

<span data-ttu-id="09f99-247">Os nomes dos parâmetros **MemberType** , **Name** , **Value** e **SecondValue** são opcionais.</span><span class="sxs-lookup"><span data-stu-id="09f99-247">The names of the **MemberType** , **Name** , **Value** , and **SecondValue** parameters are optional.</span></span>
<span data-ttu-id="09f99-248">Se você omitir os nomes de parâmetro, os valores de parâmetro não nomeados deverão aparecer nesta ordem: **MemberType** , **Name** , **Value** e **SecondValue** .</span><span class="sxs-lookup"><span data-stu-id="09f99-248">If you omit the parameter names, the unnamed parameter values must appear in this order: **MemberType** , **Name** , **Value** , and **SecondValue** .</span></span>

<span data-ttu-id="09f99-249">Se você incluir os nomes dos parâmetros, os parâmetros podem aparecer em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="09f99-249">If you include the parameter names, the parameters can appear in any order.</span></span>

<span data-ttu-id="09f99-250">Você pode usar a `$this` variável automática em blocos de script que definem os valores de novas propriedades e métodos.</span><span class="sxs-lookup"><span data-stu-id="09f99-250">You can use the `$this` automatic variable in script blocks that define the values of new properties and methods.</span></span>
<span data-ttu-id="09f99-251">A `$this` variável refere-se à instância do objeto ao qual as propriedades e os métodos estão sendo adicionados.</span><span class="sxs-lookup"><span data-stu-id="09f99-251">The `$this` variable refers to the instance of the object to which the properties and methods are being added.</span></span> <span data-ttu-id="09f99-252">Para obter mais informações sobre a `$this` variável, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="09f99-252">For more information about the `$this` variable, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

## <span data-ttu-id="09f99-253">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="09f99-253">RELATED LINKS</span></span>

[<span data-ttu-id="09f99-254">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="09f99-254">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="09f99-255">Get-Member</span><span class="sxs-lookup"><span data-stu-id="09f99-255">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="09f99-256">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="09f99-256">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="09f99-257">New-Object</span><span class="sxs-lookup"><span data-stu-id="09f99-257">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="09f99-258">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="09f99-258">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

