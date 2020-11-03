---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 0c8c386ab376afde3d15fcd29b3f653b3f738f63
ms.sourcegitcommit: 0e0f45d0d8deb8c9088a4f4a32218edde052b686
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2020
ms.locfileid: "93194844"
---
# Enable-PSRemoting

## SINOPSE
Configura o computador para receber comandos remotos.

## SYNTAX

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Enable-PSRemoting` cmdlet configura o computador para receber comandos remotos do PowerShell que são enviados usando a tecnologia de WS-Management.

A comunicação remota do PowerShell é habilitada por padrão no Windows Server 2012. Você pode usar o `Enable-PSRemoting` para habilitar a comunicação remota do PowerShell em outras versões com suporte do Windows e para reabilitar a comunicação remota no Windows Server 2012 se ele se tornar desabilitado.

Você precisa executar esse comando apenas uma vez em cada computador que receberá comandos. Você não precisa executá-lo em computadores que só enviam comandos. Como a configuração inicia os ouvintes, é prudente executá-lo somente onde for necessário.

A partir do PowerShell 3,0, o `Enable-PSRemoting` cmdlet pode habilitar a comunicação remota do PowerShell em versões cliente do Windows quando o computador está em uma rede pública. Para obter mais informações, consulte a descrição do parâmetro **SkipNetworkProfileCheck** .

O `Enable-PSRemoting` cmdlet executa as seguintes operações:

- Executa o cmdlet [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) , que executa as seguintes tarefas:
  - Inicia o serviço WinRM.
  - Define o tipo de inicialização no serviço WinRM como automático.
  - Cria um ouvinte para aceitar solicitações em qualquer endereço IP.
  - Habilita uma exceção de firewall para WS-Management comunicações.
  - Registra as configurações de sessão **Microsoft. PowerShell** e **Microsoft. PowerShell. Workflow** , se elas ainda não estiverem registradas.
  - Registra a configuração de sessão **Microsoft. powershell32** em computadores de 64 bits, se ainda não estiver registrado.
  - Habilita todas as configurações de sessão.
  - Altera o descritor de segurança de todas as configurações de sessão para permitir o acesso remoto.
- Reinicia o serviço WinRM para tornar as alterações anteriores efetivas.

Para executar esse cmdlet na plataforma Windows, inicie o PowerShell usando a opção Executar como administrador. Isso não se aplica às versões Linux ou MacOS do PowerShell.

> [!CAUTION]
> Em sistemas que têm o PowerShell 3,0 e o PowerShell 2,0, não use o PowerShell 2,0 para executar `Enable-PSRemoting` os `Disable-PSRemoting` cmdlets e. Os comandos podem parecer bem-sucedidos, mas a comunicação remota não está configurada corretamente. Os comandos remotos e tentativas posteriores de habilitar e desabilitar a comunicação remota, provavelmente falharão.

## EXEMPLOS

### Exemplo 1: configurar um computador para receber comandos remotos

Este comando configura o computador para receber comandos remotos.

```powershell
Enable-PSRemoting
```

### Exemplo 2: configurar um computador para receber comandos remotos sem um prompt de confirmação

Este comando configura o computador para receber comandos remotos.
O parâmetro **Force** suprime os prompts do usuário.

```powershell
Enable-PSRemoting -Force
```

### Exemplo 3: permitir acesso remoto em clientes

Este exemplo mostra como permitir o acesso remoto de redes públicas em versões de cliente do sistema operacional Windows. O nome da regra de firewall pode ser diferente para diferentes versões do Windows.
Use `Get-NetFirewallRule` para ver uma lista de regras. Antes de habilitar a regra de firewall, exiba as configurações de segurança na regra para verificar se a configuração é apropriada para o seu ambiente.

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

Por padrão, o `Enable-PSRemoting` cria regras de rede que permitem o acesso remoto de redes privadas e de domínio. O comando usa o parâmetro **SkipNetworkProfileCheck** para permitir acesso remoto por meio de redes públicas contidas na mesma sub-rede local. O comando especifica o parâmetro **Force** para suprimir as mensagens de confirmação.

O parâmetro **SkipNetworkProfileCheck** não afeta as versões de servidor do sistema operacional Windows, que permitem o acesso remoto de redes públicas na mesma sub-rede local por padrão.

O `Set-NetFirewallRule` cmdlet no módulo **NetSecurity** adiciona uma regra de firewall que permite o acesso remoto de redes públicas de qualquer local remoto. Isso inclui locais em sub-redes diferentes.

> [!NOTE]
> O nome da regra de firewall pode ser diferente dependendo da versão do Windows. Use o `Get-NetFirewallRule` cmdlet para listar os nomes das regras em seu sistema.

## PARAMETERS

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

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.

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

### -SkipNetworkProfileCheck

Indica que esse cmdlet habilita a comunicação remota em versões de cliente do sistema operacional Windows quando o computador está em uma rede pública. Este parâmetro habilita uma regra de firewall para redes públicas que permite o acesso remoto somente por meio de computadores na mesma sub-rede local.

Esse parâmetro não afeta as versões de servidor do sistema operacional Windows, que, por padrão, têm uma regra de firewall de sub-rede local para redes públicas. Se a regra de firewall de sub-rede local estiver desabilitada em uma versão de servidor, habilite-a `Enable-PSRemoting` novamente, independentemente do valor desse parâmetro.

Para remover a restrição de sub-rede local e habilitar o acesso remoto de todos os locais em redes públicas, use o `Set-NetFirewallRule` cmdlet no módulo **NetSecurity** .

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

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

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

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System.String

Esse cmdlet retorna cadeias de caracteres que descrevem seus resultados.

## OBSERVAÇÕES

No PowerShell 3,0, `Enable-PSRemoting` o cria as seguintes exceções de firewall para WS-Management comunicações.

Em versões de servidor do sistema operacional Windows, o `Enable-PSRemoting` cria regras de firewall para redes privadas e de domínio que permitem acesso remoto e cria uma regra de firewall para redes públicas que permite o acesso remoto somente de computadores na mesma sub-rede local.

Em versões de cliente do sistema operacional Windows, `Enable-PSRemoting` no PowerShell 3,0 cria regras de firewall para redes privadas e de domínio que permitem acesso remoto irrestrito. Para criar uma regra de firewall para redes públicas que permite acesso remoto por meio da mesma sub-rede local, use o parâmetro **SkipNetworkProfileCheck** .

Em versões de cliente ou servidor do sistema operacional Windows, para criar uma regra de firewall para redes públicas que remove a restrição de sub-rede local e permite o acesso remoto, use o `Set-NetFirewallRule` cmdlet no módulo NetSecurity para executar o seguinte comando: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`

No PowerShell 2,0, `Enable-PSRemoting` o cria as seguintes exceções de firewall para WS-Management comunicações.

Em versões de servidor do sistema operacional Windows, ele cria regras de firewall para todas as redes que permitem acesso remoto.

Nas versões cliente do sistema operacional Windows, `Enable-PSRemoting` no PowerShell 2,0 cria uma exceção de firewall somente para locais de rede privada e de domínio. Para minimizar os riscos de segurança, `Enable-PSRemoting` o não cria uma regra de firewall para redes públicas em versões de cliente do Windows. Quando o local de rede atual é público, `Enable-PSRemoting` retorna a seguinte mensagem: não é possível verificar o status do firewall.

A partir do PowerShell 3,0, `Enable-PSRemoting` o habilita todas as configurações de sessão definindo o valor da propriedade **Enabled** de todas as configurações de sessão como `$True` .

No PowerShell 2,0, `Enable-PSRemoting` Remove a configuração **Deny_All** do descritor de segurança de configurações de sessão. No PowerShell 3,0, `Enable-PSRemoting` Remove as configurações de **Deny_All** e **Network_Deny_All** . Isso fornece acesso remoto a configurações de sessão que foram reservadas para uso local.

## LINKS RELACIONADOS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Disable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Disable-PSRemoting](Disable-PSRemoting.md)

[Provedor WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Remote](About/about_Remote.md)

[about_Session_Configurations](About/about_Session_Configurations.md)
