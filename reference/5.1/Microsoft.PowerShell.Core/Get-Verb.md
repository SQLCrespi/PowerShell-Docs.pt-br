---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
ms.date: 09/07/2018
Module Name: Microsoft.PowerShell.Core
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/functions/get-verb?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 4474bb50c2bf3be10e72d2554190208e956f9040
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2020
ms.locfileid: "93195208"
---
# <span data-ttu-id="3257d-103">Get-Verb</span><span class="sxs-lookup"><span data-stu-id="3257d-103">Get-Verb</span></span>

## <span data-ttu-id="3257d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3257d-104">SYNOPSIS</span></span>
<span data-ttu-id="3257d-105">Obtém os verbos aprovados do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3257d-105">Gets approved PowerShell verbs.</span></span>

## <span data-ttu-id="3257d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3257d-106">SYNTAX</span></span>

```
Get-Verb [[-verb] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="3257d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3257d-107">DESCRIPTION</span></span>

<span data-ttu-id="3257d-108">A `Get-Verb` função obtém verbos que são aprovados para uso em comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3257d-108">The `Get-Verb` function gets verbs that are approved for use in PowerShell commands.</span></span>

<span data-ttu-id="3257d-109">O PowerShell recomenda que os nomes de cmdlet e de função tenham o formato Verb-Noun e incluam um verbo aprovado.</span><span class="sxs-lookup"><span data-stu-id="3257d-109">PowerShell recommends cmdlet and function names have the Verb-Noun format and include an approved verb.</span></span> <span data-ttu-id="3257d-110">Essa prática torna os nomes de comando mais consistentes, previsíveis e fáceis de usar.</span><span class="sxs-lookup"><span data-stu-id="3257d-110">This practice makes command names more consistent, predictable, and easier to use.</span></span>

<span data-ttu-id="3257d-111">Comandos que usam verbos não aprovados são executados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3257d-111">Commands that use unapproved verbs run in PowerShell.</span></span> <span data-ttu-id="3257d-112">No entanto, quando você importa um módulo que inclui um comando com um verbo não aprovado em seu nome, o `Import-Module` comando exibe uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="3257d-112">However, when you import a module that includes a command with an unapproved verb in its name, the `Import-Module` command displays a warning message.</span></span>

> [!NOTE]
> <span data-ttu-id="3257d-113">A lista de verbos que `Get-Verb` retorna pode não estar concluída.</span><span class="sxs-lookup"><span data-stu-id="3257d-113">The verb list that `Get-Verb` returns might not be complete.</span></span> <span data-ttu-id="3257d-114">Para obter uma lista atualizada de verbos aprovados do PowerShell com descrições, consulte [verbos aprovados](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) no Microsoft docs.</span><span class="sxs-lookup"><span data-stu-id="3257d-114">For an updated list of approved PowerShell verbs with descriptions, see [Approved Verbs](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in the Microsoft Docs.</span></span>

## <span data-ttu-id="3257d-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3257d-115">EXAMPLES</span></span>

### <span data-ttu-id="3257d-116">Exemplo 1-obter uma lista de todos os verbos</span><span class="sxs-lookup"><span data-stu-id="3257d-116">Example 1 - Get a list of all verbs</span></span>

```powershell
Get-Verb
```

### <span data-ttu-id="3257d-117">Exemplo 2 – obter uma lista de verbos aprovados que começam com "un"</span><span class="sxs-lookup"><span data-stu-id="3257d-117">Example 2 - Get a list of approved verbs that begin with "un"</span></span>

```powershell
Get-Verb un*
```

```Output
Verb                 Group
----                 -----
Undo                 Common
Unlock               Common
Unpublish            Data
Uninstall            Lifecycle
Unregister           Lifecycle
Unblock              Security
Unprotect            Security
```

### <span data-ttu-id="3257d-118">Exemplo 3-obter todos os verbos aprovados no grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="3257d-118">Example 3 - Get all approved verbs in the Security group</span></span>

```powershell
Get-Verb | Where-Object Group -EQ Security
```

```Output
Verb      Group
----      -----
Block     Security
Grant     Security
Protect   Security
Revoke    Security
Unblock   Security
Unprotect Security
```

### <span data-ttu-id="3257d-119">Exemplo 4-localiza todos os comandos em um módulo que têm verbos não aprovados</span><span class="sxs-lookup"><span data-stu-id="3257d-119">Example 4 - Finds all commands in a module that have unapproved verbs</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## <span data-ttu-id="3257d-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3257d-120">PARAMETERS</span></span>

### <span data-ttu-id="3257d-121">-verbo</span><span class="sxs-lookup"><span data-stu-id="3257d-121">-verb</span></span>

<span data-ttu-id="3257d-122">Obtém somente os verbos especificados.</span><span class="sxs-lookup"><span data-stu-id="3257d-122">Gets only the specified verbs.</span></span>
<span data-ttu-id="3257d-123">Digite o nome de um verbo ou um padrão de nome.</span><span class="sxs-lookup"><span data-stu-id="3257d-123">Enter the name of a verb or a name pattern.</span></span>
<span data-ttu-id="3257d-124">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="3257d-124">Wildcards are allowed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: All verbs
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## <span data-ttu-id="3257d-125">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3257d-125">INPUTS</span></span>

### <span data-ttu-id="3257d-126">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3257d-126">None</span></span>

## <span data-ttu-id="3257d-127">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3257d-127">OUTPUTS</span></span>

### <span data-ttu-id="3257d-128">Selected.Microsoft.PowerShell.Commands.MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="3257d-128">Selected.Microsoft.PowerShell.Commands.MemberDefinition</span></span>

## <span data-ttu-id="3257d-129">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3257d-129">NOTES</span></span>

<span data-ttu-id="3257d-130">`Get-Verb` Retorna uma versão modificada de um objeto Microsoft. PowerShell. Commands. MemberDefinition.</span><span class="sxs-lookup"><span data-stu-id="3257d-130">`Get-Verb` returns a modified version of a Microsoft.PowerShell.Commands.MemberDefinition object.</span></span>
<span data-ttu-id="3257d-131">O objeto não tem as propriedades padrão de um objeto MemberDefinition.</span><span class="sxs-lookup"><span data-stu-id="3257d-131">The object does not have the standard properties of a MemberDefinition object.</span></span> <span data-ttu-id="3257d-132">Em vez disso, ela tem propriedades Verbo e Grupo.</span><span class="sxs-lookup"><span data-stu-id="3257d-132">Instead it has Verb and Group properties.</span></span> <span data-ttu-id="3257d-133">A propriedade Verbo contém uma cadeia de caracteres com o nome do verbo.</span><span class="sxs-lookup"><span data-stu-id="3257d-133">The Verb property contains a string with the verb name.</span></span> <span data-ttu-id="3257d-134">A propriedade Grupo contém uma cadeia de caracteres com o grupo do verbo.</span><span class="sxs-lookup"><span data-stu-id="3257d-134">The Group property contains a string with the verb group.</span></span>

<span data-ttu-id="3257d-135">Os verbos do PowerShell são atribuídos a um grupo com base no uso mais comum.</span><span class="sxs-lookup"><span data-stu-id="3257d-135">PowerShell verbs are assigned to a group based on their most common use.</span></span> <span data-ttu-id="3257d-136">Os grupos são projetados para facilitar a localização e a comparação com o uso dos verbos, não para impedir seu uso.</span><span class="sxs-lookup"><span data-stu-id="3257d-136">The groups are designed to make the verbs easy to find and compare, not to restrict their use.</span></span> <span data-ttu-id="3257d-137">Você pode usar qualquer verbo aprovado para qualquer tipo de comando.</span><span class="sxs-lookup"><span data-stu-id="3257d-137">You can use any approved verb for any type of command.</span></span>

<span data-ttu-id="3257d-138">Cada verbo do PowerShell é atribuído a um dos grupos a seguir.</span><span class="sxs-lookup"><span data-stu-id="3257d-138">Each PowerShell verb is assigned to one of the following groups.</span></span>

- <span data-ttu-id="3257d-139">Comum: defina ações genéricas que podem ser aplicadas a quase qualquer cmdlet, como adicionar.</span><span class="sxs-lookup"><span data-stu-id="3257d-139">Common: Define generic actions that can apply to almost any cmdlet, such as Add.</span></span>
- <span data-ttu-id="3257d-140">Comunicações: defina as ações que se aplicam a comunicações, como conectar.</span><span class="sxs-lookup"><span data-stu-id="3257d-140">Communications:  Define actions that apply to communications, such as Connect.</span></span>
- <span data-ttu-id="3257d-141">Dados: defina as ações que se aplicam à manipulação de dados, como backup.</span><span class="sxs-lookup"><span data-stu-id="3257d-141">Data:  Define actions that apply to data handling, such as Backup.</span></span>
- <span data-ttu-id="3257d-142">Diagnóstico: defina as ações que se aplicam ao diagnóstico, como depurar.</span><span class="sxs-lookup"><span data-stu-id="3257d-142">Diagnostic: Define actions that apply to diagnostics, such as Debug.</span></span>
- <span data-ttu-id="3257d-143">Ciclo de vida: defina as ações que se aplicam ao ciclo de vida de um cmdlet, como concluído.</span><span class="sxs-lookup"><span data-stu-id="3257d-143">Lifecycle: Define actions that apply to the lifecycle of a cmdlet, such as Complete.</span></span>
- <span data-ttu-id="3257d-144">Segurança: defina as ações que se aplicam à segurança, como REVOKE.</span><span class="sxs-lookup"><span data-stu-id="3257d-144">Security: Define actions that apply to security, such as Revoke.</span></span>
- <span data-ttu-id="3257d-145">Outro: defina outros tipos de ações.</span><span class="sxs-lookup"><span data-stu-id="3257d-145">Other: Define other types of actions.</span></span>

<span data-ttu-id="3257d-146">Alguns dos cmdlets instalados com o PowerShell, como `Tee-Object` e `Where-Object` , usam verbos não aprovados.</span><span class="sxs-lookup"><span data-stu-id="3257d-146">Some of the cmdlets that are installed with PowerShell, such as `Tee-Object` and `Where-Object`, use unapproved verbs.</span></span> <span data-ttu-id="3257d-147">Esses cmdlets são exceções históricas e seus verbos são classificados como **reservados** .</span><span class="sxs-lookup"><span data-stu-id="3257d-147">These cmdlets are historic exceptions and their verbs are classified as **reserved** .</span></span>

## <span data-ttu-id="3257d-148">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3257d-148">RELATED LINKS</span></span>

[<span data-ttu-id="3257d-149">Import-Module</span><span class="sxs-lookup"><span data-stu-id="3257d-149">Import-Module</span></span>](import-module.md)
