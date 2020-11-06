---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Configurando um cliente de pull de DSC
description: Este artigo é uma visão geral das informações disponíveis para configurar o cliente de pull de DSC.
ms.openlocfilehash: 584af3aee46d801e363422ae7a197348231a1442
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646823"
---
# <a name="setting-up-a-dsc-pull-client"></a><span data-ttu-id="8515e-104">Configurando um cliente de pull de DSC</span><span class="sxs-lookup"><span data-stu-id="8515e-104">Setting up a DSC pull client</span></span>

> <span data-ttu-id="8515e-105">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="8515e-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8515e-106">O Servidor de Recepção (Recurso do Windows *Serviço DSC* ) é um componente compatível com o Windows Server, no entanto, não há planos de oferecer novos recursos ou funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="8515e-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="8515e-107">É recomendável começar a fazer a transição dos clientes gerenciados para o [DSC de Automação do Azure](/azure/automation/automation-dsc-getting-started) (inclui recursos além do Servidor de Recepção no Windows Server) ou para uma das soluções da comunidade listadas [aqui](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="8515e-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="8515e-108">Cada nó de destino deve ser instruído a usar o modo de pull e receber a URL ou local do arquivo em que possa contatar o servidor de pull para obter as configurações e recursos e para onde deve enviar os dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="8515e-108">Each target node has to be told to use pull mode and given the URL or file location where it can contact the pull server to get configurations and resources, and where it should send report data.</span></span>

<span data-ttu-id="8515e-109">Os tópicos a seguir explicam como configurar clientes de pull:</span><span class="sxs-lookup"><span data-stu-id="8515e-109">The following topics explain how to set up pull clients:</span></span>

- <span data-ttu-id="8515e-110">[Configurar um cliente de pull usando nomes de configuração](pullClientConfigNames.md)
\*-[Configurar um cliente de pull usando a ID de configuração](pullClientConfigID.md)</span><span class="sxs-lookup"><span data-stu-id="8515e-110">[Setting up a pull client using configuration names](pullClientConfigNames.md)
\*-[Setting up a pull client using configuration ID](pullClientConfigID.md)</span></span>

> [!NOTE]
> <span data-ttu-id="8515e-111">Estes tópicos se aplicam ao PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="8515e-111">These topics apply to PowerShell 5.0.</span></span> <span data-ttu-id="8515e-112">Para configurar um cliente de pull no PowerShell 4.0, consulte [Configurando um cliente de pull usando uma ID de configuração no PowerShell 4.0](pullClientConfigID4.md).</span><span class="sxs-lookup"><span data-stu-id="8515e-112">To set up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md).</span></span>
