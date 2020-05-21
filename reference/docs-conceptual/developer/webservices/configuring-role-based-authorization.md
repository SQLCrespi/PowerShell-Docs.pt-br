---
title: Configurando autorização baseada em função | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2933a6ca-fe92-4ba2-97ee-ef0f0d5fdfcf
caps.latest.revision: 8
ms.openlocfilehash: 2c9d6040b7a9c17dc5204c8eb835fd69780f62c5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564250"
---
# <a name="configuring-role-based-authorization"></a><span data-ttu-id="c03ea-102">Configurar a autorização baseada em função</span><span class="sxs-lookup"><span data-stu-id="c03ea-102">Configuring Role-based Authorization</span></span>

<span data-ttu-id="c03ea-103">Este tópico demonstra como configurar a política de autorização baseada em função para a implementação de exemplo da interface [Microsoft. Management. OData. Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) descrita em [implementando a autorização personalizada para a extensão do IIS do Management OData](./implementing-custom-authorization-for-a-management-odata-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="c03ea-103">This topic demonstrates how to configure the role-based authorization policy for the sample implementation of the [Microsoft.Management.Odata.Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) interface described in [Implementing Custom Authorization for Management OData IIS Extension](./implementing-custom-authorization-for-a-management-odata-web-service.md).</span></span>

<span data-ttu-id="c03ea-104">Neste exemplo, você configurará um arquivo XML que é usado pelo aplicativo OData de gerenciamento de exemplo para definir a política de autorização.</span><span class="sxs-lookup"><span data-stu-id="c03ea-104">In this example, you will configure an XML file that is used by the sample Management OData application to define the authorization policy.</span></span> <span data-ttu-id="c03ea-105">Você criará duas funções e associará diferentes módulos do Windows PowerShell que contêm fluxos de trabalho com essas funções.</span><span class="sxs-lookup"><span data-stu-id="c03ea-105">You will create two roles and associate different Windows PowerShell modules that contain workflows with those roles.</span></span> <span data-ttu-id="c03ea-106">O esquema que define o arquivo XML é listado no [esquema de configuração de autorização baseada em função](./role-based-authorization-configuration-schema.md).</span><span class="sxs-lookup"><span data-stu-id="c03ea-106">The schema that defines the XML file is listed at [Role-Based Authorization Configuration Schema](./role-based-authorization-configuration-schema.md).</span></span>

## <a name="modifying-the-rbacconfigurationxml-file"></a><span data-ttu-id="c03ea-107">Modificando o arquivo RBacConfiguration. xml</span><span class="sxs-lookup"><span data-stu-id="c03ea-107">Modifying the RBacConfiguration.xml File</span></span>

<span data-ttu-id="c03ea-108">Esse arquivo define a política de autorização para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c03ea-108">This file defines the authorization policy for the application.</span></span> <span data-ttu-id="c03ea-109">As funções são definidas usando `Group` nós.</span><span class="sxs-lookup"><span data-stu-id="c03ea-109">Roles are defined by using `Group` nodes.</span></span> <span data-ttu-id="c03ea-110">Um `Group` nó define os comandos do Windows PowerShell que os usuários atribuídos a esse grupo podem executar.</span><span class="sxs-lookup"><span data-stu-id="c03ea-110">A `Group` node defines the Windows PowerShell commands that users assigned to that group can run.</span></span> <span data-ttu-id="c03ea-111">Os usuários são atribuídos a grupos usando `User` nós.</span><span class="sxs-lookup"><span data-stu-id="c03ea-111">Users are assigned to groups by using `User` nodes.</span></span>

<span data-ttu-id="c03ea-112">Nestes exemplos, você adicionará um módulo ao `Group` nó administrador e adicionará um usuário a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="c03ea-112">In these examples, you will add a module to the Administrator `Group` node, and add a user to each group.</span></span>

#### <a name="adding-a-module-to-a-group-node"></a><span data-ttu-id="c03ea-113">Adicionando um módulo a um nó de grupo</span><span class="sxs-lookup"><span data-stu-id="c03ea-113">Adding a Module to a Group Node</span></span>

1. <span data-ttu-id="c03ea-114">Crie um arquivo chamado **RBacConfiguration. xml** em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="c03ea-114">Create a file named **RBacConfiguration.xml** in a text editor.</span></span> <span data-ttu-id="c03ea-115">Esse arquivo deve ser salvo no diretório principal do aplicativo para o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="c03ea-115">This file should be saved to the main application directory for your web service.</span></span> <span data-ttu-id="c03ea-116">Insira o texto a seguir no arquivo.</span><span class="sxs-lookup"><span data-stu-id="c03ea-116">Insert the following text in the file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <RbacConfiguration>
     <Groups>
       <!--Group consists of the following:
         Name:  Name of the group
         UserName (Optional): Windows Identity user name
         Password (Optional): Password of the Windows user name
         DomainName (Optional): Domain for the user. For local machine account either do not include them or give the machine name. Do not give empty string
         MapIncomingUser (Optional): Boolean value indicating whether to execute cmdlet in the context of network client.

         User credentials and MapIncomingUser=true are exclusive.
       -->
       <Group Name="NonAdminGroup" MapIncomingUser="true">
         <Cmdlets>
           <Cmdlet>Get-Service</Cmdlet>
           <Cmdlet>Set-Service</Cmdlet>
           <Cmdlet>Get-Process</Cmdlet>
           <Cmdlet>Get-Item</Cmdlet>
           <Cmdlet>New-Item</Cmdlet>
           <Cmdlet>Get-Command</Cmdlet>
           <Cmdlet>ConvertTo-Xml</Cmdlet>
           <Cmdlet>ConvertTo-Json</Cmdlet>
           <Cmdlet>ConvertFrom-Json</Cmdlet>
         </Cmdlets>
       </Group>
       <Group Name="AdminGroup" MapIncomingUser="true">
         <Cmdlets>
           <Cmdlet>Get-Service</Cmdlet>
           <Cmdlet>Get-Process</Cmdlet>
           <Cmdlet>Get-Item</Cmdlet>
           <Cmdlet>New-Item</Cmdlet>
           <Cmdlet>Get-Command</Cmdlet>
           <Cmdlet>ConvertTo-Xml</Cmdlet>
           <Cmdlet>ConvertTo-Json</Cmdlet>
           <Cmdlet>ConvertFrom-Json</Cmdlet>
         </Cmdlets>
         <Modules>
           <Module>C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ServerManager\ServerManager.psd1</Module>
         </Modules>
       </Group>
     </Groups>
     <Users>
       <!-- User consists of the following :
         Name: Name of the user. If a user is from a cer
         AuthenticationType: Authentication type used.
         DomainName (Optional): Domain for the user
       -->
       <User Name="localNonAdmin" AuthenticationType="Basic" GroupName="NonAdminGroup" />
       <User Name="localAdmin" AuthenticationType="Basic" GroupName="AdminGroup" />
     </Users>
   </RbacConfiguration>
   ```

2. <span data-ttu-id="c03ea-117">O arquivo contém dois `Group` nós.</span><span class="sxs-lookup"><span data-stu-id="c03ea-117">The file contains two `Group` nodes.</span></span> <span data-ttu-id="c03ea-118">Elas representam as duas funções usadas neste exemplo, as `NonAdminGroup` `AdminGroup` funções e.</span><span class="sxs-lookup"><span data-stu-id="c03ea-118">These represent the two roles used in this example, the `NonAdminGroup` and the `AdminGroup` roles.</span></span>

   <span data-ttu-id="c03ea-119">Diretamente após a marca de fechamento `Cmdlets` no primeiro `Group` nó, adicione o seguinte XML:</span><span class="sxs-lookup"><span data-stu-id="c03ea-119">Directly after the closing `Cmdlets` tag in the first `Group` node, add the following XML:</span></span>

   ```xml
   <Modules>
           <Module>C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ServerManager\ServerManager.psd1</Module>
         </Modules>
   ```

#### <a name="adding-a-user-to-a-group-node"></a><span data-ttu-id="c03ea-120">Adicionando um usuário a um nó de grupo</span><span class="sxs-lookup"><span data-stu-id="c03ea-120">Adding a User to a Group Node</span></span>

1. <span data-ttu-id="c03ea-121">Abra o arquivo **RBacConfiguration. xml** em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="c03ea-121">Open the **RBacConfiguration.xml** file in a text editor.</span></span> <span data-ttu-id="c03ea-122">Esse arquivo está localizado na pasta C: \\ \inetpub\wwwroot\Modata se você não alterou o nome do ponto de extremidade antes da instalação.</span><span class="sxs-lookup"><span data-stu-id="c03ea-122">This file is located in the folder C:\\\inetpub\wwwroot\Modata  if you did not change the endpoint name before installation.</span></span>

2. <span data-ttu-id="c03ea-123">Diretamente após a marca de fechamento no `Users` nó, adicione o seguinte XML:</span><span class="sxs-lookup"><span data-stu-id="c03ea-123">Directly after the closing tag in the `Users` node, add the following XML:</span></span>

   ```xml
   <User Name="UserName" GroupName="AdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```

3. <span data-ttu-id="c03ea-124">Diretamente após o XML adicionado na etapa anterior, adicione o seguinte XML:</span><span class="sxs-lookup"><span data-stu-id="c03ea-124">Directly after the XML added in the previous step, add the following XML:</span></span>

   ```xml
   <User Name="UserName" GroupName="NonAdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```
