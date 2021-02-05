---
title: Appendix A - Help Syntax (Apêndice A – Sintaxe de Ajuda)
description: Este artigo explica como ler e entender a sintaxe de um cmdlet, conforme apresentado por Get-Help.
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: b8fe218f2a9af1ad1ee6b88740414ecede0194bd
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "99597995"
---
# <a name="appendix-a---help-syntax"></a><span data-ttu-id="1d53b-103">Appendix A - Help Syntax (Apêndice A – Sintaxe de Ajuda)</span><span class="sxs-lookup"><span data-stu-id="1d53b-103">Appendix A - Help Syntax</span></span>

<span data-ttu-id="1d53b-104">O exemplo a seguir mostra a seção **SINTAXE** da Ajuda para o cmdlet `Get-EventLog`.</span><span class="sxs-lookup"><span data-stu-id="1d53b-104">The following example shows the **SYNTAX** section of the help for the `Get-EventLog` cmdlet.</span></span>

```powershell
help Get-EventLog
```

```Output
NAME
    Get-EventLog

SYNOPSIS
    Gets the events in an event log, or a list of the event logs, on the local or remote
    computers.


SYNTAX
    Get-EventLog [-LogName] <String> [[-InstanceId] <Int64[]>] [-After <DateTime>]
    [-AsBaseObject] [-Before <DateTime>] [-ComputerName <String[]>] [-EntryType {Error |
    Information | FailureAudit | SuccessAudit | Warning}] [-Index <Int32[]>] [-Message
    <String>] [-Newest <Int32>] [-Source <String[]>] [-UserName <String[]>]
    [<CommonParameters>]

    Get-EventLog [-AsString] [-ComputerName <String[]>] [-List] [<CommonParameters>]
```

<span data-ttu-id="1d53b-105">Somente a parte relevante da Ajuda é mostrada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="1d53b-105">Only the relevant portion of the help is shown in this example.</span></span>

<span data-ttu-id="1d53b-106">A sintaxe é composta principalmente por vários conjuntos de colchetes de abertura e fechamento (`[]`).</span><span class="sxs-lookup"><span data-stu-id="1d53b-106">The syntax is primarily made up of several sets of opening and closing brackets (`[]`).</span></span> <span data-ttu-id="1d53b-107">Eles têm dois significados diferentes, dependendo de como são usados.</span><span class="sxs-lookup"><span data-stu-id="1d53b-107">These have two different meanings depending on how they're used.</span></span> <span data-ttu-id="1d53b-108">Qualquer coisa contida dentro de colchetes é opcional, a menos que eles sejam um conjunto de colchetes vazios `[]`.</span><span class="sxs-lookup"><span data-stu-id="1d53b-108">Anything contained within square brackets is optional unless they're a set of empty square brackets `[]`.</span></span> <span data-ttu-id="1d53b-109">Colchetes vazios só aparecem após um tipo de dados, como `<string[]>`.</span><span class="sxs-lookup"><span data-stu-id="1d53b-109">Empty square brackets only appear after a datatype such as `<string[]>`.</span></span> <span data-ttu-id="1d53b-110">Isso significa que o parâmetro específico pode aceitar mais de um valor desse tipo.</span><span class="sxs-lookup"><span data-stu-id="1d53b-110">This means that particular parameter can accept more than one value of that type.</span></span>

<span data-ttu-id="1d53b-111">O primeiro parâmetro no primeiro conjunto de parâmetros de `Get-EventLog` é **LogName**.</span><span class="sxs-lookup"><span data-stu-id="1d53b-111">The first parameter in the first parameter set of `Get-EventLog` is **LogName**.</span></span> <span data-ttu-id="1d53b-112">LogName está entre colchetes, o que significa que é um parâmetro posicional.</span><span class="sxs-lookup"><span data-stu-id="1d53b-112">LogName is surrounded by square brackets which means that it's a positional parameter.</span></span> <span data-ttu-id="1d53b-113">Em outras palavras, a especificação do nome do parâmetro em si é opcional, desde que ele seja especificado na posição correta.</span><span class="sxs-lookup"><span data-stu-id="1d53b-113">In other words, specifying the name of the parameter itself is optional as long as it's specified in the correct position.</span></span> <span data-ttu-id="1d53b-114">As informações contidas nos colchetes angulares (`<>`) após o nome do parâmetro indicam que ele precisa de um só valor de **cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="1d53b-114">The information in the angle brackets (`<>`) after the parameter name indicates that it needs a single **string** value.</span></span> <span data-ttu-id="1d53b-115">O nome do parâmetro inteiro e o tipo de dados não são incluídos entre colchetes e, portanto, o parâmetro **LogName** é necessário ao usar esse conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="1d53b-115">The entire parameter name and datatype are not surrounded by square brackets so the **LogName** parameter is required when using this parameter set.</span></span>

```powershell
Get-EventLog [-LogName] <String>
```

<span data-ttu-id="1d53b-116">O segundo parâmetro é **InstanceId**.</span><span class="sxs-lookup"><span data-stu-id="1d53b-116">The second parameter is **InstanceId**.</span></span> <span data-ttu-id="1d53b-117">Observe que o nome do parâmetro e o tipo de dados são colocados por completo entre colchetes.</span><span class="sxs-lookup"><span data-stu-id="1d53b-117">Notice that the parameter name and the datatype are both completely surrounded by square brackets.</span></span> <span data-ttu-id="1d53b-118">Isso significa que o parâmetro **InstanceId** é opcional, não obrigatório.</span><span class="sxs-lookup"><span data-stu-id="1d53b-118">This means that the **InstanceId** parameter is optional, not mandatory.</span></span> <span data-ttu-id="1d53b-119">Observe também que **InstanceId** é colocada entre um conjunto de colchetes próprio.</span><span class="sxs-lookup"><span data-stu-id="1d53b-119">Also notice that **InstanceId** is surrounded by its own set of square brackets.</span></span> <span data-ttu-id="1d53b-120">Assim como ocorre com o parâmetro **LogName**, isso significa que o parâmetro é posicional.</span><span class="sxs-lookup"><span data-stu-id="1d53b-120">As with the **LogName** parameter, this means the parameter is positional.</span></span> <span data-ttu-id="1d53b-121">Há um último conjunto de colchetes após o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="1d53b-121">There's one last set of square brackets after the datatype.</span></span> <span data-ttu-id="1d53b-122">Isso significa que ele pode aceitar mais de um valor na forma de uma matriz ou uma lista separada por vírgula.</span><span class="sxs-lookup"><span data-stu-id="1d53b-122">This means that it can accept more than one value in the form of an array or a comma-separated list.</span></span>

```
[[-InstanceId] <Int64[]>]
```

<span data-ttu-id="1d53b-123">O segundo conjunto de parâmetros tem um parâmetro **List**.</span><span class="sxs-lookup"><span data-stu-id="1d53b-123">The second parameter set has a **List** parameter.</span></span> <span data-ttu-id="1d53b-124">É um parâmetro de opção, porque não há nenhum tipo de dados após o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="1d53b-124">It's a switch parameter because there's no datatype following the parameter name.</span></span> <span data-ttu-id="1d53b-125">Quando o parâmetro **List** é especificado, o valor é **True**.</span><span class="sxs-lookup"><span data-stu-id="1d53b-125">When the **List** parameter is specified, the value is **True**.</span></span> <span data-ttu-id="1d53b-126">Quando ele não for especificado, o valor é **False**.</span><span class="sxs-lookup"><span data-stu-id="1d53b-126">When it's not specified, the value is **False**.</span></span>

```
[-List]
```

<span data-ttu-id="1d53b-127">As informações de sintaxe de um comando também podem ser recuperadas usando `Get-Command` por meio do parâmetro **Syntax**.</span><span class="sxs-lookup"><span data-stu-id="1d53b-127">The syntax information for a command can also be retrieved using `Get-Command` using the **Syntax** parameter.</span></span> <span data-ttu-id="1d53b-128">Esse é um atalho útil que uso o tempo todo.</span><span class="sxs-lookup"><span data-stu-id="1d53b-128">This is a handy shortcut that I use all the time.</span></span> <span data-ttu-id="1d53b-129">Ele me permite aprender rapidamente a usar um comando sem precisar percorrer várias páginas de informações da Ajuda.</span><span class="sxs-lookup"><span data-stu-id="1d53b-129">It allows me to quickly learn how to use a command without having to sift through multiple pages of help information.</span></span> <span data-ttu-id="1d53b-130">Se eu acabar precisando de mais informações, voltarei a usar o conteúdo real da Ajuda.</span><span class="sxs-lookup"><span data-stu-id="1d53b-130">If I end up needing more information, then I'll revert to using the actual help content.</span></span>

```powershell
Get-Command -Name Get-EventLog -Syntax
```

```Output
Get-EventLog [-LogName] <string> [[-InstanceId] <long[]>] [-ComputerName <string[]>] [-Newest <int>]
 [-After <datetime>] [-Before <datetime>] [-UserName <string[]>] [-Index <int[]> ]
 [-EntryType <string[]>] [-Source <string[]>] [-Message <string>] [-AsBaseObject]
 [<CommonParameters>]

Get-EventLog [-ComputerName <string[]>] [-List] [-AsString] [<CommonParameters>]
```

<span data-ttu-id="1d53b-131">Quanto mais você usar o sistema de Ajuda do PowerShell, mais fácil será memorizar todas as diferentes nuances.</span><span class="sxs-lookup"><span data-stu-id="1d53b-131">The more you use the help system in PowerShell, the easier remembering all of the different nuances becomes.</span></span> <span data-ttu-id="1d53b-132">Antes que você se dê conta, o uso dele passará a ser algo natural.</span><span class="sxs-lookup"><span data-stu-id="1d53b-132">Before you know it, using it becomes second nature.</span></span>
