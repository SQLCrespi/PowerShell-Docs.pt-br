---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: 66a6bfeda557894e224753018ff9087de9887cc7
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892841"
---
# <span data-ttu-id="b4627-103">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="b4627-103">Get-PackageProvider</span></span>

## <span data-ttu-id="b4627-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b4627-104">SYNOPSIS</span></span>
<span data-ttu-id="b4627-105">Retorna uma lista de provedores de pacote que estão conectados a Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="b4627-105">Returns a list of package providers that are connected to Package Management.</span></span>

## <span data-ttu-id="b4627-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b4627-106">SYNTAX</span></span>

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="b4627-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b4627-107">DESCRIPTION</span></span>
<span data-ttu-id="b4627-108">O cmdlet **Get-packageprovider** retorna uma lista de provedores de pacote que estão conectados a gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="b4627-108">The **Get-PackageProvider** cmdlet returns a list of package providers that are connected to Package Management.</span></span>
<span data-ttu-id="b4627-109">Exemplos desses provedores incluem PSModule, NuGet e Chocolatey.</span><span class="sxs-lookup"><span data-stu-id="b4627-109">Examples of these providers include PSModule, NuGet, and Chocolatey.</span></span>
<span data-ttu-id="b4627-110">Você pode filtrar os resultados com base em todos ou em parte de um ou mais nomes de provedor.</span><span class="sxs-lookup"><span data-stu-id="b4627-110">You can filter the results based on all or part of one or more provider names.</span></span>

## <span data-ttu-id="b4627-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b4627-111">EXAMPLES</span></span>

### <span data-ttu-id="b4627-112">Exemplo 1: obter todos os provedores de pacote carregados no momento</span><span class="sxs-lookup"><span data-stu-id="b4627-112">Example 1: Get all currently loaded package providers</span></span>

```
PS C:\> Get-PackageProvider
```

<span data-ttu-id="b4627-113">Esse comando obtém uma lista de todos os provedores de pacote carregados no computador local.</span><span class="sxs-lookup"><span data-stu-id="b4627-113">This command gets a list of all the package providers that are currently loaded on the local computer.</span></span>

### <span data-ttu-id="b4627-114">Exemplo 2: obter todos os provedores de pacote disponíveis</span><span class="sxs-lookup"><span data-stu-id="b4627-114">Example 2: Get all available package providers</span></span>

```
PS C:\> Get-PackageProvider -ListAvailable
```

<span data-ttu-id="b4627-115">Esse comando obtém uma lista de todos os provedores de pacote que estão disponíveis no computador local.</span><span class="sxs-lookup"><span data-stu-id="b4627-115">This command gets a list of all package providers that are available on the local computer.</span></span>

### <span data-ttu-id="b4627-116">Exemplo 3: obter dinamicamente um provedor de pacote</span><span class="sxs-lookup"><span data-stu-id="b4627-116">Example 3: Dynamically get a package provider</span></span>

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

<span data-ttu-id="b4627-117">Esse comando instala automaticamente o provedor de Chocolatey se o seu computador não tiver o provedor de Chocolatey instalado.</span><span class="sxs-lookup"><span data-stu-id="b4627-117">This command automatically installs the Chocolatey provider if your computer does not have the Chocolatey provider installed.</span></span>

## <span data-ttu-id="b4627-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b4627-118">PARAMETERS</span></span>

### <span data-ttu-id="b4627-119">-Force</span><span class="sxs-lookup"><span data-stu-id="b4627-119">-Force</span></span>
<span data-ttu-id="b4627-120">Indica que esse cmdlet força todas as outras ações com esse cmdlet que podem ser forçadas.</span><span class="sxs-lookup"><span data-stu-id="b4627-120">Indicates that this cmdlet forces all other actions with this cmdlet that can be forced.</span></span>
<span data-ttu-id="b4627-121">Em **Get-packageprovider**, isso significa que o parâmetro *Force* age da mesma forma que o parâmetro *ForceBootstrap* .</span><span class="sxs-lookup"><span data-stu-id="b4627-121">In **Get-PackageProvider**, this means the *Force* parameter acts the same as the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="b4627-122">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="b4627-122">-ForceBootstrap</span></span>
<span data-ttu-id="b4627-123">Indica que esse cmdlet força Gerenciamento de Pacotes a instalar automaticamente o provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="b4627-123">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="b4627-124">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="b4627-124">-ListAvailable</span></span>
<span data-ttu-id="b4627-125">Obtém todos os provedores instalados.</span><span class="sxs-lookup"><span data-stu-id="b4627-125">Gets all installed providers.</span></span>
<span data-ttu-id="b4627-126">**Get-packageprovider** Obtém o provedor em caminhos listados na variável de ambiente **PSModulePath** , bem como as pastas de assembly do provedor de pacote:</span><span class="sxs-lookup"><span data-stu-id="b4627-126">**Get-PackageProvider** gets provider in paths listed in the **PSModulePath** environment variable as well as the package provider assembly folders:</span></span>

<span data-ttu-id="b4627-127">**$env:P rogramFiles\PackageManagement\ProviderAssemblies \* \* \* \* $env: LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span><span class="sxs-lookup"><span data-stu-id="b4627-127">**$env:ProgramFiles\PackageManagement\ProviderAssemblies\*\*\*\*$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span></span>

<span data-ttu-id="b4627-128">Sem esse parâmetro, **Get-packageprovider** obtém somente os provedores carregados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b4627-128">Without this parameter, **Get-PackageProvider** gets only the providers loaded in the current session.</span></span>

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

### <span data-ttu-id="b4627-129">-Name</span><span class="sxs-lookup"><span data-stu-id="b4627-129">-Name</span></span>
<span data-ttu-id="b4627-130">Especifica um ou mais nomes de provedor ou nomes de provedor parciais.</span><span class="sxs-lookup"><span data-stu-id="b4627-130">Specifies one or more provider names, or partial provider names.</span></span>
<span data-ttu-id="b4627-131">Separe vários nomes de provedor com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="b4627-131">Separate multiple provider names with commas.</span></span>
<span data-ttu-id="b4627-132">Os valores válidos para esse parâmetro incluem nomes de provedores que você instalou com pacotes; O PackageManagement é fornecido com um conjunto de provedores padrão, incluindo os provedores **PSModule** e **MSI** .</span><span class="sxs-lookup"><span data-stu-id="b4627-132">Valid values for this parameter include names of providers that you have installed with packages; PackageManagement ships with a set of default providers, including the **PSModule** and **MSI** providers.</span></span>

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

### <span data-ttu-id="b4627-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b4627-133">CommonParameters</span></span>
<span data-ttu-id="b4627-134">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b4627-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b4627-135">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b4627-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b4627-136">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b4627-136">INPUTS</span></span>

## <span data-ttu-id="b4627-137">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b4627-137">OUTPUTS</span></span>

### <span data-ttu-id="b4627-138">Packageprovider []</span><span class="sxs-lookup"><span data-stu-id="b4627-138">PackageProvider[]</span></span>

## <span data-ttu-id="b4627-139">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b4627-139">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4627-140">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="b4627-140">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="b4627-141">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4627-141">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="b4627-142">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="b4627-142">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="b4627-143">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4627-143">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="b4627-144">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b4627-144">RELATED LINKS</span></span>

[<span data-ttu-id="b4627-145">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="b4627-145">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="b4627-146">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="b4627-146">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="b4627-147">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="b4627-147">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="b4627-148">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="b4627-148">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
