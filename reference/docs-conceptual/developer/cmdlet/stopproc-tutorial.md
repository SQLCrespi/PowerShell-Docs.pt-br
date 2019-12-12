---
title: Tutorial do StopProc | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a142aeb6-9c11-44a0-b34f-1f9470fa347b
caps.latest.revision: 5
ms.openlocfilehash: 27c8e2c7525aba38e69e50b2b7fd3b18b8e54989
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369405"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="8f69a-102">Tutorial de StopProc</span><span class="sxs-lookup"><span data-stu-id="8f69a-102">StopProc Tutorial</span></span>

<span data-ttu-id="8f69a-103">Esta seção fornece um tutorial para criar o cmdlet Stop-proc, que é muito semelhante ao cmdlet [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) fornecido pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f69a-103">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="8f69a-104">Este tutorial fornece fragmentos de código que ilustram como os cmdlets são implementados e uma explicação do código.</span><span class="sxs-lookup"><span data-stu-id="8f69a-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="8f69a-105">Tópicos deste tutorial</span><span class="sxs-lookup"><span data-stu-id="8f69a-105">Topics in this Tutorial</span></span>

<span data-ttu-id="8f69a-106">Os tópicos deste tutorial foram criados para serem lidos sequencialmente, com cada tópico sobre o que foi discutido no tópico anterior.</span><span class="sxs-lookup"><span data-stu-id="8f69a-106">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="8f69a-107">[Criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md) Esta seção descreve como criar um cmdlet que dá suporte a modificações do sistema, como interromper um processo em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="8f69a-107">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="8f69a-108">[Adicionando mensagens de usuário ao seu cmdlet](./adding-user-messages-to-your-cmdlet.md) Esta seção descreve como adicionar a capacidade de gravar mensagens de usuário, depurar mensagens, mensagens de aviso e informações de progresso para seu cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f69a-108">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="8f69a-109">[Adicionando aliases, expansão de curinga e ajuda para parâmetros de cmdlet](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) Esta seção descreve como criar um cmdlet que dá suporte a aliases de parâmetro, ajuda e expansão de curinga.</span><span class="sxs-lookup"><span data-stu-id="8f69a-109">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="8f69a-110">[Adicionando conjuntos de parâmetros a cmdlets](./adding-parameter-sets-to-a-cmdlet.md) Esta seção descreve como adicionar conjuntos de parâmetros a um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f69a-110">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="8f69a-111">Os conjuntos de parâmetros permitem que o cmdlet opere de forma diferente com base em quais parâmetros são especificados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="8f69a-111">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f69a-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f69a-112">See Also</span></span>

[<span data-ttu-id="8f69a-113">Criando um cmdlet que modifica o sistema</span><span class="sxs-lookup"><span data-stu-id="8f69a-113">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="8f69a-114">Adicionando mensagens de usuário ao seu cmdlet</span><span class="sxs-lookup"><span data-stu-id="8f69a-114">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="8f69a-115">Adicionando aliases, expansão de curinga e ajuda para parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="8f69a-115">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="8f69a-116">Adicionando conjuntos de parâmetros a cmdlets</span><span class="sxs-lookup"><span data-stu-id="8f69a-116">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="8f69a-117">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f69a-117">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
