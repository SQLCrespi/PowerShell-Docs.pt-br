---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/set-psrepository?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSRepository
ms.openlocfilehash: 5b9addd42ca655436ad12d624afd39fa6747dadf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193472"
---
# <span data-ttu-id="31329-103">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="31329-103">Set-PSRepository</span></span>

## <span data-ttu-id="31329-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="31329-104">SYNOPSIS</span></span>
<span data-ttu-id="31329-105">Define valores para um repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="31329-105">Sets values for a registered repository.</span></span>

## <span data-ttu-id="31329-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="31329-106">SYNTAX</span></span>

```
Set-PSRepository [-Name] <String> [[-SourceLocation] <Uri>] [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

## <span data-ttu-id="31329-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="31329-107">DESCRIPTION</span></span>

<span data-ttu-id="31329-108">O `Set-PSRepository` cmdlet define valores para um repositório de módulo registrado.</span><span class="sxs-lookup"><span data-stu-id="31329-108">The `Set-PSRepository` cmdlet sets values for a registered module repository.</span></span> <span data-ttu-id="31329-109">As configurações são persistentes para o usuário atual e se aplicam a todas as versões do PowerShell instaladas para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="31329-109">The settings are persistent for the current user and apply to all versions of PowerShell installed for that user.</span></span>

## <span data-ttu-id="31329-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="31329-110">EXAMPLES</span></span>

### <span data-ttu-id="31329-111">Exemplo 1: definir a política de instalação para um repositório</span><span class="sxs-lookup"><span data-stu-id="31329-111">Example 1: Set the installation policy for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -InstallationPolicy Trusted
```

<span data-ttu-id="31329-112">Esse comando define a política de instalação para o repositório **Myinternalname** como **confiável** , para que você não seja solicitado antes de instalar os módulos dessa fonte.</span><span class="sxs-lookup"><span data-stu-id="31329-112">This command sets the installation policy for the **myInternalSource** repository to **Trusted** , so that you are not prompted before installing modules from that source.</span></span>

### <span data-ttu-id="31329-113">Exemplo 2: definir a origem e os locais de publicação para um repositório</span><span class="sxs-lookup"><span data-stu-id="31329-113">Example 2: Set the source and publish locations for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -SourceLocation 'https://someNuGetUrl.com/api/v2' -PublishLocation 'https://someNuGetUrl.com/api/v2/packages'
```

<span data-ttu-id="31329-114">Esse comando define o local de origem e o local de publicação para **Myinternalname** para os URIs especificados.</span><span class="sxs-lookup"><span data-stu-id="31329-114">This command sets the source location and publish location for **myInternalSource** to the specified URIs.</span></span>

## <span data-ttu-id="31329-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="31329-115">PARAMETERS</span></span>

### <span data-ttu-id="31329-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="31329-116">-Credential</span></span>

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

### <span data-ttu-id="31329-117">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="31329-117">-InstallationPolicy</span></span>

<span data-ttu-id="31329-118">Especifica a política de instalação.</span><span class="sxs-lookup"><span data-stu-id="31329-118">Specifies the installation policy.</span></span> <span data-ttu-id="31329-119">Os valores válidos são: **confiável** , **não confiável** .</span><span class="sxs-lookup"><span data-stu-id="31329-119">Valid values are: **Trusted** , **Untrusted** .</span></span>

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

### <span data-ttu-id="31329-120">-Name</span><span class="sxs-lookup"><span data-stu-id="31329-120">-Name</span></span>

<span data-ttu-id="31329-121">Especifica o nome do repositório.</span><span class="sxs-lookup"><span data-stu-id="31329-121">Specifies the name of the repository.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="31329-122">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="31329-122">-PackageManagementProvider</span></span>

<span data-ttu-id="31329-123">Especifica o provedor de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="31329-123">Specifies the package management provider.</span></span>

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

### <span data-ttu-id="31329-124">-Proxy</span><span class="sxs-lookup"><span data-stu-id="31329-124">-Proxy</span></span>

<span data-ttu-id="31329-125">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="31329-125">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="31329-126">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="31329-126">-ProxyCredential</span></span>

<span data-ttu-id="31329-127">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="31329-127">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="31329-128">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="31329-128">-PublishLocation</span></span>

<span data-ttu-id="31329-129">Especifica o URI do local de publicação.</span><span class="sxs-lookup"><span data-stu-id="31329-129">Specifies the URI of the publish location.</span></span> <span data-ttu-id="31329-130">Por exemplo, para repositórios baseados em NuGet, o local de publicação é semelhante a `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="31329-130">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31329-131">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="31329-131">-ScriptPublishLocation</span></span>

<span data-ttu-id="31329-132">Especifica o local de publicação do script.</span><span class="sxs-lookup"><span data-stu-id="31329-132">Specifies the script publish location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31329-133">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="31329-133">-ScriptSourceLocation</span></span>

<span data-ttu-id="31329-134">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="31329-134">Specifies the script source location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31329-135">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="31329-135">-SourceLocation</span></span>

<span data-ttu-id="31329-136">Especifica o URI para descobrir e instalar os módulos deste repositório.</span><span class="sxs-lookup"><span data-stu-id="31329-136">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="31329-137">Por exemplo, para repositórios baseados em NuGet, o local de origem é semelhante a `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="31329-137">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31329-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="31329-138">CommonParameters</span></span>

<span data-ttu-id="31329-139">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="31329-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="31329-140">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="31329-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="31329-141">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="31329-141">INPUTS</span></span>

### <span data-ttu-id="31329-142">System.String</span><span class="sxs-lookup"><span data-stu-id="31329-142">System.String</span></span>

### <span data-ttu-id="31329-143">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="31329-143">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="31329-144">System.Uri</span><span class="sxs-lookup"><span data-stu-id="31329-144">System.Uri</span></span>

## <span data-ttu-id="31329-145">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="31329-145">OUTPUTS</span></span>

### <span data-ttu-id="31329-146">System.Object</span><span class="sxs-lookup"><span data-stu-id="31329-146">System.Object</span></span>

## <span data-ttu-id="31329-147">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="31329-147">NOTES</span></span>

## <span data-ttu-id="31329-148">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="31329-148">RELATED LINKS</span></span>

[<span data-ttu-id="31329-149">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="31329-149">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="31329-150">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="31329-150">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="31329-151">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="31329-151">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)

