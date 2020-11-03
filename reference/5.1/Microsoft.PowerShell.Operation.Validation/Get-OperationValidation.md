---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/get-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-OperationValidation
ms.openlocfilehash: 22ff12848fb7aefaa7f684ee5d8723cc723a5879
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193888"
---
# <span data-ttu-id="ba193-103">Get-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="ba193-103">Get-OperationValidation</span></span>

## <span data-ttu-id="ba193-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ba193-104">SYNOPSIS</span></span>
<span data-ttu-id="ba193-105">Obtém testes da estrutura de validação da operação.</span><span class="sxs-lookup"><span data-stu-id="ba193-105">Gets Operation Validation Framework tests.</span></span>

## <span data-ttu-id="ba193-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ba193-106">SYNTAX</span></span>

```
Get-OperationValidation [[-ModuleName] <String[]>] [-TestType <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="ba193-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ba193-107">DESCRIPTION</span></span>
<span data-ttu-id="ba193-108">O cmdlet **Get-OperationValidation** Obtém testes de estrutura de validação de operação para módulos instalados.</span><span class="sxs-lookup"><span data-stu-id="ba193-108">The **Get-OperationValidation** cmdlet gets Operation Validation Framework tests for installed modules.</span></span>

<span data-ttu-id="ba193-109">Os módulos que incluem uma pasta de diagnóstico são inspecionados para testes de Pester na subpasta simples ou abrangente, ou ambos.</span><span class="sxs-lookup"><span data-stu-id="ba193-109">Modules that include a Diagnostics folder are inspected for Pester tests in the Simple or Comprehensive subfolder, or both.</span></span>

## <span data-ttu-id="ba193-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ba193-110">EXAMPLES</span></span>

### <span data-ttu-id="ba193-111">Exemplo 1: obter testes de validação de operação</span><span class="sxs-lookup"><span data-stu-id="ba193-111">Example 1: Get Operation Validation tests</span></span>

```
PS C:\> Get-OperationValidation -ModuleName "C:\temp\modules\AddNumbers"
    Type:     Simple
    File:     addnum.tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Simple\addnum.tests.ps1
    Name:
        Add-Em
        Subtract em
        Add-Numbers
    Type:     Comprehensive
    File:     Comp.Adding.Tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Comprehensive\Comp.Adding.Tests.ps1
    Name:
        Comprehensive Adding Tests
        Comprehensive Subtracting Tests
        Comprehensive Examples
```

<span data-ttu-id="ba193-112">Esse comando obtém testes de validação do módulo chamado AddNumbers na pasta C:\temp\modules</span><span class="sxs-lookup"><span data-stu-id="ba193-112">This command gets validation tests from the module named AddNumbers in the C:\temp\modules folder.</span></span>

## <span data-ttu-id="ba193-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ba193-113">PARAMETERS</span></span>

### <span data-ttu-id="ba193-114">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="ba193-114">-ModuleName</span></span>
<span data-ttu-id="ba193-115">Especifica uma matriz de nomes de módulos.</span><span class="sxs-lookup"><span data-stu-id="ba193-115">Specifies an array of names of modules.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ba193-116">-TestType</span><span class="sxs-lookup"><span data-stu-id="ba193-116">-TestType</span></span>
<span data-ttu-id="ba193-117">Especifica uma matriz de tipos de teste.</span><span class="sxs-lookup"><span data-stu-id="ba193-117">Specifies an array of test types.</span></span>
<span data-ttu-id="ba193-118">Os valores válidos são simples, abrangentes ou ambos.</span><span class="sxs-lookup"><span data-stu-id="ba193-118">Valid values are Simple, Comprehensive, or both.</span></span>
<span data-ttu-id="ba193-119">O padrão é "simples, abrangente".</span><span class="sxs-lookup"><span data-stu-id="ba193-119">The default is "Simple,Comprehensive".</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Simple, Comprehensive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ba193-120">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ba193-120">CommonParameters</span></span>
<span data-ttu-id="ba193-121">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ba193-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ba193-122">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ba193-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ba193-123">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ba193-123">INPUTS</span></span>

### <span data-ttu-id="ba193-124">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ba193-124">None</span></span>
<span data-ttu-id="ba193-125">Não é possível canalizar nenhuma entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ba193-125">You cannot pipe any input to this cmdlet.</span></span>

## <span data-ttu-id="ba193-126">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ba193-126">OUTPUTS</span></span>

### <span data-ttu-id="ba193-127">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="ba193-127">PSCustomObject</span></span>
<span data-ttu-id="ba193-128">O **PSCustomObject** descreve a validação.</span><span class="sxs-lookup"><span data-stu-id="ba193-128">The **PSCustomObject** describes the validation.</span></span>

## <span data-ttu-id="ba193-129">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ba193-129">NOTES</span></span>

## <span data-ttu-id="ba193-130">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ba193-130">RELATED LINKS</span></span>

[<span data-ttu-id="ba193-131">Invoke-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="ba193-131">Invoke-OperationValidation</span></span>](Invoke-OperationValidation.md)
