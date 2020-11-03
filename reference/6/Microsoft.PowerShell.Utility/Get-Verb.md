---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/07/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-verb?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 516ecf2b5d6e3bce2a0cda7c36c143d2ba75933a
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2020
ms.locfileid: "93195211"
---
# <span data-ttu-id="5bd27-103">Get-Verb</span><span class="sxs-lookup"><span data-stu-id="5bd27-103">Get-Verb</span></span>

## <span data-ttu-id="5bd27-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5bd27-104">SYNOPSIS</span></span>
<span data-ttu-id="5bd27-105">Obtém os verbos aprovados do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5bd27-105">Gets approved PowerShell verbs.</span></span>

## <span data-ttu-id="5bd27-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5bd27-106">SYNTAX</span></span>

```
Get-Verb [[-Verb] <String[]>] [[-Group] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="5bd27-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5bd27-107">DESCRIPTION</span></span>

<span data-ttu-id="5bd27-108">A `Get-Verb` função obtém verbos que são aprovados para uso em comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5bd27-108">The `Get-Verb` function gets verbs that are approved for use in PowerShell commands.</span></span>

<span data-ttu-id="5bd27-109">É recomendável que os nomes de cmdlet e de função do PowerShell tenham o `Verb-Noun` formato e incluam um verbo aprovado.</span><span class="sxs-lookup"><span data-stu-id="5bd27-109">It is recommended that PowerShell cmdlet and function names have the `Verb-Noun` format and include an approved verb.</span></span> <span data-ttu-id="5bd27-110">Essa prática torna os nomes de comando mais consistentes, previsíveis e fáceis de usar.</span><span class="sxs-lookup"><span data-stu-id="5bd27-110">This practice makes command names more consistent, predictable, and easier to use.</span></span>

<span data-ttu-id="5bd27-111">Comandos que usam verbos não aprovados, ainda são executados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5bd27-111">Commands that use unapproved verbs, still run in PowerShell.</span></span> <span data-ttu-id="5bd27-112">No entanto, quando você importa um módulo que inclui um comando com um verbo não aprovado em seu nome, o `Import-Module` comando exibe uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="5bd27-112">However, when you import a module that includes a command with an unapproved verb in its name, the `Import-Module` command displays a warning message.</span></span>

> [!NOTE]
> <span data-ttu-id="5bd27-113">A lista de verbos que `Get-Verb` retorna pode não estar concluída.</span><span class="sxs-lookup"><span data-stu-id="5bd27-113">The verb list that `Get-Verb` returns might not be complete.</span></span> <span data-ttu-id="5bd27-114">Para obter uma lista atualizada de verbos aprovados do PowerShell com descrições, consulte [verbos aprovados](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) no Microsoft docs.</span><span class="sxs-lookup"><span data-stu-id="5bd27-114">For an updated list of approved PowerShell verbs with descriptions, see [Approved Verbs](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in the Microsoft Docs.</span></span>

## <span data-ttu-id="5bd27-115">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5bd27-115">Examples</span></span>

### <span data-ttu-id="5bd27-116">Exemplo 1-obter uma lista de todos os verbos</span><span class="sxs-lookup"><span data-stu-id="5bd27-116">Example 1 - Get a list of all verbs</span></span>

```powershell
Get-Verb
```

### <span data-ttu-id="5bd27-117">Exemplo 2 – obter uma lista de verbos aprovados que começam com "un"</span><span class="sxs-lookup"><span data-stu-id="5bd27-117">Example 2 - Get a list of approved verbs that begin with "un"</span></span>

```powershell
Get-Verb un*
```

```Output
Verb       AliasPrefix Group     Description
----       ----------- -----     -----------
Undo       un          Common    Sets a resource to its previous state
Unlock     uk          Common    Releases a resource that was locked
Unpublish  ub          Data      Makes a resource unavailable to others
Uninstall  us          Lifecycle Removes a resource from an indicated location
Unregister ur          Lifecycle Removes the entry for a resource from a repository
Unblock    ul          Security  Removes restrictions to a resource
Unprotect  up          Security  Removes safeguards from a resource that were added to prevent it from attack or loss
```

### <span data-ttu-id="5bd27-118">Exemplo 3-obter todos os verbos aprovados no grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="5bd27-118">Example 3 - Get all approved verbs in the Security group</span></span>

```powershell
Get-Verb -Group Security
```

```Output
Verb      AliasPrefix Group    Description
----      ----------- -----    -----------
Block     bl          Security Restricts access to a resource
Grant     gr          Security Allows access to a resource
Protect   pt          Security Safeguards a resource from attack or loss
Revoke    rk          Security Specifies an action that does not allow access to a resource
Unblock   ul          Security Removes restrictions to a resource
Unprotect up          Security Removes safeguards from a resource that were added to prevent it from attack or loss
```

### <span data-ttu-id="5bd27-119">Exemplo 4-localiza todos os comandos em um módulo que têm verbos não aprovados</span><span class="sxs-lookup"><span data-stu-id="5bd27-119">Example 4 - Finds all commands in a module that have unapproved verbs</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## <span data-ttu-id="5bd27-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5bd27-120">PARAMETERS</span></span>

### <span data-ttu-id="5bd27-121">-Verbo</span><span class="sxs-lookup"><span data-stu-id="5bd27-121">-Verb</span></span>

<span data-ttu-id="5bd27-122">Obtém somente os verbos especificados.</span><span class="sxs-lookup"><span data-stu-id="5bd27-122">Gets only the specified verbs.</span></span> <span data-ttu-id="5bd27-123">Digite o nome de um verbo ou um padrão de nome.</span><span class="sxs-lookup"><span data-stu-id="5bd27-123">Enter the name of a verb or a name pattern.</span></span> <span data-ttu-id="5bd27-124">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5bd27-124">Wildcards are allowed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Common, Communications, Data, Diagnostic, Lifecycle, Other, Security

Required: False
Position: 1
Default value: All groups
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="5bd27-125">-Grupo</span><span class="sxs-lookup"><span data-stu-id="5bd27-125">-Group</span></span>

<span data-ttu-id="5bd27-126">Obtém somente os grupos especificados.</span><span class="sxs-lookup"><span data-stu-id="5bd27-126">Gets only the specified groups.</span></span> <span data-ttu-id="5bd27-127">Insira o nome de um grupo.</span><span class="sxs-lookup"><span data-stu-id="5bd27-127">Enter the name of a group.</span></span> <span data-ttu-id="5bd27-128">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5bd27-128">Wildcards are not allowed.</span></span>

<span data-ttu-id="5bd27-129">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="5bd27-129">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All verbs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5bd27-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5bd27-130">CommonParameters</span></span>

<span data-ttu-id="5bd27-131">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5bd27-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5bd27-132">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5bd27-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5bd27-133">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5bd27-133">INPUTS</span></span>

### <span data-ttu-id="5bd27-134">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5bd27-134">None</span></span>

## <span data-ttu-id="5bd27-135">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5bd27-135">OUTPUTS</span></span>

### <span data-ttu-id="5bd27-136">System. Management. Automation. VerbInfo</span><span class="sxs-lookup"><span data-stu-id="5bd27-136">System.Management.Automation.VerbInfo</span></span>

## <span data-ttu-id="5bd27-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5bd27-137">NOTES</span></span>

<span data-ttu-id="5bd27-138">Os verbos do PowerShell são atribuídos a um grupo com base no uso mais comum.</span><span class="sxs-lookup"><span data-stu-id="5bd27-138">PowerShell verbs are assigned to a group based on their most common use.</span></span> <span data-ttu-id="5bd27-139">Os grupos são projetados para facilitar a localização e a comparação com o uso dos verbos, não para impedir seu uso.</span><span class="sxs-lookup"><span data-stu-id="5bd27-139">The groups are designed to make the verbs easy to find and compare, not to restrict their use.</span></span> <span data-ttu-id="5bd27-140">Você pode usar qualquer verbo aprovado para qualquer tipo de comando.</span><span class="sxs-lookup"><span data-stu-id="5bd27-140">You can use any approved verb for any type of command.</span></span>

<span data-ttu-id="5bd27-141">Cada verbo do PowerShell é atribuído a um dos grupos a seguir.</span><span class="sxs-lookup"><span data-stu-id="5bd27-141">Each PowerShell verb is assigned to one of the following groups.</span></span>

- <span data-ttu-id="5bd27-142">Comum: defina ações genéricas que podem ser aplicadas a quase qualquer cmdlet, como adicionar.</span><span class="sxs-lookup"><span data-stu-id="5bd27-142">Common: Define generic actions that can apply to almost any cmdlet, such as Add.</span></span>
- <span data-ttu-id="5bd27-143">Comunicações: defina as ações que se aplicam a comunicações, como conectar.</span><span class="sxs-lookup"><span data-stu-id="5bd27-143">Communications: Define actions that apply to communications, such as Connect.</span></span>
- <span data-ttu-id="5bd27-144">Dados: defina as ações que se aplicam à manipulação de dados, como backup.</span><span class="sxs-lookup"><span data-stu-id="5bd27-144">Data: Define actions that apply to data handling, such as Backup.</span></span>
- <span data-ttu-id="5bd27-145">Diagnóstico: defina as ações que se aplicam ao diagnóstico, como depurar.</span><span class="sxs-lookup"><span data-stu-id="5bd27-145">Diagnostic: Define actions that apply to diagnostics, such as Debug.</span></span>
- <span data-ttu-id="5bd27-146">Ciclo de vida: defina as ações que se aplicam ao ciclo de vida de um cmdlet, como concluído.</span><span class="sxs-lookup"><span data-stu-id="5bd27-146">Lifecycle: Define actions that apply to the lifecycle of a cmdlet, such as Complete.</span></span>
- <span data-ttu-id="5bd27-147">Segurança: defina as ações que se aplicam à segurança, como REVOKE.</span><span class="sxs-lookup"><span data-stu-id="5bd27-147">Security: Define actions that apply to security, such as Revoke.</span></span>
- <span data-ttu-id="5bd27-148">Outro: defina outros tipos de ações.</span><span class="sxs-lookup"><span data-stu-id="5bd27-148">Other: Define other types of actions.</span></span>

<span data-ttu-id="5bd27-149">Alguns dos cmdlets instalados com o PowerShell, como `Tee-Object` e `Where-Object` , usam verbos não aprovados.</span><span class="sxs-lookup"><span data-stu-id="5bd27-149">Some of the cmdlets that are installed with PowerShell, such as `Tee-Object` and `Where-Object`, use unapproved verbs.</span></span> <span data-ttu-id="5bd27-150">Esses cmdlets são exceções históricas e seus verbos são classificados como **reservados** .</span><span class="sxs-lookup"><span data-stu-id="5bd27-150">These cmdlets are historic exceptions and their verbs are classified as **reserved** .</span></span>

## <span data-ttu-id="5bd27-151">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5bd27-151">RELATED LINKS</span></span>

[<span data-ttu-id="5bd27-152">Import-Module</span><span class="sxs-lookup"><span data-stu-id="5bd27-152">Import-Module</span></span>](../microsoft.powershell.core/import-module.md)
