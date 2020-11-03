---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-host?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Host
ms.openlocfilehash: f0b7542d551fa0dbbdec186980dcdb7ac600b60c
ms.sourcegitcommit: 758e6dbb428295698d4852b3e19f5d03deade037
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "93195318"
---
# Write-Host

## SINOPSE

Grava a saída personalizada em um host.

## SYNTAX

```
Write-Host [[-Object] <Object>] [-NoNewline] [-Separator <Object>] [-ForegroundColor <ConsoleColor>]
 [-BackgroundColor <ConsoleColor>] [<CommonParameters>]
```

## DESCRIPTION

A `Write-Host` principal finalidade do cmdlet é produzir uma saída de-(host)-somente exibição, como a impressão de texto colorido, como ao solicitar a entrada do usuário em conjunto com o [Read-Host](Read-Host.md).
`Write-Host` usa o método [ToString ()](/dotnet/api/system.object.tostring) para gravar a saída. Por outro lado, para gerar dados de saída para o pipeline, use [Write-Output](Write-Output.md) ou saída implícita.

Você pode especificar a cor do texto usando o `ForegroundColor` parâmetro e pode especificar a cor do plano de fundo usando o `BackgroundColor` parâmetro. O parâmetro separador permite que você especifique uma cadeia de caracteres a ser usada para separar os objetos exibidos. O resultado específico depende do programa que está hospedando o PowerShell.

> [!NOTE]
> A partir do Windows PowerShell 5,0, `Write-Host` é um wrapper para `Write-Information` isso permite que você use `Write-Host` para emitir a saída para o fluxo de informações. Isso permite a **captura** ou **supressão** de dados gravados usando `Write-Host` enquanto preserva a compatibilidade com versões anteriores.
>
> A `$InformationPreference` variável de preferência e o `InformationAction` parâmetro comum não afetam `Write-Host` as mensagens. A exceção a essa regra é `-InformationAction Ignore` , que suprime efetivamente a `Write-Host` saída. (consulte o "exemplo 5")

## EXEMPLOS

### Exemplo 1: gravar no console sem adicionar uma nova linha

```powershell
Write-Host "no newline test " -NoNewline
Write-Host "second string"
```

```output
no newline test second string
```

Este comando exibe a cadeia de caracteres "nenhum teste de nova linha" com o `NoNewline` parâmetro.

Uma segunda cadeia de caracteres é gravada, mas termina na mesma linha que a primeira, devido à ausência de uma linhagem separando as cadeias de caracteres.

### Exemplo 2: gravar no console e incluir um separador

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", +2= "
```

```output
2, +2= 4, +2= 6, +2= 8, +2= 10, +2= 12
```

Esse comando exibe os números pares de dois a doze. O parâmetro **Separator** é usado para adicionar a cadeia de caracteres `, +2= ` (vírgula, espaço,,, `+` `2` `=` , espaço).

### Exemplo 3: escrever com cores de texto e de plano de fundo diferentes

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", -> " -ForegroundColor DarkGreen -BackgroundColor White
```

```output
2, -> 4, -> 6, -> 8, -> 10, -> 12
```

Esse comando exibe os números pares de dois a doze. Ele usa o `ForegroundColor` parâmetro para gerar texto verde escuro e o `BackgroundColor` parâmetro para exibir um plano de fundo branco.

### Exemplo 4: escrever com cores de texto e de plano de fundo diferentes

```powershell
Write-Host "Red on white text." -ForegroundColor red -BackgroundColor white
```

```output
Red on white text.
```

Este comando exibe a cadeia de caracteres "Texto vermelho sobre branco". O texto é vermelho, conforme definido pelo `ForegroundColor` parâmetro. O plano de fundo é branco, conforme definido pelo `BackgroundColor` parâmetro.

### Exemplo 5: suprimir a saída de Write-Host

```powershell
# The following two statements can be used to effectively suppress output from Write-Host
Write-Host "I won't print" -InformationAction Ignore
Write-Host "I won't print" 6>$null
```

```output

```

Esses comandos suprimim efetivamente a saída do `Write-Host` cmdlet. A primeira usa o `InformationAction` parâmetro com o `Ignore` valor para suprimir a saída para o fluxo de informações.
O segundo exemplo redireciona o fluxo de informações do comando para a `$null` variável e, portanto, a suprime.

## PARAMETERS

### -BackgroundColor

Especifica a cor do plano de fundo. Não há nenhum padrão. Os valores aceitáveis para esse parâmetro são:

- Preto
- DarkBlue
- DarkGreen
- DarkCyan
- DarkRed
- DarkMagenta
- DarkYellow
- Cinza
- DarkGray
- Azul
- Verde
- Cores
- Vermelho
- Magenta
- Amarelo
- Branco

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForegroundColor

Especifica a cor do texto. Não há nenhum padrão. Os valores aceitáveis para esse parâmetro são:

- Preto
- DarkBlue
- DarkGreen
- DarkCyan
- DarkRed
- DarkMagenta
- DarkYellow
- Cinza
- DarkGray
- Azul
- Verde
- Cores
- Vermelho
- Magenta
- Amarelo
- Branco

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nonovat

As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída. Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída. Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.

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

### -Objeto

Objetos a serem exibidos no host.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg, Message

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Separador

Especifica uma cadeia de caracteres separadora a ser inserida entre os objetos exibidos pelo host.

```yaml
Type: System.Object
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

### System.Object

É possível redirecionar objetos a serem gravados no host.

## SAÍDAS

### Nenhum

`Write-Host` envia os objetos para o host. Ele não retorna nenhum objeto. No entanto, o host exibe os objetos que `Write-Host` enviam a ele.

## OBSERVAÇÕES

- Ao gravar uma coleção no host, os elementos da coleção são impressos na mesma linha separada por um único espaço. Isso pode ser substituído pelo parâmetro **Separator** .

- Tipos de dados não primitivos, como objetos com propriedades, podem causar resultados inesperados e não fornecem uma saída significativa. Por exemplo, `Write-Host @{a = 1; b = 2}` será impresso no `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` host.

## LINKS RELACIONADOS

[Clear-Host](../Microsoft.PowerShell.Core/Clear-Host.md)

[Out-Host](../Microsoft.PowerShell.Core/Out-Host.md)

[Write-Debug](Write-Debug.md)

[Erro de gravação](Write-Error.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
