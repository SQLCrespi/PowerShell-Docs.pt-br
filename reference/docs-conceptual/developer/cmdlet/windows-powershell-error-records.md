---
title: Registros de erro do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error category [PowerShell SDK]
- error identifier [PowerShell SDK]
- error records [PowerShell SDK]
- error category string [PowerShell SDK]
ms.assetid: bdd66fea-eb63-4bb6-9cbe-9a799e5e0db5
caps.latest.revision: 9
ms.openlocfilehash: 5412d88b690a1f5f1ef387416e3bf9da3a32c95d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369105"
---
# <a name="windows-powershell-error-records"></a>Registros de erros do Windows PowerShell

Os cmdlets devem passar um objeto [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) que identifica a condição de erro para erros de encerramento e de não finalização.

O objeto [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) contém as seguintes informações:

- A exceção que descreve o erro. Geralmente, essa é uma exceção que o cmdlet capturou e converteu em um registro de erro. Cada registro de erro deve conter uma exceção.

Se o cmdlet não capturou uma exceção, ele deve criar uma nova exceção e escolher a classe de exceção que melhor descreve a condição de erro. No entanto, não é necessário lançar a exceção porque ela pode ser acessada por meio da propriedade [System. Management. Automation. ErrorRecord. Exception](/dotnet/api/System.Management.Automation.ErrorRecord.Exception) do objeto [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) .

- Um identificador de erro que fornece um designador de destino que pode ser usado para fins de diagnóstico e por scripts do Windows PowerShell para lidar com condições de erro específicas com manipuladores de erro específicos. Cada registro de erro deve conter um identificador de erro (consulte o identificador de erro).

- Uma categoria de erro que fornece um designador geral que pode ser usado para fins de diagnóstico. Cada registro de erro deve especificar uma categoria de erro (consulte a categoria de erro).

- Uma mensagem de erro de substituição opcional e uma ação recomendada (consulte a mensagem de erro de substituição).

- Informações de invocação opcionais sobre o cmdlet que gerou o erro. Essas informações são especificadas pelo Windows PowerShell (consulte mensagem de invocação).

- O objeto de destino que estava sendo processado quando o erro ocorreu. Esse pode ser o objeto de entrada ou pode ser outro objeto que o seu cmdlet estava processando. Por exemplo, para o comando `remove-item -recurse c:\somedirectory`, o erro pode ser uma instância de um objeto FileInfo para "c:\somedirectory\lockedfile". As informações do objeto de destino são opcionais.

## <a name="error-identifier"></a>Identificador de erro

Ao criar um registro de erro, especifique um identificador que designa a condição de erro dentro do seu cmdlet. O Windows PowerShell combina o identificador de destino com o nome do seu cmdlet para criar um identificador de erro totalmente qualificado. O identificador de erro totalmente qualificado pode ser acessado por meio da propriedade [System. Management. Automation. ErrorRecord. FullyQualifiedErrorId](/dotnet/api/System.Management.Automation.ErrorRecord.FullyQualifiedErrorId) do objeto [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) . O identificador de erro não está disponível por si só. Ele está disponível apenas como parte do identificador de erro totalmente qualificado.

Use as diretrizes a seguir para gerar identificadores de erro ao criar registros de erro:

- Crie identificadores de erro específicos para uma condição de erro. Direcione os identificadores de erro para fins de diagnóstico e para scripts que manipulam condições de erro específicas com manipuladores de erro específicos. Um usuário deve ser capaz de usar o identificador de erro para identificar o erro e sua origem. Os identificadores de erro também permitem a emissão de relatórios para condições de erro específicas de exceções existentes para que novas subclasses de exceção não sejam necessárias.

- Em geral, atribua diferentes identificadores de erro a diferentes caminhos de código. Os benefícios do usuário final de identificadores específicos. Geralmente, cada caminho de código que chama [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) ou [System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) tem seu próprio identificador. Como regra, defina um novo identificador ao definir uma nova cadeia de caracteres de modelo para a mensagem de erro e vice-versa. Não use a mensagem de erro como um identificador.

- Quando você publica o código usando um identificador de erro específico, você estabelece a semântica de erros com esse identificador para o ciclo de vida completo do suporte ao produto. Não reutilize-o em um contexto que seja semanticamente diferente do contexto original. Se a semântica desse erro for alterada, crie e, em seguida, use um novo identificador.

- Em geral, você deve usar um determinado identificador de erro apenas para exceções de um determinado tipo CLR. Se o tipo da exceção ou o tipo do objeto de destino for alterado, crie e use um novo identificador.

- Escolha o texto para o identificador de erro que corresponde de forma concisa ao erro que você está relatando. Use as convenções padrão de .NET Framework de nomenclatura e de capitalização. Não use espaço em branco ou pontuação. Não Localize identificadores de erro.

- Não gere dinamicamente identificadores de erro de forma não reproduzível. Por exemplo, não incorpore informações de erro, como uma ID de processo. Os identificadores de erro são úteis apenas se corresponderem aos identificadores de erro vistos por outros usuários que estão enfrentando a mesma condição de erro.

## <a name="error-category"></a>Categoria do erro

Ao criar um registro de erro, especifique a categoria do erro usando uma das constantes definidas pela enumeração [System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0) . O Windows PowerShell usa a categoria de erro para exibir informações de erro quando os usuários definem a variável `$ErrorView` como `"CategoryView"`.

Evite usar a constante [System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0) **não especificada** . Se você tiver alguma informação sobre o erro ou sobre a operação que causou o erro, escolha a categoria que melhor descreve o erro ou a operação, mesmo que a categoria não seja uma correspondência perfeita.

As informações exibidas pelo Windows PowerShell são chamadas de cadeia de caracteres de exibição de categoria e são criadas a partir das propriedades da classe [System. Management. Automation. Errorcategoryinfo](/dotnet/api/System.Management.Automation.ErrorCategoryInfo) . (Essa classe é acessada por meio da propriedade [System. Management. Automation. ErrorRecord. CategoryInfo](/dotnet/api/System.Management.Automation.ErrorRecord.CategoryInfo) de erro.)

```
{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}
```

A lista a seguir descreve as informações exibidas:

- Categoria: uma constante [System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0) definida pelo Windows PowerShell.

- TargetName: por padrão, o nome do objeto que o cmdlet estava processando quando o erro ocorreu. Ou outra cadeia de caracteres definida pelo cmdlet.

- TargetType: por padrão, o tipo do objeto de destino. Ou outra cadeia de caracteres definida pelo cmdlet.

- Atividade: por padrão, o nome do cmdlet que criou o registro de erro. Ou qualquer outra cadeia de caracteres definida pelo cmdlet.

- Motivo: por padrão, o tipo de exceção. Ou outra cadeia de caracteres definida pelo cmdlet.

## <a name="replacement-error-message"></a>Mensagem de erro de substituição

Quando você desenvolve um registro de erro para um cmdlet, a mensagem de erro padrão do erro é proveniente do texto de mensagem padrão na propriedade [System. Exception. Message](/dotnet/api/System.Exception.Message) . Esta é uma propriedade somente leitura cujo texto de mensagem é destinado apenas para fins de depuração (de acordo com as diretrizes de .NET Framework). Recomendamos que você crie uma mensagem de erro que substitua ou aumente o texto da mensagem padrão. Torne a mensagem mais amigável e mais específica para o cmdlet.

A mensagem de substituição é fornecida por um objeto [System. Management. Automation. ErrorDetails](/dotnet/api/System.Management.Automation.ErrorDetails) . Use um dos construtores a seguir deste objeto porque eles fornecem informações de localização adicionais que podem ser usadas pelo Windows PowerShell.

- [ErrorDetails (cmdlet, Cadeia de caracteres, Cadeia de caracteres, objeto [])](/dotnet/api/system.management.automation.errordetails.-ctor?view=pscore-6.2.0#System_Management_Automation_ErrorDetails__ctor_System_Management_Automation_Cmdlet_System_String_System_String_System_Object___): Use esse construtor se a cadeia de caracteres do modelo for uma cadeia de caracteres de recurso no mesmo assembly no qual o cmdlet é implementado ou se você quiser carregar a cadeia de caracteres do modelo por meio de uma substituição do [ Método System. Management. Automation. cmdlet. GetResourceString](/dotnet/api/System.Management.Automation.Cmdlet.GetResourceString) .

- [ErrorDetails (assembly, String, String, Object [])](/dotnet/api/system.management.automation.errordetails.-ctor?view=pscore-6.2.0#System_Management_Automation_ErrorDetails__ctor_System_Reflection_Assembly_System_String_System_String_System_Object___): Use este construtor se a cadeia de caracteres do modelo estiver em outro assembly e você não carregá-lo por meio de uma substituição de [System. Management. Automation. cmdlet. GetResourceString](/dotnet/api/System.Management.Automation.Cmdlet.GetResourceString).

A mensagem de substituição deve estar em conformidade com as diretrizes de design de .NET Framework para gravar mensagens de exceção com uma pequena diferença. O estado das diretrizes que as mensagens de exceção devem ser gravadas para os desenvolvedores. Essas mensagens de substituição devem ser gravadas para o usuário do cmdlet.

A mensagem de erro de substituição deve ser adicionada antes dos métodos [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) ou [System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) serem chamados. Para adicionar uma mensagem de substituição, defina a propriedade [System. Management. Automation. ErrorRecord. ErrorDetails](/dotnet/api/System.Management.Automation.ErrorRecord.ErrorDetails) do registro de erros. Quando essa propriedade é definida, o Windows PowerShell exibe a propriedade [System. Management. Automation. ErrorDetails. Message *](/dotnet/api/System.Management.Automation.ErrorDetails.Message) em vez do texto da mensagem padrão.

## <a name="recommended-action-information"></a>Informações de ação recomendadas

O objeto [System. Management. Automation. ErrorDetails](/dotnet/api/System.Management.Automation.ErrorDetails) também pode fornecer informações sobre quais ações são recomendadas quando o erro ocorre.

## <a name="invocation-information"></a>Informações de invocação

Quando um cmdlet usa [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) ou [System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) para relatar um registro de erro, o Windows PowerShell adiciona automaticamente informações que descrevem o comando que foi invocado quando o erro ocorreu. Essas informações são fornecidas por um objeto [System. Management. Automation. InvocationInfo](/dotnet/api/System.Management.Automation.InvocationInfo) que contém o nome do cmdlet que foi invocado pelo comando, o próprio comando e as informações sobre o pipeline ou script. Esta propriedade é somente leitura.

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0)

[System. Management. Automation. Errorcategoryinfo](/dotnet/api/System.Management.Automation.ErrorCategoryInfo)

[System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)

[System. Management. Automation. ErrorDetails](/dotnet/api/System.Management.Automation.ErrorDetails)

[System. Management. Automation. InvocationInfo](/dotnet/api/System.Management.Automation.InvocationInfo)

[Relatório de erros do Windows PowerShell](./error-reporting-concepts.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
