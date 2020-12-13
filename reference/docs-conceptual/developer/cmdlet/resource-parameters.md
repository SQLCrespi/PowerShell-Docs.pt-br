---
ms.date: 09/13/2016
ms.topic: reference
title: Parâmetros do recurso
description: Parâmetros do recurso
ms.openlocfilehash: 7533f91b6d5858bcefca289eabc7854d6d5d1f2b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668143"
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

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
