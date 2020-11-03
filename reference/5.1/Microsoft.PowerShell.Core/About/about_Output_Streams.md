---
description: Explica a disponibilidade e a finalidade dos fluxos de saída no PowerShell.
keywords: PowerShell, cmdlet
Locale: en-US
ms.date: 10/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_output_streams?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Output_Streams
ms.openlocfilehash: 2f63c468f6b0d82559fca354a8ce5c1343eb2084
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196415"
---
# <a name="about-output-streams"></a>Sobre fluxos de saída

## <a name="short-description"></a>Descrição breve
Explica a disponibilidade e a finalidade dos fluxos de saída no PowerShell.

## <a name="long-description"></a>Descrição longa

O PowerShell fornece vários fluxos de saída. Os fluxos fornecem canais para diferentes tipos de mensagens. Você pode gravar nesses fluxos usando o cmdlet ou redirecionamento associado. Para obter mais informações, consulte [about_Redirection](about_Redirection.md).

O PowerShell dá suporte aos seguintes fluxos de saída.

| Fluxo # |      Descrição       | Introduzido em  |    Cmdlet de gravação     |
| -------- | ---------------------- | -------------- | ------------------- |
| 1        | Fluxo de **êxito**     | PowerShell 2.0 | `Write-Output`      |
| 2        | Fluxo de **erro**       | PowerShell 2.0 | `Write-Error`       |
| 3        | Fluxo de **aviso**     | PowerShell 3.0 | `Write-Warning`     |
| 4        | Fluxo **detalhado**     | PowerShell 3.0 | `Write-Verbose`     |
| 5        | Fluxo de **depuração**       | PowerShell 3.0 | `Write-Debug`       |
| 6        | Fluxo de **informações** | PowerShell 5.0 | `Write-Information` |
| N/D      | Fluxo de **progresso**    | PowerShell 3.0 | `Write-Progress`    |

> [!NOTE]
> O fluxo de **progresso** não dá suporte ao redirecionamento.

## <a name="success-stream"></a>Fluxo de êxito

O fluxo de **êxito** é o fluxo padrão para resultados normais e bem-sucedidos.
Use o `Write-Output` cmdlet para gravar objetos explicitamente nesse fluxo. Esse fluxo é usado para passar objetos por meio do pipeline do PowerShell. O fluxo de **êxito** é conectado ao fluxo **stdout** para aplicativos nativos.

## <a name="error-stream"></a>Fluxo de erro

O fluxo de **erro** é o fluxo padrão para resultados de erro. Use o `Write-Error` cmdlet para gravar explicitamente nesse fluxo. O fluxo de **erro** está conectado ao fluxo **stderr** para aplicativos nativos. Na maioria das condições, esses erros podem encerrar o pipeline de execução. Os erros gravados nesse fluxo também são adicionados à `$Error` variável automática. Para obter mais informações, consulte [about_Automatic_Variables](about_Automatic_Variables.md).

## <a name="warning-stream"></a>Fluxo de aviso

O fluxo de **aviso** destina-se a condições de erro menos graves do que erros gravados no fluxo de **erros** . Em condições normais, esses avisos não encerram a execução. Os avisos não são gravados na `$Error` variável automática. Use o `Write-Warning` cmdlet para gravar explicitamente nesse fluxo.

## <a name="verbose-stream"></a>Fluxo Detalhado

O fluxo **detalhado** destina-se a mensagens que ajudam os usuários a solucionar problemas de comandos à medida que são executados interativamente ou de um script. Use o `Write-Verbose` cmdlet para gravar mensagens explicitamente nesse fluxo. Muitos cmdlets fornecem uma saída detalhada que é útil para entender o funcionamento interno do cmdlet. As mensagens detalhadas são enviadas somente quando você usa o `-Verbose` parâmetro comum. Para obter mais informações, confira [about_CommonParameters](about_CommonParameters.md).

## <a name="debug-stream"></a>Fluxo de Depuração

O fluxo de **depuração** é usado para mensagens que ajudam os scripts a entender por que seu código está falhando. Use o `Write-Debug` cmdlet para gravar explicitamente nesse fluxo. As mensagens de depuração são enviadas somente quando você usa o `-Debug` parâmetro comum. Para obter mais informações, confira [about_CommonParameters](about_CommonParameters.md).

Mensagens de depuração destinam-se a desenvolvedores de script e de cmdlet mais do que usuários finais. Essas mensagens de depuração podem conter detalhes internos necessários para uma solução de problemas profunda.

## <a name="information-stream"></a>Fluxo de informações

O fluxo de **informações** destina-se a fornecer mensagens que ajudam um usuário a entender o que um script está fazendo. Ele também pode ser usado por desenvolvedores como um fluxo adicional usado para passar informações por meio do PowerShell. O desenvolvedor pode marcar dados de fluxo e ter um tratamento específico para esse fluxo. Use o `Write-Information` cmdlet para gravar explicitamente nesse fluxo.

## <a name="progress-stream"></a>Fluxo de progresso

O fluxo de **progresso** é usado para mensagens que comunicam o progresso em scripts e comandos em execução mais longos. Use o `Write-Progress` cmdlet para gravar mensagens explicitamente nesse fluxo. O fluxo de **progresso** não dá suporte ao redirecionamento.

## <a name="see-also"></a>Confira também

- [Write-Debug](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [Erro de gravação](xref:Microsoft.PowerShell.Utility.Write-Error)
- [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host)
- [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)
- [Write-Output](xref:Microsoft.PowerShell.Utility.Write-Output)
- [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [about_CommonParameters](about_CommonParameters.md)
- [about_Redirection](about_Redirection.md)
