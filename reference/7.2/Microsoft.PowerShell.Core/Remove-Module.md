---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Module
ms.openlocfilehash: 2954bbec68b837a73e5365ab6a1e8ecb501d4898
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596600"
---
# <span data-ttu-id="0ae50-102">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="0ae50-102">Remove-Module</span></span>

## <span data-ttu-id="0ae50-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0ae50-103">SYNOPSIS</span></span>
<span data-ttu-id="0ae50-104">Remove módulos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0ae50-104">Removes modules from the current session.</span></span>

## <span data-ttu-id="0ae50-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0ae50-105">SYNTAX</span></span>

### <span data-ttu-id="0ae50-106">name</span><span class="sxs-lookup"><span data-stu-id="0ae50-106">name</span></span>

```
Remove-Module [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0ae50-107">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="0ae50-107">FullyQualifiedName</span></span>

```
Remove-Module [-FullyQualifiedName] <ModuleSpecification[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0ae50-108">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="0ae50-108">ModuleInfo</span></span>

```
Remove-Module [-ModuleInfo] <PSModuleInfo[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0ae50-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0ae50-109">DESCRIPTION</span></span>

<span data-ttu-id="0ae50-110">O cmdlet **Remove-Module** remove os membros de um módulo, como cmdlets e funções, da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0ae50-110">The **Remove-Module** cmdlet removes the members of a module, such as cmdlets and functions, from the current session.</span></span>

<span data-ttu-id="0ae50-111">Se o módulo incluir um assembly (.dll), todos os membros que são implementados pelo assembly serão removidos, mas o assembly não será descarregado.</span><span class="sxs-lookup"><span data-stu-id="0ae50-111">If the module includes an assembly (.dll), all members that are implemented by the assembly are removed, but the assembly is not unloaded.</span></span>

<span data-ttu-id="0ae50-112">Esse cmdlet não desinstala o módulo nem o exclui do computador.</span><span class="sxs-lookup"><span data-stu-id="0ae50-112">This cmdlet does not uninstall the module or delete it from the computer.</span></span>
<span data-ttu-id="0ae50-113">Ele afeta apenas a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ae50-113">It affects only the current PowerShell session.</span></span>

## <span data-ttu-id="0ae50-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0ae50-114">EXAMPLES</span></span>

### <span data-ttu-id="0ae50-115">Exemplo 1: remover um módulo</span><span class="sxs-lookup"><span data-stu-id="0ae50-115">Example 1: Remove a module</span></span>

```powershell
Remove-Module -Name "BitsTransfer"
```

<span data-ttu-id="0ae50-116">Este comando remove o módulo BitsTransfer da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0ae50-116">This command removes the BitsTransfer module from the current session.</span></span>

### <span data-ttu-id="0ae50-117">Exemplo 2: remover todos os módulos</span><span class="sxs-lookup"><span data-stu-id="0ae50-117">Example 2: Remove all modules</span></span>

```powershell
Get-Module | Remove-Module
```

<span data-ttu-id="0ae50-118">Este comando remove todos os módulos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0ae50-118">This command removes all modules from the current session.</span></span>

### <span data-ttu-id="0ae50-119">Exemplo 3: remover módulos usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="0ae50-119">Example 3: Remove modules by using the pipeline</span></span>

```powershell
"FileTransfer", "PSDiagnostics" | Remove-Module -Verbose
```

```Output
VERBOSE: Performing operation "Remove-Module" on Target "filetransfer (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\filetransfer\filetransfer.psd1')".
VERBOSE: Performing operation "Remove-Module" on Target "Microsoft.BackgroundIntelligentTransfer.Management (Path: 'C:\Windows\assembly\GAC_MSIL\Microsoft.BackgroundIntelligentTransfer.Management\1.0.0.0__31bf3856ad364e35\Microsoft.BackgroundIntelligentTransfe
r.Management.dll')".
VERBOSE: Performing operation "Remove-Module" on Target "psdiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\psdiagnostics.psd1')".
VERBOSE: Removing imported function 'Start-Trace'.
VERBOSE: Removing imported function 'Stop-Trace'.
VERBOSE: Removing imported function 'Enable-WSManTrace'.
VERBOSE: Removing imported function 'Disable-WSManTrace'.
VERBOSE: Removing imported function 'Enable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Disable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Set-LogProperties'.
VERBOSE: Removing imported function 'Get-LogProperties'.
VERBOSE: Removing imported function 'Enable-PSTrace'.
VERBOSE: Removing imported function 'Disable-PSTrace'.
VERBOSE: Performing operation "Remove-Module" on Target "PSDiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\PSDiagnostics.psm1')".
```

<span data-ttu-id="0ae50-120">Este comando remove os módulos BitsTransfer e PSDiagnostics da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0ae50-120">This command removes the BitsTransfer and PSDiagnostics modules from the current session.</span></span>

<span data-ttu-id="0ae50-121">O comando usa um operador de pipeline (|) para enviar os nomes do módulo para **Remove-Module**.</span><span class="sxs-lookup"><span data-stu-id="0ae50-121">The command uses a pipeline operator (|) to send the module names to **Remove-Module**.</span></span>
<span data-ttu-id="0ae50-122">Ele usa o parâmetro comum *Verbose* para obter informações detalhadas sobre os membros que serão removidos.</span><span class="sxs-lookup"><span data-stu-id="0ae50-122">It uses the *Verbose* common parameter to get detailed information about the members that are removed.</span></span>

<span data-ttu-id="0ae50-123">As mensagens *detalhadas* mostram os itens que são removidos.</span><span class="sxs-lookup"><span data-stu-id="0ae50-123">The *Verbose* messages show the items that are removed.</span></span>
<span data-ttu-id="0ae50-124">As mensagens são diferentes porque o módulo BitsTransfer inclui um assembly que implementa seus cmdlets e um módulo aninhado com seu próprio assembly.</span><span class="sxs-lookup"><span data-stu-id="0ae50-124">The messages differ because the BitsTransfer module includes an assembly that implements its cmdlets and a nested module with its own assembly.</span></span>
<span data-ttu-id="0ae50-125">O módulo PSDiagnostics inclui um arquivo de script de módulo (.psm1) que exporta as funções.</span><span class="sxs-lookup"><span data-stu-id="0ae50-125">The PSDiagnostics module includes a module script file (.psm1) that exports functions.</span></span>

### <span data-ttu-id="0ae50-126">Exemplo 4: remover um módulo usando ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="0ae50-126">Example 4: Remove a module by using ModuleInfo</span></span>

```powershell
$a = Get-Module BitsTransfer
Remove-Module -ModuleInfo $a
```

<span data-ttu-id="0ae50-127">Esse comando usa o parâmetro *ModuleInfo* para remover o módulo BitsTransfer.</span><span class="sxs-lookup"><span data-stu-id="0ae50-127">This command uses the *ModuleInfo* parameter to remove the BitsTransfer module.</span></span>

## <span data-ttu-id="0ae50-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0ae50-128">PARAMETERS</span></span>

### <span data-ttu-id="0ae50-129">-Force</span><span class="sxs-lookup"><span data-stu-id="0ae50-129">-Force</span></span>

<span data-ttu-id="0ae50-130">Indica que este cmdlet Remove módulos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="0ae50-130">Indicates that this cmdlet removes read-only modules.</span></span>
<span data-ttu-id="0ae50-131">Por padrão, **Remove-Module** remove somente módulos de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="0ae50-131">By default, **Remove-Module** removes only read-write modules.</span></span>

<span data-ttu-id="0ae50-132">Os valores **ReadOnly** e **ReadWrite** são armazenados na propriedade **AccessMode** de um módulo.</span><span class="sxs-lookup"><span data-stu-id="0ae50-132">The **ReadOnly** and **ReadWrite** values are stored in **AccessMode** property of a module.</span></span>

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

### <span data-ttu-id="0ae50-133">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="0ae50-133">-FullyQualifiedName</span></span>

<span data-ttu-id="0ae50-134">Especifica os nomes totalmente qualificados dos módulos a serem removidos.</span><span class="sxs-lookup"><span data-stu-id="0ae50-134">Specifies the fully qualified names of modules to remove.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0ae50-135">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="0ae50-135">-ModuleInfo</span></span>

<span data-ttu-id="0ae50-136">Especifica os objetos do módulo a ser removido.</span><span class="sxs-lookup"><span data-stu-id="0ae50-136">Specifies the module objects to remove.</span></span>
<span data-ttu-id="0ae50-137">Insira uma variável que contém um objeto de módulo (**PSModuleInfo**) ou um comando que obtém um objeto de módulo, como um comando Get-Module.</span><span class="sxs-lookup"><span data-stu-id="0ae50-137">Enter a variable that contains a module object (**PSModuleInfo**) or a command that gets a module object, such as a Get-Module command.</span></span>
<span data-ttu-id="0ae50-138">Você também pode redirecionar objetos do módulo para **Remove-Module**.</span><span class="sxs-lookup"><span data-stu-id="0ae50-138">You can also pipe module objects to **Remove-Module**.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0ae50-139">-Name</span><span class="sxs-lookup"><span data-stu-id="0ae50-139">-Name</span></span>

<span data-ttu-id="0ae50-140">Especifica os nomes dos módulos a serem removidos.</span><span class="sxs-lookup"><span data-stu-id="0ae50-140">Specifies the names of modules to remove.</span></span>
<span data-ttu-id="0ae50-141">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0ae50-141">Wildcard characters are permitted.</span></span>
<span data-ttu-id="0ae50-142">Também é possível redirecionar cadeias de caracteres de nomes para **Remove-Module**.</span><span class="sxs-lookup"><span data-stu-id="0ae50-142">You can also pipe name strings to **Remove-Module**.</span></span>

```yaml
Type: System.String[]
Parameter Sets: name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="0ae50-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0ae50-143">-Confirm</span></span>

<span data-ttu-id="0ae50-144">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0ae50-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0ae50-145">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0ae50-145">-WhatIf</span></span>

<span data-ttu-id="0ae50-146">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0ae50-146">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0ae50-147">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0ae50-147">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0ae50-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0ae50-148">CommonParameters</span></span>

<span data-ttu-id="0ae50-149">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0ae50-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0ae50-150">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0ae50-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0ae50-151">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0ae50-151">INPUTS</span></span>

### <span data-ttu-id="0ae50-152">System. String, System. Management. Automation. PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="0ae50-152">System.String, System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="0ae50-153">Você pode canalizar nomes de módulo e objetos de módulo para **Remove-Module**.</span><span class="sxs-lookup"><span data-stu-id="0ae50-153">You can pipe module names and module objects to **Remove-Module**.</span></span>

## <span data-ttu-id="0ae50-154">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0ae50-154">OUTPUTS</span></span>

### <span data-ttu-id="0ae50-155">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0ae50-155">None</span></span>

<span data-ttu-id="0ae50-156">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="0ae50-156">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0ae50-157">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0ae50-157">NOTES</span></span>

<span data-ttu-id="0ae50-158">Ao remover um módulo, há um evento no módulo que será executado.</span><span class="sxs-lookup"><span data-stu-id="0ae50-158">When removing a module, there is an event on the module that will execute.</span></span>
<span data-ttu-id="0ae50-159">Esse evento permite que um módulo reaja a ser removido e execute alguma limpeza, como liberar recursos.</span><span class="sxs-lookup"><span data-stu-id="0ae50-159">This event allows a module to react to being removed and perform some cleanup such as freeing up resources.</span></span> <span data-ttu-id="0ae50-160">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="0ae50-160">Example:</span></span>

<span data-ttu-id="0ae50-161">$OnRemoveScript = {</span><span class="sxs-lookup"><span data-stu-id="0ae50-161">$OnRemoveScript = {</span></span>

  <span data-ttu-id="0ae50-162">\# executar limpeza</span><span class="sxs-lookup"><span data-stu-id="0ae50-162">\# perform cleanup</span></span>

  <span data-ttu-id="0ae50-163">$cachedSessions | Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="0ae50-163">$cachedSessions | Remove-PSSession</span></span>

<span data-ttu-id="0ae50-164">}</span><span class="sxs-lookup"><span data-stu-id="0ae50-164">}</span></span>

<span data-ttu-id="0ae50-165">$ExecutionContext. SessionState. Module. OnRemove + = $OnRemoveScript</span><span class="sxs-lookup"><span data-stu-id="0ae50-165">$ExecutionContext.SessionState.Module.OnRemove += $OnRemoveScript</span></span>

<span data-ttu-id="0ae50-166">Para consistência total, pode ser útil reagir ao fechamento do processo do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0ae50-166">For full consistency, it might be also useful to react to the closing of the PowerShell process:</span></span>

<span data-ttu-id="0ae50-167">Register-EngineEvent-SourceIdentifier ([System. Management. Automation. PsEngineEvent]:: saindo)-ação $OnRemoveScript</span><span class="sxs-lookup"><span data-stu-id="0ae50-167">Register-EngineEvent -SourceIdentifier ([System.Management.Automation.PsEngineEvent]::Exiting) -Action $OnRemoveScript</span></span>

## <span data-ttu-id="0ae50-168">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0ae50-168">RELATED LINKS</span></span>

[<span data-ttu-id="0ae50-169">Get-Module</span><span class="sxs-lookup"><span data-stu-id="0ae50-169">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="0ae50-170">Import-Module</span><span class="sxs-lookup"><span data-stu-id="0ae50-170">Import-Module</span></span>](Import-Module.md)

