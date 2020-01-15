---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Alterando o estado do computador
ms.openlocfilehash: 9278df55ba027134a61c8ed4e89b5b839d460b29
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736906"
---
# <a name="changing-computer-state"></a>Alterando o estado do computador

Para redefinir um computador no PowerShell, use uma ferramenta de linha de comando padrão ou uma classe WMI ou CIM.
Embora você esteja usando o PowerShell somente para executar a ferramenta, aprender como alterar o estado de energia do computador no PowerShell ilustra alguns dos detalhes importantes sobre como trabalhar com ferramentas externas no PowerShell.

## <a name="locking-a-computer"></a>Bloquear um computador

A única maneira de bloquear um computador diretamente com as ferramentas padrão disponíveis é chamar a função **LockWorkstation ()** em **user32.dll**:

```powershell
rundll32.exe user32.dll,LockWorkStation
```

Esse comando bloqueia imediatamente a estação de trabalho. Ele usa o **rundll32.exe**, que executa DLLs Windows (e salva suas bibliotecas para uso repetido) para executar `user32.dll`, uma biblioteca de funções de gerenciamento do Windows.

Quando você bloqueia uma estação de trabalho enquanto a Troca Rápida de Usuário estiver habilitada, como no Windows XP, o computador exibe a tela de logon do usuário em vez de iniciar a proteção de tela do usuário atual.

Para encerrar uma sessão específica em um Servidor de Terminal, use a ferramenta de linha de comando **tsshutdn.exe**.

## <a name="logging-off-the-current-session"></a>Sair da sessão atual

Você pode usar várias técnicas diferentes para sair de uma sessão no sistema local. A maneira mais simples é usar a ferramenta de linha de comando Área de Trabalho Remota/Serviços de Terminal, **logoff.exe** (para obter mais detalhes, no prompt do PowerShell, digite `logoff /?`). Para fazer logoff da sessão ativa atual, digite `logoff` sem argumentos.

Você também pode usar a ferramenta **shutdown.exe** com a opção de fazer logoff:

```powershell
shutdown.exe -l
```

Outra opção é usar o WMI. A classe **Win32_OperatingSystem** tem um método **Shutdown**.
Chamar o método com o sinalizador 0 inicia o logoff:

Para saber mais sobre o método **Shutdown**, confira [Método Shutdown da Classe Win32_OperatingSystem](/windows/win32/cimwin32prov/shutdown-method-in-class-win32-operatingsystem)

```powershell
Get-CimInstance -Classname Win32_OperatingSystem | Invoke-CimMethod -MethodName Shutdown
```

## <a name="shutting-down-or-restarting-a-computer"></a>Desligar ou reiniciar um computador

Desligar e reiniciar computadores geralmente são os mesmos tipos de tarefa. Ferramentas que desligam um computador geralmente também o reiniciam e vice-versa. Há duas opções simples para reiniciar um computador pelo PowerShell. Use **tsshutdn.exe** ou **shutdown.exe** com os argumentos apropriados. Obtenha informações de uso detalhadas em `tsshutdn.exe /?` ou `shutdown.exe /?`.

Você também pode executar as operações de desligamento e reinicialização diretamente no PowerShell.

Para desligar o computador, use o comando Stop-Computer

```powershell
Stop-Computer
```

Para reiniciar o sistema operacional, use o comando Restart-Computer

```powershell
Restart-Computer
```

Para forçar uma reinicialização imediata do computador, use o parâmetro -Force.

```powershell
Restart-Computer -Force
```
