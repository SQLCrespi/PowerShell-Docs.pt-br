---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
ms.date: 09/07/2018
Module Name: Microsoft.PowerShell.Core
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/functions/get-verb?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 4474bb50c2bf3be10e72d2554190208e956f9040
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2020
ms.locfileid: "93195208"
---
# Get-Verb

## SINOPSE
Obtém os verbos aprovados do PowerShell.

## SYNTAX

```
Get-Verb [[-verb] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

A `Get-Verb` função obtém verbos que são aprovados para uso em comandos do PowerShell.

O PowerShell recomenda que os nomes de cmdlet e de função tenham o formato Verb-Noun e incluam um verbo aprovado. Essa prática torna os nomes de comando mais consistentes, previsíveis e fáceis de usar.

Comandos que usam verbos não aprovados são executados no PowerShell. No entanto, quando você importa um módulo que inclui um comando com um verbo não aprovado em seu nome, o `Import-Module` comando exibe uma mensagem de aviso.

> [!NOTE]
> A lista de verbos que `Get-Verb` retorna pode não estar concluída. Para obter uma lista atualizada de verbos aprovados do PowerShell com descrições, consulte [verbos aprovados](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) no Microsoft docs.

## EXEMPLOS

### Exemplo 1-obter uma lista de todos os verbos

```powershell
Get-Verb
```

### Exemplo 2 – obter uma lista de verbos aprovados que começam com "un"

```powershell
Get-Verb un*
```

```Output
Verb                 Group
----                 -----
Undo                 Common
Unlock               Common
Unpublish            Data
Uninstall            Lifecycle
Unregister           Lifecycle
Unblock              Security
Unprotect            Security
```

### Exemplo 3-obter todos os verbos aprovados no grupo de segurança

```powershell
Get-Verb | Where-Object Group -EQ Security
```

```Output
Verb      Group
----      -----
Block     Security
Grant     Security
Protect   Security
Revoke    Security
Unblock   Security
Unprotect Security
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

### -verbo

Obtém somente os verbos especificados.
Digite o nome de um verbo ou um padrão de nome.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: All verbs
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## ENTRADAS

### Nenhum

## SAÍDAS

### Selected.Microsoft.PowerShell.Commands.MemberDefinition

## OBSERVAÇÕES

`Get-Verb` Retorna uma versão modificada de um objeto Microsoft. PowerShell. Commands. MemberDefinition.
O objeto não tem as propriedades padrão de um objeto MemberDefinition. Em vez disso, ela tem propriedades Verbo e Grupo. A propriedade Verbo contém uma cadeia de caracteres com o nome do verbo. A propriedade Grupo contém uma cadeia de caracteres com o grupo do verbo.

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

[Import-Module](import-module.md)
