---
ms.date: 09/13/2016
ms.topic: reference
title: Parâmetros de formato
description: Parâmetros de formato
ms.openlocfilehash: 5f970683fedc71b208ff6becad761d94611a91a6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652816"
---
# <a name="format-parameters"></a>Parâmetros de formato

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros que são usados para formatar ou gerar dados.

|Parâmetro|Funcionalidade|
|---|---|
|**Como**<br>Tipo de dados: palavra-chave|Implemente esse parâmetro para especificar o formato de saída do cmdlet. Por exemplo, os valores possíveis podem ser texto ou script.|
|**Binary**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para indicar que o cmdlet manipula valores binários.|
|**Codificação**<br>Tipo de dados: palavra-chave|Implemente esse parâmetro para especificar o tipo de codificação com suporte. Por exemplo, os valores possíveis podem ser ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, byte e cadeia de caracteres.|
|**Separados**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que os caracteres de nova linha tenham suporte quando o parâmetro for especificado.|
|**ShortName**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que os nomes curtos tenham suporte quando o parâmetro for especificado.|
|**Largura**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar a largura do dispositivo de saída.|
|**Encapsular**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o encapsulamento de texto tenha suporte quando o parâmetro for especificado.|
## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlets](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
