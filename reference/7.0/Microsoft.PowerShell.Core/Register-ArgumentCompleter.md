---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-argumentcompleter?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ArgumentCompleter
ms.openlocfilehash: c81c50152209a922c486005b5919ac4a1e7295a2
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97490308"
---
# Register-ArgumentCompleter

## SINOPSE

Registra um argumento personalizado completo.

## SYNTAX

### Nativeset

```
Register-ArgumentCompleter -CommandName <String[]> -ScriptBlock <ScriptBlock> [-Native]
 [<CommonParameters>]
```

### PowerShellset

```
Register-ArgumentCompleter [-CommandName <String[]>] -ParameterName <String>
 -ScriptBlock <ScriptBlock> [<CommonParameters>]
```

## DESCRIPTION

O `Register-ArgumentCompleter` cmdlet registra um argumento personalizado de conclusão. Um argumento completo permite que você forneça preenchimento dinâmico de tabulação, em tempo de execução para qualquer comando que você especificar.

## EXEMPLOS

### Exemplo 1: registrar um argumento personalizado como completo

O exemplo a seguir registra um argumento Complete para o parâmetro **ID** do `Set-TimeZone` cmdlet.

```powershell
$scriptBlock = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)

    (Get-TimeZone -ListAvailable).Id | Where-Object {
        $_ -like "$wordToComplete*"
    } | ForEach-Object {
          "'$_'"
    }
}
Register-ArgumentCompleter -CommandName Set-TimeZone -ParameterName Id -ScriptBlock $scriptBlock
```

O primeiro comando cria um bloco de script que usa os parâmetros necessários que são passados quando o usuário pressiona a tecla <kbd>Tab</kbd>. Para obter mais informações, consulte a descrição do parâmetro **scriptblock** .

No bloco de script, os valores disponíveis para **ID** são recuperados usando o `Get-TimeZone` cmdlet. A propriedade **ID** para cada fuso horário é canalizada para o `Where-Object` cmdlet. O `Where-Object` cmdlet filtra todas as IDs que não começam com o valor fornecido pelo `$wordToComplete` , que representa o texto que o usuário digitou antes de pressionar a <kbd>tecla Tab</kbd>. As IDs filtradas são canalizadas para o `ForEach-Object` cmdlet que inclui cada valor entre aspas, caso o valor contenha espaços.

O segundo comando registra o argumento Complete, passando o scriptblock, a ID **ParameterName**  e o **CommandName** `Set-TimeZone` .

### Exemplo 2: adicionar detalhes aos valores de preenchimento de guia

O exemplo a seguir substitui a conclusão da Tabulação pelo parâmetro **Name** do `Stop-Service` cmdlet e retorna apenas os serviços em execução.

```powershell
$s = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)
    $services = Get-Service | Where-Object {$_.Status -eq "Running" -and $_.Name -like "$wordToComplete*"}
    $services | ForEach-Object {
        New-Object -Type System.Management.Automation.CompletionResult -ArgumentList $_.Name,
            $_.Name,
            "ParameterValue",
            $_.Name
    }
}
Register-ArgumentCompleter -CommandName Stop-Service -ParameterName Name -ScriptBlock $s
```

O primeiro comando cria um bloco de script que usa os parâmetros necessários que são passados quando o usuário pressiona a tecla <kbd>Tab</kbd>. Para obter mais informações, consulte a descrição do parâmetro **scriptblock** .

No bloco de script, o primeiro comando recupera todos os serviços em execução usando o `Where-Object` cmdlet. Os serviços são canalizados para o `ForEach-Object` cmdlet. O `ForEach-Object` cmdlet cria um novo objeto [System. Management. Automation. CompletionResult](/dotnet/api/system.management.automation.completionresult) e o popula com o nome do serviço atual (representado pela variável de pipeline `$_.Name` ).

O objeto **CompletionResult** permite que você forneça detalhes adicionais para cada valor retornado:

- **completionText** (cadeia de caracteres)-o texto a ser usado como o resultado da conclusão automática. Esse é o valor enviado para o comando.
- **listItemText** (cadeia de caracteres)-o texto a ser exibido em uma lista, como quando o usuário pressiona <kbd></kbd>o + <kbd>espaço</kbd>Ctrl. Isso é usado somente para exibição e não é passado para o comando quando selecionado.
- **ResultType** ([CompletionResultType](/dotnet/api/system.management.automation.completionresulttype)) – o tipo de resultado de conclusão.
- **dica de ferramenta** (cadeia de caracteres)-o texto da dica de ferramenta com detalhes a serem exibidos sobre o objeto.
  Isso fica visível quando o usuário seleciona um item depois de pressionar <kbd>Ctrl</kbd> + <kbd>espaço</kbd>.

O último comando demonstra que os serviços interrompidos ainda podem ser passados manualmente para o `Stop-Service` cmdlet. O preenchimento com Tab é o único aspecto afetado.

### Exemplo 3: registrar um argumento nativo personalizado completo

Você pode usar o parâmetro **nativo** para fornecer a conclusão de tabulação para um comando nativo. O exemplo a seguir adiciona Tab-Complete para a `dotnet` interface de linha de comando (CLI).

> [!NOTE]
> O `dotnet complete` comando só está disponível na versão 2,0 e superior da CLI dotnet.

```powershell
$scriptblock = {
    param($wordToComplete, $commandAst, $cursorPosition)
        dotnet complete --position $cursorPosition $commandAst.ToString() | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
        }
}
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock $scriptblock
```

O primeiro comando cria um bloco de script que usa os parâmetros necessários que são passados quando o usuário pressiona a tecla <kbd>Tab</kbd>. Para obter mais informações, consulte a descrição do parâmetro **scriptblock** .

No bloco de script, o `dotnet complete` comando é usado para executar a conclusão da Tabulação.
Os resultados são canalizados para o `ForEach-Object` cmdlet que usa o **novo** método estático da classe [System. Management. Automation. CompletionResult](/dotnet/api/system.management.automation.completionresult) para criar um novo objeto **CompletionResult** para cada valor.

## PARAMETERS

### -CommandName

Especifica o nome dos comandos como uma matriz.

```yaml
Type: System.String[]
Parameter Sets: NativeSet, PowerShellSet
Aliases:

Required: True (NativeSet), False (PowerShellSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nativo

Indica que o argumento completo é para um comando nativo em que o PowerShell não pode concluir nomes de parâmetro.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NativeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterName

Especifica o nome do parâmetro cujo argumento está sendo concluído. O nome do parâmetro especificado não pode ser um valor enumerado, como o parâmetro **ForegroundColor** do `Write-Host` cmdlet.

Para obter mais informações sobre enums, consulte [about_Enum](./About/about_Enum.md).

```yaml
Type: System.String
Parameter Sets: PowerShellSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Especifica os comandos a serem executados para executar a conclusão da Tabulação. O bloco de script que você fornece deve retornar os valores que concluem a entrada. O bloco de script deve desdistribuir os valores usando o pipeline ( `ForEach-Object` , `Where-Object` , etc.) ou outro método adequado. Retornar uma matriz de valores faz com que o PowerShell trate toda a matriz como **um** valor de conclusão de tabulação.

O bloco de script deve aceitar os seguintes parâmetros na ordem especificada abaixo. Os nomes dos parâmetros não são importantes porque o PowerShell passa os valores por posição.

- `$commandName` (Posição 0)-esse parâmetro é definido como o nome do comando para o qual o bloco de script está fornecendo preenchimento com Tab.
- `$parameterName` (Posição 1)-esse parâmetro é definido como o parâmetro cujo valor requer preenchimento com Tab.
- `$wordToComplete` (Posição 2)-esse parâmetro é definido como o valor que o usuário forneceu antes de pressionar a <kbd>tecla Tab</kbd>. O bloco de script deve usar esse valor para determinar valores de preenchimento de guia.
- `$commandAst` (Posição 3)-esse parâmetro é definido como a árvore de sintaxe abstrata (AST) para a linha de entrada atual. Para obter mais informações, consulte [AST Class](/dotnet/api/system.management.automation.language.ast).
- `$fakeBoundParameters` (Posição 4)-esse parâmetro é definido como uma tabela de hash que contém o `$PSBoundParameters` para o cmdlet, antes da <kbd>guia</kbd>ser pressionada pelo usuário. Para obter mais informações, consulte [about_Automatic_Variables](./About/about_Automatic_Variables.md).

Quando você especifica o parâmetro **nativo** , o bloco de script deve usar os seguintes parâmetros na ordem especificada. Os nomes dos parâmetros não são importantes porque o PowerShell passa os valores por posição.

- `$wordToComplete` (Posição 0)-esse parâmetro é definido como o valor que o usuário forneceu antes de pressionar a <kbd>tecla Tab</kbd>. O bloco de script deve usar esse valor para determinar valores de preenchimento de guia.
- `$commandAst` (Posição 1)-esse parâmetro é definido como a árvore de sintaxe abstrata (AST) para a linha de entrada atual. Para obter mais informações, consulte [AST Class](/dotnet/api/system.management.automation.language.ast).
- `$cursorPosition` (Posição 2)-esse parâmetro é definido como a posição do cursor quando a <kbd>guia</kbd>do usuário é pressionada.

Você também pode fornecer um **ArgumentCompleter** como um atributo de parâmetro. Para obter mais informações, consulte [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](./About/about_CommonParameters.md).

## ENTRADAS

### Nenhum

Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### Nenhum

Esse cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS
