---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 03/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-experimentalfeature?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ExperimentalFeature
ms.openlocfilehash: 3260b3d8333e8a79fdf603c372d1e3e50aa0dabc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194778"
---
# Disable-ExperimentalFeature

## SINOPSE
Desabilite um recurso experimental na inicialização da nova instância do PowerShell.

## SYNTAX

```
Disable-ExperimentalFeature [-Name] <String[]> [-Scope <ConfigScope>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Disable-ExperimentalFeature` cmdlet desabilita os recursos experimentais removendo os recursos experimentais nomeados do `powershell.config.json` arquivo de configurações ler na inicialização do PowerShell.

Esse cmdlet foi introduzido no PowerShell 6,2.

> [!NOTE]
> Todas as alterações no estado do recurso experimental só entrarão em vigor na reinicialização do PowerShell

## EXEMPLOS

### Exemplo 1: desabilitar um recurso experimental

Neste exemplo, se esse recurso experimental tiver sido habilitado anteriormente, o `powershell.config.json` arquivo será atualizado para que o usuário não habilite esse recurso depois que o PowerShell for reiniciado.
Após o êxito, nada é apresentado para o pipeline e apenas uma mensagem de aviso é exibida.

```powershell
PS C:\> Disable-ExperimentalFeature PSImplicitRemotingBatching
```

```Output
WARNING: Enabling and disabling experimental features do not take effect until next start of PowerShell.
```

## PARAMETERS

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

O nome ou os nomes dos recursos experimentais a serem desabilitados.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Escopo

Determina qual `powershell.config.json` atualizar se ele afeta todos os usuários ou apenas o usuário atual.

```yaml
Type: System.Management.Automation.Configuration.ConfigScope
Parameter Sets: (All)
Aliases:
Accepted values: AllUsers, CurrentUser

Required: False
Position: Named
Default value: CurrentUser
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### ExperimentalFeature

Instâncias de pipe de ExperimentalFeature do `Get-ExperimentalFeature` cmdlet a ser desabilitado.

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

As alterações no estado de um recurso experimental só entram em vigor na reinicialização do PowerShell.

## LINKS RELACIONADOS

[Enable-ExperimentalFeature](Enable-ExperimentalFeature.md)

[Get-ExperimentalFeature](Get-ExperimentalFeature.md)

