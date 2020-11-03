---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disconnect-wsman?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-WSMan
ms.openlocfilehash: a754b6530ecd8b3153d82327a246cbb387d53dd5
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193024"
---
# Disconnect-WSMan

## SINOPSE
Desconecta o cliente do serviço WinRM em um computador remoto.

## SYNTAX

```
Disconnect-WSMan [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Disconnect-WSMan** desconecta o cliente do serviço WinRM em um computador remoto.
Se você salvou a sessão de WS-Management em uma variável, o objeto de sessão permanecerá na variável, mas o estado da sessão de WS-Management será fechado.
Você pode usar este cmdlet dentro do contexto do provedor WSMan para desconectar o cliente do serviço WinRM em um computador remoto.
No entanto, você também pode usar este cmdlet para desconectar o serviço do WinRM em computadores remotos antes de alterar para o provedor WSMan.

Para obter mais informações sobre como se conectar ao serviço WinRM em um computador remoto, consulte Connect-WSMan.

## EXEMPLOS

### Exemplo 1: excluir uma conexão com um computador remoto

```
PS C:\> Disconnect-WSMan -computer server01
PS C:\> cd WSMan:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
```

Esse comando exclui a conexão com o computador remoto chamado Server01.

Este cmdlet geralmente é usado dentro do contexto do provedor WSMan para se desconectar de um computador remoto, neste caso, o computador server01.
No entanto, você também pode usar **Disconnect-WSMan** para remover conexões a computadores remotos antes de alterar para o provedor WSMan.
Essas conexões não aparecem na lista ComputerName.

## PARAMETERS

### -ComputerName
Especifica o computador no qual executar a operação de gerenciamento.
O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.
Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.
O computador local é o padrão.
Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.
É possível redirecionar um valor desse parâmetro para o cmdlet.

Não é possível desconectar do host local.
Ou seja, não é possível desconectar a conexão padrão ao computador local.
No entanto, se você criar uma conexão separada com o computador local, por exemplo, usando o nome do computador.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
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

## LINKS RELACIONADOS

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

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
