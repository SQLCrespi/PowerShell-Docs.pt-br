---
title: Criando um serviço Web do Management OData | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06b1b050-0bf7-48f5-ba05-43f489d597c0
caps.latest.revision: 10
ms.openlocfilehash: 476fce9fc087b870bad93a9204a820c5a84df99e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359715"
---
# <a name="creating-a-management-odata-web-service"></a><span data-ttu-id="46358-102">Criar um serviço Web OData de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="46358-102">Creating a Management OData Web Service</span></span>

<span data-ttu-id="46358-103">A extensão do IIS do Management ODATA é uma infraestrutura para criar um ponto de extremidade do serviço Web ASP.NET que expõe os dados de gerenciamento, acessados por meio de cmdlets e scripts do Windows PowerShell, como entidades do serviço Web OData.</span><span class="sxs-lookup"><span data-stu-id="46358-103">Management ODATA IIS Extension is an infrastructure for creating an ASP.NET web service end point that exposes your management data, accessed through Windows PowerShell cmdlets and scripts, as OData Web service entities.</span></span> <span data-ttu-id="46358-104">Ele faz isso processando solicitações OData e convertendo-as em uma invocação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46358-104">It does that by processing OData requests and converting them into a Windows PowerShell invocation.</span></span> <span data-ttu-id="46358-105">As equipes de produtos podem se basear nessa infraestrutura para criar pontos de extremidade que exponham conjuntos específicos de dados de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="46358-105">Product teams can build on top of this infrastructure to create endpoints that expose specific sets of management data.</span></span>

<span data-ttu-id="46358-106">Baixe e instale o exemplo [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) .</span><span class="sxs-lookup"><span data-stu-id="46358-106">Download and install the [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) sample.</span></span> <span data-ttu-id="46358-107">Siga as instruções para implantar o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="46358-107">Follow the instructions to deploy the web service.</span></span> <span data-ttu-id="46358-108">Esse serviço Web expõe serviços e processos por meio de operações CRUD (criar, ler, atualizar e excluir).</span><span class="sxs-lookup"><span data-stu-id="46358-108">This web service exposes Services and Processes through Create, Read, Update, and Delete (CRUD) operations.</span></span> <span data-ttu-id="46358-109">As solicitações CRUD feitas ao serviço Web invocam comandos do Windows PowerShell que executam as operações solicitadas.</span><span class="sxs-lookup"><span data-stu-id="46358-109">CRUD requests made to the web service invoke  Windows PowerShell commands that perform the requested operations.</span></span> <span data-ttu-id="46358-110">Um mapeamento entre as operações CRUD e os comandos subjacentes do Windows PowerShell é implementado por dois arquivos de esquema, Schema. mof e Schema. xml.</span><span class="sxs-lookup"><span data-stu-id="46358-110">A mapping between the CRUD operations and the underlying Windows PowerShell commands is implemented by two schema files, schema.mof and schema.xml.</span></span> <span data-ttu-id="46358-111">O arquivo Schema. mof usa o padrão MOF ( [Distributed Management Task Force](https://www.dmtf.org/) ).</span><span class="sxs-lookup"><span data-stu-id="46358-111">The schema.mof file uses the [Distributed Management  Task Force](https://www.dmtf.org/) (DMTF) Managed Object (MOF) standard.</span></span> <span data-ttu-id="46358-112">O arquivo Schema. XML usa um esquema XML descrito no esquema de [mapeamento de recursos](./resource-mapping-schema.md).</span><span class="sxs-lookup"><span data-stu-id="46358-112">The schema.xml file uses an XML schema that is described in [Resource Mapping Schema](./resource-mapping-schema.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46358-113">Antes de habilitar a extensão do IIS do Management ODATA no Windows Server 2008 R2 SP1, os recursos a seguir devem ser habilitados.</span><span class="sxs-lookup"><span data-stu-id="46358-113">Before you enabling Management ODATA IIS Extension on Windows Server 2008 R2 SP1, the following features must be enabled.</span></span>
>
> 1.  <span data-ttu-id="46358-114">IIS-WebServerRole</span><span class="sxs-lookup"><span data-stu-id="46358-114">IIS-WebServerRole</span></span>
> 2.  <span data-ttu-id="46358-115">IIS-WebServer</span><span class="sxs-lookup"><span data-stu-id="46358-115">IIS-WebServer</span></span>
> 3.  <span data-ttu-id="46358-116">IIS-HttpTracing</span><span class="sxs-lookup"><span data-stu-id="46358-116">IIS-HttpTracing</span></span>
> 4.  <span data-ttu-id="46358-117">IIS-ManagementOData</span><span class="sxs-lookup"><span data-stu-id="46358-117">IIS-ManagementOData</span></span>

## <a name="steps-for-creating-a-management-odata-web-service"></a><span data-ttu-id="46358-118">Etapas para criar um serviço Web do Management OData</span><span class="sxs-lookup"><span data-stu-id="46358-118">Steps for creating a Management OData web service</span></span>

<span data-ttu-id="46358-119">Os tópicos a seguir descrevem como criar e implantar um serviço Web do Management OData.</span><span class="sxs-lookup"><span data-stu-id="46358-119">The following topics describe how to create and deploy a Management OData web service.</span></span>

- [<span data-ttu-id="46358-120">Adicionando recursos a um serviço Web do Management OData</span><span class="sxs-lookup"><span data-stu-id="46358-120">Adding Resources to a Management OData Web Service</span></span>](./adding-resources-to-a-management-odata-web-service.md)

- [<span data-ttu-id="46358-121">Implementando a autorização personalizada para um serviço Web do Management OData</span><span class="sxs-lookup"><span data-stu-id="46358-121">Implementing Custom Authorization for a Management OData web service</span></span>](./implementing-custom-authorization-for-a-management-odata-web-service.md)

- [<span data-ttu-id="46358-122">Implementando o SessionConfiguration para um serviço Web do Management OData</span><span class="sxs-lookup"><span data-stu-id="46358-122">Implementing SessionConfiguration for a Management OData web service</span></span>](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

- [<span data-ttu-id="46358-123">Criando o arquivo de esquema MOF para um serviço Web do Management OData</span><span class="sxs-lookup"><span data-stu-id="46358-123">Authoring the MOF schema file for a Management OData web service</span></span>](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="46358-124">Criando o arquivo de esquema XML para um serviço Web do Management OData</span><span class="sxs-lookup"><span data-stu-id="46358-124">Authoring the XML schema file for a Management OData web service</span></span>](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="46358-125">Criando o arquivo Web. config para um serviço Web do Management OData</span><span class="sxs-lookup"><span data-stu-id="46358-125">Authoring the Web.config file for a Management OData web service</span></span>](./authoring-the-web-config-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="46358-126">Implantando um serviço Web do Management OData</span><span class="sxs-lookup"><span data-stu-id="46358-126">Deploying a Management OData web service</span></span>](./deploying-a-management-odata-web-service.md)

- [<span data-ttu-id="46358-127">Associando entidades do Management OData</span><span class="sxs-lookup"><span data-stu-id="46358-127">Associating Management OData Entities</span></span>](./associating-management-odata-entities.md)

## <a name="see-also"></a><span data-ttu-id="46358-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46358-128">See Also</span></span>

[<span data-ttu-id="46358-129">Arquivos de esquema de extensão do IIS do Management ODATA</span><span class="sxs-lookup"><span data-stu-id="46358-129">Management ODATA IIS Extension Schema Files</span></span>](./management-odata-iis-extension-schema-files.md)
