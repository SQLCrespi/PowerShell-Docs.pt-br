---
title: Parâmetros de formato | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c8e031f62aa8bcb0e9d5b900b2eace7187b1f3dd
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784275"
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

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
