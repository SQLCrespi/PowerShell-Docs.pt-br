---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSnapin
ms.openlocfilehash: 156cadecd87910e3c3312e84929b16709770641d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388664"
---
# Get-PSSnapin

## SINOPSE
Obtém os snap-ins do Windows PowerShell presentes no computador.

## SYNTAX

```
Get-PSSnapin [[-Name] <String[]>] [-Registered] [<CommonParameters>]
```

## DESCRIPTION

O `Get-PSSnapin` cmdlet obtém os snap-ins do Windows PowerShell que foram adicionados à sessão atual ou que foram registrados no sistema. Esse cmdlet lista os snap-ins na ordem em que são detectados.

`Get-PSSnapin` Obtém apenas snap-ins registrados. Para registrar um snap-in do Windows PowerShell, use a ferramenta InstallUtil incluída com o Microsoft .NET Framework 2,0. Para obter mais informações, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).

A partir do Windows PowerShell 3,0, os comandos principais incluídos no Windows PowerShell são empacotados em módulos. A exceção é o **Microsoft.PowerShell.Core** , que é um snap-in (PSSnapin).
Por padrão, somente o snap-in **Microsoft.PowerShell.Core** é adicionado à sessão. Os módulos são importados automaticamente no primeiro uso e você pode usar o `Import-Module` cmdlet para importá-los.

## EXEMPLOS

### Exemplo 1: obter snap-ins que estão carregados no momento

```
PS C:\> Get-PSSnapIn
```

Esse comando obtém os snap-ins do Windows PowerShell que estão atualmente carregados na sessão. Isso inclui os snap-ins instalados com o Windows PowerShell e aqueles que foram adicionados à sessão.

### Exemplo 2: obter snap-ins que foram registrados

```
PS C:\> get-PSSnapIn -Registered
```

Esse comando obtém os snap-ins do Windows PowerShell que foram registrados no computador, incluindo aqueles que já foram adicionados à sessão. A saída não inclui snap-ins que são instalados com o Windows PowerShell ou do snap-ins de bibliotecas de vínculo dinâmico (DLLs) do Windows PowerShell que ainda não foram registrados no sistema.

### Exemplo 3: obter snap-ins atuais que correspondem a uma cadeia de caracteres

```
PS C:\> Get-PSSnapIn -Name smp*
```

Esse comando obtém os snap-ins do Windows PowerShell na sessão atual que têm nomes que começam com SMP.

## PARAMETERS

### -Name

Especifica uma matriz de nomes de snap-in. Esse cmdlet obtém apenas os snap-ins do Windows PowerShell especificados. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Registrado

Indica que esse cmdlet obtém os snap-ins do Windows PowerShell que foram registrados no sistema, mesmo que ainda não tenham sido adicionados à sessão.

Os snap-ins instalados com o Windows PowerShell não aparecem nessa lista.

Sem esse parâmetro, `Get-PSSnapin` o Obtém os snap-ins do Windows PowerShell que foram adicionados à sessão.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Management. Automation. PSSnapInInfo

`Get-PSSnapin` Retorna um objeto para cada snap-in que obtém.

## OBSERVAÇÕES

A partir do Windows PowerShell 3,0, os comandos principais instalados com o Windows PowerShell são empacotados em módulos. No Windows PowerShell 2,0 e em programas de host que criam sessões de estilo mais antigo em versões posteriores do Windows PowerShell, os comandos principais são empacotados em snap-ins ( **PSSnapin** ). A exceção é **Microsoft. PowerShell. Core** , que sempre é um snap-in. Além disso, as sessões remotas, como as iniciadas pelo `New-PSSession` cmdlet, são sessões de estilo mais antigo que incluem snap-ins de núcleo.

 Para obter informações sobre o método **CreateDefault2** que cria sessões de estilo mais recente com módulos principais, consulte [método CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2#System_Management_Automation_Runspaces_InitialSessionState_CreateDefault2).

## LINKS RELACIONADOS

[Add-PSSnapin](Add-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
