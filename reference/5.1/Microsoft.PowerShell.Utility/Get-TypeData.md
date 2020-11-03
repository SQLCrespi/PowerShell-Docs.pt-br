---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-typedata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TypeData
ms.openlocfilehash: 431b768ba909ddbd3671f03fc52789ae56c01019
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193795"
---
# <span data-ttu-id="78481-103">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="78481-103">Get-TypeData</span></span>

## <span data-ttu-id="78481-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="78481-104">Synopsis</span></span>
<span data-ttu-id="78481-105">Obtém os dados de tipo estendido na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="78481-105">Gets the extended type data in the current session.</span></span>

## <span data-ttu-id="78481-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="78481-106">Syntax</span></span>

```
Get-TypeData [[-TypeName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="78481-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="78481-107">Description</span></span>

<span data-ttu-id="78481-108">O `Get-TypeData` cmdlet obtém os dados de tipo estendido na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="78481-108">The `Get-TypeData` cmdlet gets the extended type data in the current session.</span></span> <span data-ttu-id="78481-109">Isso inclui dados de tipo que foram adicionados à sessão por `Types.ps1xml` arquivo e dados de tipo dinâmico que foram adicionados usando o parâmetro do `Update-TypeData` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="78481-109">This includes type data that was added to the session by `Types.ps1xml` file and dynamic type data that was added by using the parameter of the `Update-TypeData` cmdlet.</span></span>

<span data-ttu-id="78481-110">Você pode usar os dados de tipo estendido que o `Get-TypeData` retorna para examinar os dados de tipo na sessão e enviá-los aos `Update-TypeData` `Remove-TypeData` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="78481-110">You can use the extended type data that `Get-TypeData` returns to examine the type data in the session and send it to the `Update-TypeData` and `Remove-TypeData` cmdlets.</span></span>

<span data-ttu-id="78481-111">Dados de tipo estendido adiciona propriedades e métodos a objetos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78481-111">Extended type data adds properties and methods to objects in PowerShell.</span></span> <span data-ttu-id="78481-112">Você pode usar as propriedades e métodos adicionados da mesma maneira que usaria as propriedades e métodos definidos no tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="78481-112">You can use the added properties and methods in the same ways that you would use the properties and methods that are defined in the object type.</span></span> <span data-ttu-id="78481-113">No entanto, ao escrever scripts, lembre-se de que as propriedades e os métodos adicionados podem não estar presentes em todas as sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78481-113">However, when writing scripts, be aware that the added properties and methods might not be present in every PowerShell session.</span></span>

<span data-ttu-id="78481-114">Para obter mais informações sobre `Types.ps1xml` arquivos, consulte [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="78481-114">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span> <span data-ttu-id="78481-115">Para obter mais informações sobre os dados de tipo dinâmico que o `Update-TypeData` cmdlet adiciona, consulte `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="78481-115">For more information about dynamic type data that the `Update-TypeData` cmdlet adds, see `Update-TypeData`.</span></span>

<span data-ttu-id="78481-116">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="78481-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="78481-117">Exemplos</span><span class="sxs-lookup"><span data-stu-id="78481-117">Examples</span></span>

### <span data-ttu-id="78481-118">Exemplo 1: obter todos os dados de tipo estendido</span><span class="sxs-lookup"><span data-stu-id="78481-118">Example 1: Get all extended type data</span></span>

<span data-ttu-id="78481-119">Este exemplo obtém todos os dados de tipo estendido na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="78481-119">This example gets all extended type data in the current session.</span></span>

 ```powershell
Get-TypeData
```

### <span data-ttu-id="78481-120">Exemplo 2: obter tipos por nome</span><span class="sxs-lookup"><span data-stu-id="78481-120">Example 2: Get types by name</span></span>

<span data-ttu-id="78481-121">Este exemplo obtém todos os tipos na sessão atual que têm nomes que contêm eventos.</span><span class="sxs-lookup"><span data-stu-id="78481-121">This example gets all types in the current session that have names that contain Eventing.</span></span>

 ```powershell
"*Eventing*" | Get-TypeData
```

```Output
TypeName                                                  Members
--------                                                  -------
System.Diagnostics.Eventing.Reader.EventLogConfiguration  {}System.Diagnostics.Eventing.Reader.EventLogRecord
                                                          {}System.Diagnostics.Eventing.Reader.ProviderMetadata
                                                          {[ProviderName, System.Management.Automation.Runspaces.AliasProper...
```

### <span data-ttu-id="78481-122">Exemplo 3: obter o bloco de script que cria um valor de propriedade</span><span class="sxs-lookup"><span data-stu-id="78481-122">Example 3: Get the script block that creates a property value</span></span>

<span data-ttu-id="78481-123">Este exemplo obtém o bloco de script que cria o valor da propriedade **EventID** de objetos **EventLogEntry** .</span><span class="sxs-lookup"><span data-stu-id="78481-123">This example gets the script block that creates the value of the **EventID** property of **EventLogEntry** objects.</span></span>

 ```powershell
(Get-TypeData *EventLogEntry*).Members.EventID
```

```Output
GetScriptBlock                     SetScriptBlock     IsHidden Name
--------------                     --------------     -------- ----
$this.get_EventID() -band 0xFFFF                         False EventID
```

### <span data-ttu-id="78481-124">Exemplo 4: obter o bloco de script que define uma propriedade para um objeto especificado</span><span class="sxs-lookup"><span data-stu-id="78481-124">Example 4: Get the script block that defines a property for a specified object</span></span>

<span data-ttu-id="78481-125">Este exemplo obtém o bloco de script que define a propriedade **DateTime** de objetos **System. DateTime** no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78481-125">This example gets the script block that defines the **DateTime** property of **System.DateTime** objects in PowerShell.</span></span>

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

<span data-ttu-id="78481-126">O comando usa o `Get-TypeData` cmdlet para obter os dados de tipo estendido para o tipo **System. DataTime** .</span><span class="sxs-lookup"><span data-stu-id="78481-126">The command uses the `Get-TypeData` cmdlet to get the extended type data for the **System.DataTime** type.</span></span> <span data-ttu-id="78481-127">O comando obtém a propriedade **Members** do objeto **TypeData** .</span><span class="sxs-lookup"><span data-stu-id="78481-127">The command gets the **Members** property of the **TypeData** object.</span></span>

<span data-ttu-id="78481-128">A propriedade **Members** contém uma tabela de hash de propriedades e métodos que são definidos por dados de tipo estendido.</span><span class="sxs-lookup"><span data-stu-id="78481-128">The **Members** property contains a hash table of properties and methods that are defined by extended type data.</span></span> <span data-ttu-id="78481-129">Cada chave na tabela de hash Members é um nome de propriedade ou método, e cada valor é a definição do valor de propriedade ou método.</span><span class="sxs-lookup"><span data-stu-id="78481-129">Each key in the Members hash table is a property or method name and each value is the definition of the property or method value.</span></span>

<span data-ttu-id="78481-130">O comando obtém a chave **DateTime** em **Membros** e seu valor de propriedade **getscriptblock** .</span><span class="sxs-lookup"><span data-stu-id="78481-130">The command gets the **DateTime** key in **Members** and its **GetScriptBlock** property value.</span></span>

<span data-ttu-id="78481-131">A saída mostra o bloco de script que cria o valor da propriedade **DateTime** de cada objeto **System. DateTime** no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78481-131">The output shows the script block that creates the value of the **DateTime** property of every **System.DateTime** object in PowerShell.</span></span>

## <span data-ttu-id="78481-132">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="78481-132">Parameters</span></span>

### <span data-ttu-id="78481-133">-TypeName</span><span class="sxs-lookup"><span data-stu-id="78481-133">-TypeName</span></span>

<span data-ttu-id="78481-134">Especifica os dados de tipo como uma matriz somente para os tipos com os nomes especificados.</span><span class="sxs-lookup"><span data-stu-id="78481-134">Specifies type data as an array only for the types with the specified names.</span></span> <span data-ttu-id="78481-135">Por padrão, o `Get-TypeData` Obtém todos os tipos na sessão.</span><span class="sxs-lookup"><span data-stu-id="78481-135">By default, `Get-TypeData` gets all types in the session.</span></span>

<span data-ttu-id="78481-136">Insira nomes de tipo ou padrões de nome.</span><span class="sxs-lookup"><span data-stu-id="78481-136">Enter type names or a name patterns.</span></span> <span data-ttu-id="78481-137">Os nomes completos ou padrões de nome com caracteres curinga são necessários, mesmo para tipos no namespace System.</span><span class="sxs-lookup"><span data-stu-id="78481-137">Full names, or name patterns with wildcard characters are required, even for types in the System namespace.</span></span> <span data-ttu-id="78481-138">Há suporte para curingas e o nome do parâmetro **TypeName** é opcional.</span><span class="sxs-lookup"><span data-stu-id="78481-138">Wildcards are supported and the parameter name **TypeName** is optional.</span></span> <span data-ttu-id="78481-139">Você também pode canalizar nomes de tipo para `Get-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="78481-139">You can also pipe type names to `Get-TypeData`.</span></span>

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

### <span data-ttu-id="78481-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="78481-140">CommonParameters</span></span>

<span data-ttu-id="78481-141">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="78481-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="78481-142">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="78481-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="78481-143">Entradas</span><span class="sxs-lookup"><span data-stu-id="78481-143">Inputs</span></span>

### <span data-ttu-id="78481-144">System.String</span><span class="sxs-lookup"><span data-stu-id="78481-144">System.String</span></span>

<span data-ttu-id="78481-145">Você pode canalizar nomes de tipo para `Get-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="78481-145">You can pipe type names to `Get-TypeData`.</span></span>

## <span data-ttu-id="78481-146">Saídas</span><span class="sxs-lookup"><span data-stu-id="78481-146">Outputs</span></span>

### <span data-ttu-id="78481-147">System. Management. Automation. Runspaces. TypeData</span><span class="sxs-lookup"><span data-stu-id="78481-147">System.Management.Automation.Runspaces.TypeData</span></span>

## <span data-ttu-id="78481-148">Observações</span><span class="sxs-lookup"><span data-stu-id="78481-148">Notes</span></span>

<span data-ttu-id="78481-149">`Get-TypeData` Obtém somente os dados de tipo estendido na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="78481-149">`Get-TypeData` gets only the extended type data in the current session.</span></span> <span data-ttu-id="78481-150">Ele não gera dados de tipo estendido presentes no computador mas que não foram adicionados à sessão atual, como tipos estendidos que são definidos em módulos que não foram importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="78481-150">It does not get extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="78481-151">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="78481-151">Related links</span></span>

[<span data-ttu-id="78481-152">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="78481-152">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="78481-153">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="78481-153">Remove-TypeData</span></span>](Remove-TypeData.md)

[<span data-ttu-id="78481-154">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="78481-154">Update-TypeData</span></span>](Update-TypeData.md)
