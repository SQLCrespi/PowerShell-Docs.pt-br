---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-psdrive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSDrive
ms.openlocfilehash: d20a348f3f5ba193eb85e0f9d0e2cc11ad083b47
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597631"
---
# <span data-ttu-id="72901-102">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="72901-102">Remove-PSDrive</span></span>

## <span data-ttu-id="72901-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="72901-103">SYNOPSIS</span></span>
<span data-ttu-id="72901-104">Exclui unidades temporárias do PowerShell e desconecta unidades de rede mapeadas.</span><span class="sxs-lookup"><span data-stu-id="72901-104">Deletes temporary PowerShell drives and disconnects mapped network drives.</span></span>

## <span data-ttu-id="72901-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="72901-105">SYNTAX</span></span>

### <span data-ttu-id="72901-106">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="72901-106">Name (Default)</span></span>

```
Remove-PSDrive [-Name] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="72901-107">Valor literal</span><span class="sxs-lookup"><span data-stu-id="72901-107">LiteralName</span></span>

```
Remove-PSDrive [-LiteralName] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="72901-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="72901-108">DESCRIPTION</span></span>

<span data-ttu-id="72901-109">O `Remove-PSDrive` cmdlet exclui unidades temporárias do PowerShell que foram criadas usando o `New-PSDrive` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="72901-109">The `Remove-PSDrive` cmdlet deletes temporary PowerShell drives that were created by using the `New-PSDrive` cmdlet.</span></span>

<span data-ttu-id="72901-110">A partir do Windows PowerShell 3,0, o `Remove-PSDrive` também desconecta unidades de rede mapeadas, incluindo, mas não se limitando a, unidades criadas usando o `Persist` parâmetro de `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="72901-110">Beginning in Windows PowerShell 3.0, `Remove-PSDrive` also disconnects mapped network drives, including, but not limited to, drives created by using the `Persist` parameter of `New-PSDrive`.</span></span>

<span data-ttu-id="72901-111">`Remove-PSDrive` Não é possível excluir unidades físicas ou lógicas do Windows.</span><span class="sxs-lookup"><span data-stu-id="72901-111">`Remove-PSDrive` cannot delete Windows physical or logical drives.</span></span>

<span data-ttu-id="72901-112">A partir do Windows PowerShell 3,0, quando uma unidade externa é conectada ao computador, o PowerShell adiciona automaticamente um PSDrive ao sistema de arquivos que representa a nova unidade.</span><span class="sxs-lookup"><span data-stu-id="72901-112">Beginning in Windows PowerShell 3.0, when an external drive is connected to the computer, PowerShell automatically adds a PSDrive to the file system that represents the new drive.</span></span>
<span data-ttu-id="72901-113">Você não precisa reiniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="72901-113">You do not need to restart PowerShell.</span></span>
<span data-ttu-id="72901-114">Da mesma forma, quando uma unidade externa é desconectada do computador, o PowerShell exclui automaticamente o PSDrive que representa a unidade removida.</span><span class="sxs-lookup"><span data-stu-id="72901-114">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the PSDrive that represents the removed drive.</span></span>

## <span data-ttu-id="72901-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="72901-115">EXAMPLES</span></span>

### <span data-ttu-id="72901-116">Exemplo 1: remover uma unidade do sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="72901-116">Example 1: Remove a file system drive</span></span>

<span data-ttu-id="72901-117">Este comando remove uma unidade de sistema de arquivos temporária chamada "smp".</span><span class="sxs-lookup"><span data-stu-id="72901-117">This command removes a temporary file system drive named "smp".</span></span>

```powershell
Remove-PSDrive -Name smp
```

### <span data-ttu-id="72901-118">Exemplo 2: remover unidades de rede mapeadas</span><span class="sxs-lookup"><span data-stu-id="72901-118">Example 2: Remove mapped network drives</span></span>

<span data-ttu-id="72901-119">Esse comando usa `Remove-PSDrive` para desconectar as unidades de rede de X: e S: mapeadas.</span><span class="sxs-lookup"><span data-stu-id="72901-119">This command uses `Remove-PSDrive` to disconnect the X: and S: mapped network drives.</span></span>

```powershell
Get-PSDrive X, S | Remove-PSDrive
```

## <span data-ttu-id="72901-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="72901-120">PARAMETERS</span></span>

### <span data-ttu-id="72901-121">-Force</span><span class="sxs-lookup"><span data-stu-id="72901-121">-Force</span></span>

<span data-ttu-id="72901-122">Remove a unidade atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="72901-122">Removes the current PowerShell drive.</span></span>

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

### <span data-ttu-id="72901-123">-LiteralName</span><span class="sxs-lookup"><span data-stu-id="72901-123">-LiteralName</span></span>

<span data-ttu-id="72901-124">Especifica o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="72901-124">Specifies the name of the drive.</span></span>

<span data-ttu-id="72901-125">O valor de **LiteralName** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="72901-125">The value of **LiteralName** is used exactly as typed.</span></span>
<span data-ttu-id="72901-126">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="72901-126">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="72901-127">Se o nome inclui caracteres de escape, coloque-o entre aspas simples (').</span><span class="sxs-lookup"><span data-stu-id="72901-127">If the name includes escape characters, enclose it in single quotation marks (').</span></span>
<span data-ttu-id="72901-128">As aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="72901-128">Single quotation marks instruct PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="72901-129">-Name</span><span class="sxs-lookup"><span data-stu-id="72901-129">-Name</span></span>

<span data-ttu-id="72901-130">Especifica os nomes das unidades a remover.</span><span class="sxs-lookup"><span data-stu-id="72901-130">Specifies the names of the drives to remove.</span></span>
<span data-ttu-id="72901-131">Não digite dois-pontos (:) após o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="72901-131">Do not type a colon (:) after the drive name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="72901-132">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="72901-132">-PSProvider</span></span>

<span data-ttu-id="72901-133">Especifica uma matriz de objetos **PSProvider** .</span><span class="sxs-lookup"><span data-stu-id="72901-133">Specifies an array of **PSProvider** objects.</span></span>
<span data-ttu-id="72901-134">Esse cmdlet Remove e desconecta todas as unidades associadas ao provedor do PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="72901-134">This cmdlet removes and disconnects all of the drives associated with the specified PowerShell provider.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="72901-135">-Escopo</span><span class="sxs-lookup"><span data-stu-id="72901-135">-Scope</span></span>

<span data-ttu-id="72901-136">Especifica um escopo para a unidade.</span><span class="sxs-lookup"><span data-stu-id="72901-136">Specifies a scope for the drive.</span></span>
<span data-ttu-id="72901-137">Os valores aceitáveis para esse parâmetro são: global, local e script, ou um número relativo ao escopo atual.</span><span class="sxs-lookup"><span data-stu-id="72901-137">The acceptable values for this parameter are: Global, Local, and Script, or a number relative to the current scope.</span></span> <span data-ttu-id="72901-138">O número de escopos é 0 com o número de escopos.</span><span class="sxs-lookup"><span data-stu-id="72901-138">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="72901-139">O número de escopo atual é 0 e seu pai é 1.</span><span class="sxs-lookup"><span data-stu-id="72901-139">The current scope number is 0 and its parent is 1.</span></span>
<span data-ttu-id="72901-140">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="72901-140">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="72901-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="72901-141">-Confirm</span></span>

<span data-ttu-id="72901-142">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="72901-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="72901-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="72901-143">-WhatIf</span></span>

<span data-ttu-id="72901-144">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="72901-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="72901-145">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="72901-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="72901-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="72901-146">CommonParameters</span></span>

<span data-ttu-id="72901-147">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="72901-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="72901-148">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="72901-148">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="72901-149">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="72901-149">INPUTS</span></span>

### <span data-ttu-id="72901-150">System.Management.Automation.PSDriveInfo</span><span class="sxs-lookup"><span data-stu-id="72901-150">System.Management.Automation.PSDriveInfo</span></span>

<span data-ttu-id="72901-151">É possível canalizar um objeto de unidade, como um do `Get-PSDrive` cmdlet, para o `Remove-PSDrive` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="72901-151">You can pipe a drive object, such as one from the `Get-PSDrive` cmdlet, to the `Remove-PSDrive` cmdlet.</span></span>

## <span data-ttu-id="72901-152">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="72901-152">OUTPUTS</span></span>

### <span data-ttu-id="72901-153">Nenhum</span><span class="sxs-lookup"><span data-stu-id="72901-153">None</span></span>

<span data-ttu-id="72901-154">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="72901-154">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="72901-155">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="72901-155">NOTES</span></span>

- <span data-ttu-id="72901-156">O `Remove-PSDrive` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="72901-156">The `Remove-PSDrive` cmdlet is designed to work with the data exposed by any PowerShell provider.</span></span> <span data-ttu-id="72901-157">Para listar os provedores em sua sessão, use o `Get-PSProvider` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="72901-157">To list the providers in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="72901-158">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="72901-158">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="72901-159">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="72901-159">RELATED LINKS</span></span>

[<span data-ttu-id="72901-160">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="72901-160">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="72901-161">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="72901-161">New-PSDrive</span></span>](New-PSDrive.md)

[<span data-ttu-id="72901-162">about_Providers</span><span class="sxs-lookup"><span data-stu-id="72901-162">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

