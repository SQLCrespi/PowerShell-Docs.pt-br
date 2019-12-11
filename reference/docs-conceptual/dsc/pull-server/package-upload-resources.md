---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Empacotar e carregar recursos em um servidor de pull
ms.openlocfilehash: 29a62f96393a53c9e7da57a5e51732dcb0937194
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954373"
---
# <a name="package-and-upload-resources-to-a-pull-server"></a><span data-ttu-id="0829a-103">Empacotar e carregar recursos em um servidor de pull</span><span class="sxs-lookup"><span data-stu-id="0829a-103">Package and Upload Resources to a Pull Server</span></span>

<span data-ttu-id="0829a-104">As seções a seguir pressupõem que você já tenha configurado um servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="0829a-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="0829a-105">Se ainda não configurou, use os guias a seguir:</span><span class="sxs-lookup"><span data-stu-id="0829a-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="0829a-106">Configurar um servidor de pull SMB de DSC</span><span class="sxs-lookup"><span data-stu-id="0829a-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="0829a-107">Configurar um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="0829a-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="0829a-108">Cada nó de destino pode ser configurado para baixar configurações, recursos e até mesmo relatar seu status.</span><span class="sxs-lookup"><span data-stu-id="0829a-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="0829a-109">Este artigo mostrará como carregar recursos para que fiquem disponíveis para download e como configurar clientes para baixar os recursos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0829a-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="0829a-110">Quando o nó recebe uma configuração atribuída, por meio de **Pull** ou **Push** (v5), ele baixa automaticamente todos os recursos necessários para a configuração do local especificado no LCM.</span><span class="sxs-lookup"><span data-stu-id="0829a-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="package-resource-modules"></a><span data-ttu-id="0829a-111">Módulos do recurso Package</span><span class="sxs-lookup"><span data-stu-id="0829a-111">Package Resource Modules</span></span>

<span data-ttu-id="0829a-112">Cada recurso disponível para um cliente fazer download deve ser armazenado em um arquivo ".zip".</span><span class="sxs-lookup"><span data-stu-id="0829a-112">Each resource available for a client to download must be stored in a ".zip" file.</span></span> <span data-ttu-id="0829a-113">O exemplo a seguir mostra as etapas necessárias usando o recurso [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0).</span><span class="sxs-lookup"><span data-stu-id="0829a-113">The example below will show the required steps using the [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0) resource.</span></span>

> [!NOTE]
> <span data-ttu-id="0829a-114">Se você tem clientes que usam o PowerShell 4.0, é preciso reduzir a estrutura da pasta de recursos e remover as pastas de versão.</span><span class="sxs-lookup"><span data-stu-id="0829a-114">If you have any clients using PowerShell 4.0, you will need to flaten the resource folder structure and remove any version folders.</span></span> <span data-ttu-id="0829a-115">Para saber mais, confira [Várias versões do recurso](../configurations/import-dscresource.md#multiple-resource-versions).</span><span class="sxs-lookup"><span data-stu-id="0829a-115">For more information, see [Multiple Resource Versions](../configurations/import-dscresource.md#multiple-resource-versions).</span></span>

<span data-ttu-id="0829a-116">Você pode compactar o diretório de recursos usando qualquer utilitário, script ou método que preferir.</span><span class="sxs-lookup"><span data-stu-id="0829a-116">You can compress the resource directory using any utility, script, or method that you prefer.</span></span> <span data-ttu-id="0829a-117">No Windows, é possível *clicar com o botão direito do mouse* no diretório "xPSDesiredStateConfiguration" e selecionar "Enviar para" e, em seguida, "Pasta compactada".</span><span class="sxs-lookup"><span data-stu-id="0829a-117">In Windows, you can *right-click* on the "xPSDesiredStateConfiguration" directory, and select "Send To", then "Compressed Folder".</span></span>

![Clicar com o botão direito do mouse](../media/right-click.gif)

### <a name="naming-the-resource-archive"></a><span data-ttu-id="0829a-119">Nomear o arquivo de recurso</span><span class="sxs-lookup"><span data-stu-id="0829a-119">Naming the Resource Archive</span></span>

<span data-ttu-id="0829a-120">O arquivo de recurso precisa ser nomeado com o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="0829a-120">The Resource archive needs to be named with the following format:</span></span>

```
{ModuleName}_{Version}.zip
```

<span data-ttu-id="0829a-121">No exemplo acima, "xPSDesiredStateConfiguration.zip" deve ser renomeado como "xPSDesiredStateConfiguration_8.4.4.0.zip".</span><span class="sxs-lookup"><span data-stu-id="0829a-121">In the example above, "xPSDesiredStateConfiguration.zip" should be renamed "xPSDesiredStateConfiguration_8.4.4.0.zip".</span></span>

### <a name="create-checksums"></a><span data-ttu-id="0829a-122">Criar somas de verificação</span><span class="sxs-lookup"><span data-stu-id="0829a-122">Create CheckSums</span></span>

<span data-ttu-id="0829a-123">Quando o módulo de recurso estiver compactado e renomeado, é preciso criar uma **soma de verificação**.</span><span class="sxs-lookup"><span data-stu-id="0829a-123">Once the Resource module has been compressed and renamed, you need to create a **CheckSum**.</span></span>  <span data-ttu-id="0829a-124">A **soma de verificação** é usada pelo LCM no cliente, para determinar se o recurso foi alterado e precisa ser baixado novamente.</span><span class="sxs-lookup"><span data-stu-id="0829a-124">The **CheckSum** is used, by the LCM on the client, to determine if the resource has been changed, and needs to be downloaded again.</span></span> <span data-ttu-id="0829a-125">Você pode criar uma **soma de verificação** com o cmdlet [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum), como mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="0829a-125">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet, as shown in the example below.</span></span>

```powershell
New-DscChecksum -Path .\xPSDesiredStateConfiguration_8.4.4.0.zip
```

<span data-ttu-id="0829a-126">Nenhuma saída é exibida, mas agora você deve ver "xPSDesiredStateConfiguration_8.4.4.0.zip.checksum".</span><span class="sxs-lookup"><span data-stu-id="0829a-126">No output will be shown, but you should now see a "xPSDesiredStateConfiguration_8.4.4.0.zip.checksum".</span></span> <span data-ttu-id="0829a-127">Também pode executar `New-DSCCheckSum` em um diretório de arquivos usando o parâmetro `-Path`.</span><span class="sxs-lookup"><span data-stu-id="0829a-127">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span> <span data-ttu-id="0829a-128">Se já existir uma soma de verificação, é possível forçá-la a ser criada novamente com o parâmetro `-Force`.</span><span class="sxs-lookup"><span data-stu-id="0829a-128">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span>

### <a name="where-to-store-resource-archives"></a><span data-ttu-id="0829a-129">Onde armazenar os arquivos de recurso</span><span class="sxs-lookup"><span data-stu-id="0829a-129">Where to store Resource Archives</span></span>

#### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="0829a-130">Em um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="0829a-130">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="0829a-131">Ao configurar seu servidor de Pull HTTP, conforme explicado em [Configurar um servidor de pull HTTP de DSC](pullServer.md), você especifica diretórios para as chaves **ModulePath** e **ConfigurationPath**.</span><span class="sxs-lookup"><span data-stu-id="0829a-131">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="0829a-132">A chave **ConfigurationPath** indica onde todos os arquivos ".mof" devem ser armazenados.</span><span class="sxs-lookup"><span data-stu-id="0829a-132">The **ConfigurationPath** key indicates where any ".mof" files should be stored.</span></span> <span data-ttu-id="0829a-133">O **ModulePath** indica onde os módulos de recursos DSC devem ser armazenados.</span><span class="sxs-lookup"><span data-stu-id="0829a-133">The **ModulePath** indicates where any DSC Resource Modules should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

#### <a name="on-an-smb-share"></a><span data-ttu-id="0829a-134">Em um compartilhamento SMB</span><span class="sxs-lookup"><span data-stu-id="0829a-134">On an SMB Share</span></span>

<span data-ttu-id="0829a-135">Se você especificou um **ResourceRepositoryShare** ao configurar o seu cliente de pull, armazene os arquivos e as somas de verificação no diretório **SourcePath** do bloco **ResourceRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="0829a-135">If you specified a **ResourceRepositoryShare**, when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ResourceRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Configurations'
}

ResourceRepositoryShare SMBResourceServer
{
    SourcePath = '\\SMBPullServer\Resources'
}
```

<span data-ttu-id="0829a-136">Se você especificou apenas um **ConfigurationRepositoryShare** ao configurar o seu cliente de pull, armazene os arquivos e as somas de verificação no diretório **SourcePath** do bloco **ConfigurationRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="0829a-136">If you specified only a **ConfigurationRepositoryShare**, when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

#### <a name="updating-resources"></a><span data-ttu-id="0829a-137">Atualização de recursos</span><span class="sxs-lookup"><span data-stu-id="0829a-137">Updating resources</span></span>

<span data-ttu-id="0829a-138">Você pode forçar um nó a atualizar seus recursos alterando o número de versão no nome de arquivo ou criando uma nova soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="0829a-138">You can force a Node to update its resources by changing the version number in the archive's name, or by creating a new checksum.</span></span> <span data-ttu-id="0829a-139">O cliente de pull verifica se há versões mais recentes dos recursos necessários e somas de verificação atualizadas quando o LCM é atualizado.</span><span class="sxs-lookup"><span data-stu-id="0829a-139">The Pull Client will check for newer versions of required resources, as well as updated checksums, when its LCM refreshes.</span></span>

## <a name="see-also"></a><span data-ttu-id="0829a-140">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0829a-140">See also</span></span>

- [<span data-ttu-id="0829a-141">Configurar um servidor de pull SMB de DSC</span><span class="sxs-lookup"><span data-stu-id="0829a-141">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="0829a-142">Configurar um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="0829a-142">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
