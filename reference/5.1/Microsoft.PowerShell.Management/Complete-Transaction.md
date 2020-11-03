---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/complete-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Complete-Transaction
ms.openlocfilehash: 20fbdd86aab07dda065492eff2da4f358fb2ffca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194205"
---
# <span data-ttu-id="7e239-103">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="7e239-103">Complete-Transaction</span></span>

## <span data-ttu-id="7e239-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7e239-104">SYNOPSIS</span></span>
<span data-ttu-id="7e239-105">Confirma a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="7e239-105">Commits the active transaction.</span></span>

## <span data-ttu-id="7e239-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7e239-106">SYNTAX</span></span>

```
Complete-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7e239-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7e239-107">DESCRIPTION</span></span>
<span data-ttu-id="7e239-108">O cmdlet **Complete-Transaction** confirma uma transação ativa.</span><span class="sxs-lookup"><span data-stu-id="7e239-108">The **Complete-Transaction** cmdlet commits an active transaction.</span></span>
<span data-ttu-id="7e239-109">Quando você confirma uma transação, os comandos nessa transação são finalizados e os dados afetados pelos comandos são alterados.</span><span class="sxs-lookup"><span data-stu-id="7e239-109">When you commit a transaction, the commands in the transaction are finalized and the data affected by the commands is changed.</span></span>

<span data-ttu-id="7e239-110">Se a transação incluir vários assinantes, para confirmar a transação, você deverá inserir um comando de **transação de conclusão** para cada comando de Start-Transaction.</span><span class="sxs-lookup"><span data-stu-id="7e239-110">If the transaction includes multiple subscribers, to commit the transaction, you must enter one **Complete-Transaction** command for every Start-Transaction command.</span></span>

<span data-ttu-id="7e239-111">O cmdlet **Complete-Transaction** é um de um conjunto de cmdlets que dão suporte ao recurso de transações no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7e239-111">The **Complete-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="7e239-112">Para obter mais informações, consulte about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="7e239-112">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="7e239-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7e239-113">EXAMPLES</span></span>

### <span data-ttu-id="7e239-114">Exemplo 1: confirmar uma transação</span><span class="sxs-lookup"><span data-stu-id="7e239-114">Example 1: Commit a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}
```

<span data-ttu-id="7e239-115">Este exemplo mostra o que acontece quando você usa o cmdlet **Complete-Transaction** para confirmar uma transação.</span><span class="sxs-lookup"><span data-stu-id="7e239-115">This example shows what happens when you use the **Complete-Transaction** cmdlet to commit a transaction.</span></span>

<span data-ttu-id="7e239-116">O comando **Start-Transaction** inicia a transação.</span><span class="sxs-lookup"><span data-stu-id="7e239-116">The **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="7e239-117">O comando New-Item usa o parâmetro *UseTransaction* para incluir o comando na transação.</span><span class="sxs-lookup"><span data-stu-id="7e239-117">The New-Item command uses the *UseTransaction* parameter to include the command in the transaction.</span></span>

<span data-ttu-id="7e239-118">O primeiro comando dir (Get-ChildItem) mostra que o novo item ainda não foi adicionado ao registro.</span><span class="sxs-lookup"><span data-stu-id="7e239-118">The first dir (Get-ChildItem) command shows that the new item has not yet been added to the registry.</span></span>

<span data-ttu-id="7e239-119">O comando **Complete-Transaction** confirma a transação, o que torna a alteração do registro efetiva.</span><span class="sxs-lookup"><span data-stu-id="7e239-119">The **Complete-Transaction** command commits the transaction, which makes the registry change effective.</span></span>
<span data-ttu-id="7e239-120">Como resultado, o segundo comando dir mostra que o registro foi alterado.</span><span class="sxs-lookup"><span data-stu-id="7e239-120">As a result, the second dir command shows that the registry is changed.</span></span>

### <span data-ttu-id="7e239-121">Exemplo 2: confirmar uma transação que tem mais de um assinante</span><span class="sxs-lookup"><span data-stu-id="7e239-121">Example 2: Commit a transaction that has more than one subscriber</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
0   0 MyCompany                      {}

PS HKCU:\software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                2                Active

PS HKCU:\software> New-ItemProperty -Path MyCompany -Name MyKey -Value -UseTransaction

MyKey
-----
123

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                1                Active

PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   1 MyCompany                      {MyKey}
```

<span data-ttu-id="7e239-122">Este exemplo mostra como usar a **transação completa** para confirmar uma transação que tem mais de um assinante.</span><span class="sxs-lookup"><span data-stu-id="7e239-122">This example shows how to use **Complete-Transaction** to commit a transaction that has more than one subscriber.</span></span>

<span data-ttu-id="7e239-123">Para confirmar uma transação de vários assinantes, você deve inserir um comando **Complete-Transaction** para cada comando **Start-Transaction** .</span><span class="sxs-lookup"><span data-stu-id="7e239-123">To commit a multi-subscriber transaction, you must enter one **Complete-Transaction** command for every **Start-Transaction** command.</span></span>
<span data-ttu-id="7e239-124">Os dados são alterados somente quando o comando **Complete-Transaction** final é enviado.</span><span class="sxs-lookup"><span data-stu-id="7e239-124">The data is changed only when the final **Complete-Transaction** command is submitted.</span></span>

<span data-ttu-id="7e239-125">Para fins de demonstração, este exemplo mostra uma série de comandos inseridos na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="7e239-125">For demonstration purposes, this example shows a series of commands entered at the command line.</span></span>
<span data-ttu-id="7e239-126">Na prática, transações provavelmente serão executadas em scripts, com a transação secundária sendo executada por uma função ou script auxiliar que é chamado pelo script principal.</span><span class="sxs-lookup"><span data-stu-id="7e239-126">In practice, transactions are likely to be run in scripts, with the secondary transaction being run by a function or helper script that is called by the main script.</span></span>

<span data-ttu-id="7e239-127">Neste exemplo, um comando **Start-Transaction** inicia a transação.</span><span class="sxs-lookup"><span data-stu-id="7e239-127">In this example, a **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="7e239-128">Um comando **New-Item** com o parâmetro *UseTransaction* adiciona a chave MyCompany à chave de software.</span><span class="sxs-lookup"><span data-stu-id="7e239-128">A **New-Item** command with the *UseTransaction* parameter adds the MyCompany key to the Software key.</span></span>
<span data-ttu-id="7e239-129">Embora o cmdlet **New-Item** retorne um objeto de chave, os dados no registro ainda não foram alterados.</span><span class="sxs-lookup"><span data-stu-id="7e239-129">Although the **New-Item** cmdlet returns a key object, the data in the registry is not yet changed.</span></span>

<span data-ttu-id="7e239-130">Um segundo comando **Start-Transaction** adiciona um segundo assinante à transação existente.</span><span class="sxs-lookup"><span data-stu-id="7e239-130">A second **Start-Transaction** command adds a second subscriber to the existing transaction.</span></span>
<span data-ttu-id="7e239-131">O cmdlet **Get-Transaction** confirma que a contagem de assinantes é 2.</span><span class="sxs-lookup"><span data-stu-id="7e239-131">The **Get-Transaction** cmdlet confirms that the subscriber count is 2.</span></span>
<span data-ttu-id="7e239-132">Um comando New-ItemProperty com o parâmetro *UseTransaction* adiciona uma entrada de registro à nova chave MyCompany.</span><span class="sxs-lookup"><span data-stu-id="7e239-132">A New-ItemProperty command with the *UseTransaction* parameter adds a registry entry to the new MyCompany key.</span></span>
<span data-ttu-id="7e239-133">Novamente, o comando retorna um valor, mas o registro não é alterado.</span><span class="sxs-lookup"><span data-stu-id="7e239-133">Again, the command returns a value, but the registry is not changed.</span></span>

<span data-ttu-id="7e239-134">O primeiro comando **Complete-Transaction** reduz a contagem de assinantes em 1.</span><span class="sxs-lookup"><span data-stu-id="7e239-134">The first **Complete-Transaction** command reduces the subscriber count by 1.</span></span>
<span data-ttu-id="7e239-135">Isso é confirmado por um comando **Get-Transaction** .</span><span class="sxs-lookup"><span data-stu-id="7e239-135">This is confirmed by a **Get-Transaction** command.</span></span>
<span data-ttu-id="7e239-136">No entanto, nenhum dado é alterado, conforme evidenciado por um comando dir m \* ( **Get-ChildItem** ).</span><span class="sxs-lookup"><span data-stu-id="7e239-136">However, no data is changed, as evidenced by a dir m\* ( **Get-ChildItem** ) command.</span></span>

<span data-ttu-id="7e239-137">O segundo comando **Complete-Transaction** confirma a transação inteira e altera os dados no registro.</span><span class="sxs-lookup"><span data-stu-id="7e239-137">The second **Complete-Transaction** command commits the entire transaction and changes the data in the registry.</span></span>
<span data-ttu-id="7e239-138">Isso é confirmado por um segundo comando dir m \*, que mostra as alterações.</span><span class="sxs-lookup"><span data-stu-id="7e239-138">This is confirmed by a second dir m\* command, which shows the changes.</span></span>

### <span data-ttu-id="7e239-139">Exemplo 3: executar uma transação que não altera nenhum dado</span><span class="sxs-lookup"><span data-stu-id="7e239-139">Example 3: Perform a transaction that does not change any data</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> dir m* -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}

PS HKCU:\software> Complete-Transaction
```

<span data-ttu-id="7e239-140">Este exemplo mostra o valor do uso de get- \* Commands e outros comandos que não alteram dados, em uma transação.</span><span class="sxs-lookup"><span data-stu-id="7e239-140">This example shows the value of using Get-\* commands, and other commands that do not change data, in a transaction.</span></span>
<span data-ttu-id="7e239-141">Quando um get- \* Command é usado em uma transação, ele obtém os objetos que fazem parte da transação.</span><span class="sxs-lookup"><span data-stu-id="7e239-141">When a Get-\* command is used in a transaction, it gets the objects that are part of the transaction.</span></span>
<span data-ttu-id="7e239-142">Isso permite a você visualizar as alterações na transação antes de confirmá-las.</span><span class="sxs-lookup"><span data-stu-id="7e239-142">This allows you to preview the changes in the transaction before the changes are committed.</span></span>

<span data-ttu-id="7e239-143">Neste exemplo, uma transação é iniciada.</span><span class="sxs-lookup"><span data-stu-id="7e239-143">In this example, a transaction is started.</span></span>
<span data-ttu-id="7e239-144">Um comando New-Item com o parâmetro *UseTransaction* adiciona uma nova chave ao registro como parte da transação.</span><span class="sxs-lookup"><span data-stu-id="7e239-144">A New-Item command with the *UseTransaction* parameter adds a new key to the registry as part of the transaction.</span></span>

<span data-ttu-id="7e239-145">Como a nova chave do registro não é adicionada ao registro até que o comando **Complete-Transaction** seja executado, um comando dir ( **Get-ChildItem** ) simples mostra o registro sem a nova chave.</span><span class="sxs-lookup"><span data-stu-id="7e239-145">Because the new registry key is not added to the registry until the **Complete-Transaction** command is run, a simple dir ( **Get-ChildItem** ) command shows the registry without the new key.</span></span>

<span data-ttu-id="7e239-146">No entanto, quando você adiciona o parâmetro *UseTransaction* ao comando dir, o comando se torna parte da transação e obtém os itens na transação, mesmo que eles ainda não tenham sido adicionados aos dados.</span><span class="sxs-lookup"><span data-stu-id="7e239-146">However, when you add the *UseTransaction* parameter to the dir command, the command becomes part of the transaction, and it gets the items in the transaction even if they are not yet added to the data.</span></span>

## <span data-ttu-id="7e239-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7e239-147">PARAMETERS</span></span>

### <span data-ttu-id="7e239-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7e239-148">-Confirm</span></span>
<span data-ttu-id="7e239-149">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7e239-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7e239-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7e239-150">-WhatIf</span></span>
<span data-ttu-id="7e239-151">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="7e239-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7e239-152">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="7e239-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7e239-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7e239-153">CommonParameters</span></span>
<span data-ttu-id="7e239-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7e239-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7e239-155">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7e239-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7e239-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7e239-156">INPUTS</span></span>

### <span data-ttu-id="7e239-157">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7e239-157">None</span></span>
<span data-ttu-id="7e239-158">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7e239-158">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="7e239-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7e239-159">OUTPUTS</span></span>

### <span data-ttu-id="7e239-160">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7e239-160">None</span></span>
<span data-ttu-id="7e239-161">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="7e239-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7e239-162">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7e239-162">NOTES</span></span>

* <span data-ttu-id="7e239-163">Você não pode reverter uma transação que foi confirmada, nem confirmar uma transação que foi revertida.</span><span class="sxs-lookup"><span data-stu-id="7e239-163">You cannot roll back a transaction that has been committed, or commit a transaction that has been rolled back.</span></span>

  <span data-ttu-id="7e239-164">Você não pode reverter uma transação que não seja a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="7e239-164">You cannot roll back any transaction other than the active transaction.</span></span>
<span data-ttu-id="7e239-165">Para reverter uma transação diferente, primeiro você deve confirmar ou reverter a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="7e239-165">To roll back a different transaction, you must first commit or roll back the active transaction.</span></span>

  <span data-ttu-id="7e239-166">Por padrão, se qualquer parte de uma transação não pode ser confirmada, como por exemplo quando um comando na transação resulta em um erro, a transação inteira é revertida.</span><span class="sxs-lookup"><span data-stu-id="7e239-166">By default, if any part of a transaction cannot be committed, such as when a command in the transaction results in an error, the entire transaction is rolled back.</span></span>

*

## <span data-ttu-id="7e239-167">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7e239-167">RELATED LINKS</span></span>

[<span data-ttu-id="7e239-168">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="7e239-168">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="7e239-169">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="7e239-169">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="7e239-170">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="7e239-170">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="7e239-171">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="7e239-171">Use-Transaction</span></span>](Use-Transaction.md)

[<span data-ttu-id="7e239-172">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="7e239-172">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="7e239-173">New-Item</span><span class="sxs-lookup"><span data-stu-id="7e239-173">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="7e239-174">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7e239-174">New-ItemProperty</span></span>](New-ItemProperty.md)
