---
title: Parâmetros de data e hora | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f1b2bb3b3da2b73860298e36d88502bfd67c5b22
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774653"
---
# <a name="date-and-time-parameters"></a>Parâmetros de data e hora

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros que lidam com informações de data e hora. Os parâmetros de data e hora normalmente são usados para registrar quando algo é criado ou acessado.

|Parâmetro|Funcionalidade|
|---|---|
|**Acessíveis**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que, quando ele for especificado, o cmdlet opere nos recursos que foram acessados com base na data e hora especificadas pelos parâmetros **before** e **After** . Se esse parâmetro for especificado, os parâmetros **criado** e **modificado** não deverão ser especificados.|
|**Depois**<br>Tipo de dados: DateTime|Implemente esse parâmetro para especificar a data e a hora após a qual o cmdlet foi usado. Para que o parâmetro **After** funcione, o cmdlet também deve ter um parâmetro **acessado**, **criado**ou **modificado** . E esse parâmetro deve ser definido como **true** quando o cmdlet é chamado.|
|**Antes**<br>Tipo de dados: DateTime|Implemente esse parâmetro para especificar a data e a hora antes da qual o cmdlet foi usado. Para que o parâmetro **before** funcione, o cmdlet também deve ter um parâmetro **acessado**, **criado**ou **modificado** . E esse parâmetro deve ser definido como **true** quando o cmdlet é chamado.|
|**Criado**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que, quando ele for especificado, o cmdlet opere nos recursos que foram criados com base na data e hora especificadas pelos parâmetros **before** e **After** . Se esse parâmetro for especificado, os parâmetros **acessados** e **modificados** não deverão ser especificados.|
|**Exato**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que, quando ele for especificado, o termo de recurso deva corresponder exatamente ao nome do recurso. Quando o parâmetro não for especificado, o termo e o nome do recurso não precisarão corresponder exatamente.|
|**Alteração**<br>Tipo de dados: DateTime|Implemente esse parâmetro para que, quando ele for especificado, o cmdlet opere em recursos que foram alterados com base na data e hora especificadas pelos parâmetros **before** e **After** . Se esse parâmetro for especificado, os parâmetros **acessados** e **criados** não deverão ser especificados.|
## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlets](./cmdlet-parameters.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
