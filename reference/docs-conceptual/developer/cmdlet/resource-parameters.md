---
title: Parâmetros de recurso | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 460c43aa-f5c5-4a1a-a6f2-5e07db143de1
caps.latest.revision: 5
ms.openlocfilehash: 9752570e5c997ef4da56a08df14f39b77ba37a4a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369505"
---
# <a name="resource-parameters"></a>Parâmetros do recurso

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros de recurso. Para esses parâmetros, os recursos podem ser o assembly que contém a classe de cmdlet ou o aplicativo host que está executando o cmdlet.

|Parâmetro|Funcionalidade|
|---|---|
|**Aplicativo**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um aplicativo.|
|**)**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um assembly.|
|**Attribute**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um atributo.|
|**Classes**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar uma classe de estrutura de Microsoft .NET.|
|**Em**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um cluster.|
|**UICulture**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar a cultura na qual executar o cmdlet.|
|**Controlador**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome de domínio.|
|**Dirigir**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um nome de unidade.|
|**Circunstância**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um nome de evento.|
|**Interface**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um nome de interface de rede.|
|**IP**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um endereço IP.|
|**Trabalho**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um trabalho.|
|**LiteralPath**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o caminho para um recurso quando não houver suporte para caracteres curinga. (Use o parâmetro **path** quando houver suporte para caracteres curinga.)|
|**Mac**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um endereço MAC (controlador de acesso à mídia).|
|**ParentId**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o identificador pai.|
|**Multi-Path**<br>Tipo de dados: String, String []|Implemente esse parâmetro para que o usuário possa indicar os caminhos para um recurso quando houver suporte para caracteres curinga. (Use o parâmetro **LiteralPath** quando não houver suporte para caracteres curinga.) Recomendamos que você desenvolva esse parâmetro para que ele dê suporte à sintaxe `provider:path` completa usada pelos provedores. Também recomendamos que você o desenvolva para que funcione com o máximo de provedores possível.|
|**Porto**<br>Tipo de dados: inteiro, Cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um valor inteiro para rede ou um valor de cadeia de caracteres como "BizTalk" para outros tipos de porta.|
|**Impressora**<br>Tipo de dados: inteiro, Cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar a impressora a ser usada pelo cmdlet.|
|**Tamanho**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar um tamanho.|
|**TID**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um identificador de transação (TID) para o cmdlet.|
|**Escreva**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o tipo de recurso no qual operar.|
|**URL**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um Uniform Resource Locator (URL).|
|**User**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar seu nome ou o nome de outro usuário.|

## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlet](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
