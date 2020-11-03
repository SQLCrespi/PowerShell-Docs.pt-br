---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/invoke-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-OperationValidation
ms.openlocfilehash: 6c9d4001392de48032a0fe1ba3667db90ea614fc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193887"
---
# <span data-ttu-id="c5a16-103">Invoke-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="c5a16-103">Invoke-OperationValidation</span></span>

## <span data-ttu-id="c5a16-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c5a16-104">SYNOPSIS</span></span>

<span data-ttu-id="c5a16-105">Invoca testes de estrutura de validação de operação.</span><span class="sxs-lookup"><span data-stu-id="c5a16-105">Invokes Operation Validation Framework tests.</span></span>

## <span data-ttu-id="c5a16-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c5a16-106">SYNTAX</span></span>

### <span data-ttu-id="c5a16-107">FileAndTest (padrão)</span><span class="sxs-lookup"><span data-stu-id="c5a16-107">FileAndTest (Default)</span></span>

```
Invoke-OperationValidation [-TestInfo <PSObject[]>] [-IncludePesterOutput] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="c5a16-108">Caminho</span><span class="sxs-lookup"><span data-stu-id="c5a16-108">Path</span></span>

```
Invoke-OperationValidation [-testFilePath <String[]>] [-IncludePesterOutput] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="c5a16-109">UseGetOperationTest</span><span class="sxs-lookup"><span data-stu-id="c5a16-109">UseGetOperationTest</span></span>

```
Invoke-OperationValidation [-ModuleName <String[]>] [-TestType <String[]>] [-IncludePesterOutput] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c5a16-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c5a16-110">DESCRIPTION</span></span>

<span data-ttu-id="c5a16-111">O cmdlet **Invoke-OperationValidation** invoca testes de estrutura de validação de operação para um módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="c5a16-111">The **Invoke-OperationValidation** cmdlet invokes Operation Validation Framework tests for a specified module.</span></span>

## <span data-ttu-id="c5a16-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c5a16-112">EXAMPLES</span></span>

### <span data-ttu-id="c5a16-113">Exemplo 1: invocar um teste de validação de operação</span><span class="sxs-lookup"><span data-stu-id="c5a16-113">Example 1: Invoke an Operation Validation test</span></span>

```
PS C:\> Get-OperationValidation -ModuleName "OperationValidation" | Invoke-OperationValidation -IncludePesterOutput
Describing Simple Test Suite
 [+] first Operational test 20ms
 [+] second Operational test 19ms
 [+] third Operational test 9ms
Tests completed in 48ms
Passed: 3 Failed: 0 Skipped: 0 Pending: 0
Describing Scenario targeted tests
   Context The RemoteAccess service
    [+] The service is running 37ms
   Context The Firewall Rules
    [+] A rule for TCP port 3389 is enabled 1.19s
    [+] A rule for UDP port 3389 is enabled 11ms
Tests completed in 1.24s
Passed: 3 Failed: 0 Skipped: 0 Pending: 0




   Module: OperationValidation




Result  Name
------- --------
Passed  Simple Test Suite::first Operational test
Passed  Simple Test Suite::second Operational test
Passed  Simple Test Suite::third Operational test
Passed  Scenario targeted tests:The RemoteAccess service:The service is running
Passed  Scenario targeted tests:The Firewall Rules:A rule for TCP port 3389 is enabled
Passed  Scenario targeted tests:The Firewall Rules:A rule for UDP port 3389 is enabled
```

<span data-ttu-id="c5a16-114">Esse comando obtém o módulo chamado OperationValidation e usa o operador de pipeline para passá-lo para o cmdlet **Invoke-OperationValidation** , que executa o teste.</span><span class="sxs-lookup"><span data-stu-id="c5a16-114">This command gets the module named OperationValidation, and uses the pipeline operator to pass it to the **Invoke-OperationValidation** cmdlet, which runs the test.</span></span>

## <span data-ttu-id="c5a16-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c5a16-115">PARAMETERS</span></span>

### <span data-ttu-id="c5a16-116">-IncludePesterOutput</span><span class="sxs-lookup"><span data-stu-id="c5a16-116">-IncludePesterOutput</span></span>

<span data-ttu-id="c5a16-117">Inclui saída de teste do Pester.</span><span class="sxs-lookup"><span data-stu-id="c5a16-117">Includes Pester test output.</span></span>
<span data-ttu-id="c5a16-118">O padrão é $False.</span><span class="sxs-lookup"><span data-stu-id="c5a16-118">The default is $False.</span></span>

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

### <span data-ttu-id="c5a16-119">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="c5a16-119">-ModuleName</span></span>

<span data-ttu-id="c5a16-120">Especifica uma matriz de nomes de módulos.</span><span class="sxs-lookup"><span data-stu-id="c5a16-120">Specifies an array of names of modules.</span></span>

```yaml
Type: System.String[]
Parameter Sets: UseGetOperationTest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5a16-121">-testFilePath</span><span class="sxs-lookup"><span data-stu-id="c5a16-121">-testFilePath</span></span>

<span data-ttu-id="c5a16-122">Especifica o caminho de um arquivo de teste da estrutura de validação de operação.</span><span class="sxs-lookup"><span data-stu-id="c5a16-122">Specifies the path of an Operation Validation Framework test file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c5a16-123">-TestInfo</span><span class="sxs-lookup"><span data-stu-id="c5a16-123">-TestInfo</span></span>

<span data-ttu-id="c5a16-124">Especifica um objeto personalizado que especifica o caminho para o arquivo e o nome do teste a ser executado.</span><span class="sxs-lookup"><span data-stu-id="c5a16-124">Specifies a custom object that specifies the path to the file and the name of the test to run.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: FileAndTest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c5a16-125">-TestType</span><span class="sxs-lookup"><span data-stu-id="c5a16-125">-TestType</span></span>

<span data-ttu-id="c5a16-126">Especifica uma matriz de tipos de teste.</span><span class="sxs-lookup"><span data-stu-id="c5a16-126">Specifies an array of test types.</span></span>
<span data-ttu-id="c5a16-127">Os valores válidos são simples, abrangentes ou ambos.</span><span class="sxs-lookup"><span data-stu-id="c5a16-127">Valid values are Simple, Comprehensive, or both.</span></span>
<span data-ttu-id="c5a16-128">O padrão é "simples, abrangente".</span><span class="sxs-lookup"><span data-stu-id="c5a16-128">The default is "Simple,Comprehensive".</span></span>

```yaml
Type: System.String[]
Parameter Sets: UseGetOperationTest
Aliases:
Accepted values: Simple, Comprehensive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5a16-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c5a16-129">-Confirm</span></span>

<span data-ttu-id="c5a16-130">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c5a16-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c5a16-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c5a16-131">-WhatIf</span></span>

<span data-ttu-id="c5a16-132">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="c5a16-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c5a16-133">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="c5a16-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c5a16-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c5a16-134">CommonParameters</span></span>
<span data-ttu-id="c5a16-135">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c5a16-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c5a16-136">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c5a16-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c5a16-137">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c5a16-137">INPUTS</span></span>

### <span data-ttu-id="c5a16-138">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="c5a16-138">PSCustomObject</span></span>

<span data-ttu-id="c5a16-139">Você pode canalizar a saída de **Get-OperationValidation** para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c5a16-139">You can pipe the output of **Get-OperationValidation** to this cmdlet.</span></span>

## <span data-ttu-id="c5a16-140">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c5a16-140">OUTPUTS</span></span>

### <span data-ttu-id="c5a16-141">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="c5a16-141">PSCustomObject</span></span>

<span data-ttu-id="c5a16-142">O **PSCustomObject** descreve se a validação foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="c5a16-142">The **PSCustomObject** describes whether the validation was successful.</span></span>

## <span data-ttu-id="c5a16-143">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c5a16-143">NOTES</span></span>

## <span data-ttu-id="c5a16-144">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c5a16-144">RELATED LINKS</span></span>

[<span data-ttu-id="c5a16-145">Get-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="c5a16-145">Get-OperationValidation</span></span>](Get-OperationValidation.md)
