---
ms.date: 09/13/2016
ms.topic: reference
title: Tutorial de StopProc
description: Tutorial de StopProc
ms.openlocfilehash: 95229ee3c4905d295bd6991fe8ccf8c9840c3cdd
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646425"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="38868-103">Tutorial de StopProc</span><span class="sxs-lookup"><span data-stu-id="38868-103">StopProc Tutorial</span></span>

<span data-ttu-id="38868-104">Esta seção fornece um tutorial para criar o cmdlet Stop-Proc, que é muito semelhante ao cmdlet [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) fornecido pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38868-104">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="38868-105">Este tutorial fornece fragmentos de código que ilustram como os cmdlets são implementados e uma explicação do código.</span><span class="sxs-lookup"><span data-stu-id="38868-105">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="38868-106">Tópicos deste tutorial</span><span class="sxs-lookup"><span data-stu-id="38868-106">Topics in this Tutorial</span></span>

<span data-ttu-id="38868-107">Os tópicos deste tutorial foram criados para serem lidos sequencialmente, com cada tópico sobre o que foi discutido no tópico anterior.</span><span class="sxs-lookup"><span data-stu-id="38868-107">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="38868-108">[Criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md) Esta seção descreve como criar um cmdlet que dá suporte a modificações do sistema, como interromper um processo em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="38868-108">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="38868-109">[Adicionando mensagens de usuário ao seu cmdlet](./adding-user-messages-to-your-cmdlet.md) Esta seção descreve como adicionar a capacidade de gravar mensagens de usuário, depurar mensagens, mensagens de aviso e informações de progresso para seu cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38868-109">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="38868-110">[Adicionando aliases, expansão de curinga e ajuda para parâmetros de cmdlet](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) Esta seção descreve como criar um cmdlet que dá suporte a aliases de parâmetro, ajuda e expansão de curinga.</span><span class="sxs-lookup"><span data-stu-id="38868-110">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="38868-111">[Adicionando conjuntos de parâmetros a cmdlets](./adding-parameter-sets-to-a-cmdlet.md) Esta seção descreve como adicionar conjuntos de parâmetros a um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38868-111">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="38868-112">Os conjuntos de parâmetros permitem que o cmdlet opere de forma diferente com base em quais parâmetros são especificados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="38868-112">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="38868-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38868-113">See Also</span></span>

[<span data-ttu-id="38868-114">Criar um cmdlet que modifica o sistema</span><span class="sxs-lookup"><span data-stu-id="38868-114">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="38868-115">Adicionar mensagens de usuário para o cmdlet</span><span class="sxs-lookup"><span data-stu-id="38868-115">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="38868-116">Adicionar aliases, expansão de curinga e ajuda a parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="38868-116">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="38868-117">Adicionando conjuntos de parâmetros a cmdlets</span><span class="sxs-lookup"><span data-stu-id="38868-117">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="38868-118">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38868-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
