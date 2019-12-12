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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369745"
---
# <a name="format-parameters"></a>Parâmetros de formato

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros que são usados para formatar ou gerar dados.

|Parâmetro|Funcionalidade|
|---|---|
|**As**<br>Tipo de dados: palavra-chave|Implemente esse parâmetro para especificar o formato de saída do cmdlet. Por exemplo, os valores possíveis podem ser texto ou script.|
|**Binary**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para indicar que o cmdlet manipula valores binários.|
|**Codificação**<br>Tipo de dados: palavra-chave|Implemente esse parâmetro para especificar o tipo de codificação com suporte. Por exemplo, os valores possíveis podem ser ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, byte e cadeia de caracteres.|
|**Separados**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que os caracteres de nova linha tenham suporte quando o parâmetro for especificado.|
|**Nome curto**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que os nomes curtos tenham suporte quando o parâmetro for especificado.|
|**Largura**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar a largura do dispositivo de saída.|
|**Haja**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o encapsulamento de texto tenha suporte quando o parâmetro for especificado.|
## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlet](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
