---
title: Parâmetros de formato | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10e025c5-9aa6-45a5-b851-23d14db1f4cc
caps.latest.revision: 7
ms.openlocfilehash: 0bd3888d81aa6d1dde26c0066f7bca9dac8a8bca
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369745"
---
# <a name="format-parameters"></a><span data-ttu-id="44647-102">Parâmetros de formato</span><span class="sxs-lookup"><span data-stu-id="44647-102">Format Parameters</span></span>

<span data-ttu-id="44647-103">A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros que são usados para formatar ou gerar dados.</span><span class="sxs-lookup"><span data-stu-id="44647-103">The following table lists recommended names and functionality for parameters that are used to format or to generate data.</span></span>

|<span data-ttu-id="44647-104">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="44647-104">Parameter</span></span>|<span data-ttu-id="44647-105">Funcionalidade</span><span class="sxs-lookup"><span data-stu-id="44647-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="44647-106">**Como**</span><span class="sxs-lookup"><span data-stu-id="44647-106">**As**</span></span><br><span data-ttu-id="44647-107">Tipo de dados: palavra-chave</span><span class="sxs-lookup"><span data-stu-id="44647-107">Data type: Keyword</span></span>|<span data-ttu-id="44647-108">Implemente esse parâmetro para especificar o formato de saída do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="44647-108">Implement this parameter to specify the cmdlet output format.</span></span> <span data-ttu-id="44647-109">Por exemplo, os valores possíveis podem ser texto ou script.</span><span class="sxs-lookup"><span data-stu-id="44647-109">For example, possible values could be Text or Script.</span></span>|
|<span data-ttu-id="44647-110">**Binário**</span><span class="sxs-lookup"><span data-stu-id="44647-110">**Binary**</span></span><br><span data-ttu-id="44647-111">Tipo de dados: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="44647-111">Data type: SwitchParameter</span></span>|<span data-ttu-id="44647-112">Implemente esse parâmetro para indicar que o cmdlet manipula valores binários.</span><span class="sxs-lookup"><span data-stu-id="44647-112">Implement this parameter to indicate that the cmdlet handles binary values.</span></span>|
|<span data-ttu-id="44647-113">**Mecanismo**</span><span class="sxs-lookup"><span data-stu-id="44647-113">**Encoding**</span></span><br><span data-ttu-id="44647-114">Tipo de dados: palavra-chave</span><span class="sxs-lookup"><span data-stu-id="44647-114">Data type: Keyword</span></span>|<span data-ttu-id="44647-115">Implemente esse parâmetro para especificar o tipo de codificação com suporte.</span><span class="sxs-lookup"><span data-stu-id="44647-115">Implement this parameter to specify the type of encoding that is supported.</span></span> <span data-ttu-id="44647-116">Por exemplo, os valores possíveis podem ser ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, byte e cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="44647-116">For example, possible values could be ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte, and String.</span></span>|
|<span data-ttu-id="44647-117">**Separados**</span><span class="sxs-lookup"><span data-stu-id="44647-117">**NewLine**</span></span><br><span data-ttu-id="44647-118">Tipo de dados: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="44647-118">Data type: SwitchParameter</span></span>|<span data-ttu-id="44647-119">Implemente esse parâmetro para que os caracteres de nova linha tenham suporte quando o parâmetro for especificado.</span><span class="sxs-lookup"><span data-stu-id="44647-119">Implement this parameter so that the newline characters are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="44647-120">**Nome curto**</span><span class="sxs-lookup"><span data-stu-id="44647-120">**ShortName**</span></span><br><span data-ttu-id="44647-121">Tipo de dados: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="44647-121">Data type: SwitchParameter</span></span>|<span data-ttu-id="44647-122">Implemente esse parâmetro para que os nomes curtos tenham suporte quando o parâmetro for especificado.</span><span class="sxs-lookup"><span data-stu-id="44647-122">Implement this parameter so that short names are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="44647-123">**Largura**</span><span class="sxs-lookup"><span data-stu-id="44647-123">**Width**</span></span><br><span data-ttu-id="44647-124">Tipo de dados: Int32</span><span class="sxs-lookup"><span data-stu-id="44647-124">Data type: Int32</span></span>|<span data-ttu-id="44647-125">Implemente esse parâmetro para que o usuário possa especificar a largura do dispositivo de saída.</span><span class="sxs-lookup"><span data-stu-id="44647-125">Implement this parameter so that the user can specify the width of the output device.</span></span>|
|<span data-ttu-id="44647-126">**Haja**</span><span class="sxs-lookup"><span data-stu-id="44647-126">**Wrap**</span></span><br><span data-ttu-id="44647-127">Tipo de dados: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="44647-127">Data type: SwitchParameter</span></span>|<span data-ttu-id="44647-128">Implemente esse parâmetro para que o encapsulamento de texto tenha suporte quando o parâmetro for especificado.</span><span class="sxs-lookup"><span data-stu-id="44647-128">Implement this parameter so that text wrapping is supported when the parameter is specified.</span></span>|
## <a name="see-also"></a><span data-ttu-id="44647-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="44647-129">See Also</span></span>

[<span data-ttu-id="44647-130">Parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="44647-130">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

<span data-ttu-id="44647-131">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="44647-131">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>

[<span data-ttu-id="44647-132">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44647-132">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
