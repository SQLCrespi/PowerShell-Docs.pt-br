---
ms.date: 12/12/2018
keywords: dsc,powershell,recurso,galeria,instalação
title: Instalar recursos adicionais do DSC
ms.openlocfilehash: ecaf176230ccd934b57b1c27d72ff83e6ba906e9
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954483"
---
# <a name="install-additional-dsc-resources"></a><span data-ttu-id="09f8e-103">Instalar recursos adicionais do DSC</span><span class="sxs-lookup"><span data-stu-id="09f8e-103">Install Additional DSC Resources</span></span>

<span data-ttu-id="09f8e-104">O PowerShell inclui vários recursos prontos para uso no DSC (Desired State Configuration).</span><span class="sxs-lookup"><span data-stu-id="09f8e-104">PowerShell includes several Out-of-the-box resources for Desired State Configuration (DSC).</span></span> <span data-ttu-id="09f8e-105">O módulo **PSDesiredStateConfiguration** contém todos os recursos DSC OOB disponíveis na instância específica do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09f8e-105">The **PSDesiredStateConfiguration** module contains all of the OOB DSC resources available on your specific instance of PowerShell.</span></span>

<span data-ttu-id="09f8e-106">Esta é uma lista dos recursos OOB incluídos no PowerShell 4.0 e uma descrição das capacidades dos recursos.</span><span class="sxs-lookup"><span data-stu-id="09f8e-106">This is a list of the OOB resources included in PowerShell 4.0 and a description of the resource's capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="09f8e-107">Essa lista está incompleta, pois o número de recursos OOB cresce a cada versão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09f8e-107">This is an incomplete list, as the number of OOB resources has grown with each version of PowerShell.</span></span>

|<span data-ttu-id="09f8e-108">Recurso</span><span class="sxs-lookup"><span data-stu-id="09f8e-108">Resource</span></span>  |<span data-ttu-id="09f8e-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="09f8e-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="09f8e-110">**File**</span><span class="sxs-lookup"><span data-stu-id="09f8e-110">**File**</span></span>|<span data-ttu-id="09f8e-111">Controla o estado dos arquivos e diretórios.</span><span class="sxs-lookup"><span data-stu-id="09f8e-111">Controls the state of files and directories.</span></span> <span data-ttu-id="09f8e-112">Copia os arquivos de uma **Fonte** para um **Destino** e os atualiza quando a **Fonte** muda comparando datas, somas de verificação e hashes.</span><span class="sxs-lookup"><span data-stu-id="09f8e-112">Copies files from a **Source** to a **Destination** and updates them when the **Source** changes by comparing dates, checksums, and hashes.</span></span>|
|<span data-ttu-id="09f8e-113">**Archive**</span><span class="sxs-lookup"><span data-stu-id="09f8e-113">**Archive**</span></span>|<span data-ttu-id="09f8e-114">Desempacota os arquivos e um local especificado.</span><span class="sxs-lookup"><span data-stu-id="09f8e-114">Unpacks archives and a specified location.</span></span> <span data-ttu-id="09f8e-115">Valida os arquivos com a **soma de verificação** especificada.</span><span class="sxs-lookup"><span data-stu-id="09f8e-115">Validates the archives with a specified **Checksum**.</span></span>|
|<span data-ttu-id="09f8e-116">**Environment**</span><span class="sxs-lookup"><span data-stu-id="09f8e-116">**Environment**</span></span>|<span data-ttu-id="09f8e-117">Gerencia as variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="09f8e-117">Manages environment variables.</span></span>|
|<span data-ttu-id="09f8e-118">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="09f8e-118">**Group**</span></span>|<span data-ttu-id="09f8e-119">Gerencia os grupos locais e controla a associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="09f8e-119">Manages local groups and controls group membership.</span></span>|
|<span data-ttu-id="09f8e-120">**Log**</span><span class="sxs-lookup"><span data-stu-id="09f8e-120">**Log**</span></span>|<span data-ttu-id="09f8e-121">Grava as mensagens no log de eventos `Microsoft-Windows-Desired State Configuration/Analytic`.</span><span class="sxs-lookup"><span data-stu-id="09f8e-121">Writes messages to the `Microsoft-Windows-Desired State Configuration/Analytic` event log.</span></span>|
|<span data-ttu-id="09f8e-122">**Pacote**</span><span class="sxs-lookup"><span data-stu-id="09f8e-122">**Package**</span></span>|<span data-ttu-id="09f8e-123">Instala ou desinstala pacotes usando **Arguments**, **LogPath**, **ReturnCode** e outras configurações.</span><span class="sxs-lookup"><span data-stu-id="09f8e-123">Installs or uninstalls packages using **Arguments**, **LogPath**, **ReturnCode**, other settings.</span></span>|
|<span data-ttu-id="09f8e-124">**Registry**</span><span class="sxs-lookup"><span data-stu-id="09f8e-124">**Registry**</span></span>|<span data-ttu-id="09f8e-125">Gerencia os valores e as chaves do registro.</span><span class="sxs-lookup"><span data-stu-id="09f8e-125">Manages registry keys and values.</span></span>|
|<span data-ttu-id="09f8e-126">**Script**</span><span class="sxs-lookup"><span data-stu-id="09f8e-126">**Script**</span></span>|<span data-ttu-id="09f8e-127">Permite que você crie seus próprios blocos de script [get-test-set](../resources/get-test-set.md).</span><span class="sxs-lookup"><span data-stu-id="09f8e-127">Allows you to design your own [get-test-set](../resources/get-test-set.md) script blocks.</span></span>|
|<span data-ttu-id="09f8e-128">**Service**</span><span class="sxs-lookup"><span data-stu-id="09f8e-128">**Service**</span></span>|<span data-ttu-id="09f8e-129">Configura os serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="09f8e-129">Configures Windows services.</span></span>|
|<span data-ttu-id="09f8e-130">**User**</span><span class="sxs-lookup"><span data-stu-id="09f8e-130">**User**</span></span> |<span data-ttu-id="09f8e-131">Gerencia os atributos e usuários locais.</span><span class="sxs-lookup"><span data-stu-id="09f8e-131">Manages local users and attributes.</span></span>|
|<span data-ttu-id="09f8e-132">**WindowsFeature**</span><span class="sxs-lookup"><span data-stu-id="09f8e-132">**WindowsFeature**</span></span>|<span data-ttu-id="09f8e-133">Gerencia as funções e os recursos.</span><span class="sxs-lookup"><span data-stu-id="09f8e-133">Manages roles and features.</span></span>|
|<span data-ttu-id="09f8e-134">**WindowsProcess**</span><span class="sxs-lookup"><span data-stu-id="09f8e-134">**WindowsProcess**</span></span>|<span data-ttu-id="09f8e-135">Configura os processos do Windows.</span><span class="sxs-lookup"><span data-stu-id="09f8e-135">Configures Windows processes.</span></span>|

<span data-ttu-id="09f8e-136">Os recursos OOB proporcionam um bom ponto de partida para operações comuns.</span><span class="sxs-lookup"><span data-stu-id="09f8e-136">The OOB resources allow a good starting point for common operations.</span></span> <span data-ttu-id="09f8e-137">Se os recursos OOB não atenderem às suas necessidades, você poderá escrever seu próprio [Recurso personalizado](../resources/authoringResource.md).</span><span class="sxs-lookup"><span data-stu-id="09f8e-137">If the OOB resources do not meet your needs, you can write your own [Custom Resource](../resources/authoringResource.md).</span></span> <span data-ttu-id="09f8e-138">Antes de escrever um recurso personalizado para resolver seu problema, procure na vasta gama de recursos DSC que já foram criados pela Microsoft e pela comunidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09f8e-138">Before you write a custom resource to solve your problem, you should look through the vast number of DSC resources that have already been created by both Microsoft and the PowerShell community.</span></span>

<span data-ttu-id="09f8e-139">Você pode encontrar recursos DSC na [Galeria do PowerShell](https://www.powershellgallery.com/) e no [GitHub](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="09f8e-139">You can find DSC resources in both the [PowerShell Gallery](https://www.powershellgallery.com/) and [GitHub](https://github.com/).</span></span> <span data-ttu-id="09f8e-140">Também é possível instalar recursos DSC diretamente do console do PowerShell usando o [PowerShellGet](/powershell/module/powershellget/).</span><span class="sxs-lookup"><span data-stu-id="09f8e-140">You can also install DSC resources directly from the PowerShell console using [PowerShellGet](/powershell/module/powershellget/).</span></span>

## <a name="installing-powershellget"></a><span data-ttu-id="09f8e-141">Instalando o PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="09f8e-141">Installing PowerShellGet</span></span>

<span data-ttu-id="09f8e-142">Para determinar se você já tem o **PowerShell** ou para obter ajuda para instalá-lo, confira o guia a seguir: [Instalando o PowerShellGet](/powershell/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="09f8e-142">To determine if you already have **PowerShell** get, or to get help installing it, see the following guide: [Installing PowerShellGet](/powershell/gallery/installing-psget).</span></span>

## <a name="finding-dsc-resources-using-powershellget"></a><span data-ttu-id="09f8e-143">Localizar os recursos DSC usando o PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="09f8e-143">Finding DSC resources using PowerShellGet</span></span>

<span data-ttu-id="09f8e-144">Assim que o **PowerShellGet** é instalado no sistema, você pode localizar e instalar os recursos DSC hospedados na [Galeria do PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="09f8e-144">Once **PowerShellGet** is installed on your system, you can find and install DSC resources hosted in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>

<span data-ttu-id="09f8e-145">Primeiro, use o cmdlet [Find-DSCResource](/powershell/module/powershellget/find-dscresource) para localizar os recursos DSC.</span><span class="sxs-lookup"><span data-stu-id="09f8e-145">First, use the [Find-DSCResource](/powershell/module/powershellget/find-dscresource) cmdlet to find DSC resources.</span></span> <span data-ttu-id="09f8e-146">Ao executar `Find-DSCResource` pela primeira vez, você verá o seguinte prompt para instalar o "provedor do NuGet".</span><span class="sxs-lookup"><span data-stu-id="09f8e-146">When you run `Find-DSCResource` for the first time, you see the following prompt to install the "NuGet provider".</span></span>

```
PS> Find-DSCResource

NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based repositories. The
NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies' or
'C:\Users\xAdministrator\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install the NuGet provider
 by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to
install and import the NuGet provider now?
[Y] Yes  [N] No  [?] Help (default is "Y"):
```

<span data-ttu-id="09f8e-147">Depois de pressionar "y", o provedor "NuGet" é instalado e você verá uma lista de recursos DSC que podem ser instalados da Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09f8e-147">After pressing 'y', the "NuGet" provider is installed, you see a list of DSC resources that you can install from the PowerShell Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="09f8e-148">A lista não é exibida por ser grande demais.</span><span class="sxs-lookup"><span data-stu-id="09f8e-148">List is not shown because it is very large.</span></span>

<span data-ttu-id="09f8e-149">Você também pode especificar o parâmetro `-Name` usando caracteres curinga ou o parâmetro `-Filter` sem caracteres curinga para restringir sua pesquisa.</span><span class="sxs-lookup"><span data-stu-id="09f8e-149">You can also specify the `-Name` parameter using wildcards, or `-Filter` parameter without wildcards to narrow down your search.</span></span> <span data-ttu-id="09f8e-150">Este exemplo tenta localizar um recurso DSC de "Fuso horário" usando os caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="09f8e-150">This example attempts to find a "TimeZone" DSC resource using the wildcards.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09f8e-151">Atualmente, há um bug no cmdlet `Find-DSCResource` que impede o uso de caracteres curinga nos parâmetros `-Name` e `-Filter`.</span><span class="sxs-lookup"><span data-stu-id="09f8e-151">Currently there is a bug in the `Find-DSCResource` cmdlet that prevents using wildcards in both the `-Name` and `-Filter` parameters.</span></span> <span data-ttu-id="09f8e-152">O segundo exemplo abaixo mostra uma solução alternativa usando `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="09f8e-152">The second example below shows a workaround using `Where-Object`.</span></span>

```
PS> Find-DSCResource -Name *Time*

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Carbon_EnvironmentVariable          2.6.0      Carbon                              PSGallery
Carbon_FirewallRule                 2.6.0      Carbon                              PSGallery
Carbon_Group                        2.6.0      Carbon                              PSGallery
Carbon_IniFile                      2.6.0      Carbon                              PSGallery
Carbon_Permission                   2.6.0      Carbon                              PSGallery
Carbon_Privilege                    2.6.0      Carbon                              PSGallery
Carbon_ScheduledTask                2.6.0      Carbon                              PSGallery
Carbon_Service                      2.6.0      Carbon                              PSGallery
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
xTimeZone                           1.8.0.0    xTimeZone                           PSGallery
xSqlServerDefaultDir                1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerMoveDatabaseFiles         1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerSQLDataRoot               1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerStartupParam              1.0.0      mlSqlServerDSC                      PSGallery
```

<span data-ttu-id="09f8e-153">Você também pode usar `Where-Object` para encontrar os recursos DSC com filtragem mais granular.</span><span class="sxs-lookup"><span data-stu-id="09f8e-153">You can also use `Where-Object` to find DSC resources with more granular filtering.</span></span> <span data-ttu-id="09f8e-154">Essa abordagem será mais lenta do que usar os parâmetros de filtragem integrados.</span><span class="sxs-lookup"><span data-stu-id="09f8e-154">This approach will be slower than using built in filtering parameters.</span></span>

```
PS> Find-DSCResource | Where-Object {$_.Name -like "Time*"}

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
```

<span data-ttu-id="09f8e-155">Para saber mais sobre filtragem, confira [Where-Object](/powershell/module/microsoft.powershell.core/where-object).</span><span class="sxs-lookup"><span data-stu-id="09f8e-155">For more information on filtering, see [Where-Object](/powershell/module/microsoft.powershell.core/where-object).</span></span>

## <a name="installing-dsc-resources-using-powershellget"></a><span data-ttu-id="09f8e-156">Instalar os recursos DSC usando o PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="09f8e-156">Installing DSC Resources using PowerShellGet</span></span>

<span data-ttu-id="09f8e-157">Para instalar um recurso DSC, use o cmdlet [Install-Module](/powershell/module/PowershellGet/Install-Module), especificando o nome do módulo exibido em nome do **Módulo** nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="09f8e-157">To install a DSC resource, use the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet, specifying the name of the module shown under **Module** name in your search results.</span></span>

<span data-ttu-id="09f8e-158">O recurso de "Fuso horário" existe no módulo "ComputerManagementDSC", portanto este é o módulo que o exemplo instala.</span><span class="sxs-lookup"><span data-stu-id="09f8e-158">The "TimeZone" resource exists in the "ComputerManagementDSC" module, so that is the module this example installs.</span></span>

> [!NOTE]
> <span data-ttu-id="09f8e-159">Se você não confiar na Galeria do PowerShell, verá o aviso abaixo solicitando a confirmação e mostrando como evitar avisos subsequentes nas instalações.</span><span class="sxs-lookup"><span data-stu-id="09f8e-159">If you have not trusted the PowerShell gallery, you see the warning below asking for confirmation, and instructing you how to avoid subsequent prompts on installs.</span></span>

```
PS> Install-Module -Name ComputerManagementDSC

Untrusted repository
You are installing the modules from an untrusted repository. If you trust this repository, change its
InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from
'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="09f8e-160">Pressione "y" para continuar a instalação do módulo.</span><span class="sxs-lookup"><span data-stu-id="09f8e-160">Press 'y' to continue installing the module.</span></span> <span data-ttu-id="09f8e-161">Após a instalação, verifique se o novo recurso foi instalado usando [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource).</span><span class="sxs-lookup"><span data-stu-id="09f8e-161">After install, you can verify that your new resource is installed using [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource).</span></span>

```
PS> Get-DSCResource -Name TimeZone -Syntax

TimeZone [String] #ResourceName
{
    IsSingleInstance = [string]{ Yes }
    TimeZone = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

<span data-ttu-id="09f8e-162">Também é possível exibir outros recursos no módulo recém-instalado, especificando o parâmetro `-ModuleName`.</span><span class="sxs-lookup"><span data-stu-id="09f8e-162">You can also view other resources in your newly installed module, by specifying the `-ModuleName` parameter.</span></span>

```
PS> Get-DSCResource -Module ComputerManagementDSC

ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      Computer                  ComputerManagementDsc          6.0.0.0    {Name, Credential, DependsOn, ...
PowerShell      OfflineDomainJoin         ComputerManagementDsc          6.0.0.0    {IsSingleInstance, RequestFile...
PowerShell      PowerPlan                 ComputerManagementDsc          6.0.0.0    {IsSingleInstance, Name, Depen...
PowerShell      PowerShellExecutionPolicy ComputerManagementDsc          6.0.0.0    {ExecutionPolicy, ExecutionPol...
PowerShell      ScheduledTask             ComputerManagementDsc          6.0.0.0    {TaskName, ActionArguments, Ac...
PowerShell      TimeZone                  ComputerManagementDsc          6.0.0.0    {IsSingleInstance, TimeZone, D...
PowerShell      VirtualMemory             ComputerManagementDsc          6.0.0.0    {Drive, Type, DependsOn, Initi...
```

## <a name="see-also"></a><span data-ttu-id="09f8e-163">Consulte também</span><span class="sxs-lookup"><span data-stu-id="09f8e-163">See also</span></span>

- [<span data-ttu-id="09f8e-164">O que são recursos?</span><span class="sxs-lookup"><span data-stu-id="09f8e-164">What are Resources?</span></span>](../resources/resources.md)
