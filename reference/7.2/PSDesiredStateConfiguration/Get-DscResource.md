---
external help file: PSDesiredStateConfiguration-help.xml
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscresource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscResource
ms.openlocfilehash: dbc036562da0172dc4406f169891d2cd1c5e4098
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597399"
---
# <span data-ttu-id="65afd-102">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="65afd-102">Get-DscResource</span></span>

## <span data-ttu-id="65afd-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="65afd-103">SYNOPSIS</span></span>
<span data-ttu-id="65afd-104">Obtém recursos de DSC (configuração de estado desejado) presentes no computador.</span><span class="sxs-lookup"><span data-stu-id="65afd-104">Gets Desired State Configuration (DSC) resources present on the computer.</span></span>

## <span data-ttu-id="65afd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="65afd-105">SYNTAX</span></span>

```
Get-DscResource [[-Name] <String[]>] [[-Module] <Object>] [-Syntax] [<CommonParameters>]
```

## <span data-ttu-id="65afd-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="65afd-106">DESCRIPTION</span></span>

<span data-ttu-id="65afd-107">O `Get-DscResource` cmdlet recupera os recursos de DSC do PowerShell presentes no computador.</span><span class="sxs-lookup"><span data-stu-id="65afd-107">The `Get-DscResource` cmdlet retrieves the PowerShell DSC resources present on the computer.</span></span> <span data-ttu-id="65afd-108">Esse cmdlet descobre apenas os recursos instalados no PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="65afd-108">This cmdlet discovers only the resources installed in the PSModulePath.</span></span> <span data-ttu-id="65afd-109">Ele mostra os detalhes sobre os provedores internos e personalizados, que são criados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="65afd-109">It shows the details about built-in and custom providers, which are created by the user.</span></span> <span data-ttu-id="65afd-110">Esse cmdlet também mostra detalhes sobre os recursos de composição, que são outras configurações que são empacotadas como módulo ou criadas em tempo de execução na sessão.</span><span class="sxs-lookup"><span data-stu-id="65afd-110">This cmdlet also shows details about composite resources, which are other configurations that are packaged as module or created at run time in the session.</span></span>

## <span data-ttu-id="65afd-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="65afd-111">EXAMPLES</span></span>

### <span data-ttu-id="65afd-112">Exemplo 1: obter todos os recursos no computador local</span><span class="sxs-lookup"><span data-stu-id="65afd-112">Example 1: Get all resources on the local computer</span></span>

```powershell
Get-DscResource
```

<span data-ttu-id="65afd-113">Esse comando obtém todos os recursos no computador local.</span><span class="sxs-lookup"><span data-stu-id="65afd-113">This command gets all the resources on the local computer.</span></span>

### <span data-ttu-id="65afd-114">Exemplo 2: obter um recurso especificando o nome</span><span class="sxs-lookup"><span data-stu-id="65afd-114">Example 2: Get a resource by specifying the name</span></span>

```powershell
Get-DscResource -Name "WindowsFeature"
```

<span data-ttu-id="65afd-115">Esse comando obtém o recurso WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="65afd-115">This command gets the WindowsFeature resource.</span></span>

### <span data-ttu-id="65afd-116">Exemplo 3: obter todos os recursos de um módulo</span><span class="sxs-lookup"><span data-stu-id="65afd-116">Example 3: Get all the resources from a module</span></span>

```powershell
Get-DscResource -Module "xHyper-V"
```

<span data-ttu-id="65afd-117">Esse comando obtém todos os recursos do módulo xHyper-V.</span><span class="sxs-lookup"><span data-stu-id="65afd-117">This command gets all the resources from the xHyper-V module.</span></span>

### <span data-ttu-id="65afd-118">Exemplo 4: obter um recurso usando caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="65afd-118">Example 4: Get a resource by using wildcard characters</span></span>

```powershell
Get-DscResource -Name P*,r*
```

<span data-ttu-id="65afd-119">Esse comando obtém todos os recursos que correspondem ao padrão curinga especificado pelo parâmetro **Name** .</span><span class="sxs-lookup"><span data-stu-id="65afd-119">This command gets all resources that match the wildcard pattern specified by the **Name** parameter.</span></span>

### <span data-ttu-id="65afd-120">Exemplo 5: obter uma sintaxe de recurso</span><span class="sxs-lookup"><span data-stu-id="65afd-120">Example 5: Get a resource syntax</span></span>

```powershell
Get-DscResource -Name "WindowsFeature" -Syntax
```

<span data-ttu-id="65afd-121">Esse comando obtém o recurso WindowsFeature e mostra a sintaxe do recurso.</span><span class="sxs-lookup"><span data-stu-id="65afd-121">This command gets the WindowsFeature resource, and shows the syntax for the resource.</span></span>

### <span data-ttu-id="65afd-122">Exemplo 6: obter todas as propriedades de um recurso</span><span class="sxs-lookup"><span data-stu-id="65afd-122">Example 6: Get all the properties for a resource</span></span>

```powershell
Get-DscResource -Name "User" | Select-Object -ExpandProperty Properties
```

<span data-ttu-id="65afd-123">Esse comando obtém o recurso User e, em seguida, usa o operador de pipeline para retornar todas as propriedades do recurso User.</span><span class="sxs-lookup"><span data-stu-id="65afd-123">This command gets the User resource, and then uses the pipeline operator to return all the properties for the User resource.</span></span>

### <span data-ttu-id="65afd-124">Exemplo 7: obter todos os recursos de um módulo especificado com uma versão especificada</span><span class="sxs-lookup"><span data-stu-id="65afd-124">Example 7: Get all the resources from a specified module with a specified version</span></span>

```powershell
Get-DscResource -Module @{ModuleName='xHyper-V';RequiredVersion='3.0.0.0'}
```

<span data-ttu-id="65afd-125">Esse comando obtém todos os recursos do módulo xHyper-V com a versão 3.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="65afd-125">This command gets all the resources from xHyper-V module with version 3.0.0.0.</span></span>

## <span data-ttu-id="65afd-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="65afd-126">PARAMETERS</span></span>

### <span data-ttu-id="65afd-127">-Módulo</span><span class="sxs-lookup"><span data-stu-id="65afd-127">-Module</span></span>

<span data-ttu-id="65afd-128">Especifica o nome ou nome totalmente qualificado do módulo para o qual exibir o recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="65afd-128">Specifies the name or fully qualified name of the module for which to view the DSC resource.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="65afd-129">-Name</span><span class="sxs-lookup"><span data-stu-id="65afd-129">-Name</span></span>

<span data-ttu-id="65afd-130">Especifica uma matriz de nomes do recurso DSC a ser exibido.</span><span class="sxs-lookup"><span data-stu-id="65afd-130">Specifies an array of names of the DSC resource to view.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="65afd-131">-Sintaxe</span><span class="sxs-lookup"><span data-stu-id="65afd-131">-Syntax</span></span>

<span data-ttu-id="65afd-132">Indica que o cmdlet retorna a exibição de sintaxe dos recursos de DSC especificados.</span><span class="sxs-lookup"><span data-stu-id="65afd-132">Indicates that the cmdlet returns the syntax view of the specified DSC resources.</span></span> <span data-ttu-id="65afd-133">A sintaxe retornada mostra como usar os recursos em um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65afd-133">The returned syntax shows how to use the resources in a PowerShell script.</span></span>

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

### <span data-ttu-id="65afd-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="65afd-134">CommonParameters</span></span>

<span data-ttu-id="65afd-135">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="65afd-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="65afd-136">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="65afd-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="65afd-137">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="65afd-137">INPUTS</span></span>

### <span data-ttu-id="65afd-138">System.String[]</span><span class="sxs-lookup"><span data-stu-id="65afd-138">System.String[]</span></span>

### <span data-ttu-id="65afd-139">System.Object</span><span class="sxs-lookup"><span data-stu-id="65afd-139">System.Object</span></span>

## <span data-ttu-id="65afd-140">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="65afd-140">OUTPUTS</span></span>

### <span data-ttu-id="65afd-141">Microsoft. PowerShell. DesiredStateConfiguration. DscResourceInfo []</span><span class="sxs-lookup"><span data-stu-id="65afd-141">Microsoft.PowerShell.DesiredStateConfiguration.DscResourceInfo[]</span></span>

### <span data-ttu-id="65afd-142">string[]</span><span class="sxs-lookup"><span data-stu-id="65afd-142">string[]</span></span>

## <span data-ttu-id="65afd-143">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="65afd-143">NOTES</span></span>

## <span data-ttu-id="65afd-144">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="65afd-144">RELATED LINKS</span></span>

[<span data-ttu-id="65afd-145">Visão geral da configuração de estado desejado do PowerShell</span><span class="sxs-lookup"><span data-stu-id="65afd-145">PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="65afd-146">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="65afd-146">Invoke-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)

