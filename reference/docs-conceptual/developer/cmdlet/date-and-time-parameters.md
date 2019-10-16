---
title: Parâmetros de data e hora | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71da921b-7c32-4155-b2f8-b19f30ec774d
caps.latest.revision: 7
ms.openlocfilehash: 5b1f093de5db364ac806e58c4ed8dbf2948cb6c6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369785"
---
# <a name="date-and-time-parameters"></a>Parâmetros de data e hora

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros que lidam com informações de data e hora. Os parâmetros de data e hora normalmente são usados para registrar quando algo é criado ou acessado.

|Parâmetro|Funcionalidade|
|---|---|
|**Acessíveis**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que, quando ele for especificado, o cmdlet opere nos recursos que foram acessados com base na data e hora especificadas pelos parâmetros **before** e **After** . Se esse parâmetro for especificado, os parâmetros **criado** e **modificado** não deverão ser especificados.|
|**Após**<br>Tipo de dados: DateTime|Implemente esse parâmetro para especificar a data e a hora após a qual o cmdlet foi usado. Para que o parâmetro **After** funcione, o cmdlet também deve ter um parâmetro **acessado**, **criado**ou **modificado** . E esse parâmetro deve ser definido como **true** quando o cmdlet é chamado.|
|**Anterior**<br>Tipo de dados: DateTime|Implemente esse parâmetro para especificar a data e a hora antes da qual o cmdlet foi usado. Para que o parâmetro **before** funcione, o cmdlet também deve ter um parâmetro **acessado**, **criado**ou **modificado** . E esse parâmetro deve ser definido como **true** quando o cmdlet é chamado.|
|**Criação**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que, quando ele for especificado, o cmdlet opere nos recursos que foram criados com base na data e hora especificadas pelos parâmetros **before** e **After** . Se esse parâmetro for especificado, os parâmetros **acessados** e **modificados** não deverão ser especificados.|
|**Exact**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que, quando ele for especificado, o termo de recurso deva corresponder exatamente ao nome do recurso. Quando o parâmetro não for especificado, o termo e o nome do recurso não precisarão corresponder exatamente.|
|**Alteração**<br>Tipo de dados: DateTime|Implemente esse parâmetro para que, quando ele for especificado, o cmdlet opere em recursos que foram alterados com base na data e hora especificadas pelos parâmetros **before** e **After** . Se esse parâmetro for especificado, os parâmetros **acessados** e **criados** não deverão ser especificados.|
## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlet](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
