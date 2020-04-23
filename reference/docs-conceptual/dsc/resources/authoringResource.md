---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Criar recursos personalizados de configuração de estado desejado do Windows PowerShell
ms.openlocfilehash: f0f35e8d0083d302f142f2215c9f28fee411eb07
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71952843"
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a><span data-ttu-id="6c574-103">Criar recursos personalizados de configuração de estado desejado do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c574-103">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>

> <span data-ttu-id="6c574-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6c574-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="6c574-105">A Configuração de Estado Desejado (DSC) do Windows PowerShell tem recursos internos que podem ser usados para configurar seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="6c574-105">Windows PowerShell Desired State Configuration (DSC) has built-in resources that you can use to configure your environment.</span></span> <span data-ttu-id="6c574-106">Este tópico fornece uma visão geral do desenvolvimento de recursos e links para tópicos com exemplos e informações específicas.</span><span class="sxs-lookup"><span data-stu-id="6c574-106">This topic provides an overview of developing resources and links to topics with specific information and examples.</span></span>

## <a name="dsc-resource-components"></a><span data-ttu-id="6c574-107">Componentes de recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="6c574-107">DSC resource components</span></span>

<span data-ttu-id="6c574-108">Um recurso de DSC é um módulo do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c574-108">A DSC resource is a Windows PowerShell module.</span></span> <span data-ttu-id="6c574-109">O módulo contém o esquema (a definição das propriedades configuráveis) e a implementação (o código que faz o trabalho real especificado por uma configuração) do recurso.</span><span class="sxs-lookup"><span data-stu-id="6c574-109">The module contains both the schema (the definition of the configurable properties) and the implementation (the code that does the actual work specified by a configuration) for the resource.</span></span> <span data-ttu-id="6c574-110">Um esquema de recursos de DSC pode ser definido em um arquivo MOF e a implementação é executada por um módulo de script.</span><span class="sxs-lookup"><span data-stu-id="6c574-110">A DSC resource schema can be defined in a MOF file, and the implementation is performed by a script module.</span></span> <span data-ttu-id="6c574-111">Começando com o suporte das classes do PowerShell na versão 5, o esquema e a implementação podem ser definidos em uma classe.</span><span class="sxs-lookup"><span data-stu-id="6c574-111">Beginning with the support of PowerShell classes in version 5, the schema and implementation can both be defined in a class.</span></span> <span data-ttu-id="6c574-112">Os tópicos a seguir descrevem detalhadamente como criar recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="6c574-112">The following topics describe in more detail how to create DSC resources.</span></span>

* [<span data-ttu-id="6c574-113">Escrevendo um recurso personalizado de DSC com MOF</span><span class="sxs-lookup"><span data-stu-id="6c574-113">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
* [<span data-ttu-id="6c574-114">Implementando um recurso de DSC em C#</span><span class="sxs-lookup"><span data-stu-id="6c574-114">Implementing a DSC resource in C#</span></span>](authoringResourceMofCS.md)
* [<span data-ttu-id="6c574-115">Escrevendo um recurso personalizado de DSC com classes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c574-115">Writing a custom DSC resource with PowerShell classes</span></span>](authoringResourceClass.md)
* [<span data-ttu-id="6c574-116">Recursos de composição: usando uma configuração DSC como um recurso</span><span class="sxs-lookup"><span data-stu-id="6c574-116">Composite resources: Using a DSC configuration as a resource</span></span>](authoringResourceComposite.md)
* [<span data-ttu-id="6c574-117">Usando a ferramenta Designer de Recursos</span><span class="sxs-lookup"><span data-stu-id="6c574-117">Using the Resource Designer tool</span></span>](authoringResourceMofDesigner.md)
