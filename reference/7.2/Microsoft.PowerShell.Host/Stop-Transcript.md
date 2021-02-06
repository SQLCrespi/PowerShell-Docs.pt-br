---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 16b41711e98276fee37d56f77f57e7372daa4cf3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597623"
---
# <span data-ttu-id="1342f-102">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="1342f-102">Stop-Transcript</span></span>

## <span data-ttu-id="1342f-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1342f-103">SYNOPSIS</span></span>
<span data-ttu-id="1342f-104">Interrompe uma transcrição.</span><span class="sxs-lookup"><span data-stu-id="1342f-104">Stops a transcript.</span></span>

## <span data-ttu-id="1342f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1342f-105">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="1342f-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1342f-106">DESCRIPTION</span></span>

<span data-ttu-id="1342f-107">O `Stop-Transcript` cmdlet interrompe uma transcrição que foi iniciada pelo `Start-Transcript` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1342f-107">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="1342f-108">Como alternativa, você pode encerrar uma sessão para interromper uma transcrição.</span><span class="sxs-lookup"><span data-stu-id="1342f-108">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="1342f-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1342f-109">EXAMPLES</span></span>

### <span data-ttu-id="1342f-110">Exemplo 1: parar todas as transcrições</span><span class="sxs-lookup"><span data-stu-id="1342f-110">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="1342f-111">Esse comando interrompe todas as transcrições.</span><span class="sxs-lookup"><span data-stu-id="1342f-111">This command stops all transcripts.</span></span>

## <span data-ttu-id="1342f-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1342f-112">PARAMETERS</span></span>

### <span data-ttu-id="1342f-113">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1342f-113">CommonParameters</span></span>

<span data-ttu-id="1342f-114">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1342f-114">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1342f-115">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1342f-115">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1342f-116">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1342f-116">INPUTS</span></span>

### <span data-ttu-id="1342f-117">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1342f-117">None</span></span>

<span data-ttu-id="1342f-118">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1342f-118">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="1342f-119">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1342f-119">OUTPUTS</span></span>

### <span data-ttu-id="1342f-120">System.String</span><span class="sxs-lookup"><span data-stu-id="1342f-120">System.String</span></span>

<span data-ttu-id="1342f-121">Esse cmdlet retorna uma cadeia de caracteres que contém uma mensagem de status e o caminho para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="1342f-121">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="1342f-122">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1342f-122">NOTES</span></span>

* <span data-ttu-id="1342f-123">Se uma transcrição não tiver sido iniciada, o comando falha.</span><span class="sxs-lookup"><span data-stu-id="1342f-123">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="1342f-124">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1342f-124">RELATED LINKS</span></span>

[<span data-ttu-id="1342f-125">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="1342f-125">Start-Transcript</span></span>](Start-Transcript.md)

