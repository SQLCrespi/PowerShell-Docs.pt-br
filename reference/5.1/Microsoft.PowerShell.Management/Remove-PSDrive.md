---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-psdrive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSDrive
ms.openlocfilehash: 4b9b466be3d52877056b948e4cc373991784416a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193951"
---
# <span data-ttu-id="09918-103">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="09918-103">Remove-PSDrive</span></span>

## <span data-ttu-id="09918-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="09918-104">SYNOPSIS</span></span>
<span data-ttu-id="09918-105">Exclui unidades temporárias do PowerShell e desconecta unidades de rede mapeadas.</span><span class="sxs-lookup"><span data-stu-id="09918-105">Deletes temporary PowerShell drives and disconnects mapped network drives.</span></span>

## <span data-ttu-id="09918-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="09918-106">SYNTAX</span></span>

### <span data-ttu-id="09918-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="09918-107">Name (Default)</span></span>

```
Remove-PSDrive [-Name] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="09918-108">Valor literal</span><span class="sxs-lookup"><span data-stu-id="09918-108">LiteralName</span></span>

```
Remove-PSDrive [-LiteralName] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="09918-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="09918-109">DESCRIPTION</span></span>

<span data-ttu-id="09918-110">O `Remove-PSDrive` cmdlet exclui unidades temporárias do PowerShell que foram criadas usando o `New-PSDrive` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09918-110">The `Remove-PSDrive` cmdlet deletes temporary PowerShell drives that were created by using the `New-PSDrive` cmdlet.</span></span>

<span data-ttu-id="09918-111">A partir do Windows PowerShell 3,0, o `Remove-PSDrive` também desconecta unidades de rede mapeadas, incluindo, mas não se limitando a, unidades criadas usando o `Persist` parâmetro de `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="09918-111">Beginning in Windows PowerShell 3.0, `Remove-PSDrive` also disconnects mapped network drives, including, but not limited to, drives created by using the `Persist` parameter of `New-PSDrive`.</span></span>

<span data-ttu-id="09918-112">`Remove-PSDrive` Não é possível excluir unidades físicas ou lógicas do Windows.</span><span class="sxs-lookup"><span data-stu-id="09918-112">`Remove-PSDrive` cannot delete Windows physical or logical drives.</span></span>

<span data-ttu-id="09918-113">A partir do Windows PowerShell 3,0, quando uma unidade externa é conectada ao computador, o PowerShell adiciona automaticamente um PSDrive ao sistema de arquivos que representa a nova unidade.</span><span class="sxs-lookup"><span data-stu-id="09918-113">Beginning in Windows PowerShell 3.0, when an external drive is connected to the computer, PowerShell automatically adds a PSDrive to the file system that represents the new drive.</span></span>
<span data-ttu-id="09918-114">Você não precisa reiniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09918-114">You do not need to restart PowerShell.</span></span>
<span data-ttu-id="09918-115">Da mesma forma, quando uma unidade externa é desconectada do computador, o PowerShell exclui automaticamente o PSDrive que representa a unidade removida.</span><span class="sxs-lookup"><span data-stu-id="09918-115">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the PSDrive that represents the removed drive.</span></span>

## <span data-ttu-id="09918-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="09918-116">EXAMPLES</span></span>

### <span data-ttu-id="09918-117">Exemplo 1: remover uma unidade do sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="09918-117">Example 1: Remove a file system drive</span></span>

<span data-ttu-id="09918-118">Este comando remove uma unidade de sistema de arquivos temporária chamada "smp".</span><span class="sxs-lookup"><span data-stu-id="09918-118">This command removes a temporary file system drive named "smp".</span></span>

```powershell
Remove-PSDrive -Name smp
```

### <span data-ttu-id="09918-119">Exemplo 2: remover unidades de rede mapeadas</span><span class="sxs-lookup"><span data-stu-id="09918-119">Example 2: Remove mapped network drives</span></span>

<span data-ttu-id="09918-120">Esse comando usa `Remove-PSDrive` para desconectar as unidades de rede de X: e S: mapeadas.</span><span class="sxs-lookup"><span data-stu-id="09918-120">This command uses `Remove-PSDrive` to disconnect the X: and S: mapped network drives.</span></span>

```powershell
Get-PSDrive X, S | Remove-PSDrive
```

## <span data-ttu-id="09918-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="09918-121">PARAMETERS</span></span>

### <span data-ttu-id="09918-122">-Force</span><span class="sxs-lookup"><span data-stu-id="09918-122">-Force</span></span>

<span data-ttu-id="09918-123">Remove a unidade atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09918-123">Removes the current PowerShell drive.</span></span>

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

### <span data-ttu-id="09918-124">-LiteralName</span><span class="sxs-lookup"><span data-stu-id="09918-124">-LiteralName</span></span>

<span data-ttu-id="09918-125">Especifica o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="09918-125">Specifies the name of the drive.</span></span>

<span data-ttu-id="09918-126">O valor de **LiteralName** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="09918-126">The value of **LiteralName** is used exactly as typed.</span></span>
<span data-ttu-id="09918-127">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="09918-127">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="09918-128">Se o nome inclui caracteres de escape, coloque-o entre aspas simples (').</span><span class="sxs-lookup"><span data-stu-id="09918-128">If the name includes escape characters, enclose it in single quotation marks (').</span></span>
<span data-ttu-id="09918-129">As aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="09918-129">Single quotation marks instruct PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="09918-130">-Name</span><span class="sxs-lookup"><span data-stu-id="09918-130">-Name</span></span>

<span data-ttu-id="09918-131">Especifica os nomes das unidades a remover.</span><span class="sxs-lookup"><span data-stu-id="09918-131">Specifies the names of the drives to remove.</span></span>
<span data-ttu-id="09918-132">Não digite dois-pontos (:) após o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="09918-132">Do not type a colon (:) after the drive name.</span></span>

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

### <span data-ttu-id="09918-133">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="09918-133">-PSProvider</span></span>

<span data-ttu-id="09918-134">Especifica uma matriz de objetos **PSProvider** .</span><span class="sxs-lookup"><span data-stu-id="09918-134">Specifies an array of **PSProvider** objects.</span></span>
<span data-ttu-id="09918-135">Esse cmdlet Remove e desconecta todas as unidades associadas ao provedor do PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="09918-135">This cmdlet removes and disconnects all of the drives associated with the specified PowerShell provider.</span></span>

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

### <span data-ttu-id="09918-136">-Escopo</span><span class="sxs-lookup"><span data-stu-id="09918-136">-Scope</span></span>

<span data-ttu-id="09918-137">Especifica um escopo para a unidade.</span><span class="sxs-lookup"><span data-stu-id="09918-137">Specifies a scope for the drive.</span></span>
<span data-ttu-id="09918-138">Os valores aceitáveis para esse parâmetro são: global, local e script, ou um número relativo ao escopo atual.</span><span class="sxs-lookup"><span data-stu-id="09918-138">The acceptable values for this parameter are: Global, Local, and Script, or a number relative to the current scope.</span></span> <span data-ttu-id="09918-139">O número de escopos é 0 com o número de escopos.</span><span class="sxs-lookup"><span data-stu-id="09918-139">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="09918-140">O número de escopo atual é 0 e seu pai é 1.</span><span class="sxs-lookup"><span data-stu-id="09918-140">The current scope number is 0 and its parent is 1.</span></span>
<span data-ttu-id="09918-141">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="09918-141">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="09918-142">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="09918-142">-UseTransaction</span></span>

<span data-ttu-id="09918-143">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="09918-143">Includes the command in the active transaction.</span></span>
<span data-ttu-id="09918-144">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="09918-144">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="09918-145">Para obter mais informações, consulte about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="09918-145">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="09918-146">-Confirm</span><span class="sxs-lookup"><span data-stu-id="09918-146">-Confirm</span></span>

<span data-ttu-id="09918-147">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09918-147">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="09918-148">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="09918-148">-WhatIf</span></span>

<span data-ttu-id="09918-149">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="09918-149">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="09918-150">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="09918-150">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="09918-151">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="09918-151">CommonParameters</span></span>

<span data-ttu-id="09918-152">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="09918-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="09918-153">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="09918-153">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="09918-154">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="09918-154">INPUTS</span></span>

### <span data-ttu-id="09918-155">System.Management.Automation.PSDriveInfo</span><span class="sxs-lookup"><span data-stu-id="09918-155">System.Management.Automation.PSDriveInfo</span></span>

<span data-ttu-id="09918-156">É possível canalizar um objeto de unidade, como um do `Get-PSDrive` cmdlet, para o `Remove-PSDrive` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09918-156">You can pipe a drive object, such as one from the `Get-PSDrive` cmdlet, to the `Remove-PSDrive` cmdlet.</span></span>

## <span data-ttu-id="09918-157">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="09918-157">OUTPUTS</span></span>

### <span data-ttu-id="09918-158">Nenhum</span><span class="sxs-lookup"><span data-stu-id="09918-158">None</span></span>

<span data-ttu-id="09918-159">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="09918-159">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="09918-160">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="09918-160">NOTES</span></span>

- <span data-ttu-id="09918-161">O `Remove-PSDrive` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09918-161">The `Remove-PSDrive` cmdlet is designed to work with the data exposed by any PowerShell provider.</span></span> <span data-ttu-id="09918-162">Para listar os provedores em sua sessão, use o `Get-PSProvider` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09918-162">To list the providers in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="09918-163">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="09918-163">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="09918-164">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="09918-164">RELATED LINKS</span></span>

[<span data-ttu-id="09918-165">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="09918-165">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="09918-166">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="09918-166">New-PSDrive</span></span>](New-PSDrive.md)

[<span data-ttu-id="09918-167">about_Providers</span><span class="sxs-lookup"><span data-stu-id="09918-167">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
