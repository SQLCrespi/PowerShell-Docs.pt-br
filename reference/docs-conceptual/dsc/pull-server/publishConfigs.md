---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Publicar em um servidor de Pull usando IDs de configuração (v4/v5)
description: Este artigo mostra como carregar recursos para que fiquem disponíveis para download e como configurar clientes para baixar automaticamente os recursos.
ms.openlocfilehash: 20e12e3cac6b6e4a86563576f4a915429b18aadb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646831"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a><span data-ttu-id="55d08-104">Publicar em um servidor de Pull usando IDs de configuração (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="55d08-104">Publish to a Pull Server using Configuration IDs (v4/v5)</span></span>

<span data-ttu-id="55d08-105">As seções a seguir pressupõem que você já tenha configurado um servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="55d08-105">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="55d08-106">Se ainda não configurou o servidor de pull, use os guias a seguir:</span><span class="sxs-lookup"><span data-stu-id="55d08-106">If you haven't set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="55d08-107">Configurar um servidor de pull SMB de DSC</span><span class="sxs-lookup"><span data-stu-id="55d08-107">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="55d08-108">Configurar um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="55d08-108">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="55d08-109">Cada nó de destino pode ser configurado para baixar configurações, recursos e até mesmo relatar seu status.</span><span class="sxs-lookup"><span data-stu-id="55d08-109">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="55d08-110">Este artigo mostra como carregar recursos para que fiquem disponíveis para download e como configurar clientes para baixar automaticamente os recursos.</span><span class="sxs-lookup"><span data-stu-id="55d08-110">This article shows you how to upload resources so they're available to be downloaded, and configure clients to automatically download resources.</span></span> <span data-ttu-id="55d08-111">Quando o nó recebe uma configuração atribuída, por meio de **Pull** ou **Push** (v5), ele baixa automaticamente todos os recursos necessários para a configuração do local especificado no LCM (Local Configuration Manager).</span><span class="sxs-lookup"><span data-stu-id="55d08-111">When the node receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the Local Configuration Manager (LCM).</span></span>

## <a name="compile-configurations"></a><span data-ttu-id="55d08-112">Compilar configurações</span><span class="sxs-lookup"><span data-stu-id="55d08-112">Compile configurations</span></span>

<span data-ttu-id="55d08-113">A primeira etapa para armazenar [Configurações](../configurations/configurations.md) em um servidor de pull é compilá-las em arquivos `.mof`.</span><span class="sxs-lookup"><span data-stu-id="55d08-113">The first step to storing [Configurations](../configurations/configurations.md) on a Pull Server, is to compile them into `.mof` files.</span></span> <span data-ttu-id="55d08-114">Para tornar uma configuração genérica e aplicável a mais clientes, use `localhost` em seu bloco de nós.</span><span class="sxs-lookup"><span data-stu-id="55d08-114">To make a configuration generic, and applicable to more clients, use `localhost` in your Node block.</span></span> <span data-ttu-id="55d08-115">O exemplo a seguir mostra um shell de configuração que usa `localhost` em vez de um nome de cliente específico.</span><span class="sxs-lookup"><span data-stu-id="55d08-115">The example below shows a Configuration shell that uses `localhost` instead of a specific client name.</span></span>

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

<span data-ttu-id="55d08-116">Depois de compilar sua configuração genérica, você deve ter um arquivo `localhost.mof`.</span><span class="sxs-lookup"><span data-stu-id="55d08-116">Once you've compiled your generic configuration, you should have a `localhost.mof` file.</span></span>

## <a name="renaming-the-mof-file"></a><span data-ttu-id="55d08-117">Renomeando o arquivo MOF</span><span class="sxs-lookup"><span data-stu-id="55d08-117">Renaming the MOF file</span></span>

<span data-ttu-id="55d08-118">Você pode armazenar arquivos de configuração `.mof` em um servidor de pull por **ConfigurationName** ou **ConfigurationID** .</span><span class="sxs-lookup"><span data-stu-id="55d08-118">You can store Configuration `.mof` files on a Pull Server by **ConfigurationName** or **ConfigurationID** .</span></span> <span data-ttu-id="55d08-119">Dependendo de como você planeja configurar os clientes de pull, é possível escolher uma seção abaixo para renomear corretamente seus arquivos `.mof` compilados.</span><span class="sxs-lookup"><span data-stu-id="55d08-119">Depending on how you plan to set up your pull clients, you can choose a section below to properly rename your compiled `.mof` files.</span></span>

### <a name="configuration-ids-guid"></a><span data-ttu-id="55d08-120">IDs de configuração (GUID)</span><span class="sxs-lookup"><span data-stu-id="55d08-120">Configuration IDs (GUID)</span></span>

<span data-ttu-id="55d08-121">Você precisará renomear o arquivo `localhost.mof` como o arquivo `<GUID>.mof`.</span><span class="sxs-lookup"><span data-stu-id="55d08-121">You'll need to rename your `localhost.mof` file to `<GUID>.mof` file.</span></span> <span data-ttu-id="55d08-122">Você pode criar um **Guid** aleatório usando o exemplo abaixo ou usando o cmdlet [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid).</span><span class="sxs-lookup"><span data-stu-id="55d08-122">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="55d08-123">Saída de exemplo</span><span class="sxs-lookup"><span data-stu-id="55d08-123">Sample Output</span></span>

```Output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

<span data-ttu-id="55d08-124">Em seguida, você pode renomear o arquivo `.mof` usando qualquer método aceitável.</span><span class="sxs-lookup"><span data-stu-id="55d08-124">You can then rename your `.mof` file using any acceptable method.</span></span> <span data-ttu-id="55d08-125">O exemplo a seguir usa o cmdlet [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).</span><span class="sxs-lookup"><span data-stu-id="55d08-125">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

<span data-ttu-id="55d08-126">Para obter mais informações sobre o uso de **Guids** em seu ambiente, confira [Plan for Guids](secureServer.md#guids) (Planejar-se para usar Guids).</span><span class="sxs-lookup"><span data-stu-id="55d08-126">For more information about using **Guids** in your environment, see [Plan for Guids](secureServer.md#guids).</span></span>

### <a name="configuration-names"></a><span data-ttu-id="55d08-127">Nomes de configuração</span><span class="sxs-lookup"><span data-stu-id="55d08-127">Configuration names</span></span>

<span data-ttu-id="55d08-128">Você precisará renomear o arquivo `localhost.mof` como o arquivo `<Configuration Name>.mof`.</span><span class="sxs-lookup"><span data-stu-id="55d08-128">You'll need to rename your `localhost.mof` file to `<Configuration Name>.mof` file.</span></span> <span data-ttu-id="55d08-129">No exemplo a seguir, é usado o nome da configuração da seção anterior.</span><span class="sxs-lookup"><span data-stu-id="55d08-129">In the following example, the configuration name from the previous section is used.</span></span> <span data-ttu-id="55d08-130">Em seguida, você pode renomear o arquivo `.mof` usando qualquer método aceitável.</span><span class="sxs-lookup"><span data-stu-id="55d08-130">You can then rename your `.mof` file using any acceptable method.</span></span> <span data-ttu-id="55d08-131">O exemplo a seguir usa o cmdlet [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).</span><span class="sxs-lookup"><span data-stu-id="55d08-131">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a><span data-ttu-id="55d08-132">Criar a soma de verificação</span><span class="sxs-lookup"><span data-stu-id="55d08-132">Create the checkSum</span></span>

<span data-ttu-id="55d08-133">Cada arquivo `.mof` armazenado em um servidor de pull ou compartilhamento SMB precisa ter um arquivo `.checksum` associado.</span><span class="sxs-lookup"><span data-stu-id="55d08-133">Each `.mof` file stored on a Pull Server, or SMB share needs to have an associated `.checksum` file.</span></span>
<span data-ttu-id="55d08-134">Esse arquivo permite que os clientes saibam quando o arquivo `.mof` associado foi alterado e deve ser baixado novamente.</span><span class="sxs-lookup"><span data-stu-id="55d08-134">This file lets clients know when the associated `.mof` file has changed and should be downloaded again.</span></span>

<span data-ttu-id="55d08-135">Você pode criar um **CheckSum** com o cmdlet [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum).</span><span class="sxs-lookup"><span data-stu-id="55d08-135">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) cmdlet.</span></span> <span data-ttu-id="55d08-136">Também pode executar `New-DSCCheckSum` em um diretório de arquivos usando o parâmetro `-Path`.</span><span class="sxs-lookup"><span data-stu-id="55d08-136">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span>
<span data-ttu-id="55d08-137">Se já existir uma soma de verificação, é possível forçá-la a ser criada novamente com o parâmetro `-Force`.</span><span class="sxs-lookup"><span data-stu-id="55d08-137">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span> <span data-ttu-id="55d08-138">O exemplo a seguir especificou um diretório que contém o arquivo `.mof` da seção anterior e usa o parâmetro `-Force`.</span><span class="sxs-lookup"><span data-stu-id="55d08-138">The following example specified a directory containing the `.mof` file from the previous section, and uses the `-Force` parameter.</span></span>

```powershell
New-DscChecksum -Path '.\' -Force
```

<span data-ttu-id="55d08-139">Nenhuma saída será exibida, mas agora você deve ver um arquivo `<GUID or Configuration Name>.mof.checksum`.</span><span class="sxs-lookup"><span data-stu-id="55d08-139">No output will be shown, but you should now see a `<GUID or Configuration Name>.mof.checksum` file.</span></span>

## <a name="where-to-store-mof-files-and-checksums"></a><span data-ttu-id="55d08-140">Onde armazenar os arquivos MOF e as somas de verificação</span><span class="sxs-lookup"><span data-stu-id="55d08-140">Where to store MOF files and checkSums</span></span>

### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="55d08-141">Em um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="55d08-141">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="55d08-142">Ao configurar seu servidor de Pull HTTP, conforme explicado em [Configurar um servidor de pull HTTP de DSC](pullServer.md), você especifica diretórios para as chaves **ModulePath** e **ConfigurationPath** .</span><span class="sxs-lookup"><span data-stu-id="55d08-142">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="55d08-143">A chave **ModulePath** indica onde os arquivos `.zip` empacotados de um módulo devem ser armazenados.</span><span class="sxs-lookup"><span data-stu-id="55d08-143">The **ModulePath** key indicates where a module's packaged `.zip` files should be stored.</span></span> <span data-ttu-id="55d08-144">O **ConfigurationPath** indica onde os arquivos `.mof` e `.checksum` devem ser armazenados.</span><span class="sxs-lookup"><span data-stu-id="55d08-144">The **ConfigurationPath** indicates where any `.mof` files and `.checksum` files should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a><span data-ttu-id="55d08-145">Em um compartilhamento SMB</span><span class="sxs-lookup"><span data-stu-id="55d08-145">On an SMB share</span></span>

<span data-ttu-id="55d08-146">Quando você configurar um cliente de pull para usar um compartilhamento SMB, especifique um **ConfigurationRepositoryShare** .</span><span class="sxs-lookup"><span data-stu-id="55d08-146">When you set up a Pull Client to use an SMB share, you specify a **ConfigurationRepositoryShare** .</span></span>
<span data-ttu-id="55d08-147">Todos os arquivos `.mof` e `.checksum` devem ser armazenados no diretório **SourcePath** do bloco **ConfigurationRepositoryShare** .</span><span class="sxs-lookup"><span data-stu-id="55d08-147">All `.mof` files and `.checksum` files should be stored in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a><span data-ttu-id="55d08-148">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="55d08-148">Next steps</span></span>

<span data-ttu-id="55d08-149">Em seguida, configure clientes de pull para extrair a configuração especificada.</span><span class="sxs-lookup"><span data-stu-id="55d08-149">Next, you'll want to configure Pull Clients to pull the specified configuration.</span></span> <span data-ttu-id="55d08-150">Para saber mais, confira um dos guias a seguir:</span><span class="sxs-lookup"><span data-stu-id="55d08-150">For more information, see one of the following guides:</span></span>

- [<span data-ttu-id="55d08-151">Configurar um cliente de pull usando IDs de configuração (v4)</span><span class="sxs-lookup"><span data-stu-id="55d08-151">Set up a Pull Client using Configuration IDs (v4)</span></span>](pullClientConfigId4.md)
- [<span data-ttu-id="55d08-152">Configurar um cliente de pull usando IDs de configuração (v5)</span><span class="sxs-lookup"><span data-stu-id="55d08-152">Set up a Pull Client using Configuration IDs (v5)</span></span>](pullClientConfigId.md)
- [<span data-ttu-id="55d08-153">Configurar um cliente de pull usando Nomes de configuração (v5)</span><span class="sxs-lookup"><span data-stu-id="55d08-153">Set up a Pull Client using Configuration Names (v5)</span></span>](pullClientConfigNames.md)

## <a name="see-also"></a><span data-ttu-id="55d08-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="55d08-154">See also</span></span>

- [<span data-ttu-id="55d08-155">Configurar um servidor de pull SMB de DSC</span><span class="sxs-lookup"><span data-stu-id="55d08-155">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="55d08-156">Configurar um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="55d08-156">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
- [<span data-ttu-id="55d08-157">Empacotar e carregar recursos em um servidor de pull</span><span class="sxs-lookup"><span data-stu-id="55d08-157">Package and Upload Resources to a Pull Server</span></span>](package-upload-resources.md)
