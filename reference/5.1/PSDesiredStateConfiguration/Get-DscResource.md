---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscresource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscResource
ms.openlocfilehash: 4a46e3b78ae9db4ea58f97daf37dca399c925549
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2020
ms.locfileid: "93195066"
---
# <span data-ttu-id="f73fd-103">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="f73fd-103">Get-DscResource</span></span>

## <span data-ttu-id="f73fd-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f73fd-104">SYNOPSIS</span></span>
<span data-ttu-id="f73fd-105">Obtém recursos de DSC (configuração de estado desejado) presentes no computador.</span><span class="sxs-lookup"><span data-stu-id="f73fd-105">Gets Desired State Configuration (DSC) resources present on the computer.</span></span>

## <span data-ttu-id="f73fd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f73fd-106">SYNTAX</span></span>

```
Get-DscResource [[-Name] <String[]>] [[-Module] <Object>] [-Syntax] [<CommonParameters>]
```

## <span data-ttu-id="f73fd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f73fd-107">DESCRIPTION</span></span>

<span data-ttu-id="f73fd-108">O `Get-DscResource` cmdlet recupera os recursos de DSC do PowerShell presentes no computador.</span><span class="sxs-lookup"><span data-stu-id="f73fd-108">The `Get-DscResource` cmdlet retrieves the PowerShell DSC resources present on the computer.</span></span> <span data-ttu-id="f73fd-109">Esse cmdlet descobre apenas os recursos instalados no PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="f73fd-109">This cmdlet discovers only the resources installed in the PSModulePath.</span></span> <span data-ttu-id="f73fd-110">Ele mostra os detalhes sobre os provedores internos e personalizados, que são criados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="f73fd-110">It shows the details about built-in and custom providers, which are created by the user.</span></span> <span data-ttu-id="f73fd-111">Esse cmdlet também mostra detalhes sobre os recursos de composição, que são outras configurações que são empacotadas como módulo ou criadas em tempo de execução na sessão.</span><span class="sxs-lookup"><span data-stu-id="f73fd-111">This cmdlet also shows details about composite resources, which are other configurations that are packaged as module or created at run time in the session.</span></span>

## <span data-ttu-id="f73fd-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f73fd-112">EXAMPLES</span></span>

### <span data-ttu-id="f73fd-113">Exemplo 1: obter todos os recursos no computador local</span><span class="sxs-lookup"><span data-stu-id="f73fd-113">Example 1: Get all resources on the local computer</span></span>

```powershell
Get-DscResource
```

<span data-ttu-id="f73fd-114">Esse comando obtém todos os recursos no computador local.</span><span class="sxs-lookup"><span data-stu-id="f73fd-114">This command gets all the resources on the local computer.</span></span>

### <span data-ttu-id="f73fd-115">Exemplo 2: obter um recurso especificando o nome</span><span class="sxs-lookup"><span data-stu-id="f73fd-115">Example 2: Get a resource by specifying the name</span></span>

```powershell
Get-DscResource -Name "WindowsFeature"
```

<span data-ttu-id="f73fd-116">Esse comando obtém o recurso WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="f73fd-116">This command gets the WindowsFeature resource.</span></span>

### <span data-ttu-id="f73fd-117">Exemplo 3: obter todos os recursos de um módulo</span><span class="sxs-lookup"><span data-stu-id="f73fd-117">Example 3: Get all the resources from a module</span></span>

```powershell
Get-DscResource -Module "xHyper-V"
```

<span data-ttu-id="f73fd-118">Esse comando obtém todos os recursos do módulo xHyper-V.</span><span class="sxs-lookup"><span data-stu-id="f73fd-118">This command gets all the resources from the xHyper-V module.</span></span>

### <span data-ttu-id="f73fd-119">Exemplo 4: obter um recurso usando caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="f73fd-119">Example 4: Get a resource by using wildcard characters</span></span>

```powershell
Get-DscResource -Name P*,r*
```

<span data-ttu-id="f73fd-120">Esse comando obtém todos os recursos que correspondem ao padrão curinga especificado pelo parâmetro **Name** .</span><span class="sxs-lookup"><span data-stu-id="f73fd-120">This command gets all resources that match the wildcard pattern specified by the **Name** parameter.</span></span>

### <span data-ttu-id="f73fd-121">Exemplo 5: obter uma sintaxe de recurso</span><span class="sxs-lookup"><span data-stu-id="f73fd-121">Example 5: Get a resource syntax</span></span>

```powershell
Get-DscResource -Name "WindowsFeature" -Syntax
```

<span data-ttu-id="f73fd-122">Esse comando obtém o recurso WindowsFeature e mostra a sintaxe do recurso.</span><span class="sxs-lookup"><span data-stu-id="f73fd-122">This command gets the WindowsFeature resource, and shows the syntax for the resource.</span></span>

### <span data-ttu-id="f73fd-123">Exemplo 6: obter todas as propriedades de um recurso</span><span class="sxs-lookup"><span data-stu-id="f73fd-123">Example 6: Get all the properties for a resource</span></span>

```powershell
Get-DscResource -Name "User" | Select-Object -ExpandProperty Properties
```

<span data-ttu-id="f73fd-124">Esse comando obtém o recurso User e, em seguida, usa o operador de pipeline para retornar todas as propriedades do recurso User.</span><span class="sxs-lookup"><span data-stu-id="f73fd-124">This command gets the User resource, and then uses the pipeline operator to return all the properties for the User resource.</span></span>

### <span data-ttu-id="f73fd-125">Exemplo 7: obter todos os recursos de um módulo especificado com uma versão especificada</span><span class="sxs-lookup"><span data-stu-id="f73fd-125">Example 7: Get all the resources from a specified module with a specified version</span></span>

```powershell
Get-DscResource -Module @{ModuleName='xHyper-V';RequiredVersion='3.0.0.0'}
```

<span data-ttu-id="f73fd-126">Esse comando obtém todos os recursos do módulo xHyper-V com a versão 3.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="f73fd-126">This command gets all the resources from xHyper-V module with version 3.0.0.0.</span></span>

## <span data-ttu-id="f73fd-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f73fd-127">PARAMETERS</span></span>

### <span data-ttu-id="f73fd-128">-Módulo</span><span class="sxs-lookup"><span data-stu-id="f73fd-128">-Module</span></span>

<span data-ttu-id="f73fd-129">Especifica o nome ou nome totalmente qualificado do módulo para o qual exibir o recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="f73fd-129">Specifies the name or fully qualified name of the module for which to view the DSC resource.</span></span>

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

### <span data-ttu-id="f73fd-130">-Name</span><span class="sxs-lookup"><span data-stu-id="f73fd-130">-Name</span></span>

<span data-ttu-id="f73fd-131">Especifica uma matriz de nomes do recurso DSC a ser exibido.</span><span class="sxs-lookup"><span data-stu-id="f73fd-131">Specifies an array of names of the DSC resource to view.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="f73fd-132">-Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f73fd-132">-Syntax</span></span>

<span data-ttu-id="f73fd-133">Indica que o cmdlet retorna a exibição de sintaxe dos recursos de DSC especificados.</span><span class="sxs-lookup"><span data-stu-id="f73fd-133">Indicates that the cmdlet returns the syntax view of the specified DSC resources.</span></span> <span data-ttu-id="f73fd-134">A sintaxe retornada mostra como usar os recursos em um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f73fd-134">The returned syntax shows how to use the resources in a PowerShell script.</span></span>

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

### <span data-ttu-id="f73fd-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f73fd-135">CommonParameters</span></span>

<span data-ttu-id="f73fd-136">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f73fd-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f73fd-137">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f73fd-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f73fd-138">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f73fd-138">INPUTS</span></span>

### <span data-ttu-id="f73fd-139">System.String[]</span><span class="sxs-lookup"><span data-stu-id="f73fd-139">System.String[]</span></span>

### <span data-ttu-id="f73fd-140">System.Object</span><span class="sxs-lookup"><span data-stu-id="f73fd-140">System.Object</span></span>

## <span data-ttu-id="f73fd-141">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f73fd-141">OUTPUTS</span></span>

### <span data-ttu-id="f73fd-142">Microsoft. PowerShell. DesiredStateConfiguration. DscResourceInfo []</span><span class="sxs-lookup"><span data-stu-id="f73fd-142">Microsoft.PowerShell.DesiredStateConfiguration.DscResourceInfo[]</span></span>

### <span data-ttu-id="f73fd-143">string[]</span><span class="sxs-lookup"><span data-stu-id="f73fd-143">string[]</span></span>

## <span data-ttu-id="f73fd-144">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f73fd-144">NOTES</span></span>

- <span data-ttu-id="f73fd-145">`Get-DscResource` Não encontra recursos de DSC baseados em classe nas versões do PowerShell abaixo de 7,0.</span><span class="sxs-lookup"><span data-stu-id="f73fd-145">`Get-DscResource` does not find Class based DSC resources in PowerShell versions below 7.0.</span></span>

## <span data-ttu-id="f73fd-146">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f73fd-146">RELATED LINKS</span></span>

[<span data-ttu-id="f73fd-147">Visão geral da configuração de estado desejado do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f73fd-147">PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="f73fd-148">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="f73fd-148">Invoke-DscResource</span></span>](Invoke-DscResource.md)
