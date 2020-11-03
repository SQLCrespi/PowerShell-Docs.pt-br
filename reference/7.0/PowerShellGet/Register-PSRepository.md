---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/register-psrepository?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSRepository
ms.openlocfilehash: be7ffa38a0409fa7ef0d01649b863a32732e34de
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193087"
---
# <span data-ttu-id="d394d-103">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d394d-103">Register-PSRepository</span></span>

## <span data-ttu-id="d394d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d394d-104">SYNOPSIS</span></span>
<span data-ttu-id="d394d-105">Registra um repositório do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d394d-105">Registers a PowerShell repository.</span></span>

## <span data-ttu-id="d394d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d394d-106">SYNTAX</span></span>

### <span data-ttu-id="d394d-107">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="d394d-107">NameParameterSet (Default)</span></span>

```
Register-PSRepository [-Name] <String> [-SourceLocation] <Uri> [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

### <span data-ttu-id="d394d-108">PSGalleryParameterSet</span><span class="sxs-lookup"><span data-stu-id="d394d-108">PSGalleryParameterSet</span></span>

```
Register-PSRepository [-Default] [-InstallationPolicy <String>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="d394d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d394d-109">DESCRIPTION</span></span>

<span data-ttu-id="d394d-110">O `Register-PSRepository` cmdlet registra o repositório padrão para módulos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d394d-110">The `Register-PSRepository` cmdlet registers the default repository for PowerShell modules.</span></span> <span data-ttu-id="d394d-111">Depois que um repositório é registrado, você pode referenciá-lo `Find-Module` dos `Install-Module` `Publish-Module` cmdlets, e.</span><span class="sxs-lookup"><span data-stu-id="d394d-111">After a repository is registered, you can reference it from the `Find-Module`, `Install-Module`, and `Publish-Module` cmdlets.</span></span> <span data-ttu-id="d394d-112">O repositório registrado torna-se o repositório padrão no `Find-Module` e no `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="d394d-112">The registered repository becomes the default repository in `Find-Module` and `Install-Module`.</span></span>

<span data-ttu-id="d394d-113">Repositórios registrados são específicos ao usuário.</span><span class="sxs-lookup"><span data-stu-id="d394d-113">Registered repositories are user-specific.</span></span> <span data-ttu-id="d394d-114">Eles não são registrados em um contexto de todo o sistema.</span><span class="sxs-lookup"><span data-stu-id="d394d-114">They are not registered in a system-wide context.</span></span>

<span data-ttu-id="d394d-115">Cada repositório registrado é associado a um provedor de pacote OneGet, que é especificado com o parâmetro **PackageManagementProvider** .</span><span class="sxs-lookup"><span data-stu-id="d394d-115">Each registered repository is associated with a OneGet package provider, which is specified with the **PackageManagementProvider** parameter.</span></span> <span data-ttu-id="d394d-116">Cada provedor de OneGet é projetado para interagir com um tipo específico de repositório.</span><span class="sxs-lookup"><span data-stu-id="d394d-116">Each OneGet provider is designed to interact with a specific type of repository.</span></span> <span data-ttu-id="d394d-117">Por exemplo, o provedor de NuGet foi projetado para interagir com repositórios baseados em NuGet.</span><span class="sxs-lookup"><span data-stu-id="d394d-117">For example, the NuGet provider is designed to interact with NuGet-based repositories.</span></span> <span data-ttu-id="d394d-118">Se um provedor OneGet não for especificado durante o registro, o PowerShellGet tentará encontrar um provedor OneGet que possa manipular o local de origem especificado.</span><span class="sxs-lookup"><span data-stu-id="d394d-118">If a OneGet provider is not specified during registration, PowerShellGet attempts to find a OneGet provider that can handle the specified source location.</span></span>

## <span data-ttu-id="d394d-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d394d-119">EXAMPLES</span></span>

### <span data-ttu-id="d394d-120">Exemplo 1: registrar um repositório</span><span class="sxs-lookup"><span data-stu-id="d394d-120">Example 1: Register a repository</span></span>

```powershell
$parameters = @{
  Name = "myNuGetSource"
  SourceLocation = "https://www.myget.org/F/powershellgetdemo/api/v2"
  PublishLocation = "https://www.myget.org/F/powershellgetdemo/api/v2/Packages"
  InstallationPolicy = 'Trusted'
}
Register-PSRepository @parameters
Get-PSRepository
```

```Output
Name                SourceLocation          OneGetProvider       InstallationPolicy
----                --------------          --------------       ------------------
PSGallery           http://go.micro...      NuGet                Untrusted
myNuGetSource       https://myget.c...      NuGet                Trusted
```

<span data-ttu-id="d394d-121">O primeiro comando é registrado `https://www.myget.org/F/powershellgetdemo/` como um repositório para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="d394d-121">The first command registers `https://www.myget.org/F/powershellgetdemo/` as a repository for the current user.</span></span> <span data-ttu-id="d394d-122">Depois que o myNuGetSource é registrado, você pode referenciá-lo explicitamente ao procurar, instalar e publicar módulos.</span><span class="sxs-lookup"><span data-stu-id="d394d-122">After myNuGetSource is registered, you can explicitly reference it when searching for, installing, and publishing modules.</span></span> <span data-ttu-id="d394d-123">Como o parâmetro **PackageManagementProvider** não está especificado, o repositório não está explicitamente associado a um provedor de pacotes OneGet, portanto, o PowerShellGet sonda os provedores de pacotes disponíveis e os associa ao provedor do NuGet.</span><span class="sxs-lookup"><span data-stu-id="d394d-123">Because the **PackageManagementProvider** parameter isn't specified, the repository is not explicitly associated with a OneGet package provider, so PowerShellGet polls available package providers and associates it with the NuGet provider.</span></span>

<span data-ttu-id="d394d-124">O segundo comando obtém repositórios registrados e exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="d394d-124">The second command gets registered repositories and displays the results.</span></span>

## <span data-ttu-id="d394d-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d394d-125">PARAMETERS</span></span>

### <span data-ttu-id="d394d-126">-Credential</span><span class="sxs-lookup"><span data-stu-id="d394d-126">-Credential</span></span>

<span data-ttu-id="d394d-127">Especifica as credenciais de uma conta que tem direitos para registrar um repositório.</span><span class="sxs-lookup"><span data-stu-id="d394d-127">Specifies credentials of an account that has rights to register a repository.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d394d-128">-Default</span><span class="sxs-lookup"><span data-stu-id="d394d-128">-Default</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PSGalleryParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d394d-129">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="d394d-129">-InstallationPolicy</span></span>

<span data-ttu-id="d394d-130">Especifica a política de instalação.</span><span class="sxs-lookup"><span data-stu-id="d394d-130">Specifies the installation policy.</span></span> <span data-ttu-id="d394d-131">Os valores válidos são: confiável, não confiável.</span><span class="sxs-lookup"><span data-stu-id="d394d-131">Valid values are: Trusted, UnTrusted.</span></span> <span data-ttu-id="d394d-132">O valor padrão não é confiável.</span><span class="sxs-lookup"><span data-stu-id="d394d-132">The default value is UnTrusted.</span></span>

<span data-ttu-id="d394d-133">A política de instalação de um repositório especifica o comportamento do PowerShell ao instalar por meio desse repositório.</span><span class="sxs-lookup"><span data-stu-id="d394d-133">A repository's installation policy specifies PowerShell behavior when installing from that repository.</span></span> <span data-ttu-id="d394d-134">Ao instalar módulos de um repositório não confiável, será solicitada a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="d394d-134">When installing modules from an UnTrusted repository, the user is prompted for confirmation.</span></span>

<span data-ttu-id="d394d-135">Você pode definir o **InstallationPolicy** com o `Set-PSRepository` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d394d-135">You can set the **InstallationPolicy** with the `Set-PSRepository` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Trusted, Untrusted

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d394d-136">-Name</span><span class="sxs-lookup"><span data-stu-id="d394d-136">-Name</span></span>

<span data-ttu-id="d394d-137">Especifica o nome do repositório a ser registrado.</span><span class="sxs-lookup"><span data-stu-id="d394d-137">Specifies the name of the repository to register.</span></span> <span data-ttu-id="d394d-138">Você pode usar esse nome para especificar o repositório em cmdlets, como `Find-Module` e `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="d394d-138">You can use this name to specify the repository in cmdlets such as `Find-Module` and `Install-Module`.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d394d-139">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="d394d-139">-PackageManagementProvider</span></span>

<span data-ttu-id="d394d-140">Especifica um provedor de pacote OneGet.</span><span class="sxs-lookup"><span data-stu-id="d394d-140">Specifies a OneGet package provider.</span></span> <span data-ttu-id="d394d-141">Se você não especificar um valor para esse parâmetro, o PowerShellGet sondará os provedores de pacote disponíveis e associará esse repositório ao primeiro provedor de pacote que indica que ele pode lidar com o repositório.</span><span class="sxs-lookup"><span data-stu-id="d394d-141">If you don't specify a value for this parameter, PowerShellGet polls available package providers and associates this repository with the first package provider that indicates it can handle the repository.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d394d-142">-Proxy</span><span class="sxs-lookup"><span data-stu-id="d394d-142">-Proxy</span></span>

<span data-ttu-id="d394d-143">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="d394d-143">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d394d-144">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="d394d-144">-ProxyCredential</span></span>

<span data-ttu-id="d394d-145">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="d394d-145">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d394d-146">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="d394d-146">-PublishLocation</span></span>

<span data-ttu-id="d394d-147">Especifica o URI do local de publicação.</span><span class="sxs-lookup"><span data-stu-id="d394d-147">Specifies the URI of the publish location.</span></span> <span data-ttu-id="d394d-148">Por exemplo, para repositórios baseados em NuGet, o local de publicação é semelhante a `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="d394d-148">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d394d-149">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="d394d-149">-ScriptPublishLocation</span></span>

<span data-ttu-id="d394d-150">Especifica o local de publicação do script.</span><span class="sxs-lookup"><span data-stu-id="d394d-150">Specifies the script publish location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d394d-151">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="d394d-151">-ScriptSourceLocation</span></span>

<span data-ttu-id="d394d-152">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="d394d-152">Specifies the script source location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d394d-153">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="d394d-153">-SourceLocation</span></span>

<span data-ttu-id="d394d-154">Especifica o URI para descobrir e instalar os módulos deste repositório.</span><span class="sxs-lookup"><span data-stu-id="d394d-154">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="d394d-155">Um URI pode ser um feed de servidor do NuGet (situação mais comum), HTTP, HTTPS, FTP ou local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="d394d-155">A URI can be a NuGet server feed (most common situation), HTTP, HTTPS, FTP or file location.</span></span>

<span data-ttu-id="d394d-156">Por exemplo, para repositórios baseados em NuGet, o local de origem é semelhante a `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="d394d-156">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d394d-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d394d-157">CommonParameters</span></span>

<span data-ttu-id="d394d-158">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d394d-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d394d-159">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d394d-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d394d-160">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d394d-160">INPUTS</span></span>

### <span data-ttu-id="d394d-161">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="d394d-161">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="d394d-162">System.Uri</span><span class="sxs-lookup"><span data-stu-id="d394d-162">System.Uri</span></span>

## <span data-ttu-id="d394d-163">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d394d-163">OUTPUTS</span></span>

### <span data-ttu-id="d394d-164">System.Object</span><span class="sxs-lookup"><span data-stu-id="d394d-164">System.Object</span></span>

## <span data-ttu-id="d394d-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d394d-165">NOTES</span></span>

## <span data-ttu-id="d394d-166">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d394d-166">RELATED LINKS</span></span>

[<span data-ttu-id="d394d-167">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d394d-167">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="d394d-168">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d394d-168">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="d394d-169">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d394d-169">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
