---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Alias
ms.openlocfilehash: 20bc5d141b68cab19374afbe44b3472c72bf69bc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597184"
---
# <span data-ttu-id="f2212-102">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="f2212-102">Import-Alias</span></span>

## <span data-ttu-id="f2212-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f2212-103">SYNOPSIS</span></span>
<span data-ttu-id="f2212-104">Importa uma lista de alias de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="f2212-104">Imports an alias list from a file.</span></span>

## <span data-ttu-id="f2212-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f2212-105">SYNTAX</span></span>

### <span data-ttu-id="f2212-106">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="f2212-106">ByPath (Default)</span></span>

```
Import-Alias [-Path] <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f2212-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="f2212-107">ByLiteralPath</span></span>

```
Import-Alias -LiteralPath <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="f2212-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f2212-108">DESCRIPTION</span></span>

<span data-ttu-id="f2212-109">O `Import-Alias` cmdlet importa uma lista de alias de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="f2212-109">The `Import-Alias` cmdlet imports an alias list from a file.</span></span>

<span data-ttu-id="f2212-110">A partir do Windows PowerShell 3,0, como um recurso de segurança, `Import-Alias` o não substitui os aliases existentes por padrão.</span><span class="sxs-lookup"><span data-stu-id="f2212-110">Beginning in Windows PowerShell 3.0, as a security feature, `Import-Alias` does not overwrite existing aliases by default.</span></span>
<span data-ttu-id="f2212-111">Para substituir um alias existente, depois de garantir que o conteúdo do arquivo de alias é seguro, use o parâmetro **Force**.</span><span class="sxs-lookup"><span data-stu-id="f2212-111">To overwrite an existing alias, after assuring that the contents of the alias file is safe, use the **Force** parameter.</span></span>

## <span data-ttu-id="f2212-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f2212-112">EXAMPLES</span></span>

### <span data-ttu-id="f2212-113">Exemplo 1: importar aliases de um arquivo</span><span class="sxs-lookup"><span data-stu-id="f2212-113">Example 1: Import aliases from a file</span></span>

```powershell
Import-Alias test.txt
```

<span data-ttu-id="f2212-114">Este comando importa informações de alias de um arquivo chamado test.txt.</span><span class="sxs-lookup"><span data-stu-id="f2212-114">This command imports alias information from a file named test.txt.</span></span>

## <span data-ttu-id="f2212-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f2212-115">PARAMETERS</span></span>

### <span data-ttu-id="f2212-116">-Force</span><span class="sxs-lookup"><span data-stu-id="f2212-116">-Force</span></span>

<span data-ttu-id="f2212-117">Permite que o cmdlet importe um alias que já está definido ou é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="f2212-117">Allows the cmdlet to import an alias that is already defined or is read only.</span></span>
<span data-ttu-id="f2212-118">Você pode usar o seguinte comando para exibir informações sobre os aliases definidos no momento:</span><span class="sxs-lookup"><span data-stu-id="f2212-118">You can use the following command to display information about the currently-defined aliases:</span></span>

`Get-Alias | Select-Object Name, Options`

<span data-ttu-id="f2212-119">Se o alias correspondente for somente leitura, ele será exibido no valor da propriedade **Options**.</span><span class="sxs-lookup"><span data-stu-id="f2212-119">If the corresponding alias is read-only, it will be displayed in the value of the **Options** property.</span></span>

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

### <span data-ttu-id="f2212-120">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f2212-120">-LiteralPath</span></span>

<span data-ttu-id="f2212-121">Especifica o caminho para um arquivo que inclui informações do alias exportado.</span><span class="sxs-lookup"><span data-stu-id="f2212-121">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="f2212-122">Ao contrário do parâmetro **Path**, o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="f2212-122">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="f2212-123">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="f2212-123">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="f2212-124">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="f2212-124">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="f2212-125">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="f2212-125">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f2212-126">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f2212-126">-PassThru</span></span>

<span data-ttu-id="f2212-127">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="f2212-127">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="f2212-128">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="f2212-128">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="f2212-129">-Path</span><span class="sxs-lookup"><span data-stu-id="f2212-129">-Path</span></span>

<span data-ttu-id="f2212-130">Especifica o caminho para um arquivo que inclui informações do alias exportado.</span><span class="sxs-lookup"><span data-stu-id="f2212-130">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="f2212-131">Caracteres curinga são permitidos, mas eles devem ser resolvidos para um único nome.</span><span class="sxs-lookup"><span data-stu-id="f2212-131">Wildcards are allowed but they must resolve to a single name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="f2212-132">-Escopo</span><span class="sxs-lookup"><span data-stu-id="f2212-132">-Scope</span></span>

<span data-ttu-id="f2212-133">Especifica o escopo no qual os aliases são importados.</span><span class="sxs-lookup"><span data-stu-id="f2212-133">Specifies the scope into which the aliases are imported.</span></span>
<span data-ttu-id="f2212-134">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="f2212-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f2212-135">Global</span><span class="sxs-lookup"><span data-stu-id="f2212-135">Global</span></span>
- <span data-ttu-id="f2212-136">Local</span><span class="sxs-lookup"><span data-stu-id="f2212-136">Local</span></span>
- <span data-ttu-id="f2212-137">Script</span><span class="sxs-lookup"><span data-stu-id="f2212-137">Script</span></span>
- <span data-ttu-id="f2212-138">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)</span><span class="sxs-lookup"><span data-stu-id="f2212-138">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="f2212-139">O padrão é local.</span><span class="sxs-lookup"><span data-stu-id="f2212-139">The default is Local.</span></span>
<span data-ttu-id="f2212-140">Para obter mais informações, consulte about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="f2212-140">For more information, see about_Scopes.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f2212-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f2212-141">-Confirm</span></span>

<span data-ttu-id="f2212-142">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f2212-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f2212-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f2212-143">-WhatIf</span></span>

<span data-ttu-id="f2212-144">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="f2212-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f2212-145">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="f2212-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f2212-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f2212-146">CommonParameters</span></span>

<span data-ttu-id="f2212-147">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f2212-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f2212-148">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f2212-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f2212-149">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f2212-149">INPUTS</span></span>

### <span data-ttu-id="f2212-150">System.String</span><span class="sxs-lookup"><span data-stu-id="f2212-150">System.String</span></span>

<span data-ttu-id="f2212-151">É possível canalizar uma cadeia de caracteres que contém um caminho para `Import-Alias` .</span><span class="sxs-lookup"><span data-stu-id="f2212-151">You can pipe a string that contains a path to `Import-Alias`.</span></span>

## <span data-ttu-id="f2212-152">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f2212-152">OUTPUTS</span></span>

### <span data-ttu-id="f2212-153">Nenhum ou System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="f2212-153">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="f2212-154">Quando você usa o parâmetro **PassThru** , `Import-Alias` retorna um objeto **System. Management. Automation. AliasInfo** que representa o alias.</span><span class="sxs-lookup"><span data-stu-id="f2212-154">When you use the **Passthru** parameter, `Import-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="f2212-155">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="f2212-155">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f2212-156">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f2212-156">NOTES</span></span>

## <span data-ttu-id="f2212-157">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f2212-157">RELATED LINKS</span></span>

[<span data-ttu-id="f2212-158">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="f2212-158">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="f2212-159">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="f2212-159">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="f2212-160">New-Alias</span><span class="sxs-lookup"><span data-stu-id="f2212-160">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="f2212-161">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="f2212-161">Set-Alias</span></span>](Set-Alias.md)

