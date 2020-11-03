---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-pscallstack?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSCallStack
ms.openlocfilehash: 0052543842f97dc1a19caae15222fd1b97d49902
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192618"
---
# <span data-ttu-id="2e33d-103">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="2e33d-103">Get-PSCallStack</span></span>

## <span data-ttu-id="2e33d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2e33d-104">SYNOPSIS</span></span>
<span data-ttu-id="2e33d-105">Exibe a pilha de chamadas atual.</span><span class="sxs-lookup"><span data-stu-id="2e33d-105">Displays the current call stack.</span></span>

## <span data-ttu-id="2e33d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e33d-106">SYNTAX</span></span>

```
Get-PSCallStack [<CommonParameters>]
```

## <span data-ttu-id="2e33d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2e33d-107">DESCRIPTION</span></span>

<span data-ttu-id="2e33d-108">O cmdlet **Get-PSCallStack** exibe a pilha de chamadas atual.</span><span class="sxs-lookup"><span data-stu-id="2e33d-108">The **Get-PSCallStack** cmdlet displays the current call stack.</span></span>

<span data-ttu-id="2e33d-109">Embora ele seja projetado para ser usado com o depurador do PowerShell, você pode usar este cmdlet para exibir a pilha de chamadas em um script ou função fora do depurador.</span><span class="sxs-lookup"><span data-stu-id="2e33d-109">Although it is designed to be used with the PowerShell debugger, you can use this cmdlet to display the call stack in a script or function outside of the debugger.</span></span>

<span data-ttu-id="2e33d-110">Para executar um comando **Get-PSCallStack** no depurador, digite `k` ou `Get-PSCallStack` .</span><span class="sxs-lookup"><span data-stu-id="2e33d-110">To run a **Get-PSCallStack** command while in the debugger, type `k` or `Get-PSCallStack`.</span></span>

## <span data-ttu-id="2e33d-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2e33d-111">EXAMPLES</span></span>

### <span data-ttu-id="2e33d-112">Exemplo 1: obter a pilha de chamadas para uma função</span><span class="sxs-lookup"><span data-stu-id="2e33d-112">Example 1: Get the call stack for a function</span></span>

```
PS C:\> function my-alias {
$p = $args[0]
Get-Alias | where {$_.definition -like "*$p"} | format-table definition, name -auto
}
PS C:\ps-test> Set-PSBreakpoint -Command my-alias
Command    : my-alias
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : prompt PS C:\> my-alias Get-Content

Entering debug mode. Use h or ? for help.
Hit Command breakpoint on 'prompt:my-alias'
my-alias get-content
[DBG]: PS C:\ps-test> s
$p = $args[0]
DEBUG: Stepped to ':    $p = $args[0]    '
[DBG]: PS C:\ps-test> s
get-alias | Where {$_.Definition -like "*$p*"} | format-table Definition,
[DBG]: PS C:\ps-test>get-pscallstack

Name        CommandLineParameters         UnboundArguments              Location
----        ---------------------         ----------------              --------
prompt      {}                            {}                            prompt
my-alias    {}                            {get-content}                 prompt
prompt      {}                            {}                            prompt PS C:\> [DBG]: PS C:\ps-test> o
Definition  Name
----------  ----
Get-Content gc
Get-Content cat
Get-Content type
```

<span data-ttu-id="2e33d-113">Esse comando usa o cmdlet **Get-PSCallStack** para exibir a pilha de chamadas para My-alias, uma função simples que obtém os aliases para um nome de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2e33d-113">This command uses the **Get-PSCallStack** cmdlet to display the call stack for My-Alias, a simple function that gets the aliases for a cmdlet name.</span></span>

<span data-ttu-id="2e33d-114">O primeiro comando insere a função no prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e33d-114">The first command enters the function at the PowerShell prompt.</span></span>
<span data-ttu-id="2e33d-115">O segundo comando usa o cmdlet Set-PSBreakpoint para definir um ponto de interrupção na função My-Alias.</span><span class="sxs-lookup"><span data-stu-id="2e33d-115">The second command uses the Set-PSBreakpoint cmdlet to set a breakpoint on the My-Alias function.</span></span>
<span data-ttu-id="2e33d-116">O terceiro comando usa a função My-Alias para obter todos os aliases na sessão atual para o cmdlet Get-Content.</span><span class="sxs-lookup"><span data-stu-id="2e33d-116">The third command uses the My-Alias function to get all of the aliases in the current session for the Get-Content cmdlet.</span></span>

<span data-ttu-id="2e33d-117">O depurador interrompe na chamada de função.</span><span class="sxs-lookup"><span data-stu-id="2e33d-117">The debugger breaks in at the function call.</span></span>
<span data-ttu-id="2e33d-118">Dois comandos set-into consecutivos iniciam a execução da função linha por linha.</span><span class="sxs-lookup"><span data-stu-id="2e33d-118">Two consecutive step-into (s) commands begin executing the function line by line.</span></span>
<span data-ttu-id="2e33d-119">Em seguida, um comando **Get-PSCallStack** é usado para recuperar a pilha de chamadas.</span><span class="sxs-lookup"><span data-stu-id="2e33d-119">Then, a **Get-PSCallStack** command is used to retrieve the call stack.</span></span>

<span data-ttu-id="2e33d-120">O comando final é um comando de Step-Out (o) que sai do depurador e continua executando o script até sua conclusão.</span><span class="sxs-lookup"><span data-stu-id="2e33d-120">The final command is a Step-Out command (o) that exits the debugger and continues executing the script to completion.</span></span>

## <span data-ttu-id="2e33d-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e33d-121">PARAMETERS</span></span>

### <span data-ttu-id="2e33d-122">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2e33d-122">CommonParameters</span></span>

<span data-ttu-id="2e33d-123">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2e33d-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e33d-124">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2e33d-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e33d-125">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2e33d-125">INPUTS</span></span>

### <span data-ttu-id="2e33d-126">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2e33d-126">None</span></span>

<span data-ttu-id="2e33d-127">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2e33d-127">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="2e33d-128">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2e33d-128">OUTPUTS</span></span>

### <span data-ttu-id="2e33d-129">System. Management. Automation. CallStackFrame</span><span class="sxs-lookup"><span data-stu-id="2e33d-129">System.Management.Automation.CallStackFrame</span></span>

<span data-ttu-id="2e33d-130">**Get-PSCallStack** retorna um objeto que representa os itens na pilha de chamadas.</span><span class="sxs-lookup"><span data-stu-id="2e33d-130">**Get-PSCallStack** returns an object that represents the items in the call stack.</span></span>

## <span data-ttu-id="2e33d-131">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2e33d-131">NOTES</span></span>

## <span data-ttu-id="2e33d-132">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2e33d-132">RELATED LINKS</span></span>

[<span data-ttu-id="2e33d-133">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2e33d-133">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="2e33d-134">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2e33d-134">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="2e33d-135">Format-Table</span><span class="sxs-lookup"><span data-stu-id="2e33d-135">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="2e33d-136">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2e33d-136">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="2e33d-137">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2e33d-137">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="2e33d-138">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2e33d-138">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
