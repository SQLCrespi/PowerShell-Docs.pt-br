---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: b12b95cc46f6966c63fd8fd60c42d5417c4c7868
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196597"
---
# <span data-ttu-id="4c8d4-103">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="4c8d4-103">Set-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="4c8d4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4c8d4-104">SYNOPSIS</span></span>
<span data-ttu-id="4c8d4-105">Associa as chaves às funções de manipulador de chave definidas pelo usuário ou PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-105">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

## <span data-ttu-id="4c8d4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4c8d4-106">SYNTAX</span></span>

### <span data-ttu-id="4c8d4-107">Bloco de script</span><span class="sxs-lookup"><span data-stu-id="4c8d4-107">ScriptBlock</span></span>

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### <span data-ttu-id="4c8d4-108">Função</span><span class="sxs-lookup"><span data-stu-id="4c8d4-108">Function</span></span>

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## <span data-ttu-id="4c8d4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4c8d4-109">DESCRIPTION</span></span>

<span data-ttu-id="4c8d4-110">O `Set-PSReadLineKeyHandler` cmdlet personaliza o resultado quando uma chave ou sequência de teclas é pressionada.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-110">The `Set-PSReadLineKeyHandler` cmdlet customizes the result when a key or sequence of keys is pressed.</span></span> <span data-ttu-id="4c8d4-111">Com as associações de chave definidas pelo usuário, você pode fazer quase tudo o que for possível de dentro de um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-111">With user-defined key bindings, you can do almost anything that is possible from within a PowerShell script.</span></span>

## <span data-ttu-id="4c8d4-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4c8d4-112">EXAMPLES</span></span>

### <span data-ttu-id="4c8d4-113">Exemplo 1: associar a tecla de seta a uma função</span><span class="sxs-lookup"><span data-stu-id="4c8d4-113">Example 1: Bind the arrow key to a function</span></span>

<span data-ttu-id="4c8d4-114">Esse comando associa a tecla de seta para cima à função **HistorySearchBackward** .</span><span class="sxs-lookup"><span data-stu-id="4c8d4-114">This command binds the up arrow key to the **HistorySearchBackward** function.</span></span> <span data-ttu-id="4c8d4-115">Essa função pesquisa o histórico de comandos para linhas de comando que começam com o conteúdo atual da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-115">This function searches command history for command lines that start with the current contents of the command line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### <span data-ttu-id="4c8d4-116">Exemplo 2: associar uma chave a um bloco de script</span><span class="sxs-lookup"><span data-stu-id="4c8d4-116">Example 2: Bind a key to a script block</span></span>

<span data-ttu-id="4c8d4-117">Este exemplo mostra como uma única chave pode ser usada para executar um comando.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-117">This example shows how a single key can be used to run a command.</span></span> <span data-ttu-id="4c8d4-118">O comando associa a chave `Ctrl+B` a um bloco de script que limpa a linha, insere a palavra "Build" e, em seguida, aceita a linha.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-118">The command binds the key `Ctrl+B` to a script block that clears the line, inserts the word "build", and then accepts the line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## <span data-ttu-id="4c8d4-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4c8d4-119">PARAMETERS</span></span>

### <span data-ttu-id="4c8d4-120">-BriefDescription</span><span class="sxs-lookup"><span data-stu-id="4c8d4-120">-BriefDescription</span></span>

<span data-ttu-id="4c8d4-121">Uma breve descrição da Associação de chave.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-121">A brief description of the key binding.</span></span> <span data-ttu-id="4c8d4-122">Essa descrição é exibida pelo `Get-PSReadLineKeyHandler` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-122">This description is displayed by the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4c8d4-123">-Corda</span><span class="sxs-lookup"><span data-stu-id="4c8d4-123">-Chord</span></span>

<span data-ttu-id="4c8d4-124">A chave ou a sequência de chaves a serem associadas a um bloco de função ou de script.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-124">The key or sequence of keys to be bound to a function or script block.</span></span> <span data-ttu-id="4c8d4-125">Use uma única cadeia de caracteres para especificar uma única associação.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-125">Use a single string to specify a single binding.</span></span> <span data-ttu-id="4c8d4-126">Se a associação for uma sequência de chaves, separe as chaves por uma vírgula, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4c8d4-126">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+X,Ctrl+L`

<span data-ttu-id="4c8d4-127">Esse parâmetro aceita uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-127">This parameter accepts an array of strings.</span></span> <span data-ttu-id="4c8d4-128">Cada cadeia de caracteres é uma associação separada, não uma sequência de chaves para uma única associação.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-128">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4c8d4-129">-Description</span><span class="sxs-lookup"><span data-stu-id="4c8d4-129">-Description</span></span>

<span data-ttu-id="4c8d4-130">Especifica uma descrição mais detalhada da Associação de chave que está visível na saída do `Get-PSReadLineKeyHandler` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-130">Specifies a more detailed description of the key binding that is visible in the output of the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases: LongDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4c8d4-131">-Função</span><span class="sxs-lookup"><span data-stu-id="4c8d4-131">-Function</span></span>

<span data-ttu-id="4c8d4-132">Especifica o nome de um manipulador de chave existente fornecido por PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-132">Specifies the name of an existing key handler provided by PSReadLine.</span></span> <span data-ttu-id="4c8d4-133">Esse parâmetro permite que você reassocie as associações de chave existentes ou associe um manipulador que atualmente não está associado.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-133">This parameter lets you rebind existing key bindings, or bind a handler that is currently unbound.</span></span>

```yaml
Type: System.String
Parameter Sets: Function
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4c8d4-134">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="4c8d4-134">-ScriptBlock</span></span>

<span data-ttu-id="4c8d4-135">Especifica um valor de bloco de script a ser executado quando a corda é inserida.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-135">Specifies a script block value to run when the chord is entered.</span></span> <span data-ttu-id="4c8d4-136">PSReadLine passa um ou dois parâmetros para esse bloco de script.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-136">PSReadLine passes one or two parameters to this script block.</span></span> <span data-ttu-id="4c8d4-137">O primeiro parâmetro é um objeto **ConsoleKeyInfo** que representa a chave pressionada.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-137">The first parameter is a **ConsoleKeyInfo** object representing the key pressed.</span></span> <span data-ttu-id="4c8d4-138">O segundo argumento pode ser qualquer objeto, dependendo do contexto.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-138">The second argument can be any object depending on the context.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4c8d4-139">-ViMode</span><span class="sxs-lookup"><span data-stu-id="4c8d4-139">-ViMode</span></span>

<span data-ttu-id="4c8d4-140">Especifique a qual modo vi a associação se aplica.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-140">Specify which vi mode the binding applies to.</span></span>

<span data-ttu-id="4c8d4-141">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="4c8d4-141">Valid values are:</span></span>

- <span data-ttu-id="4c8d4-142">Inserir</span><span class="sxs-lookup"><span data-stu-id="4c8d4-142">Insert</span></span>
- <span data-ttu-id="4c8d4-143">Comando</span><span class="sxs-lookup"><span data-stu-id="4c8d4-143">Command</span></span>

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4c8d4-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4c8d4-144">CommonParameters</span></span>

<span data-ttu-id="4c8d4-145">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4c8d4-146">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4c8d4-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4c8d4-147">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4c8d4-147">INPUTS</span></span>

### <span data-ttu-id="4c8d4-148">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4c8d4-148">None</span></span>

<span data-ttu-id="4c8d4-149">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-149">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="4c8d4-150">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4c8d4-150">OUTPUTS</span></span>

### <span data-ttu-id="4c8d4-151">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4c8d4-151">None</span></span>

<span data-ttu-id="4c8d4-152">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="4c8d4-152">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4c8d4-153">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4c8d4-153">NOTES</span></span>

## <span data-ttu-id="4c8d4-154">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4c8d4-154">RELATED LINKS</span></span>

[<span data-ttu-id="4c8d4-155">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="4c8d4-155">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="4c8d4-156">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="4c8d4-156">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="4c8d4-157">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="4c8d4-157">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="4c8d4-158">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="4c8d4-158">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
