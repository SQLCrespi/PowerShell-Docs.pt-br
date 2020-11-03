---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscresource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscResource
ms.openlocfilehash: d710881f4444a35bd1dca7950292660889a3e38c
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2020
ms.locfileid: "93195080"
---
# Get-DscResource

## SINOPSE
Obtém recursos de DSC (configuração de estado desejado) presentes no computador.

## SYNTAX

```
Get-DscResource [[-Name] <String[]>] [[-Module] <Object>] [-Syntax] [<CommonParameters>]
```

## DESCRIPTION

O `Get-DscResource` cmdlet recupera os recursos de DSC do PowerShell presentes no computador. Esse cmdlet descobre apenas os recursos instalados no PSModulePath. Ele mostra os detalhes sobre os provedores internos e personalizados, que são criados pelo usuário. Esse cmdlet também mostra detalhes sobre os recursos de composição, que são outras configurações que são empacotadas como módulo ou criadas em tempo de execução na sessão.

## EXEMPLOS

### Exemplo 1: obter todos os recursos no computador local

```powershell
 Get-DscResource
```

Esse comando obtém todos os recursos no computador local.

### Exemplo 2: obter um recurso especificando o nome

```powershell
Get-DscResource -Name "WindowsFeature"
```

Esse comando obtém o recurso WindowsFeature.

### Exemplo 3: obter todos os recursos de um módulo

```powershell
Get-DscResource -Module "xHyper-V"
```

Esse comando obtém todos os recursos do módulo xHyper-V.

### Exemplo 4: obter um recurso usando caracteres curinga

```powershell
Get-DscResource -Name P*,r*
```

Esse comando obtém todos os recursos que correspondem ao padrão curinga especificado pelo parâmetro **Name** .

### Exemplo 5: obter uma sintaxe de recurso

```powershell
Get-DscResource -Name "WindowsFeature" -Syntax
```

Esse comando obtém o recurso WindowsFeature e mostra a sintaxe do recurso.

### Exemplo 6: obter todas as propriedades de um recurso

```powershell
Get-DscResource -Name "User" | Select-Object -ExpandProperty Properties
```

Esse comando obtém o recurso User e, em seguida, usa o operador de pipeline para retornar todas as propriedades do recurso User.

### Exemplo 7: obter todos os recursos de um módulo especificado com uma versão especificada

```powershell
Get-DscResource -Module @{ModuleName='xHyper-V';RequiredVersion='3.0.0.0'}
```

Esse comando obtém todos os recursos do módulo xHyper-V com a versão 3.0.0.0.

## PARAMETERS

### -Módulo

Especifica o nome ou nome totalmente qualificado do módulo para o qual exibir o recurso de DSC.

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

### -Name

Especifica uma matriz de nomes do recurso DSC a ser exibido.

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

### -Sintaxe

Indica que o cmdlet retorna a exibição de sintaxe dos recursos de DSC especificados. A sintaxe retornada mostra como usar os recursos em um script do PowerShell.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String[]

### System.Object

## SAÍDAS

### Microsoft. PowerShell. DesiredStateConfiguration. DscResourceInfo []

### string[]

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Visão geral da configuração de estado desejado do PowerShell](/powershell/scripting/dsc/overview/overview)

[Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)
