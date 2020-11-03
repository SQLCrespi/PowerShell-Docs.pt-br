---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 0f1173cbfab139438d55ff49272f9625579820dc
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193153"
---
# <span data-ttu-id="b4f50-103">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b4f50-103">Unregister-PSRepository</span></span>

## <span data-ttu-id="b4f50-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b4f50-104">SYNOPSIS</span></span>
<span data-ttu-id="b4f50-105">Cancela o registro de um repositório.</span><span class="sxs-lookup"><span data-stu-id="b4f50-105">Unregisters a repository.</span></span>

## <span data-ttu-id="b4f50-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b4f50-106">SYNTAX</span></span>

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="b4f50-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b4f50-107">DESCRIPTION</span></span>

<span data-ttu-id="b4f50-108">O `Unregister-PSRepository` cmdlet cancela o registro de um repositório para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="b4f50-108">The `Unregister-PSRepository` cmdlet unregisters a repository for the current user.</span></span>

## <span data-ttu-id="b4f50-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b4f50-109">EXAMPLES</span></span>

### <span data-ttu-id="b4f50-110">Exemplo 1: cancelar o registro de um repositório</span><span class="sxs-lookup"><span data-stu-id="b4f50-110">Example 1: Unregister a repository</span></span>

<span data-ttu-id="b4f50-111">Este exemplo cancela o registro do repositório chamado myNuGetSource.</span><span class="sxs-lookup"><span data-stu-id="b4f50-111">This example unregisters the repository named myNuGetSource.</span></span>

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### <span data-ttu-id="b4f50-112">Exemplo 2: cancelar o registro de todos os repositórios</span><span class="sxs-lookup"><span data-stu-id="b4f50-112">Example 2: Unregister all repositories</span></span>

<span data-ttu-id="b4f50-113">Este exemplo usa `Get-PSRepository` para obter todos os repositórios registrados e usa o operador de pipeline para passá-los para `Unregister-PSRepository` o cancelamento do registro.</span><span class="sxs-lookup"><span data-stu-id="b4f50-113">This example uses `Get-PSRepository` to get all registered repositories, and uses the pipeline operator to pass them to `Unregister-PSRepository` to unregister them.</span></span>

```powershell
Get-PSRepository | Unregister-PSRepository
```

## <span data-ttu-id="b4f50-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b4f50-114">PARAMETERS</span></span>

### <span data-ttu-id="b4f50-115">-Name</span><span class="sxs-lookup"><span data-stu-id="b4f50-115">-Name</span></span>

<span data-ttu-id="b4f50-116">Especifica uma matriz de nomes dos repositórios a serem removidos.</span><span class="sxs-lookup"><span data-stu-id="b4f50-116">Specifies an array of names of the repositories to remove.</span></span>

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

### <span data-ttu-id="b4f50-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b4f50-117">CommonParameters</span></span>

<span data-ttu-id="b4f50-118">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b4f50-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b4f50-119">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b4f50-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b4f50-120">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b4f50-120">INPUTS</span></span>

### <span data-ttu-id="b4f50-121">System.String[]</span><span class="sxs-lookup"><span data-stu-id="b4f50-121">System.String[]</span></span>

## <span data-ttu-id="b4f50-122">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b4f50-122">OUTPUTS</span></span>

### <span data-ttu-id="b4f50-123">System.Object</span><span class="sxs-lookup"><span data-stu-id="b4f50-123">System.Object</span></span>

## <span data-ttu-id="b4f50-124">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b4f50-124">NOTES</span></span>

## <span data-ttu-id="b4f50-125">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b4f50-125">RELATED LINKS</span></span>

[<span data-ttu-id="b4f50-126">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b4f50-126">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="b4f50-127">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b4f50-127">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="b4f50-128">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b4f50-128">Set-PSRepository</span></span>](Set-PSRepository.md)
