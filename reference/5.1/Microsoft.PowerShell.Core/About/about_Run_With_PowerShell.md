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
# <a name="about-run-with-powershell"></a><span data-ttu-id="86fb4-104">Sobre a execução com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="86fb4-104">About Run With PowerShell</span></span>

## <a name="short-description"></a><span data-ttu-id="86fb4-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="86fb4-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="86fb4-106">Explica como usar o recurso "executar com o PowerShell" para executar um script de uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="86fb4-106">Explains how to use the "Run with PowerShell" feature to run a script from a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="86fb4-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="86fb4-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="86fb4-108">A partir do Windows PowerShell 3,0, você pode usar o recurso "executar com o PowerShell" para executar scripts do explorador de arquivos no Windows 8 e no Windows Server 2012 e no Windows Explorer em versões anteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="86fb4-108">Beginning in Windows PowerShell 3.0, you can use the "Run with PowerShell" feature to run scripts from File Explorer in Windows 8 and Windows Server 2012 and from Windows Explorer in earlier versions of Windows.</span></span>

<span data-ttu-id="86fb4-109">O recurso "executar com o PowerShell" foi projetado para executar scripts que não têm parâmetros obrigatórios e não retornam a saída para o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="86fb4-109">The "Run with PowerShell" feature is designed to run scripts that do not have required parameters and do not return output to the command prompt.</span></span>

<span data-ttu-id="86fb4-110">Quando você usa o recurso "executar com o PowerShell", a janela do console do Windows PowerShell é exibida apenas brevemente, se houver.</span><span class="sxs-lookup"><span data-stu-id="86fb4-110">When you use the "Run with PowerShell" feature, the Windows PowerShell console window appears only briefly, if at all.</span></span> <span data-ttu-id="86fb4-111">Você não pode interagir com ele.</span><span class="sxs-lookup"><span data-stu-id="86fb4-111">You cannot interact with it.</span></span>

<span data-ttu-id="86fb4-112">Para usar o recurso "executar com o PowerShell":</span><span class="sxs-lookup"><span data-stu-id="86fb4-112">To use the "Run with PowerShell" feature:</span></span>

<span data-ttu-id="86fb4-113">No explorador de arquivos (ou no Windows Explorer), clique com o botão direito do mouse no nome do arquivo de script e selecione "executar com o PowerShell".</span><span class="sxs-lookup"><span data-stu-id="86fb4-113">In File Explorer (or Windows Explorer), right-click the script file name and then select "Run with PowerShell".</span></span>

<span data-ttu-id="86fb4-114">O recurso "executar com o PowerShell" inicia uma sessão do Windows PowerShell que tem uma política de execução de bypass, executa o script e fecha a sessão.</span><span class="sxs-lookup"><span data-stu-id="86fb4-114">The "Run with PowerShell" feature starts a Windows PowerShell session that has an execution policy of Bypass, runs the script, and closes the session.</span></span>

<span data-ttu-id="86fb4-115">Ele executa um comando que tem o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="86fb4-115">It runs a command that has the following format:</span></span>

```
PowerShell.exe -File <FileName> -ExecutionPolicy Bypass
```

<span data-ttu-id="86fb4-116">"Executar com o PowerShell" define a política de execução de bypass somente para a sessão (a instância atual do processo do PowerShell) na qual o script é executado.</span><span class="sxs-lookup"><span data-stu-id="86fb4-116">"Run with PowerShell" sets the Bypass execution policy only for the session (the current instance of the PowerShell process) in which the script runs.</span></span>
<span data-ttu-id="86fb4-117">Esse recurso não altera a política de execução para o computador ou o usuário.</span><span class="sxs-lookup"><span data-stu-id="86fb4-117">This feature does not change the execution policy for the computer or the user.</span></span>

<span data-ttu-id="86fb4-118">O recurso "executar com o PowerShell" é afetado somente pela política de execução AllSigned.</span><span class="sxs-lookup"><span data-stu-id="86fb4-118">The "Run with PowerShell" feature is affected only by the AllSigned execution policy.</span></span> <span data-ttu-id="86fb4-119">Se a política de execução AllSigned estiver em vigor para o computador ou o usuário, "executar com o PowerShell" executará somente scripts assinados.</span><span class="sxs-lookup"><span data-stu-id="86fb4-119">If the AllSigned execution policy is effective for the computer or the user, "Run with PowerShell" runs only signed scripts.</span></span> <span data-ttu-id="86fb4-120">"Executar com o PowerShell" não é afetado por nenhuma outra política de execução.</span><span class="sxs-lookup"><span data-stu-id="86fb4-120">"Run with PowerShell" is not affected by any other execution policy.</span></span> <span data-ttu-id="86fb4-121">Para obter mais informações, consulte [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="86fb4-121">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="86fb4-122">Observação de solução de problemas: executar com o comando do PowerShell pode solicitar que você confirme a alteração da política de execução.</span><span class="sxs-lookup"><span data-stu-id="86fb4-122">Troubleshooting Note: Run with PowerShell command might prompt you to confirm the execution policy change.</span></span>

## <a name="see-also"></a><span data-ttu-id="86fb4-123">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="86fb4-123">SEE ALSO</span></span>

[<span data-ttu-id="86fb4-124">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="86fb4-124">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="86fb4-125">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="86fb4-125">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="86fb4-126">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="86fb4-126">about_Scripts</span></span>](about_Scripts.md)
