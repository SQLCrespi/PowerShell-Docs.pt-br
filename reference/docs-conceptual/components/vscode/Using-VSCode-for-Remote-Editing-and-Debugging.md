---
title: Usando o Visual Studio Code para edição e depuração remotas
description: Usando o Visual Studio Code para edição e depuração remotas
ms.date: 08/06/2018
ms.openlocfilehash: fbc1ee3556e822b4afb2b37111d0688dc89fdab3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086656"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a>Usando o Visual Studio Code para edição e depuração remotas

Para aqueles que se familiarizaram com o ISE, talvez vocês se lembrem que podiam executar `psedit file.ps1` no console integrado para abrir arquivos locais ou remotos diretamente no ISE.

Como podemos ver, esse recurso também está disponível na extensão do PowerShell para VSCode. Este guia mostrará como fazê-lo.

## <a name="prerequisites"></a>Pré-requisitos

Este guia pressupõe que você tenha:

- Um recurso remoto (p.ex.: uma VM, um contêiner) ao qual você tenha acesso
- O PowerShell em execução nesse recurso e no computador host
- VSCode e a extensão do PowerShell para VSCode

Esse recurso funciona no Windows PowerShell e no PowerShell Core.

Esse recurso também funciona ao se conectar a um computador remoto via WinRM, PowerShell Direct ou SSH. Se você quer usar o SSH, mas está usando o Windows, consulte a [versão Win32 do SSH](https://github.com/PowerShell/Win32-OpenSSH)!

## <a name="lets-go"></a>Vamos lá

Nesta seção, vou detalhar a edição e a depuração remotas de uma VM Ubuntu em execução no Azure pelo meu MacBook Pro. Posso não estar usando o Windows, mas **o processo é idêntico**.

### <a name="local-file-editing-with-open-editorfile"></a>Edição de arquivo local com o Open-EditorFile

Com a extensão do PowerShell para VSCode iniciada e o Console Integrado do PowerShell aberto, podemos digitar `Open-EditorFile foo.ps1` ou `psedit foo.ps1` para abrir o arquivo foo.ps1 local diretamente no editor.

![O arquivo foo.ps1 no Open-EditorFile funciona localmente](https://user-images.githubusercontent.com/2644648/34895897-7c2c46ac-f79c-11e7-9410-a252aff52f13.png)

>[!NOTE]
> foo.ps1 já deve existir.

A partir daí, podemos:

adicionar pontos de interrupção à medianiz ![adicionando ponto de interrupção à medianiz](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)

e pressionar F5 para depurar o script do PowerShell.
![depurando o script local do PowerShell](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)

Durante a depuração, você pode interagir com o console de depuração, ver as variáveis no escopo à esquerda e todas as outras ferramentas de depuração padrão.

### <a name="remote-file-editing-with-open-editorfile"></a>Edição de arquivo remoto com o Open-EditorFile

Agora, vamos abordar a edição e a depuração de arquivo remoto. As etapas são praticamente as mesmas, com exceção de um pequeno detalhe: precisamos informar nossa sessão do PowerShell ao servidor remoto.

Há um cmdlet para fazer isso. Ele se chama `Enter-PSSession`.

A explicação básica do cmdlet é esta:

- `Enter-PSSession -ComputerName foo` inicia uma sessão via WinRM
- `Enter-PSSession -ContainerId foo` e `Enter-PSSession -VmId foo` iniciam uma sessão via PowerShell Direct
- `Enter-PSSession -HostName foo` inicia uma sessão via SSH

Para saber mais sobre `Enter-PSSession`, confira os documentos [aqui](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6).

Usarei SSH para a comunicação remota, pois vou passar de um macOS para uma VM Ubuntu no Azure.

Em primeiro lugar, no Console Integrado, vamos executar nosso Enter-PSSession. Você saberá que está na sessão porque `[something]` será mostrado à esquerda do seu prompt.

![A chamada a Enter-PSSession](https://user-images.githubusercontent.com/2644648/34895896-7c18e0bc-f79c-11e7-9b36-6f4bd0e9b0db.png)

Nela, podemos executar as mesmas etapas como se estivéssemos editando um script local.

1. Execute `Open-EditorFile test.ps1` ou `psedit test.ps1` para abrir o arquivo remoto `test.ps1` ![O arquivo test.ps1 do Open-EditorFile](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)
2. Edite os pontos de interrupção do arquivo/conjunto ![editar e definir pontos de interrupção](https://user-images.githubusercontent.com/2644648/34895892-7bb68246-f79c-11e7-8c0a-c2121773afbb.png)
3. Comece a depurar (F5) o arquivo remoto

![depurando o arquivo remoto](https://user-images.githubusercontent.com/2644648/34895895-7c040782-f79c-11e7-93ea-47724fa5c10d.png)

E isso é tudo! Esperamos que este guia tenha ajudado a esclarecer quaisquer dúvidas sobre a depuração e edição remotas do PowerShell no VSCode.

Em caso de problemas, fique à vontade para abrir ocorrências [no repositório GitHub](http://github.com/powershell/vscode-powershell).
