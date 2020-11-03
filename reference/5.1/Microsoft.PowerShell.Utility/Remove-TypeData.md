---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-typedata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-TypeData
ms.openlocfilehash: 5ba104eb3183916891d9fbf560dac2ecc4a9f6b6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193750"
---
# <span data-ttu-id="d1865-103">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="d1865-103">Remove-TypeData</span></span>

## <span data-ttu-id="d1865-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="d1865-104">Synopsis</span></span>
<span data-ttu-id="d1865-105">Exclui tipos estendidos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d1865-105">Deletes extended types from the current session.</span></span>

## <span data-ttu-id="d1865-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1865-106">Syntax</span></span>

### <span data-ttu-id="d1865-107">RemoveTypeDataSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="d1865-107">RemoveTypeDataSet (Default)</span></span>

```
Remove-TypeData -TypeData <TypeData> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d1865-108">RemoveTypeSet</span><span class="sxs-lookup"><span data-stu-id="d1865-108">RemoveTypeSet</span></span>

```
Remove-TypeData [-TypeName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d1865-109">Removeset</span><span class="sxs-lookup"><span data-stu-id="d1865-109">RemoveFileSet</span></span>

```
Remove-TypeData -Path <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d1865-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d1865-110">DESCRIPTION</span></span>

<span data-ttu-id="d1865-111">O `Remove-TypeData` cmdlet exclui dados de tipo estendido da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d1865-111">The `Remove-TypeData` cmdlet deletes extended type data from the current session.</span></span> <span data-ttu-id="d1865-112">Este cmdlet afeta somente a sessão atual e as sessões que são criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d1865-112">This cmdlet affects only the current session and sessions that are created in the current session.</span></span>

<span data-ttu-id="d1865-113">Você pode adicionar propriedades e métodos a objetos no PowerShell definindo-os em `Update-TypeData` comandos e `Types.ps1xml` arquivos.</span><span class="sxs-lookup"><span data-stu-id="d1865-113">You can add properties and methods to objects in PowerShell by defining them in `Update-TypeData` commands and `Types.ps1xml` files.</span></span> <span data-ttu-id="d1865-114">`Remove-TypeData` exclui as propriedades estendidas e os métodos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d1865-114">`Remove-TypeData` deletes those extended properties and methods from the current session.</span></span> <span data-ttu-id="d1865-115">`Remove-TypeData` não exclui os `Types.ps1xml` arquivos nem exclui nenhuma definição de tipo estendido dos `Types.ps1xml` arquivos.</span><span class="sxs-lookup"><span data-stu-id="d1865-115">`Remove-TypeData` does not delete the `Types.ps1xml` files or delete any extended type definitions from the `Types.ps1xml` files.</span></span> <span data-ttu-id="d1865-116">Para obter mais informações sobre `Types.ps1xml` arquivos, consulte [about_Types.ps1XML](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="d1865-116">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).</span></span>

<span data-ttu-id="d1865-117">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d1865-117">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="d1865-118">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d1865-118">Examples</span></span>

### <span data-ttu-id="d1865-119">Exemplo 1: remover dados de tipo para um tipo especificado</span><span class="sxs-lookup"><span data-stu-id="d1865-119">Example 1: Remove type data for a specified type</span></span>

<span data-ttu-id="d1865-120">Este exemplo exclui todos os dados de tipo para o tipo **System. array** da sessão, incluindo dados de tipo que foram adicionados por um `Types.ps1xml` arquivo e dados de tipo dinâmico que foram adicionados à sessão usando o `Update-TypeData` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d1865-120">This example deletes all type data for the **System.Array** type  from the session, including type data that was added by a `Types.ps1xml` file and dynamic type data that was added to the session by using the `Update-TypeData` cmdlet.</span></span>

```powershell
Remove-TypeData -TypeName System.Array
```

### <span data-ttu-id="d1865-121">Exemplo 2: remover um tipo de dados estendido de uma sessão</span><span class="sxs-lookup"><span data-stu-id="d1865-121">Example 2: Remove an extended data type from a session</span></span>

<span data-ttu-id="d1865-122">Este exemplo mostra o efeito de remover dados de tipo estendido de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d1865-122">This example shows the effect of removing extended type data from a session.</span></span> <span data-ttu-id="d1865-123">A primeira `Get-TypeData` obtém dados de tipo estendido para o tipo **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="d1865-123">The first `Get-TypeData` gets extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="d1865-124">A saída mostra que uma propriedade **DateTime** foi adicionada a todos os objetos **System. DateTime** no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1865-124">The output shows that a **DateTime** property has been added to all **System.DateTime** objects in PowerShell.</span></span> <span data-ttu-id="d1865-125">O `Get-Date` cmdlet retorna um objeto **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="d1865-125">The `Get-Date` cmdlet returns a **System.DateTime** object.</span></span> <span data-ttu-id="d1865-126">O comando usa a notação de ponto para obter o valor da propriedade **DateTime** do objeto **System. DateTime** que `Get-Date` retorna.</span><span class="sxs-lookup"><span data-stu-id="d1865-126">The command uses dot notation to get the value of the **DateTime** property of the **System.DateTime** object that `Get-Date` returns.</span></span>

```powershell
Get-TypeData System.DateTime
(Get-Date).DateTime
Get-TypeData System.DateTime | Remove-TypeData
(Get-Date).DateTime
```

```Output
TypeName        Members
--------        -------
System.DateTime {[DateTime, System.Management.Automation.Runspaces.ScriptPropertyData]}

Friday, January 20, 2012 9:01:00 PM
```

<span data-ttu-id="d1865-127">O próximo `Get-TypeData` cmdlet para obter todos os dados de tipo estendido para o tipo **System. DateTime** e canaliza para o `Remove-TypeData` cmdlet para excluir os dados de tipo estendido.</span><span class="sxs-lookup"><span data-stu-id="d1865-127">The next `Get-TypeData` cmdlet to get all extended type data for the **System.DateTime** type and pipes that to the `Remove-TypeData` cmdlet to delete the extended type data.</span></span> <span data-ttu-id="d1865-128">O último `Get-Date` cmdlet mostra o efeito de excluir os dados de tipo estendido para o tipo **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="d1865-128">The last `Get-Date` cmdlet shows the effect of deleting the extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="d1865-129">Como a propriedade **System. DateTime** não existe mais, um comando para obter seu valor não retorna nada.</span><span class="sxs-lookup"><span data-stu-id="d1865-129">Because the **System.DateTime** property no longer exists, a command to get its value returns nothing.</span></span>

### <span data-ttu-id="d1865-130">Exemplo 3: remover tipos estendidos para módulos</span><span class="sxs-lookup"><span data-stu-id="d1865-130">Example 3: Remove extended types for modules</span></span>

<span data-ttu-id="d1865-131">Este exemplo remove todos os dados de tipo estendido para objetos de módulo.</span><span class="sxs-lookup"><span data-stu-id="d1865-131">This example removes all extended type data for module objects.</span></span> <span data-ttu-id="d1865-132">Quando você canaliza um objeto para `Remove-TypeData` , `Remove-TypeData` Obtém o nome do tipo de objeto e remove todos os dados de tipo de todos os objetos desse tipo.</span><span class="sxs-lookup"><span data-stu-id="d1865-132">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the name of the object type and removes all type data for all objects of that type.</span></span>

```powershell
Get-Module | Remove-TypeData
```

### <span data-ttu-id="d1865-133">Exemplo 4: remover tipos estendidos de módulos especificados</span><span class="sxs-lookup"><span data-stu-id="d1865-133">Example 4: Remove extended types from specified modules</span></span>

<span data-ttu-id="d1865-134">Este exemplo usa o parâmetro **path** do `Remove-TypeData` cmdlet para remover os tipos estendidos que são definidos nos `Types.ps1xml` arquivos que são adicionados pelos módulos **PSScheduledJob** e **PSWorkflow** .</span><span class="sxs-lookup"><span data-stu-id="d1865-134">This example uses the **Path** parameter of the `Remove-TypeData` cmdlet to remove the extended types that are defined in the `Types.ps1xml` files that are added by the **PSScheduledJob** and **PSWorkflow** modules.</span></span> <span data-ttu-id="d1865-135">Esse comando não afeta os dados de tipo dinâmico que são adicionados usando o `Update-TypeData` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d1865-135">This command does not affect dynamic type data that is added by using the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="d1865-136">O comando terá êxito somente quando os módulos tiverem sido importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d1865-136">The command succeeds only when the modules have been imported into the current session.</span></span>

```powershell
Remove-TypeData -Path "$PSHOME\Modules\PSScheduledJob", "$PSHOME\Modules\PSWorkflow\PSWorkflow.types.ps1xml"
```

<span data-ttu-id="d1865-137">Para obter mais informações sobre módulos, consulte [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="d1865-137">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

### <span data-ttu-id="d1865-138">Exemplo 5: remover tipos estendidos de uma sessão remota</span><span class="sxs-lookup"><span data-stu-id="d1865-138">Example 5: Remove extended types from a remote session</span></span>

<span data-ttu-id="d1865-139">Este exemplo remove os tipos estendidos de uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="d1865-139">This example removes extended types from a remote session.</span></span> <span data-ttu-id="d1865-140">O comando usa o `Invoke-Command` cmdlet para remover dados de tipo estendido para todos os tipos de CIM nas sessões na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="d1865-140">The command uses the `Invoke-Command` cmdlet to remove extended type data for all CIM types in the sessions in the `$S` variable.</span></span>

```powershell
Invoke-Command -Session $S {Get-TypeData -TypeName *CIM* | Remove-TypeData}
```

## <span data-ttu-id="d1865-141">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d1865-141">Parameters</span></span>

### <span data-ttu-id="d1865-142">-Path</span><span class="sxs-lookup"><span data-stu-id="d1865-142">-Path</span></span>

<span data-ttu-id="d1865-143">Especifica uma matriz de arquivos que esse cmdlet exclui dos dados de tipo estendido da sessão.</span><span class="sxs-lookup"><span data-stu-id="d1865-143">Specifies an array of files that this cmdlet deletes from the session extended type data.</span></span> <span data-ttu-id="d1865-144">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="d1865-144">This parameter is required.</span></span>

<span data-ttu-id="d1865-145">Insira os caminhos e os nomes de arquivo de um ou mais `Types.ps1xml` arquivos.</span><span class="sxs-lookup"><span data-stu-id="d1865-145">Enter the paths and file names of one or more `Types.ps1xml` files.</span></span> <span data-ttu-id="d1865-146">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="d1865-146">Wildcards are not supported.</span></span> <span data-ttu-id="d1865-147">Se você omitir o caminho, o local padrão a considerar é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="d1865-147">If you omit the path, the default location is the current directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RemoveFileSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d1865-148">-TypeData</span><span class="sxs-lookup"><span data-stu-id="d1865-148">-TypeData</span></span>

<span data-ttu-id="d1865-149">Especifica os dados de tipo que esse cmdlet exclui da sessão.</span><span class="sxs-lookup"><span data-stu-id="d1865-149">Specifies the type data that this cmdlet deletes from the session.</span></span> <span data-ttu-id="d1865-150">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="d1865-150">This parameter is required.</span></span> <span data-ttu-id="d1865-151">Insira uma variável que contém objetos **TypeData** ( **System. Management. Automation. Runspaces. TypeData** ) ou um comando que obtém objetos **TypeData** , como um `Get-TypeData` comando.</span><span class="sxs-lookup"><span data-stu-id="d1865-151">Enter a variable that contains **TypeData** objects ( **System.Management.Automation.Runspaces.TypeData** ) or a command that gets **TypeData** objects, such as a `Get-TypeData` command.</span></span> <span data-ttu-id="d1865-152">Você também pode canalizar objetos **TypeData** para `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="d1865-152">You can also pipe **TypeData** objects to `Remove-TypeData`.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.TypeData
Parameter Sets: RemoveTypeDataSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d1865-153">-TypeName</span><span class="sxs-lookup"><span data-stu-id="d1865-153">-TypeName</span></span>

<span data-ttu-id="d1865-154">Especifica os tipos para os quais este cmdlet exclui todos os dados de tipo estendido.</span><span class="sxs-lookup"><span data-stu-id="d1865-154">Specifies the types that this cmdlet deletes all extended type data for.</span></span> <span data-ttu-id="d1865-155">Para tipos no namespace System, insira o nome abreviado.</span><span class="sxs-lookup"><span data-stu-id="d1865-155">For types in the System namespace, enter the short name.</span></span> <span data-ttu-id="d1865-156">Caso contrário, é necessário o nome completo do tipo.</span><span class="sxs-lookup"><span data-stu-id="d1865-156">Otherwise, the full type name is required.</span></span> <span data-ttu-id="d1865-157">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="d1865-157">Wildcards are not supported.</span></span>

<span data-ttu-id="d1865-158">Você pode canalizar nomes de tipo para `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="d1865-158">You can pipe type names to `Remove-TypeData`.</span></span> <span data-ttu-id="d1865-159">Quando você canaliza um objeto para `Remove-TypeData` , `Remove-TypeData` Obtém o nome do tipo do objeto e remove todos os dados do tipo para o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="d1865-159">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

```yaml
Type: System.String
Parameter Sets: RemoveTypeSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d1865-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d1865-160">-Confirm</span></span>

<span data-ttu-id="d1865-161">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d1865-161">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d1865-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d1865-162">-WhatIf</span></span>

<span data-ttu-id="d1865-163">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d1865-163">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d1865-164">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d1865-164">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d1865-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d1865-165">CommonParameters</span></span>

<span data-ttu-id="d1865-166">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d1865-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d1865-167">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d1865-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d1865-168">Entradas</span><span class="sxs-lookup"><span data-stu-id="d1865-168">Inputs</span></span>

### <span data-ttu-id="d1865-169">System. Management. Automation. Runspaces. TypeData</span><span class="sxs-lookup"><span data-stu-id="d1865-169">System.Management.Automation.Runspaces.TypeData</span></span>

<span data-ttu-id="d1865-170">Você pode canalizar o objeto **TypeData** , como aqueles que o `Get-TypeData` cmdlet retorna, para `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="d1865-170">You can pipe **TypeData** object, such as the ones that the `Get-TypeData` cmdlet returns, to `Remove-TypeData`.</span></span>

### <span data-ttu-id="d1865-171">System.String</span><span class="sxs-lookup"><span data-stu-id="d1865-171">System.String</span></span>

<span data-ttu-id="d1865-172">Você pode canalizar os nomes de tipo para `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="d1865-172">You can pipe the type names to `Remove-TypeData`.</span></span> <span data-ttu-id="d1865-173">Quando você canaliza um objeto para `Remove-TypeData` , `Remove-TypeData` Obtém o nome do tipo do objeto e remove todos os dados do tipo para o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="d1865-173">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

## <span data-ttu-id="d1865-174">Saídas</span><span class="sxs-lookup"><span data-stu-id="d1865-174">Outputs</span></span>

### <span data-ttu-id="d1865-175">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1865-175">None</span></span>

<span data-ttu-id="d1865-176">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="d1865-176">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d1865-177">Observações</span><span class="sxs-lookup"><span data-stu-id="d1865-177">Notes</span></span>

<span data-ttu-id="d1865-178">`Remove-TypeData` pode remover somente os dados de tipo estendido na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d1865-178">`Remove-TypeData` can remove only the extended type data in the current session.</span></span> <span data-ttu-id="d1865-179">Ele não pode remover dados de tipo estendido presentes no computador mas que não foram adicionados à sessão atual, como tipos estendidos que são definidos em módulos que não foram importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d1865-179">It cannot remove extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="d1865-180">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="d1865-180">Related links</span></span>

[<span data-ttu-id="d1865-181">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="d1865-181">Get-TypeData</span></span>](Get-TypeData.md)

[<span data-ttu-id="d1865-182">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="d1865-182">Update-TypeData</span></span>](Update-TypeData.md)
