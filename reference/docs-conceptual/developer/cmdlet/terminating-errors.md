---
title: Erros de encerramento | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 272e6cdd9a1da3cfd2e4f730f6aeb27577948278
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786383"
---
# <a name="terminating-errors"></a>Erros de encerramento

Este tópico discute o método usado para relatar erros de encerramento. Ele também aborda como chamar o método de dentro do cmdlet e aborda as exceções que podem ser retornadas pelo tempo de execução do Windows PowerShell quando o método é chamado.

Quando ocorre um erro de encerramento, o cmdlet deve relatar o erro chamando o método [System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) . Esse método permite que o cmdlet envie um registro de erro que descreve a condição que causou o erro de encerramento. Para obter mais informações sobre registros de erro, consulte [registros de erro do Windows PowerShell](./windows-powershell-error-records.md).

Quando o método [System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) é chamado, o tempo de execução do Windows PowerShell interrompe permanentemente a execução do pipeline e gera uma exceção de [System. Management. Automation. Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException) . Todas as tentativas subsequentes de chamar [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)ou várias outras APIs fazem com que essas chamadas gerem uma exceção de [System. Management. Automation. Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException) .

A exceção [System. Management. Automation. Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException) também pode ocorrer se outro cmdlet no pipeline relatar um erro de encerramento, se o usuário tiver solicitado a interromper o pipeline ou se o pipeline tiver sido interrompido antes da conclusão por qualquer motivo. O cmdlet não precisa capturar a exceção [System. Management. Automation. Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException) , a menos que ela deva limpar recursos abertos ou seu estado interno.

Os cmdlets podem gravar qualquer número de objetos de saída ou erros de não finalização antes de relatar um erro de encerramento. No entanto, o erro de encerramento interrompe permanentemente o pipeline e não é possível reportar outros erros de encerramento ou erros de não finalização.

Os cmdlets podem chamar [System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) somente a partir do thread que chamou o método [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)ou [System. Management. Automation. cmdlet.](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) endprocessation Input. Não tente chamar [System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) ou [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) de outro thread. Em vez disso, os erros devem ser comunicados de volta ao thread principal.

É possível que um cmdlet lance uma exceção em sua implementação do método [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)ou [System. Management. Automation. cmdlet. noprocessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) . Qualquer exceção gerada a partir desses métodos (com exceção de algumas condições de erro graves que interrompem o host do Windows PowerShell) é interpretada como um erro de encerramento que interrompe o pipeline, mas não o Windows PowerShell como um todo. (Isso se aplica somente ao thread do cmdlet principal. Exceções não capturadas em threads gerados pelo cmdlet, em geral, interrompem o host do Windows PowerShell.) Recomendamos que você use [System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) em vez de lançar uma exceção porque o registro de erro fornece informações adicionais sobre a condição de erro, que é útil para o usuário final. Os cmdlets devem honrar a diretriz de código gerenciado contra a captura e manipulação de todas as exceções ( `catch (Exception e)` ). Converta somente exceções de tipos conhecidos e esperados em registros de erros.

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[Sistema. Management. Automation. cmdlet. endprocessation](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System. Management. Automation. Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException)

[System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Registros de erros do Windows PowerShell](./windows-powershell-error-records.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
