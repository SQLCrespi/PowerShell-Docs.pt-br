---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transaction
ms.openlocfilehash: 53be131f45f15e5d2053b183040dc7b3dca4a14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193914"
---
# <span data-ttu-id="3292b-103">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="3292b-103">Start-Transaction</span></span>

## <span data-ttu-id="3292b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3292b-104">SYNOPSIS</span></span>
<span data-ttu-id="3292b-105">Inicia uma transação.</span><span class="sxs-lookup"><span data-stu-id="3292b-105">Starts a transaction.</span></span>

## <span data-ttu-id="3292b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3292b-106">SYNTAX</span></span>

```
Start-Transaction [-Timeout <Int32>] [-Independent] [-RollbackPreference <RollbackSeverity>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3292b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3292b-107">DESCRIPTION</span></span>
<span data-ttu-id="3292b-108">O cmdlet **Start-Transaction** inicia uma transação, que é uma série de comandos que são gerenciados como uma unidade.</span><span class="sxs-lookup"><span data-stu-id="3292b-108">The **Start-Transaction** cmdlet starts a transaction, which is a series of commands that are managed as a unit.</span></span>
<span data-ttu-id="3292b-109">Uma transação pode ser concluída ou confirmada.</span><span class="sxs-lookup"><span data-stu-id="3292b-109">A transaction can be completed, or committed.</span></span>
<span data-ttu-id="3292b-110">Como alternativa, ele pode ser completamente desfeito ou revertido para que todos os dados alterados pela transação sejam restaurados para seu estado original.</span><span class="sxs-lookup"><span data-stu-id="3292b-110">Alternatively, it can be completely undone, or rolled back, so that any data changed by the transaction is restored to its original state.</span></span>
<span data-ttu-id="3292b-111">Como os comandos em uma transação são gerenciados como uma unidade, todos os comandos são confirmados ou então revertidos.</span><span class="sxs-lookup"><span data-stu-id="3292b-111">Because the commands in a transaction are managed as a unit, either all commands are committed or all commands are rolled back.</span></span>

<span data-ttu-id="3292b-112">Por padrão, se qualquer comando na transação gerar um erro, as transações serão revertidas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3292b-112">By default, if any command in the transaction generates an error, transactions are rolled back automatically.</span></span>
<span data-ttu-id="3292b-113">Você pode usar o parâmetro *RollbackPreference* para alterar esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="3292b-113">You can use the *RollbackPreference* parameter to change this behavior.</span></span>

<span data-ttu-id="3292b-114">Os cmdlets usados em uma transação devem ser criados para oferecer suporte a transações.</span><span class="sxs-lookup"><span data-stu-id="3292b-114">The cmdlets used in a transaction must be designed to support transactions.</span></span>
<span data-ttu-id="3292b-115">Os cmdlets que dão suporte a transações têm um parâmetro *UseTransaction* .</span><span class="sxs-lookup"><span data-stu-id="3292b-115">Cmdlets that support transactions have a *UseTransaction* parameter.</span></span>
<span data-ttu-id="3292b-116">Para realizar transações em um provedor, este provedor deve oferecer suporte a transações.</span><span class="sxs-lookup"><span data-stu-id="3292b-116">To perform transactions in a provider, the provider must support transactions.</span></span>
<span data-ttu-id="3292b-117">O provedor de registro do Windows PowerShell no Windows Vista e versões posteriores do sistema operacional Windows dão suporte a transações.</span><span class="sxs-lookup"><span data-stu-id="3292b-117">The Windows PowerShell Registry provider in Windows Vista and later versions of the Windows operating system supports transactions.</span></span>
<span data-ttu-id="3292b-118">Você também pode usar a classe **Microsoft. PowerShell. Commands. Management.** transactionstring para incluir expressões em transações em qualquer versão do sistema Windows que ofereça suporte ao Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3292b-118">You can also use the **Microsoft.PowerShell.Commands.Management.TransactedString** class to include expressions in transactions on any version of the Windows system that supports Windows PowerShell.</span></span>
<span data-ttu-id="3292b-119">Outros provedores do Windows PowerShell também podem oferecer suporte a transações.</span><span class="sxs-lookup"><span data-stu-id="3292b-119">Other Windows PowerShell providers can also support transactions.</span></span>

<span data-ttu-id="3292b-120">Somente uma transação pode estar ativa por vez.</span><span class="sxs-lookup"><span data-stu-id="3292b-120">Only one transaction can be active at a time.</span></span>
<span data-ttu-id="3292b-121">Se você iniciar uma nova transação independente enquanto uma transação estiver em andamento, a nova transação se tornará a transação ativa e você deverá confirmar ou reverter a nova transação antes de fazer qualquer alteração na transação original.</span><span class="sxs-lookup"><span data-stu-id="3292b-121">If you start a new, independent transaction while a transaction is in progress, the new transaction becomes the active transaction, and you must commit or roll back the new transaction before you make any changes to the original transaction.</span></span>

<span data-ttu-id="3292b-122">O cmdlet **Start-Transaction** é um de um conjunto de cmdlets que dão suporte ao recurso de transações no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3292b-122">**Start-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="3292b-123">Para obter mais informações, consulte about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="3292b-123">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="3292b-124">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3292b-124">EXAMPLES</span></span>

### <span data-ttu-id="3292b-125">Exemplo 1: Iniciar e reverter uma transação</span><span class="sxs-lookup"><span data-stu-id="3292b-125">Example 1: Start and roll back a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Undo-Transaction
```

<span data-ttu-id="3292b-126">Estes comandos iniciam uma transação e em seguida a revertem.</span><span class="sxs-lookup"><span data-stu-id="3292b-126">These commands start and then roll back a transaction.</span></span>
<span data-ttu-id="3292b-127">Como a transação é revertida, nenhuma alteração é feita ao registro.</span><span class="sxs-lookup"><span data-stu-id="3292b-127">Because the transaction is rolled back, no changes are made to the registry.</span></span>

### <span data-ttu-id="3292b-128">Exemplo 2: Iniciar e concluir uma transação</span><span class="sxs-lookup"><span data-stu-id="3292b-128">Example 2: Start and complete a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
```

<span data-ttu-id="3292b-129">Estes comandos iniciam uma transação e em seguida a concluem.</span><span class="sxs-lookup"><span data-stu-id="3292b-129">These commands start and then complete a transaction.</span></span>
<span data-ttu-id="3292b-130">Nenhuma alteração é feita no registro até que o comando **Complete-Transaction** seja usado.</span><span class="sxs-lookup"><span data-stu-id="3292b-130">No changes are made to the registry until the **Complete-Transaction** command is used.</span></span>

### <span data-ttu-id="3292b-131">Exemplo 3: usar preferências de reversão diferentes</span><span class="sxs-lookup"><span data-stu-id="3292b-131">Example 3: Use different rollback preferences</span></span>

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

# Start-Transaction (-rollbackpreference error)

PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name ContosoCompany -UseTransaction

PS HKCU:\software> New-Item -Path . -Name "Contoso" -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  -Path . -Name ContosoCompany -UseTransaction

# Start-Transaction (-rollbackpreference never)

PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction

New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany                 {}
PS HKCU:\Software> Complete-Transaction

# Succeeds
```

<span data-ttu-id="3292b-132">Este exemplo demonstra o efeito de alterar o valor do parâmetro *RollbackPreference* .</span><span class="sxs-lookup"><span data-stu-id="3292b-132">This example demonstrates the effect of changing the *RollbackPreference* parameter value.</span></span>

<span data-ttu-id="3292b-133">No primeiro conjunto de comandos, **Start-Transaction** não usa *RollbackPreference* .</span><span class="sxs-lookup"><span data-stu-id="3292b-133">In the first set of commands, **Start-Transaction** does not use *RollbackPreference* .</span></span>
<span data-ttu-id="3292b-134">Como resultado, o valor padrão (erro) é usado.</span><span class="sxs-lookup"><span data-stu-id="3292b-134">As a result, the default value (Error) is used.</span></span>
<span data-ttu-id="3292b-135">Quando ocorre um erro em um comando de transação, ou seja, o caminho especificado não existe, a transação é revertida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3292b-135">When an error occurs in a transaction command, that is, the specified path does not exist, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="3292b-136">No segundo conjunto de comandos, **Start-Transaction** usa *RollbackPreference* com um valor de nunca.</span><span class="sxs-lookup"><span data-stu-id="3292b-136">In the second set of commands, **Start-Transaction** uses *RollbackPreference* with a value of Never.</span></span>
<span data-ttu-id="3292b-137">Como resultado, quando ocorre um erro em um comando de transação, a transação ainda está ativa e pode ser concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="3292b-137">As a result, when an error occurs in a transaction command, the transaction is still active and can be completed successfully.</span></span>

<span data-ttu-id="3292b-138">Como a maioria das transações deve ser executada sem erros, o valor padrão de *RollbackPreference* normalmente é preferencial.</span><span class="sxs-lookup"><span data-stu-id="3292b-138">Because most transactions must be performed without error, the default value of *RollbackPreference* is typically preferred.</span></span>

### <span data-ttu-id="3292b-139">Exemplo 4: usar este cmdlet enquanto uma transação estiver em andamento</span><span class="sxs-lookup"><span data-stu-id="3292b-139">Example 4: Use this cmdlet while a transaction is in progress</span></span>

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction
PS HKCU:\software> Get-Transaction
PS HKCU:\software> New-Item "ContosoCompany2" -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\Software> Get-Transaction
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

<span data-ttu-id="3292b-140">Este exemplo mostra o efeito de usar **Start-Transaction** enquanto uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="3292b-140">This example shows the effect of using **Start-Transaction** while a transaction is in progress.</span></span>
<span data-ttu-id="3292b-141">O efeito é semelhante ao de uma união à transação em andamento.</span><span class="sxs-lookup"><span data-stu-id="3292b-141">The effect is much like joining the transaction in progress.</span></span>

<span data-ttu-id="3292b-142">Embora esse seja um comando simplificado, esse cenário ocorre com frequência quando a transação envolve a execução de um script que inclui uma transação completa.</span><span class="sxs-lookup"><span data-stu-id="3292b-142">Although this is a simplified command, this scenario frequently occurs when the transaction involves running a script that includes a complete transaction.</span></span>

<span data-ttu-id="3292b-143">O primeiro comando **Start-Transaction** inicia a transação.</span><span class="sxs-lookup"><span data-stu-id="3292b-143">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="3292b-144">O primeiro comando **New-Item** faz parte da transação.</span><span class="sxs-lookup"><span data-stu-id="3292b-144">The first **New-Item** command is part of the transaction.</span></span>

<span data-ttu-id="3292b-145">O segundo comando **Start-Transaction** adiciona um novo assinante à transação.</span><span class="sxs-lookup"><span data-stu-id="3292b-145">The second **Start-Transaction** command adds a new subscriber to the transaction.</span></span>
<span data-ttu-id="3292b-146">O comando **Get-Transaction** agora retorna uma transação com uma contagem de assinantes de 2.</span><span class="sxs-lookup"><span data-stu-id="3292b-146">The **Get-Transaction** command now returns a transaction with a subscriber count of 2.</span></span>
<span data-ttu-id="3292b-147">O segundo comando **New-Item** faz parte da mesma transação.</span><span class="sxs-lookup"><span data-stu-id="3292b-147">The second **New-Item** command is part of the same transaction.</span></span>

<span data-ttu-id="3292b-148">Nenhuma alteração é feita no registro até que toda a transação seja concluída.</span><span class="sxs-lookup"><span data-stu-id="3292b-148">No changes are made to the registry until the whole transaction is completed.</span></span>
<span data-ttu-id="3292b-149">Para concluir a transação, você deve inserir dois comandos de **transação completa** , um para cada Assinante.</span><span class="sxs-lookup"><span data-stu-id="3292b-149">To complete the transaction, you must enter two **Complete-Transaction** commands, one for each subscriber.</span></span>
<span data-ttu-id="3292b-150">Se você reverter a transação a qualquer momento, toda a transação seria revertida para ambos os assinantes.</span><span class="sxs-lookup"><span data-stu-id="3292b-150">If you were to roll back the transaction at any point, all the transaction would be rolled back for both subscribers.</span></span>

### <span data-ttu-id="3292b-151">Exemplo 5: iniciar uma transação independente enquanto uma estiver em andamento</span><span class="sxs-lookup"><span data-stu-id="3292b-151">Example 5: Start an independent transaction while one is in progress</span></span>

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -Independent
PS HKCU:\software> Get-Transaction
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
MyKey
-----
123
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   1 MyCompany                      {MyKey}
```

<span data-ttu-id="3292b-152">Este exemplo mostra o efeito de usar o parâmetro *independente* de **Start-Transaction** para iniciar uma transação enquanto outra transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="3292b-152">This example shows the effect of using the *Independent* parameter of **Start-Transaction** to start a transaction while another transaction is in progress.</span></span>
<span data-ttu-id="3292b-153">Neste caso, a nova transação é revertida sem afetar a transação original.</span><span class="sxs-lookup"><span data-stu-id="3292b-153">In this case, the new transaction is rolled back without affecting the original transaction.</span></span>

<span data-ttu-id="3292b-154">Apesar de as transações serem logicamente independentes, porque somente uma transação pode ficar ativa por vez, você deve reverter ou confirmar a transação mais recente antes de continuar a trabalhar na transação original.</span><span class="sxs-lookup"><span data-stu-id="3292b-154">Although the transactions are logically independent, because only one transaction can be active at a time, you must roll back or commit the newest transaction before resuming work on the original transaction.</span></span>

<span data-ttu-id="3292b-155">O primeiro conjunto de comandos inicia uma transação.</span><span class="sxs-lookup"><span data-stu-id="3292b-155">The first set of commands starts a transaction.</span></span>
<span data-ttu-id="3292b-156">O comando **New-Item** faz parte da primeira transação.</span><span class="sxs-lookup"><span data-stu-id="3292b-156">The **New-Item** command is part of the first transaction.</span></span>

<span data-ttu-id="3292b-157">No segundo conjunto de comandos, o comando **Start-Transaction** usa o parâmetro *independente* .</span><span class="sxs-lookup"><span data-stu-id="3292b-157">In the second set of commands, the **Start-Transaction** command uses the *Independent* parameter.</span></span>
<span data-ttu-id="3292b-158">O comando **Get-Transaction** que segue mostra o objeto de transação para a transação ativa, que é a mais recente.</span><span class="sxs-lookup"><span data-stu-id="3292b-158">The **Get-Transaction** command that follows shows the transaction object for the active transaction, which is the newest one.</span></span>
<span data-ttu-id="3292b-159">A contagem de assinantes é igual a 1, que mostra que as transações não estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="3292b-159">The subscriber count is equal to 1, that shows that the transactions are unrelated.</span></span>

<span data-ttu-id="3292b-160">Quando a transação ativa é revertida usando um comando **Undo-Transaction** , a transação original torna-se ativa novamente.</span><span class="sxs-lookup"><span data-stu-id="3292b-160">When the active transaction is rolled back by using an **Undo-Transaction** command, the original transaction becomes active again.</span></span>

<span data-ttu-id="3292b-161">O comando **New-ItemProperty** , que faz parte da transação original, termina sem erro e a transação original pode ser concluída usando o comando **Complete-Transaction** .</span><span class="sxs-lookup"><span data-stu-id="3292b-161">The **New-ItemProperty** command, which is part of the original transaction, finishes without error, and the original transaction can be completed by using the **Complete-Transaction** command.</span></span>
<span data-ttu-id="3292b-162">Como resultado, o registro é alterado.</span><span class="sxs-lookup"><span data-stu-id="3292b-162">As a result, the registry is changed.</span></span>

### <span data-ttu-id="3292b-163">Exemplo 6: executar comandos que não fazem parte de uma transação</span><span class="sxs-lookup"><span data-stu-id="3292b-163">Example 6: Run commands that are not part of a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany1" -UseTransaction
PS HKCU:\software> New-Item "ContosoCompany2"
PS HKCU:\software> New-Item "ContosoCompany3" -UseTransaction
PS HKCU:\software> dir contoso*
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany2                {}

PS HKCU:\Software> Complete-Transaction
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany1                     {}
0   0 ContosoCompany2                     {}
0   0 ContosoCompany3                     {}
```

<span data-ttu-id="3292b-164">Este exemplo demonstra que comandos enviados enquanto uma transação está em andamento podem ser incluídos na transação ou podem não ser incluídos.</span><span class="sxs-lookup"><span data-stu-id="3292b-164">This example demonstrates that commands that are submitted while a transaction is in progress can be included in the transaction or not included.</span></span>
<span data-ttu-id="3292b-165">Somente os comandos que usam o parâmetro *UseTransaction* fazem parte da transação.</span><span class="sxs-lookup"><span data-stu-id="3292b-165">Only commands that use the *UseTransaction* parameter are part of the transaction.</span></span>

<span data-ttu-id="3292b-166">O primeiro e terceiro comandos **New-Item** usam o parâmetro *UseTransaction* .</span><span class="sxs-lookup"><span data-stu-id="3292b-166">The first and third **New-Item** commands use the *UseTransaction* parameter.</span></span>
<span data-ttu-id="3292b-167">Estes comandos fazem parte da transação.</span><span class="sxs-lookup"><span data-stu-id="3292b-167">These commands are part of the transaction.</span></span>
<span data-ttu-id="3292b-168">Como o segundo comando **New-Item** não usa o parâmetro *UseTransaction* , ele não faz parte da transação.</span><span class="sxs-lookup"><span data-stu-id="3292b-168">Because the second **New-Item** command does not use the *UseTransaction* parameter, it is not part of the transaction.</span></span>

<span data-ttu-id="3292b-169">O primeiro comando dir mostra o efeito.</span><span class="sxs-lookup"><span data-stu-id="3292b-169">The first dir command shows the effect.</span></span>
<span data-ttu-id="3292b-170">O segundo comando **New-Item** é concluído imediatamente, mas o primeiro e terceiro comandos **New-Item** não são efetivos até que a transação seja confirmada.</span><span class="sxs-lookup"><span data-stu-id="3292b-170">The second **New-Item** command is completed immediately, but the first and third **New-Item** commands are not effective until the transaction is committed.</span></span>

<span data-ttu-id="3292b-171">O comando **Complete-Transaction** confirma a transação.</span><span class="sxs-lookup"><span data-stu-id="3292b-171">The **Complete-Transaction** command commits the transaction.</span></span>
<span data-ttu-id="3292b-172">Como resultado, o segundo comando dir mostra que todos os novos itens são adicionados ao registro.</span><span class="sxs-lookup"><span data-stu-id="3292b-172">As a result, the second dir command shows that all of the new items are added to the registry.</span></span>

### <span data-ttu-id="3292b-173">Exemplo 7: reverter uma transação que não é concluída em um tempo especificado</span><span class="sxs-lookup"><span data-stu-id="3292b-173">Example 7: Roll back a transaction that does not finish in a specified time</span></span>

```
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> Get-Transaction
PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> > Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----------
Error                1                 RolledBack

PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  MyCompany -UseTransaction
```

<span data-ttu-id="3292b-174">Esse comando usa o parâmetro *Timeout* de **Start-Transaction** para iniciar uma transação que deve ser concluída dentro de dois minutos.</span><span class="sxs-lookup"><span data-stu-id="3292b-174">This command uses the *Timeout* parameter of **Start-Transaction** to start a transaction that must be completed within two minutes.</span></span>
<span data-ttu-id="3292b-175">Se a transação não for concluída quando o tempo limite expirar, ela será revertida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3292b-175">If the transaction is not finished when the time-out expires, it is rolled back automatically.</span></span>

<span data-ttu-id="3292b-176">Quando o tempo limite expirar, você não será notificado, mas a propriedade **status** do objeto de transação será definida como revertida e os comandos que usam o parâmetro *UseTransaction* falharão.</span><span class="sxs-lookup"><span data-stu-id="3292b-176">When the time-out expires, you are not notified, but the **Status** property of the transaction object is set to RolledBack and commands that use the *UseTransaction* parameter fail.</span></span>

## <span data-ttu-id="3292b-177">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3292b-177">PARAMETERS</span></span>

### <span data-ttu-id="3292b-178">-Independente</span><span class="sxs-lookup"><span data-stu-id="3292b-178">-Independent</span></span>
<span data-ttu-id="3292b-179">Indica que esse cmdlet inicia uma transação que é independente de qualquer transação em andamento.</span><span class="sxs-lookup"><span data-stu-id="3292b-179">Indicates that this cmdlet starts a transaction that is independent of any transactions in progress.</span></span>
<span data-ttu-id="3292b-180">Por padrão, se você usar **Start-Transaction** enquanto outra transação estiver em andamento, um novo assinante será adicionado à transação em andamento.</span><span class="sxs-lookup"><span data-stu-id="3292b-180">By default, if you use **Start-Transaction** while another transaction is in progress, a new subscriber is added to the transaction in progress.</span></span>
<span data-ttu-id="3292b-181">Este parâmetro tem efeito somente quando já existe uma transação em andamento na sessão.</span><span class="sxs-lookup"><span data-stu-id="3292b-181">This parameter has an effect only when a transaction is already in progress in the session.</span></span>

<span data-ttu-id="3292b-182">Por padrão, se você usar **Start-Transaction** enquanto uma transação estiver em andamento, o objeto de transação existente será reutilizado e a contagem de assinantes será incrementada.</span><span class="sxs-lookup"><span data-stu-id="3292b-182">By default, if you use **Start-Transaction** while a transaction is in progress, the existing transaction object is reused and the subscriber count is incremented.</span></span>
<span data-ttu-id="3292b-183">O efeito é semelhante ao de uma união à transação original.</span><span class="sxs-lookup"><span data-stu-id="3292b-183">The effect is much like joining the original transaction.</span></span>
<span data-ttu-id="3292b-184">Um comando Undo-Transaction reverte toda a transação.</span><span class="sxs-lookup"><span data-stu-id="3292b-184">An Undo-Transaction command rolls back the whole the transaction.</span></span>
<span data-ttu-id="3292b-185">Para concluir a transação, você deve inserir um comando Complete-Transaction para cada assinante.</span><span class="sxs-lookup"><span data-stu-id="3292b-185">To complete the transaction, you must enter a Complete-Transaction command for each subscriber.</span></span>
<span data-ttu-id="3292b-186">Como a maioria das transações que estão em andamento simultaneamente são relacionadas, o padrão é suficiente para a maior parte dos usos.</span><span class="sxs-lookup"><span data-stu-id="3292b-186">Because most transactions that are in progress at the same time are related, the default is sufficient for most uses.</span></span>

<span data-ttu-id="3292b-187">Se você especificar o parâmetro *independente* , esse cmdlet criará uma nova transação que pode ser concluída ou desfeita sem afetar a transação original.</span><span class="sxs-lookup"><span data-stu-id="3292b-187">If you specify the *Independent* parameter, this cmdlet creates a new transaction that can be completed or undone without affecting the original transaction.</span></span>
<span data-ttu-id="3292b-188">No entanto, como somente uma transação pode estar ativa por vez, você deve concluir ou reverter a nova transação antes de continuar a trabalhar com a transação original.</span><span class="sxs-lookup"><span data-stu-id="3292b-188">However, because only one transaction can be active at a time, you must complete or roll back the new transaction before resuming work on the original transaction.</span></span>

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

### <span data-ttu-id="3292b-189">-RollbackPreference</span><span class="sxs-lookup"><span data-stu-id="3292b-189">-RollbackPreference</span></span>
<span data-ttu-id="3292b-190">Especifica as condições sob as quais uma transação é revertida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3292b-190">Specifies the conditions under which a transaction is automatically rolled back.</span></span>
<span data-ttu-id="3292b-191">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="3292b-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3292b-192">Erro.</span><span class="sxs-lookup"><span data-stu-id="3292b-192">Error.</span></span>
<span data-ttu-id="3292b-193">A transação é revertida automaticamente se ocorrer um erro de finalização ou de não finalização.</span><span class="sxs-lookup"><span data-stu-id="3292b-193">The transaction is rolled back automatically if a terminating or non-terminating error occurs.</span></span>
- <span data-ttu-id="3292b-194">TerminatingError.</span><span class="sxs-lookup"><span data-stu-id="3292b-194">TerminatingError.</span></span>
<span data-ttu-id="3292b-195">Se ocorrer um erro de finalização, a transação será revertida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3292b-195">The transaction is rolled back automatically if a terminating error occurs.</span></span>
- <span data-ttu-id="3292b-196">Nunca.</span><span class="sxs-lookup"><span data-stu-id="3292b-196">Never.</span></span>
<span data-ttu-id="3292b-197">A transação nunca é revertida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3292b-197">The transaction is never rolled back automatically.</span></span>

<span data-ttu-id="3292b-198">O valor padrão é Error.</span><span class="sxs-lookup"><span data-stu-id="3292b-198">The default value is Error.</span></span>

```yaml
Type: System.Management.Automation.RollbackSeverity
Parameter Sets: (All)
Aliases:
Accepted values: Error, TerminatingError, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3292b-199">-Tempo limite</span><span class="sxs-lookup"><span data-stu-id="3292b-199">-Timeout</span></span>
<span data-ttu-id="3292b-200">Especifica o tempo máximo, em minutos, pelo qual a transação fica ativa.</span><span class="sxs-lookup"><span data-stu-id="3292b-200">Specifies the maximum time, in minutes, that the transaction is active.</span></span>
<span data-ttu-id="3292b-201">Quando o tempo limite expira, a transação é revertida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3292b-201">When the time-out expires, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="3292b-202">Por padrão, não há tempo limite para transações iniciadas pela linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3292b-202">By default, there is no time-out for transactions that are started at the command line.</span></span>
<span data-ttu-id="3292b-203">Quando as transações são iniciadas por um script, o tempo limite padrão é de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="3292b-203">When transactions are started by a script, the default time-out is 30 minutes.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutMins

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3292b-204">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3292b-204">-Confirm</span></span>
<span data-ttu-id="3292b-205">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3292b-205">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3292b-206">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3292b-206">-WhatIf</span></span>
<span data-ttu-id="3292b-207">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="3292b-207">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3292b-208">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="3292b-208">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3292b-209">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3292b-209">CommonParameters</span></span>
<span data-ttu-id="3292b-210">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3292b-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3292b-211">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3292b-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3292b-212">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3292b-212">INPUTS</span></span>

### <span data-ttu-id="3292b-213">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3292b-213">None</span></span>
<span data-ttu-id="3292b-214">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3292b-214">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="3292b-215">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3292b-215">OUTPUTS</span></span>

### <span data-ttu-id="3292b-216">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3292b-216">None</span></span>
<span data-ttu-id="3292b-217">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="3292b-217">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3292b-218">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3292b-218">NOTES</span></span>

## <span data-ttu-id="3292b-219">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3292b-219">RELATED LINKS</span></span>

[<span data-ttu-id="3292b-220">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="3292b-220">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="3292b-221">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="3292b-221">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="3292b-222">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="3292b-222">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="3292b-223">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="3292b-223">Use-Transaction</span></span>](Use-Transaction.md)
