---
title: Criar um provedor de unidade do PowerShell do Windows | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- drive providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], drive provider
- drives [PowerShell Programmer's Guide]
ms.assetid: 2b446841-6616-4720-9ff8-50801d7576ed
caps.latest.revision: 6
ms.openlocfilehash: 2696d78cae7739310b7684161b597ce436dabe92
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855197"
---
# <a name="creating-a-windows-powershell-drive-provider"></a><span data-ttu-id="d670f-102">Criar um provedor de unidade do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d670f-102">Creating a Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="d670f-103">Este tópico descreve como criar um provedor de unidade do Windows PowerShell que fornece uma maneira de acessar um armazenamento de dados por meio de uma unidade do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d670f-103">This topic describes how to create a Windows PowerShell drive provider that provides a way to access a data store through a Windows PowerShell drive.</span></span> <span data-ttu-id="d670f-104">Esse tipo de provedor é também denominado provedores de unidade do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d670f-104">This type of provider is also referred to as Windows PowerShell drive providers.</span></span> <span data-ttu-id="d670f-105">As unidades do Windows PowerShell usadas pelo provedor fornecem os meios para se conectar ao armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="d670f-105">The Windows PowerShell drives used by the provider provide the means to connect to the data store.</span></span>

<span data-ttu-id="d670f-106">O provedor da unidade do Windows PowerShell descrito aqui fornece acesso a um banco de dados do Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="d670f-106">The Windows PowerShell drive provider described here provides access to a Microsoft Access database.</span></span> <span data-ttu-id="d670f-107">Para esse provedor, a unidade do Windows PowerShell representa o banco de dados (é possível adicionar qualquer número de unidades para um provedor de unidade), os contêineres de nível superior da unidade representam as tabelas no banco de dados e os itens dos contêineres representam as linhas em as tabelas.</span><span class="sxs-lookup"><span data-stu-id="d670f-107">For this provider, the Windows PowerShell drive represents the database (it is possible to add any number of drives to a drive provider), the top-level containers of the drive represent the tables in the database, and the items of the containers represent the rows in the tables.</span></span>

## <a name="defining-the-windows-powershell-provider-class"></a><span data-ttu-id="d670f-108">Definição da classe de provedor do PowerShell do Windows</span><span class="sxs-lookup"><span data-stu-id="d670f-108">Defining the Windows PowerShell Provider Class</span></span>

<span data-ttu-id="d670f-109">Seu provedor de unidade deve definir uma classe .NET que deriva de [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) classe base.</span><span class="sxs-lookup"><span data-stu-id="d670f-109">Your drive provider must define a .NET class that derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="d670f-110">Aqui está a definição de classe para este provedor de unidade:</span><span class="sxs-lookup"><span data-stu-id="d670f-110">Here is the class definition for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L29-L30 "AccessDBProviderSample02.cs")]

<span data-ttu-id="d670f-111">Observe que neste exemplo, o [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) atributo especifica um nome amigável para o provedor e os recursos específicos do Windows PowerShell que o provedor expõe o tempo de execução do Windows PowerShell durante o processamento do comando.</span><span class="sxs-lookup"><span data-stu-id="d670f-111">Notice that in this example, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute specifies a user-friendly name for the provider and the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="d670f-112">Os valores possíveis para os recursos do provedor são definidos pela [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeração.</span><span class="sxs-lookup"><span data-stu-id="d670f-112">The possible values for the provider capabilities are defined by the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="d670f-113">Este provedor de unidade não suporta qualquer um desses recursos.</span><span class="sxs-lookup"><span data-stu-id="d670f-113">This drive provider does not support any of these capabilities.</span></span>

## <a name="defining-base-functionality"></a><span data-ttu-id="d670f-114">Definindo a funcionalidade de Base</span><span class="sxs-lookup"><span data-stu-id="d670f-114">Defining Base Functionality</span></span>

<span data-ttu-id="d670f-115">Conforme descrito em [Design o Windows PowerShell provedor](./designing-your-windows-powershell-provider.md), o [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) classe deriva de [ System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) classe base que define os métodos necessários para inicializar e cancelando a inicialização do provedor.</span><span class="sxs-lookup"><span data-stu-id="d670f-115">As described in [Design Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class derives from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class that defines the methods needed for initializing and uninitializing the provider.</span></span> <span data-ttu-id="d670f-116">Para implementar a funcionalidade para adicionar informações de inicialização de sessão específica e para liberação de recursos que são usados pelo provedor, consulte [criando um provedor básico do Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="d670f-116">To implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span> <span data-ttu-id="d670f-117">No entanto, a maioria dos provedores (incluindo o provedor descrito aqui) pode usar a implementação padrão dessa funcionalidade fornecida pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d670f-117">However, most providers (including the provider described here) can use the default implementation of this functionality that is provided by Windows PowerShell.</span></span>

## <a name="creating-drive-state-information"></a><span data-ttu-id="d670f-118">Criando informações de estado da unidade</span><span class="sxs-lookup"><span data-stu-id="d670f-118">Creating Drive State Information</span></span>

<span data-ttu-id="d670f-119">Todos os provedores do Windows PowerShell são considerados sem monitoração de estado, o que significa que seu provedor de unidade precisa criar quaisquer informações de estado que é necessária para o tempo de execução do Windows PowerShell quando ele chama o provedor.</span><span class="sxs-lookup"><span data-stu-id="d670f-119">All Windows PowerShell providers are considered stateless, which means that your drive provider needs to create any state information that is needed by the Windows PowerShell runtime when it calls your provider.</span></span>

<span data-ttu-id="d670f-120">Para este provedor de unidade, a conexão ao banco de dados é mantido como parte das informações de unidade incluem informações de estado.</span><span class="sxs-lookup"><span data-stu-id="d670f-120">For this drive provider, state information includes the connection to the database that is kept as part of the drive information.</span></span> <span data-ttu-id="d670f-121">Aqui está o código que mostra como essas informações são armazenadas do [psdriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) objeto que descreve a unidade:</span><span class="sxs-lookup"><span data-stu-id="d670f-121">Here is code that shows how this information is stored in the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L130-L151 "AccessDBProviderSample02.cs")]

## <a name="creating-a-drive"></a><span data-ttu-id="d670f-122">Criando uma unidade</span><span class="sxs-lookup"><span data-stu-id="d670f-122">Creating a Drive</span></span>

<span data-ttu-id="d670f-123">Para permitir que o tempo de execução do Windows PowerShell criar uma unidade, o provedor da unidade deve implementar o [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) método.</span><span class="sxs-lookup"><span data-stu-id="d670f-123">To allow the Windows PowerShell runtime to create a drive, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method.</span></span> <span data-ttu-id="d670f-124">O código a seguir mostra a implementação do [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) método para este provedor de unidade:</span><span class="sxs-lookup"><span data-stu-id="d670f-124">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L42-L84 "AccessDBProviderSample02.cs")]

<span data-ttu-id="d670f-125">Sua substituição desse método deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d670f-125">Your override of this method should do the following:</span></span>

- <span data-ttu-id="d670f-126">Verifique se que o [System.Management.Automation.PSDriveinfo.Root\*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) membro existe e que uma conexão ao armazenamento de dados pode ser feita.</span><span class="sxs-lookup"><span data-stu-id="d670f-126">Verify that the [System.Management.Automation.PSDriveinfo.Root\*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) member exists and that a connection to the data store can be made.</span></span>

- <span data-ttu-id="d670f-127">Criar uma unidade e preencher o membro de conexão, suportados a `New-PSDrive` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d670f-127">Create a drive and populate the connection member, in support of the `New-PSDrive` cmdlet.</span></span>

- <span data-ttu-id="d670f-128">Validar a [psdriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) objeto para a unidade proposto.</span><span class="sxs-lookup"><span data-stu-id="d670f-128">Validate the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object for the proposed drive.</span></span>

- <span data-ttu-id="d670f-129">Modificar a [psdriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) do objeto que descreve a unidade com qualquer informação de confiabilidade ou de desempenho necessários, ou fornecer dados extras para os chamadores usando a unidade.</span><span class="sxs-lookup"><span data-stu-id="d670f-129">Modify the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive with any required performance or reliability information, or provide extra data for callers using the drive.</span></span>

- <span data-ttu-id="d670f-130">Lidar com falhas usando o [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) método e, em seguida, retorno `null`.</span><span class="sxs-lookup"><span data-stu-id="d670f-130">Handle failures using the [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) method and then return `null`.</span></span>

  <span data-ttu-id="d670f-131">Esse método retorna as informações do disco que foi passadas para o método ou uma versão específica do provedor dele.</span><span class="sxs-lookup"><span data-stu-id="d670f-131">This method returns either the drive information that was passed to the method or a provider-specific version of it.</span></span>

## <a name="attaching-dynamic-parameters-to-newdrive"></a><span data-ttu-id="d670f-132">Anexando parâmetros dinâmicos a NewDrive</span><span class="sxs-lookup"><span data-stu-id="d670f-132">Attaching Dynamic Parameters to NewDrive</span></span>

<span data-ttu-id="d670f-133">O `New-PSDrive` cmdlet tem suportada pelo seu provedor de unidade pode exigir parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="d670f-133">The `New-PSDrive` cmdlet supported by your drive provider might require additional parameters.</span></span> <span data-ttu-id="d670f-134">Para anexar esses parâmetros dinâmicos para o cmdlet, o provedor implementa o [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) método.</span><span class="sxs-lookup"><span data-stu-id="d670f-134">To attach these dynamic parameters to the cmdlet, the provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) method.</span></span> <span data-ttu-id="d670f-135">Esse método retorna um objeto que tem propriedades e campos com análise de atributos, semelhantes a uma classe cmdlet ou uma [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) objeto.</span><span class="sxs-lookup"><span data-stu-id="d670f-135">This method returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="d670f-136">Este provedor de unidade não substitui esse método.</span><span class="sxs-lookup"><span data-stu-id="d670f-136">This drive provider does not override this method.</span></span> <span data-ttu-id="d670f-137">No entanto, o código a seguir mostra a implementação padrão desse método:</span><span class="sxs-lookup"><span data-stu-id="d670f-137">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a><span data-ttu-id="d670f-138">Removendo uma unidade</span><span class="sxs-lookup"><span data-stu-id="d670f-138">Removing a Drive</span></span>

<span data-ttu-id="d670f-139">Para fechar a conexão de banco de dados, o provedor da unidade deve implementar o [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) método.</span><span class="sxs-lookup"><span data-stu-id="d670f-139">To close the database connection, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method.</span></span> <span data-ttu-id="d670f-140">Este método fecha a conexão para a unidade depois de limpar todas as informações específicas do provedor.</span><span class="sxs-lookup"><span data-stu-id="d670f-140">This method closes the connection to the drive after cleaning up any provider-specific information.</span></span>

<span data-ttu-id="d670f-141">O código a seguir mostra a implementação do [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) método para este provedor de unidade:</span><span class="sxs-lookup"><span data-stu-id="d670f-141">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L91-L116 "AccessDBProviderSample02.cs")]

<span data-ttu-id="d670f-142">Se a unidade pode ser removida, o método deve retornar as informações transmitidas para o método por meio de `drive` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d670f-142">If the drive can be removed, the method should return the information passed to the method through the `drive` parameter.</span></span> <span data-ttu-id="d670f-143">Se a unidade não pode ser removida, o método deve gravar uma exceção e, em seguida, retornar `null`.</span><span class="sxs-lookup"><span data-stu-id="d670f-143">If the drive cannot be removed, the method should write an exception and then return `null`.</span></span> <span data-ttu-id="d670f-144">Se seu provedor não substitui esse método, a implementação padrão desse método retorna apenas as informações de unidade passadas como entrada.</span><span class="sxs-lookup"><span data-stu-id="d670f-144">If your provider does not override this method, the default implementation of this method just returns the drive information passed as input.</span></span>

## <a name="initializing-default-drives"></a><span data-ttu-id="d670f-145">Unidades de inicialização padrão</span><span class="sxs-lookup"><span data-stu-id="d670f-145">Initializing Default Drives</span></span>

<span data-ttu-id="d670f-146">Seu implementa de provedor de unidade do [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) método montar unidades.</span><span class="sxs-lookup"><span data-stu-id="d670f-146">Your drive provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method to mount drives.</span></span> <span data-ttu-id="d670f-147">Por exemplo, o provedor do Active Directory pode montar uma unidade para o contexto de nomenclatura se o computador tiver ingressado em um domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="d670f-147">For example, the Active Directory provider might mount a drive for the default naming context if the computer is joined to a domain.</span></span>

<span data-ttu-id="d670f-148">Esse método retorna uma coleção de informações sobre as unidades inicializadas da unidade ou uma coleção vazia.</span><span class="sxs-lookup"><span data-stu-id="d670f-148">This method returns a collection of drive information about the initialized drives, or an empty collection.</span></span> <span data-ttu-id="d670f-149">A chamada para esse método é feita após a tempo de execução do Windows PowerShell chama o [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) método para inicializar o provedor.</span><span class="sxs-lookup"><span data-stu-id="d670f-149">The call to this method is made after the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to initialize the provider.</span></span>

<span data-ttu-id="d670f-150">Este provedor de unidade não substitui o [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) método.</span><span class="sxs-lookup"><span data-stu-id="d670f-150">This drive provider does not override the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method.</span></span> <span data-ttu-id="d670f-151">No entanto, o código a seguir mostra a implementação do padrão, que retorna uma coleção vazia de unidade:</span><span class="sxs-lookup"><span data-stu-id="d670f-151">However, the following code shows the default implementation, which returns an empty drive collection:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a><span data-ttu-id="d670f-152">Itens a lembrar sobre a implementação InitializeDefaultDrives</span><span class="sxs-lookup"><span data-stu-id="d670f-152">Things to Remember About Implementing InitializeDefaultDrives</span></span>

<span data-ttu-id="d670f-153">Todos os provedores de unidade devem montar uma unidade de raiz para ajudar o usuário com capacidade de descoberta.</span><span class="sxs-lookup"><span data-stu-id="d670f-153">All drive providers should mount a root drive to help the user with discoverability.</span></span> <span data-ttu-id="d670f-154">A unidade raiz pode listar os locais que servem como raízes para outras unidades montadas.</span><span class="sxs-lookup"><span data-stu-id="d670f-154">The root drive might list locations that serve as roots for other mounted drives.</span></span> <span data-ttu-id="d670f-155">Por exemplo, o provedor do Active Directory pode criar uma unidade que lista os contextos de nomenclatura encontrados no `namingContext` atributos na raiz do ambiente do sistema distribuído (DSE).</span><span class="sxs-lookup"><span data-stu-id="d670f-155">For example, the Active Directory provider might create a drive that lists the naming contexts found in the `namingContext` attributes on the root Distributed System Environment (DSE).</span></span> <span data-ttu-id="d670f-156">Isso ajuda os usuários a descobrir os pontos de montagem para outras unidades.</span><span class="sxs-lookup"><span data-stu-id="d670f-156">This helps users discover mount points for other drives.</span></span>

## <a name="code-sample"></a><span data-ttu-id="d670f-157">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="d670f-157">Code Sample</span></span>

<span data-ttu-id="d670f-158">Para o código de exemplo completo, consulte [exemplo de código AccessDbProviderSample02](./accessdbprovidersample02-code-sample.md).</span><span class="sxs-lookup"><span data-stu-id="d670f-158">For complete sample code, see [AccessDbProviderSample02 Code Sample](./accessdbprovidersample02-code-sample.md).</span></span>

## <a name="testing-the-windows-powershell-drive-provider"></a><span data-ttu-id="d670f-159">Testando o provedor de unidade do PowerShell do Windows</span><span class="sxs-lookup"><span data-stu-id="d670f-159">Testing the Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="d670f-160">Quando o provedor do Windows PowerShell tiver sido registrado com o Windows PowerShell, você pode testá-lo, executando os cmdlets com suporte na linha de comando, incluindo qualquer cmdlets disponibilizados por derivação.</span><span class="sxs-lookup"><span data-stu-id="d670f-160">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line, including any cmdlets made available by derivation.</span></span> <span data-ttu-id="d670f-161">Vamos testar o provedor de unidade de exemplo.</span><span class="sxs-lookup"><span data-stu-id="d670f-161">Let's test the sample drive provider.</span></span>

1. <span data-ttu-id="d670f-162">Execute o `Get-PSProvider` cmdlet para recuperar a lista de provedores para garantir que o provedor da unidade AccessDB está presente:</span><span class="sxs-lookup"><span data-stu-id="d670f-162">Run the `Get-PSProvider` cmdlet to retrieve the list of providers to ensure that the AccessDB drive provider is present:</span></span>

   <span data-ttu-id="d670f-163">**PS> `Get-PSProvider`**</span><span class="sxs-lookup"><span data-stu-id="d670f-163">**PS> `Get-PSProvider`**</span></span>

   <span data-ttu-id="d670f-164">A seguinte saída é exibida:</span><span class="sxs-lookup"><span data-stu-id="d670f-164">The following output appears:</span></span>

   ```output
   Name                 Capabilities                  Drives
   ----                 ------------                  ------
   AccessDB             None                          {}
   Alias                ShouldProcess                 {Alias}
   Environment          ShouldProcess                 {Env}
   FileSystem           Filter, ShouldProcess         {C, Z}
   Function             ShouldProcess                 {function}
   Registry             ShouldProcess                 {HKLM, HKCU}
   ```

2. <span data-ttu-id="d670f-165">Certifique-se de que um nome de servidor de banco de dados (DSN) existe para o banco de dados, acessando o **fontes de dados** parte a **ferramentas administrativas** para o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="d670f-165">Ensure that a database server name (DSN) exists for the database by accessing the **Data Sources** portion of the **Administrative Tools** for the operating system.</span></span> <span data-ttu-id="d670f-166">No **DSN de usuário** da tabela, clique duas vezes em **banco de dados do MS Access** e adicione o caminho de unidade C:\ps\northwind.mdb.</span><span class="sxs-lookup"><span data-stu-id="d670f-166">In the **User DSN** table, double-click **MS Access Database** and add the drive path C:\ps\northwind.mdb.</span></span>

3. <span data-ttu-id="d670f-167">Crie uma nova unidade usando o provedor de unidade de exemplo:</span><span class="sxs-lookup"><span data-stu-id="d670f-167">Create a new drive using the sample drive provider:</span></span>

   <span data-ttu-id="d670f-168">**PS > new-psdrive-mydb nome-raiz c:\ps\northwind.mdb - psprovider AccessDb**</span><span class="sxs-lookup"><span data-stu-id="d670f-168">**PS> new-psdrive -name mydb -root c:\ps\northwind.mdb -psprovider AccessDb**</span></span>

   <span data-ttu-id="d670f-169">A seguinte saída é exibida:</span><span class="sxs-lookup"><span data-stu-id="d670f-169">The following output appears:</span></span>

   ```output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. <span data-ttu-id="d670f-170">Valide a conexão.</span><span class="sxs-lookup"><span data-stu-id="d670f-170">Validate the connection.</span></span> <span data-ttu-id="d670f-171">Como a conexão é definida como um membro da unidade, você pode verificar usando o cmdlet Get-PDDrive.</span><span class="sxs-lookup"><span data-stu-id="d670f-171">Because the connection is defined as a member of the drive, you can check it using the Get-PDDrive cmdlet.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d670f-172">O usuário ainda não é possível interagir com o provedor como uma unidade, como o provedor precisa de funcionalidade de contêiner para a interação.</span><span class="sxs-lookup"><span data-stu-id="d670f-172">The user cannot yet interact with the provider as a drive, as the provider needs container functionality for that interaction.</span></span> <span data-ttu-id="d670f-173">Para obter mais informações, consulte [criando um provedor de contêiner do Windows PowerShell](./creating-a-windows-powershell-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="d670f-173">For more information, see [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>

   <span data-ttu-id="d670f-174">**PS > .connection (get-psdrive mydb)**</span><span class="sxs-lookup"><span data-stu-id="d670f-174">**PS> (get-psdrive mydb).connection**</span></span>

   <span data-ttu-id="d670f-175">A seguinte saída é exibida:</span><span class="sxs-lookup"><span data-stu-id="d670f-175">The following output appears:</span></span>

   ```output
   ConnectionString  : Driver={Microsoft Access Driver (*.mdb)};DBQ=c:\ps\northwind.mdb
   ConnectionTimeout : 15
   Database          : c:\ps\northwind
   DataSource        : ACCESS
   ServerVersion     : 04.00.0000
   Driver            : odbcjt32.dll
   State             : Open
   Site              :
   Container         :
   ```

5. <span data-ttu-id="d670f-176">Remova a unidade e sair do shell:</span><span class="sxs-lookup"><span data-stu-id="d670f-176">Remove the drive and exit the shell:</span></span>

   <span data-ttu-id="d670f-177">**PS > remove-psdrive mydb**</span><span class="sxs-lookup"><span data-stu-id="d670f-177">**PS> remove-psdrive mydb**</span></span>

   <span data-ttu-id="d670f-178">**PS > Sair**</span><span class="sxs-lookup"><span data-stu-id="d670f-178">**PS> exit**</span></span>

## <a name="see-also"></a><span data-ttu-id="d670f-179">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d670f-179">See Also</span></span>

[<span data-ttu-id="d670f-180">Criação de provedores do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d670f-180">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="d670f-181">Projetar seu provedor do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d670f-181">Design Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)

[<span data-ttu-id="d670f-182">Criar um provedor de PowerShell do Windows básico</span><span class="sxs-lookup"><span data-stu-id="d670f-182">Creating a Basic Windows PowerShell Provider</span></span>](./creating-a-basic-windows-powershell-provider.md)