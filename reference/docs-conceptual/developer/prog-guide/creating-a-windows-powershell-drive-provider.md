---
title: Criando um provedor de unidade do Windows PowerShell | Microsoft Docs
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
ms.openlocfilehash: 2e3d97e224b06bdf36ac0bc1237911e029ea762d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366825"
---
# <a name="creating-a-windows-powershell-drive-provider"></a><span data-ttu-id="88f82-102">Criar um provedor de unidade do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88f82-102">Creating a Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="88f82-103">Este tópico descreve como criar um provedor de unidade do Windows PowerShell que fornece uma maneira de acessar um armazenamento de dados por meio de uma unidade do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88f82-103">This topic describes how to create a Windows PowerShell drive provider that provides a way to access a data store through a Windows PowerShell drive.</span></span> <span data-ttu-id="88f82-104">Esse tipo de provedor também é conhecido como provedores de unidade do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88f82-104">This type of provider is also referred to as Windows PowerShell drive providers.</span></span> <span data-ttu-id="88f82-105">As unidades do Windows PowerShell usadas pelo provedor fornecem os meios para se conectar ao armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="88f82-105">The Windows PowerShell drives used by the provider provide the means to connect to the data store.</span></span>

<span data-ttu-id="88f82-106">O provedor da unidade do Windows PowerShell descrito aqui fornece acesso a um banco de dados do Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="88f82-106">The Windows PowerShell drive provider described here provides access to a Microsoft Access database.</span></span> <span data-ttu-id="88f82-107">Para esse provedor, a unidade do Windows PowerShell representa o banco de dados (é possível adicionar qualquer número de unidades a um provedor de unidade), os contêineres de nível superior da unidade representam as tabelas no banco de dados e os itens dos contêineres representam as linhas em As tabelas.</span><span class="sxs-lookup"><span data-stu-id="88f82-107">For this provider, the Windows PowerShell drive represents the database (it is possible to add any number of drives to a drive provider), the top-level containers of the drive represent the tables in the database, and the items of the containers represent the rows in the tables.</span></span>

## <a name="defining-the-windows-powershell-provider-class"></a><span data-ttu-id="88f82-108">Definindo a classe do provedor do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88f82-108">Defining the Windows PowerShell Provider Class</span></span>

<span data-ttu-id="88f82-109">O provedor de unidade deve definir uma classe .NET que deriva da classe base [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="88f82-109">Your drive provider must define a .NET class that derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="88f82-110">Aqui está a definição de classe para este provedor de unidade:</span><span class="sxs-lookup"><span data-stu-id="88f82-110">Here is the class definition for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L29-L30 "AccessDBProviderSample02.cs")]

<span data-ttu-id="88f82-111">Observe que, neste exemplo, o atributo [System. Management. Automation. Provider. Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) especifica um nome amigável para o provedor e os recursos específicos do Windows PowerShell que o provedor expõe para o tempo de execução do Windows PowerShell durante o processamento do comando.</span><span class="sxs-lookup"><span data-stu-id="88f82-111">Notice that in this example, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute specifies a user-friendly name for the provider and the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="88f82-112">Os valores possíveis para os recursos do provedor são definidos pela enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) .</span><span class="sxs-lookup"><span data-stu-id="88f82-112">The possible values for the provider capabilities are defined by the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="88f82-113">Este provedor de unidade não oferece suporte a nenhum desses recursos.</span><span class="sxs-lookup"><span data-stu-id="88f82-113">This drive provider does not support any of these capabilities.</span></span>

## <a name="defining-base-functionality"></a><span data-ttu-id="88f82-114">Definindo a funcionalidade base</span><span class="sxs-lookup"><span data-stu-id="88f82-114">Defining Base Functionality</span></span>

<span data-ttu-id="88f82-115">Conforme descrito em [criar seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md), a classe [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) deriva da classe base [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) que define os métodos necessários para inicializar e cancelar a inicialização do provedor.</span><span class="sxs-lookup"><span data-stu-id="88f82-115">As described in [Design Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class derives from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class that defines the methods needed for initializing and uninitializing the provider.</span></span> <span data-ttu-id="88f82-116">Para implementar a funcionalidade para adicionar informações de inicialização específicas da sessão e para liberar recursos que são usados pelo provedor, consulte [criando um provedor básico do Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="88f82-116">To implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span> <span data-ttu-id="88f82-117">No entanto, a maioria dos provedores (incluindo o provedor descrito aqui) pode usar a implementação padrão dessa funcionalidade fornecida pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88f82-117">However, most providers (including the provider described here) can use the default implementation of this functionality that is provided by Windows PowerShell.</span></span>

## <a name="creating-drive-state-information"></a><span data-ttu-id="88f82-118">Criando informações de estado da unidade</span><span class="sxs-lookup"><span data-stu-id="88f82-118">Creating Drive State Information</span></span>

<span data-ttu-id="88f82-119">Todos os provedores do Windows PowerShell são considerados sem monitoração de estado, o que significa que o seu provedor de unidade precisa criar qualquer informação de estado necessária para o tempo de execução do Windows PowerShell quando ele chama seu provedor.</span><span class="sxs-lookup"><span data-stu-id="88f82-119">All Windows PowerShell providers are considered stateless, which means that your drive provider needs to create any state information that is needed by the Windows PowerShell runtime when it calls your provider.</span></span>

<span data-ttu-id="88f82-120">Para este provedor de unidade, as informações de estado incluem a conexão com o banco de dados que é mantido como parte das informações da unidade.</span><span class="sxs-lookup"><span data-stu-id="88f82-120">For this drive provider, state information includes the connection to the database that is kept as part of the drive information.</span></span> <span data-ttu-id="88f82-121">Aqui está o código que mostra como essas informações são armazenadas no objeto [System. Management. Automation. PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) que descreve a unidade:</span><span class="sxs-lookup"><span data-stu-id="88f82-121">Here is code that shows how this information is stored in the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L130-L151 "AccessDBProviderSample02.cs")]

## <a name="creating-a-drive"></a><span data-ttu-id="88f82-122">Criando uma unidade</span><span class="sxs-lookup"><span data-stu-id="88f82-122">Creating a Drive</span></span>

<span data-ttu-id="88f82-123">Para permitir que o tempo de execução do Windows PowerShell crie uma unidade, o provedor de unidade deve implementar o método [System. Management. Automation. Provider. Drivecmdletprovider. NewDrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) .</span><span class="sxs-lookup"><span data-stu-id="88f82-123">To allow the Windows PowerShell runtime to create a drive, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method.</span></span> <span data-ttu-id="88f82-124">O código a seguir mostra a implementação do método [System. Management. Automation. Provider. Drivecmdletprovider. NewDrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) para este provedor de unidade:</span><span class="sxs-lookup"><span data-stu-id="88f82-124">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L42-L84 "AccessDBProviderSample02.cs")]

<span data-ttu-id="88f82-125">A substituição desse método deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88f82-125">Your override of this method should do the following:</span></span>

- <span data-ttu-id="88f82-126">Verifique se o membro [System. Management. Automation. PSDriveinfo. raiz \*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) existe e se uma conexão com o repositório de dados pode ser feita.</span><span class="sxs-lookup"><span data-stu-id="88f82-126">Verify that the [System.Management.Automation.PSDriveinfo.Root\*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) member exists and that a connection to the data store can be made.</span></span>

- <span data-ttu-id="88f82-127">Crie uma unidade e preencha o membro de conexão, em suporte ao cmdlet `New-PSDrive`.</span><span class="sxs-lookup"><span data-stu-id="88f82-127">Create a drive and populate the connection member, in support of the `New-PSDrive` cmdlet.</span></span>

- <span data-ttu-id="88f82-128">Valide o objeto [System. Management. Automation. PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) para a unidade proposta.</span><span class="sxs-lookup"><span data-stu-id="88f82-128">Validate the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object for the proposed drive.</span></span>

- <span data-ttu-id="88f82-129">Modifique o objeto [System. Management. Automation. PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) que descreve a unidade com qualquer informação de desempenho ou confiabilidade necessária ou forneça dados adicionais para os chamadores usando a unidade.</span><span class="sxs-lookup"><span data-stu-id="88f82-129">Modify the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive with any required performance or reliability information, or provide extra data for callers using the drive.</span></span>

- <span data-ttu-id="88f82-130">Manipule falhas usando o método [System. Management. Automation. Provider. cmdletprovider. WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) e, em seguida, retorne `null`.</span><span class="sxs-lookup"><span data-stu-id="88f82-130">Handle failures using the [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) method and then return `null`.</span></span>

  <span data-ttu-id="88f82-131">Esse método retorna as informações da unidade que foram passadas para o método ou uma versão específica do provedor.</span><span class="sxs-lookup"><span data-stu-id="88f82-131">This method returns either the drive information that was passed to the method or a provider-specific version of it.</span></span>

## <a name="attaching-dynamic-parameters-to-newdrive"></a><span data-ttu-id="88f82-132">Anexando parâmetros dinâmicos a NewDrive</span><span class="sxs-lookup"><span data-stu-id="88f82-132">Attaching Dynamic Parameters to NewDrive</span></span>

<span data-ttu-id="88f82-133">O cmdlet `New-PSDrive` suportado pelo seu provedor de unidade pode exigir parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="88f82-133">The `New-PSDrive` cmdlet supported by your drive provider might require additional parameters.</span></span> <span data-ttu-id="88f82-134">Para anexar esses parâmetros dinâmicos ao cmdlet, o provedor implementa o método [System. Management. Automation. Provider. Drivecmdletprovider. Newdrivedynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) .</span><span class="sxs-lookup"><span data-stu-id="88f82-134">To attach these dynamic parameters to the cmdlet, the provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) method.</span></span> <span data-ttu-id="88f82-135">Esse método retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) .</span><span class="sxs-lookup"><span data-stu-id="88f82-135">This method returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="88f82-136">Este provedor de unidade não substitui esse método.</span><span class="sxs-lookup"><span data-stu-id="88f82-136">This drive provider does not override this method.</span></span> <span data-ttu-id="88f82-137">No entanto, o código a seguir mostra a implementação padrão desse método:</span><span class="sxs-lookup"><span data-stu-id="88f82-137">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a><span data-ttu-id="88f82-138">Removendo uma unidade</span><span class="sxs-lookup"><span data-stu-id="88f82-138">Removing a Drive</span></span>

<span data-ttu-id="88f82-139">Para fechar a conexão de banco de dados, o provedor da unidade deve implementar o método [System. Management. Automation. Provider. Drivecmdletprovider. Removedrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) .</span><span class="sxs-lookup"><span data-stu-id="88f82-139">To close the database connection, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method.</span></span> <span data-ttu-id="88f82-140">Esse método fecha a conexão com a unidade depois de limpar qualquer informação específica do provedor.</span><span class="sxs-lookup"><span data-stu-id="88f82-140">This method closes the connection to the drive after cleaning up any provider-specific information.</span></span>

<span data-ttu-id="88f82-141">O código a seguir mostra a implementação do método [System. Management. Automation. Provider. Drivecmdletprovider. Removedrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) para este provedor de unidade:</span><span class="sxs-lookup"><span data-stu-id="88f82-141">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L91-L116 "AccessDBProviderSample02.cs")]

<span data-ttu-id="88f82-142">Se a unidade puder ser removida, o método deverá retornar as informações passadas para o método por meio do parâmetro `drive`.</span><span class="sxs-lookup"><span data-stu-id="88f82-142">If the drive can be removed, the method should return the information passed to the method through the `drive` parameter.</span></span> <span data-ttu-id="88f82-143">Se a unidade não puder ser removida, o método deverá gravar uma exceção e, em seguida, retornar `null`.</span><span class="sxs-lookup"><span data-stu-id="88f82-143">If the drive cannot be removed, the method should write an exception and then return `null`.</span></span> <span data-ttu-id="88f82-144">Se o seu provedor não substituir esse método, a implementação padrão desse método retornará apenas as informações da unidade passadas como entrada.</span><span class="sxs-lookup"><span data-stu-id="88f82-144">If your provider does not override this method, the default implementation of this method just returns the drive information passed as input.</span></span>

## <a name="initializing-default-drives"></a><span data-ttu-id="88f82-145">Inicializando unidades padrão</span><span class="sxs-lookup"><span data-stu-id="88f82-145">Initializing Default Drives</span></span>

<span data-ttu-id="88f82-146">O provedor de unidade implementa o método [System. Management. Automation. Provider. Drivecmdletprovider. Initializedefaultdrives \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) para montar unidades.</span><span class="sxs-lookup"><span data-stu-id="88f82-146">Your drive provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method to mount drives.</span></span> <span data-ttu-id="88f82-147">Por exemplo, o provedor de Active Directory pode montar uma unidade para o contexto de nomenclatura padrão se o computador for ingressado em um domínio.</span><span class="sxs-lookup"><span data-stu-id="88f82-147">For example, the Active Directory provider might mount a drive for the default naming context if the computer is joined to a domain.</span></span>

<span data-ttu-id="88f82-148">Esse método retorna uma coleção de informações de unidade sobre as unidades inicializadas ou uma coleção vazia.</span><span class="sxs-lookup"><span data-stu-id="88f82-148">This method returns a collection of drive information about the initialized drives, or an empty collection.</span></span> <span data-ttu-id="88f82-149">A chamada para esse método é feita depois que o tempo de execução do Windows PowerShell chama o método [System. Management. Automation. Provider. cmdletprovider. Start \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) para inicializar o provedor.</span><span class="sxs-lookup"><span data-stu-id="88f82-149">The call to this method is made after the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to initialize the provider.</span></span>

<span data-ttu-id="88f82-150">Este provedor de unidade não substitui o método [System. Management. Automation. Provider. Drivecmdletprovider. Initializedefaultdrives \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) .</span><span class="sxs-lookup"><span data-stu-id="88f82-150">This drive provider does not override the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method.</span></span> <span data-ttu-id="88f82-151">No entanto, o código a seguir mostra a implementação padrão, que retorna uma coleção de unidades vazia:</span><span class="sxs-lookup"><span data-stu-id="88f82-151">However, the following code shows the default implementation, which returns an empty drive collection:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a><span data-ttu-id="88f82-152">Coisas a serem lembradas sobre a implementação de InitializeDefaultDrives</span><span class="sxs-lookup"><span data-stu-id="88f82-152">Things to Remember About Implementing InitializeDefaultDrives</span></span>

<span data-ttu-id="88f82-153">Todos os provedores de unidade devem montar uma unidade raiz para ajudar o usuário com a capacidade de descoberta.</span><span class="sxs-lookup"><span data-stu-id="88f82-153">All drive providers should mount a root drive to help the user with discoverability.</span></span> <span data-ttu-id="88f82-154">A unidade raiz pode listar locais que servem como raízes para outras unidades montadas.</span><span class="sxs-lookup"><span data-stu-id="88f82-154">The root drive might list locations that serve as roots for other mounted drives.</span></span> <span data-ttu-id="88f82-155">Por exemplo, o provedor de Active Directory pode criar uma unidade que lista os contextos de nomenclatura encontrados nos atributos de `namingContext` no ambiente de sistema distribuído raiz (DSE).</span><span class="sxs-lookup"><span data-stu-id="88f82-155">For example, the Active Directory provider might create a drive that lists the naming contexts found in the `namingContext` attributes on the root Distributed System Environment (DSE).</span></span> <span data-ttu-id="88f82-156">Isso ajuda os usuários a descobrir pontos de montagem para outras unidades.</span><span class="sxs-lookup"><span data-stu-id="88f82-156">This helps users discover mount points for other drives.</span></span>

## <a name="code-sample"></a><span data-ttu-id="88f82-157">Exemplo de Código</span><span class="sxs-lookup"><span data-stu-id="88f82-157">Code Sample</span></span>

<span data-ttu-id="88f82-158">Para obter o código de exemplo completo, consulte [exemplo de código AccessDbProviderSample02](./accessdbprovidersample02-code-sample.md).</span><span class="sxs-lookup"><span data-stu-id="88f82-158">For complete sample code, see [AccessDbProviderSample02 Code Sample](./accessdbprovidersample02-code-sample.md).</span></span>

## <a name="testing-the-windows-powershell-drive-provider"></a><span data-ttu-id="88f82-159">Testando o provedor de unidade do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88f82-159">Testing the Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="88f82-160">Quando o provedor do Windows PowerShell tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando os cmdlets com suporte na linha de comando, incluindo todos os cmdlets disponibilizados pela derivação.</span><span class="sxs-lookup"><span data-stu-id="88f82-160">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line, including any cmdlets made available by derivation.</span></span> <span data-ttu-id="88f82-161">Vamos testar o provedor de unidade de exemplo.</span><span class="sxs-lookup"><span data-stu-id="88f82-161">Let's test the sample drive provider.</span></span>

1. <span data-ttu-id="88f82-162">Execute o cmdlet `Get-PSProvider` para recuperar a lista de provedores para garantir que o provedor da unidade AccessDB esteja presente:</span><span class="sxs-lookup"><span data-stu-id="88f82-162">Run the `Get-PSProvider` cmdlet to retrieve the list of providers to ensure that the AccessDB drive provider is present:</span></span>

   <span data-ttu-id="88f82-163">**> PS `Get-PSProvider`**</span><span class="sxs-lookup"><span data-stu-id="88f82-163">**PS> `Get-PSProvider`**</span></span>

   <span data-ttu-id="88f82-164">A seguinte saída é exibida:</span><span class="sxs-lookup"><span data-stu-id="88f82-164">The following output appears:</span></span>

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

2. <span data-ttu-id="88f82-165">Certifique-se de que existe um nome de servidor de banco de dados (DSN) para o banco de dado, acessando a parte de **fontes de dados** das **Ferramentas administrativas** do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="88f82-165">Ensure that a database server name (DSN) exists for the database by accessing the **Data Sources** portion of the **Administrative Tools** for the operating system.</span></span> <span data-ttu-id="88f82-166">Na tabela **DSN de usuário** , clique duas vezes em **banco de dados do MS Access** e adicione o caminho de unidade C:\ps\northwind.mdb.</span><span class="sxs-lookup"><span data-stu-id="88f82-166">In the **User DSN** table, double-click **MS Access Database** and add the drive path C:\ps\northwind.mdb.</span></span>

3. <span data-ttu-id="88f82-167">Crie uma nova unidade usando o provedor de unidade de exemplo:</span><span class="sxs-lookup"><span data-stu-id="88f82-167">Create a new drive using the sample drive provider:</span></span>

   <span data-ttu-id="88f82-168">**PS > New-PSDrive-Name MyDB-raiz c:\ps\northwind.mdb-PSProvider AccessDb**</span><span class="sxs-lookup"><span data-stu-id="88f82-168">**PS> new-psdrive -name mydb -root c:\ps\northwind.mdb -psprovider AccessDb**</span></span>

   <span data-ttu-id="88f82-169">A seguinte saída é exibida:</span><span class="sxs-lookup"><span data-stu-id="88f82-169">The following output appears:</span></span>

   ```output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. <span data-ttu-id="88f82-170">Valide a conexão.</span><span class="sxs-lookup"><span data-stu-id="88f82-170">Validate the connection.</span></span> <span data-ttu-id="88f82-171">Como a conexão é definida como um membro da unidade, você pode verificá-la usando o cmdlet Get-PDDrive.</span><span class="sxs-lookup"><span data-stu-id="88f82-171">Because the connection is defined as a member of the drive, you can check it using the Get-PDDrive cmdlet.</span></span>

   > [!NOTE]
   > <span data-ttu-id="88f82-172">O usuário ainda não pode interagir com o provedor como uma unidade, pois o provedor precisa de funcionalidade de contêiner para essa interação.</span><span class="sxs-lookup"><span data-stu-id="88f82-172">The user cannot yet interact with the provider as a drive, as the provider needs container functionality for that interaction.</span></span> <span data-ttu-id="88f82-173">Para obter mais informações, consulte [criando um provedor de contêiner do Windows PowerShell](./creating-a-windows-powershell-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="88f82-173">For more information, see [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>

   <span data-ttu-id="88f82-174">**PS > (Get-PSDrive MyDB). Connection**</span><span class="sxs-lookup"><span data-stu-id="88f82-174">**PS> (get-psdrive mydb).connection**</span></span>

   <span data-ttu-id="88f82-175">A seguinte saída é exibida:</span><span class="sxs-lookup"><span data-stu-id="88f82-175">The following output appears:</span></span>

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

5. <span data-ttu-id="88f82-176">Remova a unidade e saia do Shell:</span><span class="sxs-lookup"><span data-stu-id="88f82-176">Remove the drive and exit the shell:</span></span>

   <span data-ttu-id="88f82-177">**PS > remover-PSDrive MyDB**</span><span class="sxs-lookup"><span data-stu-id="88f82-177">**PS> remove-psdrive mydb**</span></span>

   <span data-ttu-id="88f82-178">**Saída do PS >**</span><span class="sxs-lookup"><span data-stu-id="88f82-178">**PS> exit**</span></span>

## <a name="see-also"></a><span data-ttu-id="88f82-179">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="88f82-179">See Also</span></span>

[<span data-ttu-id="88f82-180">Criando provedores do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88f82-180">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="88f82-181">Criar seu provedor do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88f82-181">Design Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)

[<span data-ttu-id="88f82-182">Criando um provedor básico do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88f82-182">Creating a Basic Windows PowerShell Provider</span></span>](./creating-a-basic-windows-powershell-provider.md)
