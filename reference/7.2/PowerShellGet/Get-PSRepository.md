---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSRepository
ms.openlocfilehash: 66f840d99b107da22b6771e6327ab68d33a1b368
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597212"
---
# <span data-ttu-id="8ee5b-102">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="8ee5b-102">Get-PSRepository</span></span>

## <span data-ttu-id="8ee5b-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8ee5b-103">SYNOPSIS</span></span>
<span data-ttu-id="8ee5b-104">Obtém repositórios do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-104">Gets PowerShell repositories.</span></span>

## <span data-ttu-id="8ee5b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8ee5b-105">SYNTAX</span></span>

```
Get-PSRepository [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="8ee5b-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8ee5b-106">DESCRIPTION</span></span>

<span data-ttu-id="8ee5b-107">O cmdlet **Get-PSRepository** Obtém repositórios de módulo do PowerShell que são registrados para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-107">The **Get-PSRepository** cmdlet gets PowerShell module repositories that are registered for the current user.</span></span>

## <span data-ttu-id="8ee5b-108">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8ee5b-108">EXAMPLES</span></span>

### <span data-ttu-id="8ee5b-109">Exemplo 1: obter todos os repositórios de módulo</span><span class="sxs-lookup"><span data-stu-id="8ee5b-109">Example 1: Get all module repositories</span></span>

```
PS C:\> Get-PSRepository
Name                                     SourceLocation                                     OneGetProvider       InstallationPolicy
----                                     --------------                                     --------------       ------------------
PSGallery                                http://go.micro...                                 NuGet                Untrusted
myNuGetSource                            https://myget.c...                                 NuGet                Trusted
```

<span data-ttu-id="8ee5b-110">Esse comando obtém todos os repositórios de módulo registrados para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-110">This command gets all module repositories registered for the current user.</span></span>

### <span data-ttu-id="8ee5b-111">Exemplo 2: obter repositórios de módulo por nome</span><span class="sxs-lookup"><span data-stu-id="8ee5b-111">Example 2: Get module repositories by name</span></span>

```
PS C:\> Get-PSRepository -Name "*NuGet*"
```

<span data-ttu-id="8ee5b-112">Esse comando obtém todos os repositórios de módulo que incluem o NuGet em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-112">This command gets all module repositories that include NuGet in their names.</span></span>

### <span data-ttu-id="8ee5b-113">Exemplo 3: obter um repositório de módulo e formatar a saída</span><span class="sxs-lookup"><span data-stu-id="8ee5b-113">Example 3: Get a module repository and format the output</span></span>

```
PS C:\> Get-PSRepository -Name "Local01" | Format-List * -Force
Name                      : local01
SourceLocation            : http://manikb-dev:8765/api/v2/
Trusted                   : True
Registered                : True
InstallationPolicy        : Trusted
PackageManagementProvider : NuGet
PublishLocation           : http://pattif-dev:8765/api/v2/package/
ScriptSourceLocation      : http://pattif-dev:8765/api/v2/artifacts/psscript
ScriptPublishLocation     : http://pattif-dev:8765/api/v2/package/
ProviderOptions           : {}
```

<span data-ttu-id="8ee5b-114">Esse comando obtém o repositório chamado Local01 e usa o operador de pipeline para passar esse objeto para o cmdlet Format-List.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-114">This command gets the repository named Local01 and uses the pipeline operator to pass that object to the Format-List cmdlet.</span></span>

## <span data-ttu-id="8ee5b-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8ee5b-115">PARAMETERS</span></span>

### <span data-ttu-id="8ee5b-116">-Name</span><span class="sxs-lookup"><span data-stu-id="8ee5b-116">-Name</span></span>

<span data-ttu-id="8ee5b-117">Especifica os nomes dos repositórios a serem obtidos.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-117">Specifies the names of the repositories to get.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8ee5b-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8ee5b-118">CommonParameters</span></span>

<span data-ttu-id="8ee5b-119">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8ee5b-120">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8ee5b-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8ee5b-121">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8ee5b-121">INPUTS</span></span>

### <span data-ttu-id="8ee5b-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="8ee5b-122">System.String[]</span></span>

## <span data-ttu-id="8ee5b-123">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8ee5b-123">OUTPUTS</span></span>

### <span data-ttu-id="8ee5b-124">System.Object</span><span class="sxs-lookup"><span data-stu-id="8ee5b-124">System.Object</span></span>

## <span data-ttu-id="8ee5b-125">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8ee5b-125">NOTES</span></span>

## <span data-ttu-id="8ee5b-126">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8ee5b-126">RELATED LINKS</span></span>

[<span data-ttu-id="8ee5b-127">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="8ee5b-127">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="8ee5b-128">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="8ee5b-128">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="8ee5b-129">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="8ee5b-129">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)

