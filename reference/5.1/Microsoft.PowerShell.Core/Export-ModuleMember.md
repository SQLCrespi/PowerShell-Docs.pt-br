---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-modulemember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ModuleMember
ms.openlocfilehash: a8f059a5f7ae36415054dd94f87a1224d64c2cbf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193332"
---
# Export-ModuleMember

## SINOPSE
Especifica os membros do módulo que são exportados.

## SYNTAX

```
Export-ModuleMember [[-Function] <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Export-ModuleMember** especifica os membros do módulo que são exportados de um arquivo de módulo de script (. psm1) ou de um módulo dinâmico criado usando o cmdlet New-Module.
Os membros do módulo incluem cmdlets, funções, variáveis e aliases.
Esse cmdlet pode ser usado somente em um arquivo de módulo de script ou um módulo dinâmico.

Se um módulo de script não incluir um comando **Export-ModuleMember** , as funções e os aliases no módulo de script serão exportados, mas as variáveis não serão.
Quando um módulo de script inclui comandos **Export-ModuleMember** , somente os membros especificados nos comandos **Export-ModuleMember** são exportados.
Você também pode usar **Export-ModuleMember** para suprimir ou exportar Membros que o módulo de script importa de outros módulos.

Um comando **Export-ModuleMember** é opcional, mas é uma prática recomendada.
Mesmo que o comando confirme os valores padrão, ele demonstra a intenção do autor do módulo.

## EXEMPLOS

### Exemplo 1: exportar funções e aliases em um módulo de script

```powershell
Export-ModuleMember -Function * -Alias *
```

Esse comando exporta todas as funções e aliases definidos no módulo de script.

### Exemplo 2: exportar funções e aliases específicos

```powershell
Export-ModuleMember -Function Get-Test, New-Test, Start-Test -Alias gtt, ntt, stt
```

Este comando exporta três aliases e três funções definidas no módulo de script.

Você pode usar esse formato de comando para especificar os nomes dos membros do módulo.

### Exemplo 3: exportar nenhum membro

```powershell
Export-ModuleMember
```

Este comando especifica que nenhum membro definido no módulo de script é exportado.

Esse comando impede que os membros do módulo sejam exportados, mas não oculta os membros.
Os usuários podem ler e copiar membros de módulo ou use o operador de chamada (&) para chamar membros de módulo que não são exportados.

### Exemplo 4: exportar uma variável específica

```powershell
Export-ModuleMember -Variable increment
```

Este comando exporta apenas a variável $increment do módulo de script.
Nenhum outro membro é exportado.

Se você quiser exportar uma variável, além de exportar as funções em um módulo, o comando **Export-ModuleMember** deverá incluir os nomes de todas as funções e o nome da variável.

### Exemplo 5: vários comandos de exportação

```powershell
# From TestModule.psm1
Function New-Test
{
    Write-Output 'I am New-Test function'
}
Export-ModuleMember -Function New-Test

function Validate-Test
{
    Write-Output 'I am Validate-Test function'
}
function Start-Test
{
    Write-Output 'I am Start-Test function'
}
Set-Alias stt Start-Test
Export-ModuleMember -Function Start-Test -Alias stt
```

Esses comandos mostram como vários comandos **Export-ModuleMember** são interpretados em um arquivo de módulo de script (. psm1).

Esses comandos criam um alias e três funções e, em seguida, exportam duas funções e o alias.

Sem os comandos **Export-ModuleMember** , todas as três funções e o alias seriam exportados.
Com os comandos **Export-ModuleMember** , somente as funções **New-Test** e **Start-Test** e o alias STT são exportados.

### Exemplo 6: exportar Membros em um módulo dinâmico

```powershell
New-Module -Script {function SayHello {"Hello!"}; Set-Alias Hi SayHello; Export-ModuleMember -Alias Hi -Function SayHello}
```

Este comando mostra como usar Export-ModuleMember em um módulo dinâmico que é criado usando o cmdlet **New-Module** .

Neste exemplo, **Export-ModuleMember** é usado para exportar o alias Hi e a função **SayHello** no módulo dinâmico.

### Exemplo 7: declarar e exportar uma função em um único comando

```powershell
# From TestModule.psm1
function Export
{
  param (
    [Parameter(Mandatory=$true)]
    [ValidateSet("function","variable")]
    $Type,
    [Parameter(Mandatory=$true)]
    $Name,
    [Parameter(Mandatory=$true)]
    $Value
    )

    if ($Type -eq "function")
    {
        Set-item "function:script:$Name" $Value
        Export-ModuleMember $Name
    }
    else
    {
    Set-Variable -scope Script $Name $Value
    Export-ModuleMember -variable $Name
    }
}

Export function New-Test {Write-Output 'I am New-Test function'}
function helper {Write-Output 'I am helper function'}

Export variable Interval 0
$Interval = 2
```

Este exemplo inclui uma função chamada **Export** que declara uma função ou cria uma variável e, em seguida, grava um `Export-ModuleMember` comando para a função ou variável.
Isso permite declarar e exportar uma função ou variável em um único comando.

Para usar a função de **exportação** , inclua-a em seu módulo de script.
Para exportar uma função, digite `Export` antes da palavra-chave **Function** .

Para exportar uma variável, use o seguinte formato para declarar a variável e definir seu valor:

`Export variable <variable-name> <value>`

Os comandos do exemplo mostram o formato correto.
Neste exemplo, somente a função **New-Test** e a variável $Interval são exportadas.

## PARAMETERS

### -Alias

Especifica os aliases exportados por meio do arquivo do módulo de script.
Digite os nomes de alias.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Cmdlet

Especifica os cmdlets exportados por meio do arquivo do módulo de script.
Digite os nomes de cmdlet.
Caracteres curinga são permitidos.

Não é possível criar cmdlets em um arquivo do módulo de script, mas você pode importar cmdlets de um módulo binário em um módulo de script e exportá-los novamente do módulo de script.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Função

Especifica as funções exportadas por meio do arquivo do módulo de script.
Digite os nomes de função.
Caracteres curinga são permitidos.
Você também pode canalizar cadeias de caracteres de nome de função para **Export-ModuleMember** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Variable

Especifica as variáveis exportadas por meio do arquivo do módulo de script.
Insira os nomes de variáveis, sem um cifrão.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

Você pode canalizar cadeias de caracteres de nome de função para este cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

* Para excluir um membro da lista de membros exportados, adicione um comando **Export-ModuleMember** que lista todos os outros membros, mas omita o membro que você deseja excluir.

## LINKS RELACIONADOS

[Get-Module](Get-Module.md)

[Import-Module](Import-Module.md)

[Remove-Module](Remove-Module.md)

[about_Modules](About/about_Modules.md)
