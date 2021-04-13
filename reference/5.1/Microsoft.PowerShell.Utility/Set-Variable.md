---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/06/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: a0a76ce53af872ef2004cf8bf8213265b435abe5
ms.sourcegitcommit: 241071803915ab7d544576b5652ac23349a86369
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "107027168"
---
# Set-Variable

## Sinopse
Define o valor de uma variável. Cria a variável se uma com o nome solicitado não existir.

## Sintaxe

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Descrição

O `Set-Variable` cmdlet atribui um valor a uma variável especificada ou altera o valor atual. Se a variável não existir, o cmdlet a criará.

## Exemplos

### Exemplo 1: definir uma variável e obter seu valor

Esses comandos definem o valor da `$desc` variável como `A description` e, em seguida, obtém o valor da variável.

```powershell
Set-Variable -Name "desc" -Value "A description"
Get-Variable -Name "desc"
```

```Output
Name                           Value
----                           -----
desc                           A description
```

### Exemplo 2: definir uma variável global, somente leitura

Este exemplo cria uma variável global, somente leitura que contém todos os processos no sistema e, em seguida, exibe todas as propriedades da variável.

```powershell
Set-Variable -Name "processes" -Value (Get-Process) -Option constant -Scope global -Description "All processes" -PassThru |
    Format-List -Property *
```

O comando usa o `Set-Variable` cmdlet para criar a variável. Ele usa o parâmetro **PassThru** para criar um objeto que representa a nova variável e usa o operador de pipeline ( `|` ) para passar o objeto para o `Format-List` cmdlet. Ele usa o parâmetro **Property** de `Format-List` com um valor de All ( `*` ) para exibir todas as propriedades da variável recém-criada.

O valor, `(Get-Process)` , é colocado entre parênteses para garantir que ele seja executado antes de ser armazenado na variável. Caso contrário, a variável conterá as palavras "**Get-Process**".

### Exemplo 3: entender as variáveis públicas versus privadas

Este exemplo mostra como alterar a visibilidade de uma variável para `Private` . Essa variável pode ser lida e alterada por scripts com as permissões necessárias, mas não fica visível para o usuário.

```
PS C:\> New-Variable -Name "counter" -Visibility Public -Value 26
PS C:\> $Counter
26

PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}
Counter               26

PS C:\> Set-Variable -Name "counter" -Visibility Private
PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"

PS C:\> .\use-counter.ps1
#Commands completed successfully.
```

Este comando mostra como alterar a visibilidade de uma variável para particular. Essa variável pode ser lida e alterada por scripts com as permissões necessárias, mas não fica visível para o usuário.

## Parâmetros

### -Description

Especifica a descrição da variável.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Excluir

Especifica uma matriz de itens que esse cmdlet exclui da operação. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um elemento ou padrão de caminho, como `*.txt` .
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

Permite que você crie uma variável com o mesmo nome de uma variável somente leitura existente, ou altere o valor de uma variável somente leitura.

Por padrão, você pode substituir uma variável, a menos que a variável tenha um valor de opção de `ReadOnly` ou `Constant` . Para obter mais informações, consulte o parâmetro **Option** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Incluir

Especifica uma matriz de itens que esse cmdlet inclui na operação. O valor desse parâmetro qualifica o parâmetro de **nome** . Insira um nome ou padrão de nome, como `c*` . Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

Especifica o nome da variável.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Opção

Especifica o valor da propriedade **Options** da variável.

Os valores válidos são:

- `None`: Não define opções. ( `None` é o padrão.)
- `ReadOnly`: Pode ser excluído. Não pode ser alterado, exceto pelo uso do parâmetro Force.
- `Constant`: Não pode ser excluído ou alterado. `Constant` é válido somente quando você está criando uma variável. Você não pode alterar as opções de uma variável existente para `Constant` .
- `Private`: A variável está disponível somente no escopo atual.
- `AllScope`: A variável é copiada para todos os novos escopos criados.

Esses valores são definidos como uma enumeração baseada em sinalizador. Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro. Os valores podem ser passados para o parâmetro de **opção** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores. O cmdlet combinará os valores usando uma operação binary ou. Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa a nova variável. Por padrão, este cmdlet não gera saída.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Escopo

Especifica o escopo da variável. Os valores aceitáveis para esse parâmetro são:

- `Global`
- `Local`
- `Script`
- `Private`
- Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai).

`Local` é o padrão.

Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Especifica o valor da variável.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Visibilidade

Determina se a variável é visível fora da sessão na qual ela foi criada. Esse parâmetro é projetado para uso em scripts e comandos que serão entregues a outros usuários.

Os valores válidos são:

- `Public`: A variável está visível. ( `Public` é o padrão.)
- `Private`: A variável não é visível.

Quando uma variável é privada, ela não aparece em listas de variáveis, como as retornadas por `Get-Variable` , ou em exibições da unidade **Variable:** . Comandos para ler ou alterar o valor de uma variável privada retornam um erro. No entanto, o usuário pode executar comandos que usam uma variável privada se os comandos tiverem sido escritos na sessão em que a variável foi definida.

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: Public
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

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

## Entradas

### System.Object

É possível canalizar um objeto que representa o valor da variável para `Set-Variable` .

## Saídas

### Nenhum ou System. Management. Automation. PSVariable

Quando você usa o parâmetro **PassThru** , o `Set-Variable` gera um objeto **System. Management. Automation. PSVariable** que representa a variável nova ou alterada.
Caso contrário, este cmdlet não gera nenhuma saída.

## Anotações

## Links Relacionados

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[New-Variable](New-Variable.md)

[Remove-Variable](Remove-Variable.md)
