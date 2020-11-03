---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/07/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-verb?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 27434dfbc76d26724b34fe19fd143a7c52a14e90
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2020
ms.locfileid: "93195214"
---
# Get-Verb

## SINOPSE
Obtém os verbos aprovados do PowerShell.

## SYNTAX

```
Get-Verb [[-Verb] <String[]>] [[-Group] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

A `Get-Verb` função obtém verbos que são aprovados para uso em comandos do PowerShell.

É recomendável que os nomes de cmdlet e de função do PowerShell tenham o `Verb-Noun` formato e incluam um verbo aprovado. Essa prática torna os nomes de comando mais consistentes, previsíveis e fáceis de usar.

Comandos que usam verbos não aprovados, ainda são executados no PowerShell. No entanto, quando você importa um módulo que inclui um comando com um verbo não aprovado em seu nome, o `Import-Module` comando exibe uma mensagem de aviso.

> [!NOTE]
> A lista de verbos que `Get-Verb` retorna pode não estar concluída. Para obter uma lista atualizada de verbos aprovados do PowerShell com descrições, consulte [verbos aprovados](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) no Microsoft docs.

## Exemplos

### Exemplo 1-obter uma lista de todos os verbos

```powershell
Get-Verb
```

### Exemplo 2 – obter uma lista de verbos aprovados que começam com "un"

```powershell
Get-Verb un*
```

```Output
Verb       AliasPrefix Group     Description
----       ----------- -----     -----------
Undo       un          Common    Sets a resource to its previous state
Unlock     uk          Common    Releases a resource that was locked
Unpublish  ub          Data      Makes a resource unavailable to others
Uninstall  us          Lifecycle Removes a resource from an indicated location
Unregister ur          Lifecycle Removes the entry for a resource from a repository
Unblock    ul          Security  Removes restrictions to a resource
Unprotect  up          Security  Removes safeguards from a resource that were added to prevent it from attack or loss
```

### Exemplo 3-obter todos os verbos aprovados no grupo de segurança

```powershell
Get-Verb -Group Security
```

```Output
Verb      AliasPrefix Group    Description
----      ----------- -----    -----------
Block     bl          Security Restricts access to a resource
Grant     gr          Security Allows access to a resource
Protect   pt          Security Safeguards a resource from attack or loss
Revoke    rk          Security Specifies an action that does not allow access to a resource
Unblock   ul          Security Removes restrictions to a resource
Unprotect up          Security Removes safeguards from a resource that were added to prevent it from attack or loss
```

### Exemplo 4-localiza todos os comandos em um módulo que têm verbos não aprovados

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## PARAMETERS

### -Verbo

Obtém somente os verbos especificados. Digite o nome de um verbo ou um padrão de nome. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Common, Communications, Data, Diagnostic, Lifecycle, Other, Security

Required: False
Position: 1
Default value: All groups
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Grupo

Obtém somente os grupos especificados. Insira o nome de um grupo. Caracteres curinga não são permitidos.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All verbs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

## SAÍDAS

### System. Management. Automation. VerbInfo

## OBSERVAÇÕES

Os verbos do PowerShell são atribuídos a um grupo com base no uso mais comum. Os grupos são projetados para facilitar a localização e a comparação com o uso dos verbos, não para impedir seu uso. Você pode usar qualquer verbo aprovado para qualquer tipo de comando.

Cada verbo do PowerShell é atribuído a um dos grupos a seguir.

- Comum: defina ações genéricas que podem ser aplicadas a quase qualquer cmdlet, como adicionar.
- Comunicações: defina as ações que se aplicam a comunicações, como conectar.
- Dados: defina as ações que se aplicam à manipulação de dados, como backup.
- Diagnóstico: defina as ações que se aplicam ao diagnóstico, como depurar.
- Ciclo de vida: defina as ações que se aplicam ao ciclo de vida de um cmdlet, como concluído.
- Segurança: defina as ações que se aplicam à segurança, como REVOKE.
- Outro: defina outros tipos de ações.

Alguns dos cmdlets instalados com o PowerShell, como `Tee-Object` e `Where-Object` , usam verbos não aprovados. Esses cmdlets são exceções históricas e seus verbos são classificados como **reservados** .

## LINKS RELACIONADOS

[Import-Module](../microsoft.powershell.core/import-module.md)

