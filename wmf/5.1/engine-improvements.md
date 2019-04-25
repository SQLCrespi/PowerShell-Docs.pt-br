---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,instalação
title: Melhorias do Mecanismo do PowerShell no WMF 5.1
ms.openlocfilehash: 738f72b910de7d44f48309013237d523d0dd40a4
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055557"
---
# <a name="powershell-engine-improvements"></a><span data-ttu-id="a45fc-103">Melhorias ao Mecanismo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a45fc-103">PowerShell Engine Improvements</span></span>

<span data-ttu-id="a45fc-104">As seguintes melhorias ao mecanismo principal do PowerShell foram implementadas no WMF 5.1:</span><span class="sxs-lookup"><span data-stu-id="a45fc-104">The following improvements to the core PowerShell engine have been implemented in WMF 5.1:</span></span>

## <a name="performance"></a><span data-ttu-id="a45fc-105">Desempenho</span><span class="sxs-lookup"><span data-stu-id="a45fc-105">Performance</span></span>

<span data-ttu-id="a45fc-106">O desempenho melhorou em algumas áreas importantes:</span><span class="sxs-lookup"><span data-stu-id="a45fc-106">Performance has improved in some important areas:</span></span>

- <span data-ttu-id="a45fc-107">Inicialização</span><span class="sxs-lookup"><span data-stu-id="a45fc-107">Startup</span></span>
- <span data-ttu-id="a45fc-108">O pipeline para cmdlets como `ForEach-Object` e `Where-Object` é aproximadamente 50% mais rápido</span><span class="sxs-lookup"><span data-stu-id="a45fc-108">Pipelining to cmdlets like `ForEach-Object` and `Where-Object` is approximately 50% faster</span></span>

<span data-ttu-id="a45fc-109">Alguns exemplos de melhorias (os resultados podem variar dependendo do hardware):</span><span class="sxs-lookup"><span data-stu-id="a45fc-109">Some example improvements (your results may vary depending on your hardware):</span></span>

| <span data-ttu-id="a45fc-110">Cenário</span><span class="sxs-lookup"><span data-stu-id="a45fc-110">Scenario</span></span> | <span data-ttu-id="a45fc-111">Tempo de 5,0 (ms)</span><span class="sxs-lookup"><span data-stu-id="a45fc-111">5.0 Time (ms)</span></span> | <span data-ttu-id="a45fc-112">Tempo de 5,1 (ms)</span><span class="sxs-lookup"><span data-stu-id="a45fc-112">5.1 Time (ms)</span></span> |
| -------- | :---------------: | :---------------: |
| `powershell -command "echo 1"` | <span data-ttu-id="a45fc-113">900</span><span class="sxs-lookup"><span data-stu-id="a45fc-113">900</span></span> | <span data-ttu-id="a45fc-114">250</span><span class="sxs-lookup"><span data-stu-id="a45fc-114">250</span></span> |
| <span data-ttu-id="a45fc-115">Primeira execução do PowerShell: `powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="a45fc-115">First ever PowerShell run: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="a45fc-116">30000</span><span class="sxs-lookup"><span data-stu-id="a45fc-116">30000</span></span> | <span data-ttu-id="a45fc-117">13000</span><span class="sxs-lookup"><span data-stu-id="a45fc-117">13000</span></span> |
| <span data-ttu-id="a45fc-118">Built do cache de análise de comando: `powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="a45fc-118">Command analysis cache built: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="a45fc-119">7000</span><span class="sxs-lookup"><span data-stu-id="a45fc-119">7000</span></span> | <span data-ttu-id="a45fc-120">520</span><span class="sxs-lookup"><span data-stu-id="a45fc-120">520</span></span> |
| <code>1..1000000 &#124; % { }</code> | <span data-ttu-id="a45fc-121">1400</span><span class="sxs-lookup"><span data-stu-id="a45fc-121">1400</span></span> | <span data-ttu-id="a45fc-122">750</span><span class="sxs-lookup"><span data-stu-id="a45fc-122">750</span></span> |

> [!Note]
> <span data-ttu-id="a45fc-123">Uma alteração relacionada à inicialização pode afetar alguns cenários sem suporte.</span><span class="sxs-lookup"><span data-stu-id="a45fc-123">One change related to startup might impact some unsupported scenarios.</span></span>
> <span data-ttu-id="a45fc-124">O PowerShell não lê mais os arquivos `$pshome\*.ps1xml` – esses arquivos foram convertidos para C# para evitar sobrecarga de arquivo e CPU do processamento dos arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="a45fc-124">PowerShell no longer reads the files `$pshome\*.ps1xml` -- these files have been converted to C# to avoid some file and CPU overhead of processing the XML files.</span></span>
> <span data-ttu-id="a45fc-125">Os arquivos ainda existem para dar suporte à V2 lado a lado; portanto, se você alterar o conteúdo do arquivo, ele não terá qualquer efeito na V5, apenas na V2.</span><span class="sxs-lookup"><span data-stu-id="a45fc-125">The files still exist to support V2 side-by-side, so if you change the file contents, it will not have any effect to V5, only V2.</span></span>
> <span data-ttu-id="a45fc-126">Observe que alterar os conteúdos desses arquivos nunca foi um cenário com suporte.</span><span class="sxs-lookup"><span data-stu-id="a45fc-126">Note that changing the contents of these files was never a supported scenario.</span></span>

<span data-ttu-id="a45fc-127">Outra alteração visível é como o PowerShell armazena em cache os comandos exportados e outras informações para módulos instalados em um sistema.</span><span class="sxs-lookup"><span data-stu-id="a45fc-127">Another visible change is how PowerShell caches the exported commands and other information for modules that are installed on a system.</span></span>
<span data-ttu-id="a45fc-128">Antes, esse cache era armazenado no diretório `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`.</span><span class="sxs-lookup"><span data-stu-id="a45fc-128">Previously, this cache was stored in the directory `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`.</span></span>
<span data-ttu-id="a45fc-129">No WMF 5.1, o cache é um único arquivo `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span><span class="sxs-lookup"><span data-stu-id="a45fc-129">In WMF 5.1, the cache is a single file `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span>
<span data-ttu-id="a45fc-130">Veja [Cache de análise do módulo](scenarios-features.md#module-analysis-cache) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="a45fc-130">See [Module Analysis Cache](scenarios-features.md#module-analysis-cache) for more details.</span></span>