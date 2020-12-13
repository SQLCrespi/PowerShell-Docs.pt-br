---
ms.date: 09/13/2016
ms.topic: reference
title: Tutorial de GetProc
description: Tutorial de GetProc
ms.openlocfilehash: 9379e791dd5361fcf5b79061bf0a601ebeb84f42
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652781"
---
# <a name="getproc-tutorial"></a><span data-ttu-id="f1e5a-103">Tutorial de GetProc</span><span class="sxs-lookup"><span data-stu-id="f1e5a-103">GetProc Tutorial</span></span>

<span data-ttu-id="f1e5a-104">Esta seção fornece um tutorial para criar um cmdlet Get-Proc que é muito semelhante ao cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) fornecido pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-104">This section provides a tutorial for creating a Get-Proc cmdlet that is very similar to the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="f1e5a-105">Este tutorial fornece fragmentos de código que ilustram como os cmdlets são implementados e uma explicação do código.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-105">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="f1e5a-106">Tópicos deste tutorial</span><span class="sxs-lookup"><span data-stu-id="f1e5a-106">Topics in this Tutorial</span></span>

<span data-ttu-id="f1e5a-107">Os tópicos deste tutorial foram criados para serem lidos sequencialmente, com cada tópico sobre o que foi discutido no tópico anterior.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-107">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="f1e5a-108">[Criando um cmdlet sem parâmetros](./creating-a-cmdlet-without-parameters.md) Esta seção descreve como criar um cmdlet que recupera informações do computador local sem o uso de parâmetros e, em seguida, grava as informações no pipeline.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-108">[Creating a Cmdlet without Parameters](./creating-a-cmdlet-without-parameters.md) This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="f1e5a-109">[Adicionando parâmetros que processam Command-Line entrada](./adding-parameters-that-process-command-line-input.md) Esta seção descreve como adicionar um parâmetro ao cmdlet Get-Proc para que o cmdlet possa processar a entrada com base em objetos explícitos passados para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-109">[Adding Parameters that Process Command-Line Input](./adding-parameters-that-process-command-line-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process input based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="f1e5a-110">A implementação descrita aqui recupera processos com base em seu nome e, em seguida, grava as informações no pipeline.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-110">The implementation described here retrieves processes based on their name, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="f1e5a-111">[Adicionando parâmetros que processam a entrada do pipeline](./adding-parameters-that-process-pipeline-input.md) Esta seção descreve como adicionar um parâmetro ao cmdlet Get-Proc para que o cmdlet possa processar objetos passados para ele por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-111">[Adding Parameters that Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process objects passed to it through the pipeline.</span></span> <span data-ttu-id="f1e5a-112">O cmdlet de implementação descrito aqui recupera processos com base em objetos passados para o cmdlet e, em seguida, grava as informações no pipeline.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-112">The implementation cmdlet described here retrieves processes based on objects passed to the cmdlet, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="f1e5a-113">[Adicionando relatórios de erros não finalizados ao seu cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) Esta seção descreve como adicionar relatórios de erros não finalizados a um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-113">[Adding Nonterminating Error Reporting to Your Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) This section describes how to add nonterminating error reporting to a cmdlet.</span></span> <span data-ttu-id="f1e5a-114">A implementação descrita aqui detecta erros de não encerramento que ocorrem durante o processamento de entrada e grava um registro de erro no fluxo de erros.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-114">The implementation described here detects nonterminating errors that occur when processing input, and writes an error record to the error stream.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1e5a-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1e5a-115">See Also</span></span>

[<span data-ttu-id="f1e5a-116">Criar um cmdlet sem parâmetros</span><span class="sxs-lookup"><span data-stu-id="f1e5a-116">Creating a Cmdlet without Parameters</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="f1e5a-117">Adicionando parâmetros que processam Command-Line entrada</span><span class="sxs-lookup"><span data-stu-id="f1e5a-117">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="f1e5a-118">Adicionar parâmetros que processam a entrada de pipeline</span><span class="sxs-lookup"><span data-stu-id="f1e5a-118">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="f1e5a-119">Adicionando relatórios de erros não finalizados ao seu cmdlet</span><span class="sxs-lookup"><span data-stu-id="f1e5a-119">Adding Nonterminating Error Reporting to Your Cmdlet</span></span>](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[<span data-ttu-id="f1e5a-120">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1e5a-120">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
