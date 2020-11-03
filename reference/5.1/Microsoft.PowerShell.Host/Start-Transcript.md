---
external help file: Microsoft.PowerShell.ConsoleHost.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/start-transcript?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transcript
ms.openlocfilehash: c7e95988c385a32802c93f92216710746d268e5e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193301"
---
# Start-Transcript

## SINOPSE
Cria um registro de toda ou parte de uma sessão do PowerShell para um arquivo de texto.

## SYNTAX

### ByPath (padrão)

```
Start-Transcript [[-Path] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Start-Transcript [[-LiteralPath] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByOutputDirectory

```
Start-Transcript [[-OutputDirectory] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Start-Transcript` cmdlet cria um registro de toda ou parte de uma sessão do PowerShell para um arquivo de texto. A transcrição inclui todo comando que o usuário digita e todos os valores de saída que aparecem no console.

A partir do Windows PowerShell 5,0, `Start-Transcript` inclui o nome do host no arquivo de todas as transcrições geradas. Isso é especialmente útil quando o registro em log da sua empresa é centralizado.
Os arquivos criados pelo `Start-Transcript` cmdlet incluem caracteres aleatórios em nomes para evitar possíveis substituições ou duplicação quando duas ou mais transcrições são iniciadas simultaneamente.
Isso também impede a descoberta não autorizada de transcrições armazenadas em um compartilhamento de arquivos centralizado.

## EXEMPLOS

### Exemplo 1: iniciar um arquivo de transcrição com as configurações padrão

```powershell
Start-Transcript
```

Este comando inicia uma transcrição no local de arquivo padrão.

### Exemplo 2: iniciar um arquivo de transcrição em um local específico

```powershell
Start-Transcript -Path "C:\transcripts\transcript0.txt" -NoClobber
```

Esse comando inicia uma transcrição no `Transcript0.txt` arquivo em `C:\transcripts` . Como o parâmetro **NoClobber** é usado, o comando impede que todos os arquivos existentes sejam substituídos. Se o `Transcript0.txt` arquivo já existir, o comando falhará.

## PARAMETERS

### -Acrescentar

Indica que esse cmdlet adiciona a nova transcrição ao final de um arquivo existente. Use o parâmetro **path** para especificar o arquivo.

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

### -Force

Permite que o cmdlet acrescente a transcrição a um arquivo somente leitura existente. Quando usado em um arquivo somente leitura, o cmdlet altera a permissão do arquivo para leitura e gravação. O cmdlet não pode substituir restrições de segurança quando esse parâmetro é usado.

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

### -IncludeInvocationHeader

Indica que esse cmdlet registra o carimbo de data/hora quando comandos são executados.

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

### -LiteralPath

Especifica um local para o arquivo de transcrição. Ao contrário do parâmetro **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. As aspas simples informam o PowerShell para não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber

Indica que esse cmdlet não substituirá um arquivo existente. Por padrão, se um arquivo de transcrição existir no caminho especificado, `Start-Transcript` o substituirá o arquivo sem aviso.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputDirectory

Especifica um caminho e uma pasta específicos para salvar uma transcrição. O PowerShell atribui automaticamente o nome da transcrição.

```yaml
Type: System.String
Parameter Sets: ByOutputDirectory
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica um local para o arquivo de transcrição. Insira um caminho para um `.txt` arquivo. Caracteres curinga não são permitidos.

Se você não especificar um caminho, o `Start-Transcript` usará o caminho no valor da `$Transcript` variável global. Se você não tiver criado essa variável, `Start-Transcript` o armazenará as transcrições nos `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` arquivos.

Se qualquer um dos diretórios no caminho não existir, o comando falhará.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### System.String

Esse cmdlet retorna uma cadeia de caracteres que contém uma mensagem de confirmação e o caminho para o arquivo de saída.

## OBSERVAÇÕES

Para interromper uma transcrição, use o `Stop-Transcript` cmdlet.

Para registrar uma sessão inteira, adicione o `Start-Transcript` comando ao seu perfil. Para obter mais informações, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

## LINKS RELACIONADOS

[Stop-Transcript](Stop-Transcript.md)
