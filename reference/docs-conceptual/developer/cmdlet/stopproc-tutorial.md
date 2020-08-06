---
title: Tutorial do StopProc | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e298c729b7ac59141638052d19b95ab77aa25cd6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786468"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="331f4-102">Tutorial de StopProc</span><span class="sxs-lookup"><span data-stu-id="331f4-102">StopProc Tutorial</span></span>

<span data-ttu-id="331f4-103">Esta seção fornece um tutorial para criar o cmdlet Stop-proc, que é muito semelhante ao cmdlet [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) fornecido pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="331f4-103">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="331f4-104">Este tutorial fornece fragmentos de código que ilustram como os cmdlets são implementados e uma explicação do código.</span><span class="sxs-lookup"><span data-stu-id="331f4-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="331f4-105">Tópicos deste tutorial</span><span class="sxs-lookup"><span data-stu-id="331f4-105">Topics in this Tutorial</span></span>

<span data-ttu-id="331f4-106">Os tópicos deste tutorial foram criados para serem lidos sequencialmente, com cada tópico sobre o que foi discutido no tópico anterior.</span><span class="sxs-lookup"><span data-stu-id="331f4-106">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="331f4-107">[Criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md) Esta seção descreve como criar um cmdlet que dá suporte a modificações do sistema, como interromper um processo em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="331f4-107">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="331f4-108">[Adicionando mensagens de usuário ao seu cmdlet](./adding-user-messages-to-your-cmdlet.md) Esta seção descreve como adicionar a capacidade de gravar mensagens de usuário, depurar mensagens, mensagens de aviso e informações de progresso para seu cmdlet.</span><span class="sxs-lookup"><span data-stu-id="331f4-108">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="331f4-109">[Adicionando aliases, expansão de curinga e ajuda para parâmetros de cmdlet](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) Esta seção descreve como criar um cmdlet que dá suporte a aliases de parâmetro, ajuda e expansão de curinga.</span><span class="sxs-lookup"><span data-stu-id="331f4-109">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="331f4-110">[Adicionando conjuntos de parâmetros a cmdlets](./adding-parameter-sets-to-a-cmdlet.md) Esta seção descreve como adicionar conjuntos de parâmetros a um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="331f4-110">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="331f4-111">Os conjuntos de parâmetros permitem que o cmdlet opere de forma diferente com base em quais parâmetros são especificados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="331f4-111">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="331f4-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="331f4-112">See Also</span></span>

[<span data-ttu-id="331f4-113">Criar um cmdlet que modifica o sistema</span><span class="sxs-lookup"><span data-stu-id="331f4-113">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="331f4-114">Adicionar mensagens de usuário para o cmdlet</span><span class="sxs-lookup"><span data-stu-id="331f4-114">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="331f4-115">Adicionar aliases, expansão de curinga e ajuda a parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="331f4-115">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="331f4-116">Adicionando conjuntos de parâmetros a cmdlets</span><span class="sxs-lookup"><span data-stu-id="331f4-116">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="331f4-117">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="331f4-117">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
