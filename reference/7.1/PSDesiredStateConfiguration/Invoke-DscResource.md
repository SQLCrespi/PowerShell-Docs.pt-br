---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: 8425c3e68573fe214ec5de465c8492e0bf99b309
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "93195218"
---
# Invoke-DscResource

## SINOPSE
Executa um método de um recurso de configuração de estado desejado (DSC) do PowerShell especificado.

## SYNTAX

```
Invoke-DscResource [-Name] <String> [[-ModuleName] <ModuleSpecification>] [-Method] <String>
 [-Property] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

O cmdlet `Invoke-DscResource` executa um método de um recurso de DSC (Desired State Configuration) do PowerShell especificado.

Esse cmdlet invoca um recurso de DSC diretamente, sem criar um documento de configuração. Usando esse cmdlet, os produtos de gerenciamento de configuração podem gerenciar o Windows ou o Linux usando recursos de DSC. Esse cmdlet também habilita a depuração de recursos quando o mecanismo de DSC está em execução com a depuração habilitada.

> [!NOTE]
> `Invoke-DscResource` é um recurso experimental no PowerShell 7. Para usar o cmdlet, você deve habilitá-lo usando o comando a seguir.
>
> `Enable-ExperimentalFeature PSDesiredStateConfiguration.InvokeDscResource`

## EXEMPLOS

### Exemplo 1: invocar o método set de um recurso especificando suas propriedades obrigatórias

Este exemplo invoca o método **set** de um recurso chamado **WindowsProcess** e fornece as propriedades de **caminho** e **argumentos** obrigatórios para iniciar o processo do Windows especificado.

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

### Exemplo 2: invocar o método de teste de um recurso para um módulo especificado

Este exemplo invoca o método de **teste** de um recurso chamado **WindowsProcess** , que está no módulo chamado **PSDesiredStateConfiguration** .

```powershell
$SplatParam = @{
  Name = 'WindowsProcess'
  ModuleName = 'PSDesiredStateConfiguration'
  Property = @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''}
  Method = Test
}

Invoke-DscResource @SplatParam
```

## PARAMETERS

### -Método

Especifica o método do recurso que esse cmdlet invoca. Os valores aceitáveis para esse parâmetro são: **Get** , **set** e **Test** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModuleName

Especifica o nome do módulo do qual este cmdlet invoca o recurso especificado.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Propriedade

Especifica o nome da propriedade de recurso e seu valor em uma tabela de hash como chave e valor, respectivamente.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

### Microsoft. PowerShell. Commands. ModuleSpecification

## SAÍDAS

### System.Object

## OBSERVAÇÕES

- Anteriormente, os recursos do Windows PowerShell 5,1 eram executados no contexto do sistema, a menos que especificado com o contexto do usuário usando a chave **PsDscRunAsCredential** . No PowerShell 7,0, os recursos são executados no contexto do usuário e não há mais suporte para **PsDscRunAsCredential** . As configurações anteriores que usam essa chave gerarão uma exceção.

- A partir do PowerShell 7, o `Invoke-DscResource` não dá mais suporte à invocação de recursos de DSC do WMI. Isso inclui os recursos de **Arquivo** e **Log** em **PSDesiredStateConfiguration** .

## LINKS RELACIONADOS

[Visão geral da Desired State Configuration do Windows PowerShell](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscResource](Get-DscResource.md)
