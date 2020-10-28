---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Alterando o estado do computador
description: Este exemplo mostra como você pode usar comandos externos do PowerShell para gerenciar a configuração de um computador.
ms.openlocfilehash: 341f29f24d7e4bd341ccc0954b16d4b75880678b
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500667"
---
# <a name="changing-computer-state"></a><span data-ttu-id="8e59d-104">Alterando o estado do computador</span><span class="sxs-lookup"><span data-stu-id="8e59d-104">Changing Computer State</span></span>

<span data-ttu-id="8e59d-105">Para redefinir um computador no PowerShell, use uma ferramenta de linha de comando padrão ou uma classe WMI ou CIM.</span><span class="sxs-lookup"><span data-stu-id="8e59d-105">To reset a computer in PowerShell, use either a standard command-line tool, WMI, or a CIM class.</span></span>
<span data-ttu-id="8e59d-106">Embora você esteja usando o PowerShell somente para executar a ferramenta, aprender como alterar o estado de energia do computador no PowerShell ilustra alguns dos detalhes importantes sobre como trabalhar com ferramentas externas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e59d-106">Although you are using PowerShell only to run the tool, learning how to change a computer's power state in PowerShell illustrates some of the important details about working with external tools in PowerShell.</span></span>

## <a name="locking-a-computer"></a><span data-ttu-id="8e59d-107">Bloquear um computador</span><span class="sxs-lookup"><span data-stu-id="8e59d-107">Locking a Computer</span></span>

<span data-ttu-id="8e59d-108">A única maneira de bloquear um computador diretamente com as ferramentas padrão disponíveis é chamar a função **LockWorkstation ()** em **user32.dll** :</span><span class="sxs-lookup"><span data-stu-id="8e59d-108">The only way to lock a computer directly with the standard available tools is to call the **LockWorkstation()** function in **user32.dll** :</span></span>

```powershell
rundll32.exe user32.dll,LockWorkStation
```

<span data-ttu-id="8e59d-109">Esse comando bloqueia imediatamente a estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8e59d-109">This command immediately locks the workstation.</span></span> <span data-ttu-id="8e59d-110">Ele usa o **rundll32.exe** , que executa DLLs Windows (e salva suas bibliotecas para uso repetido) para executar `user32.dll`, uma biblioteca de funções de gerenciamento do Windows.</span><span class="sxs-lookup"><span data-stu-id="8e59d-110">It uses **rundll32.exe** , which runs Windows DLLs (and saves their libraries for repeated use) to run `user32.dll`, a library of Windows management functions.</span></span>

<span data-ttu-id="8e59d-111">Quando você bloqueia uma estação de trabalho enquanto a Troca Rápida de Usuário estiver habilitada, como no Windows XP, o computador exibe a tela de logon do usuário em vez de iniciar a proteção de tela do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="8e59d-111">When you lock a workstation while Fast User Switching is enabled, such as on Windows XP, the computer displays the user logon screen rather than starting the current user's screensaver.</span></span>

<span data-ttu-id="8e59d-112">Para encerrar uma sessão específica em um Servidor de Terminal, use a ferramenta de linha de comando **tsshutdn.exe** .</span><span class="sxs-lookup"><span data-stu-id="8e59d-112">To shut down particular sessions on a Terminal Server, use the **tsshutdn.exe** command-line tool.</span></span>

## <a name="logging-off-the-current-session"></a><span data-ttu-id="8e59d-113">Sair da sessão atual</span><span class="sxs-lookup"><span data-stu-id="8e59d-113">Logging Off the Current Session</span></span>

<span data-ttu-id="8e59d-114">Você pode usar várias técnicas diferentes para sair de uma sessão no sistema local.</span><span class="sxs-lookup"><span data-stu-id="8e59d-114">You can use several different techniques to log off of a session on the local system.</span></span> <span data-ttu-id="8e59d-115">A maneira mais simples é usar a ferramenta de linha de comando Área de Trabalho Remota/Serviços de Terminal, **logoff.exe** (para obter mais detalhes, no prompt do PowerShell, digite `logoff /?`).</span><span class="sxs-lookup"><span data-stu-id="8e59d-115">The simplest way is to use the Remote Desktop/Terminal Services command-line tool, **logoff.exe** (For details, at the PowerShell prompt, type `logoff /?`).</span></span> <span data-ttu-id="8e59d-116">Para fazer logoff da sessão ativa atual, digite `logoff` sem argumentos.</span><span class="sxs-lookup"><span data-stu-id="8e59d-116">To log off the current active session, type `logoff` with no arguments.</span></span>

<span data-ttu-id="8e59d-117">Você também pode usar a ferramenta **shutdown.exe** com a opção de fazer logoff:</span><span class="sxs-lookup"><span data-stu-id="8e59d-117">You can also use the **shutdown.exe** tool with its logoff option:</span></span>

```powershell
shutdown.exe -l
```

<span data-ttu-id="8e59d-118">Outra opção é usar o WMI.</span><span class="sxs-lookup"><span data-stu-id="8e59d-118">Another option is to use WMI.</span></span> <span data-ttu-id="8e59d-119">A classe **Win32_OperatingSystem** tem um método **Shutdown** .</span><span class="sxs-lookup"><span data-stu-id="8e59d-119">The **Win32_OperatingSystem** class has a **Shutdown** method.</span></span>
<span data-ttu-id="8e59d-120">Chamar o método com o sinalizador 0 inicia o logoff:</span><span class="sxs-lookup"><span data-stu-id="8e59d-120">Invoking the method with the 0 flag initiates logoff:</span></span>

<span data-ttu-id="8e59d-121">Para saber mais sobre o método **Shutdown** , confira [Método Shutdown da Classe Win32_OperatingSystem](/windows/win32/cimwin32prov/shutdown-method-in-class-win32-operatingsystem)</span><span class="sxs-lookup"><span data-stu-id="8e59d-121">For more information about the **Shutdown** method, see [Shutdown method of the Win32_OperatingSystem class](/windows/win32/cimwin32prov/shutdown-method-in-class-win32-operatingsystem)</span></span>

```powershell
Get-CimInstance -Classname Win32_OperatingSystem | Invoke-CimMethod -MethodName Shutdown
```

## <a name="shutting-down-or-restarting-a-computer"></a><span data-ttu-id="8e59d-122">Desligar ou reiniciar um computador</span><span class="sxs-lookup"><span data-stu-id="8e59d-122">Shutting Down or Restarting a Computer</span></span>

<span data-ttu-id="8e59d-123">Desligar e reiniciar computadores geralmente são os mesmos tipos de tarefa.</span><span class="sxs-lookup"><span data-stu-id="8e59d-123">Shutting down and restarting computers are generally the same types of task.</span></span> <span data-ttu-id="8e59d-124">Ferramentas que desligam um computador geralmente também o reiniciam e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="8e59d-124">Tools that shut down a computer will generally restart it as well—and vice versa.</span></span> <span data-ttu-id="8e59d-125">Há duas opções simples para reiniciar um computador pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e59d-125">There are two straightforward options for restarting a computer from PowerShell.</span></span> <span data-ttu-id="8e59d-126">Use **tsshutdn.exe** ou **shutdown.exe** com os argumentos apropriados.</span><span class="sxs-lookup"><span data-stu-id="8e59d-126">Use either **tsshutdn.exe** or **shutdown.exe** with appropriate arguments.</span></span> <span data-ttu-id="8e59d-127">Obtenha informações de uso detalhadas em `tsshutdn.exe /?` ou `shutdown.exe /?`.</span><span class="sxs-lookup"><span data-stu-id="8e59d-127">You can get detailed usage information from `tsshutdn.exe /?` or `shutdown.exe /?`.</span></span>

<span data-ttu-id="8e59d-128">Você também pode executar as operações de desligamento e reinicialização diretamente no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e59d-128">You can also perform shutdown and restart operations directly from PowerShell as well.</span></span>

<span data-ttu-id="8e59d-129">Para desligar o computador, use o comando Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="8e59d-129">To shut down the computer, use the Stop-Computer command</span></span>

```powershell
Stop-Computer
```

<span data-ttu-id="8e59d-130">Para reiniciar o sistema operacional, use o comando Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="8e59d-130">To restart the operating system, use the Restart-Computer command</span></span>

```powershell
Restart-Computer
```

<span data-ttu-id="8e59d-131">Para forçar uma reinicialização imediata do computador, use o parâmetro -Force.</span><span class="sxs-lookup"><span data-stu-id="8e59d-131">To force an immediate restart of the computer, use the -Force parameter.</span></span>

```powershell
Restart-Computer -Force
```
