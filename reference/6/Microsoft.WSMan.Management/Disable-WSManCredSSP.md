---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disable-wsmancredssp?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManCredSSP
ms.openlocfilehash: 6b6cf6b4056dd5907f6a43cd9cf6d491bc7512b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193451"
---
# Disable-WSManCredSSP

## SINOPSE
Desabilita a autenticação CredSSP em um computador.

## SYNTAX

```
Disable-WSManCredSSP [-Role] <String> [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Disable-WSManCredSSP** desabilita a autenticação CredSSP (provedor de suporte à segurança de credencial) em um cliente ou em um computador servidor.
Quando a autenticação CredSSP é usada, as credenciais do usuário são passadas para um computador remoto a ser autenticado.

Use este cmdlet para desabilitar o CredSSP no cliente especificando o cliente no parâmetro de *função* .
Esse cmdlet executa as seguintes ações:

- Desabilita o CredSSP no cliente. Esse cmdlet define a configuração de WS-Management **\<localhost|computername\> \Client\Auth\CredSSP** como false.
- Remove qualquer configuração WSMan/* da política **AllowFreshCredentials** do Windows CredSSP no cliente.

Use este cmdlet para desabilitar o CredSSP no servidor especificando o servidor na *função* .
Esse cmdlet executa a seguinte ação:

- Desabilita o CredSSP no servidor. Esse cmdlet define a configuração de WS-Management **\<localhost|computername\> \Service\Auth\CredSSP** como false.

Cuidado: a autenticação CredSSP Delega as credenciais do usuário do computador local para um computador remoto.
Essa prática aumenta o risco de segurança da operação remota.
Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.

## EXEMPLOS

### Exemplo 1: desabilitar CredSSP em um cliente

```
PS C:\> Disable-WSManCredSSP -Role Client
```

Este comando desabilita o CredSSP no cliente, o que impede a delegação para servidores.

### Exemplo 2: desabilitar CredSSP em um servidor

```
PS C:\> Disable-WSManCredSSP -Role Server
```

Este comando desabilita o CredSSP no servidor, o que impede a delegação por meio de clientes.

## PARAMETERS

### -Função
Especifica se o CredSSP deve ser desabilitado como um cliente ou como um servidor.
Os valores aceitáveis para esse parâmetro são: cliente e servidor.

Se você especificar cliente, esse cmdlet executará as seguintes ações:

- Desabilita o CredSSP no cliente. Este cmdlet define WS-Management definindo **\<localhost|computername\> \Client\Auth\CredSSP** como false.
- Remove qualquer configuração WSMan/* da política **AllowFreshCredentials** do Windows CredSSP no cliente.

Se você especificar servidor, esse cmdlet executará a seguinte ação:

- Desabilita o CredSSP no servidor. Esse cmdlet define a configuração de WS-Management **\<localhost|computername\> \Service\Auth\CredSSP** como false.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Client, Server

Required: True
Position: 0
Default value: None
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
Este cmdlet não gera saída.

## OBSERVAÇÕES

* Para habilitar a autenticação CredSSP, utilize o cmdlet Enable-WSManCredSSP.

*

## LINKS RELACIONADOS

[Connect-WSMan](Connect-WSMan.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
