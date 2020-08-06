---
title: Trabalhos em segundo plano | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2a1297b8dfe087474564078cca2a5a0526ed0f36
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774840"
---
# <a name="background-jobs"></a>Trabalhos em segundo plano

Os cmdlets podem executar suas ações internamente ou como um*trabalho em segundo plano*do Windows PowerShell. Quando um cmdlet é executado como um trabalho em segundo plano, o trabalho é feito de forma assíncrona em seu próprio thread separado do thread de pipeline que o cmdlet está usando. Da perspectiva do usuário, quando um cmdlet é executado como um trabalho em segundo plano, o prompt de comando retorna imediatamente, mesmo se o trabalho demorar um longo período de tempo para ser concluído, e o usuário poderá continuar sem interrupções enquanto o trabalho for executado.

## <a name="background-jobs-child-jobs-and-the-job-repository"></a>Trabalhos em segundo plano, trabalhos filho e o repositório de trabalhos

O objeto de trabalho que é retornado pelos cmdlets que oferecem suporte a trabalhos em segundo plano define o trabalho. (O cmdlet [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) também retorna um objeto de trabalho.) O nome do trabalho, um identificador que é usado para especificar o trabalho, as informações de estado e os trabalhos filho são incluídos nessa definição. O trabalho não executa nenhum trabalho. Cada trabalho em segundo plano tem pelo menos um trabalho filho porque o trabalho filho executa o trabalho real. Quando você executa um cmdlet para que o trabalho seja executado como um trabalho em segundo plano, o cmdlet deve adicionar o trabalho e os trabalhos filho a um repositório comum, chamado de *repositório de trabalhos*.

Para obter mais informações sobre como os trabalhos em segundo plano são tratados na linha de comando, consulte o seguinte:

- [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [about_Job_Details](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [about_Remote_Jobs](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a>Escrevendo um cmdlet que é executado como um trabalho em segundo plano

Para gravar um cmdlet que pode ser executado como um trabalho em segundo plano, você deve concluir as seguintes tarefas:

- Defina um `asJob` parâmetro de opção para que o usuário possa decidir se deseja executar o cmdlet como um trabalho em segundo plano.

- Crie um objeto derivado da classe [System. Management. Automation. Job](/dotnet/api/System.Management.Automation.Job) . Esse objeto pode ser um objeto de trabalho personalizado ou um objeto de trabalho fornecido pelo Windows PowerShell, como um objeto [System. Management. Automation. PSEventJob](/dotnet/api/System.Management.Automation.PSEventJob) .

- Em um método de processamento de registros, adicione uma `if` instrução que detecta se o cmdlet deve ser executado como um trabalho em segundo plano.

- Para objetos de trabalho personalizados, implemente a classe Job.

- Retorne os objetos apropriados, dependendo se o cmdlet é executado como um trabalho em segundo plano.

Para obter um exemplo de código, consulte [como dar suporte a trabalhos](./how-to-support-jobs.md).

## <a name="background-job-related-apis"></a>APIs relacionadas a trabalho em segundo plano

As APIs a seguir são fornecidas pelo Windows PowerShell para gerenciar trabalhos em segundo plano.

[System. Management. Automation. Job](/dotnet/api/System.Management.Automation.Job) deriva objetos de trabalho personalizados. Esta é uma classe abstrata.

[System. Management. Automation. Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) gerencia e fornece informações sobre os trabalhos em segundo plano ativos atuais.

[System. Management. Automation. JobState](/dotnet/api/System.Management.Automation.JobState) define o estado do trabalho em segundo plano. Os Estados incluem iniciado, em execução e parados.

[System. Management. Automation. JobStateInfo](/dotnet/api/System.Management.Automation.JobStateInfo) fornece informações sobre o estado de um trabalho em segundo plano e, se a última alteração de estado foi causada por um erro, o motivo pelo qual o trabalho entrou em seu estado atual.

[System. Management. Automation. Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) fornece os argumentos para um evento que é gerado quando um trabalho em segundo plano muda de estado.

## <a name="windows-powershell-job-cmdlets"></a>Cmdlets de trabalho do Windows PowerShell

Os cmdlets a seguir são fornecidos pelo Windows PowerShell para gerenciar trabalhos em segundo plano.

[Get-Job](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

Obtém trabalhos em segundo plano do Windows PowerShell que estão em execução na sessão atual.

[Receive-Job](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

Obtém os resultados dos trabalhos de plano de fundo do Windows PowerShell na sessão atual.

[Remove-Job](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

Exclui um trabalho em plano de fundo do Windows PowerShell.

[Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

Inicia um trabalho em segundo plano do Windows PowerShell.

[Stop-Job](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

Interrompe um trabalho em plano de fundo do Windows PowerShell.

[Wait-Job](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

Suprime o prompt de comando até que um ou todos os trabalhos em segundo plano do Windows PowerShell executados na sessão sejam concluídos.

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
