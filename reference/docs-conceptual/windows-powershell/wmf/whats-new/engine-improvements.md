---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,instalação
title: Melhorias do Mecanismo do PowerShell no WMF 5.1
ms.openlocfilehash: cccfcf8872ac60e0902669bcc797d0ed250317ba
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808932"
---
# <a name="powershell-engine-improvements"></a><span data-ttu-id="0ba9b-103">Melhorias ao Mecanismo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ba9b-103">PowerShell Engine Improvements</span></span>

<span data-ttu-id="0ba9b-104">As seguintes melhorias ao mecanismo principal do PowerShell foram implementadas no WMF 5.1:</span><span class="sxs-lookup"><span data-stu-id="0ba9b-104">The following improvements to the core PowerShell engine have been implemented in WMF 5.1:</span></span>

## <a name="performance"></a><span data-ttu-id="0ba9b-105">Desempenho</span><span class="sxs-lookup"><span data-stu-id="0ba9b-105">Performance</span></span>

<span data-ttu-id="0ba9b-106">O desempenho melhorou em algumas áreas importantes:</span><span class="sxs-lookup"><span data-stu-id="0ba9b-106">Performance has improved in some important areas:</span></span>

- <span data-ttu-id="0ba9b-107">Inicialização</span><span class="sxs-lookup"><span data-stu-id="0ba9b-107">Startup</span></span>
- <span data-ttu-id="0ba9b-108">O pipeline para cmdlets como `ForEach-Object` e `Where-Object` é aproximadamente 50% mais rápido</span><span class="sxs-lookup"><span data-stu-id="0ba9b-108">Pipelining to cmdlets like `ForEach-Object` and `Where-Object` is approximately 50% faster</span></span>

<span data-ttu-id="0ba9b-109">Alguns exemplos de melhorias (os resultados podem variar dependendo do hardware):</span><span class="sxs-lookup"><span data-stu-id="0ba9b-109">Some example improvements (your results may vary depending on your hardware):</span></span>

| <span data-ttu-id="0ba9b-110">Cenário</span><span class="sxs-lookup"><span data-stu-id="0ba9b-110">Scenario</span></span> | <span data-ttu-id="0ba9b-111">Tempo de 5,0 (ms)</span><span class="sxs-lookup"><span data-stu-id="0ba9b-111">5.0 Time (ms)</span></span> | <span data-ttu-id="0ba9b-112">Tempo de 5,1 (ms)</span><span class="sxs-lookup"><span data-stu-id="0ba9b-112">5.1 Time (ms)</span></span> |
| -------- | :---------------: | :---------------: |
| `powershell -command "echo 1"` | <span data-ttu-id="0ba9b-113">900</span><span class="sxs-lookup"><span data-stu-id="0ba9b-113">900</span></span> | <span data-ttu-id="0ba9b-114">250</span><span class="sxs-lookup"><span data-stu-id="0ba9b-114">250</span></span> |
| <span data-ttu-id="0ba9b-115">Primeira execução do PowerShell: `powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="0ba9b-115">First ever PowerShell run: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="0ba9b-116">30000</span><span class="sxs-lookup"><span data-stu-id="0ba9b-116">30000</span></span> | <span data-ttu-id="0ba9b-117">13000</span><span class="sxs-lookup"><span data-stu-id="0ba9b-117">13000</span></span> |
| <span data-ttu-id="0ba9b-118">Built do cache de análise de comando: `powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="0ba9b-118">Command analysis cache built: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="0ba9b-119">7000</span><span class="sxs-lookup"><span data-stu-id="0ba9b-119">7000</span></span> | <span data-ttu-id="0ba9b-120">520</span><span class="sxs-lookup"><span data-stu-id="0ba9b-120">520</span></span> |
| <code>1..1000000 &#124; % { }</code> | <span data-ttu-id="0ba9b-121">1\.400</span><span class="sxs-lookup"><span data-stu-id="0ba9b-121">1400</span></span> | <span data-ttu-id="0ba9b-122">750</span><span class="sxs-lookup"><span data-stu-id="0ba9b-122">750</span></span> |

> [!NOTE]
> <span data-ttu-id="0ba9b-123">Uma alteração relacionada à inicialização pode afetar alguns cenários sem suporte.</span><span class="sxs-lookup"><span data-stu-id="0ba9b-123">One change related to startup might impact some unsupported scenarios.</span></span> <span data-ttu-id="0ba9b-124">O PowerShell não lê mais os arquivos `$pshome\*.ps1xml` – esses arquivos foram convertidos para C# para evitar sobrecarga de arquivo e CPU do processamento dos arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="0ba9b-124">PowerShell no longer reads the files `$pshome\*.ps1xml` -- these files have been converted to C# to avoid some file and CPU overhead of processing the XML files.</span></span> <span data-ttu-id="0ba9b-125">Os arquivos ainda existem para dar suporte à V2 lado a lado; portanto, se você alterar o conteúdo do arquivo, ele não terá qualquer efeito na V5, apenas na V2.</span><span class="sxs-lookup"><span data-stu-id="0ba9b-125">The files still exist to support V2 side-by-side, so if you change the file contents, it will not have any effect to V5, only V2.</span></span> <span data-ttu-id="0ba9b-126">Observe que alterar os conteúdos desses arquivos nunca foi um cenário com suporte.</span><span class="sxs-lookup"><span data-stu-id="0ba9b-126">Note that changing the contents of these files was never a supported scenario.</span></span>

<span data-ttu-id="0ba9b-127">Outra alteração visível é como o PowerShell armazena em cache os comandos exportados e outras informações para módulos instalados em um sistema.</span><span class="sxs-lookup"><span data-stu-id="0ba9b-127">Another visible change is how PowerShell caches the exported commands and other information for modules that are installed on a system.</span></span> <span data-ttu-id="0ba9b-128">Antes, esse cache era armazenado no diretório `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`.</span><span class="sxs-lookup"><span data-stu-id="0ba9b-128">Previously, this cache was stored in the directory `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`.</span></span> <span data-ttu-id="0ba9b-129">No WMF 5.1, o cache é um único arquivo `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span><span class="sxs-lookup"><span data-stu-id="0ba9b-129">In WMF 5.1, the cache is a single file `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="0ba9b-130">Veja [Cache de análise do módulo](release-notes.md#module-analysis-cache) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="0ba9b-130">See [Module Analysis Cache](release-notes.md#module-analysis-cache) for more details.</span></span>
