---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: d73d8d6a30e6b7c08b5a0b7988ea2327be34002a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194144"
---
# Invoke-DscResource

## SINOPSE
Executa um método de um recurso de DSC especificado.

## SYNTAX

```
Invoke-DscResource [-Name] <String> [-Method] <String> -ModuleName <ModuleSpecification> -Property <Hashtable>
 [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Invoke-DscResource** executa um método de um recurso de DSC (configuração de estado desejado) do Windows PowerShell especificado.
Antes de executar este cmdlet, defina o modo de atualização do Configuration Manager local (LCM) como desabilitado.

Esse cmdlet invoca um recurso de DSC diretamente, sem criar um documento de configuração.
Usando esse cmdlet, os produtos de gerenciamento de configuração podem gerenciar o Windows usando recursos de DSC.
Esse cmdlet também habilita a depuração de recursos quando o mecanismo de DSC ou o LCM está em execução com a depuração habilitada.

## EXEMPLOS

### Exemplo 1: invocar o método set de um recurso especificando suas propriedades obrigatórias

```
PS C:\> Invoke-DscResource -Name Log -Method Set -Property @{Message = 'Hello World'} -ModuleName PSDesiredStateConfiguration
```

Esse comando invoca o método **set** de um recurso chamado log e especifica uma propriedade de **mensagem** para ele.

### Exemplo 2: invocar o método de teste de um recurso para um módulo especificado

```
PS C:\> Invoke-DscResource -Name WindowsProcess -Method Test -Property @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''} -ModuleName PSDesiredStateConfiguration
```

Esse comando invoca o método de **teste** de um recurso chamado WindowsProcess, que está no módulo chamado PSDesiredStateConfiguration.

## PARAMETERS

### -Método
Especifica o método do recurso que esse cmdlet invoca. Os valores aceitáveis para esse parâmetro são: Get, set e Test.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ModuleName
Especifica o nome do módulo do qual este cmdlet invoca o recurso especificado.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Especifica o nome do recurso DSC a ser iniciado.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Propriedade
Especifica o nome da propriedade de recurso e seu valor em uma tabela de hash como chave e valor, respectivamente. Use o cmdlet **Get-DscResource** para descobrir as propriedades de recurso e seus tipos.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

### Microsoft. Management. Infrastructure. CimInstance, System. Boolean

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Visão geral da Desired State Configuration do Windows PowerShell](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Get-DscResource](Get-DscResource.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Set-DscLocalConfigurationManager](Set-DscLocalConfigurationManager.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
