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
# Get-OperationValidation

## SINOPSE
Obtém testes da estrutura de validação da operação.

## SYNTAX

```
Get-OperationValidation [[-ModuleName] <String[]>] [-TestType <String[]>] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Get-OperationValidation** Obtém testes de estrutura de validação de operação para módulos instalados.

Os módulos que incluem uma pasta de diagnóstico são inspecionados para testes de Pester na subpasta simples ou abrangente, ou ambos.

## EXEMPLOS

### Exemplo 1: obter testes de validação de operação

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

Esse comando obtém testes de validação do módulo chamado AddNumbers na pasta C:\temp\modules

## PARAMETERS

### -ModuleName
Especifica uma matriz de nomes de módulos.

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

### -TestType
Especifica uma matriz de tipos de teste.
Os valores válidos são simples, abrangentes ou ambos.
O padrão é "simples, abrangente".

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

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível canalizar nenhuma entrada para este cmdlet.

## SAÍDAS

### PSCustomObject
O **PSCustomObject** descreve a validação.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Invoke-OperationValidation](Invoke-OperationValidation.md)
