---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 86903ca648ff3ee58ec939143b7881741827f453
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192668"
---
# <span data-ttu-id="ee64e-103">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="ee64e-103">Stop-Transcript</span></span>

## <span data-ttu-id="ee64e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ee64e-104">SYNOPSIS</span></span>
<span data-ttu-id="ee64e-105">Interrompe uma transcrição.</span><span class="sxs-lookup"><span data-stu-id="ee64e-105">Stops a transcript.</span></span>

## <span data-ttu-id="ee64e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ee64e-106">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="ee64e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ee64e-107">DESCRIPTION</span></span>

<span data-ttu-id="ee64e-108">O `Stop-Transcript` cmdlet interrompe uma transcrição que foi iniciada pelo `Start-Transcript` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ee64e-108">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="ee64e-109">Como alternativa, você pode encerrar uma sessão para interromper uma transcrição.</span><span class="sxs-lookup"><span data-stu-id="ee64e-109">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="ee64e-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ee64e-110">EXAMPLES</span></span>

### <span data-ttu-id="ee64e-111">Exemplo 1: parar todas as transcrições</span><span class="sxs-lookup"><span data-stu-id="ee64e-111">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="ee64e-112">Esse comando interrompe todas as transcrições.</span><span class="sxs-lookup"><span data-stu-id="ee64e-112">This command stops all transcripts.</span></span>

## <span data-ttu-id="ee64e-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ee64e-113">PARAMETERS</span></span>

### <span data-ttu-id="ee64e-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ee64e-114">CommonParameters</span></span>

<span data-ttu-id="ee64e-115">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ee64e-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ee64e-116">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ee64e-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ee64e-117">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ee64e-117">INPUTS</span></span>

### <span data-ttu-id="ee64e-118">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ee64e-118">None</span></span>

<span data-ttu-id="ee64e-119">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ee64e-119">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="ee64e-120">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ee64e-120">OUTPUTS</span></span>

### <span data-ttu-id="ee64e-121">System.String</span><span class="sxs-lookup"><span data-stu-id="ee64e-121">System.String</span></span>

<span data-ttu-id="ee64e-122">Esse cmdlet retorna uma cadeia de caracteres que contém uma mensagem de status e o caminho para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="ee64e-122">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="ee64e-123">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ee64e-123">NOTES</span></span>

* <span data-ttu-id="ee64e-124">Se uma transcrição não tiver sido iniciada, o comando falha.</span><span class="sxs-lookup"><span data-stu-id="ee64e-124">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="ee64e-125">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ee64e-125">RELATED LINKS</span></span>

[<span data-ttu-id="ee64e-126">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="ee64e-126">Start-Transcript</span></span>](Start-Transcript.md)

