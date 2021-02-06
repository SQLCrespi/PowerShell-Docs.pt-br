---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/set-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSRepository
ms.openlocfilehash: d6f3901ba389ff910dcc808d2e4296032617052c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99603747"
---
# <span data-ttu-id="ff93d-102">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="ff93d-102">Set-PSRepository</span></span>

## <span data-ttu-id="ff93d-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ff93d-103">SYNOPSIS</span></span>
<span data-ttu-id="ff93d-104">Define valores para um repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="ff93d-104">Sets values for a registered repository.</span></span>

## <span data-ttu-id="ff93d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ff93d-105">SYNTAX</span></span>

```
Set-PSRepository [-Name] <String> [[-SourceLocation] <Uri>] [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

## <span data-ttu-id="ff93d-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ff93d-106">DESCRIPTION</span></span>

<span data-ttu-id="ff93d-107">O `Set-PSRepository` cmdlet define valores para um repositório de módulo registrado.</span><span class="sxs-lookup"><span data-stu-id="ff93d-107">The `Set-PSRepository` cmdlet sets values for a registered module repository.</span></span> <span data-ttu-id="ff93d-108">As configurações são persistentes para o usuário atual e se aplicam a todas as versões do PowerShell instaladas para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="ff93d-108">The settings are persistent for the current user and apply to all versions of PowerShell installed for that user.</span></span>

## <span data-ttu-id="ff93d-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ff93d-109">EXAMPLES</span></span>

### <span data-ttu-id="ff93d-110">Exemplo 1: definir a política de instalação para um repositório</span><span class="sxs-lookup"><span data-stu-id="ff93d-110">Example 1: Set the installation policy for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -InstallationPolicy Trusted
```

<span data-ttu-id="ff93d-111">Esse comando define a política de instalação para o repositório **Myinternalname** como **confiável**, para que você não seja solicitado antes de instalar os módulos dessa fonte.</span><span class="sxs-lookup"><span data-stu-id="ff93d-111">This command sets the installation policy for the **myInternalSource** repository to **Trusted**, so that you are not prompted before installing modules from that source.</span></span>

### <span data-ttu-id="ff93d-112">Exemplo 2: definir a origem e os locais de publicação para um repositório</span><span class="sxs-lookup"><span data-stu-id="ff93d-112">Example 2: Set the source and publish locations for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -SourceLocation 'https://someNuGetUrl.com/api/v2' -PublishLocation 'https://someNuGetUrl.com/api/v2/packages'
```

<span data-ttu-id="ff93d-113">Esse comando define o local de origem e o local de publicação para **Myinternalname** para os URIs especificados.</span><span class="sxs-lookup"><span data-stu-id="ff93d-113">This command sets the source location and publish location for **myInternalSource** to the specified URIs.</span></span>

## <span data-ttu-id="ff93d-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ff93d-114">PARAMETERS</span></span>

### <span data-ttu-id="ff93d-115">-Credential</span><span class="sxs-lookup"><span data-stu-id="ff93d-115">-Credential</span></span>

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

### <span data-ttu-id="ff93d-116">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="ff93d-116">-InstallationPolicy</span></span>

<span data-ttu-id="ff93d-117">Especifica a política de instalação.</span><span class="sxs-lookup"><span data-stu-id="ff93d-117">Specifies the installation policy.</span></span> <span data-ttu-id="ff93d-118">Os valores válidos são: **confiável**, **não confiável**.</span><span class="sxs-lookup"><span data-stu-id="ff93d-118">Valid values are: **Trusted**, **Untrusted**.</span></span>

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

### <span data-ttu-id="ff93d-119">-Name</span><span class="sxs-lookup"><span data-stu-id="ff93d-119">-Name</span></span>

<span data-ttu-id="ff93d-120">Especifica o nome do repositório.</span><span class="sxs-lookup"><span data-stu-id="ff93d-120">Specifies the name of the repository.</span></span>

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

### <span data-ttu-id="ff93d-121">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="ff93d-121">-PackageManagementProvider</span></span>

<span data-ttu-id="ff93d-122">Especifica o provedor de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="ff93d-122">Specifies the package management provider.</span></span>

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

### <span data-ttu-id="ff93d-123">-Proxy</span><span class="sxs-lookup"><span data-stu-id="ff93d-123">-Proxy</span></span>

<span data-ttu-id="ff93d-124">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="ff93d-124">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="ff93d-125">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="ff93d-125">-ProxyCredential</span></span>

<span data-ttu-id="ff93d-126">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="ff93d-126">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="ff93d-127">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="ff93d-127">-PublishLocation</span></span>

<span data-ttu-id="ff93d-128">Especifica o URI do local de publicação.</span><span class="sxs-lookup"><span data-stu-id="ff93d-128">Specifies the URI of the publish location.</span></span> <span data-ttu-id="ff93d-129">Por exemplo, para repositórios baseados em NuGet, o local de publicação é semelhante a `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="ff93d-129">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

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

### <span data-ttu-id="ff93d-130">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="ff93d-130">-ScriptPublishLocation</span></span>

<span data-ttu-id="ff93d-131">Especifica o local de publicação do script.</span><span class="sxs-lookup"><span data-stu-id="ff93d-131">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="ff93d-132">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="ff93d-132">-ScriptSourceLocation</span></span>

<span data-ttu-id="ff93d-133">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="ff93d-133">Specifies the script source location.</span></span>

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

### <span data-ttu-id="ff93d-134">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="ff93d-134">-SourceLocation</span></span>

<span data-ttu-id="ff93d-135">Especifica o URI para descobrir e instalar os módulos deste repositório.</span><span class="sxs-lookup"><span data-stu-id="ff93d-135">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="ff93d-136">Por exemplo, para repositórios baseados em NuGet, o local de origem é semelhante a `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="ff93d-136">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

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

### <span data-ttu-id="ff93d-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ff93d-137">CommonParameters</span></span>

<span data-ttu-id="ff93d-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ff93d-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ff93d-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ff93d-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ff93d-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ff93d-140">INPUTS</span></span>

### <span data-ttu-id="ff93d-141">System.String</span><span class="sxs-lookup"><span data-stu-id="ff93d-141">System.String</span></span>

### <span data-ttu-id="ff93d-142">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="ff93d-142">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="ff93d-143">System.Uri</span><span class="sxs-lookup"><span data-stu-id="ff93d-143">System.Uri</span></span>

## <span data-ttu-id="ff93d-144">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ff93d-144">OUTPUTS</span></span>

### <span data-ttu-id="ff93d-145">System.Object</span><span class="sxs-lookup"><span data-stu-id="ff93d-145">System.Object</span></span>

## <span data-ttu-id="ff93d-146">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ff93d-146">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff93d-147">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="ff93d-147">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="ff93d-148">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff93d-148">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="ff93d-149">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="ff93d-149">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="ff93d-150">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff93d-150">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="ff93d-151">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ff93d-151">RELATED LINKS</span></span>

[<span data-ttu-id="ff93d-152">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="ff93d-152">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="ff93d-153">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="ff93d-153">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="ff93d-154">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="ff93d-154">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
