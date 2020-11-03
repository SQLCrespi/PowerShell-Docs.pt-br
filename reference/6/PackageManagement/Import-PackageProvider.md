---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/import-packageprovider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PackageProvider
ms.openlocfilehash: 02731fb2c45a32d947a951c6ed39c371291f71ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194023"
---
# <span data-ttu-id="e89e7-103">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="e89e7-103">Import-PackageProvider</span></span>

## <span data-ttu-id="e89e7-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e89e7-104">SYNOPSIS</span></span>
<span data-ttu-id="e89e7-105">Adiciona Gerenciamento de Pacotes provedores de pacote à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="e89e7-105">Adds Package Management package providers to the current session.</span></span>

## <span data-ttu-id="e89e7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e89e7-106">SYNTAX</span></span>

```
Import-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="e89e7-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e89e7-107">DESCRIPTION</span></span>

<span data-ttu-id="e89e7-108">O `Import-PackageProvider` cmdlet adiciona um ou mais provedores de pacote à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="e89e7-108">The `Import-PackageProvider` cmdlet adds one or more package providers to the current session.</span></span>
<span data-ttu-id="e89e7-109">O provedor que você importar deve estar instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="e89e7-109">The provider that you import must be installed on the local computer.</span></span>

<span data-ttu-id="e89e7-110">Para obter uma lista de provedores disponíveis, execute `Get-PackageProvider -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="e89e7-110">To get a list of available providers, run `Get-PackageProvider -ListAvailable`.</span></span>
<span data-ttu-id="e89e7-111">Observe que um nome de provedor de pacote pode ser diferente do nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="e89e7-111">Note that a package provider name can be different from its module name.</span></span>

<span data-ttu-id="e89e7-112">Devido a motivos de segurança, o **PackageManagement** exige que os provedores baseados em C# contenham um `provider.manifest` .</span><span class="sxs-lookup"><span data-stu-id="e89e7-112">Due to security reasons, **PackageManagement** requires C#-based providers to contain a `provider.manifest`.</span></span> <span data-ttu-id="e89e7-113">Para obter mais informações sobre como criar um provedor com `provider.manifest` injetado, consulte os `.csproj` arquivos de projeto em [https://github.com/oneget/oneget](https://github.com/oneget/oneget) .</span><span class="sxs-lookup"><span data-stu-id="e89e7-113">For more information on how to build a provider with `provider.manifest` injected, see the `.csproj` project files on [https://github.com/oneget/oneget](https://github.com/oneget/oneget).</span></span>

## <span data-ttu-id="e89e7-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e89e7-114">EXAMPLES</span></span>

### <span data-ttu-id="e89e7-115">Exemplo 1: importar um provedor de pacote do computador local</span><span class="sxs-lookup"><span data-stu-id="e89e7-115">Example 1: Import a package provider from the local computer</span></span>

```powershell
PS C:\> Import-PackageProvider -Name "Nuget"
```

<span data-ttu-id="e89e7-116">Esse comando importa o provedor do NuGet depois que ele tiver sido instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="e89e7-116">This command imports the Nuget provider after it has been installed on the local computer.</span></span>

### <span data-ttu-id="e89e7-117">Exemplo 2: importar uma versão específica de um provedor de pacote</span><span class="sxs-lookup"><span data-stu-id="e89e7-117">Example 2: Import a specific version of a package provider</span></span>

```powershell
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider -ListAvailable
Import-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
```

<span data-ttu-id="e89e7-118">Esse comando localiza, instala e importa uma versão específica do provedor de pacotes NuGet.</span><span class="sxs-lookup"><span data-stu-id="e89e7-118">This command finds, installs, and imports a specific version of the Nuget package provider.</span></span>

## <span data-ttu-id="e89e7-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e89e7-119">PARAMETERS</span></span>

### <span data-ttu-id="e89e7-120">-Force</span><span class="sxs-lookup"><span data-stu-id="e89e7-120">-Force</span></span>

<span data-ttu-id="e89e7-121">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="e89e7-121">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="e89e7-122">Importa novamente um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="e89e7-122">Re-imports a package provider.</span></span>

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

### <span data-ttu-id="e89e7-123">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="e89e7-123">-ForceBootstrap</span></span>

<span data-ttu-id="e89e7-124">Indica que esse cmdlet força Gerenciamento de Pacotes a instalar automaticamente o provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="e89e7-124">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="e89e7-125">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e89e7-125">-MaximumVersion</span></span>

<span data-ttu-id="e89e7-126">Especifica a versão máxima permitida do provedor de pacote que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="e89e7-126">Specifies the maximum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="e89e7-127">Se você não adicionar esse parâmetro, `Import-PackageProvider` o importará a versão mais recente disponível do provedor.</span><span class="sxs-lookup"><span data-stu-id="e89e7-127">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e89e7-128">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e89e7-128">-MinimumVersion</span></span>

<span data-ttu-id="e89e7-129">Especifica a versão mínima permitida do provedor de pacote que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="e89e7-129">Specifies the minimum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="e89e7-130">Se você não adicionar esse parâmetro, `Import-PackageProvider` o importará a versão mais alta disponível do pacote que também atende a qualquer versão máxima especificada usando o parâmetro *MaximumVersion* .</span><span class="sxs-lookup"><span data-stu-id="e89e7-130">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the package that also satisfies any maximum version that is specified using the *MaximumVersion* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e89e7-131">-Name</span><span class="sxs-lookup"><span data-stu-id="e89e7-131">-Name</span></span>

<span data-ttu-id="e89e7-132">Especifica um ou mais nomes de provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="e89e7-132">Specifies one or more package provider names.</span></span> <span data-ttu-id="e89e7-133">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="e89e7-133">Wildcards are not permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e89e7-134">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e89e7-134">-RequiredVersion</span></span>

<span data-ttu-id="e89e7-135">Especifica a versão exata do provedor de pacote que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="e89e7-135">Specifies the exact version of the package provider that you want to import.</span></span> <span data-ttu-id="e89e7-136">Se você não adicionar esse parâmetro, `Import-PackageProvider` o importará a versão mais recente disponível do provedor que também atende a qualquer versão máxima especificada usando o parâmetro **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="e89e7-136">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider that also satisfies any maximum version specified using the **MaximumVersion** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e89e7-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e89e7-137">CommonParameters</span></span>

<span data-ttu-id="e89e7-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e89e7-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e89e7-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e89e7-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e89e7-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e89e7-140">INPUTS</span></span>

### <span data-ttu-id="e89e7-141">Microsoft. PackageManagement. Implementation. Packageprovider</span><span class="sxs-lookup"><span data-stu-id="e89e7-141">Microsoft.PackageManagement.Implementation.PackageProvider</span></span>

<span data-ttu-id="e89e7-142">É possível canalizar um objeto **packageprovider** retornado por `Get-PackageProvider` into `Import-PackageProvider` .</span><span class="sxs-lookup"><span data-stu-id="e89e7-142">You can pipe a **PackageProvider** object returned by `Get-PackageProvider` into `Import-PackageProvider`.</span></span>

## <span data-ttu-id="e89e7-143">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e89e7-143">OUTPUTS</span></span>

## <span data-ttu-id="e89e7-144">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e89e7-144">NOTES</span></span>

## <span data-ttu-id="e89e7-145">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e89e7-145">RELATED LINKS</span></span>

[<span data-ttu-id="e89e7-146">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="e89e7-146">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="e89e7-147">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e89e7-147">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="e89e7-148">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e89e7-148">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="e89e7-149">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e89e7-149">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="e89e7-150">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="e89e7-150">Get-PackageProvider</span></span>](Get-PackageProvider.md)
