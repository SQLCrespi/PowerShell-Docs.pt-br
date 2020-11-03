---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 29a72bac55dd4aabca52673a192b13f75b88f308
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192594"
---
# <span data-ttu-id="531d8-103">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="531d8-103">Exit-PSHostProcess</span></span>

## <span data-ttu-id="531d8-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="531d8-104">SYNOPSIS</span></span>
<span data-ttu-id="531d8-105">Fecha uma sessão interativa com um processo local.</span><span class="sxs-lookup"><span data-stu-id="531d8-105">Closes an interactive session with a local process.</span></span>

## <span data-ttu-id="531d8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="531d8-106">SYNTAX</span></span>

```
Exit-PSHostProcess [<CommonParameters>]
```

## <span data-ttu-id="531d8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="531d8-107">DESCRIPTION</span></span>
<span data-ttu-id="531d8-108">O cmdlet **Exit-PSHostProcess** fecha uma sessão interativa com um processo local que você abriu executando o cmdlet Enter-PSHostProcess.</span><span class="sxs-lookup"><span data-stu-id="531d8-108">The **Exit-PSHostProcess** cmdlet closes an interactive session with a local process that you have opened by running the Enter-PSHostProcess cmdlet.</span></span>
<span data-ttu-id="531d8-109">Você executa o cmdlet **Exit-PSHostProcess** de dentro do processo, quando conclui a depuração ou a solução de problemas de um script que está sendo executado dentro de um processo.</span><span class="sxs-lookup"><span data-stu-id="531d8-109">You run the **Exit-PSHostProcess** cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process.</span></span>

## <span data-ttu-id="531d8-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="531d8-110">EXAMPLES</span></span>

### <span data-ttu-id="531d8-111">Exemplo 1: sair de um processo</span><span class="sxs-lookup"><span data-stu-id="531d8-111">Example 1: Exit a process</span></span>

```
PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

<span data-ttu-id="531d8-112">Neste exemplo, você esteve trabalhando em um processo ativo para depurar um script em execução em um runspace no processo, conforme descrito em Enter-PSHostProcess.</span><span class="sxs-lookup"><span data-stu-id="531d8-112">In this example, you have been working in an active process to debug a script running in a runspace in the process, as described in Enter-PSHostProcess.</span></span>
<span data-ttu-id="531d8-113">Depois de digitar o comando **Exit** para sair do depurador, execute o cmdlet **Exit-PSHostProcess** para fechar sua sessão interativa com o processo.</span><span class="sxs-lookup"><span data-stu-id="531d8-113">After you type the **exit** command to exit the debugger, run the **Exit-PSHostProcess** cmdlet to close your interactive session with the process.</span></span>
<span data-ttu-id="531d8-114">O cmdlet fecha a sessão no processo e retorna para o prompt PS C: \\ \> .</span><span class="sxs-lookup"><span data-stu-id="531d8-114">The cmdlet closes your session in the process, and returns you to the PS C:\\\> prompt.</span></span>

## <span data-ttu-id="531d8-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="531d8-115">PARAMETERS</span></span>

### <span data-ttu-id="531d8-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="531d8-116">CommonParameters</span></span>
<span data-ttu-id="531d8-117">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="531d8-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="531d8-118">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="531d8-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="531d8-119">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="531d8-119">INPUTS</span></span>

## <span data-ttu-id="531d8-120">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="531d8-120">OUTPUTS</span></span>

## <span data-ttu-id="531d8-121">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="531d8-121">NOTES</span></span>

## <span data-ttu-id="531d8-122">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="531d8-122">RELATED LINKS</span></span>

[<span data-ttu-id="531d8-123">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="531d8-123">Enter-PSHostProcess</span></span>](Enter-PSHostProcess.md)
