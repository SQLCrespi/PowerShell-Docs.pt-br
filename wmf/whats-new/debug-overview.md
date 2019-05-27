---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Melhorias na depuração de script do PowerShell
ms.openlocfilehash: f1771a451ba671da2371fcfc95374e6131573ddc
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855441"
---
# <a name="improvements-in-powershell-script-debugging"></a>Melhorias na depuração de script do PowerShell

O PowerShell 5.0 inclui várias melhorias para aprimorar a experiência de depuração.

## <a name="break-all"></a>Interromper Tudo

O console do PowerShell e o ISE do PowerShell agora permitem interromper o depurador para executar scripts. Isso funciona em sessões locais e remotas.

No console, pressione <kbd>Ctrl</kbd>+<kbd>Break</kbd>.

No ISE, pressione <kbd>Ctrl</kbd>+<kbd>B</kbd> ou use o comando de menu **Depurar -> Interromper Tudo**.

## <a name="remote-debugging-and-remote-file-editing-in-powershell-ise"></a>Depuração remota e edição de arquivos remota no ISE do PowerShell

O ISE do PowerShell agora permite abrir e editar arquivos em uma sessão remota com a execução do comando PSEdit.
Por exemplo, é possível abrir um arquivo para edição desde a linha de comando em uma sessão remota da seguinte maneira:

```powershell
[RemoteComputer1]: PS C:\> PSEdit C:\DebugDemoScripts\Test-GetMutex.ps1
```

Além disso, agora é possível editar e salvar alterações em um arquivo remoto aberto automaticamente no ISE do PowerShell ao atingir um ponto de interrupção. Agora, você pode depurar um arquivo de script que está em execução em um computador remoto, editar o arquivo para corrigir um erro e executar novamente o script modificado.

## <a name="advanced-script-debugging"></a>Depuração de script avançada

Há recursos de depuração novos e avançados que possibilitam anexar a qualquer processo de computador local que tenha carregado o PowerShell e depurar runspaces arbitrários no processo.

### <a name="runspace-debugging"></a>Depuração de runspaces

Foram adicionados novos cmdlets que permitem listar os runspaces atuais em um processo e anexar o console do PowerShell ou o depurador do ISE do PowerShell a esse runspace para a depuração de scripts:

- Get-Runspace
- Debug-Runspace
- Enable-RunspaceDebug
- Disable-RunspaceDebug
- Get-RunspaceDebug

### <a name="attach-to-process-hosting-powershell"></a>Anexar a um processo que hospeda o PowerShell

Agora é possível anexar a qualquer processo de computador que tenha o PowerShell carregado. Você pode fazer isso entrando em uma sessão interativa com o processo de host. Para obter mais informações, consulte:

- [Enter-PSHostProcess](/powershell/module/Microsoft.PowerShell.Core/Enter-PSHostProcess)
- [Exit-PSHostProcess](/powershell/module/Microsoft.PowerShell.Core/Exit-PSHostProcess)
