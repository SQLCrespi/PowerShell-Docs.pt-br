---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-typedata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TypeData
ms.openlocfilehash: a4f7106bfeadc963a265f5fb239f9fa6bab40800
ms.sourcegitcommit: bdd0fedaf9ba534645b2f7eb1fe1241481f58715
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "105936505"
---
# <span data-ttu-id="7ed1e-102">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="7ed1e-102">Get-TypeData</span></span>

## <span data-ttu-id="7ed1e-103">Sinopse</span><span class="sxs-lookup"><span data-stu-id="7ed1e-103">Synopsis</span></span>
<span data-ttu-id="7ed1e-104">Obtém os dados de tipo estendido na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-104">Gets the extended type data in the current session.</span></span>

## <span data-ttu-id="7ed1e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7ed1e-105">Syntax</span></span>

```
Get-TypeData [[-TypeName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="7ed1e-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="7ed1e-106">Description</span></span>

<span data-ttu-id="7ed1e-107">O `Get-TypeData` cmdlet obtém os dados de tipo estendido na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-107">The `Get-TypeData` cmdlet gets the extended type data in the current session.</span></span> <span data-ttu-id="7ed1e-108">Isso inclui dados de tipo que foram adicionados à sessão por `Types.ps1xml` arquivo e dados de tipo dinâmico que foram adicionados usando o parâmetro do `Update-TypeData` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-108">This includes type data that was added to the session by `Types.ps1xml` file and dynamic type data that was added by using the parameter of the `Update-TypeData` cmdlet.</span></span>

<span data-ttu-id="7ed1e-109">Você pode usar os dados de tipo estendido que o `Get-TypeData` retorna para examinar os dados de tipo na sessão e enviá-los aos `Update-TypeData` `Remove-TypeData` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-109">You can use the extended type data that `Get-TypeData` returns to examine the type data in the session and send it to the `Update-TypeData` and `Remove-TypeData` cmdlets.</span></span>

<span data-ttu-id="7ed1e-110">Dados de tipo estendido adiciona propriedades e métodos a objetos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-110">Extended type data adds properties and methods to objects in PowerShell.</span></span> <span data-ttu-id="7ed1e-111">Você pode usar as propriedades e métodos adicionados da mesma maneira que usaria as propriedades e métodos definidos no tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-111">You can use the added properties and methods in the same ways that you would use the properties and methods that are defined in the object type.</span></span> <span data-ttu-id="7ed1e-112">No entanto, ao escrever scripts, lembre-se de que as propriedades e os métodos adicionados podem não estar presentes em todas as sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-112">However, when writing scripts, be aware that the added properties and methods might not be present in every PowerShell session.</span></span>

<span data-ttu-id="7ed1e-113">Para obter mais informações sobre `Types.ps1xml` arquivos, consulte [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="7ed1e-113">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span> <span data-ttu-id="7ed1e-114">Para obter mais informações sobre os dados de tipo dinâmico que o `Update-TypeData` cmdlet adiciona, consulte `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7ed1e-114">For more information about dynamic type data that the `Update-TypeData` cmdlet adds, see `Update-TypeData`.</span></span>

<span data-ttu-id="7ed1e-115">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-115">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="7ed1e-116">Exemplos</span><span class="sxs-lookup"><span data-stu-id="7ed1e-116">Examples</span></span>

### <span data-ttu-id="7ed1e-117">Exemplo 1: obter todos os dados de tipo estendido</span><span class="sxs-lookup"><span data-stu-id="7ed1e-117">Example 1: Get all extended type data</span></span>

<span data-ttu-id="7ed1e-118">Este exemplo obtém todos os dados de tipo estendido na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-118">This example gets all extended type data in the current session.</span></span>

 ```powershell
Get-TypeData
```

### <span data-ttu-id="7ed1e-119">Exemplo 2: obter dados de tipo por nome</span><span class="sxs-lookup"><span data-stu-id="7ed1e-119">Example 2: Get type data by name</span></span>

<span data-ttu-id="7ed1e-120">Este exemplo obtém todos os dados de tipo na sessão atual cujo nome é qualificado com "System.IO".</span><span class="sxs-lookup"><span data-stu-id="7ed1e-120">This example gets all type data in the current session whose name is qualified with "System.IO".</span></span>

```powershell
Get-TypeData -TypeName System.IO.*
```

```Output
TypeName                Members
--------                -------
System.IO.DirectoryInfo {[Mode, System.Management.Automation.Runspaces.CodePropert…
System.IO.FileInfo      {[Mode, System.Management.Automation.Runspaces.CodePropert…
```

### <span data-ttu-id="7ed1e-121">Exemplo 3: obter o bloco de script que cria um valor de propriedade</span><span class="sxs-lookup"><span data-stu-id="7ed1e-121">Example 3: Get the script block that creates a property value</span></span>

<span data-ttu-id="7ed1e-122">Este exemplo obtém o bloco de script que cria o valor da propriedade **EventID** de objetos **EventLogEntry** .</span><span class="sxs-lookup"><span data-stu-id="7ed1e-122">This example gets the script block that creates the value of the **EventID** property of **EventLogEntry** objects.</span></span>

 ```powershell
(Get-TypeData *EventLogEntry*).Members.EventID
```

```Output
GetScriptBlock                     SetScriptBlock     IsHidden Name
--------------                     --------------     -------- ----
$this.get_EventID() -band 0xFFFF                         False EventID
```

### <span data-ttu-id="7ed1e-123">Exemplo 4: obter o bloco de script que define uma propriedade para um objeto especificado</span><span class="sxs-lookup"><span data-stu-id="7ed1e-123">Example 4: Get the script block that defines a property for a specified object</span></span>

<span data-ttu-id="7ed1e-124">Este exemplo obtém o bloco de script que define a propriedade **DateTime** de objetos **System. DateTime** no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-124">This example gets the script block that defines the **DateTime** property of **System.DateTime** objects in PowerShell.</span></span>

 ```powershell
(Get-TypeData -TypeName System.DateTime).Members["DateTime"].GetScriptBlock
if ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq  "Date") {
    "{0}" -f $this.ToLongDateString()
}
elseif ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq "Time") {
    "{0}" -f  $this.ToLongTimeString()
}
else {
    "{0} {1}" -f $this.ToLongDateString(), $this.ToLongTimeString()
}
```

<span data-ttu-id="7ed1e-125">O comando usa o `Get-TypeData` cmdlet para obter os dados de tipo estendido para o tipo **System. DataTime** .</span><span class="sxs-lookup"><span data-stu-id="7ed1e-125">The command uses the `Get-TypeData` cmdlet to get the extended type data for the **System.DataTime** type.</span></span> <span data-ttu-id="7ed1e-126">O comando obtém a propriedade **Members** do objeto **TypeData**.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-126">The command gets the **Members** property of the **TypeData** object.</span></span>

<span data-ttu-id="7ed1e-127">A propriedade **Members** contém uma tabela de hash de propriedades e métodos que são definidos por dados de tipo estendido.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-127">The **Members** property contains a hash table of properties and methods that are defined by extended type data.</span></span> <span data-ttu-id="7ed1e-128">Cada chave na tabela de hash Members é um nome de propriedade ou método, e cada valor é a definição do valor de propriedade ou método.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-128">Each key in the Members hash table is a property or method name and each value is the definition of the property or method value.</span></span>

<span data-ttu-id="7ed1e-129">O comando obtém a chave **DateTime** em **Membros** e seu valor de propriedade **getscriptblock** .</span><span class="sxs-lookup"><span data-stu-id="7ed1e-129">The command gets the **DateTime** key in **Members** and its **GetScriptBlock** property value.</span></span>

<span data-ttu-id="7ed1e-130">A saída mostra o bloco de script que cria o valor da propriedade **DateTime** de cada objeto **System. DateTime** no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-130">The output shows the script block that creates the value of the **DateTime** property of every **System.DateTime** object in PowerShell.</span></span>

## <span data-ttu-id="7ed1e-131">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7ed1e-131">Parameters</span></span>

### <span data-ttu-id="7ed1e-132">-TypeName</span><span class="sxs-lookup"><span data-stu-id="7ed1e-132">-TypeName</span></span>

<span data-ttu-id="7ed1e-133">Especifica os dados de tipo como uma matriz somente para os tipos com os nomes especificados.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-133">Specifies type data as an array only for the types with the specified names.</span></span> <span data-ttu-id="7ed1e-134">Por padrão, o `Get-TypeData` Obtém todos os tipos na sessão.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-134">By default, `Get-TypeData` gets all types in the session.</span></span>

<span data-ttu-id="7ed1e-135">Insira nomes de tipo ou padrões de nome.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-135">Enter type names or a name patterns.</span></span> <span data-ttu-id="7ed1e-136">Os nomes completos ou padrões de nome com caracteres curinga são necessários, mesmo para tipos no namespace System.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-136">Full names, or name patterns with wildcard characters are required, even for types in the System namespace.</span></span> <span data-ttu-id="7ed1e-137">Há suporte para curingas e o nome do parâmetro **TypeName** é opcional.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-137">Wildcards are supported and the parameter name **TypeName** is optional.</span></span> <span data-ttu-id="7ed1e-138">Você também pode canalizar nomes de tipo para `Get-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7ed1e-138">You can also pipe type names to `Get-TypeData`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="7ed1e-139">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7ed1e-139">CommonParameters</span></span>

<span data-ttu-id="7ed1e-140">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7ed1e-141">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7ed1e-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7ed1e-142">Entradas</span><span class="sxs-lookup"><span data-stu-id="7ed1e-142">Inputs</span></span>

### <span data-ttu-id="7ed1e-143">System.String</span><span class="sxs-lookup"><span data-stu-id="7ed1e-143">System.String</span></span>

<span data-ttu-id="7ed1e-144">Você pode canalizar nomes de tipo para `Get-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7ed1e-144">You can pipe type names to `Get-TypeData`.</span></span>

## <span data-ttu-id="7ed1e-145">Saídas</span><span class="sxs-lookup"><span data-stu-id="7ed1e-145">Outputs</span></span>

### <span data-ttu-id="7ed1e-146">System. Management. Automation. Runspaces. TypeData</span><span class="sxs-lookup"><span data-stu-id="7ed1e-146">System.Management.Automation.Runspaces.TypeData</span></span>

## <span data-ttu-id="7ed1e-147">Observações</span><span class="sxs-lookup"><span data-stu-id="7ed1e-147">Notes</span></span>

<span data-ttu-id="7ed1e-148">`Get-TypeData` Obtém somente os dados de tipo estendido na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-148">`Get-TypeData` gets only the extended type data in the current session.</span></span> <span data-ttu-id="7ed1e-149">Ele não gera dados de tipo estendido presentes no computador mas que não foram adicionados à sessão atual, como tipos estendidos que são definidos em módulos que não foram importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7ed1e-149">It does not get extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="7ed1e-150">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="7ed1e-150">Related links</span></span>

[<span data-ttu-id="7ed1e-151">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="7ed1e-151">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="7ed1e-152">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="7ed1e-152">Remove-TypeData</span></span>](Remove-TypeData.md)

[<span data-ttu-id="7ed1e-153">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="7ed1e-153">Update-TypeData</span></span>](Update-TypeData.md)

