---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/undo-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Undo-Transaction
ms.openlocfilehash: 1acb06ea7b05a2127b04a22c4c51b92cd68056f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193901"
---
# <span data-ttu-id="38363-103">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="38363-103">Undo-Transaction</span></span>

## <span data-ttu-id="38363-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="38363-104">SYNOPSIS</span></span>
<span data-ttu-id="38363-105">Reverte a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="38363-105">Rolls back the active transaction.</span></span>

## <span data-ttu-id="38363-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="38363-106">SYNTAX</span></span>

```
Undo-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="38363-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="38363-107">DESCRIPTION</span></span>
<span data-ttu-id="38363-108">O cmdlet **Undo-Transaction** reverte a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="38363-108">The **Undo-Transaction** cmdlet rolls back the active transaction.</span></span>
<span data-ttu-id="38363-109">Quando você reverte uma transação, as alterações feitas pelos comandos na transação são descartadas e os dados são restaurados para seu formato original.</span><span class="sxs-lookup"><span data-stu-id="38363-109">When you roll back a transaction, the changes that were made by the commands in the transaction are discarded and the data is restored to its original form.</span></span>

<span data-ttu-id="38363-110">Se a transação incluir vários assinantes, um comando **Undo-Transaction** reverterá toda a transação para todos os assinantes.</span><span class="sxs-lookup"><span data-stu-id="38363-110">If the transaction includes multiple subscribers, an **Undo-Transaction** command rolls back the whole transaction for all subscribers.</span></span>

<span data-ttu-id="38363-111">Por padrão, as transações serão revertidas automaticamente se qualquer comando na transação gerar um erro.</span><span class="sxs-lookup"><span data-stu-id="38363-111">By default, transactions are rolled back automatically if any command in the transaction generates an error.</span></span>
<span data-ttu-id="38363-112">No entanto, as transações podem ser iniciadas usando uma preferência de reversão diferente e você pode usar esse cmdlet para reverter a transação ativa a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="38363-112">However, transactions can be started by using a different rollback preference and you can use this cmdlet to roll back the active transaction at any time.</span></span>

<span data-ttu-id="38363-113">O cmdlet **Undo-Transaction** é um de um conjunto de cmdlets que dão suporte ao recurso de transações no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38363-113">The **Undo-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="38363-114">Para obter mais informações, consulte about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="38363-114">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="38363-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="38363-115">EXAMPLES</span></span>

### <span data-ttu-id="38363-116">Exemplo 1: reverter a transação atual</span><span class="sxs-lookup"><span data-stu-id="38363-116">Example 1: Roll back the current transaction</span></span>

```
PS C:\> Undo-Transaction
```

<span data-ttu-id="38363-117">Esse comando reverte a transação atual, ativa.</span><span class="sxs-lookup"><span data-stu-id="38363-117">This command rolls back the current, active, transaction.</span></span>

### <span data-ttu-id="38363-118">Exemplo 2: Iniciar e reverter uma transação</span><span class="sxs-lookup"><span data-stu-id="38363-118">Example 2: Start and roll back a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Undo-Transaction
```

<span data-ttu-id="38363-119">Este exemplo inicia uma transação e a reverte novamente.</span><span class="sxs-lookup"><span data-stu-id="38363-119">This example starts a transaction and then rolls it back.</span></span>
<span data-ttu-id="38363-120">Como resultado, nenhuma alteração é feita no registro.</span><span class="sxs-lookup"><span data-stu-id="38363-120">As a result, no changes are made to the registry.</span></span>

### <span data-ttu-id="38363-121">Exemplo 3: reverter uma transação para todos os assinantes</span><span class="sxs-lookup"><span data-stu-id="38363-121">Example 3: Roll back a transaction for all subscribers</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                1                 Active

PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                2                 Active

PS HKCU:\Software> Undo-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                0                 RolledBack
```

<span data-ttu-id="38363-122">Este exemplo demonstra que quando qualquer assinante reverte uma transação, toda a transação é revertida para todos os assinantes.</span><span class="sxs-lookup"><span data-stu-id="38363-122">This example demonstrates that when any subscriber rolls back a transaction, the whole transaction is rolled back for all subscribers.</span></span>

<span data-ttu-id="38363-123">O primeiro comando altera o local para a chave de registro HKCU:\Software.</span><span class="sxs-lookup"><span data-stu-id="38363-123">The first command changes the location to the HKCU:\Software registry key.</span></span>

<span data-ttu-id="38363-124">O segundo comando inicia uma transação.</span><span class="sxs-lookup"><span data-stu-id="38363-124">The second command starts a transaction.</span></span>

<span data-ttu-id="38363-125">O terceiro comando usa o cmdlet New-Item para criar uma nova chave do registro.</span><span class="sxs-lookup"><span data-stu-id="38363-125">The third command uses the New-Item cmdlet to create a new registry key.</span></span>
<span data-ttu-id="38363-126">O comando usa o parâmetro *UseTransaction* para incluir a alteração na transação.</span><span class="sxs-lookup"><span data-stu-id="38363-126">The command uses the *UseTransaction* parameter to include the change in the transaction.</span></span>

<span data-ttu-id="38363-127">O quarto comando usa o cmdlet Get-Transaction para obter a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="38363-127">The fourth command uses the Get-Transaction cmdlet to get the active transaction.</span></span>
<span data-ttu-id="38363-128">Observe que o status está ativo e que a contagem de assinante é 1.</span><span class="sxs-lookup"><span data-stu-id="38363-128">Notice that the status is Active and the subscriber count is 1.</span></span>

<span data-ttu-id="38363-129">O quinto comando usa o comando Start-Transaction novamente.</span><span class="sxs-lookup"><span data-stu-id="38363-129">The fifth command uses the Start-Transaction command again.</span></span>
<span data-ttu-id="38363-130">Normalmente, iniciar uma transação enquanto outra transação está em andamento ocorre quando um script usado pela transação principal inclui sua própria transação completa.</span><span class="sxs-lookup"><span data-stu-id="38363-130">Typically, starting a transaction while another transaction is in progress occurs when a script that is used by the main transaction includes its own complete transaction.</span></span>
<span data-ttu-id="38363-131">Este exemplo é executado interativamente para que você possa examiná-lo em estágios.</span><span class="sxs-lookup"><span data-stu-id="38363-131">This example is performed interactively so that you can examine it in stages.</span></span>
<span data-ttu-id="38363-132">Quando você executa um comando **Start-Transaction** enquanto outra transação está em andamento, os comandos se unem à transação existente como um novo assinante e a contagem de assinantes é incrementada.</span><span class="sxs-lookup"><span data-stu-id="38363-132">When you run a **Start-Transaction** command while another transaction is in progress, the commands join the existing transaction as a new subscriber and the subscriber count is incremented.</span></span>

<span data-ttu-id="38363-133">O sexto comando usa o cmdlet **Get-Transaction** para obter a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="38363-133">The sixth command uses the **Get-Transaction** cmdlet to get the active transaction.</span></span>
<span data-ttu-id="38363-134">Observe que a contagem de assinante agora é 2.</span><span class="sxs-lookup"><span data-stu-id="38363-134">Notice that the subscriber count is now 2.</span></span>

<span data-ttu-id="38363-135">O sétimo comando usa **desfazer-transação** para reverter a transação.</span><span class="sxs-lookup"><span data-stu-id="38363-135">The seventh command uses **Undo-Transaction** to roll back the transaction.</span></span>
<span data-ttu-id="38363-136">Este cmdlet não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="38363-136">This command does not return any objects.</span></span>

<span data-ttu-id="38363-137">O comando final é um comando **Get-Transaction** que obtém o ativo, ou nesse caso, a transação ativa mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="38363-137">The final command is a **Get-Transaction** command that gets the active, or in this case, the most recently active, transaction.</span></span>
<span data-ttu-id="38363-138">Os resultados mostram que a transação é revertida e a contagem de assinante é 0, mostrando que a transação foi revertida para todos os assinantes.</span><span class="sxs-lookup"><span data-stu-id="38363-138">The results show that the transaction is rolled back, and that the subscriber count is 0, showing that the transaction was rolled back for all subscribers.</span></span>

## <span data-ttu-id="38363-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="38363-139">PARAMETERS</span></span>

### <span data-ttu-id="38363-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="38363-140">-Confirm</span></span>
<span data-ttu-id="38363-141">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38363-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="38363-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="38363-142">-WhatIf</span></span>
<span data-ttu-id="38363-143">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="38363-143">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="38363-144">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="38363-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="38363-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="38363-145">CommonParameters</span></span>
<span data-ttu-id="38363-146">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="38363-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="38363-147">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="38363-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="38363-148">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="38363-148">INPUTS</span></span>

### <span data-ttu-id="38363-149">Nenhum</span><span class="sxs-lookup"><span data-stu-id="38363-149">None</span></span>
<span data-ttu-id="38363-150">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38363-150">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="38363-151">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="38363-151">OUTPUTS</span></span>

### <span data-ttu-id="38363-152">Nenhum</span><span class="sxs-lookup"><span data-stu-id="38363-152">None</span></span>
<span data-ttu-id="38363-153">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="38363-153">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="38363-154">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="38363-154">NOTES</span></span>

* <span data-ttu-id="38363-155">Você não pode reverter uma transação que foi confirmada.</span><span class="sxs-lookup"><span data-stu-id="38363-155">You cannot roll back a transaction that has been committed.</span></span>

  <span data-ttu-id="38363-156">Você não pode reverter uma transação que não seja a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="38363-156">You cannot roll back any transaction other than the active transaction.</span></span>
<span data-ttu-id="38363-157">Para reverter uma transação diferente e independente, primeiro você deve confirmar ou reverter a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="38363-157">To roll back a different, independent transaction, you must first commit or roll back the active transaction.</span></span>

  <span data-ttu-id="38363-158">Reverter a transação termina a transação.</span><span class="sxs-lookup"><span data-stu-id="38363-158">Rolling back the transaction ends the transaction.</span></span>
<span data-ttu-id="38363-159">Para usar uma transação novamente, você deve iniciar uma nova transação.</span><span class="sxs-lookup"><span data-stu-id="38363-159">To use a transaction again, you must start a new transaction.</span></span>

## <span data-ttu-id="38363-160">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="38363-160">RELATED LINKS</span></span>

[<span data-ttu-id="38363-161">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="38363-161">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="38363-162">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="38363-162">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="38363-163">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="38363-163">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="38363-164">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="38363-164">Use-Transaction</span></span>](Use-Transaction.md)
