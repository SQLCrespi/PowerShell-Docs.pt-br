---
title: Tutorial do getproc | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4663905f-560a-4e39-9b03-6db2c315c322
caps.latest.revision: 6
ms.openlocfilehash: bbd07a0d0abd30742b7e02482adedae3af43aca4
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364435"
---
# <a name="getproc-tutorial"></a><span data-ttu-id="25f5b-102">Tutorial de GetProc</span><span class="sxs-lookup"><span data-stu-id="25f5b-102">GetProc Tutorial</span></span>

<span data-ttu-id="25f5b-103">Esta seção fornece um tutorial para a criação de um cmdlet Get-proc que é muito semelhante ao cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) fornecido pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25f5b-103">This section provides a tutorial for creating a Get-Proc cmdlet that is very similar to the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="25f5b-104">Este tutorial fornece fragmentos de código que ilustram como os cmdlets são implementados e uma explicação do código.</span><span class="sxs-lookup"><span data-stu-id="25f5b-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="25f5b-105">Tópicos deste tutorial</span><span class="sxs-lookup"><span data-stu-id="25f5b-105">Topics in this Tutorial</span></span>

<span data-ttu-id="25f5b-106">Os tópicos deste tutorial foram criados para serem lidos sequencialmente, com cada tópico sobre o que foi discutido no tópico anterior.</span><span class="sxs-lookup"><span data-stu-id="25f5b-106">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="25f5b-107">[Criando um cmdlet sem parâmetros](./creating-a-cmdlet-without-parameters.md) Esta seção descreve como criar um cmdlet que recupera informações do computador local sem o uso de parâmetros e, em seguida, grava as informações no pipeline.</span><span class="sxs-lookup"><span data-stu-id="25f5b-107">[Creating a Cmdlet without Parameters](./creating-a-cmdlet-without-parameters.md) This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="25f5b-108">[Adicionando parâmetros que processam a entrada de linha de comando](./adding-parameters-that-process-command-line-input.md) Esta seção descreve como adicionar um parâmetro ao cmdlet Get-proc para que o cmdlet possa processar a entrada com base em objetos explícitos passados para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25f5b-108">[Adding Parameters that Process Command-Line Input](./adding-parameters-that-process-command-line-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process input based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="25f5b-109">A implementação descrita aqui recupera processos com base em seu nome e, em seguida, grava as informações no pipeline.</span><span class="sxs-lookup"><span data-stu-id="25f5b-109">The implementation described here retrieves processes based on their name, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="25f5b-110">[Adicionando parâmetros que processam a entrada do pipeline](./adding-parameters-that-process-pipeline-input.md) Esta seção descreve como adicionar um parâmetro ao cmdlet Get-proc para que o cmdlet possa processar objetos passados para ele por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="25f5b-110">[Adding Parameters that Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process objects passed to it through the pipeline.</span></span> <span data-ttu-id="25f5b-111">O cmdlet de implementação descrito aqui recupera processos com base em objetos passados para o cmdlet e, em seguida, grava as informações no pipeline.</span><span class="sxs-lookup"><span data-stu-id="25f5b-111">The implementation cmdlet described here retrieves processes based on objects passed to the cmdlet, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="25f5b-112">[Adicionando relatórios de erros não finalizados ao seu cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) Esta seção descreve como adicionar relatórios de erros não finalizados a um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25f5b-112">[Adding Nonterminating Error Reporting to Your Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) This section describes how to add nonterminating error reporting to a cmdlet.</span></span> <span data-ttu-id="25f5b-113">A implementação descrita aqui detecta erros de não encerramento que ocorrem durante o processamento de entrada e grava um registro de erro no fluxo de erros.</span><span class="sxs-lookup"><span data-stu-id="25f5b-113">The implementation described here detects nonterminating errors that occur when processing input, and writes an error record to the error stream.</span></span>

## <a name="see-also"></a><span data-ttu-id="25f5b-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25f5b-114">See Also</span></span>

[<span data-ttu-id="25f5b-115">Criando um cmdlet sem parâmetros</span><span class="sxs-lookup"><span data-stu-id="25f5b-115">Creating a Cmdlet without Parameters</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="25f5b-116">Adicionando parâmetros que processam a entrada de linha de comando</span><span class="sxs-lookup"><span data-stu-id="25f5b-116">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="25f5b-117">Adicionando parâmetros que processam a entrada do pipeline</span><span class="sxs-lookup"><span data-stu-id="25f5b-117">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="25f5b-118">Adicionando relatórios de erros não finalizados ao seu cmdlet</span><span class="sxs-lookup"><span data-stu-id="25f5b-118">Adding Nonterminating Error Reporting to Your Cmdlet</span></span>](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[<span data-ttu-id="25f5b-119">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="25f5b-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
