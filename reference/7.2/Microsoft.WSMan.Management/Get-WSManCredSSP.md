---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManCredSSP
ms.openlocfilehash: 9830d1feb31e9cca735a7ac8d2ed9d2ec50380b5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597591"
---
# Get-WSManCredSSP

## SINOPSE
Obtém a configuração relacionada ao Credential Security Support Provider para o cliente.

## SYNTAX

```
Get-WSManCredSSP [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Get-WSManCredSSP** Obtém a configuração relacionada ao provedor de suporte de segurança de credenciais do cliente e do servidor.
A saída indica se a autenticação Credential Security Support Provider (CredSSP) está habilitada ou desabilitada.
Esse cmdlet também exibe informações de configuração para a política **AllowFreshCredentials** de CredSSP.

Quando você usa a autenticação CredSSP, as credenciais do usuário são passadas para um computador remoto a ser autenticado.
Esse tipo de autenticação destina-se a comandos que criam uma sessão remota de outra sessão remota.
Por exemplo, se você quiser executar um trabalho em segundo plano em um computador remoto, use esse tipo de autenticação.

O cmdlet executa as seguintes ações:

- Obtém a configuração WS-Management CredSSP no cliente (**\<localhost|computername\> \Client\Auth\CredSSP**).
- Obtém a configuração de política de CredSSP do Windows **AllowFreshCredentials**.
- Obtém a configuração de WS-Management CredSSP no servidor (**\<localhost|computername\> \Service\Auth\CredSSP**).

Cuidado: a autenticação CredSSP Delega as credenciais do usuário do computador local para um computador remoto.
Essa prática aumenta o risco de segurança da operação remota.
Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.

## EXEMPLOS

### Exemplo 1: exibir a configuração de CredSSP

```
PS C:\> Get-WSManCredSSP
```

Esse comando exibe informações de configuração CredSSP para o cliente e o servidor.

A saída identifica que o computador está ou não configurado para CredSSP.

Se o computador estiver configurado para CredSSP, esta é a saída:

`The machine is configured to allow delegating fresh credentials to the following target(s): wsman/server02.accounting.fabrikam.com`

Se o computador não estiver configurado para CredSSP, esta é a saída:

`The machine is not configured to allow delegating fresh credentials.`

## PARAMETERS

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Esse cmdlet não aceita nenhuma entrada.

## SAÍDAS

### Nenhum
Este cmdlet não gera saída.

## OBSERVAÇÕES

* Para desabilitar a autenticação CredSSP, utilize o cmdlet Disable-WSManCredSSP. Para habilitar a autenticação CredSSP, utilize o cmdlet Enable-WSManCredSSP.

## LINKS RELACIONADOS

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)

