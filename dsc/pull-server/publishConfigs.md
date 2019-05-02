---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Publicar em um servidor de Pull usando IDs de configuração (v4/v5)
ms.openlocfilehash: 0144fec43d7a8d65b79891567cc0dc3952175343
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62079499"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a><span data-ttu-id="eef5b-103">Publicar em um servidor de Pull usando IDs de configuração (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="eef5b-103">Publish to a Pull Server using Configuration IDs (v4/v5)</span></span>

<span data-ttu-id="eef5b-104">As seções a seguir pressupõem que você já tenha configurado um servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="eef5b-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="eef5b-105">Se ainda não configurou, use os guias a seguir:</span><span class="sxs-lookup"><span data-stu-id="eef5b-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="eef5b-106">Configurar um servidor de pull SMB de DSC</span><span class="sxs-lookup"><span data-stu-id="eef5b-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="eef5b-107">Configurar um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="eef5b-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="eef5b-108">Cada nó de destino pode ser configurado para baixar configurações, recursos e até mesmo relatar seu status.</span><span class="sxs-lookup"><span data-stu-id="eef5b-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="eef5b-109">Este artigo mostrará como carregar recursos para que fiquem disponíveis para download e como configurar clientes para baixar os recursos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="eef5b-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="eef5b-110">Quando o nó recebe uma configuração atribuída, por meio de **Pull** ou **Push** (v5), ele baixa automaticamente todos os recursos necessários para a configuração do local especificado no LCM.</span><span class="sxs-lookup"><span data-stu-id="eef5b-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="compile-configurations"></a><span data-ttu-id="eef5b-111">Compilar configurações</span><span class="sxs-lookup"><span data-stu-id="eef5b-111">Compile Configurations</span></span>

<span data-ttu-id="eef5b-112">A primeira etapa para armazenar [Configurações](../configurations/configurations.md) em um servidor de pull, é compilá-los em arquivos ".mof".</span><span class="sxs-lookup"><span data-stu-id="eef5b-112">The first step to storing [Configurations](../configurations/configurations.md) on a Pull Server, is to compile them into ".mof" files.</span></span> <span data-ttu-id="eef5b-113">Para tornar uma configuração genérica e aplicável a mais clientes, use `localhost` em seu bloco de nós.</span><span class="sxs-lookup"><span data-stu-id="eef5b-113">To make a configuration generic, and applicable to more clients, use `localhost` in your Node block.</span></span> <span data-ttu-id="eef5b-114">O exemplo a seguir mostra um shell de configuração que usa `localhost` em vez de um nome de cliente específico.</span><span class="sxs-lookup"><span data-stu-id="eef5b-114">The example below shows a Configuration shell that uses `localhost` instead of a specific client name.</span></span>

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

<span data-ttu-id="eef5b-115">Depois de compilar sua configuração genérica, você deve ter um arquivo "localhost.mof".</span><span class="sxs-lookup"><span data-stu-id="eef5b-115">Once you have compiled your generic configuration, you should have a "localhost.mof" file.</span></span>

## <a name="renaming-the-mof-file"></a><span data-ttu-id="eef5b-116">Renomeando o arquivo MOF</span><span class="sxs-lookup"><span data-stu-id="eef5b-116">Renaming the MOF file</span></span>

<span data-ttu-id="eef5b-117">Você pode armazenar arquivos de configuração ".mof" em um servidor de pull como **ConfigurationName** ou **ConfigurationID**.</span><span class="sxs-lookup"><span data-stu-id="eef5b-117">You can store Configuration ".mof" files on a Pull Server by **ConfigurationName** or **ConfigurationID**.</span></span> <span data-ttu-id="eef5b-118">Dependendo de como você planeja configurar os clientes de pull, é possível escolher uma seção abaixo para renomear corretamente seus arquivos ".mof" compilados.</span><span class="sxs-lookup"><span data-stu-id="eef5b-118">Depending on how you plan to set up your pull clients, you can choose a section below to properly rename your compiled ".mof" files.</span></span>

### <a name="configuration-ids-guid"></a><span data-ttu-id="eef5b-119">IDs de configuração (GUID)</span><span class="sxs-lookup"><span data-stu-id="eef5b-119">Configuration IDs (GUID)</span></span>

<span data-ttu-id="eef5b-120">Será necessário renomear o arquivo "localhost.mof" como "<GUID>.mof".</span><span class="sxs-lookup"><span data-stu-id="eef5b-120">You will need to rename your "localhost.mof" file to "<GUID>.mof" file.</span></span> <span data-ttu-id="eef5b-121">Você pode criar um **Guid** aleatório usando o exemplo abaixo ou usando o cmdlet [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid).</span><span class="sxs-lookup"><span data-stu-id="eef5b-121">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="eef5b-122">Saída de exemplo</span><span class="sxs-lookup"><span data-stu-id="eef5b-122">Sample Output</span></span>

```output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

<span data-ttu-id="eef5b-123">Em seguida, você pode renomear o arquivo ".mof" usando qualquer método aceitável.</span><span class="sxs-lookup"><span data-stu-id="eef5b-123">You can then rename your ".mof" file using any acceptable method.</span></span> <span data-ttu-id="eef5b-124">O exemplo a seguir usa o cmdlet [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).</span><span class="sxs-lookup"><span data-stu-id="eef5b-124">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

<span data-ttu-id="eef5b-125">Para obter mais informações sobre o uso de **Guids** em seu ambiente, confira [Plan for Guids](/powershell/dsc/secureserver#guids) (Planejar-se para usar Guids).</span><span class="sxs-lookup"><span data-stu-id="eef5b-125">For more information about using **Guids** in your environment, see [Plan for Guids](/powershell/dsc/secureserver#guids).</span></span>

### <a name="configuration-names"></a><span data-ttu-id="eef5b-126">Nomes de configuração</span><span class="sxs-lookup"><span data-stu-id="eef5b-126">Configuration Names</span></span>

<span data-ttu-id="eef5b-127">Será necessário renomear o arquivo "localhost.mof" como "<Configuration Name>.mof".</span><span class="sxs-lookup"><span data-stu-id="eef5b-127">You will need to rename your "localhost.mof" file to "<Configuration Name>.mof" file.</span></span> <span data-ttu-id="eef5b-128">No exemplo a seguir, é usado o nome da configuração da seção anterior.</span><span class="sxs-lookup"><span data-stu-id="eef5b-128">In the following example, the configuration name from the previous section is used.</span></span> <span data-ttu-id="eef5b-129">Em seguida, você pode renomear o arquivo ".mof" usando qualquer método aceitável.</span><span class="sxs-lookup"><span data-stu-id="eef5b-129">You can then rename your ".mof" file using any acceptable method.</span></span> <span data-ttu-id="eef5b-130">O exemplo a seguir usa o cmdlet [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).</span><span class="sxs-lookup"><span data-stu-id="eef5b-130">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a><span data-ttu-id="eef5b-131">Criar a soma de verificação</span><span class="sxs-lookup"><span data-stu-id="eef5b-131">Create the CheckSum</span></span>

<span data-ttu-id="eef5b-132">Cada arquivo ".mof" armazenado em um servidor de pull ou compartilhamento SMB precisa ter um arquivo ".checksum" associado.</span><span class="sxs-lookup"><span data-stu-id="eef5b-132">Each ".mof" file stored on a Pull Server, or SMB share needs to have an associated ".checksum" file.</span></span> <span data-ttu-id="eef5b-133">Esse arquivo permite que os clientes saibam quando o arquivo associado ".mof" foi alterado e deve ser baixado novamente.</span><span class="sxs-lookup"><span data-stu-id="eef5b-133">This file lets clients know when the associated ".mof" file has changed and should be downloaded again.</span></span>

<span data-ttu-id="eef5b-134">Você pode criar um **CheckSum** com o cmdlet [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum).</span><span class="sxs-lookup"><span data-stu-id="eef5b-134">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) cmdlet.</span></span> <span data-ttu-id="eef5b-135">Também pode executar `New-DSCCheckSum` em um diretório de arquivos usando o parâmetro `-Path`.</span><span class="sxs-lookup"><span data-stu-id="eef5b-135">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span> <span data-ttu-id="eef5b-136">Se já existir uma soma de verificação, é possível forçá-la a ser criada novamente com o parâmetro `-Force`.</span><span class="sxs-lookup"><span data-stu-id="eef5b-136">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span> <span data-ttu-id="eef5b-137">O exemplo a seguir especificou um diretório que contém o arquivo ".mof" da seção anterior e usa o parâmetro `-Force`.</span><span class="sxs-lookup"><span data-stu-id="eef5b-137">The following example specified a directory containing the ".mof" file from the previous section, and uses the `-Force` parameter.</span></span>

```powershell
New-DscChecksum -Path '.\' -Force
```

<span data-ttu-id="eef5b-138">Nenhuma saída será exibida, mas agora você deve ver um arquivo "<GUID or Configuration Name>.mof.checksum".</span><span class="sxs-lookup"><span data-stu-id="eef5b-138">No output will be shown, but you should now see a "<GUID or Configuration Name>.mof.checksum" file.</span></span>

## <a name="where-to-store-mof-files-and-checksums"></a><span data-ttu-id="eef5b-139">Onde armazenar os arquivos MOF e as somas de verificação</span><span class="sxs-lookup"><span data-stu-id="eef5b-139">Where to store MOF files and CheckSums</span></span>

### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="eef5b-140">Em um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="eef5b-140">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="eef5b-141">Ao configurar seu servidor de Pull HTTP, conforme explicado em [Configurar um servidor de pull HTTP de DSC](pullServer.md), você especifica diretórios para as chaves **ModulePath** e **ConfigurationPath**.</span><span class="sxs-lookup"><span data-stu-id="eef5b-141">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="eef5b-142">A chave **ConfigurationPath** indica onde todos os arquivos ".mof" devem ser armazenados.</span><span class="sxs-lookup"><span data-stu-id="eef5b-142">The **ConfigurationPath** key indicates where any ".mof" files should be stored.</span></span> <span data-ttu-id="eef5b-143">O **ConfigurationPath** indica onde os arquivos ".mof" e ".checksum" devem ser armazenados.</span><span class="sxs-lookup"><span data-stu-id="eef5b-143">The **ConfigurationPath** indicates where any ".mof" files and ".checksum" files should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a><span data-ttu-id="eef5b-144">Em um compartilhamento SMB</span><span class="sxs-lookup"><span data-stu-id="eef5b-144">On an SMB Share</span></span>

<span data-ttu-id="eef5b-145">Quando você configurar um cliente de pull para usar um compartilhamento SMB, especifique um **ConfigurationRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="eef5b-145">When you set up a Pull Client to use an SMB share, you specify a **ConfigurationRepositoryShare**.</span></span> <span data-ttu-id="eef5b-146">Todos os arquivos ".mof" e ".checksum" devem ser armazenados no diretório **SourcePath** do bloco **ConfigurationRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="eef5b-146">All ".mof" files and ".checksum" files should then be stored in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a><span data-ttu-id="eef5b-147">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="eef5b-147">Next Steps</span></span>

<span data-ttu-id="eef5b-148">Em seguida, você deverá configurar clientes de pull para extrair a configuração especificada.</span><span class="sxs-lookup"><span data-stu-id="eef5b-148">Next, you will want to configure Pull Clients to pull the specified configuration.</span></span> <span data-ttu-id="eef5b-149">Para saber mais, confira um dos guias a seguir:</span><span class="sxs-lookup"><span data-stu-id="eef5b-149">For more information, see one of the following guides:</span></span>

- [<span data-ttu-id="eef5b-150">Configurar um cliente de pull usando IDs de configuração (v4)</span><span class="sxs-lookup"><span data-stu-id="eef5b-150">Set up a Pull Client using Configuration IDs (v4)</span></span>](pullClientConfigId4.md)
- [<span data-ttu-id="eef5b-151">Configurar um cliente de pull usando IDs de configuração (v5)</span><span class="sxs-lookup"><span data-stu-id="eef5b-151">Set up a Pull Client using Configuration IDs (v5)</span></span>](pullClientConfigId.md)
- [<span data-ttu-id="eef5b-152">Configurar um cliente de pull usando Nomes de configuração (v5)</span><span class="sxs-lookup"><span data-stu-id="eef5b-152">Set up a Pull Client using Configuration Names (v5)</span></span>](pullClientConfigNames.md)

## <a name="see-also"></a><span data-ttu-id="eef5b-153">Consulte também</span><span class="sxs-lookup"><span data-stu-id="eef5b-153">See also</span></span>

- [<span data-ttu-id="eef5b-154">Configurar um servidor de pull SMB de DSC</span><span class="sxs-lookup"><span data-stu-id="eef5b-154">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="eef5b-155">Configurar um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="eef5b-155">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
- [<span data-ttu-id="eef5b-156">Empacotar e carregar recursos em um servidor de pull</span><span class="sxs-lookup"><span data-stu-id="eef5b-156">Package and Upload Resources to a Pull Server</span></span>](package-upload-resources.md)
