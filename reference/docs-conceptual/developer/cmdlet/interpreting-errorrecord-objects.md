---
title: Interpretando objetos ErrorRecord | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a65b964-5bc6-4ade-a66b-b6afa7351ce7
caps.latest.revision: 9
ms.openlocfilehash: 32ebf2531237bfd1042310ccc4155193a58401fd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365415"
---
# <a name="interpreting-errorrecord-objects"></a>Interpretar objetos ErrorRecord

Na maioria dos casos, um objeto [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) representa um erro de não finalização gerado por um comando ou script. Os erros de encerramento também podem especificar as informações adicionais em um ErrorRecord por meio da interface [System. Management. Automation. Icontainserrorrecord](/dotnet/api/System.Management.Automation.IContainsErrorRecord) .

Se você quiser escrever um manipulador de erro em seu script ou um host para tratar erros específicos que ocorrem durante a execução do comando ou do script, você deve interpretar o objeto [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) para determinar se ele representa a classe de erro que você deseja manipular.

Quando um cmdlet encontra um erro de encerramento ou de não encerramento, ele deve criar um registro de erro que descreva a condição de erro. O aplicativo host deve investigar esses registros de erros e executar qualquer ação que reduza o erro. O aplicativo host também deve investigar registros de erro para erros de não encerramento que falharam ao processar um registro, mas que pudesse continuar e deve investigar os registros de erro para erros de encerramento que fizeram com que o pipeline fosse interrompido.

> [!NOTE]
> Para erros de encerramento, o cmdlet chama o método [System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) . Para erros de não encerramento, o cmdlet chama o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) .

## <a name="error-record-design"></a>Design do registro de erros

Os registros de erro são projetados para fornecer informações de erro adicionais que não estão disponíveis em exceções, garantindo que as informações combinadas em cada registro de erro sejam exclusivas. Essa exclusividade permite que o aplicativo host inspecione as diferentes partes do registro de erros para que ele possa identificar a condição de erro e a ação que o host deve executar.

## <a name="interpreting-error-records"></a>Interpretando registros de erro

Você pode examinar várias partes do registro de erro para identificar o erro. Essas partes incluem o seguinte:

- A categoria de erro

- A exceção de erro

- O identificador de erro totalmente qualificado (FQID)

- Outras informações

### <a name="the-error-category"></a>A categoria de erro

A categoria de erro do registro de erro é uma das constantes predefinidas fornecidas pela enumeração [System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory) . Essas informações estão disponíveis por meio da propriedade [System. Management. Automation. ErrorRecord. CategoryInfo](/dotnet/api/System.Management.Automation.ErrorRecord.CategoryInfo) do objeto [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) .

O cmdlet pode especificar as categorias CloseError, OpenError, invalidatype, ReadError e WriteError e outras categorias de erro. O aplicativo host pode usar a categoria de erro para capturar grupos de erros.

### <a name="the-exception"></a>A exceção

A exceção incluída no registro de erro é fornecida pelo cmdlet e pode ser acessada por meio da propriedade [System. Management. Automation. ErrorRecord. Exception *](/dotnet/api/System.Management.Automation.ErrorRecord.Exception) do objeto [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) .

Os aplicativos host podem usar a palavra-chave `is` para identificar que a exceção é de uma classe específica ou de uma classe derivada. É melhor ramificar o tipo de exceção, conforme mostrado no exemplo a seguir.

`if (MyNonTerminatingError.Exception is AccessDeniedException)`

Dessa forma, você captura as classes derivadas. No entanto, há problemas se a exceção for desserializada.

### <a name="the-fqid"></a>O FQID

O FQID é a informação mais específica que você pode usar para identificar o erro. É uma cadeia de caracteres que inclui um identificador definido por cmdlet, o nome da classe de cmdlet e a fonte que relatou o erro. Em geral, um registro de erro é análogo a um registro de evento de um log de eventos do Windows. O FQID é análogo à seguinte tupla, que identifica a classe do registro de evento: (*nome do log*, *origem*, *ID do evento*).

O FQID foi projetado para ser inspecionado como uma única cadeia de caracteres. No entanto, há casos em que o identificador de erro é projetado para ser analisado pelo aplicativo host. O exemplo a seguir é um identificador de erro totalmente qualificado bem formado.

`CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand.`

No exemplo anterior, o primeiro token é o identificador de erro, que é seguido pelo nome da classe de cmdlet. O identificador de erro pode ser um único token ou pode ser um identificador separado por ponto que permite a ramificação na inspeção do identificador. Não use espaço em branco ou pontuação no identificador de erro. É especialmente importante não usar uma vírgula; uma vírgula é usada pelo Windows PowerShell para separar o identificador e o nome da classe do cmdlet.

### <a name="other-information"></a>Outras informações

O objeto [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) também pode fornecer informações que descrevem o ambiente no qual o erro ocorreu. Essas informações incluem itens como detalhes do erro, informações de invocação e o objeto de destino que estava sendo processado quando o erro ocorreu. Embora essas informações possam ser úteis para o aplicativo host, ela normalmente não é usada para identificar o erro. Essas informações estão disponíveis por meio das seguintes propriedades:

[System. Management. Automation. ErrorRecord. ErrorDetails](/dotnet/api/System.Management.Automation.ErrorRecord.ErrorDetails)

[System. Management. Automation. ErrorRecord. InvocationInfo](/dotnet/api/System.Management.Automation.ErrorRecord.InvocationInfo)

[System. Management. Automation. ErrorRecord. TargetObject](/dotnet/api/System.Management.Automation.ErrorRecord.TargetObject)

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)

[System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory)

[System. Management. Automation. Errorcategoryinfo](/dotnet/api/System.Management.Automation.ErrorCategoryInfo)

[System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[Adicionando relatórios de erros não conclusivos ao seu cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[Relatório de erros do Windows PowerShell](./error-reporting-concepts.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
