---
title: Conceitos de cmdlet do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b3ef3f4-c626-4679-884f-406a37412b3e
caps.latest.revision: 16
ms.openlocfilehash: 2f84c57da7429462c69b2a020d9f8ac04f8d0f35
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369115"
---
# <a name="windows-powershell-cmdlet-concepts"></a><span data-ttu-id="db99a-102">Conceitos de cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="db99a-102">Windows PowerShell Cmdlet Concepts</span></span>

<span data-ttu-id="db99a-103">Esta seção descreve como funcionam os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="db99a-103">This section describes how cmdlets work.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="db99a-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="db99a-104">In This Section</span></span>

<span data-ttu-id="db99a-105">Esta seção inclui os seguintes tópicos.</span><span class="sxs-lookup"><span data-stu-id="db99a-105">This section includes the following topics.</span></span>

<span data-ttu-id="db99a-106">[Diretrizes de desenvolvimento de cmdlet](./cmdlet-development-guidelines.md) Este tópico fornece diretrizes de desenvolvimento que podem ser usadas para produzir cmdlets bem formados.</span><span class="sxs-lookup"><span data-stu-id="db99a-106">[Cmdlet Development Guidelines](./cmdlet-development-guidelines.md) This topic provides development guidelines that can be used to produce well-formed cmdlets.</span></span>

<span data-ttu-id="db99a-107">[Declaração de classe de cmdlet](./cmdlet-class-declaration.md) Este tópico descreve a declaração de classe de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="db99a-107">[Cmdlet Class Declaration](./cmdlet-class-declaration.md) This topic describes cmdlet class declaration.</span></span>

<span data-ttu-id="db99a-108">[Verbos aprovados para comandos do Windows PowerShell](./approved-verbs-for-windows-powershell-commands.md) Este tópico lista os verbos de cmdlet predefinidos que você pode usar ao declarar uma classe de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="db99a-108">[Approved Verbs for Windows PowerShell Commands](./approved-verbs-for-windows-powershell-commands.md) This topic lists the predefined cmdlet verbs that you can use when you declare a cmdlet class.</span></span>

<span data-ttu-id="db99a-109">[Métodos de processamento de entrada de cmdlet](./cmdlet-input-processing-methods.md) Este tópico descreve os métodos que permitem que um cmdlet execute operações de pré-processamento, operações de processamento de entrada e operações de pós-processamento.</span><span class="sxs-lookup"><span data-stu-id="db99a-109">[Cmdlet Input Processing Methods](./cmdlet-input-processing-methods.md) This topic describes the methods that allow a cmdlet to perform preprocessing operations, input processing operations, and post processing operations.</span></span>

<span data-ttu-id="db99a-110">[Parâmetros de cmdlet](./cmdlet-parameters.md) Esta seção descreve os diferentes tipos de parâmetros que você pode adicionar a cmdlets.</span><span class="sxs-lookup"><span data-stu-id="db99a-110">[Cmdlet Parameters](./cmdlet-parameters.md) This section describes the different types of parameters that you can add to cmdlets.</span></span>

<span data-ttu-id="db99a-111">[Atributos de cmdlet](./cmdlet-attributes.md) Esta seção descreve os atributos que são usados para declarar .NET Framework classes como cmdlets, declarar campos como parâmetros de cmdlet e declarar regras de validação de entrada para parâmetros.</span><span class="sxs-lookup"><span data-stu-id="db99a-111">[Cmdlet Attributes](./cmdlet-attributes.md) This section describes the attributes that are used to declare .NET Framework classes as cmdlets, to declare fields as cmdlet parameters, and to declare input validation rules for parameters.</span></span>

<span data-ttu-id="db99a-112">[Aliases de cmdlet](./cmdlet-aliases.md) Este tópico descreve os aliases de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="db99a-112">[Cmdlet Aliases](./cmdlet-aliases.md) This topic describes cmdlet aliases.</span></span>

<span data-ttu-id="db99a-113">[Saída do cmdlet](./cmdlet-output.md) Esta seção descreve o tipo de saída que os cmdlets podem retornar e como definir e exibir os objetos que são retornados por cmdlets.</span><span class="sxs-lookup"><span data-stu-id="db99a-113">[Cmdlet Output](./cmdlet-output.md) This section describes the type of output that cmdlets can return and how to define and display the objects that are returned by cmdlets.</span></span>

<span data-ttu-id="db99a-114">[Registrando cmdlets](./modules-and-snap-ins.md) Esta seção descreve como registrar cmdlets usando módulos e snap-ins.</span><span class="sxs-lookup"><span data-stu-id="db99a-114">[Registering Cmdlets](./modules-and-snap-ins.md) This section describes how to register cmdlets by using modules and snap-ins.</span></span>

<span data-ttu-id="db99a-115">[Solicitando confirmação](./requesting-confirmation-from-cmdlets.md) Esta seção descreve como os cmdlets solicitam a confirmação de um usuário antes que eles façam uma alteração no sistema.</span><span class="sxs-lookup"><span data-stu-id="db99a-115">[Requesting Confirmation](./requesting-confirmation-from-cmdlets.md) This section describes how cmdlets request confirmation from a user before they make a change to the system.</span></span>

<span data-ttu-id="db99a-116">[Relatório de erros do Windows PowerShell](./error-reporting-concepts.md) Esta seção descreve como os cmdlets relatam erros de encerramento e erros de não encerramento e descreve como interpretar registros de erro.</span><span class="sxs-lookup"><span data-stu-id="db99a-116">[Windows PowerShell Error Reporting](./error-reporting-concepts.md) This section describes how cmdlets report terminating errors and non-terminating errors, and it describes how to interpret error records.</span></span>

<span data-ttu-id="db99a-117">[Trabalhos em segundo plano](./background-jobs.md) Este tópico descreve como os cmdlets podem executar seu trabalho em trabalhos em segundo plano que não interferem nos comandos que estão sendo executados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="db99a-117">[Background Jobs](./background-jobs.md) This topic describes how cmdlets can perform their work within background jobs that do not interfere with the commands that are executing in the current session.</span></span>

<span data-ttu-id="db99a-118">[Invocando cmdlets e scripts dentro de um cmdlet](./invoking-cmdlets-and-scripts-within-a-cmdlet.md) Este tópico descreve como os cmdlets podem invocar outros cmdlets e scripts de dentro de seus métodos de processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="db99a-118">[Invoking Cmdlets and Scripts Within a Cmdlet](./invoking-cmdlets-and-scripts-within-a-cmdlet.md) This topic describes how cmdlets can invoke other cmdlets and scripts from within their input processing methods.</span></span>

<span data-ttu-id="db99a-119">[Conjuntos de cmdlets](./cmdlet-sets.md) Este tópico descreve o uso de classes base para criar conjuntos de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="db99a-119">[Cmdlet Sets](./cmdlet-sets.md) This topic describes using base classes to create sets of cmdlets.</span></span>

<span data-ttu-id="db99a-120">[Estado de sessão do Windows PowerShell](./windows-powershell-session-state.md) Este tópico descreve o estado de sessão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db99a-120">[Windows PowerShell Session State](./windows-powershell-session-state.md) This topic describes Windows PowerShell session state.</span></span>
