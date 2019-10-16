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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359715"
---
# <a name="creating-a-management-odata-web-service"></a>Criar um serviço Web OData de gerenciamento

A extensão do IIS do Management ODATA é uma infraestrutura para criar um ponto de extremidade do serviço Web ASP.NET que expõe os dados de gerenciamento, acessados por meio de cmdlets e scripts do Windows PowerShell, como entidades do serviço Web OData. Ele faz isso processando solicitações OData e convertendo-as em uma invocação do Windows PowerShell. As equipes de produtos podem se basear nessa infraestrutura para criar pontos de extremidade que exponham conjuntos específicos de dados de gerenciamento.

Baixe e instale o exemplo [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) . Siga as instruções para implantar o serviço Web. Esse serviço Web expõe serviços e processos por meio de operações CRUD (criar, ler, atualizar e excluir). As solicitações CRUD feitas ao serviço Web invocam comandos do Windows PowerShell que executam as operações solicitadas. Um mapeamento entre as operações CRUD e os comandos subjacentes do Windows PowerShell é implementado por dois arquivos de esquema, Schema. mof e Schema. xml. O arquivo Schema. mof usa o padrão MOF ( [Distributed Management Task Force](https://www.dmtf.org/) ). O arquivo Schema. XML usa um esquema XML descrito no esquema de [mapeamento de recursos](./resource-mapping-schema.md).

> [!IMPORTANT]
> Antes de habilitar a extensão do IIS do Management ODATA no Windows Server 2008 R2 SP1, os recursos a seguir devem ser habilitados.
>
> 1.  IIS-WebServerRole
> 2.  IIS-WebServer
> 3.  IIS-HttpTracing
> 4.  IIS-ManagementOData

## <a name="steps-for-creating-a-management-odata-web-service"></a>Etapas para criar um serviço Web do Management OData

Os tópicos a seguir descrevem como criar e implantar um serviço Web do Management OData.

- [Adicionando recursos a um serviço Web do Management OData](./adding-resources-to-a-management-odata-web-service.md)

- [Implementando a autorização personalizada para um serviço Web do Management OData](./implementing-custom-authorization-for-a-management-odata-web-service.md)

- [Implementando o SessionConfiguration para um serviço Web do Management OData](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

- [Criando o arquivo de esquema MOF para um serviço Web do Management OData](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

- [Criando o arquivo de esquema XML para um serviço Web do Management OData](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

- [Criando o arquivo Web. config para um serviço Web do Management OData](./authoring-the-web-config-file-for-a-management-odata-web-service.md)

- [Implantando um serviço Web do Management OData](./deploying-a-management-odata-web-service.md)

- [Associando entidades do Management OData](./associating-management-odata-entities.md)

## <a name="see-also"></a>Consulte Também

[Arquivos de esquema de extensão do IIS do Management ODATA](./management-odata-iis-extension-schema-files.md)
