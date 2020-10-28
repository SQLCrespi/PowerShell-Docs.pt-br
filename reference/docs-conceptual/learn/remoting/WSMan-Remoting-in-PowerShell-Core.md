---
title: Comunicação remota do WS-Management (WSMan) no PowerShell Core
description: Comunicação remota do WSMan no PowerShell Core
ms.date: 08/06/2018
ms.openlocfilehash: fdc4159279db28b8ee60bc0853e19512a1f9ec14
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501296"
---
# <a name="ws-management-wsman-remoting-in-powershell-core"></a><span data-ttu-id="c6164-103">Comunicação remota do WS-Management (WSMan) no PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="c6164-103">WS-Management (WSMan) Remoting in PowerShell Core</span></span>

## <a name="instructions-to-create-a-remoting-endpoint"></a><span data-ttu-id="c6164-104">Instruções para criar um ponto de extremidade de comunicação remota</span><span class="sxs-lookup"><span data-stu-id="c6164-104">Instructions to Create a Remoting Endpoint</span></span>

<span data-ttu-id="c6164-105">O pacote do PowerShell Core para Windows inclui um plug-in WinRM (`pwrshplugin.dll`) e um script de instalação (`Install-PowerShellRemoting.ps1`) em `$PSHome`.</span><span class="sxs-lookup"><span data-stu-id="c6164-105">The PowerShell Core package for Windows includes a WinRM plug-in (`pwrshplugin.dll`) and an installation script (`Install-PowerShellRemoting.ps1`) in `$PSHome`.</span></span> <span data-ttu-id="c6164-106">Esses arquivos permitem que o PowerShell aceite conexões remotas de entrada do PowerShell quando seu ponto de extremidade é especificado.</span><span class="sxs-lookup"><span data-stu-id="c6164-106">These files enable PowerShell to accept incoming PowerShell remote connections when its endpoint is specified.</span></span>

### <a name="motivation"></a><span data-ttu-id="c6164-107">Motivação</span><span class="sxs-lookup"><span data-stu-id="c6164-107">Motivation</span></span>

<span data-ttu-id="c6164-108">Uma instalação do PowerShell pode estabelecer sessões de PowerShell para computadores remotos usando `New-PSSession` e `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="c6164-108">An installation of PowerShell can establish PowerShell sessions to remote computers using `New-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="c6164-109">Para habilitá-lo a aceitar conexões remotas de entrada do PowerShell, o usuário deve criar um ponto de extremidade de comunicação remota do WinRM.</span><span class="sxs-lookup"><span data-stu-id="c6164-109">To enable it to accept incoming PowerShell remote connections, the user must create a WinRM remoting endpoint.</span></span> <span data-ttu-id="c6164-110">Esse é um cenário de aceitação explícita em que o usuário executa Install-PowerShellRemoting.ps1 para criar o ponto de extremidade do WinRM.</span><span class="sxs-lookup"><span data-stu-id="c6164-110">This is an explicit opt-in scenario where the user runs Install-PowerShellRemoting.ps1 to create the WinRM endpoint.</span></span> <span data-ttu-id="c6164-111">O script de instalação é uma solução de curto prazo, até que possamos adicionar funcionalidade adicional a `Enable-PSRemoting` para executar a mesma ação.</span><span class="sxs-lookup"><span data-stu-id="c6164-111">The installation script is a short-term solution until we add additional functionality to `Enable-PSRemoting` to perform the same action.</span></span> <span data-ttu-id="c6164-112">Para obter mais detalhes, veja o problema [#1193](https://github.com/PowerShell/PowerShell/issues/1193).</span><span class="sxs-lookup"><span data-stu-id="c6164-112">For more details, please see issue [#1193](https://github.com/PowerShell/PowerShell/issues/1193).</span></span>

### <a name="script-actions"></a><span data-ttu-id="c6164-113">Ações de script</span><span class="sxs-lookup"><span data-stu-id="c6164-113">Script Actions</span></span>

<span data-ttu-id="c6164-114">O script</span><span class="sxs-lookup"><span data-stu-id="c6164-114">The script</span></span>

1. <span data-ttu-id="c6164-115">Cria um diretório para o plug-in em `$env:windir\System32\PowerShell`</span><span class="sxs-lookup"><span data-stu-id="c6164-115">Creates a directory for the plug-in within `$env:windir\System32\PowerShell`</span></span>
1. <span data-ttu-id="c6164-116">Copia pwrshplugin.dll para esse local</span><span class="sxs-lookup"><span data-stu-id="c6164-116">Copies pwrshplugin.dll to that location</span></span>
1. <span data-ttu-id="c6164-117">Gera um arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="c6164-117">Generates a configuration file</span></span>
1. <span data-ttu-id="c6164-118">Registra esse plug-in no WinRM</span><span class="sxs-lookup"><span data-stu-id="c6164-118">Registers that plug-in with WinRM</span></span>

### <a name="registration"></a><span data-ttu-id="c6164-119">Registro</span><span class="sxs-lookup"><span data-stu-id="c6164-119">Registration</span></span>

<span data-ttu-id="c6164-120">O script deve ser executado em uma sessão do PowerShell de nível de administrador e é executado em dois modos.</span><span class="sxs-lookup"><span data-stu-id="c6164-120">The script must be executed within an Administrator-level PowerShell session and runs in two modes.</span></span>

#### <a name="executed-by-the-instance-of-powershell-that-it-will-register"></a><span data-ttu-id="c6164-121">Executado pela instância do PowerShell que ele registrará</span><span class="sxs-lookup"><span data-stu-id="c6164-121">Executed by the instance of PowerShell that it will register</span></span>

```powershell
Install-PowerShellRemoting.ps1
```

#### <a name="executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register"></a><span data-ttu-id="c6164-122">Executado por outra instância do PowerShell em nome de instância que ele registrará</span><span class="sxs-lookup"><span data-stu-id="c6164-122">Executed by another instance of PowerShell on behalf of the instance that it will register</span></span>

```powershell
<path to powershell>\Install-PowerShellRemoting.ps1 -PowerShellHome "<absolute path to the instance's $PSHOME>"
```

<span data-ttu-id="c6164-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c6164-123">For Example:</span></span>

```powershell
Set-Location -Path 'C:\Program Files\PowerShell\6.0.0\'
.\Install-PowerShellRemoting.ps1 -PowerShellHome "C:\Program Files\PowerShell\6.0.0\"
```

> [!NOTE]
> <span data-ttu-id="c6164-124">O script de Registro remoto reinicia o WinRM.</span><span class="sxs-lookup"><span data-stu-id="c6164-124">The remoting registration script restarts WinRM.</span></span> <span data-ttu-id="c6164-125">Todas as sessões de PSRP existentes são encerradas imediatamente depois que o script é executado.</span><span class="sxs-lookup"><span data-stu-id="c6164-125">All existing PSRP sessions are terminate immediately after the script is run.</span></span> <span data-ttu-id="c6164-126">Se executado durante uma sessão remota, o script encerrará a conexão.</span><span class="sxs-lookup"><span data-stu-id="c6164-126">If run during a remote session, the script terminates the connection.</span></span>

## <a name="how-to-connect-to-the-new-endpoint"></a><span data-ttu-id="c6164-127">Como se conectar ao novo ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="c6164-127">How to Connect to the New Endpoint</span></span>

<span data-ttu-id="c6164-128">Crie uma sessão do PowerShell para o novo ponto de extremidade do PowerShell, especificando `-ConfigurationName "some endpoint name"`.</span><span class="sxs-lookup"><span data-stu-id="c6164-128">Create a PowerShell session to the new PowerShell endpoint by specifying `-ConfigurationName "some endpoint name"`.</span></span> <span data-ttu-id="c6164-129">Para se conectar à instância do PowerShell do exemplo acima, use:</span><span class="sxs-lookup"><span data-stu-id="c6164-129">To connect to the PowerShell instance from the example above, use either:</span></span>

```powershell
New-PSSession ... -ConfigurationName "powershell.6.0.0"
Enter-PSSession ... -ConfigurationName "powershell.6.0.0"
```

<span data-ttu-id="c6164-130">Observe que as invocações `New-PSSession` e `Enter-PSSession` que não especificam `-ConfigurationName` têm como destino o ponto de extremidade padrão do PowerShell, `microsoft.powershell`.</span><span class="sxs-lookup"><span data-stu-id="c6164-130">Note that `New-PSSession` and `Enter-PSSession` invocations that do not specify `-ConfigurationName` will target the default PowerShell endpoint, `microsoft.powershell`.</span></span>
