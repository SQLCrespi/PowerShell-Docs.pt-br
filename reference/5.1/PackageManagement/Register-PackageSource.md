---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/register-packagesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PackageSource
ms.openlocfilehash: 323d59724507cfec5cde086e3b8e2a2c2f34b96e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891305"
---
# <span data-ttu-id="1819b-103">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="1819b-103">Register-PackageSource</span></span>

## <span data-ttu-id="1819b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1819b-104">SYNOPSIS</span></span>
<span data-ttu-id="1819b-105">Adiciona uma origem de pacote para um provedor de pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="1819b-105">Adds a package source for a specified package provider.</span></span>

## <span data-ttu-id="1819b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1819b-106">SYNTAX</span></span>

### <span data-ttu-id="1819b-107">SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="1819b-107">SourceBySearch</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="1819b-108">NuGet</span><span class="sxs-lookup"><span data-stu-id="1819b-108">NuGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="1819b-109">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="1819b-109">PowerShellGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="1819b-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1819b-110">DESCRIPTION</span></span>

<span data-ttu-id="1819b-111">O `Register-PackageSource` cmdlet adiciona uma origem de pacote para um provedor de pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="1819b-111">The `Register-PackageSource` cmdlet adds a package source for a specified package provider.</span></span> <span data-ttu-id="1819b-112">As origens do pacote são sempre gerenciadas por um provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="1819b-112">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="1819b-113">Se o provedor de pacotes não puder adicionar ou substituir uma origem de pacote, o provedor gerará uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="1819b-113">If the package provider cannot add or replace a package source, the provider generates an error message.</span></span>

## <span data-ttu-id="1819b-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1819b-114">EXAMPLES</span></span>

### <span data-ttu-id="1819b-115">Exemplo 1: registrar uma origem de pacote para o provedor de NuGet</span><span class="sxs-lookup"><span data-stu-id="1819b-115">Example 1: Register a package source for the NuGet provider</span></span>

<span data-ttu-id="1819b-116">Esse comando registra uma origem de pacote, um local baseado na Web para o provedor de **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="1819b-116">This command registers a package source, a web-based location for the **NuGet** provider.</span></span> <span data-ttu-id="1819b-117">Por padrão, as fontes não são confiáveis.</span><span class="sxs-lookup"><span data-stu-id="1819b-117">By default, sources aren't trusted.</span></span> <span data-ttu-id="1819b-118">Você será solicitado a confirmar se a fonte é confiável antes de os pacotes serem instalados.</span><span class="sxs-lookup"><span data-stu-id="1819b-118">You are prompted to confirm the source is trusted before packages are installed.</span></span> <span data-ttu-id="1819b-119">Para substituir o padrão, use o `-Trusted` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="1819b-119">To override the default, use the `-Trusted` parameter.</span></span>

```powershell
Register-PackageSource -Name MyNuGet -Location https://www.nuget.org/api/v2 -ProviderName NuGet
```

```Output
Name          ProviderName     IsTrusted  Location
----          ------------     ---------  --------
MyNuGet       NuGet            False      https://www.nuget.org/api/v2
```

## <span data-ttu-id="1819b-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1819b-120">PARAMETERS</span></span>

### <span data-ttu-id="1819b-121">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="1819b-121">-ConfigFile</span></span>

<span data-ttu-id="1819b-122">Especifica um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="1819b-122">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="1819b-123">-Credential</span></span>

<span data-ttu-id="1819b-124">Especifica uma conta de usuário que tem permissão para acessar o local autenticado.</span><span class="sxs-lookup"><span data-stu-id="1819b-124">Specifies a user account that has permission to access the authenticated location.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-125">-Force</span><span class="sxs-lookup"><span data-stu-id="1819b-125">-Force</span></span>

<span data-ttu-id="1819b-126">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="1819b-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="1819b-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="1819b-127">-ForceBootstrap</span></span>

<span data-ttu-id="1819b-128">Indica que esse cmdlet instala automaticamente o provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="1819b-128">Indicates that this cmdlet automatically installs the package provider.</span></span>

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

### <span data-ttu-id="1819b-129">-Local</span><span class="sxs-lookup"><span data-stu-id="1819b-129">-Location</span></span>

<span data-ttu-id="1819b-130">Especifica o local de origem do pacote.</span><span class="sxs-lookup"><span data-stu-id="1819b-130">Specifies the package source location.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-131">-Name</span><span class="sxs-lookup"><span data-stu-id="1819b-131">-Name</span></span>

<span data-ttu-id="1819b-132">Especifica o nome da origem do pacote a ser registrado.</span><span class="sxs-lookup"><span data-stu-id="1819b-132">Specifies the name of the package source to register.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-133">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="1819b-133">-PackageManagementProvider</span></span>

<span data-ttu-id="1819b-134">Especifica o provedor de Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="1819b-134">Specifies the Package Management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-135">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="1819b-135">-ProviderName</span></span>

<span data-ttu-id="1819b-136">Especifica o nome do provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="1819b-136">Specifies the package provider's name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-137">-Proxy</span><span class="sxs-lookup"><span data-stu-id="1819b-137">-Proxy</span></span>

<span data-ttu-id="1819b-138">Especifica um servidor proxy para a solicitação, em vez de uma conexão direta com o recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="1819b-138">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="1819b-139">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="1819b-139">-ProxyCredential</span></span>

<span data-ttu-id="1819b-140">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="1819b-140">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-141">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="1819b-141">-PublishLocation</span></span>

<span data-ttu-id="1819b-142">Especifica o local de publicação.</span><span class="sxs-lookup"><span data-stu-id="1819b-142">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-143">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="1819b-143">-ScriptPublishLocation</span></span>

<span data-ttu-id="1819b-144">Especifica o local de publicação do script.</span><span class="sxs-lookup"><span data-stu-id="1819b-144">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-145">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="1819b-145">-ScriptSourceLocation</span></span>

<span data-ttu-id="1819b-146">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="1819b-146">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-147">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="1819b-147">-SkipValidate</span></span>

<span data-ttu-id="1819b-148">Opção que ignora a validação das credenciais de uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="1819b-148">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-149">-Confiável</span><span class="sxs-lookup"><span data-stu-id="1819b-149">-Trusted</span></span>

<span data-ttu-id="1819b-150">Indica que a origem do pacote é confiável.</span><span class="sxs-lookup"><span data-stu-id="1819b-150">Indicates that the package source is trusted.</span></span>

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

### <span data-ttu-id="1819b-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1819b-151">-Confirm</span></span>

<span data-ttu-id="1819b-152">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1819b-152">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1819b-153">-WhatIf</span></span>

<span data-ttu-id="1819b-154">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="1819b-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1819b-155">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="1819b-155">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1819b-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1819b-156">CommonParameters</span></span>

<span data-ttu-id="1819b-157">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1819b-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1819b-158">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1819b-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1819b-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1819b-159">INPUTS</span></span>

## <span data-ttu-id="1819b-160">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1819b-160">OUTPUTS</span></span>

## <span data-ttu-id="1819b-161">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1819b-161">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1819b-162">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="1819b-162">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="1819b-163">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1819b-163">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="1819b-164">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="1819b-164">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="1819b-165">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1819b-165">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="1819b-166">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1819b-166">RELATED LINKS</span></span>

[<span data-ttu-id="1819b-167">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="1819b-167">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="1819b-168">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="1819b-168">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="1819b-169">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="1819b-169">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="1819b-170">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="1819b-170">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
