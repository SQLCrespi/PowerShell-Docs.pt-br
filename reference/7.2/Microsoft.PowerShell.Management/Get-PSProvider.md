---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 20820d2d194f41d43048c9617b63b9acb3fbb4f8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595575"
---
# Get-PSProvider

## SINOPSE
Obtém informações sobre o provedor do PowerShell especificado.

## SYNTAX

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-PSProvider` cmdlet obtém os provedores do PowerShell na sessão atual.
Você pode obter uma determinada unidade ou todas as unidades existentes na sessão.

Os provedores do PowerShell permitem acessar uma variedade de armazenamentos de dados como se fossem unidades do sistema de arquivos.
Para obter informações sobre provedores do PowerShell, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## EXEMPLOS

### Exemplo 1: exibir uma lista de todos os provedores disponíveis

```powershell
Get-PSProvider
```

Este comando exibe uma lista de todos os provedores do PowerShell disponíveis.

### Exemplo 2: exibir uma lista de todos os provedores do PowerShell que começam com as letras especificadas

```powershell
Get-PSProvider f*, r* | Format-List
```

Esse comando exibe uma lista de todos os provedores do PowerShell com nomes que começam com a letra f ou r.

### Exemplo 3: localizar snap-ins ou um módulo que adicionou provedores à sua sessão

```powershell
Get-PSProvider | Format-Table name, module, pssnapin -auto
```

```Output
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
```

```powershell
Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}
```

```Output
Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

Esses comandos localizam os snap-ins ou módulos do PowerShell que adicionaram provedores à sua sessão.
Todos os elementos do PowerShell, incluindo provedores, se originam em um snap-in ou em um módulo.

Esses comandos usam as propriedades PSSnapin e Module do objeto **providerInfo** que `Get-PSProvider` retorna.
Os valores dessas propriedades contêm o nome do snap-in ou módulo que adiciona o provedor.

O primeiro comando obtém todos os provedores existentes na sessão e formata-os em uma tabela com os valores de suas propriedades Name (nome), Module (módulo) e PSSnapin.

O segundo comando usa o `Where-Object` cmdlet para obter os provedores que vêm do snap-in **Microsoft. PowerShell. Security** .

### Exemplo 4: resolver o caminho da propriedade Home do provedor do sistema de arquivos

```powershell
C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

```powershell
PS C:\> (get-psprovider FileSystem).home
```

```Output
C:\Users\User01
```

Este exemplo mostra que o símbolo de til (~) representa o valor da propriedade **Home** do provedor FileSystem.
O valor da propriedade **Home** é opcional, mas para o provedor **FileSystem** , ele é definido como `$env:homedrive\$env:homepath` ou `$home` .

## PARAMETERS

### -PSProvider

Especifica o nome ou os nomes dos provedores do PowerShell sobre os quais esse cmdlet obtém informações.

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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### String[]

É possível canalizar uma ou mais cadeias de caracteres de nome de provedor para este cmdlet.

## SAÍDAS

### System. Management. Automation. ProviderInfo

Esse cmdlet retorna objetos que representam os provedores do PowerShell na sessão.

## OBSERVAÇÕES

## LINKS RELACIONADOS

