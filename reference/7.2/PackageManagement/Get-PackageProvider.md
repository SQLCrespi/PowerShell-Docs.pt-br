---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: fd8325f1a68755ee1b5c05719a04e71b22a7e9fd
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99595561"
---
# <span data-ttu-id="d04eb-102">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="d04eb-102">Get-PackageProvider</span></span>

## <span data-ttu-id="d04eb-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d04eb-103">SYNOPSIS</span></span>
<span data-ttu-id="d04eb-104">Retorna uma lista de provedores de pacote que estão conectados a Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="d04eb-104">Returns a list of package providers that are connected to Package Management.</span></span>

## <span data-ttu-id="d04eb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d04eb-105">SYNTAX</span></span>

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="d04eb-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d04eb-106">DESCRIPTION</span></span>

<span data-ttu-id="d04eb-107">O cmdlet **Get-packageprovider** retorna uma lista de provedores de pacote que estão conectados a gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="d04eb-107">The **Get-PackageProvider** cmdlet returns a list of package providers that are connected to Package Management.</span></span>
<span data-ttu-id="d04eb-108">Exemplos desses provedores incluem PSModule, NuGet e Chocolatey.</span><span class="sxs-lookup"><span data-stu-id="d04eb-108">Examples of these providers include PSModule, NuGet, and Chocolatey.</span></span>
<span data-ttu-id="d04eb-109">Você pode filtrar os resultados com base em todos ou em parte de um ou mais nomes de provedor.</span><span class="sxs-lookup"><span data-stu-id="d04eb-109">You can filter the results based on all or part of one or more provider names.</span></span>

## <span data-ttu-id="d04eb-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d04eb-110">EXAMPLES</span></span>

### <span data-ttu-id="d04eb-111">Exemplo 1: obter todos os provedores de pacote carregados no momento</span><span class="sxs-lookup"><span data-stu-id="d04eb-111">Example 1: Get all currently loaded package providers</span></span>

```
PS C:\> Get-PackageProvider
```

<span data-ttu-id="d04eb-112">Esse comando obtém uma lista de todos os provedores de pacote carregados no computador local.</span><span class="sxs-lookup"><span data-stu-id="d04eb-112">This command gets a list of all the package providers that are currently loaded on the local computer.</span></span>

### <span data-ttu-id="d04eb-113">Exemplo 2: obter todos os provedores de pacote disponíveis</span><span class="sxs-lookup"><span data-stu-id="d04eb-113">Example 2: Get all available package providers</span></span>

```
PS C:\> Get-PackageProvider -ListAvailable
```

<span data-ttu-id="d04eb-114">Esse comando obtém uma lista de todos os provedores de pacote que estão disponíveis no computador local.</span><span class="sxs-lookup"><span data-stu-id="d04eb-114">This command gets a list of all package providers that are available on the local computer.</span></span>

### <span data-ttu-id="d04eb-115">Exemplo 3: obter dinamicamente um provedor de pacote</span><span class="sxs-lookup"><span data-stu-id="d04eb-115">Example 3: Dynamically get a package provider</span></span>

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

<span data-ttu-id="d04eb-116">Esse comando instala automaticamente o provedor de Chocolatey se o seu computador não tiver o provedor de Chocolatey instalado.</span><span class="sxs-lookup"><span data-stu-id="d04eb-116">This command automatically installs the Chocolatey provider if your computer does not have the Chocolatey provider installed.</span></span>

## <span data-ttu-id="d04eb-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d04eb-117">PARAMETERS</span></span>

### <span data-ttu-id="d04eb-118">-Force</span><span class="sxs-lookup"><span data-stu-id="d04eb-118">-Force</span></span>

<span data-ttu-id="d04eb-119">Indica que esse cmdlet força todas as outras ações com esse cmdlet que podem ser forçadas.</span><span class="sxs-lookup"><span data-stu-id="d04eb-119">Indicates that this cmdlet forces all other actions with this cmdlet that can be forced.</span></span>
<span data-ttu-id="d04eb-120">Em **Get-packageprovider**, isso significa que o parâmetro *Force* age da mesma forma que o parâmetro *ForceBootstrap* .</span><span class="sxs-lookup"><span data-stu-id="d04eb-120">In **Get-PackageProvider**, this means the *Force* parameter acts the same as the *ForceBootstrap* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d04eb-121">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="d04eb-121">-ForceBootstrap</span></span>

<span data-ttu-id="d04eb-122">Indica que esse cmdlet força Gerenciamento de Pacotes a instalar automaticamente o provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="d04eb-122">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d04eb-123">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="d04eb-123">-ListAvailable</span></span>

<span data-ttu-id="d04eb-124">Obtém todos os provedores instalados.</span><span class="sxs-lookup"><span data-stu-id="d04eb-124">Gets all installed providers.</span></span>
<span data-ttu-id="d04eb-125">**Get-packageprovider** Obtém o provedor em caminhos listados na variável de ambiente **PSModulePath** , bem como as pastas de assembly do provedor de pacote:</span><span class="sxs-lookup"><span data-stu-id="d04eb-125">**Get-PackageProvider** gets provider in paths listed in the **PSModulePath** environment variable as well as the package provider assembly folders:</span></span>

<span data-ttu-id="d04eb-126">**$env:P rogramFiles\PackageManagement\ProviderAssemblies \* \* \* \* $env: LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span><span class="sxs-lookup"><span data-stu-id="d04eb-126">**$env:ProgramFiles\PackageManagement\ProviderAssemblies\*\*\*\*$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span></span>

<span data-ttu-id="d04eb-127">Sem esse parâmetro, **Get-packageprovider** obtém somente os provedores carregados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d04eb-127">Without this parameter, **Get-PackageProvider** gets only the providers loaded in the current session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d04eb-128">-Name</span><span class="sxs-lookup"><span data-stu-id="d04eb-128">-Name</span></span>

<span data-ttu-id="d04eb-129">Especifica um ou mais nomes de provedor ou nomes de provedor parciais.</span><span class="sxs-lookup"><span data-stu-id="d04eb-129">Specifies one or more provider names, or partial provider names.</span></span>
<span data-ttu-id="d04eb-130">Separe vários nomes de provedor com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="d04eb-130">Separate multiple provider names with commas.</span></span>
<span data-ttu-id="d04eb-131">Os valores válidos para esse parâmetro incluem nomes de provedores que você instalou com pacotes; O PackageManagement é fornecido com um conjunto de provedores padrão, incluindo os provedores **PSModule** e **MSI** .</span><span class="sxs-lookup"><span data-stu-id="d04eb-131">Valid values for this parameter include names of providers that you have installed with packages; PackageManagement ships with a set of default providers, including the **PSModule** and **MSI** providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d04eb-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d04eb-132">CommonParameters</span></span>

<span data-ttu-id="d04eb-133">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d04eb-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d04eb-134">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d04eb-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d04eb-135">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d04eb-135">INPUTS</span></span>

## <span data-ttu-id="d04eb-136">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d04eb-136">OUTPUTS</span></span>

### <span data-ttu-id="d04eb-137">Packageprovider []</span><span class="sxs-lookup"><span data-stu-id="d04eb-137">PackageProvider[]</span></span>

## <span data-ttu-id="d04eb-138">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d04eb-138">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d04eb-139">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="d04eb-139">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="d04eb-140">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d04eb-140">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="d04eb-141">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="d04eb-141">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="d04eb-142">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d04eb-142">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="d04eb-143">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d04eb-143">RELATED LINKS</span></span>

[<span data-ttu-id="d04eb-144">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="d04eb-144">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="d04eb-145">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d04eb-145">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="d04eb-146">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d04eb-146">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="d04eb-147">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d04eb-147">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
