---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: 1c66cd3b1cc2fccc58cd75c367b41c445deb1e72
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598412"
---
# New-TemporaryFile

## SINOPSE
Cria um arquivo temporário.

## SYNTAX

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Esse cmdlet cria arquivos temporários que você pode usar em scripts.

O `New-TemporaryFile` cmdlet cria um arquivo vazio que tem a `.tmp` extensão de nome de arquivo.
Esse cmdlet nomeia o arquivo `tmp<NNNN>.tmp` , em que `<NNNN>` é um número hexadecimal aleatório.
O cmdlet cria o arquivo em sua pasta **temporária** .

Esse cmdlet usa o método [Path. GetTempPath ()](/dotnet/api/system.io.path.gettemppath) para localizar a pasta **Temp** . Esse método verifica a existência de variáveis de ambiente na seguinte ordem e usa o primeiro caminho encontrado:

- Em plataformas Windows:

  1. O caminho especificado pela variável de ambiente TMP.
  1. O caminho especificado pela variável de ambiente TEMP.
  1. O caminho especificado pela variável de ambiente USERPROFILE.
  1. O diretório do Windows.

- Em plataformas não Windows: usa o caminho especificado pela variável de ambiente TMPDIR.

## EXEMPLOS

### Exemplo 1: criar um arquivo temporário

```powershell
$TempFile = New-TemporaryFile
```

Esse comando gera um `.tmp` arquivo em sua pasta temporária e, em seguida, armazena uma referência para o arquivo na `$TempFile` variável. Você pode usar esse arquivo posteriormente em seu script.

## PARAMETERS

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

## SAÍDAS

### System. IO. FileInfo

Esse cmdlet retorna um objeto **FileInfo** que representa o arquivo temporário.

## OBSERVAÇÕES

## LINKS RELACIONADOS

