---
title: Criando o arquivo Web. config para um serviço Web do Management OData | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d569f5d5-9746-40c0-be5e-f218bc4560f7
caps.latest.revision: 4
ms.openlocfilehash: 8e5897c3df38689e80d2135dfb82898bf9a05b86
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561474"
---
# <a name="authoring-the-webconfig-file-for-a-management-odata-web-service"></a>Criação do arquivo Web.config para um serviço Web OData de gerenciamento

Antes de poder implantar o serviço Web do Management OData, você deve configurar o arquivo Web. config para apontar para os arquivos de esquema XML e as DLLs que implementam as interfaces [Microsoft. Management. OData. Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) e [System. Management. Automation. Remoting. PSSessionConfiguration](/dotnet/api/System.Management.Automation.Remoting.PSSessionConfiguration) .

## <a name="sample-config-file"></a>Arquivo de configuração de exemplo

Veja a seguir um exemplo de como o arquivo Web. config para seu serviço Web é semelhante.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
   <configSections>
      <section name="managementOdata" type="Microsoft.Management.Odata.Core.DSConfiguration, Microsoft.Management.OData, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL" />
   </configSections>
   <managementOdata schemaFileName="Schema.mof" resourceMappingFileName="Schema.xml">
      <customAuthorization type="Microsoft.Samples.Management.OData.RoleBasedPlugins.CustomAuthorization" assembly=".\Microsoft.Samples.Management.OData.RoleBasedPlugins.dll" />
      <powershell>
         <sessionConfiguration type="Microsoft.Samples.Management.OData.RoleBasedPlugins.SessionConfiguration" assembly=".\Microsoft.Samples.Management.OData.RoleBasedPlugins.dll" />
      </powershell>
      <commandInvocation enabled="true" />
      <wcfDataServicesConfig>
      </wcfDataServicesConfig>
   </managementOdata>
   <system.serviceModel>
      <behaviors>
         <serviceBehaviors>
            <behavior>
                  <serviceAuthorization serviceAuthorizationManagerType="Microsoft.Management.Odata.Core.CustomAuthorizationManager, Microsoft.Management.OData, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />
            </behavior>
         </serviceBehaviors>
      </behaviors>
      <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
   </system.serviceModel>
   <system.webServer>
      <security>
         <authentication>
            <anonymousAuthentication enabled="false" />
            <basicAuthentication enabled="true" />
            <windowsAuthentication enabled="false" />
         </authentication>
      </security>
  </system.webServer>
</configuration>

```

## <a name="see-also"></a>Consulte Também

[Implementar autorização personalizada para um serviço Web OData de gerenciamento](./implementing-custom-authorization-for-a-management-odata-web-service.md)

[Implementar SessionConfiguration para um serviço Web OData de gerenciamento](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

[Criação do arquivo de esquema MOF para um serviço Web OData de gerenciamento](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

[Criação do arquivo de esquema XML para um serviço Web OData de gerenciamento](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

[Criar um serviço Web OData de gerenciamento](./creating-a-management-odata-web-service.md)
