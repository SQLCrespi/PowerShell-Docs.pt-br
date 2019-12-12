---
title: Amostras de host personalizadas | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55aee25b-bbcb-4d41-a4c0-fb8e30c4cdc1
caps.latest.revision: 11
ms.openlocfilehash: 1e58b74cf1c37c70ebfb0f4970cfbf8a8263ec5c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367505"
---
# <a name="custom-host-samples"></a>Amostras de host personalizadas

Esta seção inclui um código de exemplo para a gravação de um host personalizado. Você pode usar Microsoft Visual Studio para criar um aplicativo de console e, em seguida, copiar o código dos tópicos nesta seção para seu aplicativo host.

## <a name="in-this-section"></a>Nesta seção

 [Exemplo de Host01](./host01-sample.md) Este exemplo mostra como implementar um aplicativo host que usa um host personalizado básico.

 [Exemplo de Host02](./host02-sample.md) Este exemplo mostra como gravar um aplicativo host que usa o tempo de execução do Windows PowerShell junto com uma implementação de host personalizada. O aplicativo host define a cultura do host como alemão, executa o cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) e exibe os resultados como você os veria usando pwrsh. exe e, em seguida, imprime os dados e a hora atuais em alemão.

 [Exemplo de Host03](./host03-sample.md) Este exemplo mostra como criar um aplicativo de host baseado em console interativo que lê os comandos da linha de comando, executa os comandos e, em seguida, exibe os resultados para o console.

 [Exemplo de Host04](./host04-sample.md) Este exemplo mostra como criar um aplicativo de host baseado em console interativo que lê os comandos da linha de comando, executa os comandos e, em seguida, exibe os resultados para o console. Esse aplicativo host também dá suporte a exibições de avisos que permitem ao usuário especificar várias opções.

 [Exemplo de Host05](./host05-sample.md) Este exemplo mostra como criar um aplicativo de host baseado em console interativo que lê os comandos da linha de comando, executa os comandos e, em seguida, exibe os resultados para o console. Esse aplicativo host também dá suporte a chamadas para computadores remotos usando os cmdlets [Enter-PSSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) e [Exit-PSSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession)

 [Exemplo de Host06](./host06-sample.md) Este exemplo mostra como criar um aplicativo de host baseado em console interativo que lê os comandos da linha de comando, executa os comandos e, em seguida, exibe os resultados para o console. Além disso, este exemplo usa as APIs do Criador de Token para especificar a cor do texto inserido pelo usuário.

## <a name="see-also"></a>Consulte Também
