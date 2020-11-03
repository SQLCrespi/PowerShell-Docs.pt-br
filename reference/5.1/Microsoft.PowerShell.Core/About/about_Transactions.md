---
description: Descreve como gerenciar operações transacionadas no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_transactions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Transactions
ms.openlocfilehash: 522e0f727754b0b0153571039f3bf3966d0abf20
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195954"
---
# <a name="about-transactions"></a><span data-ttu-id="e4879-104">Sobre transações</span><span class="sxs-lookup"><span data-stu-id="e4879-104">About Transactions</span></span>

## <a name="short-description"></a><span data-ttu-id="e4879-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="e4879-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="e4879-106">Descreve como gerenciar operações transacionadas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4879-106">Describes how to manage transacted operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="e4879-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="e4879-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="e4879-108">As transações têm suporte no PowerShell a partir do PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="e4879-108">Transactions are supported in PowerShell beginning in PowerShell 2.0.</span></span> <span data-ttu-id="e4879-109">Esse recurso permite que você inicie uma transação, para indicar quais comandos fazem parte da transação e para confirmar ou reverter uma transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-109">This feature enables you to start a transaction, to indicate which commands are part of the transaction, and to commit or roll back a transaction.</span></span>

## <a name="about-transactions"></a><span data-ttu-id="e4879-110">SOBRE TRANSAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e4879-110">ABOUT TRANSACTIONS</span></span>

<span data-ttu-id="e4879-111">No PowerShell, uma transação é um conjunto de um ou mais comandos que são gerenciados como uma unidade lógica.</span><span class="sxs-lookup"><span data-stu-id="e4879-111">In PowerShell, a transaction is a set of one or more commands that are managed as a logical unit.</span></span> <span data-ttu-id="e4879-112">Uma transação pode ser concluída ("confirmada"), que altera os dados afetados pela transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-112">A transaction can be completed ("committed"), which changes data affected by the transaction.</span></span> <span data-ttu-id="e4879-113">Ou, uma transação pode ser completamente desfeita ("revertida") para que os dados afetados não sejam alterados pela transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-113">Or, a transaction can be completely undone ("rolled back") so that the affected data is not changed by the transaction.</span></span>

<span data-ttu-id="e4879-114">Como os comandos em uma transação são gerenciados como uma unidade, todos os comandos são confirmados ou todos os comandos são revertidos.</span><span class="sxs-lookup"><span data-stu-id="e4879-114">Because the commands in a transaction are managed as a unit, either all commands are committed, or all commands are rolled back.</span></span>

<span data-ttu-id="e4879-115">As transações são amplamente usadas no processamento de dados, mais notavelmente em operações de banco e transações financeiras.</span><span class="sxs-lookup"><span data-stu-id="e4879-115">Transactions are widely used in data processing, most notably in database operations and for financial transactions.</span></span> <span data-ttu-id="e4879-116">As transações são usadas com mais frequência quando o cenário de pior caso para um conjunto de comandos não é que todas elas falham, mas que alguns comandos tenham êxito enquanto outros falham, deixando o sistema em um estado danificado, falso ou não interpretável que seja difícil de reparar.</span><span class="sxs-lookup"><span data-stu-id="e4879-116">Transactions are most often used when the worst-case scenario for a set of commands is not that they all fail, but that some commands succeed while others fail, leaving the system in a damaged, false, or uninterpretable state that is difficult to repair.</span></span>

## <a name="transaction-cmdlets"></a><span data-ttu-id="e4879-117">CMDLETS DE TRANSAÇÃO</span><span class="sxs-lookup"><span data-stu-id="e4879-117">TRANSACTION CMDLETS</span></span>

<span data-ttu-id="e4879-118">O PowerShell inclui vários cmdlets projetados para gerenciar transações.</span><span class="sxs-lookup"><span data-stu-id="e4879-118">PowerShell includes several cmdlets designed for managing transactions.</span></span>

- <span data-ttu-id="e4879-119">Start-Transaction: inicia uma nova transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-119">Start-Transaction: Starts a new transaction.</span></span>
- <span data-ttu-id="e4879-120">Use-Transaction: Adiciona um comando ou uma expressão à transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-120">Use-Transaction: Adds a command or expression to the transaction.</span></span> <span data-ttu-id="e4879-121">O comando deve usar objetos habilitados para transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-121">The command must use transaction-enabled objects.</span></span>
- <span data-ttu-id="e4879-122">Undo-Transaction: reverte a transação para que nenhum dado seja alterado pela transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-122">Undo-Transaction: Rolls back the transaction so that no data is changed by the transaction.</span></span>
- <span data-ttu-id="e4879-123">Complete-Transaction: confirma a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-123">Complete-Transaction: Commits the transaction.</span></span> <span data-ttu-id="e4879-124">Os dados afetados pela transação são alterados.</span><span class="sxs-lookup"><span data-stu-id="e4879-124">The data affected by the transaction is changed.</span></span>
- <span data-ttu-id="e4879-125">Get-Transaction: Obtém informações sobre a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-125">Get-Transaction: Gets information about the active transaction.</span></span>

<span data-ttu-id="e4879-126">Para obter uma lista de cmdlets de transação, digite:</span><span class="sxs-lookup"><span data-stu-id="e4879-126">For a list of transaction cmdlets, type:</span></span>

```powershell
get-command *transaction
```

<span data-ttu-id="e4879-127">Para obter informações detalhadas sobre os cmdlets, digite:</span><span class="sxs-lookup"><span data-stu-id="e4879-127">For detailed information about the cmdlets, type:</span></span>

```powershell
get-help use-transaction -detailed
```

## <a name="transaction-enabled-elements"></a><span data-ttu-id="e4879-128">ELEMENTOS HABILITADOS PARA TRANSAÇÃO</span><span class="sxs-lookup"><span data-stu-id="e4879-128">TRANSACTION-ENABLED ELEMENTS</span></span>

<span data-ttu-id="e4879-129">Para participar de uma transação, o cmdlet e o provedor devem dar suporte a transações.</span><span class="sxs-lookup"><span data-stu-id="e4879-129">To participate in a transaction, both the cmdlet and the provider must support transactions.</span></span> <span data-ttu-id="e4879-130">Esse recurso é integrado aos objetos afetados pela transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-130">This feature is built in to the objects that are affected by the transaction.</span></span>

<span data-ttu-id="e4879-131">O provedor de registro do PowerShell dá suporte a transações no Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="e4879-131">The PowerShell Registry provider supports transactions in Windows Vista.</span></span> <span data-ttu-id="e4879-132">O objeto transacionastring (Microsoft. PowerShell. Commands. Management. transacionastring) funciona com qualquer sistema operacional que executa o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4879-132">The TransactedString object (Microsoft.PowerShell.Commands.Management.TransactedString) works with any operating system that runs PowerShell.</span></span>

<span data-ttu-id="e4879-133">Outros provedores do PowerShell podem dar suporte a transações.</span><span class="sxs-lookup"><span data-stu-id="e4879-133">Other PowerShell providers can support transactions.</span></span> <span data-ttu-id="e4879-134">Para localizar os provedores do PowerShell em sua sessão que dão suporte a transações, use o seguinte comando para localizar o valor de "transações" na propriedade Capabilities dos provedores:</span><span class="sxs-lookup"><span data-stu-id="e4879-134">To find the PowerShell providers in your session that support transactions, use the following command to find the "Transactions" value in the Capabilities property of providers:</span></span>

```powershell
get-psprovider | where {$_.Capabilities -like "*transactions*"}
```

<span data-ttu-id="e4879-135">Para obter mais informações sobre um provedor, consulte a ajuda do provedor.</span><span class="sxs-lookup"><span data-stu-id="e4879-135">For more information about a provider, see the Help for the provider.</span></span> <span data-ttu-id="e4879-136">Para obter ajuda do provedor, digite:</span><span class="sxs-lookup"><span data-stu-id="e4879-136">To get provider Help, type:</span></span>

```
get-help <provider-name>
```

<span data-ttu-id="e4879-137">Por exemplo, para obter Ajuda para o provedor de Registro, digite:</span><span class="sxs-lookup"><span data-stu-id="e4879-137">For example, to get Help for the Registry provider, type:</span></span>

```powershell
get-help registry
```

## <a name="the-usetransaction-parameter"></a><span data-ttu-id="e4879-138">O PARÂMETRO USETRANSACTION</span><span class="sxs-lookup"><span data-stu-id="e4879-138">THE USETRANSACTION PARAMETER</span></span>

<span data-ttu-id="e4879-139">Os cmdlets que podem dar suporte a transações têm um parâmetro UseTransaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-139">Cmdlets that can support transactions have a UseTransaction parameter.</span></span> <span data-ttu-id="e4879-140">Esse parâmetro inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-140">This parameter includes the command in the active transaction.</span></span> <span data-ttu-id="e4879-141">Você pode usar o nome completo do parâmetro ou seu alias, "usetx".</span><span class="sxs-lookup"><span data-stu-id="e4879-141">You can use the full parameter name or its alias, "usetx".</span></span>

<span data-ttu-id="e4879-142">O parâmetro pode ser usado somente quando a sessão contiver uma transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-142">The parameter can be used only when the session contains an active transaction.</span></span> <span data-ttu-id="e4879-143">Se você inserir um comando com o parâmetro UseTransaction quando não houver nenhuma transação ativa, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="e4879-143">If you enter a command with the UseTransaction parameter when there is no active transaction, the command fails.</span></span>

<span data-ttu-id="e4879-144">Para localizar cmdlets com o parâmetro UseTransaction, digite:</span><span class="sxs-lookup"><span data-stu-id="e4879-144">To find cmdlets with the UseTransaction parameter, type:</span></span>

```powershell
get-help * -parameter UseTransaction
```

<span data-ttu-id="e4879-145">No PowerShell Core, todos os cmdlets projetados para trabalhar com provedores do PowerShell dão suporte a transações.</span><span class="sxs-lookup"><span data-stu-id="e4879-145">In PowerShell core, all of the cmdlets designed to work with PowerShell providers support transactions.</span></span> <span data-ttu-id="e4879-146">Como resultado, você pode usar os cmdlets do provedor para gerenciar transações.</span><span class="sxs-lookup"><span data-stu-id="e4879-146">As a result, you can use the provider cmdlets to manage transactions.</span></span>

<span data-ttu-id="e4879-147">Para obter mais informações sobre provedores do PowerShell, consulte [about_Providers](about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="e4879-147">For more information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

## <a name="the-transaction-object"></a><span data-ttu-id="e4879-148">O OBJETO DE TRANSAÇÃO</span><span class="sxs-lookup"><span data-stu-id="e4879-148">THE TRANSACTION OBJECT</span></span>

<span data-ttu-id="e4879-149">As transações são representadas no PowerShell por um objeto de transação, System. Management. Automation. Transaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-149">Transactions are represented in PowerShell by a transaction object, System.Management.Automation.Transaction.</span></span>

<span data-ttu-id="e4879-150">O objeto tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="e4879-150">The object has the following properties:</span></span>

- <span data-ttu-id="e4879-151">RollbackPreference: contém a preferência de reversão definida para a transação atual.</span><span class="sxs-lookup"><span data-stu-id="e4879-151">RollbackPreference: Contains the rollback preference set for the current transaction.</span></span> <span data-ttu-id="e4879-152">Você pode definir a preferência de reversão ao usar Start-Transaction para iniciar a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-152">You can set the rollback preference when you use Start-Transaction to start the transaction.</span></span>

  <span data-ttu-id="e4879-153">A preferência de reversão determina as condições sob as quais a transação é revertida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e4879-153">The rollback preference determines the conditions under which the transaction is rolled back automatically.</span></span> <span data-ttu-id="e4879-154">Os valores válidos são Error, TerminatingError e Never.</span><span class="sxs-lookup"><span data-stu-id="e4879-154">Valid values are Error, TerminatingError, and Never.</span></span> <span data-ttu-id="e4879-155">O valor padrão é Error.</span><span class="sxs-lookup"><span data-stu-id="e4879-155">The default value is Error.</span></span>

- <span data-ttu-id="e4879-156">Status: contém o status atual da transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-156">Status: Contains the current status of the transaction.</span></span> <span data-ttu-id="e4879-157">Os valores válidos são ativo, confirmado e revertida.</span><span class="sxs-lookup"><span data-stu-id="e4879-157">Valid values are Active, Committed, and RolledBack.</span></span>

- <span data-ttu-id="e4879-158">SubscriberCount: contém o número de assinantes para a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-158">SubscriberCount: Contains the number of subscribers to the transaction.</span></span> <span data-ttu-id="e4879-159">Um assinante é adicionado a uma transação quando você inicia uma transação enquanto outra transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="e4879-159">A subscriber is added to a transaction when you start a transaction while another transaction is in progress.</span></span> <span data-ttu-id="e4879-160">A contagem de assinantes é decrementada quando um assinante confirma a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-160">The subscriber count is decremented when a subscriber commits the transaction.</span></span>

## <a name="active-transactions"></a><span data-ttu-id="e4879-161">TRANSAÇÕES ATIVAS</span><span class="sxs-lookup"><span data-stu-id="e4879-161">ACTIVE TRANSACTIONS</span></span>

<span data-ttu-id="e4879-162">No PowerShell, apenas uma transação está ativa por vez e você pode gerenciar apenas a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-162">In PowerShell, only one transaction is active at a time, and you can manage only the active transaction.</span></span> <span data-ttu-id="e4879-163">Várias transações podem estar em andamento na mesma sessão ao mesmo tempo, mas apenas a transação iniciada mais recentemente está ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-163">Multiple transactions can be in progress in the same session at the same time, but only the most-recently started transaction is active.</span></span>

<span data-ttu-id="e4879-164">Como resultado, você não pode especificar uma transação específica ao usar os cmdlets de transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-164">As a result, you cannot specify a particular transaction when using the transaction cmdlets.</span></span> <span data-ttu-id="e4879-165">Os comandos sempre se aplicam à transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-165">Commands always apply to the active transaction.</span></span>

<span data-ttu-id="e4879-166">Isso é mais evidente no comportamento do cmdlet Get-Transaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-166">This is most evident in the behavior of the Get-Transaction cmdlet.</span></span> <span data-ttu-id="e4879-167">Quando você insere um comando de Get-Transaction, Get-Transaction sempre obtém apenas um objeto de transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-167">When you enter a Get-Transaction command, Get-Transaction always gets only one transaction object.</span></span> <span data-ttu-id="e4879-168">Esse objeto é o objeto que representa a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-168">This object is the object that represents the active transaction.</span></span>

<span data-ttu-id="e4879-169">Para gerenciar uma transação diferente, você deve primeiro concluir a transação ativa, confirmando-a ou Redistribuindo-a.</span><span class="sxs-lookup"><span data-stu-id="e4879-169">To manage a different transaction, you must first finish the active transaction, either by committing it or rolling it back.</span></span> <span data-ttu-id="e4879-170">Quando você faz isso, a transação anterior torna-se ativa automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e4879-170">When you do this, the previous transaction becomes active automatically.</span></span> <span data-ttu-id="e4879-171">As transações se tornam ativas na ordem inversa da qual elas são iniciadas, para que a transação iniciada mais recentemente esteja sempre ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-171">Transactions become active in the reverse of order of which they are started, so that the most recently started transaction is always active.</span></span>

## <a name="subscribers-and-independent-transactions"></a><span data-ttu-id="e4879-172">ASSINANTES E TRANSAÇÕES INDEPENDENTES</span><span class="sxs-lookup"><span data-stu-id="e4879-172">SUBSCRIBERS AND INDEPENDENT TRANSACTIONS</span></span>

<span data-ttu-id="e4879-173">Se você iniciar uma transação enquanto outra transação estiver em andamento, por padrão, o PowerShell não iniciará uma nova transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-173">If you start a transaction while another transaction is in progress, by default, PowerShell does not start a new transaction.</span></span> <span data-ttu-id="e4879-174">Em vez disso, ele adiciona um "assinante" à transação atual.</span><span class="sxs-lookup"><span data-stu-id="e4879-174">Instead, it adds a "subscriber" to the current transaction.</span></span>

<span data-ttu-id="e4879-175">Quando uma transação tem vários assinantes, um único comando Undo-Transaction a qualquer momento reverte a transação inteira para todos os assinantes.</span><span class="sxs-lookup"><span data-stu-id="e4879-175">When a transaction has multiple subscribers, a single Undo-Transaction command at any point rolls back the entire transaction for all subscribers.</span></span> <span data-ttu-id="e4879-176">No entanto, para confirmar a transação, você deve inserir um comando Complete-Transaction para cada Assinante.</span><span class="sxs-lookup"><span data-stu-id="e4879-176">However, to commit the transaction, you must enter a Complete-Transaction command for every subscriber.</span></span>

<span data-ttu-id="e4879-177">Para localizar o número de assinantes de uma transação, verifique a propriedade SubscriberCount do objeto de transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-177">To find the number of subscribers to a transaction, check the SubscriberCount property of the transaction object.</span></span> <span data-ttu-id="e4879-178">Por exemplo, o comando a seguir usa o cmdlet Get-Transaction para obter o valor da propriedade SubscriberCount da transação ativa:</span><span class="sxs-lookup"><span data-stu-id="e4879-178">For example, the following command uses the Get-Transaction cmdlet to get the value of the SubscriberCount property of the active transaction:</span></span>

```powershell
(Get-Transaction).SubscriberCount
```

<span data-ttu-id="e4879-179">Adicionar um assinante é o comportamento padrão porque a maioria das transações iniciadas enquanto outra transação está em andamento está relacionada à transação original.</span><span class="sxs-lookup"><span data-stu-id="e4879-179">Adding a subscriber is the default behavior because most transactions that are started while another transaction is in progress are related to the original transaction.</span></span> <span data-ttu-id="e4879-180">No modelo típico, um script que contém uma transação chama um script auxiliar que contém sua própria transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-180">In the typical model, a script that contains a transaction calls a helper script that contains its own transaction.</span></span> <span data-ttu-id="e4879-181">Como as transações estão relacionadas, elas devem ser revertidas ou confirmadas como uma unidade.</span><span class="sxs-lookup"><span data-stu-id="e4879-181">Because the transactions are related, they should be rolled back or committed as a unit.</span></span>

<span data-ttu-id="e4879-182">No entanto, você pode iniciar uma transação que é independente da transação atual usando o parâmetro independente do cmdlet Start-Transaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-182">However, you can start a transaction that is independent of the current transaction by using the Independent parameter of the Start-Transaction cmdlet.</span></span>

<span data-ttu-id="e4879-183">Quando você inicia uma transação independente, o Start-Transaction cria um novo objeto de transação e a nova transação se torna a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-183">When you start an independent transaction, Start-Transaction creates a new transaction object, and the new transaction becomes the active transaction.</span></span>
<span data-ttu-id="e4879-184">A transação independente pode ser confirmada ou revertida sem afetar a transação original.</span><span class="sxs-lookup"><span data-stu-id="e4879-184">The independent transaction can be committed or rolled back without affecting the original transaction.</span></span>

<span data-ttu-id="e4879-185">Quando a transação independente for concluída (confirmada ou revertida), a transação original se tornará a transação ativa novamente.</span><span class="sxs-lookup"><span data-stu-id="e4879-185">When the independent transaction is finished (committed or rolled back), the original transaction becomes the active transaction again.</span></span>

## <a name="changing-data"></a><span data-ttu-id="e4879-186">ALTERANDO DADOS</span><span class="sxs-lookup"><span data-stu-id="e4879-186">CHANGING DATA</span></span>

<span data-ttu-id="e4879-187">Quando você usa transações para alterar dados, os dados que são afetados pela transação não são alterados até que você confirme a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-187">When you use transactions to change data, the data that is affected by the transaction is not changed until you commit the transaction.</span></span> <span data-ttu-id="e4879-188">No entanto, os mesmos dados podem ser alterados por comandos que não fazem parte da transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-188">However, the same data can be changed by commands that are not part of the transaction.</span></span>

<span data-ttu-id="e4879-189">Tenha isso em mente ao usar transações para gerenciar dados compartilhados.</span><span class="sxs-lookup"><span data-stu-id="e4879-189">Keep this in mind when you are using transactions to manage shared data.</span></span>
<span data-ttu-id="e4879-190">Normalmente, os bancos de dados têm mecanismos que bloqueiam os dados enquanto você trabalha nele, impedindo que outros usuários e outros comandos, scripts e funções alterem a alteração.</span><span class="sxs-lookup"><span data-stu-id="e4879-190">Typically, databases have mechanisms that lock the data while you are working on it, preventing other users, and other commands, scripts, and functions, from changing it.</span></span>

<span data-ttu-id="e4879-191">No entanto, o bloqueio é um recurso do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e4879-191">However, the lock is a feature of the database.</span></span> <span data-ttu-id="e4879-192">Ele não está relacionado a transações.</span><span class="sxs-lookup"><span data-stu-id="e4879-192">It is not related to transactions.</span></span> <span data-ttu-id="e4879-193">Se você estiver trabalhando em um sistema de arquivos habilitado para transação ou em outro armazenamento de dados, os dados poderão ser alterados enquanto a transação estiver em andamento.</span><span class="sxs-lookup"><span data-stu-id="e4879-193">If you are working in a transaction-enabled file system or other data store, the data can be changed while the transaction is in progress.</span></span>

## <a name="examples"></a><span data-ttu-id="e4879-194">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e4879-194">EXAMPLES</span></span>

<span data-ttu-id="e4879-195">Os exemplos nesta seção usam o provedor de registro do PowerShell e pressupõem que você esteja familiarizado com ele.</span><span class="sxs-lookup"><span data-stu-id="e4879-195">The examples in this section use the PowerShell Registry provider and assume that you are familiar with it.</span></span> <span data-ttu-id="e4879-196">Para obter informações sobre o provedor de registro, digite "Get-Help Registry".</span><span class="sxs-lookup"><span data-stu-id="e4879-196">For information about the Registry provider, type "get-help registry".</span></span>

### <a name="example-1-committing-a-transaction"></a><span data-ttu-id="e4879-197">EXEMPLO 1: CONFIRMANDO UMA TRANSAÇÃO</span><span class="sxs-lookup"><span data-stu-id="e4879-197">EXAMPLE 1: COMMITTING A TRANSACTION</span></span>

<span data-ttu-id="e4879-198">Para criar uma transação, use o cmdlet Start-Transaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-198">To create a transaction, use the Start-Transaction cmdlet.</span></span> <span data-ttu-id="e4879-199">O comando a seguir inicia uma transação com as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="e4879-199">The following command starts a transaction with the default settings.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="e4879-200">Para incluir comandos na transação, use o parâmetro UseTransaction do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e4879-200">To include commands in the transaction, use the UseTransaction parameter of the cmdlet.</span></span> <span data-ttu-id="e4879-201">Por padrão, os comandos não são incluídos na transação,</span><span class="sxs-lookup"><span data-stu-id="e4879-201">By default, commands are not included in the transaction,</span></span>

<span data-ttu-id="e4879-202">Por exemplo, o comando a seguir, que define o local atual na chave de software da unidade HKCU:, não está incluído na transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-202">For example, the following command, which sets the current location in the Software key of the HKCU: drive, is not included in the transaction.</span></span>

```powershell
cd hkcu:\Software
```

<span data-ttu-id="e4879-203">O comando a seguir, que cria a chave MyCompany, usa o parâmetro UseTransaction do cmdlet New-Item para incluir o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-203">The following command, which creates the MyCompany key, uses the UseTransaction parameter of the New-Item cmdlet to include the command in the active transaction.</span></span>

```powershell
new-item MyCompany -UseTransaction
```

<span data-ttu-id="e4879-204">O comando retorna um objeto que representa a nova chave, mas como o comando faz parte da transação, o registro ainda não foi alterado.</span><span class="sxs-lookup"><span data-stu-id="e4879-204">The command returns an object that represents the new key, but because the command is part of the transaction, the registry is not yet changed.</span></span>

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyCompany                      {}
```

<span data-ttu-id="e4879-205">Para confirmar a transação, use o cmdlet Complete-Transaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-205">To commit the transaction, use the Complete-Transaction cmdlet.</span></span> <span data-ttu-id="e4879-206">Como ele sempre afeta a transação ativa, você não pode especificar a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-206">Because it always affects the active transaction, you cannot specify the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="e4879-207">Como resultado, a chave MyCompany é adicionada ao registro.</span><span class="sxs-lookup"><span data-stu-id="e4879-207">As a result, the MyCompany key is added to the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-2-rolling-back-a-transaction"></a><span data-ttu-id="e4879-208">EXEMPLO 2: REVERTER UMA TRANSAÇÃO</span><span class="sxs-lookup"><span data-stu-id="e4879-208">EXAMPLE 2: ROLLING BACK A TRANSACTION</span></span>

<span data-ttu-id="e4879-209">Para criar uma transação, use o cmdlet Start-Transaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-209">To create a transaction, use the Start-Transaction cmdlet.</span></span> <span data-ttu-id="e4879-210">O comando a seguir inicia uma transação com as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="e4879-210">The following command starts a transaction with the default settings.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="e4879-211">O comando a seguir, que cria a chave MyOtherCompany, usa o parâmetro UseTransaction do cmdlet New-Item para incluir o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-211">The following command, which creates the MyOtherCompany key, uses the UseTransaction parameter of the New-Item cmdlet to include the command in the active transaction.</span></span>

```powershell
new-item MyOtherCompany -UseTransaction
```

<span data-ttu-id="e4879-212">O comando retorna um objeto que representa a nova chave, mas como o comando faz parte da transação, o registro ainda não foi alterado.</span><span class="sxs-lookup"><span data-stu-id="e4879-212">The command returns an object that represents the new key, but because the command is part of the transaction, the registry is not yet changed.</span></span>

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyOtherCompany                 {}
```

<span data-ttu-id="e4879-213">Para reverter a transação, use o cmdlet Undo-Transaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-213">To roll back the transaction, use the Undo-Transaction cmdlet.</span></span> <span data-ttu-id="e4879-214">Como ele sempre afeta a transação ativa, você não especifica a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-214">Because it always affects the active transaction, you do not specify the transaction.</span></span>

```powershell
Undo-transaction
```

<span data-ttu-id="e4879-215">O resultado é que a chave MyOtherCompany não é adicionada ao registro.</span><span class="sxs-lookup"><span data-stu-id="e4879-215">The result is that the MyOtherCompany key is not added to the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-3-previewing-a-transaction"></a><span data-ttu-id="e4879-216">EXEMPLO 3: VISUALIZANDO UMA TRANSAÇÃO</span><span class="sxs-lookup"><span data-stu-id="e4879-216">EXAMPLE 3: PREVIEWING A TRANSACTION</span></span>

<span data-ttu-id="e4879-217">Normalmente, os comandos usados em uma transação alteram dados.</span><span class="sxs-lookup"><span data-stu-id="e4879-217">Typically, the commands used in a transaction change data.</span></span> <span data-ttu-id="e4879-218">No entanto, os comandos que obtêm dados também são úteis em uma transação, pois eles obtêm dados dentro da transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-218">However, the commands that get data are useful in a transaction, too, because they get data inside of the transaction.</span></span> <span data-ttu-id="e4879-219">Isso fornece uma visualização das alterações que a confirmação da transação causaria.</span><span class="sxs-lookup"><span data-stu-id="e4879-219">This provides a preview of the changes that committing the transaction would cause.</span></span>

<span data-ttu-id="e4879-220">O exemplo a seguir mostra como usar o comando Get-ChildItem (o alias é "dir") para visualizar as alterações em uma transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-220">The following example shows how to use the Get-ChildItem command (the alias is "dir") to preview the changes in a transaction.</span></span>

<span data-ttu-id="e4879-221">O comando a seguir inicia uma transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-221">The following command starts a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="e4879-222">O comando a seguir usa o cmdlet New-ItemProperty para adicionar a entrada de Registro MyKey à chave MyCompany.</span><span class="sxs-lookup"><span data-stu-id="e4879-222">The following command uses the New-ItemProperty cmdlet to add the MyKey registry entry to the MyCompany key.</span></span> <span data-ttu-id="e4879-223">O comando usa o parâmetro UseTransaction para incluir o comando na transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-223">The command uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-itemproperty -path MyCompany -Name MyKey -value 123 -UseTransaction
```

<span data-ttu-id="e4879-224">O comando retorna um objeto que representa a nova entrada do registro, mas a entrada do registro não é alterada.</span><span class="sxs-lookup"><span data-stu-id="e4879-224">The command returns an object representing the new registry entry, but the registry entry is not changed.</span></span>

```
MyKey
-----
123
```

<span data-ttu-id="e4879-225">Para obter os itens que estão atualmente no registro, use um comando Get-ChildItem ("dir") sem o parâmetro UseTransaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-225">To get the items that are currently in the registry, use a Get-ChildItem command ("dir") without the UseTransaction parameter.</span></span> <span data-ttu-id="e4879-226">O comando a seguir obtém os itens que começam com "M".</span><span class="sxs-lookup"><span data-stu-id="e4879-226">The following command gets items that begin with "M."</span></span>

```powershell
dir m*
```

<span data-ttu-id="e4879-227">O resultado mostra que nenhuma entrada ainda foi adicionada à chave MyCompany.</span><span class="sxs-lookup"><span data-stu-id="e4879-227">The result shows that no entries have yet been added to the MyCompany key.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

<span data-ttu-id="e4879-228">Para visualizar o efeito de confirmar a transação, insira um comando Get-ChildItem ("dir") com o parâmetro UseTransaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-228">To preview the effect of committing the transaction, enter a Get-ChildItem ("dir") command with the UseTransaction parameter.</span></span> <span data-ttu-id="e4879-229">Esse comando tem uma exibição dos dados de dentro da transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-229">This command has a view of the data from within the transaction.</span></span>

```powershell
dir m* -useTransaction
```

<span data-ttu-id="e4879-230">O resultado mostra que, se a transação for confirmada, a entrada MyKey será adicionada à chave MyCompany.</span><span class="sxs-lookup"><span data-stu-id="e4879-230">The result shows that, if the transaction is committed, the MyKey entry will be added to the MyCompany key.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   1 MyCompany                      {MyKey}
```

### <a name="example-4-combining-transacted-and-non-transacted-commands"></a><span data-ttu-id="e4879-231">EXEMPLO 4: COMBINANDO COMANDOS TRANSACIONADOS E NÃO TRANSACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e4879-231">EXAMPLE 4: COMBINING TRANSACTED AND NON-TRANSACTED COMMANDS</span></span>

<span data-ttu-id="e4879-232">Você pode inserir comandos não transacionados durante uma transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-232">You can enter non-transacted commands during a transaction.</span></span> <span data-ttu-id="e4879-233">Os comandos não transacionados afetam os dados imediatamente, mas eles não afetam a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-233">The non-transacted commands affect the data immediately, but they do not affect the transaction.</span></span>
<span data-ttu-id="e4879-234">O comando a seguir inicia uma transação na chave de Registro HKCU: \ Software.</span><span class="sxs-lookup"><span data-stu-id="e4879-234">The following command starts a transaction in the HKCU:\Software registry key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="e4879-235">Os próximos três comandos usam o cmdlet New-Item para adicionar chaves ao registro.</span><span class="sxs-lookup"><span data-stu-id="e4879-235">The next three commands use the New-Item cmdlet to add keys to the registry.</span></span>
<span data-ttu-id="e4879-236">O primeiro e o terceiro comandos usam o parâmetro UseTransaction para incluir os comandos na transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-236">The first and third commands use the UseTransaction parameter to include the commands in the transaction.</span></span> <span data-ttu-id="e4879-237">O segundo comando omite o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e4879-237">The second command omits the parameter.</span></span> <span data-ttu-id="e4879-238">Como o segundo comando não está incluído na transação, ele entra em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e4879-238">Because the second command is not included in the transaction, it is effective immediately.</span></span>

```powershell
new-item MyCompany1 -UseTransaction
new-item MyCompany2
new-item MyCompany3 -UseTransaction
```

<span data-ttu-id="e4879-239">Para exibir o estado atual do registro, use um comando Get-ChildItem ("dir") sem o parâmetro UseTransaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-239">To view the current state of the registry, use a Get-ChildItem ("dir") command without the UseTransaction parameter.</span></span> <span data-ttu-id="e4879-240">Este comando obtém os itens que começam com "M".</span><span class="sxs-lookup"><span data-stu-id="e4879-240">This command gets items that begin with "M."</span></span>

```powershell
dir m*
```

<span data-ttu-id="e4879-241">O resultado mostra que a chave MyCompany2 é adicionada ao registro, mas as chaves MyCompany1 e MyCompany3, que fazem parte da transação, não são adicionadas.</span><span class="sxs-lookup"><span data-stu-id="e4879-241">The result shows that the MyCompany2 key is added to the registry, but the MyCompany1 and MyCompany3 keys, which are part of the transaction, are not added.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0    0 MyCompany2                     {}
```

<span data-ttu-id="e4879-242">O comando a seguir confirma a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-242">The following command commits the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="e4879-243">Agora, as chaves que foram adicionadas como parte da transação aparecem no registro.</span><span class="sxs-lookup"><span data-stu-id="e4879-243">Now, the keys that were added as part of the transaction appear in the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
83   1 Microsoft                      {(default)}
0    0 MyCompany1                     {}
0    0 MyCompany2                     {}
0    0 MyCompany3                     {}
```

### <a name="example-5-using-automatic-rollback"></a><span data-ttu-id="e4879-244">EXEMPLO 5: USANDO A REVERSÃO AUTOMÁTICA</span><span class="sxs-lookup"><span data-stu-id="e4879-244">EXAMPLE 5: USING AUTOMATIC ROLLBACK</span></span>

<span data-ttu-id="e4879-245">Quando um comando em uma transação gera um erro de qualquer tipo, a transação é automaticamente revertida.</span><span class="sxs-lookup"><span data-stu-id="e4879-245">When a command in a transaction generates an error of any kind, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="e4879-246">Esse comportamento padrão é projetado para scripts que executam transações.</span><span class="sxs-lookup"><span data-stu-id="e4879-246">This default behavior is designed for scripts that run transactions.</span></span> <span data-ttu-id="e4879-247">Normalmente, os scripts são bem testados e incluem lógica de tratamento de erros, de modo que os erros não são esperados e devem terminar a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-247">Scripts are typically well tested and include error-handling logic, so errors are not expected and should terminate the transaction.</span></span>

<span data-ttu-id="e4879-248">O primeiro comando inicia uma transação na chave de Registro HKCU: \ Software.</span><span class="sxs-lookup"><span data-stu-id="e4879-248">The first command starts a transaction in the HKCU:\Software registry key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="e4879-249">O comando a seguir usa o cmdlet New-Item para adicionar a chave MyCompany ao registro.</span><span class="sxs-lookup"><span data-stu-id="e4879-249">The following command uses the New-Item cmdlet to add the MyCompany key to the registry.</span></span> <span data-ttu-id="e4879-250">O comando usa o parâmetro UseTransaction (o alias é "usetx") para incluir o comando na transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-250">The command uses the UseTransaction parameter (the alias is "usetx") to include the command in the transaction.</span></span>

```powershell
New-Item MyCompany -UseTX
```

<span data-ttu-id="e4879-251">Como a chave MyCompany já existe no registro, o comando falha e a transação é revertida.</span><span class="sxs-lookup"><span data-stu-id="e4879-251">Because the MyCompany key already exists in the registry, the command fails, and the transaction is rolled back.</span></span>

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

<span data-ttu-id="e4879-252">Um comando Get-Transaction confirma que a transação foi revertida e que o SubscriberCount é 0.</span><span class="sxs-lookup"><span data-stu-id="e4879-252">A Get-Transaction command confirms that the transaction has been rolled back and that the SubscriberCount is 0.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 RolledBack
```

### <a name="example-6-changing-the-rollback-preference"></a><span data-ttu-id="e4879-253">EXEMPLO 6: ALTERANDO A PREFERÊNCIA DE REVERSÃO</span><span class="sxs-lookup"><span data-stu-id="e4879-253">EXAMPLE 6: CHANGING THE ROLLBACK PREFERENCE</span></span>

<span data-ttu-id="e4879-254">Se você quiser que a transação seja mais tolerante a erros, poderá usar o parâmetro RollbackPreference de Start-Transaction para alterar a preferência.</span><span class="sxs-lookup"><span data-stu-id="e4879-254">If you want the transaction to be more error tolerant, you can use the RollbackPreference parameter of Start-Transaction to change the preference.</span></span>

<span data-ttu-id="e4879-255">O comando a seguir inicia uma transação com uma preferência de reversão de "Never".</span><span class="sxs-lookup"><span data-stu-id="e4879-255">The following command starts a transaction with a rollback preference of "Never".</span></span>

```powershell
start-transaction -rollbackpreference Never
```

<span data-ttu-id="e4879-256">Nesse caso, quando o comando falhar, a transação não será revertida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e4879-256">In this case, when the command fails, the transaction is not automatically rolled back.</span></span>

```powershell
New-Item MyCompany -UseTX
```

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

<span data-ttu-id="e4879-257">Como a transação ainda está ativa, você pode reenviar o comando como parte da transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-257">Because the transaction is still active, you can resubmit the command as part of the transaction.</span></span>

```powershell
New-Item MyOtherCompany -UseTX
```

### <a name="example-7-using-the-use-transaction-cmdlet"></a><span data-ttu-id="e4879-258">EXEMPLO 7: USANDO O CMDLET USE-TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="e4879-258">EXAMPLE 7: USING THE USE-TRANSACTION CMDLET</span></span>

<span data-ttu-id="e4879-259">O cmdlet Use-Transaction permite que você faça script direto em objetos da estrutura Microsoft .NET habilitados para transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-259">The Use-Transaction cmdlet enables you to do direct scripting against transaction-enabled Microsoft .NET Framework objects.</span></span> <span data-ttu-id="e4879-260">Use-Transaction usa um bloco de script que só pode conter comandos e expressões que usam objetos .NET Framework habilitados para transação, como instâncias da classe Microsoft. PowerShell. Commands. Management. transagiustring.</span><span class="sxs-lookup"><span data-stu-id="e4879-260">Use-Transaction takes a script block that can only contain commands and expressions that use transaction-enabled .NET Framework objects, such as instances of the Microsoft.PowerShell.Commands.Management.TransactedString class.</span></span>

<span data-ttu-id="e4879-261">O comando a seguir inicia uma transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-261">The following command starts a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="e4879-262">O comando a seguir New-Object cria uma instância da classe transacionated e salva-a na variável $t.</span><span class="sxs-lookup"><span data-stu-id="e4879-262">The following New-Object command creates an instance of the TransactedString class and saves it in the $t variable.</span></span>

```powershell
$t = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
```

<span data-ttu-id="e4879-263">O comando a seguir usa o método Append do objeto transacionastring para adicionar texto à cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e4879-263">The following command uses the Append method of the TransactedString object to add text to the string.</span></span> <span data-ttu-id="e4879-264">Como o comando não faz parte da transação, a alteração entra em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e4879-264">Because the command is not part of the transaction, the change is effective immediately.</span></span>

```powershell
$t.append("Windows")
```

<span data-ttu-id="e4879-265">O comando a seguir usa o mesmo método Append para adicionar texto, mas adiciona o texto como parte da transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-265">The following command uses the same Append method to add text, but it adds the text as part of the transaction.</span></span> <span data-ttu-id="e4879-266">O comando é colocado entre chaves e é definido como o valor do parâmetro ScriptBlock de Use-Transaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-266">The command is enclosed in braces, and it is set as the value of the ScriptBlock parameter of Use-Transaction.</span></span> <span data-ttu-id="e4879-267">O parâmetro UseTransaction (UseTx) é necessário.</span><span class="sxs-lookup"><span data-stu-id="e4879-267">The UseTransaction parameter (UseTx) is required.</span></span>

```powershell
use-transaction {$t.append(" PowerShell")} -usetx
```

<span data-ttu-id="e4879-268">Para ver o conteúdo atual da cadeia de caracteres transacionada em $t, use o método ToString do objeto transacionastring.</span><span class="sxs-lookup"><span data-stu-id="e4879-268">To see the current content of the transacted string in $t, use the ToString method of the TransactedString object.</span></span>

```powershell
$t.tostring()
```

<span data-ttu-id="e4879-269">A saída mostra que apenas as alterações não transacionadas são efetivas.</span><span class="sxs-lookup"><span data-stu-id="e4879-269">The output shows that only the non-transacted changes are effective.</span></span>

```output
Windows
```

<span data-ttu-id="e4879-270">Para ver o conteúdo atual da cadeia de caracteres transacionada em $t de dentro da transação, incorpore a expressão em um comando Use-Transaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-270">To see the current content of the transacted string in $t from within the transaction, embed the expression in a Use-Transaction command.</span></span>

```powershell
use-transaction {$s.tostring()} -usetx
```

<span data-ttu-id="e4879-271">A saída mostra o modo de exibição de transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-271">The output shows the transaction view.</span></span>

```output
PowerShell
```

<span data-ttu-id="e4879-272">O comando a seguir confirma a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-272">The following command commits the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="e4879-273">Para ver a cadeia de caracteres final:</span><span class="sxs-lookup"><span data-stu-id="e4879-273">To see the final string:</span></span>

```
$t.tostring()
PowerShell
```

### <a name="example-8-managing-multi-subscriber-transactions"></a><span data-ttu-id="e4879-274">EXEMPLO 8: GERENCIANDO TRANSAÇÕES DE VÁRIOS ASSINANTES</span><span class="sxs-lookup"><span data-stu-id="e4879-274">EXAMPLE 8: MANAGING MULTI-SUBSCRIBER TRANSACTIONS</span></span>

<span data-ttu-id="e4879-275">Quando você inicia uma transação enquanto outra transação está em andamento, o PowerShell não cria uma segunda transação por padrão.</span><span class="sxs-lookup"><span data-stu-id="e4879-275">When you start a transaction while another transaction is in progress, PowerShell does not create a second transaction by default.</span></span> <span data-ttu-id="e4879-276">Em vez disso, ele adiciona um assinante à transação atual.</span><span class="sxs-lookup"><span data-stu-id="e4879-276">Instead, it adds a subscriber to the current transaction.</span></span>

<span data-ttu-id="e4879-277">Este exemplo mostra como exibir e gerenciar uma transação de vários assinantes.</span><span class="sxs-lookup"><span data-stu-id="e4879-277">This example shows how to view and manage a multi-subscriber transaction.</span></span>

<span data-ttu-id="e4879-278">Comece iniciando uma transação na chave HKCU: \ Software.</span><span class="sxs-lookup"><span data-stu-id="e4879-278">Begin by starting a transaction in the HKCU:\Software key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="e4879-279">O comando a seguir usa o comando Get-Transaction para obter a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-279">The following command uses the Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="e4879-280">O resultado mostra o objeto que representa a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-280">The result shows the object that represents the active transaction.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="e4879-281">O comando a seguir adiciona a chave MyCompany ao registro.</span><span class="sxs-lookup"><span data-stu-id="e4879-281">The following command adds the MyCompany key to the registry.</span></span> <span data-ttu-id="e4879-282">O comando usa o parâmetro UseTransaction para incluir o comando na transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-282">The command uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-item MyCompany -UseTransaction
```

<span data-ttu-id="e4879-283">O comando a seguir usa o comando Start-Transaction para iniciar uma transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-283">The following command uses the Start-Transaction command to start a transaction.</span></span> <span data-ttu-id="e4879-284">Embora esse comando seja digitado no prompt de comando, esse cenário é mais provável de acontecer quando você executa um script que contém uma transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-284">Although this command is typed at the command prompt, this scenario is more likely to happen when you run a script that contains a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="e4879-285">Um comando Get-Transaction mostra que a contagem de assinantes no objeto de transação é incrementada.</span><span class="sxs-lookup"><span data-stu-id="e4879-285">A Get-Transaction command shows that the subscriber count on the transaction object is incremented.</span></span> <span data-ttu-id="e4879-286">O valor agora é 2.</span><span class="sxs-lookup"><span data-stu-id="e4879-286">The value is now 2.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

<span data-ttu-id="e4879-287">O comando a seguir usa o cmdlet New-ItemProperty para adicionar a entrada do Registro MyKey à chave MyCompany.</span><span class="sxs-lookup"><span data-stu-id="e4879-287">The next command uses the New-ItemProperty cmdlet to add the MyKey registry entry to the MyCompany key.</span></span> <span data-ttu-id="e4879-288">Ele usa o parâmetro UseTransaction para incluir o comando na transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-288">It uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-itemproperty -path MyCompany -name MyKey -UseTransaction
```

<span data-ttu-id="e4879-289">A chave MyCompany não existe no registro, mas esse comando é executado com sucesso porque os dois comandos fazem parte da mesma transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-289">The MyCompany key does not exist in the registry, but this command succeeds because the two commands are part of the same transaction.</span></span>

<span data-ttu-id="e4879-290">O comando a seguir confirma a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-290">The following command commits the transaction.</span></span> <span data-ttu-id="e4879-291">Se reverter a transação, a transação seria revertida para todos os assinantes.</span><span class="sxs-lookup"><span data-stu-id="e4879-291">If it rolled back the transaction, the transaction would be rolled back for all the subscribers.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="e4879-292">Um comando Get-Transaction mostra que a contagem de assinantes no objeto de transação é 1, mas o valor de status ainda está ativo (não confirmado).</span><span class="sxs-lookup"><span data-stu-id="e4879-292">A Get-Transaction command shows that the subscriber count on the transaction object is 1, but the value of Status is still Active (not Committed).</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="e4879-293">Para concluir a confirmação da transação, insira um segundo comando Complete-Transaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-293">To finish committing the transaction, enter a second Complete- Transaction command.</span></span> <span data-ttu-id="e4879-294">Para confirmar uma transação de vários assinantes, você deve inserir um comando Complete-Transaction para cada comando Start-Transaction.</span><span class="sxs-lookup"><span data-stu-id="e4879-294">To commit a multi-subscriber transaction, you must enter one Complete-Transaction command for each Start-Transaction command.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="e4879-295">Outro comando Get-Transaction mostra que a transação foi confirmada.</span><span class="sxs-lookup"><span data-stu-id="e4879-295">Another Get-Transaction command shows that the transaction has been committed.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 Committed
```

### <a name="example-9-managing-independent-transactions"></a><span data-ttu-id="e4879-296">EXEMPLO 9: GERENCIANDO TRANSAÇÕES INDEPENDENTES</span><span class="sxs-lookup"><span data-stu-id="e4879-296">EXAMPLE 9: MANAGING INDEPENDENT TRANSACTIONS</span></span>

<span data-ttu-id="e4879-297">Ao iniciar uma transação enquanto outra transação está em andamento, você pode usar o parâmetro independente de Start-Transaction para tornar a nova transação independente da transação original.</span><span class="sxs-lookup"><span data-stu-id="e4879-297">When you start a transaction while another transaction is in progress, you can use the Independent parameter of Start-Transaction to make the new transaction independent of the original transaction.</span></span>

<span data-ttu-id="e4879-298">Quando você faz isso, Start-Transaction cria um novo objeto de transação e torna a nova transação a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-298">When you do, Start-Transaction creates a new transaction object and makes the new transaction the active transaction.</span></span>

<span data-ttu-id="e4879-299">Comece iniciando uma transação na chave HKCU: \\ software.</span><span class="sxs-lookup"><span data-stu-id="e4879-299">Begin by starting a transaction in the HKCU:\\Software key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="e4879-300">O comando a seguir usa o comando Get-Transaction para obter a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-300">The following command uses the Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="e4879-301">O resultado mostra o objeto que representa a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-301">The result shows the object that represents the active transaction.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="e4879-302">O comando a seguir adiciona a chave do Registro MyCompany como parte da transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-302">The following command adds the MyCompany registry key as part of the transaction.</span></span> <span data-ttu-id="e4879-303">Ele usa o parâmetro UseTransaction (UseTx) para incluir o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-303">It uses the UseTransaction parameter (UseTx) to include the command in the active transaction.</span></span>

```powershell
new-item MyCompany -use
```

<span data-ttu-id="e4879-304">O comando a seguir inicia uma nova transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-304">The following command starts a new transaction.</span></span> <span data-ttu-id="e4879-305">O comando usa o parâmetro independente para indicar que essa transação não é um assinante para a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-305">The command uses the Independent parameter to indicate that this transaction is not a subscriber to the active transaction.</span></span>

```powershell
start-transaction -independent
```

<span data-ttu-id="e4879-306">Quando você cria uma transação independente, a nova transação (criada mais recentemente) torna-se a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-306">When you create an independent transaction, the new (most-recently created) transaction becomes the active transaction.</span></span> <span data-ttu-id="e4879-307">Você pode usar um comando Get-Transaction para obter a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-307">You can use a Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="e4879-308">Observe que o SubscriberCount da transação é 1, indicando que não há outros assinantes e que a transação é nova.</span><span class="sxs-lookup"><span data-stu-id="e4879-308">Note that the SubscriberCount of the transaction is 1, indicating that there are no other subscribers and that the transaction is new.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="e4879-309">A nova transação deve ser concluída (confirmada ou revertida) antes que você possa gerenciar a transação original.</span><span class="sxs-lookup"><span data-stu-id="e4879-309">The new transaction must be finished (either committed or rolled back) before you can manage the original transaction.</span></span>

<span data-ttu-id="e4879-310">O comando a seguir adiciona a chave MyOtherCompany ao registro.</span><span class="sxs-lookup"><span data-stu-id="e4879-310">The following command adds the MyOtherCompany key to the registry.</span></span> <span data-ttu-id="e4879-311">Ele usa o parâmetro UseTransaction (UseTx) para incluir o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-311">It uses the UseTransaction parameter (UseTx) to include the command in the active transaction.</span></span>

```powershell
new-item MyOtherCompany -usetx
```

<span data-ttu-id="e4879-312">Agora, reverta a transação.</span><span class="sxs-lookup"><span data-stu-id="e4879-312">Now, roll back the transaction.</span></span> <span data-ttu-id="e4879-313">Se houver uma única transação com dois assinantes, reverter a transação reverteria toda a transação para todos os assinantes.</span><span class="sxs-lookup"><span data-stu-id="e4879-313">If there were a single transaction with two subscribers, rolling back the transaction would roll back the entire transaction for all the subscribers.</span></span>

<span data-ttu-id="e4879-314">No entanto, como essas transações são independentes, a reversão da transação mais recente cancela as alterações do registro e torna a transação original a Transaction ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-314">However, because these transactions are independent, rolling back the newest transaction cancels the registry changes and makes the original transaction the active transaction.</span></span>

```powershell
undo-transaction
```

<span data-ttu-id="e4879-315">Um comando Get-Transaction confirma que a transação original ainda está ativa na sessão.</span><span class="sxs-lookup"><span data-stu-id="e4879-315">A Get-Transaction command confirms that the original transaction is still active in the session.</span></span>

```powershell
get-transaction
```

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="e4879-316">O comando a seguir confirma a transação ativa.</span><span class="sxs-lookup"><span data-stu-id="e4879-316">The following command commits the active transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="e4879-317">Um comando Get-ChildItem mostra que o registro foi alterado.</span><span class="sxs-lookup"><span data-stu-id="e4879-317">A Get-ChildItem command shows that the registry has been changed.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

## <a name="see-also"></a><span data-ttu-id="e4879-318">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="e4879-318">SEE ALSO</span></span>

[<span data-ttu-id="e4879-319">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="e4879-319">Start-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Start-Transaction)

[<span data-ttu-id="e4879-320">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="e4879-320">Get-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Get-Transaction)

[<span data-ttu-id="e4879-321">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="e4879-321">Complete-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Complete-Transaction)

[<span data-ttu-id="e4879-322">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="e4879-322">Undo-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Undo-Transaction)

[<span data-ttu-id="e4879-323">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="e4879-323">Use-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Use-Transaction)

[<span data-ttu-id="e4879-324">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="e4879-324">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

[<span data-ttu-id="e4879-325">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e4879-325">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

[<span data-ttu-id="e4879-326">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e4879-326">about_Providers</span></span>](about_Providers.md)
