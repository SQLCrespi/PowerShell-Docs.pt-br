---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/use-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Use-Transaction
ms.openlocfilehash: db8423aef6dc4b25c4ddd13f9b29b774463c6a6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193905"
---
# <span data-ttu-id="2bf10-103">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="2bf10-103">Use-Transaction</span></span>

## <span data-ttu-id="2bf10-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2bf10-104">SYNOPSIS</span></span>
<span data-ttu-id="2bf10-105">Adiciona o bloco de script à transação ativa.</span><span class="sxs-lookup"><span data-stu-id="2bf10-105">Adds the script block to the active transaction.</span></span>

## <span data-ttu-id="2bf10-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2bf10-106">SYNTAX</span></span>

```
Use-Transaction [-TransactedScript] <ScriptBlock> [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="2bf10-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2bf10-107">DESCRIPTION</span></span>
<span data-ttu-id="2bf10-108">O cmdlet **Use-Transaction** adiciona um bloco de script a uma transação ativa.</span><span class="sxs-lookup"><span data-stu-id="2bf10-108">The **Use-Transaction** cmdlet adds a script block to an active transaction.</span></span>
<span data-ttu-id="2bf10-109">Isso permite que você faça scripts transacionados usando objetos da estrutura de Microsoft .NET habilitados para transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-109">This enables you to do transacted scripting by using transaction-enabled Microsoft .NET Framework objects.</span></span>
<span data-ttu-id="2bf10-110">O bloco de script pode conter somente objetos de transações habilitadas do .NET Framework., como instâncias da classe Microsoft.PowerShell.Commands.Management.TransactedString.</span><span class="sxs-lookup"><span data-stu-id="2bf10-110">The script block can contain only transaction-enabled .NET Framework objects, such as instances of the Microsoft.PowerShell.Commands.Management.TransactedString class.</span></span>

<span data-ttu-id="2bf10-111">O parâmetro *UseTransaction* , que é opcional para a maioria dos cmdlets, é necessário quando você usa esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2bf10-111">The *UseTransaction* parameter, which is optional for most cmdlets, is required when you use this cmdlet.</span></span>

<span data-ttu-id="2bf10-112">**Use-Transaction** é um de um conjunto de cmdlets que dão suporte ao recurso de transações no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2bf10-112">**Use-Transaction** is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="2bf10-113">Para obter mais informações, consulte about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="2bf10-113">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="2bf10-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2bf10-114">EXAMPLES</span></span>

### <span data-ttu-id="2bf10-115">Exemplo 1: script usando um objeto habilitado para transação</span><span class="sxs-lookup"><span data-stu-id="2bf10-115">Example 1: Script by using a transaction-enabled object</span></span>

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> $transactedString.ToString()
Hello
PS C:\> Use-Transaction -TransactedScript { $transactedString.ToString() } -UseTransaction
Hello, World
PS C:\> Complete-Transaction
PS C:\> $transactedString.ToString()
Hello, World
```

<span data-ttu-id="2bf10-116">Este exemplo mostra como usar o **Use-Transaction** para script em relação a um objeto de .NET Framework habilitado para transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-116">This example shows how to use **Use-Transaction** to script against a transaction-enabled .NET Framework object.</span></span>
<span data-ttu-id="2bf10-117">Nesse caso, o objeto é um objeto **transacionated** .</span><span class="sxs-lookup"><span data-stu-id="2bf10-117">In this case, the object is a **TransactedString** object.</span></span>

<span data-ttu-id="2bf10-118">O primeiro comando utiliza o cmdlet Start-Transaction para iniciar uma transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-118">The first command uses the Start-Transaction cmdlet to start a transaction.</span></span>

<span data-ttu-id="2bf10-119">O segundo comando usa o comando New-Object para criar um objeto **transacionated** .</span><span class="sxs-lookup"><span data-stu-id="2bf10-119">The second command uses the New-Object command to create a **TransactedString** object.</span></span>
<span data-ttu-id="2bf10-120">Ele armazena o objeto na variável $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="2bf10-120">It stores the object in the $TransactedString variable.</span></span>

<span data-ttu-id="2bf10-121">O terceiro e o quarto comandos usam o método **Append** do objeto **transacionastring** para adicionar texto ao valor de $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="2bf10-121">The third and fourth commands both use the **Append** method of the **TransactedString** object to add text to the value of $TransactedString.</span></span>
<span data-ttu-id="2bf10-122">Um comando faz parte da transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-122">One command is part of the transaction.</span></span>
<span data-ttu-id="2bf10-123">O outro comando não é.</span><span class="sxs-lookup"><span data-stu-id="2bf10-123">The other command is not.</span></span>

<span data-ttu-id="2bf10-124">O terceiro comando usa o método **Append** da cadeia de caracteres transacionada para adicionar Hello ao valor de $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="2bf10-124">The third command uses the **Append** method of the transacted string to add Hello to the value of $TransactedString.</span></span>
<span data-ttu-id="2bf10-125">Como o comando não é parte da transação, a alteração será aplicada imediatamente.</span><span class="sxs-lookup"><span data-stu-id="2bf10-125">Because the command is not part of the transaction, the change is applied immediately.</span></span>

<span data-ttu-id="2bf10-126">O quarto comando usa **Use-Transaction** para adicionar texto à cadeia de caracteres na transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-126">The fourth command uses **Use-Transaction** to add text to the string in the transaction.</span></span>
<span data-ttu-id="2bf10-127">O comando usa o método **Append** para adicionar ", World" ao valor de $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="2bf10-127">The command uses the **Append** method to add ", World" to the value of $TransactedString.</span></span>
<span data-ttu-id="2bf10-128">O comando é colocado entre chaves ( {} ) para torná-lo um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="2bf10-128">The command is enclosed in braces ( {} ) to make it a script block.</span></span>
<span data-ttu-id="2bf10-129">O parâmetro *UseTransaction* é necessário neste comando.</span><span class="sxs-lookup"><span data-stu-id="2bf10-129">The *UseTransaction* parameter is required in this command.</span></span>

<span data-ttu-id="2bf10-130">O quinto e o sexto comandos usam o método **ToString** do objeto **transacionastring** para exibir o valor de **transacionated** como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2bf10-130">The fifth and sixth commands use the **ToString** method of the **TransactedString** object to display the value of the **TransactedString** as a string.</span></span>
<span data-ttu-id="2bf10-131">Novamente, um comando faz parte da transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-131">Again, one command is part of the transaction.</span></span>
<span data-ttu-id="2bf10-132">A outra transação não é.</span><span class="sxs-lookup"><span data-stu-id="2bf10-132">The other transaction is not.</span></span>

<span data-ttu-id="2bf10-133">O quinto comando usa o método **ToString** para exibir o valor atual da variável $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="2bf10-133">The fifth command uses the **ToString** method to display the current value of the $TransactedString variable.</span></span>
<span data-ttu-id="2bf10-134">Por não fazer parte da transação, ele exibe apenas o estado atual da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2bf10-134">Because it is not part of the transaction, it displays only the current state of the string.</span></span>

<span data-ttu-id="2bf10-135">O sexto comando usa **Use-Transaction** para executar o mesmo comando na transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-135">The sixth command uses **Use-Transaction** to run the same command in the transaction.</span></span>
<span data-ttu-id="2bf10-136">Como o comando faz parte da transação, ele exibe o valor atual da cadeia de caracteres na transação, assim como uma visualização das alterações de transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-136">Because the command is part of the transaction, it displays the current value of the string in the transaction, much like a preview of the transaction changes.</span></span>

<span data-ttu-id="2bf10-137">O sétimo comando utiliza o cmdlet Complete-Transaction para confirmar a transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-137">The seventh command uses the Complete-Transaction cmdlet to commit the transaction.</span></span>

<span data-ttu-id="2bf10-138">O comando final usa o método **ToString** para exibir o valor resultante da variável como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2bf10-138">The final command uses the **ToString** method to display the resulting value of the variable as a string.</span></span>

### <span data-ttu-id="2bf10-139">Exemplo 2: reverter uma transação</span><span class="sxs-lookup"><span data-stu-id="2bf10-139">Example 2: Roll back a transaction</span></span>

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> Undo-Transaction
PS C:\> $transactedString.ToString()
Hello
```

<span data-ttu-id="2bf10-140">Este exemplo mostra o efeito de reverter uma transação que inclui comandos **de transação de uso** .</span><span class="sxs-lookup"><span data-stu-id="2bf10-140">This example shows the effect of rolling back a transaction that includes **Use-Transaction** commands.</span></span>
<span data-ttu-id="2bf10-141">Como todos os comandos em uma transação, quando a transação for revertida, as alterações realizadas são descartadas e os dados não são alterados.</span><span class="sxs-lookup"><span data-stu-id="2bf10-141">Like all commands in a transaction, when the transaction is rolled back, the transacted changes are discarded and the data is unchanged.</span></span>

<span data-ttu-id="2bf10-142">O primeiro comando usa **Start-Transaction** para iniciar uma transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-142">The first command uses **Start-Transaction** to start a transaction.</span></span>

<span data-ttu-id="2bf10-143">O segundo comando usa **New-Object** para criar um objeto **transacionated** .</span><span class="sxs-lookup"><span data-stu-id="2bf10-143">The second command uses **New-Object** to create a **TransactedString** object.</span></span>
<span data-ttu-id="2bf10-144">Ele armazena o objeto na variável $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="2bf10-144">It stores the object in the $TransactedString variable.</span></span>

<span data-ttu-id="2bf10-145">O terceiro comando, que não faz parte da transação, usa o método **Append** para adicionar "Hello" ao valor de $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="2bf10-145">The third command, which is not part of the transaction, uses the **Append** method to add "Hello" to the value of $TransactedString.</span></span>

<span data-ttu-id="2bf10-146">O quarto comando usa **Use-Transaction** para executar outro comando que usa o método **Append** na transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-146">The fourth command uses **Use-Transaction** to run another command that uses the **Append** method in the transaction.</span></span>
<span data-ttu-id="2bf10-147">O comando usa o método **Append** para adicionar ", World" ao valor de $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="2bf10-147">The command uses the **Append** method to add ", World" to the value of $TransactedString.</span></span>

<span data-ttu-id="2bf10-148">O quinto comando utiliza o cmdlet Undo-Transaction para reverter a transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-148">The fifth command uses the Undo-Transaction cmdlet to roll back the transaction.</span></span>
<span data-ttu-id="2bf10-149">Como resultado, todos os comandos executados na transação são revertidos.</span><span class="sxs-lookup"><span data-stu-id="2bf10-149">As a result, all commands performed in the transaction are reversed.</span></span>

<span data-ttu-id="2bf10-150">O comando final usa o método **ToString** para exibir o valor resultante de $TransactedString como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2bf10-150">The final command uses the **ToString** method to display the resulting value of $TransactedString as a string.</span></span>
<span data-ttu-id="2bf10-151">Os resultados mostram que apenas as alterações feitas fora da transação foram aplicadas ao objeto.</span><span class="sxs-lookup"><span data-stu-id="2bf10-151">The results show that only the changes that were made outside the transaction were applied to the object.</span></span>

## <span data-ttu-id="2bf10-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2bf10-152">PARAMETERS</span></span>

### <span data-ttu-id="2bf10-153">-TransactedScript</span><span class="sxs-lookup"><span data-stu-id="2bf10-153">-TransactedScript</span></span>
<span data-ttu-id="2bf10-154">Especifica o bloco de script que é executado na transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-154">Specifies the script block that is run in the transaction.</span></span>
<span data-ttu-id="2bf10-155">Insira qualquer bloco de script válido entre chaves ({}).</span><span class="sxs-lookup"><span data-stu-id="2bf10-155">Enter any valid script block enclosed in braces ( { } ).</span></span>
<span data-ttu-id="2bf10-156">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="2bf10-156">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2bf10-157">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="2bf10-157">-UseTransaction</span></span>
<span data-ttu-id="2bf10-158">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="2bf10-158">Includes the command in the active transaction.</span></span>
<span data-ttu-id="2bf10-159">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="2bf10-159">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="2bf10-160">Para obter mais informações, consulte about_transactions.</span><span class="sxs-lookup"><span data-stu-id="2bf10-160">For more information, see about_transactions.</span></span>

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

### <span data-ttu-id="2bf10-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2bf10-161">CommonParameters</span></span>
<span data-ttu-id="2bf10-162">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2bf10-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2bf10-163">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2bf10-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2bf10-164">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2bf10-164">INPUTS</span></span>

### <span data-ttu-id="2bf10-165">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2bf10-165">None</span></span>
<span data-ttu-id="2bf10-166">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2bf10-166">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2bf10-167">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2bf10-167">OUTPUTS</span></span>

### <span data-ttu-id="2bf10-168">PSObject</span><span class="sxs-lookup"><span data-stu-id="2bf10-168">PSObject</span></span>
<span data-ttu-id="2bf10-169">Esse cmdlet retorna o resultado da transação.</span><span class="sxs-lookup"><span data-stu-id="2bf10-169">This cmdlet returns the result of the transaction.</span></span>

## <span data-ttu-id="2bf10-170">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2bf10-170">NOTES</span></span>

* <span data-ttu-id="2bf10-171">O parâmetro *UseTransaction* inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="2bf10-171">The *UseTransaction* parameter includes the command in the active transaction.</span></span> <span data-ttu-id="2bf10-172">Como o cmdlet **Use-Transaction** é sempre usado em transações, esse parâmetro é necessário para fazer com que qualquer comando **Use-Transaction** seja efetivo.</span><span class="sxs-lookup"><span data-stu-id="2bf10-172">Because the **Use-Transaction** cmdlet is always used in transactions, this parameter is required to make any **Use-Transaction** command effective.</span></span>

*

## <span data-ttu-id="2bf10-173">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2bf10-173">RELATED LINKS</span></span>

[<span data-ttu-id="2bf10-174">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="2bf10-174">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="2bf10-175">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="2bf10-175">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="2bf10-176">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="2bf10-176">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="2bf10-177">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="2bf10-177">Undo-Transaction</span></span>](Undo-Transaction.md)
