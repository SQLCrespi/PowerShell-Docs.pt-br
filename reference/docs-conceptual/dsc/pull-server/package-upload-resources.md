---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Empacotar e carregar recursos em um servidor de pull
description: Este artigo mostra como carregar recursos em um Servidor de Pull para que eles possam ser baixados pelas configurações nos nós gerenciados pela DSC.
ms.openlocfilehash: a19d04346a0ae546cfcaf70701fde870d3839f65
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661696"
---
# <a name="package-and-upload-resources-to-a-pull-server"></a><span data-ttu-id="40c0c-104">Empacotar e carregar recursos em um servidor de pull</span><span class="sxs-lookup"><span data-stu-id="40c0c-104">Package and Upload Resources to a Pull Server</span></span>

<span data-ttu-id="40c0c-105">As seções a seguir pressupõem que você já tenha configurado um servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="40c0c-105">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="40c0c-106">Se ainda não configurou, use os guias a seguir:</span><span class="sxs-lookup"><span data-stu-id="40c0c-106">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="40c0c-107">Configurar um servidor de pull SMB de DSC</span><span class="sxs-lookup"><span data-stu-id="40c0c-107">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="40c0c-108">Configurar um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="40c0c-108">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="40c0c-109">Cada nó de destino pode ser configurado para baixar configurações, recursos e até mesmo relatar seu status.</span><span class="sxs-lookup"><span data-stu-id="40c0c-109">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="40c0c-110">Este artigo mostrará como carregar recursos para que fiquem disponíveis para download e como configurar clientes para baixar os recursos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="40c0c-110">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="40c0c-111">Quando o nó recebe uma configuração atribuída, por meio de **Pull** ou **Push** (v5), ele baixa automaticamente todos os recursos necessários para a configuração do local especificado no LCM.</span><span class="sxs-lookup"><span data-stu-id="40c0c-111">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="package-resource-modules"></a><span data-ttu-id="40c0c-112">Módulos do recurso Package</span><span class="sxs-lookup"><span data-stu-id="40c0c-112">Package Resource Modules</span></span>

<span data-ttu-id="40c0c-113">Cada recurso disponível para um cliente fazer download deve ser armazenado em um arquivo `.zip`.</span><span class="sxs-lookup"><span data-stu-id="40c0c-113">Each resource available for a client to download must be stored in a `.zip` file.</span></span> <span data-ttu-id="40c0c-114">O exemplo a seguir mostra as etapas necessárias usando o recurso [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0).</span><span class="sxs-lookup"><span data-stu-id="40c0c-114">The example below will show the required steps using the [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0) resource.</span></span>

> [!NOTE]
> <span data-ttu-id="40c0c-115">Se você tem clientes que usam o PowerShell 4.0, é preciso reduzir a estrutura da pasta de recursos e remover as pastas de versão.</span><span class="sxs-lookup"><span data-stu-id="40c0c-115">If you have any clients using PowerShell 4.0, you will need to flatten the resource folder structure and remove any version folders.</span></span> <span data-ttu-id="40c0c-116">Para saber mais, confira [Várias versões do recurso](../configurations/import-dscresource.md#multiple-resource-versions).</span><span class="sxs-lookup"><span data-stu-id="40c0c-116">For more information, see [Multiple Resource Versions](../configurations/import-dscresource.md#multiple-resource-versions).</span></span>

<span data-ttu-id="40c0c-117">Você pode compactar o diretório de recursos usando qualquer utilitário, script ou método que preferir.</span><span class="sxs-lookup"><span data-stu-id="40c0c-117">You can compress the resource directory using any utility, script, or method that you prefer.</span></span> <span data-ttu-id="40c0c-118">No Windows, _clique com o botão direito do mouse_ no diretório `xPSDesiredStateConfiguration` e selecione **Enviar para** e em **Pasta compactada**.</span><span class="sxs-lookup"><span data-stu-id="40c0c-118">In Windows, you can _right-click_ on the `xPSDesiredStateConfiguration` directory, and select **Send To** , then **Compressed Folder**.</span></span>

![Clique com o botão direito do mouse – Enviar para – Pasta compactada](media/package-upload-resources/right-click.gif)

### <a name="naming-the-resource-archive"></a><span data-ttu-id="40c0c-120">Nomear o arquivo de recurso</span><span class="sxs-lookup"><span data-stu-id="40c0c-120">Naming the Resource Archive</span></span>

<span data-ttu-id="40c0c-121">O arquivo de recurso precisa ser nomeado com o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="40c0c-121">The Resource archive needs to be named with the following format:</span></span>

```
{ModuleName}_{Version}.zip
```

<span data-ttu-id="40c0c-122">No exemplo acima, `xPSDesiredStateConfiguration.zip` deve ser renomeado como `xPSDesiredStateConfiguration_8.4.4.0.zip`.</span><span class="sxs-lookup"><span data-stu-id="40c0c-122">In the example above, `xPSDesiredStateConfiguration.zip` should be renamed `xPSDesiredStateConfiguration_8.4.4.0.zip`.</span></span>

### <a name="create-checksums"></a><span data-ttu-id="40c0c-123">Criar somas de verificação</span><span class="sxs-lookup"><span data-stu-id="40c0c-123">Create CheckSums</span></span>

<span data-ttu-id="40c0c-124">Quando o módulo de recurso estiver compactado e renomeado, é preciso criar uma **soma de verificação**.</span><span class="sxs-lookup"><span data-stu-id="40c0c-124">Once the Resource module has been compressed and renamed, you need to create a **CheckSum**.</span></span> <span data-ttu-id="40c0c-125">A **soma de verificação** é usada pelo LCM no cliente, para determinar se o recurso foi alterado e precisa ser baixado novamente.</span><span class="sxs-lookup"><span data-stu-id="40c0c-125">The **CheckSum** is used, by the LCM on the client, to determine if the resource has been changed, and needs to be downloaded again.</span></span> <span data-ttu-id="40c0c-126">Você pode criar uma **soma de verificação** com o cmdlet [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum), como mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="40c0c-126">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet, as shown in the example below.</span></span>

```powershell
New-DscChecksum -Path .\xPSDesiredStateConfiguration_8.4.4.0.zip
```

<span data-ttu-id="40c0c-127">Nenhuma saída é exibida, mas agora você deve ver "xPSDesiredStateConfiguration_8.4.4.0.zip.checksum".</span><span class="sxs-lookup"><span data-stu-id="40c0c-127">No output will be shown, but you should now see a "xPSDesiredStateConfiguration_8.4.4.0.zip.checksum".</span></span> <span data-ttu-id="40c0c-128">Também pode executar `New-DSCCheckSum` em um diretório de arquivos usando o parâmetro `-Path`.</span><span class="sxs-lookup"><span data-stu-id="40c0c-128">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span> <span data-ttu-id="40c0c-129">Se já existir uma soma de verificação, é possível forçá-la a ser criada novamente com o parâmetro `-Force`.</span><span class="sxs-lookup"><span data-stu-id="40c0c-129">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span>

### <a name="where-to-store-resource-archives"></a><span data-ttu-id="40c0c-130">Onde armazenar os arquivos de recurso</span><span class="sxs-lookup"><span data-stu-id="40c0c-130">Where to store Resource Archives</span></span>

#### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="40c0c-131">Em um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="40c0c-131">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="40c0c-132">Ao configurar seu servidor de Pull HTTP, conforme explicado em [Configurar um servidor de pull HTTP de DSC](pullServer.md), você especifica diretórios para as chaves **ModulePath** e **ConfigurationPath**.</span><span class="sxs-lookup"><span data-stu-id="40c0c-132">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="40c0c-133">A chave **ConfigurationPath** indica onde todos os arquivos ".mof" devem ser armazenados.</span><span class="sxs-lookup"><span data-stu-id="40c0c-133">The **ConfigurationPath** key indicates where any ".mof" files should be stored.</span></span> <span data-ttu-id="40c0c-134">O **ModulePath** indica onde os módulos de recursos DSC devem ser armazenados.</span><span class="sxs-lookup"><span data-stu-id="40c0c-134">The **ModulePath** indicates where any DSC Resource Modules should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

#### <a name="on-an-smb-share"></a><span data-ttu-id="40c0c-135">Em um compartilhamento SMB</span><span class="sxs-lookup"><span data-stu-id="40c0c-135">On an SMB Share</span></span>

<span data-ttu-id="40c0c-136">Se você especificou um **ResourceRepositoryShare** ao configurar o seu cliente de pull, armazene os arquivos e as somas de verificação no diretório **SourcePath** do bloco **ResourceRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="40c0c-136">If you specified a **ResourceRepositoryShare** , when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ResourceRepositoryShare** block.</span></span>

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

<span data-ttu-id="40c0c-137">Se você especificou apenas um **ConfigurationRepositoryShare** ao configurar o seu cliente de pull, armazene os arquivos e as somas de verificação no diretório **SourcePath** do bloco **ConfigurationRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="40c0c-137">If you specified only a **ConfigurationRepositoryShare** , when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

#### <a name="updating-resources"></a><span data-ttu-id="40c0c-138">Atualização de recursos</span><span class="sxs-lookup"><span data-stu-id="40c0c-138">Updating resources</span></span>

<span data-ttu-id="40c0c-139">Você pode forçar um nó a atualizar seus recursos alterando o número de versão no nome de arquivo ou criando uma nova soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="40c0c-139">You can force a Node to update its resources by changing the version number in the archive's name, or by creating a new checksum.</span></span> <span data-ttu-id="40c0c-140">O cliente de pull verifica se há versões mais recentes dos recursos necessários e somas de verificação atualizadas quando o LCM é atualizado.</span><span class="sxs-lookup"><span data-stu-id="40c0c-140">The Pull Client will check for newer versions of required resources, as well as updated checksums, when its LCM refreshes.</span></span>

## <a name="see-also"></a><span data-ttu-id="40c0c-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="40c0c-141">See also</span></span>

- [<span data-ttu-id="40c0c-142">Configurar um servidor de pull SMB de DSC</span><span class="sxs-lookup"><span data-stu-id="40c0c-142">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="40c0c-143">Configurar um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="40c0c-143">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
