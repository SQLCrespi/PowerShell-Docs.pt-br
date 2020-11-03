---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/convert-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-Path
ms.openlocfilehash: a442d8ff9f021e1ec05671d9190d35ef97ff4d72
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194202"
---
# Convert-Path

## SINOPSE
Converte um caminho de um caminho do PowerShell para um caminho de provedor do PowerShell.

## SYNTAX

### Caminho (padrão)

```
Convert-Path [-Path] <String[]> [-UseTransaction] [<CommonParameters>]
```

### LiteralPath

```
Convert-Path -LiteralPath <String[]> [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

O `Convert-Path` cmdlet converte um caminho de um caminho do PowerShell para um caminho de provedor do PowerShell.

## EXEMPLOS

### Exemplo 1: converter o diretório de trabalho em um caminho de sistema de arquivos padrão

Este exemplo converte o diretório de trabalho atual, que é representado por um ponto ( `.` ), em um caminho de sistema de arquivos padrão.

```
PS C:\> Convert-Path .
C:\
```

### Exemplo 2: converter um caminho de provedor para um caminho de registro padrão

Este exemplo converte o caminho do provedor do PowerShell em um caminho de registro padrão.

```powershell
PS C:\> Convert-Path HKLM:\Software\Microsoft
HKEY_LOCAL_MACHINE\Software\Microsoft
```

### Exemplo 3: converter um caminho para uma cadeia de caracteres

Este exemplo converte o caminho para o diretório base do provedor atual, que é o provedor FileSystem, para uma cadeia de caracteres.

```powershell
PS C:\> Convert-Path ~
C:\Users\User01
```

## PARAMETERS

### -LiteralPath

Especifica, como uma matriz de cadeia de caracteres, o caminho a ser convertido. O valor do parâmetro **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica o caminho do PowerShell a ser convertido.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UseTransaction
Inclui o comando na transação ativa.
Este parâmetro é válido somente quando uma transação está em andamento.
Para obter mais informações, consulte about_transactions.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar um caminho, mas não um caminho literal, para esse cmdlet.

## SAÍDAS

### System.String

Esse cmdlet retorna uma cadeia de caracteres que contém o caminho convertido.

## OBSERVAÇÕES

Os cmdlets que contêm o caminho substantivo manipulam nomes de caminho e retornam os nomes em um formato conciso que todos os provedores do PowerShell podem interpretar. Eles foram projetados para uso em programas e scripts onde você deseja exibir uma parte ou todo um nome de caminho em um formato específico. Use-os como você usaria **dirname** , **Normpath** , **realpath** , **Join** ou outros manipuladores de caminho.

Você pode usar os cmdlets Path com vários provedores, incluindo os provedores de sistema de arquivos, registro e certificado.

Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

`Convert-Path` converte apenas os caminhos existentes. Ele não pode ser usado para converter um local que ainda não existe.

## LINKS RELACIONADOS

[Join-Path](Join-Path.md)

[Resolve-Path](Resolve-Path.md)

[Split-Path](Split-Path.md)

[Test-Path](Test-Path.md)

[Get-PSProvider](Get-PSProvider.md)
