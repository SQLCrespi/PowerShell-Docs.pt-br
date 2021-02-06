---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 908a43506bfbff964cfbdd8eea270b1fa42c3e77
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598816"
---
# <span data-ttu-id="f4fb1-102">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f4fb1-102">Unregister-PSRepository</span></span>

## <span data-ttu-id="f4fb1-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f4fb1-103">SYNOPSIS</span></span>
<span data-ttu-id="f4fb1-104">Cancela o registro de um repositório.</span><span class="sxs-lookup"><span data-stu-id="f4fb1-104">Unregisters a repository.</span></span>

## <span data-ttu-id="f4fb1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f4fb1-105">SYNTAX</span></span>

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="f4fb1-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f4fb1-106">DESCRIPTION</span></span>

<span data-ttu-id="f4fb1-107">O `Unregister-PSRepository` cmdlet cancela o registro de um repositório para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="f4fb1-107">The `Unregister-PSRepository` cmdlet unregisters a repository for the current user.</span></span>

## <span data-ttu-id="f4fb1-108">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f4fb1-108">EXAMPLES</span></span>

### <span data-ttu-id="f4fb1-109">Exemplo 1: cancelar o registro de um repositório</span><span class="sxs-lookup"><span data-stu-id="f4fb1-109">Example 1: Unregister a repository</span></span>

<span data-ttu-id="f4fb1-110">Este exemplo cancela o registro do repositório chamado myNuGetSource.</span><span class="sxs-lookup"><span data-stu-id="f4fb1-110">This example unregisters the repository named myNuGetSource.</span></span>

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### <span data-ttu-id="f4fb1-111">Exemplo 2: cancelar o registro de todos os repositórios</span><span class="sxs-lookup"><span data-stu-id="f4fb1-111">Example 2: Unregister all repositories</span></span>

<span data-ttu-id="f4fb1-112">Este exemplo usa `Get-PSRepository` para obter todos os repositórios registrados e usa o operador de pipeline para passá-los para `Unregister-PSRepository` o cancelamento do registro.</span><span class="sxs-lookup"><span data-stu-id="f4fb1-112">This example uses `Get-PSRepository` to get all registered repositories, and uses the pipeline operator to pass them to `Unregister-PSRepository` to unregister them.</span></span>

```powershell
Get-PSRepository | Unregister-PSRepository
```

## <span data-ttu-id="f4fb1-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f4fb1-113">PARAMETERS</span></span>

### <span data-ttu-id="f4fb1-114">-Name</span><span class="sxs-lookup"><span data-stu-id="f4fb1-114">-Name</span></span>

<span data-ttu-id="f4fb1-115">Especifica uma matriz de nomes dos repositórios a serem removidos.</span><span class="sxs-lookup"><span data-stu-id="f4fb1-115">Specifies an array of names of the repositories to remove.</span></span>

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

### <span data-ttu-id="f4fb1-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f4fb1-116">CommonParameters</span></span>

<span data-ttu-id="f4fb1-117">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f4fb1-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f4fb1-118">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f4fb1-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f4fb1-119">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f4fb1-119">INPUTS</span></span>

### <span data-ttu-id="f4fb1-120">System.String[]</span><span class="sxs-lookup"><span data-stu-id="f4fb1-120">System.String[]</span></span>

## <span data-ttu-id="f4fb1-121">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f4fb1-121">OUTPUTS</span></span>

### <span data-ttu-id="f4fb1-122">System.Object</span><span class="sxs-lookup"><span data-stu-id="f4fb1-122">System.Object</span></span>

## <span data-ttu-id="f4fb1-123">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f4fb1-123">NOTES</span></span>

## <span data-ttu-id="f4fb1-124">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f4fb1-124">RELATED LINKS</span></span>

[<span data-ttu-id="f4fb1-125">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f4fb1-125">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="f4fb1-126">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f4fb1-126">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="f4fb1-127">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f4fb1-127">Set-PSRepository</span></span>](Set-PSRepository.md)
