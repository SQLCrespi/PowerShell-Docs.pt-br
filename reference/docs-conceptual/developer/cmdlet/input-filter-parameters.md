---
title: Parâmetros de filtro de entrada | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e45929d1-bbb4-4dc6-892f-f9eacdb1c84c
caps.latest.revision: 8
ms.openlocfilehash: 7a1582031d27f78bad069f5539408312ccabb3f2
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83563883"
---
# <a name="input-filter-parameters"></a>Parâmetros de filtro de entrada

Um cmdlet pode definir `Filter` , `Include` e `Exclude` parâmetros que filtram o conjunto de objetos de entrada que o cmdlet afeta.

Normalmente, o conjunto de objetos de entrada é especificado por `InputObject` um `Path` parâmetro, ou `Name` . Por exemplo, um cmdlet pode ter um `Path` parâmetro que aceita vários caminhos usando caracteres curinga e cada caminho aponta para um objeto de entrada. Usados juntos, os `Filter` `Include` parâmetros, e `Exclude` qualificam ainda mais os caminhos em que o cmdlet funciona sempre que é invocado.

## <a name="include-and-exclude-parameters"></a>Incluir e excluir parâmetros

Os `Include` `Exclude` parâmetros e identificam os objetos que são incluídos ou excluídos do conjunto de objetos de entrada passados para o cmdlet. Use esses parâmetros quando o filtro puder ser expresso na linguagem padrão de curinga. (Para obter mais informações sobre caracteres curinga, consulte [suportando curingas em parâmetros de cmdlet](./supporting-wildcard-characters-in-cmdlet-parameters.md).) O `Include` parâmetro inclui todos os objetos cujos nomes correspondem ao filtro de inclusão. O `Exclude` parâmetro exclui todos os objetos cujos nomes correspondem ao filtro.

## <a name="filter-parameter"></a>Parâmetro de filtro

O `Filter` parâmetro especifica um filtro que não é expresso na linguagem curinga padrão. Por exemplo, as interfaces de serviço Active Directory (ADSI) ou filtros SQL podem ser passados para o cmdlet por meio de seu `Filter` parâmetro. Nos cmdlets fornecidos pelo Windows PowerShell, esses filtros são especificados pelos provedores do Windows PowerShell que usam o cmdlet para acessar um armazenamento de dados. Cada provedor normalmente define seu próprio filtro.

## <a name="filtering-if-no-set-of-input-objects-is-specified"></a>Filtragem se nenhum conjunto de objetos de entrada for especificado

Se nenhum conjunto de objetos de entrada for especificado, isso geralmente significa filtrar em relação a todos os objetos. Para obter mais informações, consulte[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process).

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
