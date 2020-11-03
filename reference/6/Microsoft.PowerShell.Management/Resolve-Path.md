---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resolve-path?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resolve-Path
ms.openlocfilehash: 7e88e873c5c6aa0733869cdaaf1fba583468261d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193393"
---
# Resolve-Path

## SINOPSE
Resolve os caracteres curinga em um caminho e exibe o conteúdo do caminho.

## SYNTAX

### Caminho (padrão)

```
Resolve-Path [-Path] <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

### LiteralPath

```
Resolve-Path -LiteralPath <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

O `Resolve-Path` cmdlet exibe os itens e contêineres que correspondem ao padrão curinga no local especificado. A correspondência pode incluir arquivos, pastas, chaves do registro ou qualquer outro objeto acessível por meio de um provedor PSDrive.

## EXEMPLOS

### Exemplo 1: resolver o caminho da pasta base

O caractere de til (~) é uma notação abreviada para a pasta base do usuário atual. Este exemplo mostra `Resolve-Path` o retorno do valor de caminho totalmente qualificado.

```powershell
PS C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

### Exemplo 2: resolver o caminho da pasta do Windows

```powershell
PS C:\> Resolve-Path -Path "windows"
```

```Output
Path
----
C:\Windows
```

Quando executado da raiz da unidade C:, esse comando retorna o caminho da pasta do Windows na unidade C:.

### Exemplo 3: obter todos os caminhos na pasta do Windows

```powershell
PS C:\> "C:\windows\*" | Resolve-Path
```

Esse comando retorna todas as pastas na pasta C:\Windows. O comando usa um operador de pipeline (|) para enviar uma cadeia de caracteres de caminho para `Resolve-Path` .

### Exemplo 4: resolver um caminho UNC

```powershell
PS C:\> Resolve-Path -Path "\\Server01\public"
```

Esse comando resolve um caminho de convenção de nomenclatura Universal (UNC) e retorna os compartilhamentos no caminho.

### Exemplo 5: obter caminhos relativos

```powershell
PS C:\> Resolve-Path -Path "c:\prog*" -Relative
```

```Output
.\Program Files
.\Program Files (x86)
.\programs.txt
```

Esse comando retorna os caminhos relativos para os diretórios na raiz da unidade C:.

### Exemplo 6: resolver um caminho contendo colchetes

Este exemplo usa o parâmetro **LiteralPath** para resolver o caminho da \[ subpasta XML de teste \] .
O uso de **LiteralPath** faz com que os colchetes sejam tratados como caracteres normais em vez de uma expressão regular.

```powershell
PS C:\> Resolve-Path -LiteralPath 'test[xml]'
```

## PARAMETERS

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. O padrão é o usuário atual.

Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou passe um objeto **PSCredential** . Você pode criar um objeto **PSCredential** usando o `Get-Credential` cmdlet. Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.

Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralPath

Especifica os caminhos que serão resolvidos. O valor do parâmetro **LiteralPath** é usado exatamente como tipado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica o caminho do PowerShell a ser resolvido. Este parâmetro é necessário. Também é possível canalizar uma cadeia de caracteres de caminho para `Resolve-Path` . Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Relativo

Indica que esse cmdlet retorna um caminho relativo.

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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.

## SAÍDAS

### System. Management. Automation. PathInfo, System. String

Retorna um objeto **PathInfo** . Retorna um valor de cadeia de caracteres para o caminho resolvido se você especificar o parâmetro **relativo** .

## OBSERVAÇÕES

Os `*-Path` cmdlets funcionam com o sistema de arquivos, o registro e os provedores de certificado.

`Resolve-Path` o foi projetado para funcionar com qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` . Para obter mais informações, consulte [about_Providers](../microsoft.powershell.core/about/about_providers.md).

`Resolve-Path` resolve apenas os caminhos existentes. Ele não pode ser usado para resolver um local que ainda não existe.

## LINKS RELACIONADOS

[Convert-Path](Convert-Path.md)

[Join-Path](Join-Path.md)

[Split-Path](Split-Path.md)

[Test-Path](Test-Path.md)
