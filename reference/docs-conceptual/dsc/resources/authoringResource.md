---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Criar recursos personalizados de configuração de estado desejado do Windows PowerShell
ms.openlocfilehash: f0f35e8d0083d302f142f2215c9f28fee411eb07
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71952843"
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a><span data-ttu-id="032db-103">Criar recursos personalizados de configuração de estado desejado do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="032db-103">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>

> <span data-ttu-id="032db-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="032db-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="032db-105">A Configuração de Estado Desejado (DSC) do Windows PowerShell tem recursos internos que podem ser usados para configurar seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="032db-105">Windows PowerShell Desired State Configuration (DSC) has built-in resources that you can use to configure your environment.</span></span> <span data-ttu-id="032db-106">Este tópico fornece uma visão geral do desenvolvimento de recursos e links para tópicos com exemplos e informações específicas.</span><span class="sxs-lookup"><span data-stu-id="032db-106">This topic provides an overview of developing resources and links to topics with specific information and examples.</span></span>

## <a name="dsc-resource-components"></a><span data-ttu-id="032db-107">Componentes de recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="032db-107">DSC resource components</span></span>

<span data-ttu-id="032db-108">Um recurso de DSC é um módulo do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="032db-108">A DSC resource is a Windows PowerShell module.</span></span> <span data-ttu-id="032db-109">O módulo contém o esquema (a definição das propriedades configuráveis) e a implementação (o código que faz o trabalho real especificado por uma configuração) do recurso.</span><span class="sxs-lookup"><span data-stu-id="032db-109">The module contains both the schema (the definition of the configurable properties) and the implementation (the code that does the actual work specified by a configuration) for the resource.</span></span> <span data-ttu-id="032db-110">Um esquema de recursos de DSC pode ser definido em um arquivo MOF e a implementação é executada por um módulo de script.</span><span class="sxs-lookup"><span data-stu-id="032db-110">A DSC resource schema can be defined in a MOF file, and the implementation is performed by a script module.</span></span> <span data-ttu-id="032db-111">Começando com o suporte das classes do PowerShell na versão 5, o esquema e a implementação podem ser definidos em uma classe.</span><span class="sxs-lookup"><span data-stu-id="032db-111">Beginning with the support of PowerShell classes in version 5, the schema and implementation can both be defined in a class.</span></span> <span data-ttu-id="032db-112">Os tópicos a seguir descrevem detalhadamente como criar recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="032db-112">The following topics describe in more detail how to create DSC resources.</span></span>

* [<span data-ttu-id="032db-113">Escrevendo um recurso personalizado de DSC com MOF</span><span class="sxs-lookup"><span data-stu-id="032db-113">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
* [<span data-ttu-id="032db-114">Implementando um recurso de DSC em C#</span><span class="sxs-lookup"><span data-stu-id="032db-114">Implementing a DSC resource in C#</span></span>](authoringResourceMofCS.md)
* [<span data-ttu-id="032db-115">Escrevendo um recurso personalizado de DSC com classes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="032db-115">Writing a custom DSC resource with PowerShell classes</span></span>](authoringResourceClass.md)
* [<span data-ttu-id="032db-116">Recursos de composição: usando uma configuração DSC como um recurso</span><span class="sxs-lookup"><span data-stu-id="032db-116">Composite resources: Using a DSC configuration as a resource</span></span>](authoringResourceComposite.md)
* [<span data-ttu-id="032db-117">Usando a ferramenta Designer de Recursos</span><span class="sxs-lookup"><span data-stu-id="032db-117">Using the Resource Designer tool</span></span>](authoringResourceMofDesigner.md)
