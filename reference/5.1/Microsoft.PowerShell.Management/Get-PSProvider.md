---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 997d86460837946a2cf18fc78f058f21472dd909
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194166"
---
# Get-PSProvider

## SINOPSE
Obtém informações sobre o provedor do Windows PowerShell especificado.

## SYNTAX

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Get-PSProvider** Obtém os provedores do Windows PowerShell na sessão atual.
Você pode obter uma determinada unidade ou todas as unidades existentes na sessão.

Os provedores do Windows PowerShell permitem que você acesse uma variedade de fontes de dados, como se fossem unidades do sistema de arquivos.
Para obter informações sobre os provedores do Windows PowerShell, consulte about_Providers.

## EXEMPLOS

### Exemplo 1: exibir uma lista de todos os provedores disponíveis

```
PS C:\> Get-PSProvider
```

Este comando exibe uma lista de todos os provedores disponíveis do Windows PowerShell.

### Exemplo 2: exibir uma lista de todos os provedores do Windows PowerShell que começam com as letras especificadas

```
PS C:\> Get-PSProvider f*, r* | Format-List
```

Esse comando exibe uma lista de todos os provedores do Windows PowerShell com nomes que começam com a letra f ou r.

### Exemplo 3: localizar snap-ins ou um módulo que adicionou provedores à sua sessão

```
PS C:\> Get-PSProvider | Format-Table name, module, pssnapin -auto

Name        Module       PSSnapIn
----        ------       --------
Test        TestModule
WSMan                    Microsoft.WSMan.Management
Alias                    Microsoft.PowerShell.Core
Environment              Microsoft.PowerShell.Core
FileSystem               Microsoft.PowerShell.Core
Function                 Microsoft.PowerShell.Core
Registry                 Microsoft.PowerShell.Core
Variable                 Microsoft.PowerShell.Core
Certificate              Microsoft.PowerShell.Security

PS C:\> Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}

Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

Estes comandos encontram os módulos ou snap-ins do Windows PowerShell que adicionaram provedores à sua sessão.
Todos os elementos do Windows PowerShell, incluindo provedores, são originadas em um snap-in ou em um módulo.

Esses comandos usam as propriedades PSSnapin e Module do objeto **providerInfo** que o **Get-PSProvider** retorna.
Os valores dessas propriedades contêm o nome do snap-in ou módulo que adiciona o provedor.

O primeiro comando obtém todos os provedores existentes na sessão e formata-os em uma tabela com os valores de suas propriedades Name (nome), Module (módulo) e PSSnapin.

O segundo comando usa o cmdlet Where-Object para obter os provedores que vêm do snap-in **Microsoft. PowerShell. Security** .

### Exemplo 4: resolver o caminho da propriedade Home do provedor do sistema de arquivos

```
PS C:\> Resolve-Path ~

Path
----
C:\Users\User01

PS C:\> (get-psprovider FileSystem).home
C:\Users\User01
```

Este exemplo mostra que o símbolo de til (~) representa o valor da propriedade Home (início) do provedor FileSystem.
O valor da propriedade Home é opcional, mas para o provedor FileSystem, ele é definido como $env: HomeDrive \$ env: homepath ou $Home.

## PARAMETERS

### -PSProvider
Especifica o nome ou os nomes dos provedores do Windows PowerShell sobre os quais esse cmdlet obtém informações.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### String[]

É possível canalizar uma ou mais cadeias de caracteres de nome de provedor para este cmdlet.

## SAÍDAS

### System. Management. Automation. ProviderInfo
Esse cmdlet retorna objetos que representam os provedores do Windows PowerShell na sessão.

## OBSERVAÇÕES

## LINKS RELACIONADOS

## LINKS RELACIONADOS
