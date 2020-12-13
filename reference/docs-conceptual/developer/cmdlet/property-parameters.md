---
ms.date: 09/13/2016
ms.topic: reference
title: Parâmetros de propriedade
description: Parâmetros de propriedade
ms.openlocfilehash: eff51fcd395e5f9570193ea91684f9e70030bc7d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652602"
---
# <a name="property-parameters"></a>Parâmetros de propriedade

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros de propriedade.

|Parâmetro|Funcionalidade|
|---|---|
|**Count**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar o número de objetos a serem processados.|
|**Descrição**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar uma descrição para um recurso.|
|**De**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o objeto de referência do qual obter informações.|
|**Id**<br>Tipo de dados: dependente de recurso|Implemente esse parâmetro para que o usuário possa especificar o identificador de um recurso.|
|**Entrada**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar a especificação do arquivo de entrada.|
|**Localidade**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o local do recurso.|
|**LogName**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome do arquivo de log a ser processado ou usado.|
|**Nome**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome do recurso.|
|**Saída**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o arquivo de saída.|
|**Proprietário**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome do proprietário do recurso.|
|**Propriedade**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome ou os nomes das propriedades a serem usadas.|
|**Motivo**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar por que esse cmdlet está sendo invocado.|
|**Regex**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que as expressões regulares sejam usadas quando o parâmetro for especificado. Quando esse parâmetro é especificado, os caracteres curinga não são resolvidos.|
|**Rápida**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar a taxa de transmissão. O usuário define esse parâmetro como a velocidade do recurso.|
|**State**<br>Tipo de dados: matriz de palavras-chave|Implemente esse parâmetro para que o usuário possa especificar os nomes dos Estados, como KEYDOWN.|
|**Valor**<br>Tipo de dados: objeto|Implemente esse parâmetro para que o usuário possa especificar um valor a ser fornecido ao cmdlet.|
|**Versão**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar a versão da propriedade.|

## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlets](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
