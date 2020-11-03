---
description: Explica como usar o recurso "executar com o PowerShell" para executar um script de uma unidade do sistema de arquivos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_run_with_powershell?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Run_With_PowerShell
ms.openlocfilehash: 28eb4b6d7419ffa52ce205cfea8521bf51e9021f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195972"
---
# <a name="about-run-with-powershell"></a>Sobre a execução com o PowerShell

## <a name="short-description"></a>DESCRIÇÃO BREVE

Explica como usar o recurso "executar com o PowerShell" para executar um script de uma unidade do sistema de arquivos.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A partir do Windows PowerShell 3,0, você pode usar o recurso "executar com o PowerShell" para executar scripts do explorador de arquivos no Windows 8 e no Windows Server 2012 e no Windows Explorer em versões anteriores do Windows.

O recurso "executar com o PowerShell" foi projetado para executar scripts que não têm parâmetros obrigatórios e não retornam a saída para o prompt de comando.

Quando você usa o recurso "executar com o PowerShell", a janela do console do Windows PowerShell é exibida apenas brevemente, se houver. Você não pode interagir com ele.

Para usar o recurso "executar com o PowerShell":

No explorador de arquivos (ou no Windows Explorer), clique com o botão direito do mouse no nome do arquivo de script e selecione "executar com o PowerShell".

O recurso "executar com o PowerShell" inicia uma sessão do Windows PowerShell que tem uma política de execução de bypass, executa o script e fecha a sessão.

Ele executa um comando que tem o seguinte formato:

```
PowerShell.exe -File <FileName> -ExecutionPolicy Bypass
```

"Executar com o PowerShell" define a política de execução de bypass somente para a sessão (a instância atual do processo do PowerShell) na qual o script é executado.
Esse recurso não altera a política de execução para o computador ou o usuário.

O recurso "executar com o PowerShell" é afetado somente pela política de execução AllSigned. Se a política de execução AllSigned estiver em vigor para o computador ou o usuário, "executar com o PowerShell" executará somente scripts assinados. "Executar com o PowerShell" não é afetado por nenhuma outra política de execução. Para obter mais informações, consulte [about_Execution_Policies](about_Execution_Policies.md).

Observação de solução de problemas: executar com o comando do PowerShell pode solicitar que você confirme a alteração da política de execução.

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Execution_Policies](about_Execution_Policies.md)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_Scripts](about_Scripts.md)
