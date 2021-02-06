---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSSessionConfiguration
ms.openlocfilehash: 86650f33f376ccb7d1428836c9d0070e749cf0ee
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596181"
---
# Disable-PSSessionConfiguration

## SINOPSE
Habilita as configurações de sessão no computador local.

## SYNTAX

```
Enable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-SecurityDescriptorSddl <String>]
 [-SkipNetworkProfileCheck] [-NoServiceRestart] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Enable-PSSessionConfiguration` cmdlet habilita as configurações de sessão registradas que foram desabilitadas, como usando `Disable-PSSessionConfiguration` os `Disable-PSRemoting` cmdlets ou ou o parâmetro **AccessMode** de `Register-PSSessionConfiguration` . Esse é um cmdlet avançado projetado para ser utilizado por administradores de sistema a fim de gerenciar configurações de sessão personalizadas para seus usuários.

Sem parâmetros, `Enable-PSSessionConfiguration` habilita a configuração do **Microsoft. PowerShell** , que é a configuração padrão usada para sessões.

`Enable-PSSessionConfiguration` Remove a configuração de **Deny_All** do descritor de segurança das configurações de sessão afetadas, ativa o ouvinte que aceita solicitações em qualquer endereço IP e reinicia o serviço WinRM. A partir do PowerShell 3,0, `Enable-PSSessionConfiguration` também define o valor da propriedade **Enabled** da configuração de sessão ( `WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled` ) como true. No entanto, `Enable-PSSessionConfiguration` o não remove ou  altera a `AccessMode=Local` configuração do descritor de segurança Network_Deny_All () que permite que somente usuários do computador local usem para a configuração de sessão.

## EXEMPLOS

### Exemplo 1: reabilitar a sessão padrão

Este exemplo habilita novamente a configuração de sessão padrão do **Microsoft. PowerShell** no computador.

```powershell
Enable-PSSessionConfiguration
```

### Exemplo 2: reabilitar as sessões especificadas

Este exemplo habilita novamente as configurações de sessão **MaintenanceShell** e **AdminShell** no computador.

```powershell
Enable-PSSessionConfiguration -Name MaintenanceShell, AdminShell
```

### Exemplo 3: reabilitar todas as sessões

Este exemplo habilita novamente todas as configurações de sessão no computador. Esses comandos são equivalentes.
Portanto, você pode usar qualquer um.

```powershell
Enable-PSSessionConfiguration -Name *
Get-PSSessionConfiguration | Enable-PSSessionConfiguration
```

`Enable-PSSessionConfiguration` não gerará um erro se você habilitar uma configuração de sessão que já está habilitada.

### Exemplo 4: reabilitar uma sessão e especificar um novo descritor de segurança

Este exemplo habilita novamente a configuração de sessão **MaintenanceShell** e especifica um novo descritor de segurança para a configuração.

```powershell
$sddl = "O:NSG:BAD:P(A;;GXGWGR;;;BA)(A;;GAGR;;;S-1-5-21-123456789-188441444-3100496)S:P"
Enable-PSSessionConfiguration -Name MaintenanceShell -SecurityDescriptorSDDL $sddl
```

## PARAMETERS

### -Force

Indica que o cmdlet não solicita confirmação e reinicia o serviço WinRM sem avisar. Reiniciar o serviço faz a com que a alteração da configuração entre em vigor.

Para evitar uma reinicialização e suprimir o prompt de reinicialização, use o parâmetro **NoServiceRestart**.

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

### -Name

Especifica os nomes das configurações de sessão a habilitar. Insira um ou mais nomes de configuração.
Caracteres curinga são permitidos.

Você também pode canalizar uma cadeia de caracteres que contém um nome de configuração ou um objeto de configuração de sessão para `Enable-PSSessionConfiguration` .

Se você omitir esse parâmetro, `Enable-PSSessionConfiguration` o habilitará a configuração de sessão do **Microsoft. PowerShell** .

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

### -NoServiceRestart

Indica que o cmdlet não reinicia o serviço.

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

### -SecurityDescriptorSddl

Especifica um descritor de segurança com o qual esse cmdlet substitui o descritor de segurança na configuração da sessão.

Se você omitir esse parâmetro, `Enable-PSSessionConfiguration` o excluirá apenas o item negar tudo do descritor de segurança.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipNetworkProfileCheck

Indica que esse cmdlet habilita a configuração de sessão quando o computador está em uma rede pública. Este parâmetro habilita uma regra de firewall para redes públicas que permite o acesso remoto somente por meio de computadores na mesma sub-rede local. Por padrão, `Enable-PSSessionConfiguration` o falha em uma rede pública.

Esse parâmetro é projetado para versões de cliente do sistema operacional Windows. As versões de servidor do sistema operacional Windows têm uma regra de firewall de sub-rede local para redes públicas. No entanto, se a regra de firewall de sub-rede local estiver desabilitada em uma versão de servidor do sistema operacional Windows, esse parâmetro o habilitará novamente.

Para remover a restrição de sub-rede local e habilitar o acesso remoto de todos os locais em redes públicas, use o `Set-NetFirewallRule` cmdlet no módulo NetSecurity. Para obter mais informações, consulte `Enable-PSRemoting`.

Esse parâmetro foi introduzido no PowerShell 3,0.

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

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

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

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Microsoft. PowerShell. Commands. PSSessionConfigurationCommands # PSSessionConfiguration, System. String

É possível canalizar um objeto de configuração de sessão ou uma cadeia de caracteres que contém o nome de uma configuração de sessão para esse cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhum objeto.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

Para usar esse cmdlet, você deve iniciar o PowerShell usando a opção **Executar como administrador** .

## LINKS RELACIONADOS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Provedor WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
