---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Transaction
ms.openlocfilehash: bb8e9e1f204c67207f31613181f856d3bcaf8dc3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192592"
---
# <span data-ttu-id="25e80-103">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="25e80-103">Get-Transaction</span></span>

## <span data-ttu-id="25e80-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="25e80-104">SYNOPSIS</span></span>
<span data-ttu-id="25e80-105">Obtém a transação atual (ativa).</span><span class="sxs-lookup"><span data-stu-id="25e80-105">Gets the current (active) transaction.</span></span>

## <span data-ttu-id="25e80-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="25e80-106">SYNTAX</span></span>

```
Get-Transaction [<CommonParameters>]
```

## <span data-ttu-id="25e80-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="25e80-107">DESCRIPTION</span></span>
<span data-ttu-id="25e80-108">O cmdlet **Get-Transaction** Obtém um objeto que representa a transação atual na sessão.</span><span class="sxs-lookup"><span data-stu-id="25e80-108">The **Get-Transaction** cmdlet gets an object that represents the current transaction in the session.</span></span>

<span data-ttu-id="25e80-109">Esse cmdlet nunca retorna mais de um objeto, porque somente uma transação está ativa por vez.</span><span class="sxs-lookup"><span data-stu-id="25e80-109">This cmdlet never returns more than one object, because only one transaction is active at a time.</span></span>
<span data-ttu-id="25e80-110">Se você iniciar uma ou mais transações independentes (usando o parâmetro independente de Start-Transaction), a transação iniciada mais recentemente estará ativa e essa será a transação que o **Get-Transaction** retornará.</span><span class="sxs-lookup"><span data-stu-id="25e80-110">If you start one or more independent transactions (by using the Independent parameter of Start-Transaction), the most recently started transaction is active, and that is the transaction that **Get-Transaction** returns.</span></span>

<span data-ttu-id="25e80-111">Quando todas as transações ativas tiverem sido revertidas ou confirmadas, esse cmdlet mostrará a transação que foi ativada mais recentemente na sessão.</span><span class="sxs-lookup"><span data-stu-id="25e80-111">When all active transactions have either been rolled back or committed, this cmdlet shows the transaction that was most recently active in the session.</span></span>

<span data-ttu-id="25e80-112">Esse cmdlet é um de um conjunto de cmdlets que dão suporte ao recurso de transações no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25e80-112">This cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="25e80-113">Para obter mais informações, consulte about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="25e80-113">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="25e80-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="25e80-114">EXAMPLES</span></span>

### <span data-ttu-id="25e80-115">Exemplo 1: obter a transação atual</span><span class="sxs-lookup"><span data-stu-id="25e80-115">Example 1: Get the current transaction</span></span>

```
PS C:\> Start-Transaction
PS C:\> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="25e80-116">Esse comando usa o cmdlet Get-Transaction para obter a transação atual.</span><span class="sxs-lookup"><span data-stu-id="25e80-116">This command uses the Get-Transaction cmdlet to get the current transaction.</span></span>

### <span data-ttu-id="25e80-117">Exemplo 2: mostrar as propriedades e os métodos do objeto de transação</span><span class="sxs-lookup"><span data-stu-id="25e80-117">Example 2: Show the properties and methods of the transaction object</span></span>

```
PS C:\> Get-Transaction | Get-Member

Name               MemberType Definition
----               ---------- ----------
Dispose            Method     System.Void Dispose(), System.Void Dispose(Boolean disposing)
Equals             Method     System.Boolean Equals(Object obj)
GetHashCode        Method     System.Int32 GetHashCode()
GetType            Method     System.Type GetType()
ToString           Method     System.String ToString()
IsCommitted        Property   System.Boolean IsCommitted {get;}
IsRolledBack       Property   System.Boolean IsRolledBack {get;}
RollbackPreference Property   System.Management.Automation.RollbackSeverity RollbackPreference {get;}
SubscriberCount    Property   System.Int32 SubscriberCount {get;set;}
```

<span data-ttu-id="25e80-118">Esse comando usa o cmdlet Get-Member para mostrar as propriedades e métodos do objeto de transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-118">This command uses the Get-Member cmdlet to show the properties and methods of the transaction object.</span></span>

### <span data-ttu-id="25e80-119">Exemplo 3: mostrar os valores de propriedade de uma transação revertida</span><span class="sxs-lookup"><span data-stu-id="25e80-119">Example 3: Show the property values of a rolled back transaction</span></span>

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Undo-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ----------
Error                0                 RolledBack
```

<span data-ttu-id="25e80-120">Esse comando mostra os valores de propriedade de um objeto de transação para uma transação que foi revertida.</span><span class="sxs-lookup"><span data-stu-id="25e80-120">This command shows the property values of a transaction object for a transaction that has been rolled back.</span></span>

### <span data-ttu-id="25e80-121">Exemplo 4: mostrar os valores de propriedade de uma transação confirmada</span><span class="sxs-lookup"><span data-stu-id="25e80-121">Example 4: Show the property values of a committed transaction</span></span>

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

<span data-ttu-id="25e80-122">Esse comando mostra os valores de propriedade de um objeto de transação para uma transação que foi confirmada.</span><span class="sxs-lookup"><span data-stu-id="25e80-122">This command shows the property values of a transaction object for a transaction that has been committed.</span></span>

### <span data-ttu-id="25e80-123">Exemplo 5: iniciar uma transação enquanto outra estiver em andamento</span><span class="sxs-lookup"><span data-stu-id="25e80-123">Example 5: Start a transaction while another is in progress</span></span>

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany2 -UseTransaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

<span data-ttu-id="25e80-124">Este exemplo mostra o efeito sobre o objeto de transação de iniciar uma transação enquanto outra transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="25e80-124">This example shows the effect on the transaction object of starting a transaction while another transaction is in progress.</span></span>
<span data-ttu-id="25e80-125">Normalmente, isso ocorre quando um script que executa uma transação inclui uma função ou chama um script que contém outra transação completa.</span><span class="sxs-lookup"><span data-stu-id="25e80-125">Typically, this happens when a script that runs a transaction includes a function or calls a script that contains another complete transaction.</span></span>

<span data-ttu-id="25e80-126">A menos que o segundo comando **Start-Transaction** inclua o parâmetro *independente* , **Start-Transaction** não criará uma nova transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-126">Unless the second **Start-Transaction** command includes the *Independent* parameter, **Start-Transaction** does not create a new transaction.</span></span>
<span data-ttu-id="25e80-127">Em vez disso, ele adiciona um segundo assinante à transação original.</span><span class="sxs-lookup"><span data-stu-id="25e80-127">Instead, it adds a second subscriber to the original transaction.</span></span>

<span data-ttu-id="25e80-128">O primeiro comando **Start-Transaction** inicia a transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-128">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="25e80-129">Um comando New-Item com o parâmetro *UseTransaction* é parte da transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-129">A New-Item command with the *UseTransaction* parameter is part of the transaction.</span></span>

<span data-ttu-id="25e80-130">Um segundo comando **Start-Transaction** adiciona um assinante à transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-130">A second **Start-Transaction** command adds a subscriber to the transaction.</span></span>
<span data-ttu-id="25e80-131">O comando New-Item seguinte também faz parte da transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-131">The next New-Item command is also part of the transaction.</span></span>

<span data-ttu-id="25e80-132">O primeiro comando **Get-Transaction** mostra a transação de vários assinantes.</span><span class="sxs-lookup"><span data-stu-id="25e80-132">The first **Get-Transaction** command shows the multi-subscriber transaction.</span></span>
<span data-ttu-id="25e80-133">Observe que a contagem de assinantes é 2.</span><span class="sxs-lookup"><span data-stu-id="25e80-133">Notice that the subscriber count is 2.</span></span>

<span data-ttu-id="25e80-134">O primeiro comando Complete-Transaction não confirma a transação, mas reduz a contagem de assinantes para 1.</span><span class="sxs-lookup"><span data-stu-id="25e80-134">The first Complete-Transaction command does not commit the transaction, but it reduces the subscriber count to 1.</span></span>

<span data-ttu-id="25e80-135">O segundo comando **Complete-Transaction** confirma a transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-135">The second **Complete-Transaction** command commits the transaction.</span></span>

### <span data-ttu-id="25e80-136">Exemplo 6: iniciar uma transação independente enquanto outra estiver em andamento</span><span class="sxs-lookup"><span data-stu-id="25e80-136">Example 6: Start an independent transaction while another is in progress</span></span>

```
PS C:\>
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Start-Transaction -Independent
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
```

<span data-ttu-id="25e80-137">Este exemplo mostra o efeito sobre o objeto de transação de iniciar uma transação independente enquanto outra transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="25e80-137">This example shows the effect on the transaction object of starting an independent transaction while another transaction is in progress.</span></span>

<span data-ttu-id="25e80-138">O primeiro comando **Start-Transaction** inicia a transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-138">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="25e80-139">Um comando **New-Item** com o parâmetro *UseTransaction* é parte da transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-139">A **New-Item** command with the *UseTransaction* parameter is part of the transaction.</span></span>

<span data-ttu-id="25e80-140">Um segundo comando **Start-Transaction** adiciona um assinante à transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-140">A second **Start-Transaction** command adds a subscriber to the transaction.</span></span>
<span data-ttu-id="25e80-141">O próximo comando **New-Item** também faz parte da transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-141">The next **New-Item** command is also part of the transaction.</span></span>

<span data-ttu-id="25e80-142">O primeiro comando **Get-Transaction** mostra a transação de vários assinantes.</span><span class="sxs-lookup"><span data-stu-id="25e80-142">The first **Get-Transaction** command shows the multi-subscriber transaction.</span></span>
<span data-ttu-id="25e80-143">Observe que a contagem de assinantes é 2.</span><span class="sxs-lookup"><span data-stu-id="25e80-143">Note that the subscriber count is 2.</span></span>

<span data-ttu-id="25e80-144">O comando **Complete-Transaction** reduz a contagem de assinantes para 1, mas não confirma a transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-144">The **Complete-Transaction** command reduces the subscriber count to 1, but it does not commit the transaction.</span></span>

<span data-ttu-id="25e80-145">O segundo comando **Complete-Transaction** confirma a transação.</span><span class="sxs-lookup"><span data-stu-id="25e80-145">The second **Complete-Transaction** command commits the transaction.</span></span>

## <span data-ttu-id="25e80-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="25e80-146">PARAMETERS</span></span>

### <span data-ttu-id="25e80-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="25e80-147">CommonParameters</span></span>
<span data-ttu-id="25e80-148">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="25e80-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="25e80-149">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="25e80-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="25e80-150">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="25e80-150">INPUTS</span></span>

### <span data-ttu-id="25e80-151">Nenhum</span><span class="sxs-lookup"><span data-stu-id="25e80-151">None</span></span>
<span data-ttu-id="25e80-152">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25e80-152">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="25e80-153">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="25e80-153">OUTPUTS</span></span>

### <span data-ttu-id="25e80-154">System. Management. Automation. PSTransaction</span><span class="sxs-lookup"><span data-stu-id="25e80-154">System.Management.Automation.PSTransaction</span></span>
<span data-ttu-id="25e80-155">Esse cmdlet retorna um objeto que representa a transação atual.</span><span class="sxs-lookup"><span data-stu-id="25e80-155">This cmdlet returns an object that represents the current transaction.</span></span>

## <span data-ttu-id="25e80-156">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="25e80-156">NOTES</span></span>

## <span data-ttu-id="25e80-157">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="25e80-157">RELATED LINKS</span></span>

[<span data-ttu-id="25e80-158">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="25e80-158">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="25e80-159">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="25e80-159">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="25e80-160">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="25e80-160">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="25e80-161">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="25e80-161">Use-Transaction</span></span>](Use-Transaction.md)

[<span data-ttu-id="25e80-162">New-Item</span><span class="sxs-lookup"><span data-stu-id="25e80-162">New-Item</span></span>](New-Item.md)
