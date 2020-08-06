---
title: Declaração de classe de cmdlet | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- cmdlets [PowerShell SDK], declaring
- declaring cmdlets [PowerShell SDK]
ms.openlocfilehash: 96ce8144795346b6f46878ee6163ce69cdb1799a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784496"
---
# <a name="cmdlet-class-declaration"></a>Declaração de classe do cmdlet

Uma classe de estrutura de Microsoft .NET é declarada como um cmdlet especificando o atributo de **cmdlet** como metadados para a classe. (O atributo de **cmdlet** é o único atributo necessário para todos os cmdlets).
Ao especificar o atributo de **cmdlet** , você deve especificar o par verbo-e-substantivo que identifica o cmdlet para o usuário. Além disso, você deve descrever a funcionalidade do Windows PowerShell que o cmdlet dá suporte. Para obter mais informações sobre a sintaxe de declaração usada para especificar o atributo de **cmdlet** , consulte [declaração de atributo de cmdlet](./cmdlet-attribute-declaration.md).

> [!NOTE]
> O atributo **cmdlet** é definido pela classe [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) . As propriedades dessa classe correspondem aos parâmetros de declaração que são usados quando você declara o atributo.

## <a name="nouns"></a>Substantivos

O substantivo do cmdlet especifica os recursos sobre os quais o cmdlet atua. O substantivo diferencia seus cmdlets de outros cmdlets.

Os substantivos nos nomes de cmdlet devem ser específicos e, no caso de substantivos genéricos, como *servidor*, é melhor adicionar um prefixo curto que diferencie seu recurso de outros recursos semelhantes. Por exemplo, um nome de cmdlet que inclui um substantivo com um prefixo é `Get-SQLServer` . A combinação de um substantivo específico com um verbo mais geral permite que o usuário localize rapidamente o cmdlet por sua ação e, em seguida, identifique o cmdlet por seu recurso, evitando, ao mesmo tempo, a duplicação do nome do cmdlet desnecessário.

Para obter uma lista de caracteres especiais que não podem ser usados em nomes de cmdlet, consulte [diretrizes de desenvolvimento necessárias](./required-development-guidelines.md).

## <a name="verbs"></a>Verbos

Quando você especifica um verbo, as diretrizes de desenvolvimento exigem que você use um dos verbos predefinidos fornecidos pelo Windows PowerShell. Usando um desses verbos predefinidos, você garantirá a consistência entre os cmdlets que você escreve e os cmdlets que são escritos pela Microsoft e por outros. Por exemplo, o verbo "Get" é usado para cmdlets que recuperam dados.

Para obter mais informações sobre as diretrizes para verbos, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md). Para obter uma lista de caracteres especiais que não podem ser usados em nomes de cmdlet, consulte [diretrizes de desenvolvimento necessárias](./required-development-guidelines.md).

## <a name="supporting-windows-powershell-functionality"></a>Suporte à funcionalidade do Windows PowerShell

O atributo **cmdlet** também permite que você especifique que o cmdlet oferece suporte a algumas das funcionalidades comuns fornecidas pelo Windows PowerShell. Isso inclui suporte para funcionalidades comuns, como confirmação de comentários do usuário (conhecido como suporte para o recurso ShouldProcess) e suporte para transações. (O suporte para transações foi introduzido no Windows PowerShell 2,0).

Para obter mais informações sobre a sintaxe de declaração usada para especificar o atributo de **cmdlet** , consulte [declaração de atributo de cmdlet](./cmdlet-attribute-declaration.md).

## <a name="cmdlet-class-definition"></a>Definição de classe de cmdlet

O código a seguir é a definição de uma classe de cmdlet getproc. Observe que o uso de maiúsculas e minúsculas do Pascal é usado e que o nome da classe inclui o verbo e o substantivo do cmdlet.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="33-34":::

## <a name="pascal-casing"></a>Compartimento de Pascal

Quando você nomear cmdlets, use a embalagem do Pascal. Por exemplo, os `Get-Item` `Get-ItemProperty` cmdlets e mostram a maneira correta de usar a capitalização ao nomear cmdlets.

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)

[Declaração de CmdletAttribute](./cmdlet-attribute-declaration.md)

[Nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
