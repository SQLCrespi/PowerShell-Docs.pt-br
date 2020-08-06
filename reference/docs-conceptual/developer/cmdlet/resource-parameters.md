---
title: Parâmetros de recurso | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e618951d57ff1cf303b38f0278858144df31afaf
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786519"
---
# <a name="resource-parameters"></a>Parâmetros do recurso

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros de recurso. Para esses parâmetros, os recursos podem ser o assembly que contém a classe de cmdlet ou o aplicativo host que está executando o cmdlet.

|Parâmetro|Funcionalidade|
|---|---|
|**Aplicativo**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um aplicativo.|
|**Assembly**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um assembly.|
|**Atributo**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um atributo.|
|**Classe**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar uma classe de estrutura de Microsoft .NET.|
|**Cluster**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um cluster.|
|**Cultura**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar a cultura na qual executar o cmdlet.|
|**Domínio**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome de domínio.|
|**Unidade**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um nome de unidade.|
|**Evento**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um nome de evento.|
|**Interface**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um nome de interface de rede.|
|**IP**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um endereço IP.|
|**Trabalho**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um trabalho.|
|**LiteralPath**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o caminho para um recurso quando não houver suporte para caracteres curinga. (Use o parâmetro **path** quando houver suporte para caracteres curinga.)|
|**Mac**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um endereço MAC (controlador de acesso à mídia).|
|**ParentId**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o identificador pai.|
|**Caminho**<br>Tipo de dados: String, String []|Implemente esse parâmetro para que o usuário possa indicar os caminhos para um recurso quando houver suporte para caracteres curinga. (Use o parâmetro **LiteralPath** quando não houver suporte para caracteres curinga.) Recomendamos que você desenvolva esse parâmetro para que ele dê suporte à `provider:path` sintaxe completa usada pelos provedores. Também recomendamos que você o desenvolva para que funcione com o máximo de provedores possível.|
|**Porta**<br>Tipo de dados: inteiro, Cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um valor inteiro para rede ou um valor de cadeia de caracteres como "BizTalk" para outros tipos de porta.|
|**Impressora**<br>Tipo de dados: inteiro, Cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar a impressora a ser usada pelo cmdlet.|
|**Tamanho**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar um tamanho.|
|**TID**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um identificador de transação (TID) para o cmdlet.|
|**Tipo**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o tipo de recurso no qual operar.|
|**URL**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um Uniform Resource Locator (URL).|
|**Usuário**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar seu nome ou o nome de outro usuário.|

## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlets](./cmdlet-parameters.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
