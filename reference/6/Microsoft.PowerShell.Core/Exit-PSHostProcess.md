---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 1734758d34e89020f579fffa217cef58eb222736
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344041"
---
# <span data-ttu-id="7590c-103">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="7590c-103">Exit-PSHostProcess</span></span>

## <span data-ttu-id="7590c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7590c-104">SYNOPSIS</span></span>
<span data-ttu-id="7590c-105">Fecha uma sessão interativa com um processo local.</span><span class="sxs-lookup"><span data-stu-id="7590c-105">Closes an interactive session with a local process.</span></span>

## <span data-ttu-id="7590c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7590c-106">SYNTAX</span></span>

```
Exit-PSHostProcess [<CommonParameters>]
```

## <span data-ttu-id="7590c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7590c-107">DESCRIPTION</span></span>

<span data-ttu-id="7590c-108">O `Exit-PSHostProcess` cmdlet fecha uma sessão interativa com um processo local que você abriu executando o `Enter-PSHostProcess` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7590c-108">The `Exit-PSHostProcess` cmdlet closes an interactive session with a local process that you have opened by running the `Enter-PSHostProcess` cmdlet.</span></span> <span data-ttu-id="7590c-109">Você executa o `Exit-PSHostProcess` cmdlet de dentro do processo, quando conclui a depuração ou a solução de problemas de um script que está sendo executado dentro de um processo.</span><span class="sxs-lookup"><span data-stu-id="7590c-109">You run the `Exit-PSHostProcess` cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process.</span></span> <span data-ttu-id="7590c-110">A partir do PowerShell 6,2, esse cmdlet tem suporte em plataformas que não são do Windows.</span><span class="sxs-lookup"><span data-stu-id="7590c-110">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="7590c-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7590c-111">EXAMPLES</span></span>

### <span data-ttu-id="7590c-112">Exemplo 1: sair de um processo</span><span class="sxs-lookup"><span data-stu-id="7590c-112">Example 1: Exit a process</span></span>

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

<span data-ttu-id="7590c-113">Neste exemplo, você esteve trabalhando em um processo ativo para depurar um script em execução em um runspace no processo, conforme descrito em `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="7590c-113">In this example, you have been working in an active process to debug a script running in a runspace in the process, as described in `Enter-PSHostProcess`.</span></span> <span data-ttu-id="7590c-114">Depois de digitar o `exit` comando para sair do depurador, execute o `Exit-PSHostProcess` cmdlet para fechar sua sessão interativa com o processo.</span><span class="sxs-lookup"><span data-stu-id="7590c-114">After you type the `exit` command to exit the debugger, run the `Exit-PSHostProcess` cmdlet to close your interactive session with the process.</span></span>
<span data-ttu-id="7590c-115">O cmdlet fecha a sessão no processo e retorna para o `PS C:\>` prompt.</span><span class="sxs-lookup"><span data-stu-id="7590c-115">The cmdlet closes your session in the process, and returns you to the `PS C:\>` prompt.</span></span>

## <span data-ttu-id="7590c-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7590c-116">PARAMETERS</span></span>

### <span data-ttu-id="7590c-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7590c-117">CommonParameters</span></span>

<span data-ttu-id="7590c-118">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7590c-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7590c-119">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7590c-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7590c-120">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7590c-120">INPUTS</span></span>

## <span data-ttu-id="7590c-121">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7590c-121">OUTPUTS</span></span>

## <span data-ttu-id="7590c-122">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7590c-122">NOTES</span></span>

## <span data-ttu-id="7590c-123">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7590c-123">RELATED LINKS</span></span>

[<span data-ttu-id="7590c-124">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="7590c-124">Enter-PSHostProcess</span></span>](Enter-PSHostProcess.md)
