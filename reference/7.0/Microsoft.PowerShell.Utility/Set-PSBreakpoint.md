---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-psbreakpoint?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSBreakpoint
ms.openlocfilehash: ee2229866bdbee530230fbd5cf04ae362722bf2f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192793"
---
# Set-PSBreakpoint

## SINOPSE
Define um ponto de interrupção em uma linha, um comando ou uma variável.

## SYNTAX

### Linha (padrão)

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Column] <Int32>] [-Line] <Int32[]> [-Script] <String[]>
 [<CommonParameters>]
```

### Comando

```
Set-PSBreakpoint [-Action <ScriptBlock>] -Command <String[]> [[-Script] <String[]>] [<CommonParameters>]
```

### Variável

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Script] <String[]>] -Variable <String[]>
 [-Mode <VariableAccessMode>] [<CommonParameters>]
```

## DESCRIPTION

O `Set-PSBreakpoint` cmdlet define um ponto de interrupção em um script ou em qualquer comando executado na sessão atual. Você pode usar `Set-PSBreakpoint` para definir um ponto de interrupção antes de executar um script ou executar um comando, ou durante a depuração, quando interrompido em outro ponto de interrupção.

`Set-PSBreakpoint` Não é possível definir um ponto de interrupção em um computador remoto. Para depurar um script em um computador remoto, copie o script para o computador local e o depure localmente.

Cada `Set-PSBreakpoint` comando cria um dos três tipos de pontos de interrupção a seguir:

- Ponto de interrupção de linha – define os pontos de interrupção em coordenadas de linha e coluna específicas.
- Ponto de interrupção do comando – define pontos de interrupção em comandos e funções.
- Ponto de interrupção da variável – define pontos de interrupção em variáveis.

Você pode definir um ponto de interrupção em várias linhas, comandos ou variáveis em um único `Set-PSBreakpoint` comando, mas cada `Set-PSBreakpoint` comando define apenas um tipo de ponto de interrupção.

Em um ponto de interrupção, o PowerShell interrompe temporariamente a execução e dá controle ao depurador. O prompt de comando muda para `DBG\>` e um conjunto de comandos do depurador se torna disponível para uso. No entanto, você pode usar o parâmetro **Action** para especificar uma resposta alternativa, como condições para o ponto de interrupção ou instruções para executar tarefas adicionais, como log ou diagnóstico.

O `Set-PSBreakpoint` cmdlet é um dos vários cmdlets projetados para depurar scripts do PowerShell.
Para obter mais informações sobre o depurador do PowerShell, consulte [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).

## EXEMPLOS

### Exemplo 1: definir um ponto de interrupção em uma linha

Este exemplo define um ponto de interrupção na linha 5 no script Sample.ps1. Quando o script é executado, a execução é interrompida imediatamente antes que a linha 5 seja executada.

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Line 5
```

```output
Column     : 0
Line       : 5
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

Quando você define um novo ponto de interrupção por número de linha, o `Set-PSBreakpoint` cmdlet gera um objeto de ponto de interrupção de linha ( **System. Management. Automation. LineBreakpoint** ) que inclui a ID de ponto de interrupção e a contagem de acesso.

### Exemplo 2: definir um ponto de interrupção em uma função

Este exemplo cria um ponto de interrupção de comando na `Increment` função no cmdlet Sample.ps1. O script para de executar imediatamente antes de cada chamada para a função especificada.

```powershell
Set-PSBreakpoint -Command "Increment" -Script "sample.ps1"
```

```Output
Command    : Increment
Action     :
Enabled    : True
HitCount   : 0
Id         : 1
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

O resultado é um objeto de ponto de interrupção do comando. Antes de o script ser executado, o valor da propriedade **contagem** é 0.

### Exemplo 3: definir um ponto de interrupção em uma variável

Este exemplo define um ponto de interrupção na variável de **servidor** no script Sample.ps1. Ele usa o parâmetro **Mode** com um valor de **ReadWrite** para interromper a execução quando o valor da variável é lido e pouco antes de o valor ser alterado.

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Variable "Server" -Mode ReadWrite
```

### Exemplo 4: definir um ponto de interrupção em cada comando que começa com o texto especificado

Este exemplo define um ponto de interrupção em cada comando no script de Sample.ps1 que começa com "Write", como `Write-Host` .

```powershell
Set-PSBreakpoint -Script Sample.ps1 -Command "write*"
```

### Exemplo 5: definir um ponto de interrupção dependendo do valor de uma variável

Este exemplo interrompe a execução na `DiskTest` função no script Test.ps1 somente quando o valor da `$Disk` variável é maior que 2.

```powershell
Set-PSBreakpoint -Script "test.ps1" -Command "DiskTest" -Action { if ($Disk -gt 2) { break } }
```

O valor da **ação** é um bloco de script que testa o valor da `$Disk` variável na função.

A ação usará a `break` palavra-chave para interromper a execução se a condição for atendida. A alternativa (e o padrão) é **continuar** .

### Exemplo 6: definir um ponto de interrupção em uma função

Este exemplo define um ponto de interrupção na `CheckLog` função. Como o comando não especifica um script, o ponto de interrupção é definido em qualquer coisa que seja executada na sessão atual. O depurador interrompe quando a função é chamada, não quando é declarada.

```
PS> Set-PSBreakpoint -Command "checklog"
Id       : 0
Command  : checklog
Enabled  : True
HitCount : 0
Action   :

function CheckLog {
>> get-eventlog -log Application |
>> where {($_.source -like "TestApp") -and ($_.Message -like "*failed*")}
>>}
>>
PS> Checklog
DEBUG: Hit breakpoint(s)
DEBUG:  Function breakpoint on 'prompt:Checklog'
```

### Exemplo 7: definir pontos de interrupção em várias linhas

Este exemplo define três pontos de interrupção de linha no script de Sample.ps1. Ele define um ponto de interrupção na coluna 2 para cada uma das linhas especificada no script. A ação especificada no parâmetro **Action** aplica-se a todos os pontos de interrupção.

```powershell
PS C:\> Set-PSBreakpoint -Script "sample.ps1" -Line 1, 14, 19 -Column 2 -Action {&(log.ps1)}
```

```Output
Column     : 2
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 6
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 14
Action     :
Enabled    : True
HitCount   : 0
Id         : 7
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 19
Action     :
Enabled    : True
HitCount   : 0
Id         : 8
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

## PARAMETERS

### -Action

Especifica comandos que são executados em cada ponto de interrupção em vez de interromper. Insira um bloco de script que contenha os comandos. Você pode usar esse parâmetro para definir pontos de interrupção condicionais ou realizar outras tarefas, como teste ou registro em log.

Se este parâmetro é omitido, ou nenhuma ação é especificada, a execução para no ponto de interrupção e o depurador é iniciado.

Quando o parâmetro **Action** é usado, o bloco de script Action é executado em cada ponto de interrupção. A execução não é interrompida a menos que o bloco de script inclua a palavra-chave Break. Se você usar a palavra-chave Continue no bloco de script, a execução continua até o próximo ponto de interrupção.

Para obter mais informações, consulte [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md)e [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Coluna

Especifica o número de coluna da coluna no arquivo de script em que a execução é interrompida. Insira apenas um número de coluna. O padrão é a coluna 1.

O valor da coluna é usado com o valor do parâmetro **line** para especificar o ponto de interrupção. Se o parâmetro de **linha** especificar várias linhas, o parâmetro de **coluna** definirá um ponto de interrupção na coluna especificada em cada uma das linhas especificadas. O PowerShell para de executar antes da instrução ou expressão que inclui o caractere na linha especificada e na posição da coluna.

Colunas são contadas a partir da margem superior esquerda começando pela coluna número 1 (não a 0). Se especificar uma coluna que não existe no script, um erro não é declarado, mas o ponto de interrupção não é executado.

```yaml
Type: System.Int32
Parameter Sets: Line
Aliases:

Required: False
Position: 2
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -Command

Define um ponto de interrupção do comando. Insira nomes de cmdlet, como `Get-Process` ou nomes de função. Caracteres curinga são permitidos.

A execução para antes que cada instância de cada comando seja executada. Se o comando for uma função, a execução é interrompida toda vez que a função é chamada e a cada seção BEGIN, PROCESS e END.

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases: C

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Linha

Define um ponto de interrupção em um script. Insira um ou mais números de linha, separados por vírgulas. O PowerShell para imediatamente antes de executar a instrução que começa em cada uma das linhas especificadas.

Linhas são contadas a partir da margem superior esquerda do arquivo de script começando pela linha número 1 (não a 0).
Se especificar uma linha em branco, a execução para antes da próxima linha que não estiver em branco. Se a linha está fora do intervalo, o ponto de interrupção nunca é atingido.

```yaml
Type: System.Int32[]
Parameter Sets: Line
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode

Especifica o modo de acesso que dispara pontos de interrupção de variável. O padrão é **gravação** .

Esse parâmetro é válido somente quando o parâmetro **Variable** é usado no comando. O modo se aplica a todos os pontos de interrupção definidos no comando. Os valores aceitáveis para esse parâmetro são:

- **Write** -interrompe a execução imediatamente antes que um novo valor seja gravado na variável.
- **Read** -interrompe a execução quando a variável é lida, ou seja, quando seu valor é acessado, seja para ser atribuído, exibido ou usado. No modo de leitura, a execução não é interrompida quando o valor da variável é alterado.
- **ReadWrite** – interrompe a execução quando a variável é lida ou gravada.

```yaml
Type: System.Management.Automation.VariableAccessMode
Parameter Sets: Variable
Aliases:
Accepted values: Read, Write, ReadWrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Script

Especifica uma matriz de arquivos de script em que este cmdlet define um ponto de interrupção. Insira os caminhos e nomes de arquivo de um ou mais arquivos de script. Se os arquivos estão no diretório atual, você pode omitir o caminho.
Caracteres curinga são permitidos.

Por padrão, os pontos de interrupção variáveis e os pontos de interrupção de comando são definidos em qualquer comando executado na sessão atual. Esse parâmetro é necessário somente ao definir um ponto de interrupção de linha.

```yaml
Type: System.String[]
Parameter Sets: Line, Command, Variable
Aliases:

Required: True (Line), False (Command, Variable)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Variable

Especifica uma matriz de variáveis em que este cmdlet define os pontos de interrupção. Insira uma lista separada por vírgulas de variáveis sem sinais de dólar ( `$` ).

Use o parâmetro **Mode** para determinar o modo de acesso que dispara os pontos de interrupção. O modo padrão, Write, para a execução imediatamente antes de um novo valor ser gravado na variável.

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases: V

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível canalizar a entrada para `Set-PSBreakpoint` .

## SAÍDAS

### Objeto de ponto de interrupção (System. Management. Automation. LineBreakpoint, System. Management. Automation. VariableBreakpoint, System. Management. Automation. CommandBreakpoint)

`Set-PSBreakpoint` Retorna um objeto que representa cada ponto de interrupção que ele define.

## OBSERVAÇÕES

- `Set-PSBreakpoint` Não é possível definir um ponto de interrupção em um computador remoto. Para depurar um script em um computador remoto, copie o script para o computador local e o depure localmente.
- Quando você define um ponto de interrupção em mais de uma linha, comando ou variável, `Set-PSBreakpoint` o gera um objeto de ponto de interrupção para cada entrada.
- Ao definir um ponto de interrupção em uma função ou variável no prompt de comando, você pode definir o ponto de interrupção antes ou depois de criar uma função ou variável.

## LINKS RELACIONADOS

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)
