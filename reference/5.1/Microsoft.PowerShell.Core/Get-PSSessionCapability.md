---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessioncapability?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionCapability
ms.openlocfilehash: d76baaef31c27184bc355b6f0fc79ca67b986157
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193320"
---
# Get-PSSessionCapability

## SINOPSE
Obtém os recursos de um usuário específico em uma configuração de sessão restrita.

## SYNTAX

```
Get-PSSessionCapability [-ConfigurationName] <String> [-Username] <String> [-Full] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Get-PSSessionCapability** Obtém os recursos de um usuário específico em uma configuração de sessão restrita.
Use este cmdlet para auditar configurações de sessão personalizadas para usuários.

A partir do Windows PowerShell 5,0, você pode usar a propriedade **RoleDefinitions** em um arquivo de configuração de sessão (. PSSC).
O uso dessa propriedade permite que você conceda aos usuários recursos diferentes em um único ponto de extremidade restrito com base na associação de grupo.
O cmdlet **Get-PSSessionCapability** reduz a complexidade ao auditar esses pontos de extremidade, permitindo que você determine os recursos exatos concedidos a um usuário.

Por padrão, o cmdlet **Get-PSSessionCapability** retorna uma lista de comandos que o usuário especificado pode executar no ponto de extremidade especificado.
Isso é equivalente ao usuário que está executando **Get-Command** no ponto de extremidade especificado.
Quando executado com o parâmetro *Full* , esse cmdlet retorna um objeto **InitialSessionState** .
Este objeto contém detalhes sobre o runspace do Windows PowerShell com o qual o usuário especificado interagiria com o ponto de extremidade especificado.
Ele inclui informações como o modo de linguagem, a política de execução e as variáveis ambientais.

## EXEMPLOS

### Exemplo 1: obter os comandos disponíveis para um usuário

```
PS C:\> Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User'
```

Este exemplo retorna os comandos disponíveis para o usuário CONTOSO\User ao se conectar ao ponto de extremidade restrito do Endpoint1 no computador local.

### Exemplo 2: obter detalhes sobre um runspace para um usuário

```
PS C:\> Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User' -Full
```

Este exemplo retorna detalhes sobre o runspace ao qual o usuário CONTOSO\User interagiria ao se conectar ao ponto de extremidade restrito de Endpoint1.

## PARAMETERS

### -ConfigurationName
Especifica a configuração de sessão restrita (ponto de extremidade) que você está inspecionando.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Full
Indica que esse cmdlet retorna o estado de sessão inicial inteiro para o usuário especificado no ponto de extremidade restrito especificado.

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

### -Username
Especifica o usuário cujos recursos você está inspecionando.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

### System. Management. Automation. AliasInfo

### System. Management. Automation. FunctionInfo

### System.Management.Automation.Runspaces.InitialSessionState

## OBSERVAÇÕES

## LINKS RELACIONADOS

[New-PSRoleCapabilityFile](New-PSRoleCapabilityFile.md)
