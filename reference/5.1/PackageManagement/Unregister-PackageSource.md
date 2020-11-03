---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/unregister-packagesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PackageSource
ms.openlocfilehash: 0825fa0182783e307e143b2ae10c5c744c2d524b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193632"
---
# <span data-ttu-id="f4c79-103">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f4c79-103">Unregister-PackageSource</span></span>

## <span data-ttu-id="f4c79-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f4c79-104">SYNOPSIS</span></span>
<span data-ttu-id="f4c79-105">Remove uma origem de pacote registrada.</span><span class="sxs-lookup"><span data-stu-id="f4c79-105">Removes a registered package source.</span></span>

## <span data-ttu-id="f4c79-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f4c79-106">SYNTAX</span></span>

### <span data-ttu-id="f4c79-107">SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="f4c79-107">SourceBySearch</span></span>

```
Unregister-PackageSource [[-Source] <String>] [-Location <String>] [-Credential <PSCredential>]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="f4c79-108">SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="f4c79-108">SourceByInputObject</span></span>

```
Unregister-PackageSource -InputObject <PackageSource[]> [-Credential <PSCredential>] [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f4c79-109">NuGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="f4c79-109">NuGet:SourceByInputObject</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="f4c79-110">NuGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="f4c79-110">NuGet:SourceBySearch</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="f4c79-111">PowerShellGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="f4c79-111">PowerShellGet:SourceByInputObject</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="f4c79-112">PowerShellGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="f4c79-112">PowerShellGet:SourceBySearch</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="f4c79-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f4c79-113">DESCRIPTION</span></span>

<span data-ttu-id="f4c79-114">O `Unregister-PackageSource` cmdlet Remove uma origem de pacote registrada.</span><span class="sxs-lookup"><span data-stu-id="f4c79-114">The `Unregister-PackageSource` cmdlet removes a registered package source.</span></span> <span data-ttu-id="f4c79-115">As origens do pacote são sempre gerenciadas por um provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="f4c79-115">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="f4c79-116">Para localizar fontes de pacote, use o `Get-PackageSource` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f4c79-116">To find package sources, use the `Get-PackageSource` cmdlet.</span></span>

## <span data-ttu-id="f4c79-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f4c79-117">EXAMPLES</span></span>

### <span data-ttu-id="f4c79-118">Exemplo 1: cancelar o registro de uma origem de pacote para o provedor de NuGet</span><span class="sxs-lookup"><span data-stu-id="f4c79-118">Example 1: Unregister a package source for the Nuget provider</span></span>

<span data-ttu-id="f4c79-119">O `Unregister-PackageSource` cmdlet cancela o registro de uma origem do pacote do computador local.</span><span class="sxs-lookup"><span data-stu-id="f4c79-119">The `Unregister-PackageSource` cmdlet unregisters a package source from the local computer.</span></span> <span data-ttu-id="f4c79-120">Os parâmetros **local** e de **provedor** podem ser usados para especificar ainda mais a origem a ser removida.</span><span class="sxs-lookup"><span data-stu-id="f4c79-120">The **Location** and **Provider** parameters can be used to further specify the source to remove.</span></span>

```
PS> Unregister-PackageSource -Source MyNuGet
```

<span data-ttu-id="f4c79-121">O `Unregister-PackageSource` cmdlet usa o parâmetro **Source** para especificar qual fonte remover.</span><span class="sxs-lookup"><span data-stu-id="f4c79-121">The `Unregister-PackageSource` cmdlet uses the **Source** parameter to specify which source to remove.</span></span>

### <span data-ttu-id="f4c79-122">Exemplo 2: usar um objeto de pacote para cancelar o registro de um pacote</span><span class="sxs-lookup"><span data-stu-id="f4c79-122">Example 2: Use a PackageSource object to unregister a package</span></span>

<span data-ttu-id="f4c79-123">Este exemplo usa `Get-PackageSource` e `Unregister-PackageSource` para cancelar o registro de uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="f4c79-123">This example uses the `Get-PackageSource` and `Unregister-PackageSource` to unregister a package source.</span></span> <span data-ttu-id="f4c79-124">O objeto **Packager** é armazenado em uma variável.</span><span class="sxs-lookup"><span data-stu-id="f4c79-124">The **PackageSource** object is stored in a variable.</span></span>

```
PS> $pkgsource = Get-PackageSource -Name MyNuGet
PS> Unregister-PackageSource -InputObject $pkgsource
```

<span data-ttu-id="f4c79-125">A `$pkgsource` variável armazena o **Packager** criado pelo `Get-PackageSource` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f4c79-125">The `$pkgsource` variable stores the **PackageSource** created by the `Get-PackageSource` cmdlet.</span></span>
<span data-ttu-id="f4c79-126">`Unregister-PackageSource` usa a `$pkgsource` entrada as para o parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="f4c79-126">`Unregister-PackageSource` uses the `$pkgsource` as input to the **InputObject** parameter.</span></span>

<span data-ttu-id="f4c79-127">Como alternativa, o `Unregister-PackageSource` cmdlet pode especificar um valor para o parâmetro **InputObject** :</span><span class="sxs-lookup"><span data-stu-id="f4c79-127">As an alternative, the `Unregister-PackageSource` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Unregister-PackageSource -InputObject ( Get-PackageSource -Name MyNuGet )`

## <span data-ttu-id="f4c79-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f4c79-128">PARAMETERS</span></span>

### <span data-ttu-id="f4c79-129">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="f4c79-129">-ConfigFile</span></span>

<span data-ttu-id="f4c79-130">Especifica um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="f4c79-130">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4c79-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="f4c79-131">-Credential</span></span>

<span data-ttu-id="f4c79-132">Especifica uma conta de usuário que tem permissão para acessar o computador e executar comandos.</span><span class="sxs-lookup"><span data-stu-id="f4c79-132">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="f4c79-133">Digite um nome de usuário, como **User01** , **Domínio01 \ Usuário01** ou insira um objeto **PSCredential** , gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f4c79-133">Type a user name, such as **User01** , **Domain01\User01** , or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="f4c79-134">Se você digitar um nome de usuário, você será solicitado a fornecer uma senha.</span><span class="sxs-lookup"><span data-stu-id="f4c79-134">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="f4c79-135">Quando o parâmetro **Credential** não é especificado, a conta de usuário atual é usada.</span><span class="sxs-lookup"><span data-stu-id="f4c79-135">When the **Credential** parameter isn't specified, the current user account is used.</span></span>

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

### <span data-ttu-id="f4c79-136">-Force</span><span class="sxs-lookup"><span data-stu-id="f4c79-136">-Force</span></span>

<span data-ttu-id="f4c79-137">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="f4c79-137">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="f4c79-138">Substitui as restrições que impedem `Unregister-PackageSource` o sucesso, com exceção da segurança.</span><span class="sxs-lookup"><span data-stu-id="f4c79-138">Overrides restrictions that prevent `Unregister-PackageSource` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="f4c79-139">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="f4c79-139">-ForceBootstrap</span></span>

<span data-ttu-id="f4c79-140">Indica que `Unregister-PackageSource` o **PackageManagement** força a desinstalação automática do provedor de pacote para a origem do pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="f4c79-140">Indicates that `Unregister-PackageSource` forces **PackageManagement** to automatically uninstall the package provider for the specified package source.</span></span>

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

### <span data-ttu-id="f4c79-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f4c79-141">-InputObject</span></span>

<span data-ttu-id="f4c79-142">Aceita a entrada de pipeline que especifica o objeto de **empacotador** do `Get-PackageSource` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f4c79-142">Accepts pipeline input that specifies the **PackageSource** object from the `Get-PackageSource` cmdlet.</span></span> <span data-ttu-id="f4c79-143">**InputObject** aceita o objeto **Packager** como um `Get-PackageSource` valor ou uma variável que contém o objeto.</span><span class="sxs-lookup"><span data-stu-id="f4c79-143">**InputObject** accepts the **PackageSource** object as a `Get-PackageSource` value or a variable that contains the object.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.PackageSource[]
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f4c79-144">-Local</span><span class="sxs-lookup"><span data-stu-id="f4c79-144">-Location</span></span>

<span data-ttu-id="f4c79-145">Especifica o local para o qual uma origem de pacote aponta.</span><span class="sxs-lookup"><span data-stu-id="f4c79-145">Specifies the location to which a package source points.</span></span> <span data-ttu-id="f4c79-146">O valor desse parâmetro pode ser um URI, um caminho de arquivo ou qualquer outro formato de destino que tenha suporte do provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="f4c79-146">The value of this parameter can be a URI, a file path, or any other destination format that is supported by the package provider.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4c79-147">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="f4c79-147">-PackageManagementProvider</span></span>

<span data-ttu-id="f4c79-148">Especifica o provedor de **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="f4c79-148">Specifies the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4c79-149">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="f4c79-149">-ProviderName</span></span>

<span data-ttu-id="f4c79-150">Especifica o nome do provedor.</span><span class="sxs-lookup"><span data-stu-id="f4c79-150">Specifies the provider name.</span></span>

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

### <span data-ttu-id="f4c79-151">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="f4c79-151">-PublishLocation</span></span>

<span data-ttu-id="f4c79-152">Especifica o local de publicação.</span><span class="sxs-lookup"><span data-stu-id="f4c79-152">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4c79-153">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="f4c79-153">-ScriptPublishLocation</span></span>

<span data-ttu-id="f4c79-154">Especifica o local de publicação do script.</span><span class="sxs-lookup"><span data-stu-id="f4c79-154">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4c79-155">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="f4c79-155">-ScriptSourceLocation</span></span>

<span data-ttu-id="f4c79-156">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="f4c79-156">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4c79-157">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="f4c79-157">-SkipValidate</span></span>

<span data-ttu-id="f4c79-158">Opção que ignora a validação das credenciais de uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="f4c79-158">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4c79-159">-Source</span><span class="sxs-lookup"><span data-stu-id="f4c79-159">-Source</span></span>

<span data-ttu-id="f4c79-160">Especifica o nome amigável da origem do pacote.</span><span class="sxs-lookup"><span data-stu-id="f4c79-160">Specifies the friendly name of the package source.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4c79-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f4c79-161">-Confirm</span></span>

<span data-ttu-id="f4c79-162">Solicita que você confirme antes que o `Unregister-PackageSource` seja executado.</span><span class="sxs-lookup"><span data-stu-id="f4c79-162">Prompts you for confirmation before `Unregister-PackageSource` is run.</span></span>

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

### <span data-ttu-id="f4c79-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f4c79-163">-WhatIf</span></span>

<span data-ttu-id="f4c79-164">Mostra o que aconteceria se o `Unregister-PackageSource` cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="f4c79-164">Shows what would happen if `Unregister-PackageSource` cmdlet is run.</span></span> <span data-ttu-id="f4c79-165">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="f4c79-165">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="f4c79-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f4c79-166">CommonParameters</span></span>

<span data-ttu-id="f4c79-167">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f4c79-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f4c79-168">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f4c79-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f4c79-169">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f4c79-169">INPUTS</span></span>

### <span data-ttu-id="f4c79-170">`Unregister-PackageSource` aceita objetos de **compactador** do pipeline como entrada.</span><span class="sxs-lookup"><span data-stu-id="f4c79-170">`Unregister-PackageSource` accepts **PackageSource** objects from the pipeline as input.</span></span>

## <span data-ttu-id="f4c79-171">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f4c79-171">OUTPUTS</span></span>

### <span data-ttu-id="f4c79-172">`Unregister-PackageSource` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="f4c79-172">`Unregister-PackageSource` doesn't generate any output.</span></span>

## <span data-ttu-id="f4c79-173">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f4c79-173">NOTES</span></span>

<span data-ttu-id="f4c79-174">A inclusão de um provedor de pacote em um comando pode tornar os parâmetros dinâmicos disponíveis para um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f4c79-174">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="f4c79-175">Parâmetros dinâmicos são específicos para um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="f4c79-175">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="f4c79-176">O `Get-Help` cmdlet lista os conjuntos de parâmetros de um cmdlet e inclui o conjunto de parâmetros do provedor.</span><span class="sxs-lookup"><span data-stu-id="f4c79-176">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span>

## <span data-ttu-id="f4c79-177">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f4c79-177">RELATED LINKS</span></span>

[<span data-ttu-id="f4c79-178">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="f4c79-178">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="f4c79-179">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="f4c79-179">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="f4c79-180">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f4c79-180">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="f4c79-181">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f4c79-181">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="f4c79-182">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f4c79-182">Set-PackageSource</span></span>](Set-PackageSource.md)
