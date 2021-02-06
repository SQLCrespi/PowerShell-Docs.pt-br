---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-typedata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-TypeData
ms.openlocfilehash: 8ede1375faa1287b70eeb49689ec7fe1bb800d55
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595783"
---
# <span data-ttu-id="7855a-102">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="7855a-102">Remove-TypeData</span></span>

## <span data-ttu-id="7855a-103">Sinopse</span><span class="sxs-lookup"><span data-stu-id="7855a-103">Synopsis</span></span>
<span data-ttu-id="7855a-104">Exclui tipos estendidos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7855a-104">Deletes extended types from the current session.</span></span>

## <span data-ttu-id="7855a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7855a-105">Syntax</span></span>

### <span data-ttu-id="7855a-106">RemoveTypeDataSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="7855a-106">RemoveTypeDataSet (Default)</span></span>

```
Remove-TypeData -TypeData <TypeData> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7855a-107">RemoveTypeSet</span><span class="sxs-lookup"><span data-stu-id="7855a-107">RemoveTypeSet</span></span>

```
Remove-TypeData [-TypeName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7855a-108">Removeset</span><span class="sxs-lookup"><span data-stu-id="7855a-108">RemoveFileSet</span></span>

```
Remove-TypeData -Path <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7855a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7855a-109">DESCRIPTION</span></span>

<span data-ttu-id="7855a-110">O `Remove-TypeData` cmdlet exclui dados de tipo estendido da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7855a-110">The `Remove-TypeData` cmdlet deletes extended type data from the current session.</span></span> <span data-ttu-id="7855a-111">Este cmdlet afeta somente a sessão atual e as sessões que são criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7855a-111">This cmdlet affects only the current session and sessions that are created in the current session.</span></span>

<span data-ttu-id="7855a-112">Você pode adicionar propriedades e métodos a objetos no PowerShell definindo-os em `Update-TypeData` comandos e `Types.ps1xml` arquivos.</span><span class="sxs-lookup"><span data-stu-id="7855a-112">You can add properties and methods to objects in PowerShell by defining them in `Update-TypeData` commands and `Types.ps1xml` files.</span></span> <span data-ttu-id="7855a-113">`Remove-TypeData` exclui as propriedades estendidas e os métodos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7855a-113">`Remove-TypeData` deletes those extended properties and methods from the current session.</span></span> <span data-ttu-id="7855a-114">`Remove-TypeData` não exclui os `Types.ps1xml` arquivos nem exclui nenhuma definição de tipo estendido dos `Types.ps1xml` arquivos.</span><span class="sxs-lookup"><span data-stu-id="7855a-114">`Remove-TypeData` does not delete the `Types.ps1xml` files or delete any extended type definitions from the `Types.ps1xml` files.</span></span> <span data-ttu-id="7855a-115">Para obter mais informações sobre `Types.ps1xml` arquivos, consulte [about_Types.ps1XML](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="7855a-115">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).</span></span>

<span data-ttu-id="7855a-116">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7855a-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="7855a-117">Exemplos</span><span class="sxs-lookup"><span data-stu-id="7855a-117">Examples</span></span>

### <span data-ttu-id="7855a-118">Exemplo 1: remover dados de tipo para um tipo especificado</span><span class="sxs-lookup"><span data-stu-id="7855a-118">Example 1: Remove type data for a specified type</span></span>

<span data-ttu-id="7855a-119">Este exemplo exclui todos os dados de tipo para o tipo **System. array** da sessão, incluindo dados de tipo que foram adicionados por um `Types.ps1xml` arquivo e dados de tipo dinâmico que foram adicionados à sessão usando o `Update-TypeData` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7855a-119">This example deletes all type data for the **System.Array** type  from the session, including type data that was added by a `Types.ps1xml` file and dynamic type data that was added to the session by using the `Update-TypeData` cmdlet.</span></span>

```powershell
Remove-TypeData -TypeName System.Array
```

### <span data-ttu-id="7855a-120">Exemplo 2: remover um tipo de dados estendido de uma sessão</span><span class="sxs-lookup"><span data-stu-id="7855a-120">Example 2: Remove an extended data type from a session</span></span>

<span data-ttu-id="7855a-121">Este exemplo mostra o efeito de remover dados de tipo estendido de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="7855a-121">This example shows the effect of removing extended type data from a session.</span></span> <span data-ttu-id="7855a-122">A primeira `Get-TypeData` obtém dados de tipo estendido para o tipo **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="7855a-122">The first `Get-TypeData` gets extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="7855a-123">A saída mostra que uma propriedade **DateTime** foi adicionada a todos os objetos **System. DateTime** no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7855a-123">The output shows that a **DateTime** property has been added to all **System.DateTime** objects in PowerShell.</span></span> <span data-ttu-id="7855a-124">O `Get-Date` cmdlet retorna um objeto **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="7855a-124">The `Get-Date` cmdlet returns a **System.DateTime** object.</span></span> <span data-ttu-id="7855a-125">O comando usa a notação de ponto para obter o valor da propriedade **DateTime** do objeto **System. DateTime** que `Get-Date` retorna.</span><span class="sxs-lookup"><span data-stu-id="7855a-125">The command uses dot notation to get the value of the **DateTime** property of the **System.DateTime** object that `Get-Date` returns.</span></span>

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

<span data-ttu-id="7855a-126">O próximo `Get-TypeData` cmdlet para obter todos os dados de tipo estendido para o tipo **System. DateTime** e canaliza para o `Remove-TypeData` cmdlet para excluir os dados de tipo estendido.</span><span class="sxs-lookup"><span data-stu-id="7855a-126">The next `Get-TypeData` cmdlet to get all extended type data for the **System.DateTime** type and pipes that to the `Remove-TypeData` cmdlet to delete the extended type data.</span></span> <span data-ttu-id="7855a-127">O último `Get-Date` cmdlet mostra o efeito de excluir os dados de tipo estendido para o tipo **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="7855a-127">The last `Get-Date` cmdlet shows the effect of deleting the extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="7855a-128">Como a propriedade **System. DateTime** não existe mais, um comando para obter seu valor não retorna nada.</span><span class="sxs-lookup"><span data-stu-id="7855a-128">Because the **System.DateTime** property no longer exists, a command to get its value returns nothing.</span></span>

### <span data-ttu-id="7855a-129">Exemplo 3: remover tipos estendidos para módulos</span><span class="sxs-lookup"><span data-stu-id="7855a-129">Example 3: Remove extended types for modules</span></span>

<span data-ttu-id="7855a-130">Este exemplo remove todos os dados de tipo estendido para objetos de módulo.</span><span class="sxs-lookup"><span data-stu-id="7855a-130">This example removes all extended type data for module objects.</span></span> <span data-ttu-id="7855a-131">Quando você canaliza um objeto para `Remove-TypeData` , `Remove-TypeData` Obtém o nome do tipo de objeto e remove todos os dados de tipo de todos os objetos desse tipo.</span><span class="sxs-lookup"><span data-stu-id="7855a-131">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the name of the object type and removes all type data for all objects of that type.</span></span>

```powershell
Get-Module | Remove-TypeData
```

### <span data-ttu-id="7855a-132">Exemplo 4: remover tipos estendidos de módulos especificados</span><span class="sxs-lookup"><span data-stu-id="7855a-132">Example 4: Remove extended types from specified modules</span></span>

<span data-ttu-id="7855a-133">Este exemplo usa o parâmetro **path** do `Remove-TypeData` cmdlet para remover os tipos estendidos que são definidos nos `Types.ps1xml` arquivos que são adicionados pelos módulos **PSScheduledJob** e **PSWorkflow** .</span><span class="sxs-lookup"><span data-stu-id="7855a-133">This example uses the **Path** parameter of the `Remove-TypeData` cmdlet to remove the extended types that are defined in the `Types.ps1xml` files that are added by the **PSScheduledJob** and **PSWorkflow** modules.</span></span> <span data-ttu-id="7855a-134">Esse comando não afeta os dados de tipo dinâmico que são adicionados usando o `Update-TypeData` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7855a-134">This command does not affect dynamic type data that is added by using the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="7855a-135">O comando terá êxito somente quando os módulos tiverem sido importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7855a-135">The command succeeds only when the modules have been imported into the current session.</span></span>

```powershell
Remove-TypeData -Path "$PSHOME\Modules\PSScheduledJob", "$PSHOME\Modules\PSWorkflow\PSWorkflow.types.ps1xml"
```

<span data-ttu-id="7855a-136">Para obter mais informações sobre módulos, consulte [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="7855a-136">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

### <span data-ttu-id="7855a-137">Exemplo 5: remover tipos estendidos de uma sessão remota</span><span class="sxs-lookup"><span data-stu-id="7855a-137">Example 5: Remove extended types from a remote session</span></span>

<span data-ttu-id="7855a-138">Este exemplo remove os tipos estendidos de uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="7855a-138">This example removes extended types from a remote session.</span></span> <span data-ttu-id="7855a-139">O comando usa o `Invoke-Command` cmdlet para remover dados de tipo estendido para todos os tipos de CIM nas sessões na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="7855a-139">The command uses the `Invoke-Command` cmdlet to remove extended type data for all CIM types in the sessions in the `$S` variable.</span></span>

```powershell
Invoke-Command -Session $S {Get-TypeData -TypeName *CIM* | Remove-TypeData}
```

## <span data-ttu-id="7855a-140">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7855a-140">Parameters</span></span>

### <span data-ttu-id="7855a-141">-Path</span><span class="sxs-lookup"><span data-stu-id="7855a-141">-Path</span></span>

<span data-ttu-id="7855a-142">Especifica uma matriz de arquivos que esse cmdlet exclui dos dados de tipo estendido da sessão.</span><span class="sxs-lookup"><span data-stu-id="7855a-142">Specifies an array of files that this cmdlet deletes from the session extended type data.</span></span> <span data-ttu-id="7855a-143">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="7855a-143">This parameter is required.</span></span>

<span data-ttu-id="7855a-144">Insira os caminhos e os nomes de arquivo de um ou mais `Types.ps1xml` arquivos.</span><span class="sxs-lookup"><span data-stu-id="7855a-144">Enter the paths and file names of one or more `Types.ps1xml` files.</span></span> <span data-ttu-id="7855a-145">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="7855a-145">Wildcards are not supported.</span></span> <span data-ttu-id="7855a-146">Se você omitir o caminho, o local padrão a considerar é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="7855a-146">If you omit the path, the default location is the current directory.</span></span>

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

### <span data-ttu-id="7855a-147">-TypeData</span><span class="sxs-lookup"><span data-stu-id="7855a-147">-TypeData</span></span>

<span data-ttu-id="7855a-148">Especifica os dados de tipo que esse cmdlet exclui da sessão.</span><span class="sxs-lookup"><span data-stu-id="7855a-148">Specifies the type data that this cmdlet deletes from the session.</span></span> <span data-ttu-id="7855a-149">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="7855a-149">This parameter is required.</span></span> <span data-ttu-id="7855a-150">Insira uma variável que contém objetos **TypeData** (**System. Management. Automation. Runspaces. TypeData**) ou um comando que obtém objetos **TypeData** , como um `Get-TypeData` comando.</span><span class="sxs-lookup"><span data-stu-id="7855a-150">Enter a variable that contains **TypeData** objects (**System.Management.Automation.Runspaces.TypeData**) or a command that gets **TypeData** objects, such as a `Get-TypeData` command.</span></span> <span data-ttu-id="7855a-151">Você também pode canalizar objetos **TypeData** para `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7855a-151">You can also pipe **TypeData** objects to `Remove-TypeData`.</span></span>

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

### <span data-ttu-id="7855a-152">-TypeName</span><span class="sxs-lookup"><span data-stu-id="7855a-152">-TypeName</span></span>

<span data-ttu-id="7855a-153">Especifica os tipos para os quais este cmdlet exclui todos os dados de tipo estendido.</span><span class="sxs-lookup"><span data-stu-id="7855a-153">Specifies the types that this cmdlet deletes all extended type data for.</span></span> <span data-ttu-id="7855a-154">Para tipos no namespace System, insira o nome abreviado.</span><span class="sxs-lookup"><span data-stu-id="7855a-154">For types in the System namespace, enter the short name.</span></span> <span data-ttu-id="7855a-155">Caso contrário, é necessário o nome completo do tipo.</span><span class="sxs-lookup"><span data-stu-id="7855a-155">Otherwise, the full type name is required.</span></span> <span data-ttu-id="7855a-156">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="7855a-156">Wildcards are not supported.</span></span>

<span data-ttu-id="7855a-157">Você pode canalizar nomes de tipo para `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7855a-157">You can pipe type names to `Remove-TypeData`.</span></span> <span data-ttu-id="7855a-158">Quando você canaliza um objeto para `Remove-TypeData` , `Remove-TypeData` Obtém o nome do tipo do objeto e remove todos os dados do tipo para o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="7855a-158">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

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

### <span data-ttu-id="7855a-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7855a-159">-Confirm</span></span>

<span data-ttu-id="7855a-160">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7855a-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7855a-161">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7855a-161">-WhatIf</span></span>

<span data-ttu-id="7855a-162">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="7855a-162">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7855a-163">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="7855a-163">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7855a-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7855a-164">CommonParameters</span></span>

<span data-ttu-id="7855a-165">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7855a-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7855a-166">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7855a-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7855a-167">Entradas</span><span class="sxs-lookup"><span data-stu-id="7855a-167">Inputs</span></span>

### <span data-ttu-id="7855a-168">System. Management. Automation. Runspaces. TypeData</span><span class="sxs-lookup"><span data-stu-id="7855a-168">System.Management.Automation.Runspaces.TypeData</span></span>

<span data-ttu-id="7855a-169">Você pode canalizar o objeto **TypeData** , como aqueles que o `Get-TypeData` cmdlet retorna, para `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7855a-169">You can pipe **TypeData** object, such as the ones that the `Get-TypeData` cmdlet returns, to `Remove-TypeData`.</span></span>

### <span data-ttu-id="7855a-170">System.String</span><span class="sxs-lookup"><span data-stu-id="7855a-170">System.String</span></span>

<span data-ttu-id="7855a-171">Você pode canalizar os nomes de tipo para `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7855a-171">You can pipe the type names to `Remove-TypeData`.</span></span> <span data-ttu-id="7855a-172">Quando você canaliza um objeto para `Remove-TypeData` , `Remove-TypeData` Obtém o nome do tipo do objeto e remove todos os dados do tipo para o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="7855a-172">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

## <span data-ttu-id="7855a-173">Saídas</span><span class="sxs-lookup"><span data-stu-id="7855a-173">Outputs</span></span>

### <span data-ttu-id="7855a-174">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7855a-174">None</span></span>

<span data-ttu-id="7855a-175">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="7855a-175">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7855a-176">Observações</span><span class="sxs-lookup"><span data-stu-id="7855a-176">Notes</span></span>

<span data-ttu-id="7855a-177">`Remove-TypeData` pode remover somente os dados de tipo estendido na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7855a-177">`Remove-TypeData` can remove only the extended type data in the current session.</span></span> <span data-ttu-id="7855a-178">Ele não pode remover dados de tipo estendido presentes no computador mas que não foram adicionados à sessão atual, como tipos estendidos que são definidos em módulos que não foram importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7855a-178">It cannot remove extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="7855a-179">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="7855a-179">Related links</span></span>

[<span data-ttu-id="7855a-180">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="7855a-180">Get-TypeData</span></span>](Get-TypeData.md)

[<span data-ttu-id="7855a-181">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="7855a-181">Update-TypeData</span></span>](Update-TypeData.md)

