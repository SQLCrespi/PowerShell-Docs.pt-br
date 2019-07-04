---
title: Usando o Visual Studio Code para edição e depuração remotas
description: Usando o Visual Studio Code para edição e depuração remotas
ms.date: 06/13/2019
ms.openlocfilehash: ae3b7a3709498fcd547a48d0849b0dc880217225
ms.sourcegitcommit: 13f24786ed39ca1c07eff2b73a1974c366e31cb8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2019
ms.locfileid: "67263933"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a>Usando o Visual Studio Code para edição e depuração remotas

Para aqueles que se familiarizaram com o ISE, talvez se lembrem que podiam executar `psedit file.ps1` no console integrado para abrir arquivos locais ou remotos diretamente no ISE.

Esse recurso também está disponível na extensão do PowerShell para VSCode. Este guia mostra como fazê-lo.

## <a name="prerequisites"></a>Pré-requisitos

Este guia pressupõe que você tenha:

- Um recurso remoto (p.ex.: uma VM, um contêiner) ao qual você tenha acesso
- O PowerShell em execução nesse recurso e no computador host
- VSCode e a extensão do PowerShell para VSCode

Esse recurso funciona no Windows PowerShell e no PowerShell Core.

Esse recurso também funciona ao se conectar a um computador remoto via WinRM, PowerShell Direct ou SSH. Se você quer usar o SSH, mas está usando o Windows, consulte a [versão Win32 do SSH](https://github.com/PowerShell/Win32-OpenSSH)!

> [!IMPORTANT]
> Os comandos `Open-EditorFile` e `psedit` funcionam somente no **Console integrado do PowerShell** criado pela extensão do PowerShell para VSCode.

## <a name="usage-examples"></a>Exemplos de uso

Esses exemplos mostram a edição e a depuração remotas de uma VM Ubuntu em execução no Azure por um MacBook Pro. O processo é idêntico no Windows.

### <a name="local-file-editing-with-open-editorfile"></a>Edição de arquivo local com o Open-EditorFile

Com a extensão do PowerShell para VSCode iniciada e o Console Integrado do PowerShell aberto, podemos digitar `Open-EditorFile foo.ps1` ou `psedit foo.ps1` para abrir o arquivo foo.ps1 local diretamente no editor.

![O arquivo foo.ps1 no Open-EditorFile funciona localmente](images/Using-VSCode-for-Remote-Editing-and-Debugging/1-open-local-file.png)

>[!NOTE]
> O arquivo `foo.ps1` já deve existir.

A partir daí, podemos:

- Adicionar pontos de interrupção à medianiz

  ![adicionando pontos de interrupção à medianiz](images/Using-VSCode-for-Remote-Editing-and-Debugging/2-adding-breakpoint-gutter.png)

- Pressione F5 para depurar o script do PowerShell.

  ![depurando o script local do PowerShell](images/Using-VSCode-for-Remote-Editing-and-Debugging/3-local-debug.png)

Durante a depuração, você pode interagir com o console de depuração, ver as variáveis no escopo à esquerda e todas as outras ferramentas de depuração padrão.

### <a name="remote-file-editing-with-open-editorfile"></a>Edição de arquivo remoto com o Open-EditorFile

Agora, vamos abordar a edição e a depuração de arquivo remoto. As etapas são praticamente as mesmas, com exceção de um pequeno detalhe: precisamos informar nossa sessão do PowerShell ao servidor remoto.

Há um cmdlet para fazer isso. Ele se chama `Enter-PSSession`.

A explicação básica do cmdlet é esta:

- `Enter-PSSession -ComputerName foo` inicia uma sessão via WinRM
- `Enter-PSSession -ContainerId foo` e `Enter-PSSession -VmId foo` iniciam uma sessão via PowerShell Direct
- `Enter-PSSession -HostName foo` inicia uma sessão via SSH

Para saber mais, veja a documentação para o [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).

Como estamos passando de um macOS para uma VM Ubuntu no Azure, vamos usar SSH para a comunicação remota.

Primeiro, no Console Integrado, execute `Enter-PSSession`. Você estará conectado à sessão remota quando o `[<hostname>]` aparecer à esquerda de seu prompt.

![A chamada a Enter-PSSession](images/Using-VSCode-for-Remote-Editing-and-Debugging/4-enter-pssession.png)

Agora podemos executar as mesmas etapas como se estivéssemos editando um script local.

1. Execute `Open-EditorFile test.ps1` ou `psedit test.ps1` para abrir o arquivo `test.ps1` remoto

  ![Abrir o arquivo test.ps1 no EditorFile](images/Using-VSCode-for-Remote-Editing-and-Debugging/5-open-remote-file.png)

1. Edite os pontos de interrupção do arquivo/conjunto

   ![editar e definir pontos de interrupção](images/Using-VSCode-for-Remote-Editing-and-Debugging/6-set-breakpoints.png)

1. Comece a depurar (F5) o arquivo remoto

   ![depurando o arquivo remoto](images/Using-VSCode-for-Remote-Editing-and-Debugging/7-start-debugging.png)

Em caso de problemas, você pode abrir ocorrências [no repositório GitHub](https://github.com/powershell/vscode-powershell).
