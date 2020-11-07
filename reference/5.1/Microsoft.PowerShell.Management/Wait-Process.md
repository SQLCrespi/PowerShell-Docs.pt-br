---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/wait-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Process
ms.openlocfilehash: 6fe942f98183a3b185adf5781699bf41d03db920
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343344"
---
# Wait-Process

## SINOPSE
Aguarda que os processos sejam interrompidos antes de aceitar mais entradas.

## SYNTAX

### Nome (padrão)

```
Wait-Process [-Name] <String[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### ID

```
Wait-Process [-Id] <Int32[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### InputObject

```
Wait-Process [[-Timeout] <Int32>] -InputObject <Process[]> [<CommonParameters>]
```

## DESCRIPTION

O `Wait-Process` cmdlet aguarda que um ou mais processos em execução sejam interrompidos antes de aceitar a entrada. No console do PowerShell, esse cmdlet suprime o prompt de comando até que os processos sejam interrompidos. Você pode especificar um processo por nome do processo ou ID do processo (PID) ou canalizar um objeto de processo para `Wait-Process` .

`Wait-Process` funciona somente em processos em execução no computador local.

## EXEMPLOS

### Exemplo 1: parar um processo e aguardar

```
PS C:\> $nid = (Get-Process notepad).id
PS C:\> Stop-Process -Id $nid
PS C:\> Wait-Process -Id $nid
```

Este exemplo interrompe o processo do bloco de notas e aguarda até que o processo seja interrompido antes de continuar com o próximo comando.

O primeiro comando usa o `Get-Process` cmdlet para obter a ID do processo do bloco de notas. Ele armazena a ID na `$nid` variável.

O segundo comando usa o `Stop-Process` cmdlet para interromper o processo com a ID armazenada em `$nid` .

O terceiro comando usa `Wait-Process` para aguardar até que o processo do bloco de notas seja interrompido. Ele usa o parâmetro **ID** de `Wait-Process` para identificar o processo.

### Exemplo 2: especificando um processo

```
PS C:\> $p = Get-Process notepad
PS C:\> Wait-Process -Id $p.id
PS C:\> Wait-Process -Name "notepad"
PS C:\> Wait-Process -InputObject $p
```

Esses comandos mostram três métodos diferentes de especificar um processo para o `Wait-Process` . O primeiro comando obtém o processo do bloco de notas e o armazena na `$p` variável.

O segundo comando usa o parâmetro **ID** , o terceiro comando usa o parâmetro **Name** e o quarto comando usa o parâmetro **InputObject** .

Esses comandos têm os mesmos resultados e podem ser usados alternadamente.

### Exemplo 3: aguardar processos por um tempo especificado

```
PS C:\> Wait-Process -Name outlook, winword -Timeout 30
```

Esse comando espera 30 segundos até que os processos do Outlook e do Winword sejam interrompidos. Se ambos os processos não forem interrompidos, o cmdlet exibirá um erro de não finalização e o prompt de comando.

## PARAMETERS

### -Id

Especifica as identificações de processos dos processos. Para especificar IDs múltiplas, use vírgulas para separá-las.
Para localizar o PID de um processo, digite `Get-Process` .

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Especifica os processos enviando objetos de processo. Insira uma variável que contenha os objetos de processo ou digite um comando ou uma expressão que obtenha os objetos de processo, como o `Get-Process` cmdlet.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Especifica os nomes de processo dos processos. Para especificar vários nomes, use vírgulas para separar os nomes. Não há suporte para caracteres curinga.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tempo limite

Especifica o tempo máximo, em segundos, que esse cmdlet aguarda a interrupção dos processos especificados.
Quando esse intervalo expira, o comando exibirá um erro de não finalização que lista os processos que estão em execução e termina a espera. Por padrão, não há tempo limite.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.Diagnostics.Process

É possível canalizar um objeto de processo para esse cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

Esse cmdlet usa o método **WaitForExit** da classe **System. Diagnostics. Process** .

## LINKS RELACIONADOS

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
