---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/import-packageprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PackageProvider
ms.openlocfilehash: 6c19d1cbc7b7e4dc37e24c466f83efae688f3cec
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99597393"
---
# <span data-ttu-id="4c4e1-102">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="4c4e1-102">Import-PackageProvider</span></span>

## <span data-ttu-id="4c4e1-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4c4e1-103">SYNOPSIS</span></span>
<span data-ttu-id="4c4e1-104">Adiciona Gerenciamento de Pacotes provedores de pacote à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-104">Adds Package Management package providers to the current session.</span></span>

## <span data-ttu-id="4c4e1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4c4e1-105">SYNTAX</span></span>

```
Import-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="4c4e1-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4c4e1-106">DESCRIPTION</span></span>

<span data-ttu-id="4c4e1-107">O `Import-PackageProvider` cmdlet adiciona um ou mais provedores de pacote à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-107">The `Import-PackageProvider` cmdlet adds one or more package providers to the current session.</span></span>
<span data-ttu-id="4c4e1-108">O provedor que você importar deve estar instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-108">The provider that you import must be installed on the local computer.</span></span>

<span data-ttu-id="4c4e1-109">Para obter uma lista de provedores disponíveis, execute `Get-PackageProvider -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="4c4e1-109">To get a list of available providers, run `Get-PackageProvider -ListAvailable`.</span></span>
<span data-ttu-id="4c4e1-110">Observe que um nome de provedor de pacote pode ser diferente do nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-110">Note that a package provider name can be different from its module name.</span></span>

<span data-ttu-id="4c4e1-111">Devido a motivos de segurança, o **PackageManagement** exige que os provedores baseados em C# contenham um `provider.manifest` .</span><span class="sxs-lookup"><span data-stu-id="4c4e1-111">Due to security reasons, **PackageManagement** requires C#-based providers to contain a `provider.manifest`.</span></span> <span data-ttu-id="4c4e1-112">Para obter mais informações sobre como criar um provedor com `provider.manifest` injetado, consulte os `.csproj` arquivos de projeto em [https://github.com/oneget/oneget](https://github.com/oneget/oneget) .</span><span class="sxs-lookup"><span data-stu-id="4c4e1-112">For more information on how to build a provider with `provider.manifest` injected, see the `.csproj` project files on [https://github.com/oneget/oneget](https://github.com/oneget/oneget).</span></span>

## <span data-ttu-id="4c4e1-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4c4e1-113">EXAMPLES</span></span>

### <span data-ttu-id="4c4e1-114">Exemplo 1: importar um provedor de pacote do computador local</span><span class="sxs-lookup"><span data-stu-id="4c4e1-114">Example 1: Import a package provider from the local computer</span></span>

```powershell
PS C:\> Import-PackageProvider -Name "Nuget"
```

<span data-ttu-id="4c4e1-115">Esse comando importa o provedor do NuGet depois que ele tiver sido instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-115">This command imports the Nuget provider after it has been installed on the local computer.</span></span>

### <span data-ttu-id="4c4e1-116">Exemplo 2: importar uma versão específica de um provedor de pacote</span><span class="sxs-lookup"><span data-stu-id="4c4e1-116">Example 2: Import a specific version of a package provider</span></span>

```powershell
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider -ListAvailable
Import-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
```

<span data-ttu-id="4c4e1-117">Esse comando localiza, instala e importa uma versão específica do provedor de pacotes NuGet.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-117">This command finds, installs, and imports a specific version of the Nuget package provider.</span></span>

## <span data-ttu-id="4c4e1-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4c4e1-118">PARAMETERS</span></span>

### <span data-ttu-id="4c4e1-119">-Force</span><span class="sxs-lookup"><span data-stu-id="4c4e1-119">-Force</span></span>

<span data-ttu-id="4c4e1-120">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-120">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="4c4e1-121">Importa novamente um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-121">Re-imports a package provider.</span></span>

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

### <span data-ttu-id="4c4e1-122">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="4c4e1-122">-ForceBootstrap</span></span>

<span data-ttu-id="4c4e1-123">Indica que esse cmdlet força Gerenciamento de Pacotes a instalar automaticamente o provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-123">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="4c4e1-124">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="4c4e1-124">-MaximumVersion</span></span>

<span data-ttu-id="4c4e1-125">Especifica a versão máxima permitida do provedor de pacote que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-125">Specifies the maximum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="4c4e1-126">Se você não adicionar esse parâmetro, `Import-PackageProvider` o importará a versão mais recente disponível do provedor.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-126">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider.</span></span>

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

### <span data-ttu-id="4c4e1-127">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="4c4e1-127">-MinimumVersion</span></span>

<span data-ttu-id="4c4e1-128">Especifica a versão mínima permitida do provedor de pacote que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-128">Specifies the minimum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="4c4e1-129">Se você não adicionar esse parâmetro, `Import-PackageProvider` o importará a versão mais alta disponível do pacote que também atende a qualquer versão máxima especificada usando o parâmetro *MaximumVersion* .</span><span class="sxs-lookup"><span data-stu-id="4c4e1-129">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the package that also satisfies any maximum version that is specified using the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="4c4e1-130">-Name</span><span class="sxs-lookup"><span data-stu-id="4c4e1-130">-Name</span></span>

<span data-ttu-id="4c4e1-131">Especifica um ou mais nomes de provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-131">Specifies one or more package provider names.</span></span> <span data-ttu-id="4c4e1-132">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-132">Wildcards are not permitted.</span></span>

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

### <span data-ttu-id="4c4e1-133">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="4c4e1-133">-RequiredVersion</span></span>

<span data-ttu-id="4c4e1-134">Especifica a versão exata do provedor de pacote que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-134">Specifies the exact version of the package provider that you want to import.</span></span> <span data-ttu-id="4c4e1-135">Se você não adicionar esse parâmetro, `Import-PackageProvider` o importará a versão mais recente disponível do provedor que também atende a qualquer versão máxima especificada usando o parâmetro **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="4c4e1-135">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider that also satisfies any maximum version specified using the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="4c4e1-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4c4e1-136">CommonParameters</span></span>

<span data-ttu-id="4c4e1-137">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4c4e1-138">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4c4e1-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4c4e1-139">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4c4e1-139">INPUTS</span></span>

### <span data-ttu-id="4c4e1-140">Microsoft. PackageManagement. Implementation. Packageprovider</span><span class="sxs-lookup"><span data-stu-id="4c4e1-140">Microsoft.PackageManagement.Implementation.PackageProvider</span></span>

<span data-ttu-id="4c4e1-141">É possível canalizar um objeto **packageprovider** retornado por `Get-PackageProvider` into `Import-PackageProvider` .</span><span class="sxs-lookup"><span data-stu-id="4c4e1-141">You can pipe a **PackageProvider** object returned by `Get-PackageProvider` into `Import-PackageProvider`.</span></span>

## <span data-ttu-id="4c4e1-142">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4c4e1-142">OUTPUTS</span></span>

## <span data-ttu-id="4c4e1-143">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4c4e1-143">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c4e1-144">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-144">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="4c4e1-145">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-145">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="4c4e1-146">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="4c4e1-146">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="4c4e1-147">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c4e1-147">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="4c4e1-148">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4c4e1-148">RELATED LINKS</span></span>

[<span data-ttu-id="4c4e1-149">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="4c4e1-149">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="4c4e1-150">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="4c4e1-150">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="4c4e1-151">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="4c4e1-151">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="4c4e1-152">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="4c4e1-152">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="4c4e1-153">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="4c4e1-153">Get-PackageProvider</span></span>](Get-PackageProvider.md)
