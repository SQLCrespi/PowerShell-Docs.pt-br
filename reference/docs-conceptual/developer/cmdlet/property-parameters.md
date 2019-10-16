---
title: Parâmetros de propriedade | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d17e0d66-42ea-4e4c-a85b-3ca09b146492
caps.latest.revision: 6
ms.openlocfilehash: cc0742b86a7a36e5712707c077fd1952691f3f4b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369575"
---
# <a name="property-parameters"></a>Parâmetros de propriedade

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros de propriedade.

|Parâmetro|Funcionalidade|
|---|---|
|**Contar**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar o número de objetos a serem processados.|
|**Descrição**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar uma descrição para um recurso.|
|**De**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o objeto de referência do qual obter informações.|
|**Sessão**<br>Tipo de dados: dependente de recurso|Implemente esse parâmetro para que o usuário possa especificar o identificador de um recurso.|
|**Entrada**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar a especificação do arquivo de entrada.|
|**Local**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o local do recurso.|
|**LogName**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome do arquivo de log a ser processado ou usado.|
|**Nomes**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome do recurso.|
|**Der**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o arquivo de saída.|
|**Proprietário**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome do proprietário do recurso.|
|**Propriedade**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome ou os nomes das propriedades a serem usadas.|
|**Falha**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar por que esse cmdlet está sendo invocado.|
|**Regex**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que as expressões regulares sejam usadas quando o parâmetro for especificado. Quando esse parâmetro é especificado, os caracteres curinga não são resolvidos.|
|**Rápida**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar a taxa de transmissão. O usuário define esse parâmetro como a velocidade do recurso.|
|**Status**<br>Tipo de dados: matriz de palavras-chave|Implemente esse parâmetro para que o usuário possa especificar os nomes dos Estados, como KEYDOWN.|
|**Valor**<br>Tipo de dados: objeto|Implemente esse parâmetro para que o usuário possa especificar um valor a ser fornecido ao cmdlet.|
|**Versão**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar a versão da propriedade.|

## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlet](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
