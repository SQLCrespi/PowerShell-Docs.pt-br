---
ms.date: 09/13/2016
ms.topic: reference
title: Parâmetros de data e hora
description: Parâmetros de data e hora
ms.openlocfilehash: 2f73d16ca8261ebc4ca8d2c18aff4176d7d7314c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653196"
---
# <a name="date-and-time-parameters"></a>Parâmetros de data e hora

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros que lidam com informações de data e hora. Os parâmetros de data e hora normalmente são usados para registrar quando algo é criado ou acessado.

|Parâmetro|Funcionalidade|
|---|---|
|**Acessíveis**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que, quando ele for especificado, o cmdlet opere nos recursos que foram acessados com base na data e hora especificadas pelos parâmetros **before** e **After** . Se esse parâmetro for especificado, os parâmetros **criado** e **modificado** não deverão ser especificados.|
|**Depois**<br>Tipo de dados: DateTime|Implemente esse parâmetro para especificar a data e a hora após a qual o cmdlet foi usado. Para que o parâmetro **After** funcione, o cmdlet também deve ter um parâmetro **acessado**, **criado** ou **modificado** . E esse parâmetro deve ser definido como **true** quando o cmdlet é chamado.|
|**Antes**<br>Tipo de dados: DateTime|Implemente esse parâmetro para especificar a data e a hora antes da qual o cmdlet foi usado. Para que o parâmetro **before** funcione, o cmdlet também deve ter um parâmetro **acessado**, **criado** ou **modificado** . E esse parâmetro deve ser definido como **true** quando o cmdlet é chamado.|
|**Criado**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que, quando ele for especificado, o cmdlet opere nos recursos que foram criados com base na data e hora especificadas pelos parâmetros **before** e **After** . Se esse parâmetro for especificado, os parâmetros **acessados** e **modificados** não deverão ser especificados.|
|**Exato**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que, quando ele for especificado, o termo de recurso deva corresponder exatamente ao nome do recurso. Quando o parâmetro não for especificado, o termo e o nome do recurso não precisarão corresponder exatamente.|
|**Modificado**<br>Tipo de dados: DateTime|Implemente esse parâmetro para que, quando ele for especificado, o cmdlet opere em recursos que foram alterados com base na data e hora especificadas pelos parâmetros **before** e **After** . Se esse parâmetro for especificado, os parâmetros **acessados** e **criados** não deverão ser especificados.|
## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlets](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
