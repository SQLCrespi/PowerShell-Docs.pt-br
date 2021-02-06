---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 10/02/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmanquickconfig?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManQuickConfig
ms.openlocfilehash: e5d50af0551a183b8e9e1995fbd722c331a48486
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603322"
---
# Set-WSManQuickConfig

## SINOPSE
Configura o computador local para gerenciamento remoto.

## SYNTAX

### Tudo

```
Set-WSManQuickConfig [-UseSSL] [-Force] [-SkipNetworkProfileCheck] [<CommonParameters>]
```

## DESCRIPTION

O `Set-WSManQuickConfig` cmdlet configura o computador para receber comandos remotos do PowerShell que são enviados usando a tecnologia Web Services for Management (WS-Management).

`Set-WSManQuickConfig` executa as seguintes ações:

- Verifica se o serviço WinRM está em execução. Se o serviço WinRM não estiver em execução, o serviço será iniciado.
- Define o tipo de inicialização do serviço WinRM como automático.
- Cria um ouvinte para aceitar solicitações em qualquer endereço IP. O transporte padrão é **http**.
- Habilita uma exceção de firewall para o tráfego do WinRM.

Para executar `Set-WSManQuickConfig` , inicie o PowerShell com a opção **Executar como administrador** .

## EXEMPLOS

### Exemplo 1: habilitar o gerenciamento remoto do computador local por HTTP

Este exemplo define a configuração necessária para habilitar o gerenciamento remoto do computador local. Por padrão, esse comando cria um ouvinte de WS-Management em **http**.

```powershell
Set-WSManQuickConfig
```

### Exemplo 2: habilitar o gerenciamento remoto do computador local por HTTPS

Este exemplo define a configuração necessária para habilitar o gerenciamento remoto do computador local. O parâmetro **UseSSL** especifica que o **https** é usado para se comunicar com o computador.

```powershell
Set-WSManQuickConfig -UseSSL
```

> [!NOTE]
> O **https** requer configuração manual. Para obter mais informações, consulte a descrição do parâmetro **UseSSL** .

## PARAMETERS

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipNetworkProfileCheck

Configura as versões do cliente do Windows para comunicação remota quando o computador está em uma rede pública. Este parâmetro habilita uma regra de firewall para redes públicas que permite o acesso remoto somente por meio de computadores na mesma sub-rede local.

Esse parâmetro não tem nenhum efeito nas versões de servidor do Windows, por padrão, ter uma regra de firewall de sub-rede local para redes públicas. Se a regra de firewall de sub-rede local estiver desabilitada na versão de servidor do Windows, habilite-a `Enable-PSRemoting` novamente, independentemente do valor desse parâmetro.

Para remover a restrição de sub-rede local e habilitar o acesso remoto de todos os locais em redes públicas, use o `Set-NetFirewallRule` cmdlet no módulo **NetSecurity** .

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

Especifica que o protocolo de protocolo SSL (SSL) é usado para estabelecer uma conexão com o computador remoto. Por padrão, o SSL não é usado.

WS-Management criptografa todo o conteúdo do PowerShell que é transmitido pela rede. O parâmetro **UseSSL** permite especificar a proteção adicional do HTTPS em vez de http. Se você usar esse parâmetro e o SSL não estiver disponível na porta usada para a conexão, o comando falhará.

O **https** requer configuração manual de regras de firewall e WinRM. Para obter mais informações, consulte [como: configurar o WinRM para https](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Esse cmdlet não aceita nenhuma entrada.

## SAÍDAS

### Nenhum

Esse cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-PSRemoting](../Microsoft.PowerShell.Core/Enable-PSRemoting.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Como configurar o WINRM para HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-PSSession](../Microsoft.PowerShell.Core/New-PSSession.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Test-WSMan](Test-WSMan.md)

