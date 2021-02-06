---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-experimentalfeature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExperimentalFeature
ms.openlocfilehash: aad634bb0a917d418aa9c7fa295a53fda280b8a3
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "99595973"
---
# <span data-ttu-id="44584-102">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="44584-102">Get-ExperimentalFeature</span></span>

## <span data-ttu-id="44584-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="44584-103">SYNOPSIS</span></span>
<span data-ttu-id="44584-104">Obtém recursos experimentais.</span><span class="sxs-lookup"><span data-stu-id="44584-104">Gets experimental features.</span></span>

## <span data-ttu-id="44584-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="44584-105">SYNTAX</span></span>

```
Get-ExperimentalFeature [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="44584-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44584-106">DESCRIPTION</span></span>

<span data-ttu-id="44584-107">O `Get-ExperimentalFeature` cmdlet retorna todos os recursos experimentais descobertos pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44584-107">The `Get-ExperimentalFeature` cmdlet returns all experimental features discovered by PowerShell.</span></span>
<span data-ttu-id="44584-108">Os recursos experimentais podem vir de módulos ou do mecanismo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44584-108">Experimental features can come from modules or the PowerShell engine.</span></span> <span data-ttu-id="44584-109">Os recursos experimentais permitem que os usuários testem novos recursos com segurança e forneçam comentários (normalmente por meio do GitHub) antes que o design seja considerado concluído e quaisquer alterações possam se tornar uma alteração significativa.</span><span class="sxs-lookup"><span data-stu-id="44584-109">Experimental features allow users to safely test new features and provide feedback (typically via GitHub) before the design is considered complete and any changes can become a breaking change.</span></span>

## <span data-ttu-id="44584-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="44584-110">EXAMPLES</span></span>

### <span data-ttu-id="44584-111">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="44584-111">Example 1</span></span>

<span data-ttu-id="44584-112">Obtém a lista de recursos experimentais registrados no momento e seu estado atual.</span><span class="sxs-lookup"><span data-stu-id="44584-112">Gets the list of currently registered experimental features and their current state.</span></span>

```powershell
Get-ExperimentalFeature
```

```Output
Name                         Enabled Source      Description
----                         ------- ------      -----------
PSImplicitRemotingBatching   False PSEngine      Batch implicit remoting proxy commands to improve performance
```

## <span data-ttu-id="44584-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="44584-113">PARAMETERS</span></span>

### <span data-ttu-id="44584-114">-Name</span><span class="sxs-lookup"><span data-stu-id="44584-114">-Name</span></span>

<span data-ttu-id="44584-115">Nome ou nomes de recursos experimentais específicos a serem retornados.</span><span class="sxs-lookup"><span data-stu-id="44584-115">Name or names of specific experimental features to return.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="44584-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="44584-116">CommonParameters</span></span>

<span data-ttu-id="44584-117">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="44584-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="44584-118">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="44584-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="44584-119">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="44584-119">INPUTS</span></span>

### <span data-ttu-id="44584-120">System.String[]</span><span class="sxs-lookup"><span data-stu-id="44584-120">System.String[]</span></span>

<span data-ttu-id="44584-121">Nome ou nomes dos recursos experimentais a serem retornados.</span><span class="sxs-lookup"><span data-stu-id="44584-121">Name or names of experimental features to return.</span></span>

## <span data-ttu-id="44584-122">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="44584-122">OUTPUTS</span></span>

### <span data-ttu-id="44584-123">System. Management. Automation. ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="44584-123">System.Management.Automation.ExperimentalFeature</span></span>

<span data-ttu-id="44584-124">Retorna instâncias que correspondem aos nomes solicitados ou a todos os recursos experimentais se nenhum nome for especificado.</span><span class="sxs-lookup"><span data-stu-id="44584-124">Returns instances that match the requested names or all experimental features if no name is specified.</span></span>

## <span data-ttu-id="44584-125">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="44584-125">RELATED LINKS</span></span>

[<span data-ttu-id="44584-126">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="44584-126">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="44584-127">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="44584-127">Enable-ExperimentalFeature</span></span>](Enable-ExperimentalFeature.md)
